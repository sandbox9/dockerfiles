FROM leehanwool/cent7-jdk7

#Use LTS Version
ENV SONAR_VERSION 4.5.4

RUN yum -y update

RUN yum -y install wget unzip

RUN mkdir -p /applications

WORKDIR /applications

RUN wget -q http://dist.sonar.codehaus.org/sonarqube-$SONAR_VERSION.zip && \
    unzip sonarqube-$SONAR_VERSION.zip

RUN yum remove -y wget unzip

RUN rm -rf /applications/sonarqube-$SONAR_VERSION/conf/sonar.properties

ADD sonar.properties /applications/sonarqube-$SONAR_VERSION/conf/

EXPOSE 9000

VOLUME /applications/sonarqube-$SONAR_VERSION/extensions
VOLUME /applications/sonarqube-$SONAR_VERSION/logs
VOLUME /applications/sonarqube-$SONAR_VERSION/conf

WORKDIR /applications/sonarqube-$SONAR_VERSION/bin/linux-x86-64/
CMD sh sonar.sh console
