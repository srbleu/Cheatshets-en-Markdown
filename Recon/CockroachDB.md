## Conexion
```bash
cockroach  sql --insecure --host IP
```
### Internal comands
#### Version
```sql
select version()
```
#### Databases
```sql
show databases;
```
#### Tables
```sql
use DBNAME;
show tables
```
#### Privileges
```sql
show grants on database DBNAME;
```
## Node List
```bash
cockroach  node ls --insecure --host IP
```
