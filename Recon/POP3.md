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
## Interacion con el servicio
### Conexion
```
nc IP PORT
```
### Autenticacion
```
user USERNAME
pass PASSWORD
```
### Listar correos para el usuario
```
list
```
### Recuperar un correo
```
RETR NUMBER
```

## Ataque por fuerza bruta
### Hydra
```
hydra -L UserList -P PassList pop3 IP
```
