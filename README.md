## PHP-APACHE-DOCKER
Easy and Simple Docker for PHP+Apache


I just stumbled over the internet looking for apache docker images but i only found images for PHP 8  with NGINX. why not apache?
so i tried to create my own docker. trying to do it most lightweight possible

## DISCLAIMER: This docker is suitable for development only. not for production!! 

```console
foo@bar:~$ docker-compose build 
foo@bar:~$ docker-compose up 
```

run as daemon
```console
foo@bar:~$ docker-compose build 
foo@bar:~$ docker-compose up -d 
```

### Link:
Open your favorite browser (Internet Explorer not included)
```
 http://localhost 
```

## Ports in use (default):
- **Apache**: 8000
- **MySQL (MariaDB)**: 33060
- **XDebug**: 9003

## Default Passwords (please change):
``` console
MARIADB_ROOT_PASSWORD: root
MARIADB_DATABASE: project_db
MARIADB_USER: project
MARIADB_PASSWORD: project
```
## XDebug:
XDebug is enabled by default at 9003 port, if you need to disable it just run this command below before build

``` console
sed -i 's/WITH_XDEBUG=.*/WITH_XDEBUG=\"true\"/g' docker/Dockerfile
```

 