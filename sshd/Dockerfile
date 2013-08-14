FROM ubuntu
MAINTAINER Zef Hemel
RUN apt-get update
RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo "root:root" | chpasswd
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
