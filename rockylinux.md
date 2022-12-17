## Elasticsearch on Rockylinux note

### Docs
* [Elasticsearch Install](https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html)
* [Elasticsearch 7.17.0 on Centos 8 or RockyLinux](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-elasticsearch-on-centos-8)

```
sudo dnf install java-1.8.0-openjdk.x86_64 -y
sudo rpm -ivh https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.17.0-x86_64.rpm
sudo systemctl daemon-reload && sudo systemctl enable elasticsearch.service
sudo systemctl start elasticsearch.service

curl -X GET 'http://localhost:9200'

```

### Awesome Tutorial: