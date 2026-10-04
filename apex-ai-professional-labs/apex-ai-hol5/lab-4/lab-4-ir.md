# Add Pages to the Talent Acquisition Portal

## Introduction

In this lab, you will extend the Talent Acquisition Portal with interactive report pages and forms for offers and jobs. APEX uses the existing table definitions and primary keys to create pages for managing records and to recognize relationships between related data.

Estimated time: 5 minutes

### Objectives

In this lab, you will:

- Add table-driven pages to Talent Acquisition Portal (TAP).

## Task 1: Add Pages to the Talent Acquisition Portal

In this task, you add two more table-driven pages to the Talent Acquisition Portal. These pages show how APEX can quickly create working CRUD pages for existing database tables.

1. From the left navigation menu, click the **App Builder** icon.

    ![App Builder after HR Analytics App is created](images/app-builder-haa-created.png " ")

2. Click **Talent Acquisition Portal** application.

    ![Open Talent Acquisition Portal in App Builder](images/app-builder-select-tap.png " ")

3. Click **Create Page**.

    ![Talent Acquisition Portal Create Page button](images/tap-application-home-create-page.png " ")

4. Under **Component** tab, select **Interactive Report**.

    ![Select Interactive Report for Offer Management](images/create-page-select-interactive-report.png " ")

5. For the Create Interactive Report page, enter or select the following:

    - Under Page Definition:

        - Page Name: **Offer Management**

        - Include Form Page: **Toggle On**

        - Form Page Name: **Form on Offers**

    - Under Data Source:

        - Data Source: **Local Database**

        - Table or View: **TMS_OFFERS**

6. Click **Next**.

    ![Offer Management page definition](images/offer-management-page-definition.png " ")

    This page gives recruiters a place to review offer records and open a form for offer details.

7. For **Primary Key Column 1**, select **OFFER_ID (Number)** and click **Create Page**.

    ![Offer Management primary key settings](images/offer-management-primary-key.png " ")

    APEX uses the table metadata to detect relationships to `CANDIDATES` and `JOB_REQUISITIONS`.

8. In Page Designer, click **Save and Run**.

    ![Offer Management page in Page Designer](images/offer-management-page-designer.png " ")

9. Confirm that the page works immediately without additional configuration.

    ![Offer Management running page](images/offer-management-running-page.png " ")

10. Return to App Builder and navigate to Page Designer toolbar, hover over **+v** and select **Page**.

    ![Create another page from the Offer Management page](images/offer-management-create-page-menu.png " ")

11. Under **Component** tab, select **Interactive Report**.

    ![Select Interactive Report for Offer Management](images/create-page-select-interactive-report.png " ")

12. For the Create Interactive Report page, enter or select the following:

    - Under Page Definition:

        - Page Name: **Jobs**

        - Include Form Page: **Toggle On**

        - Form Page Name: **Form on Jobs**

    - Under Data Source:

        - Data Source: **Local Database**

        - Table or View: **TMS_JOBS**

13. Click **Next**.

    ![Jobs page definition](images/jobs-page-definition.png " ")

    This page gives administrators a quick way to review and maintain job records used by requisitions.

14. For **Primary Key Column 1**, select **JOB_ID(Number)** and click **Create Page**.

    ![Jobs primary key settings](images/jobs-primary-key.png " ")

15. In Page Designer, click **Save and Run**.

    ![Jobs page in Page Designer](images/jobs-page-designer.png " ")

16. Confirm that the Jobs page loads.

    ![Jobs running page](images/jobs-running-page.png " ")

## Summary

In this lab, you added and ran two table-driven pages in the Talent Acquisition Portal.

- Created an Offer Management interactive report and form based on `TMS_OFFERS`.
- Created a Jobs interactive report and form based on `TMS_JOBS`.
- Selected each table's primary key and confirmed that the generated pages load.

## Acknowledgements

- **Author** - Ankita Beri, Senior Product Manager
- **Last Updated By/Date** - Ankita Beri, Senior Product Manager, July 2026
