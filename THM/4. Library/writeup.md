# Library

## Nmap

![alt text](image.png)

Podemos ver el nombre de la persona que lo ha puesto el post ``meliodas``
![alt text](image-1.png)

En entramos en el ``robots.txt``
![alt text](image-2.png)

## SSH

Hacemos un ataque de fuerza bruta usando el usuario ``mediolas`` y la lista ``rockyou``
![alt text](image-3.png)

Entramos en el usuario, aqui encontramos ``user.txt``
![alt text](image-4.png)

## Escalada de privilegios

Tenemos un archivo que se encarga de hacer un backup
![alt text](image-6.png)

Vemos los permisos que tenemos

    sudo -l

![alt text](image-5.png)

Borramos el script de backup

    rm -f bak.py

Creamos el archivo de nuevo
![alt text](image-6.png)

Lo ejecutamos y tendremos acceso root

    sudo /usr/bin/python3 /home/meliodas/bak.py

![alt text](image-7.png)

Vamos a la ruta ``/root`` y aqui encontraremos ``root.txt``
![alt text](image-8.png)