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
```
mkdir asgar
```
<img width="1506" height="92" alt="image" src="https://github.com/user-attachments/assets/152dcdd1-0b87-48f4-b775-7de50bfdcd6c" />



## COMMAND AND OUTPUT

Remove the directory "my-folder"
```
rmdir asgar
```
<img width="1557" height="111" alt="image" src="https://github.com/user-attachments/assets/919b1d00-0b2a-4b0a-a628-dbe8c7256617" />



## COMMAND AND OUTPUT


Create the file Rose.txt
```
type nul > rose.txt
```
<img width="1600" height="87" alt="image" src="https://github.com/user-attachments/assets/11ba20ce-9429-4f4d-ab44-7ae75564448c" />




## COMMAND AND OUTPUT


Create the file hello.txt using echo and redirection
```
echo Hello World > hello.txt
```
<img width="1607" height="76" alt="image" src="https://github.com/user-attachments/assets/52c76969-a4a8-42c0-bf84-bb6ba7eef9a9" />



## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt
```
copy hello.txt hello1.txt
```
<img width="1411" height="125" alt="image" src="https://github.com/user-attachments/assets/8efbf271-bba4-4617-9b4a-30fb762d25c3" />



## COMMAND AND OUTPUT

Remove the file hello1.txt
```
del hello1.txt
```
<img width="502" height="31" alt="image" src="https://github.com/user-attachments/assets/6ab7d8f2-9d49-42ac-b316-02e52e78d48f" />


## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory
```
dir hello1.txt
```
<img width="533" height="167" alt="image" src="https://github.com/user-attachments/assets/6f4f33ec-5b78-47e5-8576-3b1def9c91c0" />


## COMMAND AND OUTPUT

List out all the associated file extensions 
```
assoc
```
<img width="562" height="690" alt="image" src="https://github.com/user-attachments/assets/b33182f3-3dbe-493b-aa1e-4ca6348d5e01" />


## COMMAND AND OUTPUT


Compare the file hello.txt and rose.txt
```
fc hello.txt rose.txt
```
<img width="627" height="138" alt="image" src="https://github.com/user-attachments/assets/340dfa79-afe7-4d57-924b-c48c001a2344" />


## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
@echo off
set name=John
echo Hello, %name%
pause
```





## OUTPUT
<img width="907" height="292" alt="image" src="https://github.com/user-attachments/assets/0771caf5-c88a-43ad-aeac-98292b9c9022" />





Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
## CODE
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
<img width="907" height="367" alt="image" src="https://github.com/user-attachments/assets/497b267d-0192-4f69-aa19-8470ca79657c" />






Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
## CODE
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```




## OUTPUT
<img width="667" height="302" alt="image" src="https://github.com/user-attachments/assets/cf90a593-9f23-4927-8f3e-6da16b93d9d4" />






Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
## CODE
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
<img width="335" height="32" alt="image" src="https://github.com/user-attachments/assets/afe3b0a3-0c65-4068-a216-beb24b16adc6" />




Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
## CODE
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



## OUTPUT 1
<img width="530" height="137" alt="image" src="https://github.com/user-attachments/assets/c2e90cef-2a40-461d-afec-98c1cae1755f" />

## OUTPUT 2
<img width="387" height="132" alt="image" src="https://github.com/user-attachments/assets/95c60b1e-09bb-4629-9f47-d7610042fe04" />

## OUTPUT 3
<img width="455" height="132" alt="image" src="https://github.com/user-attachments/assets/37b88dca-f5ff-4314-8a3f-9c46f7cda58d" />








# RESULT:
The commands/batch files are executed successfully.
