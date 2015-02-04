FROM leehanwool/cent7-jdk7-tomcat7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

# Download war image from Nexus
RUN curl --user admin:admin00 "http://1.223.129.52:8081/nexus/service/local/artifact/maven/redirect?r=releases&g=com.mycompany&a=api&v=1.0&p=war" -o api.war -L

RUN mv api.war /applications/tomcat/webapps/

WORKDIR /applications/tomcat/bin

EXPOSE 8080

CMD ["catalina.sh", "run"]