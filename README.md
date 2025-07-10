# windows-troublshooting-guide
A practical reference for diagnosing and fixing common Windows issues using built-in tools, command-line utilities, and real-world fixes. Great for IT techs, field support, helpdesk agents, and self-taught troubleshooters.


# 🧰 Windows Troubleshooting Guide



## Sections

- [Boot Issues](boot-issues.md)
- [Network Issues](network-issues.md)
- [User Profile Issues](user-profiles.md)
- [File Permission Issues](file-permissions.md)
- [Command Line Cheatsheet](command-line-cheatsheet.md)
- [Common Tools](tools/README.md)


## How to Use This Guide

- Browse for the type of issue you're facing
- Use copy-pasteable commands where needed
- Most solutions require admin rights



## Top 10 Boot Commands
```sh
bootrec /fixmbr            # Fixes Master Boot Record
bootrec /fixboot           # Writes a new boot sector
bootrec /scanos            # Scans for Windows installations
bootrec /rebuildbcd        # Rebuilds the Boot Configuration Data
bcdedit /set {default} safeboot minimal  # Boot into Safe Mode
sfc /scannow               # System File Checker
chkdsk C: /f /r            # Check disk for errors and fix them
DISM /Online /Cleanup-Image /RestoreHealth  # Repairs system image
bcdedit /export C:\BCD_Backup  # Backup current BCD settings
shutdown /r /o             # Restart into advanced boot options
```

---

## Top 10 Network Commands
```sh
ipconfig /all             # Displays full IP configuration
ipconfig /release         # Releases current IP address
ipconfig /renew           # Renews the IP address
ipconfig /flushdns        # Clears DNS cache
ping 8.8.8.8              # Tests internet connectivity
tracert google.com        # Traces route to destination
netsh int ip reset        # Resets TCP/IP stack
netsh winsock reset       # Resets Winsock catalog
nslookup example.com      # DNS resolution check
arp -a                    # View ARP cache
```

---

## Top 10 User Profile Commands
```sh
whoami                    # Displays current user info
net user                  # Lists all user accounts
net user username /active:yes  # Enable user account
rundll32.exe userinit.dll,ProcessIdleTasks  # Run user logon scripts
control userpasswords2    # Opens legacy user management
wmic useraccount get name,sid  # View user SIDs
regedit                   # Open Registry Editor (to inspect profiles)
del /F /Q "C:\Users\TEMP" # Remove temp profile folders
shutdown /l               # Log off user
GPResult /H report.html   # Generate Group Policy report
```

---

## Top 10 File Permission Commands
```sh
icacls C:\MyFolder        # View permissions for folder
icacls C:\MyFolder /grant username:F  # Grant full access
takeown /f C:\MyFolder /r /d y  # Take ownership recursively
cacls C:\MyFolder /e /p username:F  # Edit ACL (legacy)
dir /Q                    # Show file owner
attrib +r myfile.txt      # Set file to read-only
attrib -h -s myfile.txt   # Remove hidden/system attributes
fsutil file queryallocranges myfile.txt  # Inspect file allocation
secedit /export /cfg secpol.cfg  # Export local security policy
powershell Get-Acl        # View permissions via PowerShell
```

---

## Top 10 Command Line Cheats
```sh
systeminfo                # View system summary
hostname                  # Show computer name
tasklist                  # List running processes
taskkill /IM notepad.exe /F  # Kill a process by name
shutdown /s /t 0          # Immediate shutdown
wmic os get caption       # Show OS version
powercfg /batteryreport   # Battery health (laptops)
set                       # View environment variables
echo %USERNAME%           # Show current user
cls                       # Clear command prompt screen
```

---

## Top 10 Common Tools
```txt
1. Event Viewer – Logs system/application/security events
2. Task Manager – Monitor processes and performance
3. Device Manager – Manage drivers and hardware
4. Services.msc – View and control background services
5. msconfig – Configure system startup
6. Disk Management – Manage partitions and volumes
7. Group Policy Editor – Manage system and user policies
8. System Restore – Roll back to previous state
9. Windows Memory Diagnostic – Check for RAM issues
10. Reliability Monitor – Visual history of system stability
```

🔀 This project has multiple branches. See the [`dev`](https://github.com/gervaseburkett/boot-issues-/blob/main/README.md) branch for the latest features and testing updates.

