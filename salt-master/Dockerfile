FROM lab-registry.3cbeta.co.uk:5000/redhat7:7.2

MAINTAINER Ian Ellis

RUN yum install -y http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-7.noarch.rpm \
 && yum install -y salt-master

EXPOSE 5405 5406

ENTRYPOINT /usr/bin/salt-master
