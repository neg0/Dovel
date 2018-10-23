FROM php:7.2-fpm

LABEL maintainer = "Hadi T"

RUN echo "Updating and Installting required binary packages" \
    && apt-get update -y && apt-get install -y \
    apt-utils \
    git \
    zip \
    unzip \
    libssl-ocaml \
    libbz2-dev \
    libzip-dev \
    openssl \
    libxml2-dev \
    && docker-php-ext-install bz2 \
    && docker-php-ext-install zip \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install soap \
    && docker-php-ext-configure zip --with-libzip=/usr/include/

RUN echo "Installing Xdebug Extension" \
    && pecl update-channels \
    && pecl install xdebug-2.7.0beta1
COPY php/xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

RUN echo "Installing latest version of Composer" \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && composer --version

RUN echo "Setting shared volumes and working directory" \
    && mkdir -p /usr/local/src
VOLUME /usr/local/src
WORKDIR /usr/local/src