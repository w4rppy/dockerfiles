FROM alpine:3.9
LABEL maintainer "Dorian Colnot dcolnot@w4rppy.net"

RUN apk --no-cache --update add \
          iproute2 \
          libffi-dev \
          openssl-dev \
          python \
          py-crypto \
          python2-dev \
          py-netaddr \
          py-pip \
          gcc \
          git \
          linux-headers \
          musl-dev \
          curl \
          make \
          bash \
          docker \
       && pip install ansible molecule docker \
       && curl -L https://github.com/aelsabbahy/goss/releases/download/v0.3.6/goss-linux-amd64 -o /usr/local/bin/goss \
       && chmod +rx /usr/local/bin/goss

ENV HOME /root

WORKDIR $HOME

