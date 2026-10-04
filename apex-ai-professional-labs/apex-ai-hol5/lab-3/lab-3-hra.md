# Create the HR Analytics App from a File

## Introduction

In this lab, you will create an HR Analytics App (HAA) from the provided candidate pipeline CSV file. You will upload the file, load its data into a database table, and let APEX generate a starter application that you can run and review.

Estimated time: 5 minutes

### Objectives

In this lab, you will:

- Create HR Analytics App (HAA) using Application from File.

### What You Will Build

- **HR Analytics App (HAA)**: Created from `candidate_pipeline_sample.csv` using Application from File.

## Task 1: Create the HR Analytics App from a File

In this task, you create the HR Analytics App from a CSV file upload. This application shows how APEX can turn a spreadsheet-style data file into a working application with a table and report pages.

1. Download the provided CSV file:

    [candidate\_pipeline\_sample.csv](files/candidate_pipeline_sample.csv)

    This file contains sample candidate pipeline data that APEX uses to create the starter analytics table.

2. From the left navigation menu, click the **App Builder** icon.

    ![App Builder with Employee Self-Service Portal created](images/app-builder-ess-created.png " ")

3. Click **Create**.

    ![Create an app from a file](images/app-builder-create-haa-from-file.png " ")

4. Select **Create App From a File**.

    ![HR Analytics App from file option](images/haa-create-app-from-file.png " ")

5. Upload or Drag and Drop `candidate_pipeline_sample.csv`.

    ![Upload the candidate pipeline CSV file](images/haa-upload-csv-file.png " ")

6. For **Table Name**, enter: **TMS\_CANDIDATE\_PIPELINE** and click **Load Data**.

    ![Set the generated table name](images/haa-load-data-table-name.png " ")

    This table stores the uploaded candidate pipeline data for the HR Analytics App.

7. Click **Create Application**.

    ![CSV data loaded and ready to create application](images/haa-data-loaded-create-application.png " ")

    APEX uses the uploaded data to generate an application with starter pages automatically.

8. For the application **Name**, enter: **HR Analytics App** and click **Create Application**.

    ![Review HR Analytics App generated pages](images/haa-review-pages-create-application.png " ")

9. Click **Run Application**.

    ![HR Analytics App home in App Builder](images/haa-application-home-builder.png " ")

10. Log in to the application.

    ![HR Analytics App sign in page](images/haa-sign-in-page.png " ")

11. Confirm that the generated pages load.

    ![HR Analytics App running home page](images/haa-home-page-running.png " ")

    This is a quick starter application.

## Summary

In this lab, you created and ran the HR Analytics App from `candidate_pipeline_sample.csv`.

- Loaded the candidate pipeline data into the `TMS_CANDIDATE_PIPELINE` table.
- Let APEX generate starter application pages from the uploaded data.
- Ran the application and confirmed that the generated pages load.

## Acknowledgements

- **Author** - Ankita Beri, Senior Product Manager
- **Last Updated By/Date** - Ankita Beri, Senior Product Manager, July 2026
