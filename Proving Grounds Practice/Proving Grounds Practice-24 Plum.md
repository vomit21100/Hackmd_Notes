## NMAP
```
PORT   STATE SERVICE REASON         VERSION
22/tcp open  ssh     syn-ack ttl 61 OpenSSH 8.4p1 Debian 5+deb11u1 (protocol 2.0)
| ssh-hostkey: 
|   3072 c9:c3:da:15:28:3b:f1:f8:9a:36:df:4d:36:6b:a7:44 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDNEbgprJqVJa8R95Wkbo3cemB4fdRzos+v750LtPEnRs+IJQn5jcg5l89Tx4junU+AXzLflrMVo55gbuKeNTDtFRU9ltlIu4AU+f7lRlUlvAHlNjUbU/z3WBZ5ZU9j7Xc9WKjh1Ov7chC0UnDdyr5EGrIwlLzgk8zrWx364+S4JqLtER2/n0rhVxa9RCw0tR/oL24kMep4q7rFK6dThiRtQ9nsJFhh6yw8Fmdg7r4uohqH70UJurVwVNwFqtr/86e4VSSoITlMQPZrZFVvoSsjyL8LEODt1qznoLWudMD95Eo1YFSPID5VcS0kSElfYigjSr+9bNSdlzAof1mU6xJA67BggGNu6qITWWIJySXcropehnDAt2nv4zaKAUKc/T0ij9wkIBskuXfN88cEmZbu+gObKbLgwQSRQJIpQ+B/mA8CD4AiaTmEwGSWz1dVPp5Fgb6YVy6E4oO9ASuD9Q1JWuRmnn8uiHF/nPLs2LC2+rh3nPLXlV+MG/zUfQCrdrE=
|   256 26:03:2b:f6:da:90:1d:1b:ec:8d:8f:8d:1e:7e:3d:6b (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBCUhhvrIBs53SApXKZYHWBlpH50KO3POt8Y+WvTvHZ5YgRagAEU5eSnGkrnziCUvDWNShFhLHI7kQv+mx+4R6Wk=
|   256 fb:43:b2:b0:19:2f:d3:f6:bc:aa:60:67:ab:c1:af:37 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIN4MSEXnpONsc0ANUT6rFQPWsoVmRW4hrpSRq++xySM9
80/tcp open  http    syn-ack ttl 61 Apache httpd 2.4.56 ((Debian))
|_http-title: PluXml - Blog or CMS, XML powered !
|_http-server-header: Apache/2.4.56 (Debian)
|_http-favicon: Unknown favicon MD5: 2D58FC0104110AF4C9BE979DFD8FD83C
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

## 80 HTTP
![image](https://hackmd.io/_uploads/BkPr0Wus-e.png)
![image](https://hackmd.io/_uploads/rJdQQGOjbx.png)
`admin:admin`
![image](https://hackmd.io/_uploads/HJHHmz_jbl.png)
![image](https://hackmd.io/_uploads/HyPvXGds-g.png)
https://github.com/MoritzHuppert/CVE-2022-25018/blob/main/CVE-2022-25018.pdf
![image](https://hackmd.io/_uploads/HJZSNMOjbe.png)
![image](https://hackmd.io/_uploads/HkGyrMuoZg.png)
![image](https://hackmd.io/_uploads/BJcmHz_o-x.png)
`http://192.168.171.28/index.php?static1/static-1&cmd=id`
![image](https://hackmd.io/_uploads/rJfrrGuiWl.png)
![image](https://hackmd.io/_uploads/rkGJIfOoZe.png)

## Privilege Escalation
1. SUID
失敗
![image](https://hackmd.io/_uploads/BJve0M_jWg.png)
![image](https://hackmd.io/_uploads/rJYUAfOjbe.png)
![image](https://hackmd.io/_uploads/HJPw0z_oZg.png)
![image](https://hackmd.io/_uploads/HkVTAGOo-x.png)

2. SMTP
![image](https://hackmd.io/_uploads/SkdTMQusZx.png)
![image](https://hackmd.io/_uploads/HkWPQX_jbx.png)
![image](https://hackmd.io/_uploads/S1-FX7djWx.png)

