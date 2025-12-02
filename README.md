# Windows Notes

Notes from Try Hack Me's Windows Fundamentals Path

## Intro to Windows

- File System
  - NTFS
    - New Technology File System
    - Known as a journaling file system
      - The file system can automatically repair the folders/files on disk using information stored in a log file
    - Supports files larger than 4GB
    - Folder and file compresison
    - Set specific permissions on files and folders
      - Full control
      - Modify
      - Read & Execute
      - List folder contents
      - Read
      - Write
    - Encryption
      - Encryption FIle System (EFS)
    - Alternate Data Streams
      - ADS allows files to contain more than one stream of data.
      - Hidden to Windows user. Accessible via PowerShell
  - FAT16/32
    - File Allocation Table
    - Before NTFS
    - Typically used in USB devices or MicroSD
  - HPFS 
    - High Performance File System

## System32 Folders

- Windows folder typically contains Windows Operating System
  - `C:\Windows`
  - Folder doesn't have to reside on `C:\` drive
  - `%windir%` contains system enviornmental variables
  - `System32` Folder
    - Critical for Windows OS operations
    - [More info here](https://www.howtogeek.com/346997/what-is-the-system32-directory-and-why-you-shouldnt-delete-it/)
  
## User Accounts, Profiles and Permissions

- Two typical user accounts
  - Administrator
    - Add users, delete users, modify groups, modify settings on the system, etc. 
  - Standard User
    - Make changes to folders/files attributed to the user & can't perform system-level changes, such as install programs.
  - Accounts appear in `Users` folder
    - `C:\Users\Dave`
  - Each user will have the following folders
    - Each user profile will have the same folders; a few of them are:
      - Desktop
      - Documents
      - Downloads
      - Music
      - Pictures

## User Account Control

- User Account Control
  - When a user with an account type of administrator logs into a system, the current session doesn't run with elevated permissions. When an operation requiring higher-level privileges eeds to execute, the user will be prompted to confirm if they permit the operation to run. 
  - Noted by a shield icon 
  - UAC will prompt to allow higher-level privileges to install the program.

## Settings and Control Panel

- Control Panel/Settings are the primary locations to make changes.

## Task Manager




