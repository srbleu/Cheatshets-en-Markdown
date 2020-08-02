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
