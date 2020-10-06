FROM phpdockerio/php73-fpm:latest
WORKDIR "/var/www"

ARG PUID=1000
ENV PUID ${PUID}
ARG PGID=1000
ENV PGID ${PGID}
RUN groupadd -g ${PGID} dev && \
useradd -u ${PUID} -g dev -m dev && \
usermod -p "*" dev

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash

RUN apt-get update && apt-get install -y nodejs && apt-get clean

RUN apt-get update && apt-get install -y git

RUN apt-get update && apt-get install -y nano

RUN apt-get update && apt-get install -y net-tools


# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install  php7.3-mysql php7.3-pgsql \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*