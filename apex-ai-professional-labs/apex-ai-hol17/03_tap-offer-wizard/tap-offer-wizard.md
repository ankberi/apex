# Build the TAP Offer Wizard Using Collections

## Introduction

In this lab, you will create a two-step Offer Wizard in the Talent Acquisition Portal. The first step collects offer terms and stages them in an APEX Collection. The second step reviews the staged values, creates the offer row, sends an offer email, and removes the collection.

Estimated Time: 5 minutes

### Objectives

In this lab, you will:

- Create a two-step Offer Wizard.
- Add offer term items to the first wizard step.
- Populate the job ID from the selected candidate.
- Stage offer terms in an APEX Collection.
- Review and send the offer.
- Clean up the collection when the user finishes or cancels.

## Task 1: Create the Offer Wizard

The wizard replaces a single Offer Form with a guided flow that separates offer entry from review and send actions.

1. Open **App Builder**.

2. Open the **Talent Acquisition Portal** application.

    ![Talent Acquisition Portal application in App Builder](images/01-open-talent-acquisition-portal.png)

3. Click **Create Page**.

    ![Create Page button in the Talent Acquisition Portal application](images/02-click-create-page.png)

4. Select **Wizard**.

    ![Wizard page type selected in the Create a Page dialog](images/03-select-wizard-page-type.png)

5. Select **Two-Step Wizard**.

6. Enter or select the following settings:

    - Page Definition > Wizard Name: **Offer Wizard**

    - Under Wizard Steps:

        | Step Number | Page Number | Name |
        | ---- | ---- | ---- |
        | 1 | 16 | Offer Terms |
        | 2 | 19 | Preview & Send |

        *Note - Delete rest of the steps. We only need 2 steps wizard for this task*

    - Navigation > Parent Navigation Menu Entry: **Offers**

7. Click **Create Wizard**.

    ![Wizard steps renamed to Offer Terms and Preview and Send](images/06-name-offer-wizard-steps.png)

    *Note: The source uses page 16 for **Offer Terms** and page 19 for **Preview & Send**. Your generated page numbers may differ.*

## Task 2: Configure Step 1 for Offer Terms

Step 1 collects offer values and stages them in `OFFER_COLLECTION`.

1. Open the first wizard step in Page Designer.

2. In the left pane, right-click **Offer Terms** region and select **Create Page Item**.

    ![Offer Terms page open in Page Designer](images/07-create-offer-terms-page-item.png)

3. In the **Offer Terms** region, add the following items:

    | Item | Type |
    | --- | --- |
    | `P16_CANDIDATE_ID` | Select List |
    | `P16_JOB_ID` | Hidden |
    | `P16_SALARY` | Number Field |
    | `P16_START_DATE` | Date Picker |
    | `P16_EXPIRY_DATE` | Date Picker |

4. Select `P16_CANDIDATE_ID` page item and enter/select the following:

    - Under List of Values:

        - Type: **Shared Component**

        - List of Value: **TMS_CANDIDATES.FIRST_NAME**

    ![Candidate select list item on the Offer Terms page](images/08-candidate-select-list-item.png)

5. Right-click `P16_CANDIDATE_ID` page item and select **Create Dynamic Action**.

    ![Create Dynamic Action menu for the candidate item](images/09-create-candidate-dynamic-action.png)

6. In the Property Editor, enter Name as **Derive Job Id**.

    ![Derive Job ID dynamic action configured on candidate change](images/10-derive-job-id-dynamic-action.png)

7. Select **Show** True action and enter/select the following:

    - Identification > Type: **Set Value**

    - Under Settings:

        - Set Type: **SQL Query**

        - SQL Query: Copy and Paste the following code:

        ```
        <copy>
        SELECT r.job_id
        FROM   tms_job_requisitions r
        JOIN   tms_candidates      c ON c.req_id = r.req_id
        WHERE  c.candidate_id = :P16_CANDIDATE_ID
        </copy>
        ```

        - Item to Submit: `P16_CANDIDATE_ID`

    - Under Affected Elements:

        - Selection Type: **Item(s)**

        - Item (s): `P16_JOB_ID`

    ![Set Value action query for deriving the job ID](images/11-set-value-job-id-query.png)

    ![Affected item set to return the derived job ID](images/22-return-job-id-affected-item.png)

8. Select `P16_SALARY` and enter the following:

    - Appearance > Format mask: `FML999G999G999D00`

    ![Set Value action query for deriving the job ID](images/14-salary-number-field.png)

9. Navigate to **Processing** tab and right-click **Processing** and select **Create Process**.

    ![Create Process menu in the Processing tab](images/12-create-stage-to-collection-process.png)

10. In the Property Editor, enter/select the following:

    - Identification > Name: **Stage to collection**

    - Source > PL/SQL Code: Copy and Paste the following code:

    ```
    <copy>
    BEGIN
        APEX_COLLECTION.CREATE_OR_TRUNCATE_COLLECTION('OFFER_COLLECTION');

        APEX_COLLECTION.ADD_MEMBER(
            p_collection_name => 'OFFER_COLLECTION',
            p_seq             => 1,
            p_c001            => :P16_CANDIDATE_ID,
            p_c002            => :P16_JOB_ID,
            p_n001            => TO_NUMBER(REPLACE(:P16_SALARY, ',')),
            p_d001            => :P16_START_DATE,
            p_d002            => :P16_EXPIRY_DATE
        );
    END;
    </copy>
    ```

    ![Stage to Collection process configured with PL/SQL code](images/13-stage-to-collection-process-code.png)

## Task 3: Add Step 1 Cancellation Logic

The cancel action must remove the staged offer collection before returning the user to the portal home page.

1. Navigate to **Rendering Pane**, right-click the **Cancel** button and select **Create Trigger Action**.

    ![Create trigger action from the Cancel button](images/16-create-cancel-trigger-action.png)

2. In the Property Editor, enter/select the following:

    - Settings > PL/SQL Code: Copy and paste the following code:

    ```
    <copy>
    IF APEX_COLLECTION.COLLECTION_EXISTS('OFFER_COLLECTION') THEN
        APEX_COLLECTION.DELETE_COLLECTION('OFFER_COLLECTION');
    END IF;

    APEX_UTIL.REDIRECT_URL('f?p=&APP_ID.:HOME:&SESSION.');
    </copy>
    ```

3. Click **Save**.

    ![Cancel cleanup server-side code for deleting the offer collection](images/17-cancel-cleanup-server-code.png)

## Task 4: Configure Step 2 for Preview and Send

Step 2 shows the staged offer data, creates the final offer row, and sends the offer email.

1. From the Page Designer toolbar, navigate the Page Selector and select Page **19**: Preview & Send**.

    ![Page Finder with Preview and Send selected](images/18-open-preview-send-page.png)

2. Right-click **Preview & Send** region and select **Create Page Item**.

    ![Create page item on the Preview and Send wizard step](images/19-create-preview-page-item.png)

3. Add the following page items:

    | Name | Type |
    | --- | --- |
    | `P19_CANDIDATE` | Display Only |
    | `P19_JOB` | Display Only |
    | `P19_SALARY` | Display Only |
    | `_P19_START` | Display Only |
    | `P19_EXPIRY` | Display Only |
    | `P19_OFFER_TO` | Hidden |

    ![Candidate display-only item on the Preview and Send step](images/20-preview-candidate-display-item.png)

4. Select `P19_OFFER_TO` page item and enter the following:

    - Under Default:

        - Type:  **SQL Query return Single Value**

        - SQL Query returning Single Value: Copy and paste the following code:

        ```
        <copy>
        SELECT email
        FROM tms_candidates
        WHERE candidate_id = :P19_CANDIDATE_ID;
        </copy>
        ```

    ![Offer email recipient default SQL query](images/21-offer-email-default-query.png)

## Task 5: Create Offer Processing

The final processing step reads the staged collection row, creates the offer, and deletes the collection.

1. Navigate **Processing** tab, right-click **Processing** and select **Create Process**.

2. In the Property Editor, enter/select the following:

    - 

3. For **PL/SQL Code**, enter:

    <copy>

    ```sql
    DECLARE
        v_cand_id NUMBER;
        v_job_id  NUMBER;
        v_salary  NUMBER;
        v_start   DATE;
        v_expiry  DATE;
    BEGIN
        SELECT TO_NUMBER(c001),
               TO_NUMBER(c002),
               n001,
               d001,
               d002
        INTO   v_cand_id,
               v_job_id,
               v_salary,
               v_start,
               v_expiry
        FROM   apex_collections
        WHERE  collection_name = 'OFFER_COLLECTION'
        AND    seq_id = 1;

        INSERT INTO tms_offers (
            candidate_id,
            req_id,
            offered_salary,
            start_date,
            expiry_date,
            status
        )
        VALUES (
            v_cand_id,
            v_job_id,
            v_salary,
            v_start,
            v_expiry,
            'Sent'
        )
        RETURNING offer_id INTO :P19_OFFER_ID;

        APEX_COLLECTION.DELETE_COLLECTION('OFFER_COLLECTION');
    END;
    ```

    </copy>

4. Create another process named **SEND_OFFER_EMAIL**.

5. Set the type to **Send E-Mail**.

6. Configure it to run after **CREATE_OFFER**.

7. Enter or select the following settings:

    - Template: **OFFER_SENT**
    - To: `&P19_OFFER_TO.`

8. Configure the email placeholders:

    | Placeholder | Value |
    | --- | --- |
    | `CANDIDATE_NAME` | `SELECT first_name || ' ' || last_name FROM tms_candidates WHERE candidate_id = :P16_CANDIDATE_ID` |
    | `JOB_TITLE` | `SELECT job_title FROM tms_jobs WHERE job_id = :P16_JOB_ID` |
    | `OFFERED_SALARY` | `TO_CHAR(:P16_SALARY, 'FML999G999G999D00')` |
    | `START_DATE` | `:P16_START_DATE` |
    | `EXPIRY_DATE` | `:P16_EXPIRY_DATE` |

9. Create a success branch to the **Offer Management** page.

    The source identifies this target as page 14.

10. Add the same cancel cleanup logic from Task 3 to this wizard step.

## Task 6: Test the Offer Wizard

Test both the finish path and the cancel path.

1. Run the Offer Wizard.

2. Enter offer data on the first step.

3. Click **Next**.

4. Review the offer on the second step.

5. Click **Finish**.

6. Confirm that:

    - A row exists in `TMS_OFFERS`.
    - The email appears in `APEX_MAIL_LOG`.
    - `OFFER_COLLECTION` no longer exists.

7. Run the wizard again and click **Cancel** on each step.

8. Confirm that no offer row is inserted and the collection is removed.

## Summary

You created a two-step Offer Wizard in the Talent Acquisition Portal. The wizard stages offer terms in an APEX Collection, previews the staged offer, creates the final offer row, sends an email, and clears the collection when the user finishes or cancels.

## Acknowledgements

**Author** - Ankita Beri, Senior Product Manager; Roopesh Thokala, Principal Product Manager

**Last Updated By/Date** - Ankita Beri, August 12, 2026
