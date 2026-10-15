# Lab 05: Active Directory Architecture, RBAC & Workstation GPO

![Windows Server](https://img.shields.io/badge/Windows%20Server-2025-0078D6?style=flat-square&logo=windows-server&logoColor=white)
![Active Directory](https://img.shields.io/badge/Active%20Directory-Architecture-0078D6?style=flat-square&logo=windows&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-Academy%20Learner%20Lab-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)

## Overview

This lab documents the design and configuration of an Active Directory environment for a fictional Ensign College Student Success Center. The environment supports one Center Manager and five Student Advisors, with role-based access to shared resources and centralized Group Policy settings.

**Domain:** `ensignsuccess.corp`  
**Domain controller:** `ENSIGN-DC01`  
**Platform:** AWS Academy Learner Lab  
**Server OS:** Windows Server 2025 Datacenter

## Objectives

- Organize user and computer objects into functional Organizational Units (OUs).
- Provision manager, advisor, and backup-administrator accounts.
- Use security groups to manage access according to job responsibilities.
- Configure shared-folder NTFS permissions following least privilege.
- Configure password and account-lockout policies.
- Configure workstation branding, browser startup, and removable-storage write restrictions.

## Directory Architecture

The intended OU layout separates users from computer objects:

```text
ensignsuccess.corp
├── Student-Success-Users
│   ├── Management
│   └── Student Advisors
├── Student-Success-Computers
│   └── Student-Advisor-Workstations
└── Security-Groups
```

Use the screenshots in this lab to confirm the exact OU paths and names in the deployed environment.

## Accounts and Groups

**Center Manager**
- `usr-mgr-mdoan`

**Student Advisors**
- `usr-adv-jdoe`
- `usr-adv-asmith`
- `usr-adv-bjohnson`
- `usr-adv-clee`
- `usr-adv-dgarcia`

**Backup administrator**
- `usr-adm-backup`

**Security groups**
- `SG-Center-Management`
- `SG-Student-Advisors`

Group-based access is used instead of assigning folder permissions individually to every user.

## Shared Folders and Access Control

The shared folders are stored under `C:\\Shares`.

| Folder | Intended NTFS access |
|---|---|
| `C:\\Shares\\AdvisingDocs` | `SG-Center-Management` and `SG-Student-Advisors`: Modify |
| `C:\\Shares\\AdminReports` | `SG-Center-Management`: Full Control; administrators and SYSTEM retain administrative access |

Network paths:
- `\\\\ENSIGN-DC01\\shares\\AdvisingDocs`
- `\\\\ENSIGN-DC01\\shares\\AdminReports`

Sample documents created for the demonstration:
- `Final Advising.txt`
- `Final Admin Report.txt`

### NTFS ACL verification

The following commands were used to inspect the folder ACLs:

```powershell
icacls "C:\Shares\AdvisingDocs"
icacls "C:\Shares\AdminReports"
Get-SmbShareAccess -Name shares
```

The observed NTFS ACL output showed Modify permissions for both security groups on AdvisingDocs, and Full Control for the management group on AdminReports. Administrators and SYSTEM retained Full Control.

**Scope note:** Effective network access depends on both SMB share permissions and NTFS permissions, as well as account group membership. The ACL inspection is documented, but a separate-client access test was not completed.

## Group Policy Settings

### Domain password and lockout policy

Configured values:
- Minimum password length: **12 characters**
- Password history: **24 passwords**
- Maximum password age: **90 days**
- Password complexity: **Enabled**
- Account lockout threshold: **5 failed attempts**

### Student Advisor workstation branding

GPO: `GPO-Student-Advisor-Workstation-Branding`

Intended target: `Student-Advisor-Workstations`

Configured/documented settings:
- Desktop wallpaper uses the Ensign College logo and a UNC path.
- Microsoft Edge startup/homepage is set to the Ensign College IT Portal: [https://www.ensign.edu/information-technology](https://www.ensign.edu/information-technology).
- **Removable Disks: Deny write access** is enabled.

**Validation limitation:** A separate domain-joined workstation was not deployed. Therefore, client-side policy application was not validated. Do not describe the wallpaper, browser, or USB restriction as successfully tested on a client workstation. The proposal mentions loopback processing; only report it as enabled if confirmed in Group Policy Management.

## Validation Commands

Run on the domain controller in an elevated PowerShell session where appropriate:

```powershell
Get-ADDomain | Select-Object DNSRoot, DomainMode, PDCEmulator

Get-ChildItem "C:\Shares\AdvisingDocs"
Get-ChildItem "C:\Shares\AdminReports"

icacls "C:\Shares\AdvisingDocs"
icacls "C:\Shares\AdminReports"

Get-SmbShareAccess -Name shares
```

Do not commit passwords, AWS credentials, private keys, tokens, or unredacted sensitive information.

## Evidence

The screenshot evidence register and uploaded images are in the [`evidence/` folder](./evidence/README.md). The register identifies what each screenshot supports and notes any validation limits. Suggested evidence:

1. AWS instance running (with sensitive details cropped/redacted).
2. Active Directory domain and OU tree.
3. User accounts and security-group membership.
4. Shared folders and the two sample text files.
5. AdvisingDocs NTFS ACL.
6. AdminReports NTFS ACL.
7. Workstation GPO settings.
8. Password and account-lockout policy settings.

Do not use placeholder images as evidence. Screenshots document configuration; they do not by themselves prove successful client-side policy application or effective access from a separate workstation.

## Lessons Learned

- Role-based security groups simplify permission management.
- NTFS and SMB share permissions combine to determine effective access.
- Separating user and computer OUs makes policy targeting easier to reason about.
- A policy being configured does not prove that it successfully applied to a client.
- Cloud lab resources should be secured and cleaned up according to the lab's rules.

## Author

**Bill Spencer Captain**  
Portfolio: [Spence-X/cybersecurity-and-sysadmin-labs](https://github.com/Spence-X/cybersecurity-and-sysadmin-labs)
