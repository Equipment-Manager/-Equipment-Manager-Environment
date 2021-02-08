FROM php:8.0.2-fpm-alpine

ARG COMPOSER_VERSION
ENV COMPOSER_HOME=/application/.composer
ENV COMPOSER_MEMORY_LIMIT=-1



RUN apk update && apk upgrade \
    && apk add --no-cache zip libzip-dev libpng-dev git \
    && curl -sS https://getcomposer.org/installer | php -- --version=${COMPOSER_VERSION} --install-dir=/usr/local/bin --filename=composer \
    && docker-php-ext-install mysqli pdo pdo_mysql bcmath zip gd \
    && docker-php-ext-configure zip
