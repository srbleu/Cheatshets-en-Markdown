# Mountd

## Enum
### Nmap full rpcbind
```
nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount
```
## Interacción con el servicio
### Montaje
```
sudo mount IP:/exposedmount /mountpoint
```
