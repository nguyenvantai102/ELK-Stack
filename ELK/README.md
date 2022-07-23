<h1 align='center'> ✨ ELK Stacks ✨</h1>

- Requirements:
  - Java 11
  - Python 3

<h2 align="center">🛠 Tool 🛠</h2>

<strong> Elasticsearch </strong>

1. Download Elasticsearch

```
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-8.3.2-linux-x86_64.tar.gz
tar -xzf elasticsearch-8.3.2-linux-x86_64.tar.gz
```

<strong> Logstash </strong>

1. Download Logstash
```
wget https://artifacts.elastic.co/downloads/logstash/logstash-8.3.2-linux-x86_64.tar.gz
tar -xzf logstash-8.3.2-linux-x86_64.tar.gz
```

2. Edit the Logstash Configuration


```
nano config/logstash.yml

# Write into file
modules:
  - name: netflow
    var.input.udp.port: 9996
    var.elasticsearch.hosts: http://127.0.0.1:9200
    var.elasticsearch.ssl.enabled: false
    var.kibana.host: 127.0.0.1:5601
    var.kibana.scheme: http
    var.kibana.ssl.enabled: false
    var.kibana.ssl.verification_mode: disable
    
 ```

<strong> Kibana </strong>

1. Download Kibana

```
wget https://artifacts.elastic.co/downloads/kibana/kibana-8.3.2-linux-x86_64.tar.gz
tar -xzf kibana-8.3.2-linux-x86_64.tar.gz
```


<h2 align="center">🔥 Launching ELK Stacks 🔥</h2>

```
cd ~/elasticsearch-8.3.2-linux-x86_64/
bin/elasticsearch
cd ~/kibana-8.3.2-linux-x86_64/
bin/kibana
cd ~/logstash-8.3.2-linux-x86_64/
bin/logstash --modules netflow setup
```

<h2 align="center">🌱 Result 🌱</h2>

<p align="center"> <img src="https://user-images.githubusercontent.com/67199007/180600963-74105ff8-2661-47fc-a85e-7e39bafd2ab0.png"></p>
