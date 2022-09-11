FROM daocloud.io/library/centos:centos7.8.2003
ENV MYPATH /
WORKDIR $MYPATH
ADD CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo
RUN sed -i -e '/mirrors.cloud.aliyuncs.com/d' -e '/mirrors.aliyuncs.com/d' /etc/yum.repos.d/CentOS-Base.repo
RUN yum clean all
RUN yum makecache
RUN yum install net-tools -y
CMD systemctl stop firewalld
CMD systemctl disable firewalld
CMD sudo sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config && setenforce 0 
RUN yum install -y vim wget git
RUN yum -y install gcc gcc-c++ make gd-devel libxml2-devel libcurl-devel libjpeg-devel libpng-devel openssl-devel bison flex
RUN yum install tcpdump -y
ENV TZ=Asia/Shanghai
ADD apache-skywalking-apm-es7-8.5.0.tar.gz /
RUN cd /
RUN pwd && ls
#RUN tar -zxvf apache-skywalking-apm-es7-8.5.0.tar.gz 
RUN mv apache-skywalking-apm-bin-es7 skywalking
RUN mv skywalking/agent/optional-plugins/apm-trace-ignore-plugin* skywalking/agent/plugins/ 
RUN mkdir -p /usr/skywalking/
RUN mv /skywalking/agent /usr/skywalking/
RUN cd /usr/skywalking/agent && ls
MAINTAINER app
ENV LANG=C.UTF-8
EXPOSE 22