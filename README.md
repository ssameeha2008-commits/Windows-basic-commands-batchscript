# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"
## COMMAND AND OUTPUT
mkdir my-folder
<img width="483" height="77" alt="image" src="https://github.com/user-attachments/assets/547b62f8-3563-4aa6-b9e4-bc9470b2e179" />

Remove the directory "my-folder"

## COMMAND AND OUTPUT
rmdir my-folder
<img width="506" height="67" alt="image" src="https://github.com/user-attachments/assets/e47855eb-3062-4ca2-a558-9bffa7c64334" />

Create the file Rose.txt

## COMMAND AND OUTPUT
type nul > Rose.txt
<img width="685" height="62" alt="image" src="https://github.com/user-attachments/assets/9562d940-4ee2-4795-8b3f-93970661b6fd" />

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
echo Hello World > hello.txt
<img width="707" height="65" alt="image" src="https://github.com/user-attachments/assets/5bfefecc-4bd2-414f-b633-02d120281bcf" />

Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
copy hello.txt hello1.txt
<img width="625" height="83" alt="image" src="https://github.com/user-attachments/assets/58c25064-ec5c-4fc9-8b7a-ca26d88da6f3" />

Remove the file hello1.txt

## COMMAND AND OUTPUT
del hello1.txt
<img width="547" height="226" alt="image" src="https://github.com/user-attachments/assets/bc4d1c9f-e9e4-4714-847f-e166ea6049ca" />

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
dir hello1.txt
<img width="548" height="226" alt="image" src="https://github.com/user-attachments/assets/397ccd65-92f0-4649-9229-1423c3f568ff" />

List out all the associated file extensions 

## COMMAND AND OUTPUT
assoc
<img width="779" height="805" alt="image" src="https://github.com/user-attachments/assets/87413d4d-217f-439d-95d2-de9fef378c00" />

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
fc hello.txt Rose.txt
<img width="666" height="202" alt="image" src="https://github.com/user-attachments/assets/6c685692-f3e3-4218-9787-54f67dc5255c" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

## CODE:
```
@echo off
set name=John
echo Hello, %name%
pause
```



## OUTPUT
<img width="612" height="89" alt="image" src="https://github.com/user-attachments/assets/693863ee-ff1c-4d9f-af30-2207eedeb98e" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

## CODE:
```
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE

:END
echo Thank you!
pause
```
## OUTPUT
<img width="805" height="258" alt="image" src="https://github.com/user-attachments/assets/f8b2928d-f9d4-497f-a3b9-e2168f0b13cc" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

## CODE:
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```

## OUTPUT
<img width="576" height="210" alt="image" src="https://github.com/user-attachments/assets/eb1e2f6b-5192-4a9e-9a6d-e2291c0b7a0b" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
## CODE:
```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```

## OUTPUT

<img width="534" height="72" alt="image" src="https://github.com/user-attachments/assets/89b8fdcc-c244-46c2-af28-3bb1b9dc1004" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
## CODE:
```
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU

:EXIT
echo Goodbye!
pause
exit
```

## OUTPUT1
<img width="513" height="237" alt="image" src="https://github.com/user-attachments/assets/dc146834-76a4-4f02-ae04-56e8b4c59d7d" />
## OUTPUT2
<img width="562" height="268" alt="image" src="https://github.com/user-attachments/assets/123d355e-a843-4f79-8e82-11dcb8792918" />
## OUTPUT3
<img width="536" height="252" alt="image" src="https://github.com/user-attachments/assets/aa9e7320-4bba-4df3-880b-b53f5fc9f1a9" />



# RESULT:
The commands/batch files are executed successfully.
The commands/batch files are executed successfully.

