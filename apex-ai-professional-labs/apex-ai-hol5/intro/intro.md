# Introduction

## About this Workshop

In this workshop, you will create three Transaction Management System applications in Oracle APEX by using low-code application creation options in App Builder.

The database schema is already available. In this module, you will build the first working versions of the Talent Acquisition Portal, Employee Self-Service Portal, and HR Analytics App. You will create applications from wizard-defined pages, from an uploaded CSV file, from existing database tables, and from a natural-language prompts.

Estimated workshop time: 30 minutes

## Objectives

In this workshop, you will:

- Create the Talent Acquisition Portal by using the Create App Wizard.
- Create the Employee Self-Service Portal by using the Create App Wizard.
- Create the HR Analytics App by using Application from File.
- Add report and form pages to the Talent Acquisition Portal from existing database tables.
- Create a Talent Acquisition Portal cards dashboard from a natural-language prompts.
- Review how Oracle APEX generates applications, pages, forms, and reports from the metadata you provide.

## Applications

- **Talent Acquisition Portal (TAP)**: A recruiting application with Home, Job Requisitions, Candidate Pipeline, Interview Schedule, Offers, Offer Management, Jobs, and an AI-generated dashboard.

- **Employee Self-Service Portal (ESS)**: An employee-facing application with Home, My Tasks, My Profile, Leave Request, and My Payslip.

- **HR Analytics App (HAA)**: An analytics starter application created from a CSV file upload.

## Prerequisites

- An APEX workspace.

- An API key for the AI provider of your choice (OCI Gen AI, Open AI, Cohere, Google Gemini, Anthropic Claude, Mistral AI, Ollama and Generic(OpenAI API Compatible)).

- If you choose OCI Gen AI as your AI provider, the prerequisites are as follows:

    - A paid Oracle Cloud Infrastructure (OCI) account or a Free Oracle Cloud account with $300 in credits valid for 30 days to use on other services. Learn more at: oracle.com/cloud/free/. The OCI account must be created in, or subscribed to, a region that supports the OCI Generative AI service. Currently, OCI Generative AI Service is supported in the following regions:

        - Brazil East (Sao Paulo)
        - Germany Central (Frankfurt)
        - India South (Hyderabad)
        - Japan Central (Osaka)
        - Saudi Arabia Central (Riyadh)
        - UAE East (Dubai)
        - UK South (London)
        - US East (Ashburn)
        - US Midwest (Chicago)
        - US West (Phoenix)

    - The OCI Generative AI service is available only in select regions. To see if your cloud region supports OCI Generative AI service, visit the documentation.

    - An OCI compartment. An Oracle Cloud account comes with two preconfigured compartments: the tenancy (root compartment) and ManagedCompartmentForPaaS(created by Oracle for Oracle Platform services).

    - The logged-in user must have the necessary privileges to create and manage Autonomous Database instances in this compartment. You can configure these privileges via an OCI IAM Policy. If you are using a Free Tier account, it is likely that you already have all the necessary privileges.

*Note: This workshop assumes you are using Oracle APEX 26.1. Some of the features might not be available in prior releases and the instructions, flow, and screenshots might differ if you use an older version of Oracle APEX.*

*Important: This workshop requires an active account with a supported Generative AI provider. Oracle APEX connects to the provider using your own credentials. Any API usage charges are billed directly by your provider. Please review your provider’s pricing before proceeding.*

## Let's Get Started!

- Click **Getting Started** from the menu on the right. If you already have an Oracle Cloud account, click on **Lab 1: Configure AI Service and Create Data Model using AI**.

>**Note**: If you have a **Free Trial** account, when your Free Trial expires your account will be converted to an **Always Free** account. You will not be able to conduct Free Tier workshops unless the Always Free environment is available. **[Click here for the Free Tier FAQ page.](https://www.oracle.com/cloud/free/faq.html)**

## Downloads

If you are stuck or the App is not working as expected, you can download and install the completed App as follows:

1. **[Click here](files/event-management-hol-app.sql)** to download the completed application.

2. Follow Lab [Appendix: Download Instructions](?lab=8-appendix) to import the application in your workspace.

## Learn More - *Useful Links*

- APEX on Autonomous:   [https://apex.oracle.com/autonomous](https://apex.oracle.com/autonomous)
- APEX Collateral:   [http://oracle.com/apex](https://www.oracle.com/apex)
- Tutorials:   [https://apex.oracle.com/en/learn/tutorials](https://apex.oracle.com/en/learn/tutorials)
- Community:  [https://apex.oracle.com/community](https://apex.oracle.com/community)
- External Site + Slack:   [http://apex.world](http://apex.world)

## Acknowledgements

- **Author** - Ankita Beri, Senior Product Manager
- **Last Updated By/Date** - Ankita Beri, Senior Product Manager, July 2026
