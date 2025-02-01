# Active Directory Home Lab

## Table of Contents
- [Overview](#overview)
- [Lab Architecture](#lab-architecture)
  - [Key Components](#key-components)
- [Objectives](#objectives)
- [Skills Demonstrated](#skills-demonstrated)
- [Tools and Technologies](#tools-and-technologies)
- [Setup Instructions](#setup-instructions)
  - [Install Oracle VirtualBox](#1-install-oracle-virtualbox)
  - [Set Up Windows Server VM](#2-set-up-windows-server-vm)
  - [Promote to Domain Controller](#3-promote-to-domain-controller)
  - [Manage Users with PowerShell](#4-manage-users-with-powershell)
- [Results](#results)
- [Conclusion](#conclusion)
- [Screenshots](#screenshots)
  - [Download VirtualBox and Windows Server 2022 ISO](#download-virtualbox-and-windows-server-2022-iso)
  - [VirtualBox Installed](#virtualbox-installed)
  - [Virtual Machine Settings](#virtual-machine-settings)
  - [Windows Server Installation](#windows-server-installation)
- [Configuring Network Adapters in VirtualBox](#configuring-network-adapters-in-virtualbox)
  - [Step 1: Access VirtualBox Network Settings](#step-1-access-virtualbox-network-settings)
  - [Step 2: Configure Adapter 1 (NAT)](#step-2-configure-adapter-1-nat)
  - [Step 3: Configure Adapter 2 (Internal Network)](#step-3-configure-adapter-2-internal-network)
  - [Step 4: Save the Settings](#step-4-save-the-settings)
  - [Explanation of Network Adapters](#explanation-of-network-adapters)
- [Configuring Network Adapters in Windows Server](#configuring-network-adapters-in-windows-server)
  - [Step 1: Access the Network Menu](#step-1-access-the-network-menu)
  - [Step 2: Open Network & Internet Settings](#step-2-open-network--internet-settings)
  - [Step 3: Access Change Adapter Options](#step-3-access-change-adapter-options)
  - [Step 4: View Available Network Adapters](#step-4-view-available-network-adapters)
  - [Step 5: Identify the Internet-Connected Adapter](#step-5-identify-the-internet-connected-adapter)
  - [Step 6: Verify the Internet-Connected Adapter](#step-6-verify-the-internet-connected-adapter)
  - [Step 7: Rename the Adapters for Easy Identification](#step-7-rename-the-adapters-for-easy-identification)
  - [Benefits of Renaming Adapters](#benefits-of-renaming-adapters)

---

## Overview
This project involves setting up a home lab using Oracle VirtualBox to install and configure Active Directory. The lab includes creating a Windows Server virtual machine, promoting it to a Domain Controller, and managing users with PowerShell.

---

## Lab Architecture

The following diagram illustrates the network topology and key components of this Active Directory lab environment:

![Network Topology](screenshots/network-topology.png)

### Key Components
1. **DC (Domain Controller)**:
   - Runs Active Directory Domain Services (AD DS).
   - Provides DNS and DHCP for the internal network.
   - IP: `172.16.0.1`

2. **Client1 (Windows 10)**:
   - Joins the domain and communicates with the Domain Controller.
   - Receives IP and DNS configuration from the Domain Controller.

3. **DHCP Scope**:
   - IP Range: `172.16.0.100` to `172.16.0.200`

4. **RAS/NAT**:
   - Enables internal machines to access the internet via the Domain Controller.

This setup simulates a real-world environment for hands-on practice in Active Directory, DHCP, and PowerShell scripting.

---

## Objectives
- Install and configure Oracle VirtualBox.
- Set up a Windows Server virtual machine.
- Promote the server to a Domain Controller.
- Manage Active Directory users using PowerShell scripts.

---

## Skills Demonstrated
- **Virtualization**: Setting up and managing virtual machines.
- **Windows Server Administration**: Installing and configuring Windows Server roles.
- **Active Directory**: Configuring and managing Active Directory Domain Services.
- **PowerShell Scripting**: Automating user management tasks.

---

## Tools and Technologies
- **Oracle VirtualBox**: Virtualization platform.
- **Windows Server**: Operating system for the Domain Controller.
- **Active Directory Domain Services (AD DS)**: Directory service for Windows domain networks.
- **PowerShell**: Scripting language for task automation.

---

## Setup Instructions

### 1. Install Oracle VirtualBox
Download and install [Oracle VirtualBox](https://www.virtualbox.org/).

### 2. Set Up Windows Server VM
- Create a new virtual machine and install Windows Server.
- Configure network settings and ensure the VM has internet access.

### 3. Promote to Domain Controller
- Install the Active Directory Domain Services (AD DS) role.
- Promote the server to a Domain Controller and create a new domain.

### 4. Manage Users with PowerShell
- Write PowerShell scripts to add, modify, and delete users in Active Directory.

---

## Results
- Successfully set up a virtualized environment with Active Directory.
- Automated user management tasks using PowerShell scripts.

---

## Conclusion
This project provided hands-on experience in setting up an Active Directory environment, enhancing skills in virtualization, server administration, and scripting.

---

## Screenshots

### Download VirtualBox and Windows Server 2022 ISO
- **Download VirtualBox:** [www.virtualbox.org](https://www.virtualbox.org)
  ![VirtualBox Download Page](screenshots/virtualbox-download.png)

- **Download Windows Server 2022 ISO:** [Microsoft Evaluation Center](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022)
  ![Windows Server ISO Download](screenshots/iso.png)

---

### VirtualBox Installed
This screenshot shows that Oracle VirtualBox is installed and ready for use:

![VirtualBox Installed](screenshots/virtualbox-installed.png)

---

### Virtual Machine Settings
These screenshots show the hardware, hard disk, and storage settings for the Windows Server 2022 VM:

#### Hardware Settings
![VirtualBox VM Settings](screenshots/virtualbox-hardware.png)

#### Hard Disk Settings
![VirtualBox Hard Disk Settings](screenshots/virtualbox-hdd.png)

#### Storage/ISO Settings
![VirtualBox ISO Settings](screenshots/virtualbox-isosettings.png)

---

### Windows Server Installation

#### Select Custom Install
![Windows Install Screen](screenshots/customos.png)

#### Edition Selection
![Windows Edition Selection](screenshots/installos.png)

#### Disk Selection
![Windows Disk Selection](screenshots/installos2.png)

#### Windows Server 2022 GUI
![Windows First Login](screenshots/windowsgui1.png)

---

## Configuring Network Adapters in VirtualBox

### Step 1: Access VirtualBox Network Settings
1. Open **VirtualBox** and select your **Windows Server 2022 VM**.
2. Click on **Settings** (gear icon) → Navigate to the **Network** tab.

### Step 2: Configure Adapter 1 (NAT)
1. Under **Adapter 1**, ensure the following settings:
   - **Enable Network Adapter**: Checked.
   - **Attached to**: NAT.

![Adapter 1 (NAT)](screenshots/virtualbox-networksettings1.png)

### Step 3: Configure Adapter 2 (Internal Network)
1. Click on **Adapter 2** and configure the following:
   - **Enable Network Adapter**: Checked.
   - **Attached to**: Internal Network.

![Adapter 2 (Internal Network)](screenshots/virtualbox-networksettings2.png)

---

## Configuring Network Adapters in Windows Server

### Step 1: Access the Network Menu
![Accessing the Network Menu](screenshots/network1.png)

### Step 2: Open Network & Internet Settings
![Network Settings](screenshots/network2.png)

### Step 3: Access Change Adapter Options
![Change Adapter Options](screenshots/network3.png)

---

