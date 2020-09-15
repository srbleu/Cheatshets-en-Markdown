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
# AD
## Domain Info
```
Get-ADDomain | Select-Object NetBIOSName, DNSRoot, InfrastructureMaster
```
## Trusts
```
Get-ADTrust -Filter * | Select-Object Direction,Source,Target
```
## AV off
```
Set-MpPreference -DisableRealtimeMonitoring $true
```
