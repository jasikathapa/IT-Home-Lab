# Active Directory Tasks

This document outlines the Active Directory tasks completed in the IT Home Lab.


#### Install Active Directory
- Server Manager → Manage → Add Roles and Features  
- Installation type: Role-based or feature-based  
- Role: Active Directory Domain Services → Install  
- Promote server to Domain Controller  
- Create **New Forest** and Domain: `LAB.local`  
- Set DSRM password  
- Restart server after installation

#### Create Organizational Units

```
LAB.local
├── IT Department
├── HR Department
├── Engineering Department
```
#### User Creation 

| Username      | Full Name       | Password  | 
|---------------|----------------|-----------|
| justin.biber  | Justin Biber    | Pa55word  |
| talyor.swift  | Talyor Swift    | Pa55word  |
| selena.gomez  | Selena Gomez    | Pa55word  |

- Created test user accounts in Active Directory  
- Assigned users to appropriate departments (OUs)
- 

### File Share Setup

- Created shared folder: `EngineeringShare`
- Configured NTFS permissions
- Disabled inherited permissions
- Restricted access to Engineering users only



### Domain Join

- Joined CLIENT01 to the `LAB.local` domain
- Verified successful domain authentication

