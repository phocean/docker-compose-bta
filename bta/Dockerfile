FROM ubuntu

MAINTAINER Phocean <jc@phocean.net>

WORKDIR /root

RUN apt-get update \
      && apt-get install -yq python-ldap python-dev python-pip libunac1-dev curl \
      && rm -rf /var/lib/apt/lists/* \
      && pip install bta \
      && curl -sSL -o libesedb-20170121.tar.gz https://github.com/libyal/libesedb/releases/download/20170121/libesedb-experimental-20170121.tar.gz \
      && echo "6b29b7e634953885c0716f144b278e7b2c64e9e3  libesedb-20170121.tar.gz" | sha1sum -c - \
      && tar -xf libesedb-20170121.tar.gz && cd libesedb-20170121 \
      && ./configure && make && make install \
      && apt-get -yq remove curl \
      && rm -rf /root/libesedb*

ENV LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH

VOLUME /data
WORKDIR /data

CMD ["/bin/bash"]
