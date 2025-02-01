# Active Directory Home Lab

## Table of Contents
- [Overview](#overview)
- [Lab Architecture](#lab-architecture)
- [Objectives](#objectives)
- [Skills Demonstrated](#skills-demonstrated)
- [Tools and Technologies](#tools-and-technologies)
- [Setup Instructions](#setup-instructions)
- [Results](#results)
- [Conclusion](#conclusion)
- [Screenshots](#screenshots)
- [Configuring Network Adapters in VirtualBox](#configuring-network-adapters-in-virtualbox)
- [Configuring Network Adapters in Windows Server](#configuring-network-adapters-in-windows-server)

---

## Configuring Network Adapters in Windows Server

### Step 1: Access the Network Menu
1. Navigate to the **system tray** at the bottom-right corner of the screen.
2. Locate the **network icon** (it may appear as a globe or Wi-Fi symbol).
3. **Right-click** the network icon to open the menu.

![Accessing the Network Menu](screenshots/network1.png)

---

### Step 2: Open Network & Internet Settings
1. From the network menu, click on **Network & Internet settings**.
2. This opens the Windows Settings panel with network-related options.

![Network Settings](screenshots/network2.png)

---

### Step 3: Access Change Adapter Options
1. In the **Network & Internet Settings** window, select **Ethernet** from the left-hand panel.
2. Under **Related settings**, click **Change adapter options**.
3. This opens the **Network Connections** window.

![Change Adapter Options](screenshots/network3.png)

---

### Step 4: View Available Network Adapters
1. In the **Network Connections** window, you’ll see a list of all available adapters.
   - Each adapter shows its name and current status (e.g., `Network` or `Unidentified network`).

![Available Adapters](screenshots/networkadapters1.png)

---

### Step 5: Identify the Internet-Connected Adapter
1. Right-click on each adapter and select **Status** to view its connection details.
2. In the **Ethernet Status** window, click **Details...** to see network properties.

**Screenshots:**
- **Checking Adapter Status:**
  ![Adapter Status](screenshots/networkadapters2.png)

- **Network Connection Details:**
  ![Connection Details](screenshots/networkadapters3.png)

---

### Step 6: Verify the Internet-Connected Adapter
- Look for the following details in the **Network Connection Details** window:
  1. **IPv4 Address**: `10.0.2.15` (indicates this adapter is active on the network).
  2. **Default Gateway**: `10.0.2.2` (confirms this adapter is used to route traffic to the internet).
  3. **DHCP Enabled**: `Yes` (shows the adapter is receiving its IP address dynamically).

**Explanation:**
- The adapter with a valid **IPv4 Address** and a configured **Default Gateway** is connected to the internet.
- In this case, the adapter with IP `10.0.2.15` is the internet-connected adapter.

---

### Step 7: Rename the Adapters for Easy Identification
1. In the **Network Connections** window, right-click each adapter and select **Rename**.
2. Rename the adapters as follows:
   - **Adapter connected to the internet:** `_INTERNET_`.
   - **Adapter for internal communication:** `X_internal_X`.

![Renamed Adapters](screenshots/networktrename.png)

---

### Benefits of Renaming Adapters
1. **Improved Clarity**:
   - Clearly distinguishes between the external (internet-facing) and internal adapters.
2. **Prevents Configuration Errors**:
   - Makes it easier to assign services like DHCP, DNS, or Active Directory roles.
