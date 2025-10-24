# Adding-Users-Using-PowerShell
A PowerShell script will be used to add 1,000 new users. The script can be found at the following link.

## Steps

1. **Download and unzip** the `AD_PS-master` folder.  
2. Inside the folder, you will find:
   - A PowerShell script **1_CREATE_USERS.ps1**.
   - A plain text file (`names.txt`) containing the usernames to be added.  
   You can open `names.txt` and add your name or other usernames.
3. **Open PowerShell** as an administrator.  
4. **Open the script** `CREATE_USERS.ps1` in PowerShell.  
5. **Allow script execution** by running the following command:

   **Set-ExecutionPolicy Unrestricted**
   
6. In the window that appears, click **Yes to All**.

7. Navigate to the directory containing **1_CREATE_USERS.ps1**.

8. Run the script by clicking Run, and in the warning window that appears, select **Run Once**.

9. The users will be created, and you can see the progress directly in the PowerShell window.
