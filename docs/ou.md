# Adding Users to Active Directory Using Powershell

## Table of Contents
- [PowerShell Script for Creating Active Directory Users](#powershell-script-for-creating-active-directory-users)
- [How the Script Works](#how-the-script-works)
- [File Requirements](#file-requirements)
- [Notes](#notes)
- [Instructions for Using the Script in PowerShell ISE](#instructions-for-using-the-script-in-powershell-ise)
- [Sample User Data File](#sample-user-data-file)
- [Next Step:](docs/.md)
- [Back to Active Directory Home Lab README](../README.md)


## PowerShell Script for Creating Active Directory Users

This project uses a PowerShell script to automate the creation of Active Directory users. Below is the script and a breakdown of its functionality:

```powershell
# ----- Edit these Variables for your own Use Case ----- #
$PASSWORD_FOR_USERS   = "Password1"
$USER_FIRST_LAST_LIST = Get-Content .\names.txt
# ------------------------------------------------------ #

$password = ConvertTo-SecureString $PASSWORD_FOR_USERS -AsPlainText -Force
New-ADOrganizationalUnit -Name _USERS -ProtectedFromAccidentalDeletion $false

foreach ($n in $USER_FIRST_LAST_LIST) {
    $first = $n.Split(" ")[0].ToLower()
    $last = $n.Split(" ")[1].ToLower()
    $username = "$($first.Substring(0,1))$($last)".ToLower()
    Write-Host "Creating user: $($username)" -BackgroundColor Black -ForegroundColor Cyan
    
    New-AdUser -AccountPassword $password `
               -GivenName $first `
               -Surname $last `
               -DisplayName $username `
               -Name $username `
               -EmployeeID $username `
               -PasswordNeverExpires $true `
               -Path "ou=_USERS,$(([ADSI]`"").distinguishedName)" `
               -Enabled $true
}
```
---

## How the Script Works

### Variable Setup:
- **PASSWORD_FOR_USERS**:  
  This sets the default password for all created users. You should replace `"Password1"` with a strong, secure password.  
- **USER_FIRST_LAST_LIST**:  
  This reads a list of user names (in the format `FirstName LastName`) from a file named `names.txt` located in the same directory as the script.

### Convert Password to Secure String:
- Converts the plain text password into a secure string to meet PowerShell's security requirements.

### Create Organizational Unit:
- Creates a new Organizational Unit (OU) named `_USERS`, which will house the new users.  
- The `ProtectedFromAccidentalDeletion` option is disabled.

### User Creation Loop:
For each name in `names.txt`, the script:
1. Extracts the first name and last name.
2. Constructs a username using the first letter of the first name and the full last name (e.g., `"John Doe"` becomes `"jdoe"`).
3. Creates the user in Active Directory with the following attributes:
   - **GivenName**: First name.
   - **Surname**: Last name.
   - **DisplayName**: The username.
   - **Name**: The username.
   - **EmployeeID**: The username.
   - Assigns the password defined in `$PASSWORD_FOR_USERS`.
   - Sets the user's password to never expire.
   - Places the user in the `_USERS` Organizational Unit.
   - Enables the user account.

## File Requirements

### `names.txt`:
- A text file containing a list of names in the format `FirstName LastName`, one per line.  
- **Example:**
  ```plaintext
  John Doe
  Jane Smith
  Alice Johnson

## Notes

- Ensure that the PowerShell script is executed on a system with the Active Directory module installed and connected to a domain controller.
- Customize the `names.txt` file and password to suit your organization's requirements.
- The script creates users with basic attributes. You can extend it to include additional attributes as needed.

### This script demonstrates automation with PowerShell and highlights ability to manage Active Directory effectively.

---

## Instructions for Using the Script in PowerShell ISE

To run the provided PowerShell script in **PowerShell ISE**, follow these steps:

---

### Step 1: Open PowerShell ISE
1. Press `Windows + S` to open the search bar.
2. Type `PowerShell ISE` and select the **Windows PowerShell ISE** application.

---

### Step 2: Create and Save the Script
1. In PowerShell ISE, click on `File` > `New` to open a new script file.
2. Copy and paste the provided PowerShell script into the editor window.
3. Save the script with a `.ps1` extension by clicking on `File` > `Save As`. For example, save it as `CreateUsers.ps1`.

---

### Step 3: Prepare the `names.txt` File
1. Create a text file named `names.txt` in the same directory where the script is saved.
2. Add the list of users in the format `FirstName LastName`, one user per line.
   - **Example**:
     ```plaintext
     John Doe
     Jane Smith
     Alice Johnson
     ```

---

### Step 4: Modify Script Variables (Optional)
1. Open the script file (`CreateUsers.ps1`) in PowerShell ISE.
2. Edit the following variables at the top of the script:
   - `PASSWORD_FOR_USERS`: Replace `"Password1"` with a strong password for the users.
   - `USER_FIRST_LAST_LIST`: Ensure the file path points to the correct `names.txt` location.

---

### Step 5: Run the Script
1. Use the following command in PowerShell ISE for convenience during this lab: 

```powershell
Set-ExecutionPolicy Unrestricted
```
2. In PowerShell ISE, press `Ctrl + O` and open the saved `CreateUsers.ps1` script.
3. Highlight the script content or ensure the cursor is anywhere within the script window.
4. Click `Run Script` or press `F5` to execute the script.

---

### Step 6: Verify User Creation
1. Ensure the script completes successfully.
2. Verify that:
   - The `_USERS` Organizational Unit has been created in Active Directory.
   - The users from `names.txt` are created within the `_USERS` Organizational Unit.

---

### Notes
- Ensure that PowerShell is running with administrative privileges.
- The system must have the **Active Directory module** installed and be connected to the domain controller.
- If any errors occur, check the error messages for details and verify that the `names.txt` file and variables are configured correctly.

---

## Sample User Data File

This project includes a `names.txt` file containing a list of 1000 names that the PowerShell script pulls from to create users in Active Directory.

### **File Structure**
Each line in `names.txt` consists of a **first name** and **last name**, separated by a space. The script processes each line to generate usernames and create user accounts in AD.

### **Example Entries from `names.txt`**
```plaintext
John Doe
Jane Smith
Alice Johnson
Michael Brown
Sarah Davis
```
### Usage

- Ensure `names.txt` is located in the same directory as the PowerShell script.
- The script reads names from `names.txt`, generates usernames, and creates corresponding AD user accounts.
- Each username is constructed using **the first letter of the first name + full last name**  
  _(e.g., John Doe → `jdoe`)._

### Customizing `names.txt`

- You can modify this file to include real or test users based on your needs.
- Ensure each entry follows the `FirstName LastName` format to avoid errors.

---

This file enables **bulk user creation in Active Directory**, demonstrating automation through PowerShell.


[🔝 Back to Table of Contents](#table-of-contents)

##
[Next Step:](docs/.md)

[Back to Active Directory Home Lab README](../README.md)
##