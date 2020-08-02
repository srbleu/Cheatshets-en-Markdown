## Anonymous sesion
### Check con nmap
```
nmap IP --script ftp-anon
```
### Sesion
```
ftp IP
> username Anonymous
> password Any Password
```

## Bruteforce login
### Hydra
```
hydra -L UserList -P PassList ftp IP 
```
### Nmap
```
nmap --script ftp-brute --script-args userdb=UserList -p Puerto IP
```
