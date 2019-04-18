FROM alpine:latest
LABEL maintainer "Dorian Colnot dcolnot@w4rppy.net"

RUN mkdir /build
RUN apk update && \
    apk add --no-cache \
    curl \
    bash \
    py-pip \
    zip \
    ansible
#PACKER
RUN curl -O https://releases.hashicorp.com/packer/1.4.0/packer_1.4.0_linux_amd64.zip && \
    unzip packer_1.3.2_linux_amd64.zip && mv packer /usr/local/bin/ && \
    rm packer*
#PLUGINS
RUN curl -L https://github.com/jetbrains-infra/packer-builder-vsphere/releases/download/v2.3/packer-builder-vsphere-clone.linux > packer-builder-vsphere-clone.linux && \
    mkdir -p ~/.packer.d/plugins/ && \
    chmod +x packer-builder-vsphere-clone.linux && \
    mv packer-builder-vsphere-clone.linux ~/.packer.d/plugins/

ENV HOME /build
WORKDIR $HOME

ENTRYPOINT [ "bash"]
