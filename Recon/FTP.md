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
## Common Vulnerabilities

### ProFTPD 1.3.5
```
https://www.exploit-db.com/exploits/36742
```
### vsftpd 2.3.4 Backdoor
```
https://github.com/ahervias77/vsftpd-2.3.4-exploit
```
