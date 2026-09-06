## NMAP
```

```

## 445 SMB
```
┌──(kali㉿kali)-[~]
└─$ nxc smb 192.168.216.180 -u anonymous -p anonymous
SMB         192.168.216.180 445    MIKE-PC          [*] Windows 10 / Server 2019 Build 19041 x64 (name:MIKE-PC) (domain:Mike-PC) (signing:False) (SMBv1:None)
SMB         192.168.216.180 445    MIKE-PC          [-] Mike-PC\anonymous:anonymous STATUS_LOGON_FAILURE
```

## 80 HTTP
1. default page
`http://192.168.216.180/` -> `http://192.168.216.180/index.html`
![image](https://hackmd.io/_uploads/Bkjn6aDcWx.png)

2. dirsearch
```
┌──(kali㉿kali)-[~]
└─$ dirsearch -u http://192.168.216.180
/usr/lib/python3/dist-packages/dirsearch/dirsearch.py:23: DeprecationWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html
  from pkg_resources import DistributionNotFound, VersionConflict

  _|. _ _  _  _  _ _|_    v0.4.3
 (_||| _) (/_(_|| (_| )

Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 25 | Wordlist size: 11460

Output File: /home/kali/reports/http_192.168.216.180/_26-03-18_02-55-34.txt

Target: http://192.168.216.180/

[02:55:34] Starting: 
[02:55:35] 403 -    1KB - /%3f/                                             
[02:55:35] 403 -    1KB - /%C0%AE%C0%AE%C0%AF                               
[02:55:35] 403 -    1KB - /%ff                                              
[02:55:37] 403 -    1KB - /.ht_wsr.txt                                      
[02:55:38] 403 -    1KB - /.htaccess.bak1                                   
[02:55:38] 403 -    1KB - /.htaccess_extra
[02:55:38] 403 -    1KB - /.htm                                             
[02:55:38] 403 -    1KB - /.htaccess.save
[02:55:38] 403 -    1KB - /.htaccess.sample                                 
[02:55:38] 403 -    1KB - /.htaccessOLD2                                    
[02:55:38] 403 -    1KB - /.htaccess_orig
[02:55:38] 403 -    1KB - /.html
[02:55:38] 403 -    1KB - /.htaccessOLD                                     
[02:55:38] 403 -    1KB - /.htaccessBAK                                     
[02:55:38] 403 -    1KB - /.htaccess.orig                                   
[02:55:38] 403 -    1KB - /.htaccess_sc                                     
[02:55:38] 403 -    1KB - /.htpasswd_test
[02:55:38] 403 -    1KB - /.htpasswds
[02:55:38] 403 -    1KB - /.httr-oauth                                      
[02:55:49] 301 -  344B  - /assets  ->  http://192.168.216.180/assets/       
[02:55:49] 200 -    2KB - /assets/                                          
[02:55:50] 301 -  342B  - /blog  ->  http://192.168.216.180/blog/           
[02:55:51] 403 -    1KB - /cgi-bin/                                         
[02:55:51] 404 -    3KB - /blog/wp-login                                    
[02:55:51] 404 -    3KB - /blog/wp-content/backups/
[02:55:51] 404 -    3KB - /blog/phpmyadmin/
[02:55:51] 404 -    3KB - /blog/error_log
[02:55:51] 404 -    3KB - /blog/wp-login.php
[02:55:51] 200 -    4KB - /blog/
[02:55:51] 404 -    3KB - /blog/wp-content/backup-db/
[02:55:51] 404 -    3KB - /blog/fckeditor
[02:55:51] 200 -    2KB - /cgi-bin/printenv.pl                              
[02:55:55] 403 -    1KB - /error/                                           
[02:55:57] 503 -    1KB - /examples/jsp/snp/snoop.jsp                       
[02:55:57] 503 -    1KB - /examples/servlet/SnoopServlet
[02:55:57] 503 -    1KB - /examples/                                        
[02:55:57] 503 -    1KB - /examples/jsp/%252e%252e/%252e%252e/manager/html/
[02:55:57] 503 -    1KB - /examples
[02:55:57] 503 -    1KB - /examples/jsp/index.html                          
[02:55:57] 503 -    1KB - /examples/websocket/index.xhtml                   
[02:55:57] 503 -    1KB - /examples/servlets/index.html
[02:55:57] 503 -    1KB - /examples/servlets/servlet/RequestHeaderExample
[02:55:57] 503 -    1KB - /examples/servlets/servlet/CookieExample
[02:55:59] 403 -    1KB - /index.php::$DATA                                 
[02:56:08] 403 -    1KB - /phpmyadmin                                       
[02:56:09] 403 -    1KB - /phpmyadmin/                                      
[02:56:09] 403 -    1KB - /phpmyadmin/docs/html/index.html                  
[02:56:09] 403 -    1KB - /phpmyadmin/phpmyadmin/index.php                  
[02:56:09] 403 -    1KB - /phpmyadmin/README
[02:56:09] 403 -    1KB - /phpmyadmin/doc/html/index.html                   
[02:56:09] 403 -    1KB - /phpmyadmin/ChangeLog
[02:56:09] 403 -    1KB - /phpmyadmin/scripts/setup.php
[02:56:09] 403 -    1KB - /phpmyadmin/index.php
[02:56:11] 403 -    1KB - /server-info                                      
[02:56:11] 403 -    1KB - /server-status                                    
[02:56:11] 403 -    1KB - /server-status/                                   
[02:56:15] 403 -    1KB - /Trace.axd::$DATA                                 
[02:56:16] 403 -    1KB - /web.config::$DATA                                
[02:56:16] 403 -    1KB - /webalizer                                        
[02:56:16] 403 -    1KB - /webalizer/
```

3. /blog
`http://192.168.216.180/blog/`
found CMS nmae
![image](https://hackmd.io/_uploads/SyRj0TwcZl.png)

4. CVE search
`CVE-2018-9037` & `CVE-2018-6383`
Found 2 cve but both describe same thing
![image](https://hackmd.io/_uploads/S16A0Tw5Zg.png)
![image](https://hackmd.io/_uploads/rJxrk0v9-x.png)

5. add hosts
```
┌──(kali㉿kali)-[~]
└─$ cat /etc/hosts                                                   
127.0.0.1       localhost
127.0.1.1       kali
::1             localhost ip6-localhost ip6-loopback
ff02::1         ip6-allnodes
ff02::2         ip6-allrouters

192.168.216.180 monster.pg    <-   added
```

6. walk around in /blog
Two interesting page found
- `https://monster.pg/blog/users`
![image](https://hackmd.io/_uploads/HkgiAQ0v5-e.png)

- `https://monster.pg/blog/admin/`
![image](https://hackmd.io/_uploads/rJhxVCDc-g.png)

7. test weak password
![image](https://hackmd.io/_uploads/HyRQD_Wo-e.png)
![image](https://hackmd.io/_uploads/rku2Dd-jWx.png)

8. upload function
無法上傳普通png檔案，推測目標拒絕任何的檔案上傳
![image](https://hackmd.io/_uploads/r1W6udWoZg.png)
![image](https://hackmd.io/_uploads/S1YR__WjZe.png)
`D4Zi17gXkAE8464.png`
![D4Zi17gXkAE8464.png](https://hackmd.io/_uploads/SJgJq_-s-g.png)
![image](https://hackmd.io/_uploads/ByRlKO-ibx.png)

9. Backup function
可以點擊按鈕進行備份，備份壓縮檔內為`C:/xampp/htdocs/blog`，在裡面一個檔案找到hash，但無法使用
![image](https://hackmd.io/_uploads/HyUmqOWo-g.png)
![image](https://hackmd.io/_uploads/Sy2FiOWjWx.png)
![image](https://hackmd.io/_uploads/HkchNtZi-l.png)
![image](https://hackmd.io/_uploads/ByzfBYbsbe.png)
![image](https://hackmd.io/_uploads/HJ-UrYZiZg.png)
![image](https://hackmd.io/_uploads/HyywrFWo-g.png)

10. Exploit-DB
![image](https://hackmd.io/_uploads/H1FzIK-oZl.png)
![image](https://hackmd.io/_uploads/rk8i4FWsZe.png)
![image](https://hackmd.io/_uploads/SJaCLY-iWg.png)

## Privilege Escalation
1. whoami /all
```
PS C:\xampp\htdocs\blog\public\themes\default> whoami /all

USER INFORMATION
----------------

User Name    SID                                           
============ ==============================================
mike-pc\mike S-1-5-21-2619112490-2635448554-1147358759-1002


GROUP INFORMATION
-----------------

Group Name                             Type             SID          Attributes                                        
====================================== ================ ============ ==================================================
Everyone                               Well-known group S-1-1-0      Mandatory group, Enabled by default, Enabled group
BUILTIN\Remote Desktop Users           Alias            S-1-5-32-555 Mandatory group, Enabled by default, Enabled group
BUILTIN\Users                          Alias            S-1-5-32-545 Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\INTERACTIVE               Well-known group S-1-5-4      Mandatory group, Enabled by default, Enabled group
CONSOLE LOGON                          Well-known group S-1-2-1      Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\Authenticated Users       Well-known group S-1-5-11     Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\This Organization         Well-known group S-1-5-15     Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\Local account             Well-known group S-1-5-113    Mandatory group, Enabled by default, Enabled group
LOCAL                                  Well-known group S-1-2-0      Mandatory group, Enabled by default, Enabled group
NT AUTHORITY\NTLM Authentication       Well-known group S-1-5-64-10  Mandatory group, Enabled by default, Enabled group
Mandatory Label\Medium Mandatory Level Label            S-1-16-8192                                                    


PRIVILEGES INFORMATION
----------------------

Privilege Name                Description                          State   
============================= ==================================== ========
SeShutdownPrivilege           Shut down the system                 Disabled
SeChangeNotifyPrivilege       Bypass traverse checking             Enabled 
SeUndockPrivilege             Remove computer from docking station Disabled
SeIncreaseWorkingSetPrivilege Increase a process working set       Disabled
SeTimeZonePrivilege           Change the time zone                 Disabled
```

2. backup files
https://simpleinfoseccom.wordpress.com/2018/05/27/monstra-cms-3-0-4-unauthenticated-user-credential-exposure/
double md5 password hash
![image](https://hackmd.io/_uploads/ByzfBYbsbe.png)
`C:\xampp\htdocs\blog\boot\defines.php`
![image](https://hackmd.io/_uploads/B1BAl5bo-x.png)
`C:\xampp\htdocs\blog\engine\Security.php`
![image](https://hackmd.io/_uploads/Bk_MbcZs-g.png)
![image](https://hackmd.io/_uploads/rylKW9WsWe.png)

    - hashcat
    `sudo hashcat -m 2600 pass /usr/share/wordlists/rockyou.txt -r md5rule --force`
    
    `md5rule`
    ```
    $Y $O $U $R $\x5F $S $A $L $T $\x5F $H $E $R $E
    ```
    ```
    Dictionary cache hit:
    * Filename..: /usr/share/wordlists/rockyou.txt
    * Passwords.: 14344385
    * Bytes.....: 139921507
    * Keyspace..: 14344385

    a2b4e80cd640aaa6e417febe095dcbfc:wazowskiYOUR_SALT_HERE
    844ffc2c7150b93c4133a6ff2e1a2dba:Mike14YOUR_SALT_HERE 
    ```

3. xampp
`C:\xampp\properties.ini`
![image](https://hackmd.io/_uploads/ryy_ScbsZg.png)
![image](https://hackmd.io/_uploads/rJF58c-oWl.png)
![image](https://hackmd.io/_uploads/Sk0XP5Zi-l.png)
![image](https://hackmd.io/_uploads/BkjZDqbsbx.png)
![image](https://hackmd.io/_uploads/S1czv5-oZx.png)

