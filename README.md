#Windows Security Controls
There are different things in Windows that could prevent you from enumerating the system, run executables or even detect your activities. You should read the following page and enumerate all these defenses mechanisms before starting the privilege escalation enumeration:

#Windows Security Controls
System Info
Version info enumeration
Check if the Windows version has any known vulnerability (check also the patches applied).

Copy
systeminfo
systeminfo | findstr /B /C:"OS Name" /C:"OS Version" #Get only that information
wmic qfe get Caption,Description,HotFixID,InstalledOn #Patches
wmic os get osarchitecture || echo %PROCESSOR_ARCHITECTURE% #Get system architecture
Copy
[System.Environment]::OSVersion.Version #Current OS version
Get-WmiObject -query 'select * from win32_quickfixengineering' | foreach {$_.hotfixid} #List all patches
Get-Hotfix -description "Security update" #List only "Security Update" patches
