## NMAP
```
PORT     STATE SERVICE REASON         VERSION
22/tcp   open  ssh     syn-ack ttl 61 OpenSSH 8.9p1 Ubuntu 3ubuntu0.14 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 b9:bc:8f:01:3f:85:5d:f9:5c:d9:fb:b6:15:a0:1e:74 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBBYESg2KmNLhFh1KJaN2UFCVAEv6MWr58pqp2fIpCSBEK2wDJ5ap2XVBVGLk9Po4eKBbqTo96yttfVUvXWXoN3M=
|   256 53:d9:7f:3d:22:8a:fd:57:98:fe:6b:1a:4c:ac:79:67 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIBdIs4PWZ8yY2OQ6Jlk84Ihd5+15Nb3l0qvpf1ls3wfa
3000/tcp open  http    syn-ack ttl 61 WEBrick httpd 1.7.0 (Ruby 3.0.2 (2021-07-07))
|_http-server-header: WEBrick/1.7.0 (Ruby/3.0.2/2021-07-07)
|_http-title: RubyDome HTML to PDF
| http-methods: 
|_  Supported Methods: GET HEAD
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

## 3000 HTTP
![image](https://hackmd.io/_uploads/SJRvXMNoZg.png)
![image](https://hackmd.io/_uploads/SyEALMEo-x.png)
Test with `https://gtfobins.org/`, 
![image](https://hackmd.io/_uploads/HJn_VfEjZe.png)
![image](https://hackmd.io/_uploads/S1uZozViZe.png)
`https://github.com/UNICORDev/exploit-CVE-2022-25765`
![image](https://hackmd.io/_uploads/BJd1ozVobe.png)
![image](https://hackmd.io/_uploads/ByDgCMEi-g.png)
![image](https://hackmd.io/_uploads/HJ4KCGVibe.png)

## Privilege Escalation
1. sudo
![image](https://hackmd.io/_uploads/BJVtJmNjZx.png)
![image](https://hackmd.io/_uploads/BkHP7QVsWl.png)

