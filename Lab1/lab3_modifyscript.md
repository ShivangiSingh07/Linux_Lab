### Assignment 3: Modify an Existing Script

## Objective: Enhance and Modify a Script
 📜
 Script chosen: Script_5.sh

 The program:
 ![alt text](<Images/WhatsApp Image 2025-09-10 at 21.54.47_7d382260.jpg>)

 Output:
 ![alt text](<Images/WhatsApp Image 2025-09-10 at 21.54.47_7d382260-1.jpg>)


*  Before modifying the program, user input was invalid. Range was
 already specified.
 
*  After modifying the program the user can input start, end and
 step values.
 
*  The older script Script_5.sh has been saved as enhanced_numbers.sh.


 The program is as follows:
 ![alt text](<Images/WhatsApp Image 2025-09-10 at 22.22.13_8bf025f5.jpg>)

![alt text](<Images/WhatsApp Image 2025-09-10 at 22.22.20_a9b8dcb7.jpg>)s

Result:


![alt text](<Images/Screenshot 2025-09-10 221912.png>)

Difference between old script and new script:

| 5_script.sh | enhanced_numbers.sh |
| :-------: | :-------: |
| 🔹This script prints numbers in a basic loop ranging from 1-5. | 🔹This script asks the user for input (start, end, step) and includes validation.|
| 🔹User interaction is rare. | 🔹User interaction is included. |
| 🔹It doesn't ask for input from the user. | 🔹It asks for input (start, end and step) from the user. |
| 🔹Range is already specified. | 🔹Range is specified by the user. |

Extra Questions

Q1. Difference between 1,@, and $# in bash?

 Ans. $1: -It is a positional parameter.
 Range is specified by the user.-Represents the first positional argument passed to the script or function

 $@: -Expands to all positional parameters where each paramenter is treated as a
 seperate individually quoted string.-It is crucial especially when arguments contain spaces or special characters.

 $#: -Expands to the total number of positional parameters/arguments passed to the
 script or function.-It displays number of arguments provided.

 Q2. What does exit 1 mean in a script?
Ans. exit 1 means that a problem or an error has occured during the script's
 execution


 
 <h2 align="center">Thank you☺️</h2>