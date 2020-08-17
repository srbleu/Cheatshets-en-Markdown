# Mountd
## Nmap full rpcbind
```
nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount
```
## Montaje
```
sudo mount IP:/exposedmount /mountpoint
```
