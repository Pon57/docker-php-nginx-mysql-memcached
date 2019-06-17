FROM php:7.3.6-fpm-alpine

RUN apk --update add zlib-dev libzip-dev unzip git bash \
    && docker-php-ext-install zip pdo_mysql \
    && rm -rf /var/cache/apk/*

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
ENV COMPOSER_ALLOW_SUPERUSER 1

# set path for composer
RUN echo 'export PATH="$PATH:$HOME/.composer/vendor/bin"' >> ~/.bashrc \
    && . ~/.bashrc

# If you want to install global command
# For example
## install drush8
# RUN composer global require drush/drush:8.*