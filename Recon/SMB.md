# SMB

## Enumeración
### Vuln discovery (nmap)
```
nmap --script vuln -p139,445 IP
```
### Enum4liux
```
enum4linuz -a IP
```
### Discover netbios name & OS 
```
nmap --script smb-os-discovery.nse -p 445 
```

## Interacción con el servicio
### Accesso mediante null session
```
rpcclient -U "" -N IP
```
### Sacar usuarios (rpcclient)
```
enumdomusers
```
### Ver SID de un usuario (rpcclient)
```
lookupnames user
```
### Obtener groups (rpcclient)
``` 
enumdomgroups
```		
### Enumerar shares
#### Enumeracion con nmap
```
nmap --script smb-enum-shares.nse -p445 IP
```
### Enumeración y obtencion (smbclient)
```
smbclient -L IP -N
smbget smb://IP//folder -R
```
### Acceso a folder mediante null sesion
```
smbclient -N \\\\IP\\folder 
```
## Enumeracion de usuarios (nmap)
```
nmap --script smb-enum-users.nse -p445 IP
```
## Crackmapexec user discovery via RID
```
crackmapexec -t 90 smb IP -u users.txt -p pass.txt --rid-brute
```

## Ataques por fuerza bruta
### Hydra
```
hydra -L UserList -P PassList smb IP
```

## Vulnerabilidades comunes sin metasploit
### MS17-010
```
https://github.com/helviojunior/MS17-010 
```
### SMB 3.0.X RCE:				
```
https://github.com/amriunix/CVE-2007-2447
```
