# REDIS

## Conexion 
```bash
redis-cli -h IP
```
### Internal comands
#### Version
```redis
INFO
```
#### Ver los nombres de las keys
```redis
KEYS *
```
#### Listar todos los items bajo una key 
```
LRANGE KEYNAME 0 -1
```
```
SMEMBERS KEYNAME
```
```
HGETS KEYNAME
```
#### Li
## See active channels
```nmap
nmap -p PORT --script redis-info IP
```
