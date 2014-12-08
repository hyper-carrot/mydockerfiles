#
# My Dockerfile - golang
#
# https://github.com/hyper-carrot/dockerfile/golang
#
 
FROM centos:latest
MAINTAINER Robert Hao <hypermind.cn@gmail.com>

# Install base tools
RUN yum -q -y install tar
RUN yum -q -y install gzip

# Install Golang
RUN \
  mkdir -p /go && \
  curl https://storage.googleapis.com/golang/go1.3.3.linux-amd64.tar.gz | tar xvzf - -C /go --strip-components=1

# Set environment variables.
ENV GOROOT /go
ENV GOPATH /golib
ENV GOBIN /gobin
ENV PATH $GOROOT/bin:$GOPATH/bin:$GOBIN:$PATH

# Define working directory.
WORKDIR /gopath

# Define default command.
CMD ["bash"]

