## Update Elasticsearch on Centos7 note

PUT _cluster/settings{  "persistent": {    "cluster.routing.allocation.enable": "primaries"  }}

POST _flush/synced


systemctl stop elasticsearch


rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.17.3-x86_64.rpm
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.17.3-x86_64.rpm.sha512
shasum -a 512 -c elasticsearch-7.17.3-x86_64.rpm.sha512
rpm -U elasticsearch-7.17.3-x86_64.rpm

nano /usr/lib/tmpfiles.d/elasticsearch.conf

action.auto_create_index: "*"


systemctl daemon-reload

systemctl enable elasticsearch

systemctl start elasticsearch.service

PUT _cluster/settings{"persistent": {"cluster.routing.allocation.enable": null }}


