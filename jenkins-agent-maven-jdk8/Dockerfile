FROM jenkins/agent:latest-jdk8

ARG MVN_URL=https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.5.2/apache-maven-3.5.2-bin.tar.gz

USER root

RUN apt update && apt install -y curl \
  && mkdir -p /usr/share/maven /usr/share/maven/ref \
  && echo "Downloading maven" \
  && curl -fsSL -o /tmp/apache-maven.tar.gz ${MVN_URL} \
  \
  && echo "Unziping maven" \
  && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1 \
  \
  && echo "Cleaning and setting links" \
  && rm -f /tmp/apache-maven.tar.gz \
  && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
