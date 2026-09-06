## NMAP
```
PORT     STATE SERVICE REASON         VERSION
22/tcp   open  ssh     syn-ack ttl 61 OpenSSH 8.9p1 Ubuntu 3ubuntu0.4 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 b9:bc:8f:01:3f:85:5d:f9:5c:d9:fb:b6:15:a0:1e:74 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBBYESg2KmNLhFh1KJaN2UFCVAEv6MWr58pqp2fIpCSBEK2wDJ5ap2XVBVGLk9Po4eKBbqTo96yttfVUvXWXoN3M=
|   256 53:d9:7f:3d:22:8a:fd:57:98:fe:6b:1a:4c:ac:79:67 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIBdIs4PWZ8yY2OQ6Jlk84Ihd5+15Nb3l0qvpf1ls3wfa
80/tcp   open  http    syn-ack ttl 61 Apache httpd 2.4.52 ((Ubuntu))
|_http-server-header: Apache/2.4.52 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
|_http-title: Apache2 Ubuntu Default Page: It works
8338/tcp open  http    syn-ack ttl 61 Python http.server 3.5 - 3.10
| http-robots.txt: 1 disallowed entry 
|_/
|_http-favicon: Unknown favicon MD5: 4F9B844EA920CCFEA291014FE8B51B6D
|_http-server-header: Maltrail/0.52
|_http-title: Maltrail
| http-methods: 
|_  Supported Methods: GET POST
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

## 80 HTTP
![image](https://hackmd.io/_uploads/r1HbKi-nZl.png)

## 8338 HTTP
![image](https://hackmd.io/_uploads/ByU7Kj-2Wg.png)
![image](https://hackmd.io/_uploads/HJM5tjW3Zl.png)
![image](https://hackmd.io/_uploads/SJzntibnWx.png)
![image](https://hackmd.io/_uploads/ryW19jb3-x.png)
![image](https://hackmd.io/_uploads/HJwxco-nZe.png)

* cve
https://github.com/joshchalabi/Maltrail-0.52-Exploit-RCE
![image](https://hackmd.io/_uploads/BJRX5sW2Zg.png)
![image](https://hackmd.io/_uploads/rke0O9jZ3bl.png)
![image](https://hackmd.io/_uploads/HJ9Y9iWnbl.png)


## Privilege Escalation
1. possible password
![image](https://hackmd.io/_uploads/SyOu3jbn-l.png)
![image](https://hackmd.io/_uploads/By6Y3j-hZl.png)

2. sus file
`/var/backups/etc_Backup.sh`
![image](https://hackmd.io/_uploads/ry9pRj-3Zl.png)
![image](https://hackmd.io/_uploads/rkjRAobh-e.png)
![image](https://hackmd.io/_uploads/BJR1knWnWg.png)
沒反應

3. /var/backups/etc_Backup.sh(again)
測試後只有22、80、8338可以用於反連
![image](https://hackmd.io/_uploads/r1mA-2bnZe.png)
