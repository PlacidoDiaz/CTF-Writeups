# Nmap

![alt text](image.png)

# Fuzzing

![alt text](image-1.png)

Encontramos ``/panel``, intentaremos subir una revershell en php

Como la página no acepta ``.php``, intentaremos hacer un bypass

    mv php-reverse-shell.php php_reverse_shell.phtml 

![alt text](image-2.png)

Ponemos el puerto en escucha

![alt text](image-3.png)

Entramos en la ruta donde se subió y lo ejecutamos

![alt text](image-4.png)

Ya tendremos la shell

![alt text](image-5.png)

# User.txt

    find / -type f -name user.txt 

![alt text](image-6.png)


![alt text](image-7.png)

# Root.txt

Para buscar los archivos con permiso SUID podemos usar el comando:

    find / -type f -user root -perm -4000 2>/dev/null

![alt text](image-8.png)

Usamos [gtfobins](https://gtfobins.github.io/#python), buscamos python.

![alt text](image-9.png)

![alt text](image-10.png)

