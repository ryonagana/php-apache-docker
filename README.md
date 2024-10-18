## PHP-APACHE-DOCKER
Dead Simple Docker for PHP+Apache

I just stumbled over the internet looking for apache docker images but i only found images for PHP 8  with NGINX. why not apache?
so i tried to create my own docker. trying to do it most lightweight possible

## DISCLAIMER: This Docker is suitable for development only. not for production!! 

```console
foo@bar:~$ docker-compose build 
foo@bar:~$ docker-compose up 
```

**run as daemon**
```console
foo@bar:~$ docker-compose build 
foo@bar:~$ docker-compose up -d 
```

### Link:
Open your favorite browser **(Internet Explorer not included)**
```
 http://localhost:8000 
```
## phpMyAdmin
Server: <blank>
User: **root**
Password: **root**
```
 http://localhost:8090
```


## Change UID and GID 
``` console
id -u
1000
id -g
1000
```
then copy the values  in **docker-compose.yml**:
``` yml
  args:
    - UID=${UID:-1000}
    - GID=${GID:-1000}
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

## Extensions Installed
-  PHP Default Extensions
- GD
- MySQL (MySQLi)
- PDO MySQL
- Intl
- Imagick
- XDebug

## XDebug:
XDebug is enabled by default at 9003 port, if you need to disable it just run this command below before build

``` console
sed -i 's/WITH_XDEBUG=.*/WITH_XDEBUG=\"true\"/g' docker/Dockerfile
```


 

