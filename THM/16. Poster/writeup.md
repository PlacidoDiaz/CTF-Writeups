# NMAP

![alt text](image.png)

# Postgres

![alt text](image-1.png)

![alt text](image-2.png)

Para obtener la version, introducimos el usuario y contraseña anterior

![alt text](image-3.png)

![alt text](image-4.png)

Dumpeamos los hashes

![alt text](image-5.png)

![alt text](image-6.png)

Módulo para leer archivos: ``auxiliary/admin/postgres/postgres_readfile``

Módulo que permite la ejecución de comandos arbitrarios con las credenciales de usuario adecuadas es: ``exploit/multi/postgres/postgres_copy_from_program_cmd_exec``

![alt text](image-7.png)

![alt text](image-8.png)

Leemos ``credentials.txt``

![alt text](image-9.png)

# SSH

![alt text](image-10.png)

Mejoramos la consola

![alt text](image-11.png)

No podemos acceder a los ficheros de `alison`

![alt text](image-12.png)

Buscamos los ficheros que pertenecen a `alison`

    find / -type f -user alison 2>/dev/null

![alt text](image-13.png)

Revisamos `config.php`

![alt text](image-14.png)

p4ssw0rdS3cur3!#

# Flag user

![alt text](image-15.png)

# Escala de Privilegios

![alt text](image-16.png)

# Flag root

![alt text](image-17.png)

