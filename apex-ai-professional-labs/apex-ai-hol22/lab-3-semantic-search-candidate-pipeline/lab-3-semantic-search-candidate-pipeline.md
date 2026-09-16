# Lab 3: Implement Semantic Search on the Candidate Pipeline in TAP

## Introduction

This lab adds semantic search to the Candidate Pipeline in TAP. You will create a vector search configuration, add a search page item, and validate ranking against natural-language skills queries such as low-code Oracle application developer, cloud infrastructure engineer, and AI database developer.

Estimated Lab Time: 10 minutes

### Objectives

In this lab, you will:

- Create an Oracle AI Vector Search configuration for the candidate table.

- Add a semantic search input to the Candidate Pipeline page.

- Connect the search region to the vector source.

- Validate result ranking with natural-language searches.

## Task 1: Create the Vector Search Configuration

1. Open **Talent Acquisition Portal(TAP)** application.

2. From **App Builder** home page and navigate to **Shared Components**.

    ![Opening Search Configurations in Shared Components](images/open-tap-shared-components.png)

3. Under **Navigation and Search**, select **Search Configurations**.

    ![Opening Search Configurations in Shared Components](images/open-tap-search-configurations.png)

4. Click **Create**.

    ![Opening Search Configurations in Shared Components](images/tap-search-configurations-list.png)

5. Configure the settings as follows:

    - Name: **Candidate Semantic Search**

    - Search Type: **Oracle AI Vector Search**

6. Click **Next**.

    ![Configuring Candidate Semantic Search vector search settings](images/create-candidate-search-configuration.png)

7. Select **DB ONNX Model** as Vector Provider.

8. For Table/View Owner, select **TMS_CANDIDATES** and click **Next**.

    ![Configuring Candidate Semantic Search vector search settings](images/select-candidate-search-source.png)

9. For Column Mapping, enter/select the following:

    - Primary Key: **CANDIDATE_ID (Number)**

    - Vector Column: **SKILLS_VECTOR (Vector)**

    - Title Column: **FIRST_NAME (Varchar2)**

    - Description Column: **SKILLS_TEXT (Varchar2)**

10. Click **Create Search Configuration**

    ![Configuring Candidate Semantic Search vector search settings](images/map-candidate-search-columns.png)

## Task 2: Add the search item and region on the Candidate Pipeline page

1. Navigate to your **Application ID**.

    ![Opening Page 4 Candidate Pipeline in Page Designer](images/candidate-search-configuration-created.png)

2. Select **4: Candidate Pipeline** page.

    ![Opening Page 4 Candidate Pipeline in Page Designer](images/open-candidate-pipeline-page.png)

3. Right-click **Body** and select **Create Page Item**.

4. Drag the page item above **P4\_REQ_ID** page item. In the Property Editor, enter/select the following:

    - Under Identification:

        - Name: **P4\_SEMANTIC\_SEARCH**

        - Type: **Text Field**

    - Label > Label: **Search Candidates**

    - Appearance > Value Placeholder: **Search candidates by skills or experience...**

    ![Creating P4_SEMANTIC_SEARCH text field item](images/create-semantic-search-page-item.png)

5. Now, right-click on **Body** and select **Create Region**. Drag it below P4\_SEMANTIC\_SEARCH page item.

6. In the Property Editor, enter/select the following:

    - Under Identification:

        - Name: **Semantic Candidate Search**

        - Type: **Search**

    ![Adding Search region to Candidate Pipeline page](images/create-semantic-candidate-search-region.png)

7. In the Property Editor, select **Attributes** tab and enter/select the following:

    - Under Settings:

        - Search Page Item: **P4\_SEMANTIC\_SEARCH**

        - Search as You Type: **Toggle On**

        - Minimum Characters: **3**

    ![Configuring search region attributes and search as you type](images/configure-semantic-search-region.png)

8. Under the **Semantic Candidate Search** region, select **Search Sources** and configure it with the following:

    - Under Identification:

        - Name: **Candidate Semantic Search**

        - Search Configuration: **Candidate Semantic Search**

9. Click **Save and Run**.

    ![Adding Search Source configured to Candidate Semantic Search](images/add-candidate-search-source.png)

    ![Saving the Page Designer changes to Candidate Pipeline page](images/save-and-run-candidate-search-page.png)

## Task 3: Test Semantic Candidate Ranking

1. Open the **Candidate Pipeline** in **TAP** and enter the following search text in the Search Candidates field:

    ```
    <copy>
    low code Oracle application developer
    </copy>
    ```

    Candidates with skills such as Oracle APEX, PL/SQL, ORDS, REST APIs, and Oracle Database should rank higher in the results.

    ![Candidate Pipeline showing search results for low-code Oracle developer role](images/candidate-pipeline-low-code-results.png)

2. Now, let's test an OCI-focused search. Search for:

    ```
    <copy>
    cloud infrastructure engineer
    </copy>
    ```

    Candidates with OCI Compute, OCI Networking, IAM, Object Storage, and cloud architecture experience should rank higher.

    ![Candidate Pipeline showing search results for cloud infrastructure engineer role](images/candidate-pipeline-cloud-results.png)

3. Test an AI and vector-focused search. Search for:

    ```
     <copy>
    AI semantic search database developer
     </copy>
    ```

    Candidates with Oracle AI Database, AI Vector Search, VECTOR, ONNX embedding models, SQL, and PL/SQL should rank higher.

    ![Candidate Pipeline showing search results for AI and vector-focused database developer role](images/candidate-pipeline-ai-results.png)

## Summary

The Candidate Pipeline now supports semantic search using the vector embeddings generated from candidate skill descriptions. The ranking aligns with the meaning of the prompt rather than exact word matching alone.

## Acknowledgements

- **Author** - Ankita Beri, Senior Product Manager
- **Last Updated By/Date** - Ankita Beri, August 2026
