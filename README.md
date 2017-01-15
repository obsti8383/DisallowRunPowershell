# DisallowRunPowershell
Some material for preventing simple malicious powershell attacks - uses DisallowRun Registry Keys.

Disables PowerShell execution via Windows Explorer.

**cmd.exe or other programs can still be used (and misused) to start powershell.exe**

## Test File
Example_LNK.zip: Contains a .lnk file that was created with a modified .vbs from https://github.com/xillwillx/tricky.lnk. It looks like a txt file, opens Notepad.exe and then downloads Procexp.exe from sysinternals.live.com and starts it.

## Enable protection
To defend against such an attack (and direct execution of .ps1 files) you can add the following .reg file:  	enable_disallowrun_powershell.reg and _restart Windows_.

##Disable protection
To disable it use: disable_disallowrun_powershell.reg and _restart Windows_.

##Additional information
Registry keys are created below: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer

So this only protects the current user. You have to enable it for all users that should be protected.

##Used sources
* https://technet.microsoft.com/en-us/library/cc960900.aspx

* http://fipso100.blogspot.de/2016/06/use-windows-lnk-file-to-execute.html

* http://www.howtogeek.com/howto/8739/restrict-users-to-run-only-specified-programs-in-windows-7/
