# Using Active Directory

## Table of Contents
- [Installing Active Directory Domain Services (AD DS)](#installing-active-directory-domain-services-(ad-ds))

##
- [Back to Active Directory Home Lab README](../README.md)
##

## **Installing Active Directory Domain Services (AD DS)**

### Step 1: Open Server Manager and Select "Add Roles and Features"
1. Launch **Server Manager** from the Start menu or taskbar.
2. Click on **Add roles and features** to open the wizard.

![Server Manager Dashboard](../screenshots/servermanager.png)

---

### Step 2: Begin the Add Roles and Features Wizard
1. In the **Before You Begin** screen, review the prerequisites:
   - Administrator account has a strong password.
   - Static IP addresses are configured.
   - Latest Windows Updates are installed.
2. Click **Next** to continue.

![Before You Begin](../screenshots/servermanager2.png)

---

### Step 3: Select the Server Roles
1. Keep clicking **Next** until you reach the **Server Roles** screen.
2. Check **Active Directory Domain Services**.

![Select Server Roles](../screenshots/servermanager3.png)

---

### Step 4: Add Required Features
1. A dialog box will appear asking to add features required for AD DS.
2. Click **Add Features**.

![Add Features](../screenshots/servermanager4.png)

---

### Step 5: Confirm and Install
1. Continue clicking **Next** until you reach the **Confirmation** screen.
2. Review the selected roles and features to ensure everything is correct.
3. Click **Install** to begin the installation process.

![Confirm Installation](../screenshots/servermanager5.png)

---

Once the installation is complete, proceed to the next steps to configure your new domain.


## 1. Manage Users with PowerShell
- Write PowerShell scripts to add, modify, and delete users in Active Directory.

##
- [Back to Active Directory Home Lab README](../README.md)
##
