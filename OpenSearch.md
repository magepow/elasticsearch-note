## OpenSearch 2.5

https://opensearch.org/docs/2.5/install-and-configure/install-opensearch/rpm/

```
sudo yum install opensearch-2.5.0-linux-x64.rpm

sudo curl -SL https://artifacts.opensearch.org/releases/bundle/opensearch/2.x/opensearch-2.x.repo -o /etc/yum.repos.d/opensearch-2.x.repo

# List version
sudo yum list opensearch --showduplicates

# Latest version
sudo yum install opensearch


# Special version
sudo yum install 'opensearch-2.5.0'

sudo systemctl start opensearch
sudo systemctl status opensearch

sudo systemctl edit opensearch.service
#  Now, add the following lines in the unit file.
[Service]
Restart=always

sudo systemctl daemon-reload
sudo systemctl cat opensearch.service

curl -X GET https://localhost:9200 -u 'admin:admin' --insecure
curl -X GET https://localhost:9200/_cat/plugins?v -u 'admin:admin' --insecure

sudo vi /etc/opensearch/opensearch.yml

```


https://stackoverflow.com/questions/52624720/how-to-auto-restart-elasticsearch-search-once-crashed-on-linux-server

Step to Auto restart elasticsearch services after crash or down:
1) Edit elasticsearch service unit file using the following command

sudo systemctl edit elasticsearch.service 
This command will create a file

/etc/systemd/system/elasticsearch.service.d/override.conf
2) Now, add the following lines in the unit file.

[Service]
Restart=always
3) Save the file .

ctrl+x  > Y > Enter
4) Refresh the unit file using command

sudo systemctl daemon-reload
5) Can check the changes using command

sudo systemctl cat elasticsearch.service