# 📝Report : File Check Script in Bash

## 📌Objective: To create a BASH script that checks whether a file exits, dispalys its contents if it does and offers to creae it if it doesn't.


### 🪜Steps Followed:


#### 1️⃣Creation of a Script File

* Firstly we create an empty script file.
 
   ![Image 1](<Images/WhatsApp Image 2025-09-18 at 12.15.20_a4978a6f.jpg>)
 
* This command generated a blank file named `file_check.sh` in the `Scripts` directory.


#### 2️⃣Writing the Script

* We opened the file in a text editor `nano` and wrote the fillowing code:

  ![Image 2](<Images/WhatsApp Image 2025-09-18 at 12.18.08_89a196a7.jpg>)

#### 3️⃣Make the Script Executable

* give it permission to run:

  ```bash
  chmod +x file_check.sh
  ```
#### 4️⃣Run the Script

* you execute it with a filename:

  ![Image 3](<Images/WhatsApp Image 2025-09-18 at 12.15.20_08a7a597.jpg>)



* If the file doesn't exist, the script asks:

  ```bash
  File "filename" does not exist.
  create it now/ (y/N):
  ```
* You type `y` to create a file and edit it using any editor `nano`

  ![Image 4](<Images/WhatsApp Image 2025-09-18 at 12.47.27_1fe9d85e.jpg>)


