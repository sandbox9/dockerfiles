FROM leehanwool/cent7-jdk7-tomcat7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

# docker JAVA profile
ENV JAVA_OPTS=-"-Dspring.profiles.active=dev -Djava.awt.headless=true -server -Xms512m -Xmx1024m -XX:NewSize=256m -XX:MaxNewSize=256m -XX:PermSize=256m -XX:MaxPermSize=256m -XX:+DisableExplicitGC"

WORKDIR /applications/

# Download war image from Nexus
RUN curl --user admin:admin123 "http://1.223.129.52:8081/nexus/service/local/artifact/maven/redirect?r=snapshots&g=fury.nautilus&a=nautilus-admin&v=1.0.0-SNAPSHOT&p=war" -o nautilus.war -L

RUN mv nautilus.war /applications/tomcat/webapps

EXPOSE 8080

WORKDIR /applications/tomcat/bin/

CMD sh catalina.sh run