#+++++++++++++++++++++++++++++++++++++++
# Dockerfile for webdevops/base-app:centos-7
#    -- automatically generated  --
#+++++++++++++++++++++++++++++++++++++++

FROM webdevops/base:centos-7

MAINTAINER info@webdevops.io
LABEL vendor=WebDevOps.io
LABEL io.webdevops.layout=8
LABEL io.webdevops.version=0.53.0

ENV APPLICATION_USER  application
ENV APPLICATION_GROUP application
ENV APPLICATION_PATH  /app
ENV APPLICATION_UID   1000
ENV APPLICATION_GID   1000

COPY conf/ /opt/docker/

# Install services
RUN /usr/local/bin/yum-install \
        openssh-server \
        mysql \
        sqlite \
        dnsmasq \
        postfix \
        # Install tools
        sudo \
        zip \
        unzip \
        bzip2 \
        wget \
        curl \
        net-tools \
        moreutils \
        dnsutils \
        bind-utils \
        rsync \
        git \
        pygpgme \
        nano \
        vim \
    && /usr/local/bin/generate-locales \
    && /opt/docker/bin/provision run --tag bootstrap --role webdevops-base-app \
    && /opt/docker/bin/bootstrap.sh

