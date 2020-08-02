## Checkear registros DNS

### Name Server
```
dig NS domain @ServerIP
```
### Mail Servers
```
dig MX domain @ServerIP
```
### Certificates
```	
dig CAA domain @ServerIP
```
### Location
```
dig LOC domain @ServerIP
```
### Text
```
dig TXT domain @ServerIP
```
### Zone Transfer
```
dig axfr domain @ServerIP
```
### Keys (DNSSEC)
```
dig DNSKEY domain +multiline @ServerIP
```
### DNSSEC Zone Enumeration
```
ldns-walk domain
```
