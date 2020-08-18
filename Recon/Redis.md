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
AUTH ùsername
```
## Ataque por fuerza bruta
### Nmap Script
```nmap
nmap -p PORT --script redis-brute IP
```
