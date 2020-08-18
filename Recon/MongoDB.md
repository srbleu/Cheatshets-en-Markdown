# MongoDB

## Interacción con el servicio
### Conexion mediante el cliente mongo
```
mongo IP
```
### Obtener la lista debases de datos mediante el cliente mongo
```
show dbs
```
### Obtener la lista estructura de la DB mediante el cliente mongo
```
use DBNAME
show collections
```
## Ataque por fuerza bruta
```
nmap -p PORT --script mongodb-brute --script-args mongodb-brute.db=DBNAME IP
```

