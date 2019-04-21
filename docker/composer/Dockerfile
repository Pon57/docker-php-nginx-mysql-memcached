FROM php:fpm

RUN apt-get update \
    && apt-get install -y zlib1g-dev libzip-dev \
    && docker-php-ext-install zip pdo_mysql

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
ENV COMPOSER_ALLOW_SUPERUSER 1

# install git
RUN apt-get update \
  && apt-get install -y git

# If you want to install global command
# For example
## install drush8
RUN composer global require drush/drush:8.*
RUN export PATH="$PATH:$HOME/.composer/vendor/bin" \
  && echo 'export PATH="$PATH:$HOME/.composer/vendor/bin"' >> ~/.bashrc \
  && . ~/.bashrc 