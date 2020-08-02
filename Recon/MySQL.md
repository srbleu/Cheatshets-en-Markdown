## Check Empty Password
```
nmap --script=mysql-empty-password -p 3306 IP
```	
## Enumeración de usuarios
### Nmap
```
nmap --script=mysql-users --script-args="mysqluser='VALIDUSER',mysqlpass='VALIDPASS'" -p 3306 IP
```	
## Ver estructura
### Nmap
```
nmap --script=mysql-databases --script-args="mysqluser='VALIDUSER',mysqlpass='VALIDPASS'" -p 3306 IP
```
### Metasploit 
```
auxiliary/scanner/mysql/mysql_schemadump
```
## Hashdump
### Metasploit
```
auxiliary/scanner/mysql/mysql_hashdump
```
### Nmap
```
nmap --script mysql-dump-hashes --script-args="mysqluser='VALIDUSER',mysqlpass='VALIDPASS'" -p 3306 IP
```		
### Ver Writable directories desde la DB
```
auxiliary/scanner/mysql/mysql_writable_dirs
```
### Ver readable files
```
auxiliary/scanner/mysql/mysql_file_enum
```
