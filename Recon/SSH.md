# SSH
## Enumeración
### Ver metodos de login para un ususario
```
nmap -p PORT IP --script ssh-auth-methods --script-args="ssh.user=USER"
```
## Ataques por fuerza bruta
### Hydra
```
hydra -L UserList -P PassList ssh IP
```
### Nmap
```
nmap --script ssh-brute --script-args userdb=Userlist -p PUERTO IP
```

