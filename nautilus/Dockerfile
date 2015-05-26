FROM leehanwool/cent7-jdk7-tomcat7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

WORKDIR /applications/

# Download war image from Nexus
RUN curl --user admin:admin00 "http://1.223.129.52:8081/nexus/service/local/artifact/maven/redirect?r=snapshots&g=fury.merkava&a=merkava-nautilus&v=1.0-SNAPSHOT&p=war" -o nautilus.war -L

RUN mv nautilus.war /applications/tomcat/webapps

EXPOSE 8080

WORKDIR /applications/tomcat/bin/

ENV JAVA_OPTS=-Dspring.profiles.active=docker

CMD sh catalina.sh run