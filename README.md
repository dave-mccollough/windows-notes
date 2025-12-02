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

## System Configuration

- System configuration utility `msconfig`
- Launched via run command or start menu
- Five tabs
  - General
    - Startup modes
      - Normal, Diagnostic, or Selective. 
  - Boot 
      - Determine Windows boot options. 
  - Services
    - All services configured for the system regardless of their state (running or stopped). 
  - Startup
    - Startup managed in Task Manager
  - Tools
    - Tools tab allows you to configure the operating system further. 

## UAC Settings

- User Account Control
  - The UAC settings can be changed or even turned off entirely (not recommended).

## Computer Administration

- Lauched with `compmgmt.msc` command
- Three key sections
  - System Tools
    - Task Scheduler
      - Create and manage common tasks than can automated at times specified.
      - Task can run applications, scripts, etc
    - Event Viewer
      - View events that have occurred on the computer.
      - Five types of events
        - Error 
        - Warning
        - Informational
        - Success Audit
        - Failure Audit
      - Event details can be found [here](https://learn.microsoft.com/en-us/windows/win32/eventlog/event-types) and [here](https://learn.microsoft.com/en-us/windows/win32/eventlog/eventlog-key).
    - Shared Folders
      - Complete list of shares and folders shared that others can connect to. 
    - Local Users and Groups
    - Performance
      - Performance Monitor (`perfmon`)
        - Ciew performance data either in real-time or from a log file.
    - Device Manager
      - View and configure the hardware,
  - Storage
    - Windows Server Backup
    - Disk Management
      - Set up a new drive
      - Extend a partition
      - Shrink a partition
      - Assign or change a drive letter (ex. E:) 
  - Services and Applications

## System Information

- Launched with `msinfo32` command
- This tool gathers information about your computer and displays a comprehensive view of your hardware, system components, and software environment, which you can use to diagnose computer issues.
- Hardware Resources
  - Learn more [here](https://learn.microsoft.com/en-us/windows-hardware/drivers/kernel/hardware-resources)
- Components
  - Information about hardware devices installed on your computer
  - Network Connections
- Software Enviornment
  - Information about software installed and operating system level software
  - Environment Variables
    - Store information about the operating system environment. 

## Resource Monitor

- launched with `resmon` command
- Displays CPU, memory, disk, and network usage information
- CPU
- Disk 
- Netowrk
- Memory
  
## Command Prompt

- Launched with `cmd` command
- Commands
  - `hostname`
    - Displays computer name
  - `whoami`
    - Displays logged in user
  - `ipconfig`
    - Displays network settings
    - Use `ipconfig /all` to show detailed information
  - `/?`
    - Displays help
      - `ipconfig /?`
  - `cls`
    - Clear screen
  - `netstat`
    - Displays current TCP/IP settings and network protocol info

## Registry

- Launched with `regedit` or `regedt32.exe` command
- Central database used to store information necessary to configure the system for one or more users, applications, and hardware devices.

## Windows Updates

- In Settings
- Windows Update is a service provided by Microsoft to provide security updates, feature enhancements, and patches for the Windows operating system and other Microsoft products, such as Microsoft Defender. 
- Windows Update FAQ [here](https://support.microsoft.com/en-us/windows/windows-update-faq-8a903416-6f45-0718-f5c7-375e92dddeb2)

## Windows Security

- In Settings
- Manage tools that protect device and data
- Protection areas include
  - Virus & threat protection
  - Firewall & network protection
  - App & browser control
  - Device security
- Status icons
  - Green means your device is protected.
  - Yellow means there is a safety recommendation for you to review.
  - Red means something needs your immediate attention.

## Virus and Threat Protection

- In Settings
- Current Threats
  - Scanning options
    - Quick scan: Checks folders in your system where threats are commonly found.
    - Full scan: Checks all files and running programs on your hard disk. This scan could take longer than one hour.
    - Custom scan: Choose which files and locations you want to check.
  - Threat History
    - Last scan: Windows Defender Antivirus automatically scans your device for viruses and other threats to help keep it safe.
    - Quarantined threats: Quarantined threats have been isolated and prevented from running on your device. They will be periodically removed.
    - Allowed threats: Allowed threats are items identified as threats, which you allowed to run on your device. 
- Virus and Protection settings
  - Settings
    - Real-time protection: Locates and stops malware from installing or running on your device.
    - Cloud-delivered protection: Provides increased and faster protection with access to the latest protection data in the cloud.
    - Automatic sample submission: Send sample files to Microsoft to help protect you and others from potential threats
    - Controlled folder access: Protect files, folders, and memory areas on your device from unauthorized changes by unfriendly applications.
    - Exclusions: Windows Defender Antivirus won't scan items that you've excluded.
    - Notifications: Windows Defender Antivirus will send notifications with critical information about the health and security of your device. 
- Ransomware Protection
  - Controlled folder access: Ransomware protection requires this feature to be enabled, which in turn requires Real-time protection to be enabled.

## Firewall and Network Protection

- Launched with `WF.msc` command 
- Firewalls control network traffic flow
- Windows has three firewall profiles
  - Domain: Applies to networks where the host system can authenticate to a domain controller. 
  - Private: User-assigned profile and is used to designate private or home networks.
  - Public: Default profile. Used to designate public networks such as Wi-Fi hotspots at coffee shops, airports, and other locations.

## App and Browser Control

- Microsoft Defender SmartScreen
  - Microsoft Defender SmartScreen protects against phishing or malware websites and applications, and the downloading of potentially malicious files
  - Docs can be found [here](https://feedback.smartscreen.microsoft.com/smartscreenfaq.aspx)

## Device Security

- Core isolation
  - Memory integrity: Prevents attacks from inserting malicious code into high security process
- Security Processor Details
  - Trusted Platform Module (TPM)
    - Hardware based security functions
    - 
## Bitlocker

- BitLocker Drive Encryption is a data protection feature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers
- Works best on devices with TPM installed
- Docs can be found [here](https://learn.microsoft.com/en-us/windows/security/operating-system-security/data-protection/bitlocker/)

## Volume Shadow Copy Service

- Coordinates the required actions to create a consistent shadow copy (also known as a snapshot or a point-in-time copy) of the data that is to be backed up
- Stored in System Volume Information Folder
- If enabled, you can complete the following tasks
  - Create a restore point
  - Perform system restore
  - Configure restore settings
  - Delete restore points