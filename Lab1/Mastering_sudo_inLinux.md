Let’s level up with intermediate and advanced terminal commands, diving into essential topics like user management, file permissions, and powerful sudo operations—key skills for mastering system administration and development on Linux and macOS.


## sudo- Run Commands as Administrator

`sudo` (SuperUser DO) allows you to run commands with root privileges.
````bash
sudo command
````
Example

```bash
sudo apt update      # Run package update as admin
sudo reboot          # Reboot system

```
In most cases, you'll be asked to enter your password.

## User Management (Linux/macOS only)

`adduser` - creates a new user.
 
 ```bash
 sudo adduser newusername
 ```
 You'll be asked to provide with user info and password

`passwd` - Change user password

 ```bash
 sudo passwd newusername
 ```

`usermod` - modify user account

 Add a user to a group 

 ```bash
 sudo usermod -aG groupname username
 ```
  Example 

  ```bash 
  sudo usermod -aG sudo alice     # Give 'alice' sudo access
  ```
  ## deluser – Delete a User

```bash 
sudo deluser username
```
To remove the user's home directory:

```bash
sudo deluser --remove-home username
```
## File Permissions with chmod and chown

`chmod` - Change file Permissions

Common Usage:

```bash
chmod 755 script.sh     # Owner: read/write/execute; others: read/execute
chmod +x file.sh        # Add execute permission
chmod -x file.sh        # Remove execute permission
```
What Do Numbers Mean :

| Number | Permission             |
| ------ | ---------------------- |
| 7      | read + write + execute |
| 6      | read + write           |
| 5      | read + execute         |
| 4      | read only              |
| 0      | no permission          |

Example:

```bash
chmod 644 file.txt
# Owner: read/write, Group: read, Others: read
```
` chown` – Change File Owner

```bash
sudo chown user:group file
```

Example:

`sudo chown alice:alice myfile.txt`

## Shutdown and Reboot

```bash
sudo apt update      # Run package update as admin
sudo reboot          # Reboot system
```





