# NMAP

![alt text](image.png)

# WEB

![alt text](image-1.png)

# Fuzzing

![alt text](image-3.png)

![alt text](image-2.png)

![alt text](image-4.png)

![alt text](image-5.png)

Usando ``-x`` podemos buscar por extension

![alt text](image-6.png)

![alt text](image-7.png)

# Decode

Instalamos [Basecrack](https://github.com/mufeedvh/basecrack)

    python3 basecrack.py -f ../ticket 

![alt text](image-8.png)

Contraseña FTP: ``!#th3h00d``

# FTP

vigilante

![alt text](image-9.png)

![alt text](image-10.png)

Descargamos las imagenes, encontramos otro usuario `slade`

![alt text](image-12.png)

Al ver su contenido vemos que `Leave_me_alone.png` no es una imagen

![alt text](image-11.png)


# Fuerza Bruta

    stegcracker ../aa.jpg /usr/share/wordlists/rockyou.txt 

![alt text](image-13.png)

![alt text](image-14.png)

![alt text](image-15.png)

![alt text](image-16.png)

Contraseña ssh: ``M3tahuman``

# SSH

![alt text](image-17.png)

# User Flag

![alt text](image-21.png)

# Escalada de Privilegios

![alt text](image-18.png)

![alt text](image-19.png)

# Root Flag

![alt text](image-20.png)

