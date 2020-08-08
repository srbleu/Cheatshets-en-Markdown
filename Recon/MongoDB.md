## Mongo Conexion
```
mongo IP
```
### Internal DB enum
```
show dbs
```
### Ver estructura de una db
```
use DBNAME
show collections
```
## Muestra las bases de datos
### Nmap Script
```
nmap --script mongodb-databases IP -p PORT
```
## Bruteforce
### Nmap Login BF
```
nmap -p PORT --script mongodb-brute --script-args mongodb-brute.db=DBNAME IP
```
### Metasploit module
```
use auxiliary/scanner/mongodb/mongodb_login
```
