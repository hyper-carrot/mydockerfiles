#
# My Dockerfile - Golang project
#
# https://github.com/hyper-carrot/mydockerfiles/golang
#
FROM ubuntu:14.04.2
MAINTAINER Robert Hao <hypermind.cn@gmail.com>

# Set timestamp
ENV REFRESHED_AT 2015-07-02

# Install base tools
RUN \
  apt-get install -yqq software-properties-common && \
  apt-get update -yqq && \
  apt-get install -yqq git mercurial curl tar gzip vim

# Install Golang
ENV GOROOT /usr/local/go 
#ENV DOWNLOAD_URL https://storage.googleapis.com/golang/go1.4.2.linux-amd64.tar.gz
ENV DOWNLOAD_URL http://golangtc.com/static/go/go1.4.2.linux-amd64.tar.gz

RUN \
  mkdir -p /usr/local/go && \
  curl `echo $DOWNLOAD_URL` | tar xvzf - -C `echo $GOROOT` --strip-components=1

# Set enviroment for Golang
ENV WORK_BASE /opt
ENV LIB_DIR $WORK_BASE/golib
ENV PROJECT_DIR $WORK_BASE/goproject
ENV GOPATH $LIB_DIR:$PROJECT_DIR
ENV GOBIN  $WORK_BASE/gobin 
ENV PATH   $GOROOT/bin:$GOBIN:$PATH

RUN \
  mkdir -p $LIB_DIR/src && \
  mkdir -p $PROJECT_DIR/src && \
  mkdir $GOBIN

VOLUME ["$PROJECT_DIR"]

# Download & set golang tools
RUN \
  mkdir $LIB_DIR/src/golang.org && \
  curl http://golangtc.com/static/download/packages/golang.org.x.tools.tar.gz | tar xvzf - -C $LIB_DIR/src/golang.org --strip-components=1

# Set localtime
RUN \
  mkdir /etc/sysconfig && \
  echo -e "ZONE=Asia/Shanghai\nUTC=false\nARC=false" >> /etc/sysconfig/clock && \ 
  rm /etc/localtime && \
  ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

# Set work dir 
WORKDIR $WORK_BASE

# Set command:
CMD ["go", "version"]
