# When you run **`terraform -v`** and output is **command not found** in gitbash 
``` C:\Users\Harshitha R\EKS> terraform init
terraform : The term 'terraform' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if 
a path was included, verify that the path is correct and try again.
```
 ****this is in terminal of vs code****

## The problem here is terraform is not installed and not added to system environment path

### solution

**Step 1:** Download Terraform
(https://developer.hashicorp.com/terraform/install#windows)
> extract it once it's downloaded
> copy the path


**Step 2** : Add Your Current Download Folder to PATH

C:\Users\Harshitha R\Downloads\terraform_1.11.4_windows_amd64
You can add this exact folder to your system PATH instead.

🔧 Steps to add it:
Press Win + S → search “Environment Variables”

Open Edit the system environment variables

In the window that opens, click Environment Variables

Under System Variables, find and click on Path → then click Edit

Click New and paste:

makefile
Copy
Edit
C:\Users\Harshitha R\Downloads\terraform_1.11.4_windows_amd64
Click OK on everything.

🔁 Now restart:
PowerShell

Git Bash

VS Code

Then in any terminal, try:

terraform -v
If it works, you're fully set ✅

**finally we can perform terraform commands**

