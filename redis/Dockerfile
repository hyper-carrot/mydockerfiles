#
# My Dockerfile - Redis server
#
# https://github.com/hyper-carrot/mydockerfiles/redis
#
FROM centos:latest
MAINTAINER Robert Hao <hypermind.cn@gmail.com>

# Set timestamp
ENV REFRESHED_AT 2015-01-21

# Yum update
RUN yum -q -y upgrade

# Install base tools
RUN yum -q -y install tar
RUN yum -q -y install gzip
RUN yum -q -y install vim

# Install Redis
RUN yum -y update; yum clean all
RUN yum -y install epel-release; yum clean all
RUN yum -y install redis; yum clean all

# Set environment
RUN \ 
  mkdir -p /opt/logs/ && \
  mkdir -p /opt/backup/redis
VOLUME ["/opt/conf"]
EXPOSE 6379

# Set command
ENTRYPOINT  ["/usr/bin/redis-server"]
CMD ["--help"]




