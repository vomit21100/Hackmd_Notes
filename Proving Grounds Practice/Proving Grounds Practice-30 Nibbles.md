## NMAP
```
PORT     STATE  SERVICE      REASON         VERSION
21/tcp   open   ftp          syn-ack ttl 61 vsftpd 3.0.3
22/tcp   open   ssh          syn-ack ttl 61 OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 10:62:1f:f5:22:de:29:d4:24:96:a7:66:c3:64:b7:10 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDJgyzpWrB8SyLb/XmPYQYzsnfizW7d0aNZHpwQ9ivcHQ/RYLbCc8yUIQGN2JMqCgfSj8CRMA36UnV8jnngjkw9njcgMyA5qc1mO4tzzH7VNkW2t5AmP7Q1HBt+SThlLa0JxBN6Gd5BOPwrsk9YTjLj8ax2ncvGBq8jzQjYmm9jF4VgBak5DY+Q5JWdf9krumSlR+V8yneV9aQ6sVy2XgkCJQLQ8GoUTm/13XUTc3TCKQ2KOJ2FzA8VcNTfxqTDxalwnYrZ1tod7BRfMeff5MwxC5gzeB+hdOVC0zAZlvNtMxH6SCxMBRCoX9IHL27E6WtSGXCj1SLYJWrFImjp+I1L
|   256 c9:15:ff:cd:f3:97:ec:39:13:16:48:38:c5:58:d7:5f (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBM7uIYLogPsKP+c0QrezqQfB94ml7djfUOtG8ZAoMX6yK898l0TbgyAShcQSmdOsSMGdSO4GZpixCFJdsYkBi0M=
|   256 90:7c:a3:44:73:b4:b4:4c:e3:9c:71:d1:87:ba:ca:7b (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIKoHnGdMtb37ORTRBt2cTfWvQE7IB3fF3ewP/1tqn0JF
80/tcp   open   http         syn-ack ttl 61 Apache httpd 2.4.38 ((Debian))
|_http-server-header: Apache/2.4.38 (Debian)
|_http-title: Enter a title, displayed at the top of the window.
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
139/tcp  closed netbios-ssn  reset ttl 61
445/tcp  closed microsoft-ds reset ttl 61
5437/tcp open   postgresql   syn-ack ttl 61 PostgreSQL DB 11.3 - 11.9
| ssl-cert: Subject: commonName=debian
| Subject Alternative Name: DNS:debian
| Issuer: commonName=debian
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2020-04-27T15:41:47
| Not valid after:  2030-04-25T15:41:47
| MD5:   b086:6d30:4913:684e:16c1:8348:fc76:fe43
| SHA-1: cb30:5109:0fc1:14ab:0fb9:8e55:5874:4bb5:ba57:66af
| -----BEGIN CERTIFICATE-----
| MIIC0DCCAbigAwIBAgIUYoM4kALX3eWKWuCQ1/K5FujVbGowDQYJKoZIhvcNAQEL
| BQAwETEPMA0GA1UEAwwGZGViaWFuMB4XDTIwMDQyNzE1NDE0N1oXDTMwMDQyNTE1
| NDE0N1owETEPMA0GA1UEAwwGZGViaWFuMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8A
| MIIBCgKCAQEAkpSVo7cfTt1CRy7yDV5Nr2dOJxIyg3JdaE+Mdtsw7/cbPaucXy/L
| fYOoyUsSINbZtIV6/WEpFVD+fIWwPoPWsgazcnNF0Z1quuxOjXnmZICvVqku5vHk
| Q+facbUNjGpz9OMC4s0y/T7uHH6psPoBBgL5ZVTNvU6tK/CnvjtPpMgQ+bOkIqsM
| mMxQnUILBBfUdaVfgetlPCc1qg4+fq0ZCP/d0vjIlb6kA3AuprjFo2xpLwtbx0RM
| BXkmm+STQRTxYnY62MRiL52tzACWfI7lml8LnUFP98tpPzT/0UCBx8cLLNrGlhQP
| ZZb7sALAS8hjpOcIjvRT+ZfXKHHma5RvGQIDAQABoyAwHjAJBgNVHRMEAjAAMBEG
| A1UdEQQKMAiCBmRlYmlhbjANBgkqhkiG9w0BAQsFAAOCAQEAJ1f62YGJW8Ds0e31
| s6hlCQX0kpn5+UXbTMMkjkBWp54aPg6YjUbg4py/E+gJtDWDv/Z8bT+ggiHdIQLf
| +99KE7ShNlnn+hiI4MYjza5rl2W00taN0PiYcKpz898aQ/4Kmho5wkYz+s1bi87O
| 5/IphYJXZYLOLf3CzuWzCT5RUBKZO/BVX79kqJvOLH2xJOkRwA9mgNh5QY0CBzCk
| NVOoDL+Yhof2sZs/UetiW//U8Mtiz22rQWmU4l/tU/X8rUAJQYOCmohGCXnU3aN2
| 6VSDkryCvRWChxwJtqXdKEMZ03E/zr35LhqLWmQmRSEjeVw10HN3g6Y1NpAKV1+g
| rFaQxA==
|_-----END CERTIFICATE-----
|_ssl-date: TLS randomness does not represent time
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel
```

## 21 FTP
![image](https://hackmd.io/_uploads/B1_xrh-nZg.png)

## 80 HTTP
![image](https://hackmd.io/_uploads/BJGQBnZ3Zg.png)

## 8423
![image](https://hackmd.io/_uploads/S10S_3-2Wg.png)
![image](https://hackmd.io/_uploads/BkDCO2bn-x.png)
![image](https://hackmd.io/_uploads/Skw4K2WhWx.png)
![image](https://hackmd.io/_uploads/SkFzinb2-e.png)

## Privilege Escalation
![image](https://hackmd.io/_uploads/BkslMmQ3Wx.png)
![image](https://hackmd.io/_uploads/HJIWfQX2Ze.png)
![image](https://hackmd.io/_uploads/HyqfMmQh-g.png)
