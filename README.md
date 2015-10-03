# Evento DEVDAY 2015 - Belo Horizonte

Código e anotações sobre apresentação do [DEVDAY 2015](http://devday.devisland.com)

A apresentação pode ser vista no link: [Monitoramento em tempo real com Elasticsearch e Kibana](https://goo.gl/sm5scO)

## Prerequisitos
Os seguites softwares devem ser instalados:

## Start ambiente 
```
boot2docker ip
boot2docker init
boot2docker ssh
```

Após iniciar ambiente, será necessário iniciar os conteiners para elasticsearch e kibana
```
docker pull elasticsearch
docker run --name=es -d -p 9200:9200 elasticsearch
docker run  --name=kibana --link es:elasticsearch -d -p 5601:5601 kibana
```

Para realizar um teste, execute os comandos abaixo:
```
export DOCKER_IP=`boot2docker ip`  
export DOCKER_HOST=`boot2docker socket`
curl $DOCKER_IP:9200
````

http://192.168.59.103:9200

Esse comando irá gerar um output com status do seu servidor elasticserach, como:
```
{
  "status": 200,
  "name": "Ecstasy",
  "cluster_name": "elasticsearch",
  "version": {
    "number": "1.7.2",
    "build_hash": "e43676b1385b8125d647f593f7202acbd816e8ec",
    "build_timestamp": "2015-09-14T09:49:53Z",
    "build_snapshot": false,
    "lucene_version": "4.10.4"
  },
  "tagline": "You Know, for Search"
}
```


```json
{
  "created_at": "Fri Oct 02 20:26:12 +0000 2015",
  "text": "RT @sadserver: Introducing Elastic DevNull",
  "user": {
    "name": "Marcus Lacerda",
    "screen_name": "mlacerda_cit"
  }
}
```
