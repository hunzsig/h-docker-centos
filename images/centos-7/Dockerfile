
FROM centos:7

ENV container docker

RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == \
systemd-tmpfiles-setup.service ] || rm -f $i; done); \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;
VOLUME [ "/sys/fs/cgroup" ]
CMD ["/usr/sbin/init"]

RUN yum -y update

RUN yum -y install wget
RUN yum -y install curl
RUN yum -y install net-tools
RUN yum -y install git
RUN yum -y install vim

RUN modinfo tun
RUN modprobe tun
RUN lsmid | grep tun

RUN echo -e "[nux-misc]\nname=Nux Misc\nbaseurl=http://li.nux.ro/download/nux/misc/el7/x86_64/\nenabled=0\ngpgcheck=1\ngpgkey=http://li.nux.ro/download/nux/RPM-GPG-KEY-nux.ro" >> /etc/yum.repos.d/nux-misc.repo
RUN yum -y --enablerepo=nux-misc install tunctl
RUN tunctl -t enp2s0
RUN ifconfig enp2s0 down
RUN ifconfig enp2s0 hw ether 0c:9d:92:c8:cf:04
RUN ifconfig enp2s0 up

# 镜像信息
LABEL Author="hunzsig-centos-7"
LABEL Version="2021.02"
LABEL Description="centos-7"