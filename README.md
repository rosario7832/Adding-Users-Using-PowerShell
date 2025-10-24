# Adding-Users-Using-PowerShell
A PowerShell script will be used to add 1,000 new users to Active Directory. The script can be found in the repository, inside the folder named `AD_PS-master`.

1. **Download and unzip** the `AD_PS-master` folder.  
2. Inside the folder, you will find:
   - A PowerShell script **1_CREATE_USERS.ps1**.
   - A plain text file (`names.txt`) containing the usernames to be added.  
   You can open `names.txt` and add your name or other usernames.
<img src="https://i.imgur.com/SR1BoQ5.png" height="50%" width="60%"/>

3. **Open PowerShell** as an administrator.  
4. **Open the script** `1_CREATE_USERS.ps1` in PowerShell.  


5. **Allow script execution** by running the following command:

   **Set-ExecutionPolicy Unrestricted**
   
6. In the window that appears, click **Yes to All**.

7. To run the script, make sure you are in the directory that contains 1_CREATE_USERS.ps1.

<img src="https://i.imgur.com/bDYniXh.png" height="70%" width="70%"/>

8. Run the script by clicking Run, and in the warning window that appears, select **Run Once**.

9. The users will be created, and you can see the progress directly in the PowerShell window.

<img src="https://i.imgur.com/avaiXD9.png" height="70%" width="70%"/>

10. Once the user creation is complete, you can go to **Active Directory Users and Computers** and see that a directory named `_USERS` has been created, containing the 1,000 users that were added using PowerShell.

<img src="https://i.imgur.com/zg4ZPMW.png" height="70%" width="70%"/>

# PowerShell Script Overview for Adding Users to Active Directory

## Initial Variables
- `$PASSWORD_FOR_USERS` sets the password that will be used for all users.
- `$USER_FIRST_LAST_LIST` reads a list of full names from a file called `names.txt`.

## Prepare the Password
- Converts the password into a secure string (`SecureString`) so it can be used safely when creating users.

## Create an Organizational Unit (OU)
- `New-ADOrganizationalUnit` creates an OU named `_USERS` where all the users will be stored.

## Create Users in Active Directory
- Loops through each line in `names.txt`.
- Splits the full name into first and last names, then generates a username using the first letter of the first name + last name (all lowercase).
- Shows on-screen which user is being created (`Write-Host`).
- `New-ADUser` creates the user in AD with:
  - First name, last name, and display name.
  - The defined password.
  - Password set to never expire.
  - Placement inside the `_USERS` OU.
  - User enabled.
