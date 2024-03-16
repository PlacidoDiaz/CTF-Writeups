# Anthem

## Nmap

![alt text](image.png)

## Web

robots.txt

![alt text](image-1.png)

Umbraco login

![alt text](image-5.png)

Dominio

![alt text](image-4.png)

Email
![alt text](image-6.png)

## Flags

![alt text](image-3.png)

![alt text](image-2.png)

![alt text](image-7.png)

![alt text](image-8.png)

## Pasos Finales

![alt text](image-9.png)

Acceso RDP

    rdesktop -u SD 10.10.139.254

Usamos la contraseña encontrada antes

![alt text](image-10.png)

Contenido de ``User.txt``

![alt text](image-11.png)

Miramos los archivos ocultos del sistema, encontramos la carpeta ``backup``

Le damos permisos a los usuarios del sistema al archivo

![alt text](image-12.png)

![alt text](image-13.png)

Accedemos al usuario administrador y vemos el contenido de ``root.txt``

![alt text](image-14.png)

Para ganar acceso de otra manera podríamos ejecutar ``windows-exploit-suggester.py`` y ver los CVE críticos del sistema