# Retro

## Nmap

![alt text](image.png)

## Fuzzing

    gobuster dir -u http://10.10.229.168/ -w /usr/share/dirbuster/wordlists/directory-list-2.3-small.txt -x php

![alt text](image-3.png)

    xfreerdp /u:wade /p:parzival /v:10.10.229.168

![alt text](image-1.png)

En la papelera de reciclaje encontramos un ejecutable que nos permite aumentar los privilegios

![alt text](image-2.png)

Descargamos el [CVE-2017-0213](https://github.com/WindowsExploits/Exploits/tree/master/CVE-2017-0213) y lo ejecutamos en la máquina atacante

![alt text](image-4.png)

Accedemos al escritorio del Administrador, aquí encontraremos el ``root.txt``

![alt text](image-5.png)