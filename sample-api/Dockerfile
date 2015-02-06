FROM leehanwool/cent7-jdk7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

WORKDIR /applications/
# Download war image from Nexus
RUN curl --user admin:admin00 "http://1.223.129.52:8081/nexus/service/local/artifact/maven/redirect?r=snapshots&g=org.springframework.boot&a=sample-api&v=0.0.1-SNAPSHOT&p=jar" -o api.jar -L

EXPOSE 10001

CMD java -jar api.jar