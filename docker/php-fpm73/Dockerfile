FROM php:7.3.6-fpm-alpine

ADD php.ini /usr/local/etc/php/conf.d/php.ini

RUN apk --update add libmemcached-dev autoconf zlib-dev build-base \
    && pecl install memcached-3.1.3 \
    && docker-php-ext-install pdo_mysql mysqli mbstring \
    && docker-php-ext-enable memcached opcache mbstring \
    && rm -rf /var/cache/apk/*