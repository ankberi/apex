# Create Talent Acquisition Portal (TAP) using the Create App Wizard

## Introduction

In this lab, you will use the APEX Create App Wizard to build a starter Talent Acquisition Portal (TAP). You will add report pages for job requisitions and candidates, along with blank pages reserved for interview scheduling and offers, then run the application to confirm that its pages are available.

Estimated time: 5 minutes

### Objectives

In this lab, you will:

- Create Talent Acquisition Portal (TAP) using the Create App Wizard.

### What You Will Build

- **Talent Acquisition Portal (TAP)**: Created with the Create App Wizard. It includes Home, Job Requisitions, Candidate Pipeline, Interview Schedule, and Offers pages.

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

19. Make sure **Appearance** is selected with the default **IRIS** style.

20. Click **Create Application**.

    ![Review Talent Acquisition Portal pages and create application](images/tap-review-pages-create-application.png " ")

21. Click **Run Application**.

    ![Talent Acquisition Portal application home in App Builder](images/tap-application-home-builder.png " ")

22. Log in to the application.

    ![Talent Acquisition Portal sign in page](images/tap-sign-in-page.png " ")

23. Click through all five pages and confirm that the application is live.

    ![Talent Acquisition Portal running home page](images/tap-home-page-running.png " ")

## Summary

In this lab, you created and ran the Talent Acquisition Portal using the Create App Wizard.

- Added interactive report pages with forms for job requisitions and candidates.
- Added blank pages for interview scheduling and offers, ready for functionality in later modules.
- Ran the application and confirmed that its five pages load.

## Acknowledgements

- **Author** - Ankita Beri, Senior Product Manager
- **Last Updated By/Date** - Ankita Beri, Senior Product Manager, July 2026
