# Evento DEVDAY 2015 - Belo Horizonte

Código e anotações sobre apresentação do [DEVDAY 2015](http://devday.devisland.com)

A apresentação pode ser vista no link: [Monitoramento em tempo real com Elasticsearch e Kibana](https://goo.gl/sm5scO)

Apresentação do Rodrigo Domingues sobre [Arquitetura Incremanetal] (http://pt.slideshare.net/RodrigoStefaniDoming/qcon-rio-2015-arquitetura-incremental) de um projeto de 1 milhão de linhas de código.


# Prerequisitos
* Testes realizados utilizando Mac OS X
* Java 8

# Elasticsearch
## Start ambiente 
```
wget https://download.elastic.co/elasticsearch/elasticsearch/elasticsearch-1.7.2.tar.gz
tar -xf elasticsearch-1.7.2.tar.gz
./elasticsearch-1.7.2/bin/elasticsearch
```

Em uma outra console executar uma verificação se o servidor está escutando na porta 9200, usando o comando abaixo.
```
curl localhost:9200
```

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


```javascript
{
  "created_at": "Fri Oct 02 20:26:12 +0000 2015",
  "text": "RT @sadserver: Introducing Elastic DevNull",
  "user": {
    "name": "Marcus Lacerda",
    "screen_name": "mlacerda_cit"
  }
}
```
