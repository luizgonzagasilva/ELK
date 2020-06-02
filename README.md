## Stack ELK

## Componentes por container:
 
.\ELK\elastic – Elasticsearch (3 nós) \
.\ELK\filebeat – Filebeat (1 instância) \
.\ELK\kafka – kafka (2 brokers) \
.\ELK\kibana – Kibana (1 instância) \
.\ELK\logstash – Logstash (1 instância) 
 
Obs.: antes de executar o comando “docker-compose up” é necessário criar a rede externa através do comando “docker network create elastic”.
 
## Separação parte lógica da infraestrutura:
 
filebeat.yml, kibana.yml e logstash.conf – contém lógica da ETL \
docker-compose.yml – configuração do container 
 
## Arquivos para importação dos dashboards no kibana estão em:
 
.\ELK\dashboards 
 
## Comandos para importação no kibana:
 
curl -X POST "localhost:5601/api/kibana/dashboards/import" -H "kbn-xsrf:reporting" -H "Content-type:application/json" -d @body_dash_alcadas.json \
curl -X POST "localhost:5601/api/kibana/dashboards/import" -H "kbn-xsrf:reporting" -H "Content-type:application/json" -d @body_dash_request.json 
 
 
