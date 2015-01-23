#
# My Dockerfile - Java7(JDK7)+Tomcat7
#
# https://github.com/hyper-carrot/mydockerfiles/java/tomcat
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
  wget -qO- --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/7u72-b14/jdk-7u72-linux-x64.tar.gz | tar xvzf - -C $JAVA_HOME --strip-components=1

# Install Tomcat7
ENV CATALINA_HOME /apache-tomcat-7.0 
RUN \
  mkdir -p ${CATALINA_HOME} && \
  wget -qO- http://mirrors.hust.edu.cn/apache/tomcat/tomcat-7/v7.0.57/bin/apache-tomcat-7.0.57.tar.gz | tar xvzf - -C $CATALINA_HOME --strip-components=1

# Set environment
ENV CLASSPATH .:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH ${JAVA_HOME}/bin:$PATH
ENV CATALINA_OPTS -Xms512m -Xmx2048m -XX:PermSize=256m -XX:MaxPermSize=512m 

# Define work dir
WORKDIR ${CATALINA_HOME}

# Define command.
ENTRYPOINT ["bin/catalina.sh", "run"]

