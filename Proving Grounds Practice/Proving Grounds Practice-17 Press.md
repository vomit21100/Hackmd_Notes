## NMAP
```
PORT     STATE SERVICE REASON         VERSION
22/tcp   open  ssh     syn-ack ttl 61 OpenSSH 8.4p1 Debian 5+deb11u1 (protocol 2.0)
| ssh-hostkey: 
|   3072 c9:c3:da:15:28:3b:f1:f8:9a:36:df:4d:36:6b:a7:44 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDNEbgprJqVJa8R95Wkbo3cemB4fdRzos+v750LtPEnRs+IJQn5jcg5l89Tx4junU+AXzLflrMVo55gbuKeNTDtFRU9ltlIu4AU+f7lRlUlvAHlNjUbU/z3WBZ5ZU9j7Xc9WKjh1Ov7chC0UnDdyr5EGrIwlLzgk8zrWx364+S4JqLtER2/n0rhVxa9RCw0tR/oL24kMep4q7rFK6dThiRtQ9nsJFhh6yw8Fmdg7r4uohqH70UJurVwVNwFqtr/86e4VSSoITlMQPZrZFVvoSsjyL8LEODt1qznoLWudMD95Eo1YFSPID5VcS0kSElfYigjSr+9bNSdlzAof1mU6xJA67BggGNu6qITWWIJySXcropehnDAt2nv4zaKAUKc/T0ij9wkIBskuXfN88cEmZbu+gObKbLgwQSRQJIpQ+B/mA8CD4AiaTmEwGSWz1dVPp5Fgb6YVy6E4oO9ASuD9Q1JWuRmnn8uiHF/nPLs2LC2+rh3nPLXlV+MG/zUfQCrdrE=
|   256 26:03:2b:f6:da:90:1d:1b:ec:8d:8f:8d:1e:7e:3d:6b (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBCUhhvrIBs53SApXKZYHWBlpH50KO3POt8Y+WvTvHZ5YgRagAEU5eSnGkrnziCUvDWNShFhLHI7kQv+mx+4R6Wk=
|   256 fb:43:b2:b0:19:2f:d3:f6:bc:aa:60:67:ab:c1:af:37 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIN4MSEXnpONsc0ANUT6rFQPWsoVmRW4hrpSRq++xySM9
80/tcp   open  http    syn-ack ttl 61 Apache httpd 2.4.56 ((Debian))
|_http-server-header: Apache/2.4.56 (Debian)
|_http-title: Lugx Gaming Shop HTML5 Template
| http-methods: 
|_  Supported Methods: POST OPTIONS HEAD GET
8089/tcp open  http    syn-ack ttl 61 Apache httpd 2.4.56 ((Debian))
| http-methods: 
|_  Supported Methods: GET HEAD POST
|_http-favicon: Unknown favicon MD5: 315957B26C1BD8805590E36985990754
|_http-server-header: Apache/2.4.56 (Debian)
|_http-generator: FlatPress fp-1.2.1
|_http-title: FlatPress
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

## 80 HTTP
![image](https://hackmd.io/_uploads/S1-veyfjbx.png)
![image](https://hackmd.io/_uploads/HJOMmJGo-g.png)

## 8089 HTTP
![image](https://hackmd.io/_uploads/H1QqZyzjbx.png)
![image](https://hackmd.io/_uploads/BJ87fyGjbe.png)

1. login page
![image](https://hackmd.io/_uploads/Hy7a41zsbe.png)
![image](https://hackmd.io/_uploads/HkIySJMiWl.png)

2. upload page
上傳功能沒辦法直接上傳php、php5之類的檔案，不過png等圖片能夠正常上傳
![php](https://hackmd.io/_uploads/rkdMUyfobl.png)
在burp suite中把`Content-Type`修改為png也不行
![image](https://hackmd.io/_uploads/SJN0x6zjZe.png)
![image](https://hackmd.io/_uploads/rktN-aGjWl.png)
利用`Magic Byte`繞過類型檢查，但上傳後的結果只會保留最後一項副檔名，所以把`.php`放在最後面
![image](https://hackmd.io/_uploads/SyvLbpfsbx.png)
![image](https://hackmd.io/_uploads/rJxYWazi-l.png)
![image](https://hackmd.io/_uploads/SJBs-6Mibl.png)
`http://192.168.237.29:8089/fp-content/attachs/mime_shellpng.php?cmd=id`
![image](https://hackmd.io/_uploads/BywfM6fo-l.png)


## Privilege Escalation
![image](https://hackmd.io/_uploads/B1Hn2aGi-l.png)
![image](https://hackmd.io/_uploads/ryNJTpzsWe.png)
![image](https://hackmd.io/_uploads/HJIZpaGsbe.png)
