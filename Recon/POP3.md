## Hallar el domain name/banner 
### Netcat
```
nc IP Puerto 
```
### Nmap
```
nmap -sV -script banner IP
```	
## Bruteforcing
### Hydra
```
hydra -L UserList -P PassList pop3 IP
```
### Hydra SSL version 
```
hydra -L UserList -P PassList pop3s IP 	
```
### Metasploit module
```
auxiliary/scanner/pop3/pop3_login
```
