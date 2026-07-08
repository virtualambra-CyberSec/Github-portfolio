# Active Directory Domain Deployment Lab (Azure)

## Overview

This project simulates a basic enterprise Active Directory environment deployed in Microsoft Azure. The setup includes a Domain Controller, a client machine, user and group management, Group Policy configuration, and network file sharing.

The objective was to understand how centralized authentication, identity management, and access control operate in a Windows domain environment.

---

## Environment Architecture

* Resource Group: AD-Lab-RG
* Virtual Network: ADLab-VNet
* Domain Controller: Windows Server 2022 (DC1)
* Client Machine: Windows 10/11 (Client1)
* Domain: ADLab.local

---

## Domain Controller Setup

* Installed Active Directory Domain Services (AD DS)
* Promoted the server to a Domain Controller
* Configured DNS during the domain setup process

---

## Client Configuration

* Joined the client machine to the domain
* Configured DNS to point to the Domain Controller
* Verified domain connectivity and authentication

---

## User and Group Management

* Created domain users and security groups
* Assigned users to appropriate groups
* Tested login using domain credentials (domain\username format)

---

## File Sharing

* Created a shared folder on the Domain Controller
* Configured NTFS and share permissions
* Verified access from the client machine

---

## Group Policy Configuration

* Created a Group Policy Object (GPO)
* Configured automatic network drive mapping
* Applied the policy to domain users

---

## Testing and Validation

* Logged into the client machine using domain credentials
* Verified user context with system commands
* Confirmed network drive mapping and access permissions

---

## Troubleshooting

During the lab, several issues were identified and resolved:

* DNS misconfiguration affecting domain join
* Delays in Group Policy application
* Authentication context confusion between local and domain users

---

## Skills Demonstrated

* Active Directory administration
* DNS configuration in domain environments
* Windows Server management
* Identity and access management
* Group Policy configuration
* Network file sharing and permissions
* Troubleshooting in a domain environment

---

## Outcome

Successfully deployed and configured a functional Active Directory environment, demonstrating centralized authentication, policy enforcement, and secure resource access.

