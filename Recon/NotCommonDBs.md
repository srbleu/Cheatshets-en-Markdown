# ArangoDB
Sistema de base de datos multimodelo, usualmente ubicado en el puerto 8529
## Obtener version a traves de la REST API
```
curl -X GET http://IP:PORT/_api/version | jq '.'
```
## Enumeración de usuarios a través de la REST API
```
curl -X GET http://IP:PORT/_api/user |  jq '.'
```
## Interacción con el servicio
Para interacturar con el servicio de ArangoDB podemos usar el cliente Arangosh 
### Conexión mediante Arangosh
```
arangosh --server.endpoint tcp://IP:PORT
```
### Dump de la base de datos con Arangodump
```
arangodump --all-databases tcp://IP:PORT
```
## Ataque por fuerza bruta
Para la obtencion de credenciales usaremos metodos de fuerza bruta a servicios web (http) 
```
hydra -L USERLIST -P PASSWORDLIST -s PORT -f IP http-get /endpoint/to/authenticate
```
# CockroachDB
Sistema de gestión de base de datos distribuido, usualmente ubicado en el puerto 26257
### Obtener la lista de nodos desde el cliente cockroach
```bash
cockroach  node ls --insecure --host IP
```
### Conexión mediante el cliente cockroach
```bash
cockroach sql --insecure --host IP
```
#### Comandos internos
* Obtener version desde la DB
```sql
select version()
```
* Obtener el listado de las bases de datos desde dentro de la DB
```sql
show databases;
```
* Obtener el listado de las tablas desde dentro de la DB
```sql
use DBNAME;
show tables
```
* Obtener los privilegios de los usuarios de la DB 
```sql
show grants on database DBNAME;
```

