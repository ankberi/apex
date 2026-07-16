# Low Code Application Development

## Introduction

In this lab, you will create three APEX applications from scratch using multiple APEX application creation methods. You will create the Talent Acquisition Portal and Employee Self-Service Portal with the Create App Wizard, create the HR Analytics App from a CSV file, add generated pages from database tables, and build a cards page with Natural Language.

Estimated time: 30 minutes

### Objectives

In this lab, you will:

- Create Talent Acquisition Portal (TAP) using the Create App Wizard.

- Create Employee Self-Service Portal (ESS) using the Create App Wizard.

- Create HR Analytics App (HAA) using Application from File.

- Add table-driven pages to Talent Acquisition Portal (TAP).

- Create the Cards page using Natural Language.

### What You Will Build

- **Talent Acquisition Portal (TAP)**: Created with the Create App Wizard. It includes Home, Job Requisitions, Candidate Pipeline, Interview Schedule, and Offers pages. You will extend it with Offer Management and Jobs pages using Application from Tables, then create cards page using natural language.

- **Employee Self-Service Portal (ESS)**: Created with the Create App Wizard. It includes Home, My Tasks, My Profile, Leave Request, and My Payslip pages.

- **HR Analytics App (HAA)**: Created from `candidate_pipeline_sample.csv` using Application from File.

## Task 1: Create the Talent Acquisition Portal Application using the Create App Wizard

In this task, you create the Talent Acquisition Portal application using the Create App Wizard. This application becomes the main recruiting workspace for job requisitions, candidates, interviews, and offers.

1. On the Workspace home page, click **App Builder**.

    ![App Builder create application tile](images/app-builder-create-app-tile.png " ")

2. Click **Create**.

    ![App Builder New Application card](images/app-builder-new-application-card.png " ")

3. Click **Use Create App Wizard**.

    ![Create App Wizard option](images/create-application-create-app-wizard.png " ")

4. For **Name**, enter: **Talent Acquisition Portal**

    ![Talent Acquisition Portal application name](images/tap-enter-application-name.png " ")

5. To add a **Report with Form** page, click **Add Page**.

    ![Add page in the Talent Acquisition Portal wizard](images/tap-click-add-page.png " ")

6. Select **Interactive Report**.

    ![Select Interactive Report page type](images/add-page-select-interactive-report.png " ")

7. For the Add Report Page, enter or select the following:

    - Page Name: **Job Requisitions**

    - Table or View: **TMS\_JOB\_REQUISITIONS**

    - Include Form: **Toggle On**

    This page gives recruiters a working list of open job requisitions and a form to maintain each requisition.

8. Click **Add Page**.

    ![Job Requisitions report page details](images/tap-job-requisitions-report-page.png " ")

9. On the Create an Application page, click **Add Page** again.

    ![Job Requisitions page added](images/tap-job-requisitions-page-added.png " ")

10. Select **Interactive Report**.

    ![Select Interactive Report page type](images/add-page-select-interactive-report.png " ")

11. For the Add Report Page, enter or select the following:

    - Page Name: **Candidate Pipeline**

    - Table or View: **TMS_CANDIDATES**

    - Include Form: **Toggle On**

    This page lets recruiters review candidates and update candidate records as they move through the hiring process.

12. Click **Add Page**.

    ![Candidate Pipeline report page details](images/tap-candidate-pipeline-report-page.png " ")

13. On the Create an Application page, click **Add Page** again.

    ![Candidate Pipeline page added](images/tap-candidate-pipeline-page-added.png " ")

14. Select **Blank**.

    ![Select Blank Page type](images/add-page-select-blank-page.png " ")

15. For the page name, enter: **Interview Schedule** and click **Add Page**.

    ![Interview Schedule blank page details](images/tap-interview-schedule-blank-page.png " ")

    This blank page reserves a place for interview scheduling functionality that is added in a later module.

16. To add another **Blank Page**, click **Add Page** on the Create an Application page.

17. Select **Blank**.

    ![Select Blank Page type](images/add-page-select-blank-page.png " ")

18. For the page name, enter: **Offers** and click **Add Page**.

    ![Offers blank page details](images/tap-offers-blank-page.png " ")

    This blank page reserves a place for offer-related functionality that is added in a later module.

    ![Talent Acquisition Portal pages with Offers added](images/tap-pages-with-offers-added.png " ")

19. Make sure **Universal Theme** is selected with the default **IRIS** style.

20. Click **Create Application**.

    ![Review Talent Acquisition Portal pages and create application](images/tap-review-pages-create-application.png " ")

21. Click **Run Application**.

    ![Talent Acquisition Portal application home in App Builder](images/tap-application-home-builder.png " ")

22. Log in to the application.

    ![Talent Acquisition Portal sign in page](images/tap-sign-in-page.png " ")

23. Click through all five pages and confirm that the application is live.

    ![Talent Acquisition Portal running home page](images/tap-home-page-running.png " ")

## Task 2: Create the Employee Self-Service Portal using the Create App Wizard

In this task, you create the Employee Self-Service Portal application. This application becomes the employee-facing workspace for onboarding tasks, profile details, leave requests, and payslip access.

1. From the left navigation menu, click the **App Builder** icon.

    ![App Builder with Talent Acquisition Portal created](images/app-builder-tap-created.png " ")

2. Click **Create**.

    ![Create a new Employee Self-Service Portal application](images/app-builder-create-ess-start.png " ")

3. Click **Use Create App Wizard**.

    ![Employee Self-Service Portal Create App Wizard option](images/ess-create-app-wizard.png " ")

4. For **Name**, enter: **Employee Self-Service Portal**

    ![Employee Self-Service Portal application name](images/ess-enter-application-name.png " ")

5. To add a **Report with Form** page, click **Add Page**.

    ![Add page in the Employee Self-Service Portal wizard](images/ess-click-add-page.png " ")

6. Select **Interactive Report**.

    ![Select Interactive Report page type](images/add-page-select-interactive-report.png " ")

7. For the Add Report Page, enter or select the following:

    - Page Name: **My Tasks**

    - Table or View: **TMS\_ONBOARDING\_TASKS**

    - Include Form: **Toggle On**

    This page gives employees a simple place to view and update their onboarding tasks.

8. Click **Add Page**.

    ![My Tasks report page details](images/ess-my-tasks-report-page.png " ")

9. On the Create an Application page, click **Add Page** again.

    ![My Tasks page added](images/ess-my-tasks-page-added.png " ")

10. Select a **Blank** page.

    ![Select Blank Page type](images/add-page-select-blank-page.png " ")

11. For the page name, enter: **My Profile** and click **Add Page**.

    ![My Profile blank page details](images/ess-my-profile-blank-page.png " ")

    This blank page reserves a place for employee profile information that is added in a later module.

12. To add another **Blank Page**, click **Add Page**.

    ![Add another Employee Self-Service Portal page](images/ess-add-page-after-profile.png " ")

13. For the page name, enter: **Leave Request** and click **Add Page**.

    ![Leave Request blank page details](images/ess-leave-request-blank-page.png " ")

    This blank page reserves a place for leave request functionality that is added in a later module.

14. To add another **Blank** page, click **Add Page**.

    ![Leave Request page added](images/ess-leave-request-page-added.png " ")

15. For the page name, enter: **My Payslip** and click **Add Page**.

    ![My Payslip blank page details](images/ess-my-payslip-blank-page.png " ")

    This blank page reserves a place for payslip access that is added in a later module.

16. Click **Create Application**.

    ![Review Employee Self-Service Portal pages and create application](images/ess-review-pages-create-application.png " ")

17. Click **Run Application**.

    ![Employee Self-Service Portal application home in App Builder](images/ess-application-home-builder.png " ")

18. Log in to the application.

    ![Employee Self-Service Portal sign in page](images/ess-sign-in-page.png " ")

19. Confirm that all five pages load.

    ![Employee Self-Service Portal running home page](images/ess-home-page-running.png " ")

## Task 3: Create the HR Analytics App from a File

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

## Task 4: Add Pages to the Talent Acquisition Portal

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

7. Review the primary key settings and click **Create Page**.

    ![Offer Management primary key settings](images/offer-management-primary-key.png " ")

    APEX uses the table metadata to detect relationships to `CANDIDATES` and `JOB_REQUISITIONS`.

8. In Page Designer, click **Save and Run**.

    ![Offer Management page in Page Designer](images/offer-management-page-designer.png " ")

9. Confirm that the page works immediately without additional configuration.

    ![Offer Management running page](images/offer-management-running-page.png " ")

10. Return to App Builder and navigate to Page Designer toolbar, hover over **+v** and select **Page**. 

    ![Create another page from the Offer Management page](images/offer-management-create-page-menu.png " ")

11. Under **Componenet** tab, select **Interactive Report**.

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

14. Review the primary key settings and click **Create Page**.

    ![Jobs primary key settings](images/jobs-primary-key.png " ")

15. In Page Designer, click **Save and Run**.

    ![Jobs page in Page Designer](images/jobs-page-designer.png " ")

16. Confirm that the Jobs page loads.

    ![Jobs running page](images/jobs-running-page.png " ")

## Task 5: Create a Page using Natural Language

In this task, you use Generative AI to create the Talent Acquisition Portal page. The cards page gives recruiters a high-level view of open requisitions, candidate activity, interviews, and pending offers.

1. Return to **App Builder** and navigate to Page Designer Toolbar, hover over **+v** and select **Page**.

    ![Create page from the Jobs page](images/jobs-create-page-menu.png " ")

2. On the Create a Page page, select **Generative AI** tab.

3. If prompted, accept the Generative AI terms.

    ![Accept the Generative AI terms](images/generative-ai-terms-dialog.png " ")

4. Enter the following prompt and click the send icon:

    ```
    <copy>
    Create a page showing total open requisitions, candidates this week, interviews today, and offers pending as cards
    </copy>
    ```

    ![Enter the AI dashboard prompt](images/ai-dashboard-prompt-entered.png " ")

    This prompt asks APEX AI to create metric cards that summarize the recruiting pipeline.

5. Review the generated cards page and click **Create Page**.

    ![APEX AI page generation response](images/ai-dashboard-create-page-response.png " ")

6. Review the cards layout and attributes settings and click **Create Page**.

    ![Create the generated cards page](images/ai-dashboard-cards-layout-create-page.png " ")

7. In Page Designer, click **Save and Run**.

    ![Recruitment Metrics page in Page Designer](images/recruitment-metrics-page-designer.png " ")

8. Observe the generated cards page.

    ![Recruitment Metrics dashboard running page](images/recruitment-metrics-dashboard-running.png " ")

## Summary

In this lab, you created the first working versions of the three TMS applications using different APEX application creation methods.

- **Talent Acquisition Portal** was created with the Create App Wizard, extended with Offer Management and Jobs pages, and updated with an AI-generated dashboard.

- **Employee Self-Service Portal** was created with starter pages for onboarding tasks, profile details, leave requests, and payslip access.

- **HR Analytics App** was created from a CSV file upload, showing how quickly APEX can turn data into a working application.

You also saw how APEX can generate pages from tables, detect table relationships, create forms and reports, and use natural language to generate a page. These starter applications carry forward into the next modules, where you refine the page structure, add real functionality, and improve the generated SQL and user experience.

## Acknowledgements

- **Author** - Ankita Beri, Senior Product Manager
- **Last Updated By/Date** - Ankita Beri, Senior Product Manager, July 2026
