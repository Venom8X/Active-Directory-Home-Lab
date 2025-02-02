# Adding Users to Active Directory Using Powershell

## Table of Contents
- [PowerShell Script for Creating Active Directory Users]()
- [How the Script Works]()
- [File Requirements]()
- [Notes]()
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

---

This script demonstrates automation with PowerShell and highlights your ability to manage Active Directory effectively.

You can copy this explanation and script directly into your `README.md` file to showcase your PowerShell skills and project functionality.
