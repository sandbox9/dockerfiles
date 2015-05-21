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

EXPOSE 9000

WORKDIR /applications/sonarqube-$SONAR_VERSION/bin/linux-x86-64/
CMD ./sonar.sh start
