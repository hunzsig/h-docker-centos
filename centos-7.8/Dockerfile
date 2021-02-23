
FROM centos7.8

ENV ACCEPT_EULA=Y

RUN yum install wget
RUN yum install curl

RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
RUN wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo
RUN yum clean all
RUN yum makecache
RUN yum update

RUN yum -y install git

# 镜像信息
LABEL Author="hunzsig-centos-7.8"
LABEL Version="2021.02"
LABEL Description="centos-7.8"