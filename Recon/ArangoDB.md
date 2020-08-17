# Arango DB
Es un sistema de base de datos multimodelo


## Enumeracion mediante la REST API
### Version
```
curl -X GET http://IP:PORT/_api/version | jq '.'
```
### Users
```
curl -X GET http://IP:PORT/_api/user |  jq '.'
```

## Conexion
### Arangosh
```
arangosh --server.endpoint tcp://IP:PORT
```
### Arangodump
```
arangosh --server.endpoint tcp://IP:PORT
```

## Bruteforce
### Hydra
```
hydra -L USERLIST -P PASSWORDLIST -s PORT -f IP http-get /endpoiint/to/authenticate
```
