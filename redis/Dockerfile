# Hypermind2 Dockerfile
FROM centos:latest
MAINTAINER Robert Hao <hypermind.cn@gmail.com>

# Set timestamp
ENV REFRESHED_AT 2015-01-21

# Yum
RUN yum -q -y upgrade

# Install base tools
RUN yum -q -y install tar
RUN yum -q -y install gzip
RUN yum -q -y install vim

# Redis
RUN yum -y update; yum clean all
RUN yum -y install epel-release; yum clean all
RUN yum -y install redis; yum clean all

RUN \ 
  mkdir -p /opt/logs/ && \
  mkdir -p /opt/backup/redis

VOLUME ["/opt/conf"]
EXPOSE 6379

ENTRYPOINT  ["/usr/bin/redis-server"]
CMD ["--help"]




