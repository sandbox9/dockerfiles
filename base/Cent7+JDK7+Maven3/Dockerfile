FROM leehanwool/cent7-jdk7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

VOLUME ["/src", "/.m2"]

ENV MAVEN_MAJOR 3
ENV MAVEN_VERSION 3.2.5

RUN yum install -y wget tar

RUN \
  wget http://mirror.apache-kr.org/maven/maven-$MAVEN_MAJOR/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz && \
  tar -xzf apache-maven-$MAVEN_VERSION-bin.tar.gz -C /usr/local && \
  mv /usr/local/apache-maven-$MAVEN_VERSION /usr/local/maven && \
  rm apache-maven-$MAVEN_VERSION-bin.tar.gz && \
  ln -s /usr/local/maven/bin/mvn /usr/local/bin/mvn && \
  ln -s /usr/local/maven/bin/mvnDebug /usr/local/bin/mvnDebug && \
  ln -s /.m2 ~/.m2
  
RUN yum remove -y wget tar