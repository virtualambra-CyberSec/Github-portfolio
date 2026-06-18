# Active Directory Domain Deployment Lab (Azure)

## 📌 Overview
This project simulates a real enterprise Active Directory environment built in Microsoft Azure. It includes a Domain Controller, client machine, user management, Group Policy configuration, and network file sharing.

The goal was to understand how identity, authentication, and access control work in a corporate IT environment.

---

## 🏗️ Environment Architecture

- Azure Resource Group: AD-Lab-RG
- Virtual Network: ADLab-VNet
- Domain Controller: Windows Server 2022 (DC1)
- Client Machine: Windows 10/11 (Client1)
- Domain: ADLab.local

---

## ⚙️ Core Setup

### Domain Controller
- Installed Active Directory Domain Services (AD DS)
- Promoted server to Domain Controller
- Configured DNS automatically during promotion

### Client Machine
- Joined to AD domain
- Configured DNS to point to Domain Controller private IP

---

## 👥 User & Group Management

Created:
- Domain users (e.g. Giovanni Lee, Jane Doe, John Doe)
- Security groups (HR, IT)

Key concept:
- Login uses `sAMAccountName` format (e.g. adlab\giovannilee)

---

## 📁 File Sharing

- Created shared network folder: `\\DC1\SHARED_Folder`
- Configured NTFS and share permissions
- Enabled controlled access via AD users

---

## ⚙️ Group Policy (GPO)

- Created Group Policy Object for drive mapping
- Automatically mapped network drive:

Z: → \\DC1\SHARED_Folder
- User Configuration → Preferences → Drive Maps

---
## 🔐 Authentication & Testing

Validated:
- Domain login from client machine
- Verified mapped drives using `net use`

## 🛠️ Troubleshooting

Resolved issues involving:
- GPO not applying immediately
- Authentication context (local vs domain login)
---

## 💡 Key Skills Demonstrated

- Active Directory administration
- Windows Server management
- Identity and access management
- Group Policy configuration
- Troubleshooting enterprise IT systems

---

## 🚀 Outcome

Successfully built a fully functional enterprise-style domain environment demonstrating centralized authentication, automated policy deployment, and secure file sharing.- Network file sharing and permissions
- DNS configuration in domain environments

- Domain join failures
- DNS misconfiguration
---

- Command: `whoami`
- User authentication via Active Directory

Applied using:

