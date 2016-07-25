FROM local:systemd

MAINTAINER Ian Ellis

RUN yum install -y http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-7.noarch.rpm \
 && yum install -y sudo \
 && yum install -y salt-minion \
 && systemctl enable salt-minion

COPY grains /etc/salt/grains

CMD ["/usr/sbin/init"]
