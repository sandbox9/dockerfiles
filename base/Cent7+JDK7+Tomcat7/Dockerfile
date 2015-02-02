FROM leehanwool/cent7-jdk7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

ENV CATALINA_HOME /applications/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
ENV TOMCAT_MAJOR_VERSION 7
ENV TOMCAT_VERSION 7.0.57
ENV TOMCAT_TGZ_URL http://mirror.apache-kr.org/tomcat/tomcat-$TOMCAT_MAJOR_VERSION/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz

RUN yum install -y net-tools wget tar

RUN mkdir /applications

WORKDIR /applications

# INSTALL TOMCAT
RUN wget -q $TOMCAT_TGZ_URL

RUN tar xvf apache-tomcat-$TOMCAT_VERSION.tar.gz

RUN mv apache-tomcat-$TOMCAT_VERSION tomcat

RUN rm -rf apache-tomcat-$TOMCAT_VERSION.tar.gz

EXPOSE 8080