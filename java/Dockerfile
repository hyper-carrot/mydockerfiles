#
# My Dockerfile - Java7(JDK7)
#
# https://github.com/hyper-carrot/mydockerfiles/java
#
 
FROM centos:latest
MAINTAINER Robert Hao <hypermind.cn@gmail.com>

# Set timestamp
ENV REFRESHED_AT 2015-01-19

# Update them
RUN  yum -q -y upgrade

# Install base tools
RUN yum -q -y install wget
RUN yum -q -y install tar
RUN yum -q -y install gzip

# Install Java7
RUN \
  mkdir -p /jdk1.7.0 && \
  wget -qO- --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/7u72-b14/jdk-7u72-linux-x64.tar.gz | tar xvzf - -C /jdk1.7.0 --strip-components=1
# Set environment variables.
ENV JAVA_HOME /jdk1.7.0
ENV CLASSPATH .:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH ${JAVA_HOME}/bin:$PATH

# Define working directory.
RUN \
  mkdir -p /opt/apps && \
  mkdir -p /opt/scripts && \
  mkdir -p /opt/conf && \
  mkdir -p /opt/logs
WORKDIR /opt

# Define default command.
CMD ["bash"]

