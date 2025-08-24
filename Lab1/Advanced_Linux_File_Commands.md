# Advanced Linux File Commands
 

 ## 1. File Manipulation Commands
 
 `touch` -Create or Update File Timestamps

 ```bash
 # Create an empty file
 touch filename.txt

 # Update timestamp of an existing file
 touch existing.txt

 # Create multiple files at once
 touch filename2.txt filename3.txt
```
 `cp` -Copy Files and Directories

 ```bash
 # Copy a file
cp original.txt copy.txt

# Copy to another directory
cp original.txt /path/to/copy/

# Copy directory recursively
cp -r dir1 dir2

# Preserve file attributes (timestamps, permissions)
cp -p original.txt backup.txt
```
`rm`- Remove Files and Directories 

```bash
# Remove a file
rm file.txt

# Remove multiple files
rm file1.txt file2.txt

# Remove a directory recursively
rm -r foldername/

# Force remove without prompt
rm -rf foldername/
 ```

 `cat`- View or Concatenate Files

 ```bash
 # Display file contents
cat file.txt

# Combine multiple files into one
cat file1.txt file2.txt > combined.txt

# Display file with line numbers
cat -n file.txt
```
### 2. File Permissions and Ownership

 `ls -la`- View Deatiled File Info

 ```bash
 ls -l
# Example output:
# -rw-r--r-- 1 user group 1024 Aug 14 10:00 filename.txt
# Breakdown:
# [1] -rw-r--r-- → Permissions
# [2] 1 → Hard link count
# [3] user → Owner
# [4] group → Group owner
# [5] 1024 → File size (bytes)
# [6] Aug 14 10:00 → Last modified date/time
# [7] filename.txt → File name
```
### File Permission Structure

* **Owner (u)** - File creator
* **Group (g)** - Users in same group
* **Others (o)** - Everyone else
Permissions: **r (read)**, **w (write)**, **x (execute)**

`chmod` - Change File Permissions

```bash
# Symbolic menthod
chmod u+x file.sh  #Add execute for owner 
chmod g-w file.txt # Remove write for group
chmod o+r file.txt # Add read for others

# Numeric method (r=4, w=2, x=1)
chmod 755 file.sh #rwxr-xr-x
chmod 644 file.txt #rww-r--r--
```
`ln` - Create links

```bash
# Hard link
ln original.txt hardlink.txt

# Symbolic (soft) link
ln -s /path/to/original symlinknam
```







