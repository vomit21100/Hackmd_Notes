## NMAP
```
PORT     STATE SERVICE        REASON          VERSION
1978/tcp open  remotemouse    syn-ack ttl 125 Emote Remote Mouse
1979/tcp open  unisql-java?   syn-ack ttl 125
1980/tcp open  pearldoc-xact? syn-ack ttl 125
3389/tcp open  ms-wbt-server  syn-ack ttl 125 Microsoft Terminal Services
| ssl-cert: Subject: commonName=Remote-PC
| Issuer: commonName=Remote-PC
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2025-12-02T17:03:21
| Not valid after:  2026-06-03T17:03:21
| MD5:   7310:58e1:f474:d80b:d8a8:e520:e559:6777
| SHA-1: 2df4:9c88:76bf:01a5:cc77:e8aa:4d4a:7202:50cb:10fb
| -----BEGIN CERTIFICATE-----
| MIIC1jCCAb6gAwIBAgIQFROsLVy6BKNHDHSD/nhssTANBgkqhkiG9w0BAQsFADAU
| MRIwEAYDVQQDEwlSZW1vdGUtUEMwHhcNMjUxMjAyMTcwMzIxWhcNMjYwNjAzMTcw
| MzIxWjAUMRIwEAYDVQQDEwlSZW1vdGUtUEMwggEiMA0GCSqGSIb3DQEBAQUAA4IB
| DwAwggEKAoIBAQCkTYVZWoxN8QCkX6NiTHxrfdRLCilzcjj1+fmwTVfSmayQ8pac
| l26eajvleOqGHP7NfJFG23vgysLEnp5md14p7eFpFlFEtQNqNXdkl6c2UGyMm1oL
| 8F44vHsgMtqpomXByLiMPPLYE+1mHoMwaUWsxRk5eP7mutF7srKZKUOTzs1xqk8g
| s2AO44Xv2jR7lb7E3kMuZlhPlQ1sr7n484+cD50tzijELlkD2lUjoL+YO9sJr+Mk
| CFtzE/0v+h/hhlv2HTWWnx5dj8HqwelvyE7bgaNW2LWE70bMEBuQV38ZGWEc/Cmo
| jJGvIK7lEgqfMMHa2hsxPv62UvQuTw+6vf1ZAgMBAAGjJDAiMBMGA1UdJQQMMAoG
| CCsGAQUFBwMBMAsGA1UdDwQEAwIEMDANBgkqhkiG9w0BAQsFAAOCAQEAnZPq0xMm
| SNYroE1Z9AoOzblZXIzidV51oSFqRco608uIU73J6oIyiJtCUdQ/nhS7tVrR5wv+
| KtyqC0vXzvteRz87ConEhIV5+dKdpd6UypFMqXGxZX/SAsjPUP091oqJj313hw24
| WVrRYZNJnHE9ay9T7uxq0JxOGxB5Fw6QGsPoaS6GPUkkUkRqW856eAxj7/Or3wvH
| T1f//8TnLhb09f+iIOct6qJChx+Hm3EfsExfPiIfRrIncqPH8rECbC2hqQQoi8mD
| J3eb8NNNlGXH0v6iZgrn90bmPH1xMDKeQCv8sFp0d+cM1JuRwL+MCBNyQtUSUDC6
| I3HhClfooBgNdg==
|_-----END CERTIFICATE-----
| rdp-ntlm-info: 
|   Target_Name: REMOTE-PC
|   NetBIOS_Domain_Name: REMOTE-PC
|   NetBIOS_Computer_Name: REMOTE-PC
|   DNS_Domain_Name: Remote-PC
|   DNS_Computer_Name: Remote-PC
|   Product_Version: 10.0.19041
|_  System_Time: 2026-03-25T17:24:29+00:00
|_ssl-date: 2026-03-25T17:24:56+00:00; +2s from scanner time.
7680/tcp open  pando-pub?     syn-ack ttl 125
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows
```

## 1978 remotemouse
1. exploit-db
把cale.exe的部份改成powershell reverse shell，但等待一段時間後還是未觸發
![image](https://hackmd.io/_uploads/HJWL05Wo-e.png)
![image](https://hackmd.io/_uploads/ryqDJj-sbx.png)
![image](https://hackmd.io/_uploads/B1rW-jWobl.png)

2. github
`https://github.com/p0dalirius/RemoteMouse-3.008-Exploit/blob/master/RemoteMouse-3.008-Exploit.py`
![image](https://hackmd.io/_uploads/BJ12WoWobx.png)
![image](https://hackmd.io/_uploads/ByC_Li-oWx.png)
![image](https://hackmd.io/_uploads/B1JqLsWoZe.png)
![image](https://hackmd.io/_uploads/Sk3qLsbjbg.png)

## Privilege Escalation
1. local files
`Get-ChildItem -Path C:\ -Include *.ini,*.cfg,*.xml -File -Force -Recurse -ErrorAction SilentlyContinue | where-Object { $_.FullName -notmatch 'C:\\Windows\\' -and $_.Name -notin 'desktop.ini','ntuser.ini' }`
winpeas裡面沒有找到有用的資訊，只剩windows的版本更新漏洞還沒查，但優先查看其他有讀取權限的檔案
![image](https://hackmd.io/_uploads/B1uUjoZobg.png)
![image](https://hackmd.io/_uploads/rJNMhiWj-g.png)
![image](https://hackmd.io/_uploads/ryXv3j-sZl.png)

2. exploit-db
![image](https://hackmd.io/_uploads/BycaTsZoWe.png)
![image](https://hackmd.io/_uploads/ryRm1hbsZx.png)
![image](https://hackmd.io/_uploads/HyJHJhZsZg.png)
![image](https://hackmd.io/_uploads/SJ9M13-o-g.png)
![image](https://hackmd.io/_uploads/H1ZIJ3ZiZg.png)

