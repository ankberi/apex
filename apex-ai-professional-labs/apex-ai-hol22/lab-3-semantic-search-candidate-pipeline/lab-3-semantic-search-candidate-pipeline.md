# Lab 3: Implement Semantic Search on the Candidate Pipeline in TAP

## Introduction

This lab adds semantic search to the Candidate Pipeline in TAP. You will create a vector search configuration, add a search page item, and validate ranking against natural-language skills queries such as low-code Oracle application developer, cloud infrastructure engineer, and AI database developer.

Estimated Lab Time: 10 minutes

### Objectives

In this lab, you will:
* create an Oracle AI Vector Search configuration for the candidate table,
* add a semantic search input to the Candidate Pipeline page,
* connect the search region to the vector source,
* validate result ranking with natural-language searches.

## Task 1: Create the vector search configuration

1. Open TAP and navigate to Shared Components.

    Go to Shared Components and then Search Configurations, and select Create.

    ![Opening Search Configurations in Shared Components](images/open-tap-search-configurations.png)

2. Create the new configuration.

    Configure the settings as follows:

    - Type: Oracle AI Vector Search
    - Name: Candidate Semantic Search
    - Static ID: CANDIDATE_SEMANTIC_SEARCH
    - Source: TMS_CANDIDATES
    - Primary Key: CANDIDATE_ID
    - Vector Column: SKILLS_VECTOR
    - Vector Provider: DB ONNX Model

    ![Configuring Candidate Semantic Search vector search settings](images/create-candidate-search-configuration.png)

    Save the Search Configuration.

    ![Saving the Candidate Semantic Search configuration](images/candidate-search-configuration-created.png)

## Task 2: Add the search item and region on the Candidate Pipeline page

1. Open Page 4: Candidate Pipeline in Page Designer.

    ![Opening Page 4 Candidate Pipeline in Page Designer](images/open-candidate-pipeline-page.png)

2. Create a page item above the Candidate Pipeline regions.

    Use the following values:

    - Name: P4_SEMANTIC_SEARCH
    - Type: Text Field
    - Label: Search Candidates
    - Placeholder: Search candidates by skills or experience...

    ![Creating P4_SEMANTIC_SEARCH text field item](images/create-semantic-search-page-item.png)

3. Create a search region.

    Add a new region with the following details:

    - Type: Search
    - Title: Semantic Candidate Search

    ![Adding Search region to Candidate Pipeline page](images/create-semantic-candidate-search-region.png)

4. Configure the search region.

    In the region attributes, set:

    - Search Page Item: P4_SEMANTIC_SEARCH
    - Search as You Type: On
    - Minimum Characters: 3

    ![Configuring search region attributes and search as you type](images/configure-semantic-search-region.png)

5. Add the Search Source.

    Under the Search region, create a Search Source and configure it with:

    - Name: Candidate Semantic Search
    - Search Configuration: Candidate Semantic Search

    ![Adding Search Source configured to Candidate Semantic Search](images/add-candidate-search-source.png)

    Save the page.

    ![Saving the Page Designer changes to Candidate Pipeline page](images/save-and-run-candidate-search-page.png)


## Task 3: Test semantic candidate ranking

1. Run the Candidate Pipeline page.

    Open the Candidate Pipeline in TAP and enter the following search text in the Search Candidates field:

    ```text
    low code Oracle application developer
    ```

    Candidates with skills such as Oracle APEX, PL/SQL, ORDS, REST APIs, and Oracle Database should rank higher in the results.

    ![Candidate Pipeline showing search results for low-code Oracle developer role](images/candidate-pipeline-low-code-results.png)


2. Test an OCI-focused search.

    Search for:

    ```text
    cloud infrastructure engineer
    ```

    Candidates with OCI Compute, OCI Networking, IAM, Object Storage, and cloud architecture experience should rank higher.

    ![Candidate Pipeline showing search results for cloud infrastructure engineer role](images/candidate-pipeline-cloud-results.png)


3. Test an AI and vector-focused search.

    Search for:

    ```text
    AI semantic search database developer
    ```

    Candidates with Oracle AI Database, AI Vector Search, VECTOR, ONNX embedding models, SQL, and PL/SQL should rank higher.

    ![Candidate Pipeline showing search results for AI and vector-focused database developer role](images/candidate-pipeline-ai-results.png)

## Summary

The Candidate Pipeline now supports semantic search using the vector embeddings generated from candidate skill descriptions. The ranking aligns with the meaning of the prompt rather than exact word matching alone.

## Acknowledgements
* **Author** - AI-generated LiveLabs workshop authoring workflow
* **Contributors** - Module 22 source material and APEX workshop guidance
* **Last Updated By/Date** - Copilot, August 2026
