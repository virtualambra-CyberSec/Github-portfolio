# Active Directory Azure Lab

## Overview

This project documents the deployment and configuration of a functional Active Directory environment using Microsoft Azure and Windows Server.

The goal of this lab was to simulate a small business IT environment, including a Domain Controller, client workstation, centralized user management, shared resources, and Group Policy automation.

Through this project, I practiced core IT support and system administration tasks including Windows Server management, Active Directory administration, DNS configuration, user management, permissions, and troubleshooting.

---

## Lab Architecture

```text
Microsoft Azure

|
├── Resource Group
|   └── AD-Lab-RG
|
├── Virtual Network
|   └── ADLab-VNet
|
├── Domain Controller
|   ├── VM: DC1
|   ├── OS: Windows Server 2022
|   ├── Roles:
|   |   ├── Active Directory Domain Services (AD DS)
|   |   └── DNS
|   └── Domain: ADLab.local
|
└── Client Machine
    ├── VM: Client1
    ├── OS: Windows
    └── Joined to ADLab.local domain
```

---

## Objectives

- Deploy Windows virtual machines in Microsoft Azure
- Configure a Windows Server Domain Controller
- Install and configure Active Directory Domain Services
- Create and manage domain users and groups
- Join a client machine to the domain
- Configure shared folders and permissions
- Create and apply Group Policy Objects (GPOs)
- Troubleshoot authentication and connectivity issues

---

## Environment

| Component | Details |
|---|---|
| Cloud Platform | Microsoft Azure |
| Server OS | Windows Server 2022 |
| Client OS | Windows |
| Domain | ADLab.local |
| Domain Controller | DC1 |
| Client Machine | Client1 |
| Services | AD DS, DNS, Group Policy |

---

## Implementation

### 1. Azure Infrastructure Setup

Created the core Azure infrastructure including:
- Resource Group
- Virtual Network
- Subnet configuration

---

### 2. Domain Controller Deployment

Deployed a Windows Server 2022 VM to act as the Domain Controller.

- VM Name: DC1
- Connected to virtual network
- Remote Desktop enabled

![Domain Controller VM](images/azure-domain-controller-vm-creation.png)

---

### 3. Active Directory Setup

Installed Active Directory Domain Services and promoted the server.

- Created domain: ADLab.local
- DNS installed automatically

![AD DS Installation](images/ad-ds-role-installation.png)

![Domain Controller Setup](images/ad-domain-controller-promotion-configuration.png)

---

### 4. Client Domain Join

Created client VM and joined it to the domain.

- VM Name: Client1
- Connected to same network
- DNS pointed to Domain Controller

![Client VM](images/client-vm-creation.png)

![Domain Join Success](images/client-domain-join-success.png)

---

### 5. User and Group Management

Created users and groups in Active Directory.

Users:
- Giovanni Lee
- Jane Doe
- Jhon Doe

Groups:
- HR
- IT

![AD Users and Computers](images/active-directory-users-and-computers.png)

![User Creation](images/active-directory-user-creation.png)

---

### 6. File Sharing

Created a shared folder on the Domain Controller:

\\DC1\SHARED_Folder

Configured permissions and tested access from client.

![Shared Folder Access](images/shared-folder-access-test.png)

---

### 7. Group Policy Drive Mapping

Configured GPO to map a network drive.

- Path: \\DC1\SHARED_Folder



#### Authentication Issue
User login initially failed.

- Checked domain membership
- Verified credentials

ADLab\giovannilee

---

#### Group Policy Issue

Drive mapping did not apply immediately.

Resolved using:

```powershell
gpupdate /force
```

Confirmed drive was mapped successfully.

![Mapped Drive](images/mapped-network-drive-verification.png)

---

## Skills Demonstrated

- Azure VM deployment
- Windows Server administration
- Active Directory management
- DNS configuration
- User and group management
- Domain joining
- Group Policy configuration
- Troubleshooting Windows environments

---

## Outcome

Successfully built and configured a working Active Directory environment simulating a real-world IT setup.

This project demonstrates hands-on experience with system administration tasks and troubleshooting commonly performed in entry-level IT support roles.- File sharing and permissions
- Retried with correct format:


### 8. Testing and Troubleshooting
---
![Drive Mapping](images/gpo-network-drive-configuration.png)

![GPO Creation](images/gpo-drive-mapping-creation.png)
