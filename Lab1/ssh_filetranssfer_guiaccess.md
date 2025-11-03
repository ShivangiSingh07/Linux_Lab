# Experiment 3: Transferring a file between two laptops using gui access

## Objective

 To transfer a file from from system one to system two using graphical user interface (GUI) methods.


## Material Required:

*   Two laptops
* a file on a system.
* USB drive or WI-FI connection or cloud storage account (e.g.,Google  Drive)

### System One (Sender)

1. Open File Manager. (Nautilus)

2. Right_click the folder

 Choose "Local Netwrok Share" (if not visible, install nasutilus_share.)
 
3. 	Enable Sharing
• 	Check "Share this folder"
• 	Optionally allow others to create/delete files
• 	Check "Guest access" for easier access
• 	Click Create Share
4. 	Allow Firewall Access (if prompted)
Accept any prompts to allow file sharing through the firewall.
5. 	Note the Hostname or IP Address
Open Terminal and run  or  to get the address System Two will use.

### System Two (Receiver)
1. 	Open File Manager (Nautilus)
Press Ctrl + L to focus the address bar.
2. 	Access the Shared Folder
Type:
```bash 

smb://<SystemOne_IP_or_hostname>

```
3. 	Browse to the Shared Folder
Open the folder containing the  file.
4. 	Copy the File
Right-click the  file → Copy → Paste it into a local folder.

## Result
The  file is successfully transferred from System One to System Two using GUI-based Samba sharing.


<h2 align="center">Thank you☺️</h2>
