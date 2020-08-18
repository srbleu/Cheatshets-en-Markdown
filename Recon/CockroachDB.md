# CockroachDB
Un sistema de gestión de base de datos distribuido

## Enumeración
### Obtener la lista de nodos desde el cliente
```bash
cockroach  node ls --insecure --host IP
```

## Interacción con el servicio
### Conexión mediante el cliente
```bash
cockroach sql --insecure --host IP
```
#### Obtener version desde la DB
```sql
select version()
```
#### Obtener el listado de las bases de datos desde dentro de la DB
```sql
show databases;
```
#### Obtener el listado de las tablas desde dentro de la DB
```sql
use DBNAME;
show tables
```
#### Obtener los privilegios de los usuarios de la DB 
```sql
show grants on database DBNAME;
```
