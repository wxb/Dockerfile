#+++++++++++++++++++++++++++++++++++++++
# Dockerfile for webdevops/php-dev:ubuntu-15.10
#    -- automatically generated  --
#+++++++++++++++++++++++++++++++++++++++

FROM webdevops/php:ubuntu-15.10

MAINTAINER info@webdevops.io
LABEL vendor=WebDevOps.io
LABEL io.webdevops.layout=8
LABEL io.webdevops.version=0.53.0

COPY conf/ /opt/docker/

# Install development environment
RUN wget -O - https://packagecloud.io/gpg.key | apt-key add - \
    && echo "deb https://packages.blackfire.io/debian any main" | tee /etc/apt/sources.list.d/blackfire.list \
    && /usr/local/bin/apt-install \
        # Install tools
        graphviz \
        # Install php development stuff
        php5-xdebug \
        blackfire-php \
    && /opt/docker/bin/provision run --tag bootstrap --role webdevops-php-dev \
    && /opt/docker/bin/bootstrap.sh

