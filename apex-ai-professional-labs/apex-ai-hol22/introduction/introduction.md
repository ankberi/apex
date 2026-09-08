# Introduction

## About this Workshop

In many real-world applications, users do not search using exact keywords. They describe intent, ask a question in natural language, or search using a concept instead of a phrase that matches one field exactly. This workshop shows how to implement semantic search in Oracle APEX so your application understands meaning, not just text.

You will configure the database embedding model, prepare candidate and HR policy data for vector search, and then add semantic search to the TAP and ESS applications. By the end of the workshop, you will have a working example that ranks results based on similarity to the user's intent instead of direct keyword match.

Estimated Workshop Time: 45 minutes

### Objectives

In this workshop you will:

- Configure the ONNX embedding model and APEX vector provider
- Prepare data for semantic search in the candidate and HR policy tables,
- Implement Oracle AI Vector Search Configuration in TAP
- Build an HR Policy Search page in ESS
- Validate natural-language queries against semantic ranking

### Prerequisites

To take advantage of AI Vector Search in Oracle AI Database 26ai and build Semantic Search in your APEX apps, you need:

- A paid Oracle Cloud Infrastructure (OCI) account or a FREE Oracle Cloud account with $300 credits for 30 days to use on other services. Read more about it at: oracle.com/cloud/free/.

- The logged-in user should have the necessary privileges to create and manage Autonomous Database instances in this compartment. You can configure these privileges via an OCI IAM Policy. If you are using a Free Tier account, it is likely that you already have all the necessary privileges.

- Database Version : This workshop requires Autonomous Database 23ai, version 23.7 or later.


*Note: This workshop assumes you are using Oracle APEX 26.1. Some of the features might not be available in prior releases and the instructions, flow, and screenshots might differ if you use an older version of Oracle APEX.*

## Learn More

- [Oracle APEX AI Vector Search](https://docs.oracle.com/en/database/oracle/apex/24.2/aeai/)

- [Oracle Database Vector Search](https://docs.oracle.com/en/database/oracle/oracle-database/23ai/)

- [Oracle APEX and AI-powered search](https://www.oracle.com/database/)

## Acknowledgements

- **Author** - Ankita Beri, Senior Product Manager; Roopesh Thokala, Principal Product Manager

- **Last Updated By/Date** - Ankita Beri, August 2026
