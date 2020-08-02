## Hallar el domain name/banner 
### Netcat
```
nc IP Puerto 
```	
### Nmap
```
nmap -sV -script banner IP
```

## Enumeracion de usuarios mediante fuerza bruta
```
smtp-user-enum -M VRFY -U USERLIST -t HOST
```
