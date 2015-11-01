#Demo 

Arquivo com detalhes de como executar a demo apresentada durante o evento que coleta tweets com as hashtag #ESDAVDAY2015 através do Logstash, indexando os documentos no Elasticsearch para visualização no Kibana. Exemplo baseando no https://github.com/elastic/examples/tree/master/ELK_twitter

## Prerequisitos
* Testes realizados utilizando Mac OS X
* Java 8 instalado

## Elasticsearch

Siga os comandos abaixo para fazer o downloado do elasticsearch (versão 1.7.2) e inicia-lo.

```
wget https://download.elastic.co/elasticsearch/elasticsearch/elasticsearch-1.7.2.tar.gz
tar -xf elasticsearch-1.7.2.tar.gz
cp -r conf/elasticsearch/sample_data/ elasticsearch-1.7.2/data/
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

## Logstach

Primeiro será necessário configurar algumas propriedades do indice twitter com os comandos abaixo. Por exemplo, isso define o campo coordinates.coordinates como um [geo_point](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-geo-point-type.html). 
```
curl -XDELETE localhost:9200/_template/twitter
curl -XPUT -H "Content-Type: application/json" --data @conf/logstash/twitter_template.json localhost:9200/_template/twitter

```
Veja mais detalhes so sobre index template na documentação [Index Templates](https://www.elastic.co/guide/en/elasticsearch/reference/1.3/indices-templates.html)


Será necessário criar sua chave de acesso no twitter. Para isso, acesso o [Twitter application] (https://apps.twitter.com/) e cria sua chave de acesso para substituir as variáveis abaixo no arquivo logstash-twitter.conf 
```
consumer_key => "%consumer_key%"
consumer_secret => "%consumer_secret%"
oauth_token => "%oauth_token%"
oauth_token_secret => "%oauth_token_secret%"
```

Na sequência siga os comandos abaixo para fazer o downloado do elasticsearch (versão 1.7.2) e inicia-lo.
```
wget https://download.elastic.co/logstash/logstash/logstash-1.5.4.tar.gz
tar -xf logstash-1.5.4.tar.gz
./logstash-1.5.4/bin/logstash --verbose -f conf/logstash/logstash-twitter.conf

```

## Kibana
Siga os comandos abaixo para fazer o downloado do kibana (versão 4.1.2) e inicia-lo.

```
wget https://download.elastic.co/kibana/kibana/kibana-4.1.2-darwin-x64.tar.gz
tar -xf kibana-4.1.2-darwin-x64.tar.gz
./kibana-4.1.2-darwin-x64/bin/kibana
``

Acessar a página http://localhost:5601/
