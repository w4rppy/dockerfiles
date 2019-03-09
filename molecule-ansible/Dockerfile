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
          make \
          bash \
          docker \
          && pip install ansible molecule docker

ENV HOME /root

WORKDIR $HOME
