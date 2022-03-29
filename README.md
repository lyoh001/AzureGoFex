# VICGOV - Azure Active Directory Roles Report
## 1. Introduction
### 1.1	Overview

A number of challenges arise when managing AAD roles across multiple tenants, Hosting Services team have been working to make this process easier to maintain with less administrative overhead.

This document is intended to provide a high level overview of workflow on how the automation notifies the admins with Azure AD roles assigned to all staff in VICGOV.

Included in this report is a step by step detailed guide around where to look for troubleshooting.

## 2 O365 Process Reports (CIS Benchmark)
- Priority: 1
- Description: MS Sharepoint integration from the on-prem server..
- Owners: Tier 0


## 3 Logical Architecture
### 3.1	Logical System Component Overview
![Figure 1: Logical Architecture Overview](./.images/workflow.png)
1. The file gets dumped from the application.
1. Scheduler runs the script to copy files from on-prem to Azure Blob.
1. This invokes a function via eventgrid. 
1. The function will auth via managed identity against Azure AD and retrieves API credentials from Azure Keyvault that is secured under T0 subscription.
1. SPN has permission on the BAS sharepoint site to upload a file.
1. The function will invoke logic app for notification email.

## Used By

This project is used by the following teams:

- BAS
- Cloud Platform



