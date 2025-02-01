# Setting up NAS/RAS

## Table of Contents
- [Configuring NAT and Remote Access Service (RAS)](#step-1-select-role-services-refer-to-installing-active-directory-domain-services-ad-ds-for-adding-roles-and-features)

## Step 1: Select Role Services
(refer to [Installing Active Directory Domain Services (AD DS)](/docs/usingAD.md#step-1-open-server-manager-and-select-add-roles-and-features) for adding roles and features)

1. Open the **Add Roles and Features Wizard**.
2. Navigate to the **Role Services** step under **Remote Access**.
3. Select the following role services:
   - **DirectAccess and VPN (RAS)**
   - **Routing**
4. Click **Next** to proceed.

![Select Role Services](../screenshots/ras.png)

---

## Step 2: Add Required Features

1. When prompted, click **Add Features** to include the required management tools for DirectAccess and VPN (RAS).
2. Ensure that **Include management tools (if applicable)** is checked.
3. Click **Add Features**.

![Add Required Features](../screenshots/ras2.png)

---

## Step 3: Confirm Role Services

1. Ensure that the following options are selected:
   - **DirectAccess and VPN (RAS)**
   - **Routing**
2. If additional role services are needed (e.g., **Web Application Proxy**), you may select them as well.
3. Click **Next** to continue.

![Confirm Role Services](../screenshots/ras3.png)

---

## Step 4: Confirm Installation Selections

1. Review the installation selections to ensure all necessary features and roles are included:
   - **RAS Connection Manager Administration Kit (CMAK)**
   - **Remote Access Management Tools**
   - **Remote Access module for Windows PowerShell**
2. Click **Install** to begin the installation process.

![Confirm Installation Selections](../screenshots/ras4.png)

---

## Conclusion

Once the installation is complete, you can configure your Remote Access and NAT settings as required to provide connectivity and routing for your network environment.


[🔝 Back to Table of Contents](#table-of-contents)
