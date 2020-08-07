## Check Empty Password
```nmap
nmap --script=mysql-empty-password -p 3306 IP
```	
## Enumeración de usuarios
### Nmap
```
nmap --script=mysql-users --script-args="mysqluser='VALIDUSER',mysqlpass='VALIDPASS'" -p 3306 IP
```	
## Login Bruteforce
### Metasploit 
```
use auxiliary/scanner/mysql/mysql_login
```
### Hydra
```
hydra -L USERLIST  -P PASSLIST IP mysql
```

## Ver database schema
### Nmap
```
nmap --script=mysql-databases --script-args="mysqluser='VALIDUSER',mysqlpass='VALIDPASS'" -p 3306 IP
```
### Metasploit 
```
auxiliary/scanner/mysql/mysql_schemadump
```
## POST
### Hashdump
#### Metasploit
```
auxiliary/scanner/mysql/mysql_hashdump
```
#### Nmap Script
```
nmap --script mysql-dump-hashes --script-args="mysqluser='VALIDUSER',mysqlpass='VALIDPASS'" -p 3306 IP
```		
### Writable directories list
```
auxiliary/scanner/mysql/mysql_writable_dirs
```
### Readable files list
```
auxiliary/scanner/mysql/mysql_file_enum
```
