# Mountd

## Enum
### Nmap full rpcbind
```
nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount
```
### Showmounts
```
showmunt -e IP
```
## Interacción con el servicio
### Montaje
```
sudo mount IP:/exposedmount /mountpoint
```
