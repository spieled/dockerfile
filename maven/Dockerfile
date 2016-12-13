FROM daocloud.io/liushaoping/oracle-java:latest

MAINTAINER Shaoping Liu <spieled916@gmail.com>

ENV MAVEN_VERSION 3.3.9
ENV MAVEN_HOME /usr/lib/maven
ENV PATH /usr/lib/maven/bin:$JAVA_HOME/bin:$PATH

RUN apk --no-cache add --virtual build-dependencies wget && \
    cd /tmp && \
    wget -q http://archive.apache.org/dist/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz -O - | tar xzf - && \
    mv /tmp/apache-maven-$MAVEN_VERSION /usr/lib/maven && \
    ln -s /usr/lib/maven/bin/mvn /usr/bin/mvn && \
    rm -rf /tmp/* && \
    apk del --purge build-dependencies

CMD ["mvn", "--version"]