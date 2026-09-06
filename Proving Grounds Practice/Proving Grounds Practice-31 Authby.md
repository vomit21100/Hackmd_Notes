## NMAP
```
PORT     STATE SERVICE       REASON          VERSION
21/tcp   open  ftp           syn-ack ttl 125 zFTPServer 6.0 build 2011-10-17
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
| total 9680
| ----------   1 root     root      5610496 Oct 18  2011 zFTPServer.exe
| ----------   1 root     root           25 Feb 10  2011 UninstallService.bat
| ----------   1 root     root      4284928 Oct 18  2011 Uninstall.exe
| ----------   1 root     root           17 Aug 13  2011 StopService.bat
| ----------   1 root     root           18 Aug 13  2011 StartService.bat
| ----------   1 root     root         8736 Nov 09  2011 Settings.ini
| dr-xr-xr-x   1 root     root          512 Apr 08 07:38 log
| ----------   1 root     root         2275 Aug 08  2011 LICENSE.htm
| ----------   1 root     root           23 Feb 10  2011 InstallService.bat
| dr-xr-xr-x   1 root     root          512 Nov 08  2011 extensions
| dr-xr-xr-x   1 root     root          512 Nov 08  2011 certificates
|_dr-xr-xr-x   1 root     root          512 Oct 11 00:16 accounts
242/tcp  open  http          syn-ack ttl 125 Apache httpd 2.2.21 ((Win32) PHP/5.3.8)
| http-auth: 
| HTTP/1.1 401 Authorization Required\x0D
|_  Basic realm=Qui e nuce nuculeum esse volt, frangit nucem!
|_http-server-header: Apache/2.2.21 (Win32) PHP/5.3.8
|_http-title: 401 Authorization Required
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
3145/tcp open  zftp-admin    syn-ack ttl 125 zFTPServer admin
3389/tcp open  ms-wbt-server syn-ack ttl 125 Microsoft Terminal Service
| rdp-ntlm-info: 
|   Target_Name: LIVDA
|   NetBIOS_Domain_Name: LIVDA
|   NetBIOS_Computer_Name: LIVDA
|   DNS_Domain_Name: LIVDA
|   DNS_Computer_Name: LIVDA
|   Product_Version: 6.0.6001
|_  System_Time: 2026-04-08T00:38:59+00:00
|_ssl-date: 2026-04-08T00:39:04+00:00; +3s from scanner time.
| ssl-cert: Subject: commonName=LIVDA
| Issuer: commonName=LIVDA
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha1WithRSAEncryption
| Not valid before: 2025-10-09T17:16:18
| Not valid after:  2026-04-10T17:16:18
| MD5:   6bfe:7637:252b:c376:89c8:e8a3:b163:9ec1
| SHA-1: 1316:97ca:628d:4e98:83c4:af51:2537:b4f5:2e20:55fe
| -----BEGIN CERTIFICATE-----
| MIICzjCCAbagAwIBAgIQjGzgfFRktJdB1OA45IO/BTANBgkqhkiG9w0BAQUFADAQ
| MQ4wDAYDVQQDEwVMSVZEQTAeFw0yNTEwMDkxNzE2MThaFw0yNjA0MTAxNzE2MTha
| MBAxDjAMBgNVBAMTBUxJVkRBMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKC
| AQEAi39FWlmRLE9vKDpT27n3nM22SO7NGy8LZoUZ8ntqXlXwbtrLRIm8YbyTuKwm
| JPaYa4xelXs2FkxLVqUA7SAk6loCpIrv0BBV7Du9rTm92xkhjMY1xiqe4hg2aO87
| kxrzSx+vwjweN/D57hnqVmnCnEQjLjRe5GLh8p+R4XQaOnO5kW9JLvcr9s3tNEpb
| /YIKQu9GO/NmcUMurkP4kGzIHUC1WBwhyDn93o5b9DI7EH4knR+9nsu5Lkj85JR6
| 9PWP7Q+SdDRHiCKVp11Vv7IAGaCRuUzOSSRqd958mdeRNSlupsSCA7rqnGxlzTVE
| AuT6qpVGDtSvhiTy4iAVT9ZPjQIDAQABoyQwIjATBgNVHSUEDDAKBggrBgEFBQcD
| ATALBgNVHQ8EBAMCBDAwDQYJKoZIhvcNAQEFBQADggEBACjanYqgLHXTGlGhs8/m
| +UCJ9PLc2L32YwtXmrOSz69l1Ok75EX3dibszU8mes0+OF0xVpI6vp7jNk0NwkXr
| qNTad0HI7/EikNEk6k7qYZhpE2gl0mIzS5G4OMm/ICOuAp/YMamahikTAwQ6vR3s
| pMdzQWxQcKw/nCo9C1aV2XORFbuqzixEF/MbxHdBla2ujy2ZuYz2RTjBmi9VtILK
| xhbvpsBGfy7+wqkrENszkAmL+BqLGAUp9I04O5+n2WPu+NiOJveS4DA6bDVWKvxy
| PALyBkhZa1zrFrSW2BpTD8fimyedrN+JWmrB6svEvlwwzHIRez2d0YQoCEKApD8D
| sfY=
|_-----END CERTIFICATE-----
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows
```

## 21 & 3145 FTP
![image](https://hackmd.io/_uploads/ryEXEXm3bx.png)
![image](https://hackmd.io/_uploads/SJs0S7m3Wg.png)
![image](https://hackmd.io/_uploads/Sycet7m3Wl.png)
![image](https://hackmd.io/_uploads/ryd6u7Q2-l.png)
![image](https://hackmd.io/_uploads/BJzvYm73-e.png)
![image](https://hackmd.io/_uploads/rk_5FmQn-e.png)
![image](https://hackmd.io/_uploads/Hk5RY7Q2-g.png)
![image](https://hackmd.io/_uploads/SJUEcQQ3-e.png)
![image](https://hackmd.io/_uploads/SybziX7nWx.png)

## 242 HTTP
![image](https://hackmd.io/_uploads/HybKom7nZl.png)
![image](https://hackmd.io/_uploads/BktYi7mn-x.png)

## Privilege Escalation
![image](https://hackmd.io/_uploads/Byq-3QQ3Zl.png)
![image](https://hackmd.io/_uploads/HkUZYEmhWe.png)
![image](https://hackmd.io/_uploads/SkWMYNm3Zl.png)
![image](https://hackmd.io/_uploads/HkzZa47h-e.png)
![image](https://hackmd.io/_uploads/Bk716VQ3Zl.png)
