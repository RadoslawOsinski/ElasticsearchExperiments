0. Optional: remove existing tag
docker rm elasticsearch_tests;

1. Build postgres image in docker
docker build -t elasticsearch_tests .

2. Run image with published ports
#docker run -d -p 9200:9200 -p 9300:9300 -v <data-dir>:/data dockerfile/elasticsearch /elasticsearch/bin/elasticsearch -Des.config=/data/elasticsearch.yml
docker run -d -p 9200:9200 -p 9300:9300 elasticsearch_tests -Des.config=/data/elasticsearch.yml
