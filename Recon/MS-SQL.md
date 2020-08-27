# MS-SQL

## Conexión
```
mssqlclient.py 'DOMAIN/user:pass@IP' -windows-auth
```
### Interación con el servicio
#### Version
```
SELECT @@version
```
#### Listar usuarios
```
SELECT name FROM master..syslogins
```
#### Listar databases
```
SELECT name FROM master..sysdatabases;
```
#### Ver si el usuario actual tiene sysadmin como rol
Si retorna 1 es que si
```
SELECT IS_SRVROLEMEMBER ('sysadmin')
```
