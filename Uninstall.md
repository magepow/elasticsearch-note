## Elasticsearch Uninstall

https://www.kevinleary.net/blog/uninstalling-elasticsearch/

```

curl -XPOST https://localhost:9200/_cluster/nodes/_shutdown
killall -KILL elas
sudo service elasticsearch stop
rpm -e elasticsearch
sudo yum remove elasticsearch
sudo rm -rf /var/lib/elasticsearch/
sudo rm -rf /etc/elasticsearch

```