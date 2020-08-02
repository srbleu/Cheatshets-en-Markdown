## Discover netbios name & OS 
```
nmap --script smb-os-discovery.nse -p 445 
```
## Null session
```
rpcclient -U "" -N IP
```

## Comandos propios de RPCclient
### Sacar usuarios
```
enumdomusers
```
### Ver SID de un usuario
```
lookupnames user
```
### Groups
```
enumdomgroups
```		
## Shares
### Nmap
```
nmap --script smb-enum-shares.nse -p445 IP
```
### Metasploit
```
auxiliary/scanner/smb/smb_enumshares
```
### SmbClient
```
smbclient -L IP -N
```

## Enumeracion de usuarios
### Nmap
```
nmap --script smb-enum-users.nse -p445 IP
```
### Metasploit
```
auxiliary/scanner/smb/smb_enumusers
```		
## Bruteforce
### Metasploit
```
auxiliary/scanner/smb/smb_login
```
### Hydra
```
hydra -L UserList -P PassList smb IP
```
