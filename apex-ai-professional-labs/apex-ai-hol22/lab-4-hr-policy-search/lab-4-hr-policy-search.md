# Lab 4: Build the HR Policy Search Page in ESS

## Introduction

This lab prepares the HR policy data for semantic search and then creates a dedicated search page in ESS. You will embed policy content, build the search configuration, and test natural-language prompts such as annual leave policy, benefits information, and employee onboarding requirements.

Estimated Lab Time: 15 minutes

### Objectives

In this lab, you will:

- Generate embeddings for HR policy content.

- Create an Oracle AI Vector Search configuration for policy records.

- Create an HR Policy Search page in ESS.

- Test semantic ranking for policy-related natural-language questions.

## Task 1: Generate HR policy embeddings

1. Navigate back to your APEX workspace.

2. Navigate to **SQL Workshop** and then **SQL Commands**. **Run** the following SQL Query:

    ```
    <copy>
    UPDATE tms_hr_policy
    SET embedding_vector = apex_ai.get_vector_embeddings(
            p_value => title || ' ' || content,
            p_service_static_id => 'db-onnx-model'
        );
    </copy>
    ```

    ![Generating embeddings for all HR policy records](images/generate-hr-policy-embeddings.png)

3. To verify the embedding status, **Run** the following SQL Query:

    ```
    <copy>
    SELECT policy_id,
           category,
           title,
           CASE
               WHEN embedding_vector IS NULL THEN 'NOT EMBEDDED'
               ELSE 'EMBEDDED'
           END AS embedding_status
    FROM tms_hr_policy
    ORDER BY category, title;
    </copy>
    ```

    Confirm that the policy rows show EMBEDDED.

    ![Verifying HR policy embedding status for all records](images/verify-hr-policy-embedding-status.png)

## Task 2: Create the HR Policy Vector Search configuration

1. Open **Employee Self-Service Portal (ESS)** application.

2. Navigate to **Shared Components**.

    ![Opening Search Configurations in ESS Shared Components](images/open-ess-shared-components.png)

3. Under **Navigation and Search**, select **Search Configurations**.

    ![Opening Search Configurations in ESS Shared Components](images/open-ess-search-configurations.png)

4. Click **Create**.

    ![Opening Search Configurations in ESS Shared Components](images/ess-search-configurations-list.png)

5. Configure the settings as follows:

    - Name: **HR Policy Semantic Search**

    - Search Type: **Oracle AI Vector Search**

6. Click **Next**.

    ![Opening Search Configurations in ESS Shared Components](images/create-hr-policy-search-configuration.png)

7. Select **DB ONNX Model** as Vector Provider.

8. For Table/View Owner, select **TMS\_HR\_POLICY** and click **Next**.

    ![Opening Search Configurations in ESS Shared Components](images/select-hr-policy-search-source.png)

9. For Column Mapping, enter/select the following:

    - Primary Key: **POLICY_ID (Number)**

    - Vector Column: **EMBEDDING_VECTOR (Vector)**

    - Title Column: **TITLE (Varchar2)**

    - Description Column: **CONTENT (Clob)**

10. Click **Create Search Configuration**

    ![Configuring HR Policy Semantic Search vector search settings](images/map-hr-policy-search-columns.png)

## Task 3: Create the HR Policy Search page

1. Navigate to **Application ID**.

    ![Configuring HR Policy Semantic Search vector search settings](images/hr-policy-search-configuration-created.png)

2. Click **Create Page**.

    ![Selecting Search Page component type in ESS page creation](images/open-ess-create-page.png)

3. Select **Search Page**.

    ![Selecting Search Page component type in ESS page creation](images/select-search-page-component.png)

4. Configure the following:

    - Name: **HR Policy Search**

    - Search Configurations: Select **HR Policy Semantic Search**

    - Parent Navigation Menu Entry: **HR Info**

5. Click **Create Page**.

    ![Selecting Search Page component type in ESS page creation](images/configure-hr-policy-search-page.png)

    ![Selecting Search Page component type in ESS page creation](images/set-hr-policy-search-navigation.png)

6. Select the **P24_SEARCH** page item. In the Property Editor, update the following:

    - Appearance > Value Placeholder: **Search HR policies by meaning...**

    ![HR Policy Search page configured and saved in Page Designer](images/set-hr-policy-search-placeholder.png)

7. Click **Save and Run**.

## Task 4: Validate policy search behavior

1. In HR Policy Search page, search for annual leave.

    Enter:

    ```
    <copy>
    annual leave policy
    </copy>
    ```

    Relevant leave-related policies should rank higher.

    ![HR Policy Search results for an annual leave query](images/hr-policy-search-annual-leave-results.png)

2. Search for benefits information.

    Enter:

    ```
    <copy>
    what benefits are available to employees
    </copy>
    ```

    Relevant benefit-related policies should rank higher.

    ![HR Policy Search results for an employee benefits query](images/hr-policy-search-benefits-results.png)

3. Search for onboarding requirements.

    Enter:

    ```
    <copy>
    new employee onboarding requirements
    </copy>
    ```

    Relevant onboarding and employee-policy content should rank higher.

    ![HR Policy Search results for an employee benefits query](images/new-employee-search.png)

## Summary

The HR policy search page now uses semantic ranking to match user intent across policy titles and content. That makes the search experience more natural and supports downstream AI agent grounding for onboarding and policy questions.

## Acknowledgements

- **Author** - Ankita Beri, Senior Product Manager
- **Last Updated By/Date** - Ankita Beri, August 2026
