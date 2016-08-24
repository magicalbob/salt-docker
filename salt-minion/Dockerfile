FROM centos:7

MAINTAINER Ian Ellis

ENV container docker
RUN yum -y update                                                                              \
 && yum -y install systemd                                                                     \
 && cd /lib/systemd/system/sysinit.target.wants/                                               \
 && for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done                  \
 && rm -f /lib/systemd/system/multi-user.target.wants/*                                        \
 && rm -f /etc/systemd/system/*.wants/*                                                        \
 && rm -f /lib/systemd/system/local-fs.target.wants/*                                          \
 && rm -f /lib/systemd/system/sockets.target.wants/*udev*                                      \
 && rm -f /lib/systemd/system/sockets.target.wants/*initctl*                                   \
 && rm -f /lib/systemd/system/basic.target.wants/*                                             \
 && rm -f /lib/systemd/system/anaconda.target.wants/*                                          \
 && yum install -y iptables openssh-server sudo                                                \
 && yum install -y http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-8.noarch.rpm \
 && yum install -y salt-minion                                                                 \      
 && systemctl enable salt-minion                                                               \      
 && yum clean all

VOLUME [ "/sys/fs/cgroup" ]

CMD ["/usr/sbin/init"]
