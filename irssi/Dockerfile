FROM ubuntu
MAINTAINER Zef Hemel
RUN apt-get update
RUN apt-get install -y tmux irssi openssh-server
RUN mkdir /var/run/sshd
RUN echo "root:irc" | chpasswd
ADD bashrc /root/.bashrc
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
#CMD ["irssi"]
