## NMAP
```
PORT     STATE SERVICE  REASON         VERSION
22/tcp   open  ssh      syn-ack ttl 61 OpenSSH 9.0p1 Ubuntu 1ubuntu8.5 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 02:79:64:84:da:12:97:23:77:8a:3a:60:20:96:ee:cf (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBEXrRUno9oC8lTzQc4mkRYkhVE1WFraJqALzhn+4EmH4j57s4WioLYYYESpMPsdluWAXJreN+LVlUL/5UteMBbI=
|   256 dd:49:a3:89:d7:57:ca:92:f0:6c:fe:59:a6:24:cc:87 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIITU00dnwzhT+PFW6y7qRlFYCQ0UzFakp4R4NIq5TWiS
8090/tcp open  http     syn-ack ttl 61 Apache Tomcat (language: en)
|_http-favicon: Unknown favicon MD5: 966E60F8EB85B7EA43A7B0095F3E2336
| http-title: Log In - Confluence
|_Requested resource was /login.action?os_destination=%2Findex.action&permissionViolation=true
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-trane-info: Problem with XML parsing of /evox/about
8091/tcp open  jamlink? syn-ack ttl 61
| fingerprint-strings: 
|   FourOhFourRequest: 
|     HTTP/1.1 204 No Content
|     Server: Aleph/0.4.6
|     Date: Sat, 28 Mar 2026 16:45:51 GMT
|     Connection: Close
|   GetRequest: 
|     HTTP/1.1 204 No Content
|     Server: Aleph/0.4.6
|     Date: Sat, 28 Mar 2026 16:45:16 GMT
|     Connection: Close
|   HTTPOptions: 
|     HTTP/1.1 200 OK
|     Access-Control-Allow-Origin: *
|     Access-Control-Max-Age: 31536000
|     Access-Control-Allow-Methods: OPTIONS, GET, PUT, POST
|     Server: Aleph/0.4.6
|     Date: Sat, 28 Mar 2026 16:45:16 GMT
|     Connection: Close
|     content-length: 0
|   Help, Kerberos, LDAPSearchReq, LPDString, SSLSessionReq, TLSSessionReq, TerminalServerCookie: 
|     HTTP/1.1 414 Request-URI Too Long
|     text is empty (possibly HTTP/0.9)
|   RTSPRequest: 
|     HTTP/1.1 200 OK
|     Access-Control-Allow-Origin: *
|     Access-Control-Max-Age: 31536000
|     Access-Control-Allow-Methods: OPTIONS, GET, PUT, POST
|     Server: Aleph/0.4.6
|     Date: Sat, 28 Mar 2026 16:45:16 GMT
|     Connection: Keep-Alive
|     content-length: 0
|   SIPOptions: 
|     HTTP/1.1 200 OK
|     Access-Control-Allow-Origin: *
|     Access-Control-Max-Age: 31536000
|     Access-Control-Allow-Methods: OPTIONS, GET, PUT, POST
|     Server: Aleph/0.4.6
|     Date: Sat, 28 Mar 2026 16:45:57 GMT
|     Connection: Keep-Alive
|_    content-length: 0
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
```

## 8090 HTTP
`http://192.168.159.41:8090` -> `http://192.168.159.41:8090/login.action?os_destination=%2Findex.action&permissionViolation=true`
![image](https://hackmd.io/_uploads/BkzBwFrjbg.png)
![image](https://hackmd.io/_uploads/rk7NOFBsbe.png)
![image](https://hackmd.io/_uploads/BJ8tOtHsZx.png)
https://github.com/jbaines-r7/through_the_wire
![image](https://hackmd.io/_uploads/HkxBtFHsbg.png)
![image](https://hackmd.io/_uploads/r1sSKKriZe.png)
![image](https://hackmd.io/_uploads/Syf7tFrsWx.png)


## Privilege Escalation
1. backup 
![image](https://hackmd.io/_uploads/r1rqecBoZg.png)
![image](https://hackmd.io/_uploads/H1ZDlcSjZl.png)
![image](https://hackmd.io/_uploads/S1mplqSiZg.png)
![image](https://hackmd.io/_uploads/Hk8O-5HjZg.png)
![image](https://hackmd.io/_uploads/rk28ZqrjWe.png)

2. crack password
![image](https://hackmd.io/_uploads/SyNmM9Hjbx.png)

3. ssh private key
No `.ssh` folder in current user's home, so assume key was for root
![image](https://hackmd.io/_uploads/HJm4NcSsZx.png)
![image](https://hackmd.io/_uploads/rk4585Bsbe.png)

4. Tar Wildcard injection
![image](https://hackmd.io/_uploads/Hy4Kw9HoZx.png)
![image](https://hackmd.io/_uploads/HkJB3qrjbg.png)
![image](https://hackmd.io/_uploads/Bkhy6crsWl.png)
![image](https://hackmd.io/_uploads/H1MexjBjWe.png)

5. /opt/log-backup.sh
Edit `/opt/log-backup.sh`
![image](https://hackmd.io/_uploads/HkC4xjBobg.png)
![image](https://hackmd.io/_uploads/rJavlorj-g.png)
![image](https://hackmd.io/_uploads/HJcqeorjZx.png)

