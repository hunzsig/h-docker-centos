FROM ubuntu:18

ARG DEBIAN_FRONTEND=noninteractive

RUN sed -i s@/archive.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list
RUN apt-get clean

RUN apt-get update
RUN apt-get -y install sudo
RUN apt-get -y install dialog
RUN apt-get -y install apt-utils
RUN apt-get -y install vim
RUN apt-get -y install net-tools
RUN apt-get -y install git
RUN apt-get -y install curl
RUN apt-get -y install wget

# 镜像信息
LABEL Author="hunzsig-ubuntu-18"
LABEL Version="2021.02"
LABEL Description="ubuntu-18"