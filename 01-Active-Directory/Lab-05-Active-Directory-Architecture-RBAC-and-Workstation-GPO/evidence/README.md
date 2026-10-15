# Lab 05 Evidence Register

This folder tracks the screenshots collected for the Student Success Center Active Directory project. Screenshots should be added here with the numbered filenames below as image files; this register does not substitute for the original image evidence.

## Evidence received (October 15, 2026)

| Suggested filename | What the screenshot shows | What it supports | Limitation |
|---|---|---|---|
| `01-aws-ec2-instance.png` | AWS EC2 instance named `Ensign-AD-Server`, running, type `t3.small` | Server hosted in AWS Academy Learner Lab | Status check is still initializing in the screenshot |
| `02-server-manager-ad-ds.png` | Server Manager AD DS view with `ENSIGN-DC01` and private IPv4 `172.31.41.121` | Domain controller server identity and AD DS role view | Does not alone prove every AD DS service is healthy |
| `03-ad-ou-structure.png` | AD Users and Computers OU hierarchy | Student Success users/computers, advisor workstation OU, and security-groups container exist |
| `04-administrative-accounts-ou.png` | Administrative Accounts OU selected; `usr-adm-backup` visible | Backup admin account exists in that OU |
| `05-management-ou.png` | Management OU selected; `usr-mgr-mdoan` visible | Manager account exists in Management OU |
| `06-student-advisors-ou.png` | Student Advisors OU selected; five advisor accounts visible | Five advisor accounts exist in the intended OU |
| `07-security-groups.png` | Security-Groups OU with `SG-Center-Management` and `SG-Student-Advisors` | Both role-based security groups exist |
| `08-management-group-membership.png` | Members tab for `SG-Center-Management`, showing `usr-mgr-mdoan` | Manager is a member of the management group |
| `09-advisors-group-membership.png` | Members tab for `SG-Student-Advisors`, showing five advisor accounts | Five advisors are members of the advisor group |
| `10-shares-folder-structure.png` | `C:\Shares` with `AdminReports` and `AdvisingDocs` | Both intended shared-folder directories exist |
| `11-adminreports-ntfs-permissions.png` | Security tab for `C:\Shares\AdminReports` | Management group, Administrators, SYSTEM, and Creator Owner entries are visible; selected-group permissions shown |
| `12-advisingdocs-advisor-permissions.png` | Security tab for `C:\Shares\AdvisingDocs`, advisor group selected | Advisor group has Modify-related permissions shown |
| `13-advisingdocs-admin-permissions.png` | Security tab for `C:\Shares\AdvisingDocs`, Administrators selected | Administrators have Full Control shown |
| `14-workstation-gpo-link.png` | Group Policy Management with branding GPO linked to Student-Advisor-Workstations OU | GPO link is present and enabled |
| `15-workstation-gpo-admx-editor.png` | Group Policy Management Editor showing Administrative Templates categories including Microsoft Edge | Edge policy templates are available in the editor |

## Still needed for a complete demonstration

- The actual screenshot image files must be committed alongside this register.
- A screenshot showing the configured Edge homepage/startup URL value.
- A screenshot showing the wallpaper policy value and the removable-storage write restriction.
- A screenshot or command output documenting the domain password policy.
- If available, a successful client-side test from a domain-joined workstation (GPO application, wallpaper/browser result, and role-based access). No separate workstation is evidenced by the screenshots received so far, so client-side application should not be claimed as verified.

## Privacy and security

Do not commit passwords, private keys, access tokens, or other credentials. Keep AWS account identifiers and public IP addresses out of public evidence when they are not needed. The screenshots received so far show a private IP address and an AWS account ID; consider cropping or redacting account identifiers before publishing the images.
