FROM svenruppert-docker-local-svenruppert.jfrog.io/svenruppert/adopt:1.8.0-172
MAINTAINER sven.ruppert@gmail.com

ARG USER_HOME_DIR="/root"
ENV MAVEN_BINARY_URL  http://apache.hippo.nl/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
#ENV MAVEN_BINARY_URL  https://svenruppert.jfrog.io/artifactory/generic-local-maven/apache-maven-3.6.3-bin.tar.gz

RUN mkdir -p /usr/share/maven /usr/share/maven/ref \
  && curl -o /tmp/apache-maven.tar.gz \ $MAVEN_BINARY_URL \
  && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1 \
  && rm -f /tmp/apache-maven.tar.gz \
  && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn

ENV MAVEN_HOME /usr/share/maven
ENV MAVEN_CONFIG "$USER_HOME_DIR/.m2"

CMD ["mvn"]