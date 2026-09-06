## NMAP
```
PORT     STATE SERVICE  REASON         VERSION
21/tcp   open  ftp      syn-ack ttl 61 vsftpd 3.0.5
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_-rw-r--r--    1 0        0            1752 Sep 19  2024 config.xml
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to 192.168.45.241
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 1
|      vsFTPd 3.0.5 - secure, fast, stable
|_End of status
22/tcp   open  ssh      syn-ack ttl 61 OpenSSH 9.6p1 Ubuntu 3ubuntu13.4 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 76:18:f1:19:6b:29:db:da:3d:f6:7b:ab:f4:b5:63:e0 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBMeGcI7LXAgYpdcxsbgmDh+FrFwBJxUEPxSU4XODxVs1CWLxFnxl1/SZ0ReciCentljLQxi9LqNYvR//3y6kAms=
|   256 cb:d8:d6:ef:82:77:8a:25:32:08:dd:91:96:8d:ab:7d (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAILE9A0DdfM97fpb5q8N9nmI/9/8rqT8ADRWK8KBegxYM
80/tcp   open  http     syn-ack ttl 61 Apache httpd 2.4.58 ((Ubuntu))
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
|_http-title: Apache2 Ubuntu Default Page: It works
|_http-server-header: Apache/2.4.58 (Ubuntu)
9443/tcp open  ssl/http syn-ack ttl 61 Apache httpd 2.4.58 ((Ubuntu))
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title:  Home - Prison Management System
| tls-alpn: 
|_  http/1.1
| ssl-cert: Subject: commonName=vmdak.local/organizationName=PrisonManagement/stateOrProvinceName=California/countryName=US/localityName=San Francisco/organizationalUnitName=PrisonManagement
| Subject Alternative Name: DNS:vmdak.local
| Issuer: commonName=vmdak.local/organizationName=PrisonManagement/stateOrProvinceName=California/countryName=US/localityName=San Francisco/organizationalUnitName=PrisonManagement
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2024-08-20T09:21:33
| Not valid after:  2025-08-20T09:21:33
| MD5:   a084:b16c:8fa7:a1e8:6913:bc01:d4ef:0ac7
| SHA-1: 1af5:2e89:01e5:9ac8:0dbd:3019:b265:0ff4:938f:23a5
| -----BEGIN CERTIFICATE-----
| MIID1TCCAr2gAwIBAgIURiW3dAwH8nmwj7Pas1KEsHwyaVcwDQYJKoZIhvcNAQEL
| BQAwgYYxCzAJBgNVBAYTAlVTMRMwEQYDVQQIDApDYWxpZm9ybmlhMRYwFAYDVQQH
| DA1TYW4gRnJhbmNpc2NvMRkwFwYDVQQKDBBQcmlzb25NYW5hZ2VtZW50MRkwFwYD
| VQQLDBBQcmlzb25NYW5hZ2VtZW50MRQwEgYDVQQDDAt2bWRhay5sb2NhbDAeFw0y
| NDA4MjAwOTIxMzNaFw0yNTA4MjAwOTIxMzNaMIGGMQswCQYDVQQGEwJVUzETMBEG
| A1UECAwKQ2FsaWZvcm5pYTEWMBQGA1UEBwwNU2FuIEZyYW5jaXNjbzEZMBcGA1UE
| CgwQUHJpc29uTWFuYWdlbWVudDEZMBcGA1UECwwQUHJpc29uTWFuYWdlbWVudDEU
| MBIGA1UEAwwLdm1kYWsubG9jYWwwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEK
| AoIBAQCl8yfoIUj2NmSk604KvUiywINTEotSYWjkgytYJX31qFyZ1AQHiltdprGo
| AWdDhKg5K/SGV8v+sYW01Uy9DZht1NOl3LTKxKIUpDbIW4ZcNGZhzvnj8fXvUs9u
| cbp1x8Ihf62+zn7OrN8BLG0mvLH9RPv8s61eLwNlAB22mR5ae88M65VKBAWJE2Bw
| D0M9aqvALnwfzZnCwLnoaeX7S0E2zKnLpRfp/eWyxnMrRz+jOTYXUbfP29mJpE8U
| xWtwUx/Y25L7/6ys0PNwsftzF+bVDukp9cuyKHupeMrUqCFXk2gJADgfgwynvOTY
| o6WHV+BSAJUFgSU2z8lsdTtKdmxJAgMBAAGjOTA3MBYGA1UdEQQPMA2CC3ZtZGFr
| LmxvY2FsMB0GA1UdDgQWBBTEG82q/A3SsR5MsIRHvcSaG6zhWTANBgkqhkiG9w0B
| AQsFAAOCAQEApUC8oiqqm6hvnCtdGj91FKe0dXUOCoNr+lOPqsxvzAz9Cz/+RYiR
| uPbay7CPkLO6uJgMAy/u0F7LXuii6nmMmbLIjHyxVuNSAlwrBthjwuoA5vHWsbn8
| Ol7BHnWwL7toLOBk2g1LmD7mlJ8Nm50ZXC2bxJrfHrXL47EH2ejkq43mAD8QbyS5
| yt0Bu8Hf0FjLrE5dQoa1zZoSbqqHjVzmR+9DLwiZpAEGJnG2qMdGkQKWRnBftq+o
| rH6qH63qUWXqyXYFYuuCEyDraNVSl9eaB+lmCIuQLjISm3b4lGEPbAzc839yMHQ4
| c72pNPdHxlcKTjHMCE3pF4UMYoBk/cineg==
|_-----END CERTIFICATE-----
|_ssl-date: TLS randomness does not represent time
|_http-server-header: Apache/2.4.58 (Ubuntu)
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel
```

## 21 FTP
![image](https://hackmd.io/_uploads/r1-cLUpibx.png)
![image](https://hackmd.io/_uploads/r1V4PUToZg.png)

## 80 HTTP
![image](https://hackmd.io/_uploads/HJHChIajWl.png)
![image](https://hackmd.io/_uploads/H1SyaIasWl.png)

## 9443 HTTP
![image](https://hackmd.io/_uploads/H1oB8v6sWg.png)

1. login
![image](https://hackmd.io/_uploads/SywrwvaiZe.png)
![image](https://hackmd.io/_uploads/ryKUwPTjZg.png)
![image](https://hackmd.io/_uploads/BJSMOPTjbx.png)

2. RCE
https://github.com/Aa1b/mycve/blob/main/Readme.md
![image](https://hackmd.io/_uploads/B1zW5wasZl.png)
![image](https://hackmd.io/_uploads/r1awoPTiZe.png)
![image](https://hackmd.io/_uploads/Sk2inwpibe.png)
![image](https://hackmd.io/_uploads/SkwhhP6jWx.png)
![image](https://hackmd.io/_uploads/HkKanD6jWg.png)
![image](https://hackmd.io/_uploads/Bk4RnPToWl.png)

## Privilege Escalation
![image](https://hackmd.io/_uploads/S1lmXdajWl.png)
`sqlCr3ds3xp0seD`
![image](https://hackmd.io/_uploads/r11UXdpjbe.png)
![image](https://hackmd.io/_uploads/SyCDNOao-l.png)
![image](https://hackmd.io/_uploads/H1gs4_6o-l.png)
![image](https://hackmd.io/_uploads/rJ8lSO6o-x.png)
![image](https://hackmd.io/_uploads/BJ54DdpiWx.png)
![image](https://hackmd.io/_uploads/rksHvupiZx.png)
![image](https://hackmd.io/_uploads/rkwIPuaoWg.png)
`Malcom:escobar2012`
![image](https://hackmd.io/_uploads/Bk1mw_piWx.png)
沒有Malcom這個使用者
![image](https://hackmd.io/_uploads/rJxkuuTiWx.png)
![image](https://hackmd.io/_uploads/ryZmd_aj-g.png)
`RonnyCache001`
![image](https://hackmd.io/_uploads/HyRDu_6s-l.png)
`vmdak:RonnyCache001`
![image](https://hackmd.io/_uploads/HkHWF_pj-x.png)
![image](https://hackmd.io/_uploads/BJnNFuTsbx.png)
![image](https://hackmd.io/_uploads/SyP33upi-e.png)
`127.0.0.1:8080`
![image](https://hackmd.io/_uploads/H1uWIc-2-l.png)
![image](https://hackmd.io/_uploads/HkIAF5-3be.png)
![image](https://hackmd.io/_uploads/ryD0j5bhZx.png)
![image](https://hackmd.io/_uploads/BJGA-sb2Zg.png)
![image](https://hackmd.io/_uploads/S1TAZjb2bx.png)

