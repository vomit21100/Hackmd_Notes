## NMAP
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Shenzi]
└─$ nmap -p- -sCV 192.168.231.55 
Starting Nmap 7.95 ( https://nmap.org ) at 2026-03-11 11:06 EDT
Nmap scan report for 192.168.231.55
Host is up (0.061s latency).
Not shown: 65520 closed tcp ports (reset)
PORT      STATE SERVICE       VERSION
21/tcp    open  ftp           FileZilla ftpd 0.9.41 beta
80/tcp    open  http          Apache httpd 2.4.43 ((Win64) OpenSSL/1.1.1g PHP/7.4.6)
|_http-server-header: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.4.6
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
443/tcp   open  ssl/http      Apache httpd 2.4.43 ((Win64) OpenSSL/1.1.1g PHP/7.4.6)
| tls-alpn: 
|_  http/1.1
|_http-server-header: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.4.6
| ssl-cert: Subject: commonName=localhost
| Not valid before: 2009-11-10T23:48:47
|_Not valid after:  2019-11-08T23:48:47
| http-title: Welcome to XAMPP
|_Requested resource was https://192.168.231.55/dashboard/
|_ssl-date: TLS randomness does not represent time
445/tcp   open  microsoft-ds?
3306/tcp  open  mysql         MariaDB 10.3.24 or later (unauthorized)
5040/tcp  open  unknown
7680/tcp  open  pando-pub?
49664/tcp open  msrpc         Microsoft Windows RPC
49665/tcp open  msrpc         Microsoft Windows RPC
49666/tcp open  msrpc         Microsoft Windows RPC
49667/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
49669/tcp open  msrpc         Microsoft Windows RPC
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2026-03-11T15:11:03
|_  start_date: N/A

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 256.99 seconds
```

## 21 FTP
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Shenzi]
└─$ nxc ftp 192.168.231.55 -u anonymous -p anonymous
FTP         192.168.231.55  21     192.168.231.55   [-] anonymous:anonymous (Response:530 Login or password incorrect!)
```

## 135 SMB
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Shenzi]
└─$ nxc smb 192.168.231.55 -u anonymous -p anonymous
SMB         192.168.231.55  445    SHENZI           [*] Windows 10 / Server 2019 Build 19041 x64 (name:SHENZI) (domain:shenzi) (signing:False) (SMBv1:None)
SMB         192.168.231.55  445    SHENZI           [+] shenzi\anonymous:anonymous (Guest)
                                                                                                                                                                                                                                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Desktop/Pen200/Shenzi]
└─$ nxc smb 192.168.231.55 -u anonymous -p anonymous --shares
SMB         192.168.231.55  445    SHENZI           [*] Windows 10 / Server 2019 Build 19041 x64 (name:SHENZI) (domain:shenzi) (signing:False) (SMBv1:None)
SMB         192.168.231.55  445    SHENZI           [+] shenzi\anonymous:anonymous (Guest)
SMB         192.168.231.55  445    SHENZI           [*] Enumerated shares
SMB         192.168.231.55  445    SHENZI           Share           Permissions     Remark
SMB         192.168.231.55  445    SHENZI           -----           -----------     ------
SMB         192.168.231.55  445    SHENZI           IPC$            READ            Remote IPC
SMB         192.168.231.55  445    SHENZI           Shenzi          READ
```
```
smbclient //192.168.231.55/Shenzi --user anonymous%anonymous
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Thu May 28 11:45:09 2020
  ..                                  D        0  Thu May 28 11:45:09 2020
  passwords.txt                       A      894  Thu May 28 11:45:09 2020
  readme_en.txt                       A     7367  Thu May 28 11:45:09 2020
  sess_klk75u2q4rpgfjs3785h6hpipp      A     3879  Thu May 28 11:45:09 2020
  why.tmp                             A      213  Thu May 28 11:45:09 2020
  xampp-control.ini                   A      178  Thu May 28 11:45:09 2020

                12941823 blocks of size 4096. 6492013 blocks available
smb: \> mask ""
smb: \> recurse ON
smb: \> prompt OFF
smb: \> mget *
getting file \passwords.txt of size 894 as passwords.txt (3.5 KiloBytes/sec) (average 3.5 KiloBytes/sec)
getting file \readme_en.txt of size 7367 as readme_en.txt (29.0 KiloBytes/sec) (average 16.2 KiloBytes/sec)
getting file \sess_klk75u2q4rpgfjs3785h6hpipp of size 3879 as sess_klk75u2q4rpgfjs3785h6hpipp (15.2 KiloBytes/sec) (average 15.9 KiloBytes/sec)
getting file \why.tmp of size 213 as why.tmp (0.8 KiloBytes/sec) (average 12.1 KiloBytes/sec)
getting file \xampp-control.ini of size 178 as xampp-control.ini (0.7 KiloBytes/sec) (average 9.9 KiloBytes/sec)
smb: \> 
```
```passwords.txt
### XAMPP Default Passwords ###

1) MySQL (phpMyAdmin):

   User: root
   Password:
   (means no password!)

2) FileZilla FTP:

   [ You have to create a new user on the FileZilla Interface ] 

3) Mercury (not in the USB & lite version): 

   Postmaster: Postmaster (postmaster@localhost)
   Administrator: Admin (admin@localhost)

   User: newuser  
   Password: wampp 

4) WEBDAV: 

   User: xampp-dav-unsecure
   Password: ppmax2011
   Attention: WEBDAV is not active since XAMPP Version 1.7.4.
   For activation please comment out the httpd-dav.conf and
   following modules in the httpd.conf
   
   LoadModule dav_module modules/mod_dav.so
   LoadModule dav_fs_module modules/mod_dav_fs.so  
   
   Please do not forget to refresh the WEBDAV authentification (users and passwords).     

5) WordPress:

   User: admin
   Password: FeltHeadwallWight357
```

## 80 HTTP
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Shenzi]
└─$ dirsearch -u http://192.168.231.55  
/usr/lib/python3/dist-packages/dirsearch/dirsearch.py:23: DeprecationWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html
  from pkg_resources import DistributionNotFound, VersionConflict

  _|. _ _  _  _  _ _|_    v0.4.3                                                                                                                                                                                                                                                                                                                                                                                                                           
 (_||| _) (/_(_|| (_| )                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                                                                                                                                           
Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 25 | Wordlist size: 11460

Output File: /home/kali/Desktop/Pen200/Shenzi/reports/http_192.168.231.55/_26-03-11_11-18-39.txt

Target: http://192.168.231.55/

[11:18:39] Starting:                                                                                                                                                                                                                                                                                                                                                                                                                                       
[11:18:40] 403 -    1KB - /%3f/                                             
[11:18:40] 403 -    1KB - /%C0%AE%C0%AE%C0%AF                               
[11:18:40] 403 -    1KB - /%ff                                              
[11:18:42] 403 -    1KB - /.ht_wsr.txt                                      
[11:18:42] 403 -    1KB - /.htaccess.bak1                                   
[11:18:42] 403 -    1KB - /.htaccess.orig                                   
[11:18:42] 403 -    1KB - /.htaccess.sample                                 
[11:18:42] 403 -    1KB - /.htaccess.save
[11:18:42] 403 -    1KB - /.htaccess_orig                                   
[11:18:42] 403 -    1KB - /.htaccess_extra                                  
[11:18:42] 403 -    1KB - /.htaccess_sc
[11:18:42] 403 -    1KB - /.htaccessBAK
[11:18:42] 403 -    1KB - /.htaccessOLD
[11:18:42] 403 -    1KB - /.htaccessOLD2                                    
[11:18:42] 403 -    1KB - /.htm                                             
[11:18:42] 403 -    1KB - /.html
[11:18:42] 403 -    1KB - /.htpasswd_test                                   
[11:18:42] 403 -    1KB - /.htpasswds
[11:18:42] 403 -    1KB - /.httr-oauth
[11:18:53] 403 -    1KB - /cgi-bin/                                         
[11:18:53] 500 -    1KB - /cgi-bin/printenv.pl                              
[11:18:55] 301 -  344B  - /dashboard  ->  http://192.168.231.55/dashboard/  
[11:18:55] 200 -    7KB - /dashboard/                                       
[11:18:55] 200 -    6KB - /dashboard/howto.html
[11:18:55] 200 -   31KB - /dashboard/faq.html                               
[11:18:55] 200 -   78KB - /dashboard/phpinfo.php                            
[11:18:56] 403 -    1KB - /error/                                           
[11:18:57] 200 -   30KB - /favicon.ico                                      
[11:19:02] 503 -    1KB - /examples/                                        
[11:19:02] 503 -    1KB - /examples                                         
[11:19:02] 503 -    1KB - /examples/jsp/%252e%252e/%252e%252e/manager/html/
[11:19:02] 503 -    1KB - /examples/servlet/SnoopServlet                    
[11:19:02] 503 -    1KB - /examples/jsp/snp/snoop.jsp
[11:19:02] 503 -    1KB - /examples/jsp/index.html                          
[11:19:02] 503 -    1KB - /examples/servlets/index.html                     
[11:19:02] 503 -    1KB - /examples/servlets/servlet/RequestHeaderExample
[11:19:02] 503 -    1KB - /examples/servlets/servlet/CookieExample
[11:19:02] 503 -    1KB - /examples/websocket/index.xhtml
[11:19:03] 301 -  338B  - /img  ->  http://192.168.231.55/img/              
[11:19:03] 403 -    1KB - /index.php::$DATA                                 
[11:19:08] 403 -    1KB - /phpmyadmin                                       
[11:19:09] 403 -    1KB - /phpmyadmin/                                      
[11:19:09] 403 -    1KB - /phpmyadmin/ChangeLog
[11:19:09] 403 -    1KB - /phpmyadmin/doc/html/index.html
[11:19:09] 403 -    1KB - /phpmyadmin/docs/html/index.html
[11:19:09] 403 -    1KB - /phpmyadmin/index.php                             
[11:19:09] 403 -    1KB - /phpmyadmin/phpmyadmin/index.php
[11:19:09] 403 -    1KB - /phpmyadmin/README                                
[11:19:09] 403 -    1KB - /phpmyadmin/scripts/setup.php                     
[11:19:11] 403 -    1KB - /server-info                                      
[11:19:11] 403 -    1KB - /server-status
[11:19:11] 403 -    1KB - /server-status/
[11:19:14] 403 -    1KB - /Trace.axd::$DATA                                 
[11:19:16] 403 -    1KB - /web.config::$DATA                                
[11:19:16] 403 -    1KB - /webalizer                                        
[11:19:16] 403 -    1KB - /webalizer/                                       
[11:19:16] 200 -  780B  - /Webalizer/
[11:19:17] 200 -  772B  - /xampp/                                           
                                                                             
Task Completed
```
![image](https://hackmd.io/_uploads/BJbzt-15We.png)
![image](https://hackmd.io/_uploads/rkZXF-Jqbx.png)
![image](https://hackmd.io/_uploads/HklPtbyqbl.png)


## 3306 MYSQL
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Shenzi]
└─$ mysql -h 192.168.231.55 -u root -p 
Enter password: 
ERROR 2002 (HY000): Received error packet before completion of TLS handshake. The authenticity of the following error cannot be verified: 1130 - Host '192.168.45.221' is not allowed to connect to this MariaDB server
```

## 80 HTTP HIDDEN FOLDER

![image](https://hackmd.io/_uploads/SkdTzzkq-e.png)
```
┌──(kali㉿kali)-[~/Desktop/Pen200/Shenzi]
└─$ wpscan --url http://192.168.231.55/shenzi
_______________________________________________________________
         __          _______   _____
         \ \        / /  __ \ / ____|
          \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
           \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
            \  /\  /  | |     ____) | (__| (_| | | | |
             \/  \/   |_|    |_____/ \___|\__,_|_| |_|

         WordPress Security Scanner by the WPScan Team
                         Version 3.8.28
                               
       @_WPScan_, @ethicalhack3r, @erwan_lr, @firefart
_______________________________________________________________

[i] Updating the Database ...
[i] Update completed.

[+] URL: http://192.168.231.55/shenzi/ [192.168.231.55]
[+] Started: Wed Mar 11 12:06:44 2026

Interesting Finding(s):

[+] Headers
 | Interesting Entries:
 |  - Server: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.4.6
 |  - X-Powered-By: PHP/7.4.6
 | Found By: Headers (Passive Detection)
 | Confidence: 100%

[+] XML-RPC seems to be enabled: http://192.168.231.55/shenzi/xmlrpc.php
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 100%
 | References:
 |  - http://codex.wordpress.org/XML-RPC_Pingback_API
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_ghost_scanner/
 |  - https://www.rapid7.com/db/modules/auxiliary/dos/http/wordpress_xmlrpc_dos/
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_xmlrpc_login/
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_pingback_access/

[+] WordPress readme found: http://192.168.231.55/shenzi/readme.html
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 100%

[+] Upload directory has listing enabled: http://192.168.231.55/shenzi/wp-content/uploads/
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 100%

[+] The external WP-Cron seems to be enabled: http://192.168.231.55/shenzi/wp-cron.php
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 60%
 | References:
 |  - https://www.iplocation.net/defend-wordpress-from-ddos
 |  - https://github.com/wpscanteam/wpscan/issues/1299

[+] WordPress version 5.4.1 identified (Insecure, released on 2020-04-29).
 | Found By: Rss Generator (Passive Detection)
 |  - http://192.168.231.55/shenzi/feed/, <generator>https://wordpress.org/?v=5.4.1</generator>
 |  - http://192.168.231.55/shenzi/comments/feed/, <generator>https://wordpress.org/?v=5.4.1</generator>

[+] WordPress theme in use: twentytwenty
 | Location: http://192.168.231.55/shenzi/wp-content/themes/twentytwenty/
 | Last Updated: 2025-12-03T00:00:00.000Z
 | Readme: http://192.168.231.55/shenzi/wp-content/themes/twentytwenty/readme.txt
 | [!] The version is out of date, the latest version is 3.0
 | Style URL: http://192.168.231.55/shenzi/wp-content/themes/twentytwenty/style.css?ver=1.2
 | Style Name: Twenty Twenty
 | Style URI: https://wordpress.org/themes/twentytwenty/
 | Description: Our default theme for 2020 is designed to take full advantage of the flexibility of the block editor...
 | Author: the WordPress team
 | Author URI: https://wordpress.org/
 |
 | Found By: Css Style In Homepage (Passive Detection)
 | Confirmed By: Css Style In 404 Page (Passive Detection)
 |
 | Version: 1.2 (80% confidence)
 | Found By: Style (Passive Detection)
 |  - http://192.168.231.55/shenzi/wp-content/themes/twentytwenty/style.css?ver=1.2, Match: 'Version: 1.2'

[+] Enumerating All Plugins (via Passive Methods)

[i] No plugins Found.

[+] Enumerating Config Backups (via Passive and Aggressive Methods)
 Checking Config Backups - Time: 00:00:08 <=============================================================================================================================================> (137 / 137) 100.00% Time: 00:00:08

[i] No Config Backups Found.

[!] No WPScan API Token given, as a result vulnerability data has not been output.
[!] You can get a free API token with 25 daily requests by registering at https://wpscan.com/register

[+] Finished: Wed Mar 11 12:07:01 2026
[+] Requests Done: 185
[+] Cached Requests: 6
[+] Data Sent: 47.894 KB
[+] Data Received: 23.237 MB
[+] Memory used: 277.312 MB
[+] Elapsed time: 00:00:17

```
![image](https://hackmd.io/_uploads/S1xdGrlqbx.png)
![image](https://hackmd.io/_uploads/SkynzHe9Zl.png)
![image](https://hackmd.io/_uploads/S1w0fBl5Wl.png)
![image](https://hackmd.io/_uploads/BkPpzBx5Zx.png)
![image](https://hackmd.io/_uploads/rk9XXBeqZe.png)

## Privilege Escalation
![image](https://hackmd.io/_uploads/SJVseUe9Zx.png)
![image](https://hackmd.io/_uploads/HyUnlLxc-x.png)
![image](https://hackmd.io/_uploads/BkBagIgcZx.png)
