FROM php:7.4-fpm-alpine

RUN apk upgrade --update \
    && apk --update add --no-cache --virtual .phpize-deps $PHPIZE_DEPS imagemagick-dev libtool \
    && pecl install imagick \
    && docker-php-ext-configure exif \
    && docker-php-ext-install -j$(nproc) mysqli exif pdo pdo_mysql \
    && docker-php-ext-enable imagick \
    && docker-php-ext-enable exif \
    && apk add --no-cache --virtual .imagick-runtime-deps imagemagick \
    && apk del .phpize-deps

WORKDIR /var/www/html
