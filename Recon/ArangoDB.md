## Version
### Rest API
```
curl -X GET http://IP:PORT/_api/version | jq '.'
```

## User Enum
### Rest API
```
curl -X GET http://IP:PORT/_api/user |  jq '.'
```

## Conexion
### Arangosh
```
arangosh --server.endpoint tcp://IP:PORT
```

## Bruteforce
### Hydra
```
hydra -L USERLIST -P PASSWORDLIST -s PORT -f IP http-get /endpoiint/to/authenticate
```
