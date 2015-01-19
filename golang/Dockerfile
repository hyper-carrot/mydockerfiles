#
# My Dockerfile - Golang
#
# https://github.com/hyper-carrot/mydockerfiles/golang
#
 
FROM centos:latest
MAINTAINER Robert Hao <hypermind.cn@gmail.com>

# Set timestamp
ENV REFRESHED_AT 2015-01-19

# Update them
RUN  yum -q -y upgrade

# Install base tools
RUN yum -q -y install tar
RUN yum -q -y install gzip

# Install Golang1.4.1
RUN \
  mkdir -p /go && \
  curl https://storage.googleapis.com/golang/go1.4.1.linux-amd64.tar.gz | tar xvzf - -C /go --strip-components=1

# Set environment variables.
RUN \
  mkdir -p /golib && \
  mkdir -p /projects/golang && \
  mkdir -p /gobin
ENV GOROOT /go
ENV GOPATH /golib:/projects/golang
ENV GOBIN /gobin
ENV PATH $GOROOT/bin:$GOBIN:$PATH

# Define working directory.
WORKDIR /projects/golang

# Define default command.
CMD ["bash"]

