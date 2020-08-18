# Arango DB
Es un sistema de base de datos multimodelo, usualmente ubicado en el puerto 8529

## Enumeracion 

### Version a traves de la REST API
```
curl -X GET http://IP:PORT/_api/version | jq '.'
```
### Enumeración de usuarios a través de la REST AAPI
```
curl -X GET http://IP:PORT/_api/user |  jq '.'
```

## Interacción con el servicio
### Conexión mediante Arangosh
```
arangosh --server.endpoint tcp://IP:PORT
```
### Dump de la base de datos con Arangodump
```
arangosh --server.endpoint tcp://IP:PORT
```
## Ataque por fuerza bruta
### Hydra
```
hydra -L USERLIST -P PASSWORDLIST -s PORT -f IP http-get /endpoint/to/authenticate
```
