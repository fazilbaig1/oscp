#System Info
Version info enumeration
Check if the Windows version has any known vulnerability (check also the patches applied).


#systeminfo

```systeminfo | findstr /B /C:"OS Name" /C:"OS Version" #Get only that information
wmic qfe get Caption,Description,HotFixID,InstalledOn #Patches
wmic os get osarchitecture || echo %PROCESSOR_ARCHITECTURE% #Get system architecture```

```[System.Environment]::OSVersion.Version #Current OS version
Get-WmiObject -query 'select * from win32_quickfixengineering' | foreach {$_.hotfixid} #List all patches
Get-Hotfix -description "Security update" #List only "Security Update" patches```
Version Exploits
This site is handy for searching out detailed information about Microsoft security vulnerabilities. This database has more than 4,700 security vulnerabilities, showing the massive attack surface that a Windows environment presents.

On the system

post/windows/gather/enum_patches

post/multi/recon/local_exploit_suggester

watson

winpeas (Winpeas has watson embedded)

Locally with system information

https://github.com/AonCyberLabs/Windows-Exploit-Suggester

https://github.com/bitsadmin/wesng

Github repos of exploits:

https://github.com/nomi-sec/PoC-in-GitHub

https://github.com/abatchy17/WindowsExploits

https://github.com/SecWiki/windows-kernel-exploits
