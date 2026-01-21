# IT-Home-Lab

This repository documents my personal IT Home Lab built using VirtualBox.
It includes a Windows Server 2022 Domain Controller (DC01) and a Windows 11 Pro Client (CLIENT01).
The lab simulates a small business IT environment to practice 1st Line / Junior IT Support tasks.
## Respistory
```
IT Home Lab
├── README.md
├── Tasks
  ├── ...
├── Troubleshotting
```
## Table of Contents
1. [VirtualBox Setup](#virtualbox-setup)
2. [Windows Server Setup](#windows-server-setup)
3. [Active Directory Configuration](#active-directory-configuration)
4. [Windows 11 Client Setup](#windows-11-client-setup)

## VirtualBox Setup
- Download and install [VirtualBox](https://www.virtualbox.org/) on your host machine
- Create NAT Network:
```
  - File → Tools → Network → NAT Network → Create
  - Set Network Name: `NAT Network`
  - IPv4 Network: `10.0.2.0/24`
  - Enable DHCP
```
> 💡 **Tip:** NAT Network allows your VMs to communicate and access the internet.

## Windows Server Setup
##### 1. Create Window Server
```
- OS: Windows Server 11
- RAM: 4 GB
- CPU: 2 cores
- Disk: 50 GB
- Network: NAT Network       
```

##### 2. Configure Static IP
```
- IP address: `10.0.2.4`  
- Subnet mask: `255.255.255.0`  
- Default gateway: `10.0.2.1`  
- DNS server: `127.0.0.1`
```
##### 3. Install Active Directory
- Open Settings -> Sytstem -> About
- Rename the PC: DC01
- Server Manager → Manage → Add Roles and Features  
- Installation type: Role-based or feature-based  
- Role: Active Directory Domain Services → Install  
- Promote server to Domain Controller  
- Create **New Forest** and Domain: `LAB.local`  
- Set DSRM password  
- Restart server after installation

## Active Directory Configuration
This section confirms that the lab environment is fully configured and operational.

##### 1. Organizational Unit Structure
```
LAB.local
├── IT Department
├── HR Department
├── Engineering Department
```
##### 2. User Accounts
  
    | Username      | Full Name       | Password  | 
    |---------------|-----------------|-----------|
    | justin.biber  | Justin Biber    | Pa55word  |
    | talyor.swift  | Talyor Swift    | Pa55word  |
    | selena.gomez  | Selena Gomez    | Pa55word  |
- Created test user accounts in Active Director
- Set all accounts to "User must change password at next logon" for security.
- Assigned users to the appropriate departmental Organizational Units
```
justin.biber → HR Department
talyor.swift → Engineering Department
selena.gomez → IT Department
```

## Windows 11 Client Setup

##### 1. Create Client VM
```
- OS: Windows 11
- RAM: 4 GB
- CPU: 2 cores
- Disk: 50 GB
- Network: NAT Network       
```

##### 2. Configure Static IP
```
- IP address: `10.0.2.9`  
- Subnet mask: `255.255.255.0`  
- Default gateway: `10.0.2.1`  
- DNS server: `10.0.2.4` (DC IP)
```
##### 3. Join Domain
- Open Settings -> Sytstem -> About
- Rename the PC: CLIENT01
- Open Accounts → Access work or schools
- Selected "Domain" and typed: LAB.local
- Entered domain admin username and password
- Computer restarted
  <img width="725" height="441" alt="Screenshot 2026-01-20 192744" src="https://github.com/user-attachments/assets/a3f29fe7-5bc7-4387-89fb-f9ebfb0c83d7" />
  <img width="663" height="241" alt="Screenshot 2026-01-20 192820" src="https://github.com/user-attachments/assets/d74701a4-e7f5-4c8b-8d4e-698d71ee3cf7" />

##### 4. Verification
- Test domian was joined by logging in to CLIENT01 using domain credentials
- Windows prompted me to change password
- Successfully logged in!
<img width="343" height="116" alt="Screenshot 2026-01-20 214149" src="https://github.com/user-attachments/assets/37cacf58-f8c4-47d0-ad7b-43d506224799" />


  
