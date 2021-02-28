FROM php:7.3-alpine

COPY .common /tmp

ENV COMPOSER_HOME /tmp/.composer

RUN apk add --update php
RUN /tmp/setup.sh

# PHP-GD
RUN apk add --update libgd libpng-dev
RUN docker-php-ext-configure gd && docker-php-ext-install gd
RUN apk add --update php

# PHP MBSTRING
RUN docker-php-ext-install mbstring

# PHP-JSON
RUN docker-php-ext-configure json && docker-php-ext-install json

# PHP-BCMATH
RUN docker-php-ext-configure bcmath && docker-php-ext-install bcmath

# PHP-ZIP
RUN apk add --update zlib-dev libzip-dev
RUN docker-php-ext-install zip


WORKDIR /var/app
ENTRYPOINT ["bash", "/tmp/entrypoint" ]
CMD [ "php", "-a" ]

#INSTALA AWS CLI
RUN apk add --no-cache \
        python3 \
        py3-pip \
    && pip3 install --upgrade pip \
    && pip3 install \
        awscli \
    && rm -rf /var/cache/apk/*

RUN aws --version
