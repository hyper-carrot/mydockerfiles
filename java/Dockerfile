#
# My Dockerfile - Java7(JDK7)
#
# https://github.com/hyper-carrot/mydockerfiles/java
#
FROM centos:latest
MAINTAINER Robert Hao <hypermind.cn@gmail.com>

# Set timestamp
ENV REFRESHED_AT 2015-01-23

# Update them
RUN  yum -q -y upgrade

# Install base tools
RUN yum -q -y install wget
RUN yum -q -y install tar
RUN yum -q -y install gzip

# Install Java7
ENV JAVA_HOME /jdk1.7.0
RUN \
  mkdir -p $JAVA_HOME && \
  wget -qO- --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u40-b26/jdk-8u40-linux-x64.tar.gz | tar xvzf - -C $JAVA_HOME --strip-components=1

# Set environment
ENV CLASSPATH .:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $JAVA_HOME/bin:$PATH
ENV PROJECT_DIR /projects
RUN mkdir -p $PROJECT_DIR 
VOLUME ["$PROJECT_DIR"]

# Define work dir 
WORKDIR $PROJECT_DIR

# Define command
ENTRYPOINT  [""]
CMD ["java", "-version"]

