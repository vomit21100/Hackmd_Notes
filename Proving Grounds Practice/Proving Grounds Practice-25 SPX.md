## NMAP
```
PORT   STATE SERVICE REASON         VERSION
22/tcp open  ssh     syn-ack ttl 61 OpenSSH 8.9p1 Ubuntu 3ubuntu0.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 b9:bc:8f:01:3f:85:5d:f9:5c:d9:fb:b6:15:a0:1e:74 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBBYESg2KmNLhFh1KJaN2UFCVAEv6MWr58pqp2fIpCSBEK2wDJ5ap2XVBVGLk9Po4eKBbqTo96yttfVUvXWXoN3M=
|   256 53:d9:7f:3d:22:8a:fd:57:98:fe:6b:1a:4c:ac:79:67 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIBdIs4PWZ8yY2OQ6Jlk84Ihd5+15Nb3l0qvpf1ls3wfa
80/tcp open  http    syn-ack ttl 61 Apache httpd 2.4.52 ((Ubuntu))
|_http-title: Tiny File Manager
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.52 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

## 80 HTTP

![image](_assets/S1Q4O8tobg.png)

![image](_assets/HJDD_LYibx.png)

![image](_assets/ryQuuUKjbg.png)

![image](_assets/H1vhuLtoZx.png)

![image](_assets/H1VJYUKi-l.png)

* exploit-db

  ![image](_assets/BkkmYUtsbx.png)

  ![image](_assets/H1IMF8YsZe.png)

* search default password
found default password in offical repository
https://github.com/prasathmani/tinyfilemanager/blob/master/tinyfilemanager.php

  ![image](_assets/SJUAcUYsbx.png)

  ![image](_assets/S1-Nj8tj-x.png)

* findind password

  ![image](_assets/SkjY7PFj-x.png)

  ![image](_assets/BJC7SPKsWx.png)

* CVE-2024-42007
https://github.com/strikoder/CVE-2024-42007-POC

  ![image](_assets/ryLp8PYiZl.png)

  ![image](_assets/B1G0Lwtobg.png)

  ![image](_assets/rJlcFvtjWl.png)

  ![image](_assets/H1RctwKi-g.png)

  ![image](_assets/rkOJzdYs-g.png)

`admin:lowprofile`

  ![image](_assets/HJBQzOFjWx.png)

  ![image](_assets/SJswzutibl.png)

  ![image](_assets/r1AdMdtjZg.png)

  ![image](_assets/Bka5MuYiWg.png)

  ![image](_assets/H1t0N_Ksbe.png)

## Privilege Escalation
1. SUID

   ![image](_assets/ryJ0xttsZg.png)

2. Capabilities

   ![image](_assets/SypkbFtsbx.png)

3. Another user
'profiler:lowprofile'

   ![image](_assets/SJkvgttjWg.png)

   ![image](_assets/SyP9ltYsZg.png)

4. sudo -l

   ![image](_assets/HyN7bFYjWg.png)

   ![image](_assets/SkrzGYKi-e.png)

   ![image](_assets/HkQLftYi-l.png)

   ![image](_assets/Hkhizttsbe.png)

   ![/tmp/sh](_assets/H1grNKKsZe.png)

   ![image](_assets/S1h8EFYoWg.png)
