FROM ubuntu
MAINTAINER Zef Hemel
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get install -y wget openjdk-7-jre-headless redis-server supervisor
RUN cd /opt && wget --no-check-certificate https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-0.20.6.tar.gz && tar xzf elasticsearch-*.tar.gz && rm *.tar.gz && mv elasticsearch-* elasticsearch
RUN cd /opt && wget http://logstash.objects.dreamhost.com/release/logstash-1.1.13-flatjar.jar && mv logstash-* logstash.jar
ADD supervisord.conf /etc/supervisord.conf
ADD indexer.conf /etc/indexer.conf
EXPOSE 9292 6379
CMD ["supervisord", "-c", "/etc/supervisord.conf", "-n"]
