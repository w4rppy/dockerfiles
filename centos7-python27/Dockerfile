FROM centos:7
LABEL maintainer "Dorian Colnot dcolnot@w4rppy.net"

RUN yum makecache fast \
 && yum -y install epel-release \
 && yum -y update \
 && yum -y install \
      gcc \
      make \
      sudo \
      wget \
      which \
      iproute \
      bzip2-devel \
      openssl-devel \
      python-pip \
 && yum clean all \
 && pip install netaddr

WORKDIR /usr/src

RUN wget https://www.python.org/ftp/python/2.7.15/Python-2.7.15.tgz && \
    tar xzf Python-2.7.15.tgz && \
    cd /usr/src/Python-2.7.15 && \
    ./configure --enable-optimizations && \
    make altinstall && \
    cd /usr/src && \
    rm -rf /usr/src/Python-* && \
    curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py" && \
    /usr/local/bin/python2.7 get-pip.py

ENV HOME /root
WORKDIR $HOME

CMD ["/usr/lib/systemd/systemd"]

