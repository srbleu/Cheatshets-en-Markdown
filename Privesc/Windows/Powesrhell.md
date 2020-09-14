# Powerview
## Ver usuarios
```
Get-NetUser | select cn
```
## Ver grupos de administracion
```
Get-NetGroup -GroupName *admin*
```
## Ver los shares
```
Invoke-ShareFinder
```
