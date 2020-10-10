FROM php:7.2-fpm
WORKDIR "/var/www"

ARG PUID=1000
ENV PUID ${PUID}
ARG PGID=1000
ENV PGID ${PGID}
RUN groupadd -g ${PGID} dev && \
useradd -u ${PUID} -g dev -m dev && \
usermod -p "*" dev


RUN ldconfig

RUN apt-get update && apt install -y openssl bash libxml2-dev postgresql-client libpq-dev libpng-dev libaio1

RUN docker-php-ext-install zip

RUN docker-php-ext-install pdo pdo_mysql pdo_pgsql soap gd

RUN docker-php-ext-install exif

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash

RUN apt-get update && apt-get install -y nodejs && apt-get clean

RUN apt-get update && apt-get install -y git

RUN apt-get update && apt-get install -y nano

RUN apt-get update && apt-get install -y net-tools

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN rm -rf /var/www/html

RUN apt-get update && apt-get install -y libxrender-dev libfontconfig

COPY ./php-ini-overrides.ini /usr/local/etc/php/conf.d

