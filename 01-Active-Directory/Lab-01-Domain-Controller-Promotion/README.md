# Lab 01: Promoting Windows Server to a Domain Controller

## Overview
Configured Active Directory Domain Services (AD DS) on a Windows Server VM in AWS EC2, promoted the server to a new forest (`billspencer.local`), provisioned a custom domain administrator (`domainadmin`), and verified authenticated RDP access via CLI and GUI protocols.

## Objective & Requirements
* Install AD DS role on Windows Server 2022.
* Create a new forest with root domain name `billspencer.local`.
* Create user `domainadmin` with **Domain Admins** authorization before system restart.
* Authenticate over RDP using explicit domain notation (`billspencer.local\domainadmin`).
* Collect multi-factor verification evidence (GUI & CLI).

## Key Skills Demonstrated
* **Directory Services:** AD DS Installation, Domain Controller Promotion, DSRM Configuration.
* **Identity & Access Management (IAM):** Privilege Elevation, Domain Admin Creation, Domain Scope Authentication.
* **Verification Methods:** Task Manager User Session Audit (GUI), Command Line Verification (`whoami`).

## Implementation Summary
1. Installed **Active Directory Domain Services** via Server Manager.
2. Promoted server to Domain Controller for `billspencer.local`.
3. Created user `domainadmin` in Computer Management (`compmgmt.msc`) and added to the **Administrators** group prior to promotion finalization.
4. Signed in via RDP using `billspencer.local\domainadmin`.
5. Verified session details in Task Manager and Command Prompt (`whoami`).
