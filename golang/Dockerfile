#
# My Dockerfile - Golang project
#
# https://github.com/hyper-carrot/mydockerfiles/golang
#
FROM centos:latest
MAINTAINER Robert Hao <hypermind.cn@gmail.com>

# Set timestamp
ENV REFRESHED_AT 2015-01-19

# Yum update
RUN  yum -q -y upgrade

# Install base tools
RUN yum -q -y install tar
RUN yum -q -y install gzip

# Install Golang1.4.1
RUN \
  mkdir -p /go && \
  curl https://storage.googleapis.com/golang/go1.4.1.linux-amd64.tar.gz | tar xvzf - -C /go --strip-components=1

# Set environment
ENV PROJECT_DIR /projects/golang
RUN \
  mkdir -p /golib/src && \
  mkdir -p $PROJECT_DIR/src && \
  mkdir -p /gobin
VOLUME ["$PROJECT_DIR"]
ENV GOROOT /go
ENV GOPATH /golib:$PROJECT_DIR
ENV GOBIN /gobin
ENV PATH $GOROOT/bin:$GOBIN:$PATH

# Set work dir 
WORKDIR $PROJECT_DIR/src

# Set command:
ENTRYPOINT  [""]
CMD ["go", "version"]
