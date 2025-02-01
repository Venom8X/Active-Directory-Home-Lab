# Active Directory Home Lab

## Table of Contents
- [Overview](#overview)
- [Lab Architecture](#lab-architecture)
- [Objectives, Skills Demonstrated, and Tools](#objectives)
- [Results and Conclusion of this Lab](#results)
- [PowerShell Usage for Project Management](#powershell-usage-for-project-management)
- [Setup Instructions](docs/setup.md)
- [Using Active Directory](docs/usingAD.md)
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

## Tools
- **Oracle VirtualBox**: Virtualization platform.
- **Windows Server**: Operating system for the Domain Controller.
- **Active Directory Domain Services (AD DS)**: Directory service for Windows domain networks.
- **PowerShell**: Scripting language for task automation.

---

## Results
- Successfully set up a virtualized environment with Active Directory.
- Automated user management tasks using PowerShell scripts.

---

## Conclusion
This project provided hands-on experience in setting up an Active Directory environment, enhancing skills in virtualization, server administration, and scripting.

---

## PowerShell Usage for Project Management

This project was managed and documented entirely using **PowerShell**, showcasing my proficiency in using PowerShell for version control, automation, and project documentation. Below are the specific PowerShell commands and workflows I utilized:

### Repository Setup
- Created the local repository and linked it to the remote GitHub repository:
  ```powershell
  git init
  git remote add origin https://github.com/your-username/repository-name.git

### Commit and Version Control
- Tracked file changes, staged updates, and committed code/documentation:
  ```powershell
  git add .
  git commit -m "Commit message"
- Pushed commits to GitHub
  ```powershell
  git push origin main

### Branching and Merging
- Used branches for feature development and documentation updates:
  ```powershell
  git branch feature-branch
  git checkout feature-branch
  git merge feature-branch

### Remote Repository Management
- Updated the remote repository URL after a username change:
  ```powershell
  git remote set-url origin https://github.com/new-username/repository-name.git

### Screenshots and Documentation
- Used [ShareX](https://getsharex.com/) to capture screenshots and managed file structure using PowerShell.
- Committed updated screenshots and linked them in documentation files:
  ```powershell
  git add screenshots/
  git commit -m "Added screenshots for documentation"

### Workflow Automation
- Automated repetitive tasks, such as adding, committing, and pushing changes, by creating custom PowerShell scripts:
  ```powershell
  # Example Script
  git add .
  git commit -m "Automated commit message"
  git push origin main

### Collaboration and Conflict Resolution
- Resolved merge conflicts and ensured code integrity using PowerShell commands:
  ```powershell
  git status
  git diff
  git merge --abort

### SSH Key Management
- Configured SSH authentication to streamline interactions with GitHub:
  ```powershell
  ssh-keygen -t rsa -b 4096 -C luisvandenbussche@gmail.com
  ssh-add ~/.ssh/id_rsa

## Why I Used PowerShell

- **Professionalism**: PowerShell is widely used in IT and DevOps environments, demonstrating my ability to work in professional workflows.
- **Efficiency**: Automating tasks through PowerShell scripts saved time and ensured consistent management of the project.
- **Version Control Expertise**: Managed the entire project lifecycle, from initialization to deployment, using Git commands in PowerShell.
- **Reproducibility**: PowerShell scripts and workflows ensure that the project setup can be replicated by others in a structured and efficient manner.

