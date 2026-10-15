# Lab 05 Evidence Register

This folder tracks screenshots collected for the Student Success Center Active Directory project. The original screenshot files have been uploaded to this folder. The table below identifies the intended filename and the claim each image supports. Review each image directly before relying on it as proof.

## Evidence received (October 15, 2026)

| Suggested filename | What the screenshot shows | What it supports | Limitation |
|---|---|---|---|
| `01-aws-ec2-instance.png` | AWS EC2 instance named `Ensign-AD-Server`, running, type `t3.small` | Server hosted in AWS Academy Learner Lab | Status check was still initializing in the screenshot |
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
| `16-edge-homepage-policy.png` | “Configure the home page URL” policy is Enabled; URL field visibly begins `https://www.ensign.edu/information-tec...` | Homepage URL policy is configured in the GPO | Text field is visually truncated; the screenshot does not show the full URL |
| `17-desktop-wallpaper-policy.png` | Desktop Wallpaper policy is Enabled, style set to Fill, path field begins `\\ENSIGN-DC01\shares\AdvisingDocs\...` | Wallpaper policy is configured with a UNC path | Path field is truncated; image availability and client-side application are not proven |
| `18-password-policy.png` | Default Domain Policy password settings show history 24, max age 90 days, min length 12, complexity enabled, reversible encryption disabled | Core domain password policy settings are visible | Minimum password age is also shown as 1 day; capture confirms the displayed settings only |
| `19-account-lockout-policy.png` | Lockout duration 30 minutes, threshold 5 invalid attempts, administrator lockout enabled, reset counter after 10 minutes | Account lockout configuration is visible | These are the values shown in the policy editor |
| `20-removable-disks-policy.png` | “Removable Disks: Deny write access” is Enabled | Removable-disk write restriction is configured in the policy editor | Client-side enforcement has not been demonstrated |

## Still needed for a complete demonstration

- If available, a successful client-side test from a domain-joined workstation (GPO application, wallpaper/browser result, and role-based access). No separate workstation is evidenced by the screenshots received so far, so client-side application should not be claimed as verified.
- If possible, a separate view of the full Edge homepage URL and wallpaper UNC path, without the fields truncated.

## Privacy and security

Do not commit passwords, private keys, access tokens, or other credentials. Keep AWS account identifiers and public IP addresses out of public evidence when they are not needed. Before keeping the AWS console screenshot public, ensure the AWS account ID is cropped or redacted. The private IP address is internal lab information, but it can also be omitted from a public screenshot if it is not needed.

## Open the screenshot files

The screenshots are stored in this folder. Open the image matching the filename in the table above to inspect the evidence. If any uploaded filenames differ from the suggested filenames, update this register to match the actual names.
