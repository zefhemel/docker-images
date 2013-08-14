FROM zefhemel/sshd
MAINTAINER Zef Hemel
RUN apt-get install -y tmux irssi
ADD bashrc /root/.bashrc
CMD /usr/sbin/sshd -D
