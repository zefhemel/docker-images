FROM ubuntu
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y openjdk-6-jdk curl unzip rlwrap
RUN cd /opt && curl -O http://repo1.maven.org/maven2/org/clojure/clojure/1.5.1/clojure-1.5.1.zip && unzip clojure-1.5.1.zip
CMD rlwrap java -jar /opt/clojure-1.5.1/clojure-1.5.1.jar
