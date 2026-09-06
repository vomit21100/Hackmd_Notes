## NMAP
```
PORT     STATE  SERVICE    REASON         VERSION
22/tcp   open   ssh        syn-ack ttl 61 OpenSSH 9.6p1 Ubuntu 3ubuntu13.5 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 f2:5a:a9:66:65:3e:d0:b8:9d:a5:16:8c:e8:16:37:e2 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBGT2bbuknyDQCZL8wcewIxfJHCT3ZA9MHovHm5vV8gnY+WaklYD1KkExYX16RT7Du6kDkOd7/VtgT8wyumO7X74=
|   256 9b:2d:1d:f8:13:74:ce:96:82:4e:19:35:f9:7e:1b:68 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIP9T+RtTpSheh2mjfbGIXvNadPVCLuheP1AqmUPx6yic
80/tcp   open   http       syn-ack ttl 61 Apache httpd
| http-git: 
|   192.168.234.186:80/.git/
|     Git repository found!
|     .git/config matched patterns 'user'
|     Repository description: Unnamed repository; edit this file 'description' to name the...
|_    Last commit message: created .env to store the database configuration 
|_http-server-header: Apache
|_http-title: Did not follow redirect to http://bitforge.lab/
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
3306/tcp open   mysql      syn-ack ttl 61 MySQL 8.0.40-0ubuntu0.24.04.1
| ssl-cert: Subject: commonName=MySQL_Server_8.0.40_Auto_Generated_Server_Certificate
| Issuer: commonName=MySQL_Server_8.0.40_Auto_Generated_CA_Certificate
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2025-01-15T14:38:11
| Not valid after:  2035-01-13T14:38:11
| MD5:   6ffd:19b3:1593:91e3:ca5f:95c7:4224:8213
| SHA-1: 5a03:d302:2473:ec92:5347:eaca:48cf:80ea:90c3:2a64
| -----BEGIN CERTIFICATE-----
| MIIDBzCCAe+gAwIBAgIBAjANBgkqhkiG9w0BAQsFADA8MTowOAYDVQQDDDFNeVNR
| TF9TZXJ2ZXJfOC4wLjQwX0F1dG9fR2VuZXJhdGVkX0NBX0NlcnRpZmljYXRlMB4X
| DTI1MDExNTE0MzgxMVoXDTM1MDExMzE0MzgxMVowQDE+MDwGA1UEAww1TXlTUUxf
| U2VydmVyXzguMC40MF9BdXRvX0dlbmVyYXRlZF9TZXJ2ZXJfQ2VydGlmaWNhdGUw
| ggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC3vlh6B1Ng3HYyQjYZO7ql
| gL8vHWgPjT+76J32PHVd8Czjw/ajdvZEj7oyxaMKL4vtZ4OLEbv8BqIJSoD8XTMg
| abxKU5rlAjv5YQ69uqXL35Em3JMZSDMi2PJfP6y5hN1B1CmaEz84IlkOXlunXC26
| PSqmnsT7XZBu5tqzEkAtx1jncPEoaC6QM/lT2nYY8CwBVOV28o7VG4t9LdzahPak
| ZUaOS7e2qEQXCv3RzCmmwR2WyJHfMmxIwOamv/y1s9KZwsUDCOO0T2WJt6VKc4aC
| 7BC/9pNLxCfDlsf8b/bP41liOofwtlQDs8+2VkYX9xTDzfcK9qDbEgSCKV9nicK/
| AgMBAAGjEDAOMAwGA1UdEwEB/wQCMAAwDQYJKoZIhvcNAQELBQADggEBAK7Q9X4j
| Wou6+QCXCh+hvKRoOtFjL/IV1r/2uUGnxU43BYCSFOX/jrBHo+nMh8YERb4e3FtZ
| xmjMEjsbypOBk/FftB2Zc7z4rXZuwwexYRmFFE5LamhT8xm7XoTkHrT8VSEroMeD
| cMkxALo3sBsg8CydjVeKF0g3r6O+eRPYQpwelenWr1ZfVEW09yU5BFqmrNKwLye/
| jkgxUphTSuFL7HudjDHXfkstG9k3NCmMQmaleh6/kqVbjQjA6JQ1b7CoF+kXjJux
| va8oXywtNpvaJxf5bSQolR1LlSLx8kcxkJ6VLHJVtr/qBxnL3JwtzBpTzG3Mj/7m
| H2kcLkCMSfA/PHE=
|_-----END CERTIFICATE-----
|_ssl-date: TLS randomness does not represent time
| mysql-info: 
|   Protocol: 10
|   Version: 8.0.40-0ubuntu0.24.04.1
|   Thread ID: 16
|   Capabilities flags: 65535
|   Some Capabilities: InteractiveClient, LongPassword, ODBCClient, SwitchToSSLAfterHandshake, Speaks41ProtocolNew, LongColumnFlag, SupportsTransactions, SupportsCompression, IgnoreSpaceBeforeParenthesis, ConnectWithDatabase, Speaks41ProtocolOld, DontAllowDatabaseTableColumn, FoundRows, Support41Auth, IgnoreSigpipes, SupportsLoadDataLocal, SupportsMultipleStatments, SupportsMultipleResults, SupportsAuthPlugins
|   Status: Autocommit
|   Salt: 2}BKkB +\x03\IF~%W;c\x03.\x13
|_  Auth Plugin Name: caching_sha2_password
9000/tcp closed cslistener reset ttl 61
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

## 80 HTTP
![image](https://hackmd.io/_uploads/SyYfsQnoZl.png)
![image](https://hackmd.io/_uploads/ry_Ijm3iWx.png)
![image](https://hackmd.io/_uploads/r15DjXhjWg.png)

1. git-dumper
https://github.com/arthaud/git-dumper
![image](https://hackmd.io/_uploads/S1Ju2mhsWl.png)
![image](https://hackmd.io/_uploads/B1v9nmnobx.png)
![image](https://hackmd.io/_uploads/B1WbTQ2iWx.png)
![image](https://hackmd.io/_uploads/HJQrC7njWg.png)

2. EMPLOYEE PLANNING PORTAL
![image](https://hackmd.io/_uploads/H1c9MNniWl.png)
![image](https://hackmd.io/_uploads/rJg2GEnoWg.png)
![image](https://hackmd.io/_uploads/SksvfNnibx.png)
![image](https://hackmd.io/_uploads/H1fmX42obe.png)

## 3306 MYSQL
1. `bitforge_customer_db`
![image](https://hackmd.io/_uploads/ByX6SNnsbx.png)
2. `soplanning`
![image](https://hackmd.io/_uploads/rJtlLV2sZe.png)
![image](https://hackmd.io/_uploads/rk3vI42jWg.png)
![image](https://hackmd.io/_uploads/S1iUw43oZx.png)
![image](https://hackmd.io/_uploads/rk3BOV3iZx.png)
![image](https://hackmd.io/_uploads/Bki2dEhsWg.png)
![image](https://hackmd.io/_uploads/B1VpdNni-x.png)

## 80 HTTP CVE
![image](https://hackmd.io/_uploads/S1RKFEnibx.png)
https://www.exploit-db.com/exploits/52082
![image](https://hackmd.io/_uploads/BkD5YV3jZx.png)
![image](https://hackmd.io/_uploads/rJbF2E2iWe.png)
![image](https://hackmd.io/_uploads/SJE9h4nobl.png)
![image](https://hackmd.io/_uploads/Hygu24hsZx.png)
![image](https://hackmd.io/_uploads/B1Z3nV2sbx.png)
![image](https://hackmd.io/_uploads/r16goVnjWg.png)
![image](https://hackmd.io/_uploads/ry0-i42s-g.png)
![image](https://hackmd.io/_uploads/S1m63N2ibg.png)


## Privilege Escalation

1. Linpeas
SUID、Crontab、backup都沒找到東西

2. pspy
![image](https://hackmd.io/_uploads/Syr5XI2sWl.png)
![image](https://hackmd.io/_uploads/ByKhm83jWe.png)

3. sudo
![image](https://hackmd.io/_uploads/SkT6mUnjWx.png)
![image](https://hackmd.io/_uploads/HJh3IL2iZl.png)
![image](https://hackmd.io/_uploads/rysjLLhs-g.png)
![image](https://hackmd.io/_uploads/r1668Ino-e.png)
![image](https://hackmd.io/_uploads/ByKziI3j-e.png)
