## PHP-APACHE-DOCKER
Easy and Simple Docker for PHP+Apache


I just stumbled over the internet looking for apache docker images but i only found images for PHP 8  with NGINX. why not apache?


```console
foo@bar:~$ docker-compose build 
foo@bar:~$ docker-compose up 
```

run as daemon
```console
foo@bar:~$ docker-compose build 
foo@bar:~$ docker-compose up -d 
```

## Ports in use (default):
- **Apache**: 80
- **MySQL (MariaDB)**: 3306
- **XDebug**: 9003

## Default Passwords (change me):
``` console
MARIADB_ROOT_PASSWORD: root
MARIADB_DATABASE: project_db
MARIADB_USER: project
MARIADB_PASSWORD: project
```