# ElasticStack Overview



## ElasticSearch

Stores Json-formated documents.  It stores, analyzes, performs correlation on the data

## Logstash

Logstash is a data processing engine used to take the data from different sources, apply the filter on it or normalize it, and then send it to the destination which could be Kibana or a listening port.

* Input -> Source
* Filter -> options to normalize the logs
* output -> where the user wants the filtered data to send

## Beats

Is used to ship/transfer data from the endpoints to elasticsearch

## Kibana

Analysis and Visualization

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/ec4f681a412aa825b284523dcd5b8650.png" alt=""><figcaption></figcaption></figure>

* Beats is a set of different data shipping agents used to collect data from multiple agents. Like Winlogbeat is used to collect windows event logs, Packetbeat collects network traffic flows.
* Logstash collects data from beats, ports or files, etc., parses/normalizes it into field value pairs, and stores them into elasticsearch.
* Elasticsearch acts as a database used to search and analyze the data.
* Kibana is responsible for displaying and visualizing the data stored in elasticsearch. The data stored in elasticseach can easily be shaped into different visualizations, time charts, infographics, etc., using Kibana.
