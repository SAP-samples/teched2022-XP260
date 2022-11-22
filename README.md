[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2022-XP260)](https://api.reuse.software/info/github.com/SAP-samples/teched2022-XP260)

# XP260 - Configuring SAP BTP Services Securely

## Description

This repository contains the material for the SAP TechEd 2022 session XP260 - Configuring SAP BTP Services Securely.  

## Overview

In this session attendees will learn about the recently published security recommendation for BTP services and how to implement them. The [SAP BTP Security Recommendations](https://help.sap.com/docs/BTP/c8a9bb59fe624f0981efa0eff2497d7d/531f33def8074ccdb6f1f784a34dafcb.html) are available in the SAP Help Portal in the sections for the SAP Business Technology Platform.

## Requirements

None

## Exercises


- [Getting Started](exercises/ex0/)
- [Exercise 1 - Using a custom identity provider to authenticate platform users](exercises/ex1/)
    - [Exercise 1.1 - Configure the global account cockpit to trust identity provider](exercises/ex1/#exercise-11---configure-the-global-account-cockpit-to-trust-identity-provider)
    - [Exercise 1.2 - Giving a user access to the global account](exercises/ex1/#exercise-12---giving-a-user-access-to-the-global-account)
    - [Exercise 1.3 - Giving a user access to a subaccount](exercises/ex1#exercise-13---giving-a-user-access-to-a-subaccount)
- [Exercise 2 - Protect access to the SAP BTP Cockpit with multi-factor-authentication](exercises/ex2/)
    - [Exercise 2.1 - Configuring the users that shall use MFA](exercises/ex2/README.md#exercise-21-configuring-the-users-that-shall-use-mfa)
    - [Exercise 2.2 - Configuring MFA for accessing the SAP BTP Cockpit](exercises/ex2/README.md#exercise-22-configuring-mfa-for-accessing-the-sap-btp-cockpit)
    - [Exercise 2.3 - Access the SAP BTP Cockpit with MFA](exercises/ex2/README.md#exercise-23-access-the-sap-btp-cockpit-with-mfa)
- [Exercise 3 - Security recommendations regarding user access and authentication](exercises/ex3/)
    - [Exercise 3.1 - Identify obsolete users](exercises/ex3/README.md#exercise-31-identify-obsolete-users)
    - [Exercise 3.2 - Defining a custom password policy](exercises/ex3/README.md#exercise-32-defining-a-custom-password-policy)
- [Exercise 4 -Security Recommendations regarding the Audit Log](exercises/ex4/)
    - [Exercise 4.1 - Configure the SAP Audit Log Viewer service](exercises/ex4/README.md#Exercise-41-configure-the-sap-audit-log-viewer-service)
    - [Exercise 4.2 - Check the audit logs and download audit log entries via the SAP Audit Log Viewer service](exercises/ex4/README.md#exercise-42-check-the-audit-logs-and-download-audit-log-entries-via-the-sap-audit-log-viewer-service)
- [Exercise 5 - SAP Cloud Connector](exercises/ex5/)
    - [Exercise 5.1 - Access the SAP Cloud Connector console and connect your SAP BTP subaccount](exercises/ex5/README.md#exercise-51-access-the-sap-cloud-connector-console-and-connect-your-sap-btp-subaccount)
    - [Exercise 5.2 - Add a mapping to an on-premise system that shall be called from the cloud](exercises/ex5/README.md#exercise-52-add-a-mapping-to-an-on-premise-system-that-shall-be-called-from-the-cloud)
    - [Exercise 5.3 - Restrict access to the on-premise system and only expose relevant capabilities](exercises/ex5/README.md#exercise-53-restrict-access-to-the-on-premise-system-and-only-expose-relevant-capabilities)
    - [Exercise 5.4 - Managing the allowed TLS cipher suites](exercises/ex5/README.md#exercise-54-managing-the-allowed-tls-cipher-suites)

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed.

## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
