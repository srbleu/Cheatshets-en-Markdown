# SMTP

## Enumeracion
## Hallar el domain name/banner (Netcat)
```
nc IP Puerto 
```	
### Hallar el domain name/banner (Nmap)
```
nmap -sV -script banner IP
```
### Enumeracion de usuarios mediante fuerza bruta
```
smtp-user-enum -M VRFY -U USERLIST -t HOST
```
