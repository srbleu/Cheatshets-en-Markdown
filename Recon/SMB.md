# SMB

## Enumeración
### Enum4liux
```
enum4linuz -a IP
```
###Discover netbios name & OS 
```
nmap --script smb-os-discovery.nse -p 445 
```

## Interacción con el servicio
### Accesso mediante null session
```
rpcclient -U "" -N IP
```
### Sacar usuarios mediante (rpcclient)
```
enumdomusers
```
### Ver SID de un usuario mediante (rpcclient)
```
lookupnames user
```
### Obtener groups mediante (rpcclient)
``` 
enumdomgroups
```		
## Shares
### Nmap
```
nmap --script smb-enum-shares.nse -p445 IP
```
### SmbClient
```
smbclient -L IP -N
smbget smb://IP//folder -R
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
## SMB Vulns
### Discovery
```
nmap --script vuln -p139,445 IP
```
### MS17-010
```
https://github.com/worawit/MS17-010
```
### SMB 3.0.X RCE:				
```
https://github.com/amriunix/CVE-2007-2447
```
