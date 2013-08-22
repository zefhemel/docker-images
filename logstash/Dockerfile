FROM ubuntu
MAINTAINER Zef Hemel
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get install -y wget openjdk-7-jre-headless redis-server supervisor rubygems
RUN cd /opt && wget --no-check-certificate https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-0.20.6.tar.gz && tar xzf elasticsearch-*.tar.gz && rm *.tar.gz && mv elasticsearch-* elasticsearch
RUN cd /opt && wget http://logstash.objects.dreamhost.com/release/logstash-1.1.13-flatjar.jar && mv logstash-* logstash.jar
RUN cd /opt && wget --no-check-certificate https://github.com/rashidkpc/Kibana/archive/v0.2.0.tar.gz && tar xzf v0.2.0.tar.gz && rm v0.2.0.tar.gz && mv Kibana-* kibana
RUN cd /opt/kibana && gem install bundler && bundle install
ADD supervisord.conf /etc/supervisord.conf
ADD indexer.conf /etc/indexer.conf
ADD KibanaConfig.rb /opt/kibana/KibanaConfig.rb
EXPOSE 6379 5601
CMD ["supervisord", "-c", "/etc/supervisord.conf", "-n"]
