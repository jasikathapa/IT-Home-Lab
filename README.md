# IT-Home-Lab

This repository documents my personal IT Home Lab built using VirtualBox.
It includes a Windows Server 2022 Domain Controller (DC01) and a Windows 11 Pro Client (CLIENT01).
The lab simulates a small business IT environment to practice 1st Line / Junior IT Support tasks.

## Table of Contents
1. [VirtualBox Setup](#virtualbox-setup)
2. [Windows Server Setup](#windows-server-setup)
3. [Windows 11 Client Setup](#windows-11-client-setup)
4. [Active Directory Users](#active-directory-users)
5. [Testing Domain Login](#testing-domain-login)
6. [Troubleshooting](#troubleshooting)

## VirtualBox Setup

### ✅ Steps
- [ ] Download and install [VirtualBox](https://www.virtualbox.org/) on your host machine
- [ ] Create NAT Network:
  1. **File → Tools → Network → NAT Network → Create**
  2. Set Network Name: `NAT Network`
  3. IPv4 Network: `10.0.2.0/24`
  4. Enable DHCP

> 💡 **Tip:** NAT Network allows your VMs to communicate and access the internet.

## Windows Server Setup

### 1. Create Server VM
| Setting        | Value                  |
|----------------|-----------------------|
| Name           | DC01                  |
| OS             | Windows Server 2022   |
| RAM            | 4 GB                  |
| CPU            | 2 cores               |
| Disk           | 50 GB                 |
| Network        | NAT Network           |

### 2. Configure Static IP
- IP address: `10.0.2.4`  
- Subnet mask: `255.255.255.0`  
- Default gateway: `10.0.2.1`  
- DNS server: `127.0.0.1`

### 3. Install Active Directory
- Server Manager → Manage → Add Roles and Features  
- Installation type: Role-based or feature-based  
- Role: Active Directory Domain Services → Install  
- Promote server to Domain Controller  
- Create **New Forest** and Domain: `LAB.local`  
- Set DSRM password  
- Restart server after installation

## Windows 11 Client Setup

### 1. Create Client VM
| Setting        | Value                  |
|----------------|-----------------------|
| Name           | Client01              |
| OS             | Windows 11            |
| RAM            | 4 GB                  |
| CPU            | 2 cores               |
| Disk           | 50 GB                 |
| Network        | NAT Network           |

### 2. Configure Static IP
- IP address: `10.0.2.9`  
- Subnet mask: `255.255.255.0`  
- Default gateway: `10.0.2.1`  
- DNS server: `10.0.2.4` (DC IP)
