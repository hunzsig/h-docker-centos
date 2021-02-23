
FROM ubuntu:18.04

ENV ACCEPT_EULA=Y

RUN sed -i "s@http://deb.debian.org@http://mirrors.aliyun.com@g" /etc/apt/sources.list
RUN rm -Rf /var/lib/apt/lists/*
RUN apt-get update

RUN apt-get -y install apt-utils
RUN apt-get -y install wget
RUN apt-get -y install curl
RUN apt-get -y install net-tools
RUN apt-get -y install git
RUN apt-get -y install vim

# 镜像信息
LABEL Author="hunzsig-ubuntu-18"
LABEL Version="2021.02"
LABEL Description="ubuntu-18"