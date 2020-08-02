## Ver metodos de login del ususario
```
nmap -p PORT IP --script ssh-auth-methods --script-args="ssh.user=USER"
```
## Bruteforcing
### Hydra
```
hydra -L UserList -P PassList ssh IP
```
### Nmap
```
nmap --script ssh-brute --script-args userdb=Userlist -p PUERTO IP
```
### Metasploit module
```
auxiliary/scanner/ssh/ssh_login
```
