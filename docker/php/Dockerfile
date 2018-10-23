FROM php:7.2-fpm

LABEL maintainer = "Hadi T <hadi.tajallaei@prettylittlething.com"

RUN echo "Updating and Installting required binary packages:" \
    && apt-get update -y && apt-get install -y \
    git \
    zip \
    unzip \
    libssl-ocaml \
    libbz2-dev \
    libzip-dev \
    && docker-php-ext-install bz2 \
    && docker-php-ext-install zip \
    && docker-php-ext-install pdo_mysql

RUN echo "Installing xdebug" \
    && pecl update-channels \
    && pecl install xdebug-2.7.0beta1

RUN echo "Installing latest version of Composer" \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && composer --version

RUN echo "Setting shared volumes and working directory" \
    && mkdir -p /usr/local/src
VOLUME /usr/local/src
WORKDIR /usr/local/src