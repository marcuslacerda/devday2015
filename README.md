# Evento DEVDAY 2015 - Belo Horizonte

Código e anotações sobre apresentação do [DEVDAY 2015](http://devday.devisland.com)

A apresentação pode ser vista no link: [Monitoramento em tempo real com Elasticsearch e Kibana](https://docs.google.com/presentation/d/1bMvYYQh8v0BkwQHtedOkId9yrw5G99gz9AMuyFAR29Y/pub?start=false&loop=false&delayms=3000)


## Referências
Apresentação do Rodrigo Domingues sobre [Arquitetura Incremanetal] (http://pt.slideshare.net/RodrigoStefaniDoming/qcon-rio-2015-arquitetura-incremental) de um projeto de 1 milhão de linhas de código.

[Codahale metrics] (http://metrics.dropwizard.io) que foi utilizado para criar métricas de runtime do código. Ver também o [ElasticsearchReporter] (https://github.com/elastic/elasticsearch-metrics-reporter-java) que foi utilizado para enviar as métricas para o elasticsearch. 


## Outras dicas
Instalar o plugin head para facilitar na administração dos índices. Depois de instalar será necessário reiniciar o elasticsearch.
./elasticsearch-1.7.2/bin/plugin -install mobz/elasticsearch-head


Instalar no Chrome o plugin POSTMAN que auxilia na utilização da API REST do Elasticserach
https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop