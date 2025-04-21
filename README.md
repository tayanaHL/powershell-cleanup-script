🧼 PowerShell Cleanup Script
🎯 Description
This project automates a basic system cleanup using PowerShell. The script clears user temporary files, the Windows update cache, and empties the Recycle Bin. It simulates common Tier 1/Tier 2 maintenance tasks used to resolve slow performance and free up disk space.

This was built and tested in a Windows 10 virtual machine as part of my hands-on IT home lab environment.

🛠 Tools Used
PowerShell

VirtualBox (Windows 10 VM)

$env:TEMP, Remove-Item, Clear-RecycleBin

📋 What the Script Does (Line-by-Line Breakdown)
Write-Output "Starting system cleanup..."
➡️ Displays a message indicating that the script has started.

Remove-Item -Path "$env:TEMP\*" -Recurse -Force -ErrorAction SilentlyContinue
🧹 Clears temporary files stored in the user’s profile. These are leftover files from installs, browser sessions, app usage, etc. Removing them helps free up space and prevent slowdowns.

Remove-Item -Path "C:\Windows\SoftwareDistribution\Download\*" -Recurse -Force -ErrorAction SilentlyContinue
🧼 Deletes files from the Windows Update cache. This can help resolve update failures caused by corrupted or stuck files.

Clear-RecycleBin -Force -ErrorAction SilentlyContinue
🗑 Empties the Recycle Bin silently across all drives. Useful for freeing up additional space and tidying up the system.

Write-Output "Cleanup complete!"
✅ Confirms that the script has finished running successfully.

🧠 Key Learnings
Wrote and executed a .ps1 PowerShell script for routine system maintenance

Practiced adjusting PowerShell’s execution policy to allow script running

Learned how to use environment variables like $env:TEMP

Gained awareness of system folders that store unnecessary cached data

Simulated a lightweight IT automation workflow for Tier 1/Tier 2 support

🔐 How to Run This Script
Run PowerShell as Administrator

Allow script execution:
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

Navigate to script location:
cd $env:USERPROFILE\Desktop

Run the script:
.\cleanup.ps1

You’ll see:
Starting system cleanup...
Cleanup complete!


✅ Outcome
Successfully created and ran a PowerShell script to perform basic cleanup and maintenance tasks. This project simulates real-world responsibilities in entry-level IT roles and forms the foundation for future automation scripting.

🔗 Related Skills
PowerShell Scripting

Windows OS Maintenance

Temp File Management

Windows Update Troubleshooting

IT Support & Help Desk Tasks

