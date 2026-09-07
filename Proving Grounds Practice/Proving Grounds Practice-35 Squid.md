## NMAP
```
PORT      STATE SERVICE       REASON          VERSION
135/tcp   open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
139/tcp   open  netbios-ssn   syn-ack ttl 125 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds? syn-ack ttl 125
3128/tcp  open  http-proxy    syn-ack ttl 125 Squid http proxy 4.14
|_http-server-header: squid/4.14
|_http-title: ERROR: The requested URL could not be retrieved
49666/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
49667/tcp open  msrpc         syn-ack ttl 125 Microsoft Windows RPC
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-time: 
|   date: 2026-04-16T02:32:35
|_  start_date: N/A
| p2p-conficker: 
|   Checking for Conficker.C or higher...
|   Check 1 (port 26044/tcp): CLEAN (Timeout)
|   Check 2 (port 52603/tcp): CLEAN (Timeout)
|   Check 3 (port 38221/udp): CLEAN (Timeout)
|   Check 4 (port 45882/udp): CLEAN (Timeout)
|_  0/4 checks are positive: Host is CLEAN or ports are blocked
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
|_clock-skew: 2s
```

## 445 SMB

![image](_assets/HJw0q6anZg.png)

## 3128 HTTP-PROXY

![image](_assets/rJBWi6p3Zx.png)

![image](_assets/S1vhJ0T2Wl.png)

![image](_assets/HkFuU80hZl.png)

## 8080

![image](_assets/HkG5wL0h-g.png)

![image](_assets/SJHEtI02Wx.png)

![image](_assets/S1z4lPAnbe.png)

![image](_assets/BJRNlwC2Wg.png)

![image](_assets/ry_eWPC3bx.png)

![image](_assets/B1LbWPAn-g.png)

![image](_assets/B1V_7wA3Wl.png)

![image](_assets/SyJYXPAhWg.png)

![image](_assets/rJ8FIvRnWl.png)

![image](_assets/B1NmwwRnWl.png)

## Privilege Escalation

![image](_assets/B1J9OwCnWl.png)

## REF
https://infosecwriteups.com/proving-grounds-practice-squid-walkthrough-f761d2da973f