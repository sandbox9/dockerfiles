FROM centos:centos7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

RUN yum -y install wget && \
    wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/7u72-b14/jdk-7u72-linux-x64.rpm && \
    echo "c55acf3c04e149c0b91f57758f6b63ce  jdk-7u72-linux-x64.rpm" >> MD5SUM && \
    md5sum -c MD5SUM && \
    rpm -Uvh jdk-7u72-linux-x64.rpm && \
    yum -y remove wget && \
    rm -f jdk-7u72-linux-x64.rpm MD5SUM