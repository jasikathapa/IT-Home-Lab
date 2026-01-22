# File Share Setup
This document outlines the steps to set up a shared folder for the Engineering Department in the IT Home Lab, 
including specific access for a project manager in HR.
```
Ticket Request:
Set up a file share only for the Engineering Department and add users Talyor and Justin. 
Justin needs access as he is the project manager even though he belongs to HR.
```
##### 1. Create group named EngineeringShare
- Open Active Directory Users and Computers 
- Navigate to Engineering Department OU → New → Group
- group name: EngineeringShares
- add users: Talyor and Justin

  <img width="445" height="478" alt="image" src="https://github.com/user-attachments/assets/d73fc988-59e4-4034-84f6-bdf31dca0e80" />
##### 2. Create Shared Folder
- open Server Manager → File and Storage Services → Shares → Tasks → New Share
- share name: EngineeringShare 
- click Customized permissions -> Disabled inheritance
- remove unrelated users/groups
- add EngineeringShare group
> This ensures only authorized users have access.

##### 3. Configure NTFS Permission Entry
- Ensure that the EngineeringShare group has access to make changes to the folder.
 <img width="913" height="509" alt="image" src="https://github.com/user-attachments/assets/5d706d2b-3838-42e9-a612-d8b1ef9326ec" />

##### 4. Verfication
- login to CLIENT01 with each user account
- open File Explorer and navigate to "\\DC01\EngineeringShare"
- Confirm users have access based on group membership
  
##### 5. Map Network Drive
- on CLIENT01, map the shared folder to a network drive
- select Reconnect at sign-in for persistent mapping
- confirm both usercan access the mapped drive
<img width="624" height="500" alt="Screenshot 2026-01-20 235111" src="https://github.com/user-attachments/assets/14672d5b-1e99-426d-813d-ce5f390094c2" />
<img width="320" height="118" alt="Screenshot 2026-01-20 235144" src="https://github.com/user-attachments/assets/12a605a3-63a6-44f2-8656-0eb69cd71a58" />

### Skills Demonstrated
- Active Directory security group management
- File share creation and NTFS permission configuration
- User-specific access control
- Mapping shared network drives on clients
- Verification of correct access from domain-joined clients
