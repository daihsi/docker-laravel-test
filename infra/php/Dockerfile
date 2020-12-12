FROM php:7.4-fpm
ENV COMPOSER_ALLOW_SUPERUSER=1 \
  COMPOSER_HOME=/composer
COPY --from=composer:1.10 /usr/bin/composer /usr/bin/composer
RUN apt-get update && \
  apt-get -y install git libzip-dev libicu-dev libonig-dev unzip && \
  docker-php-ext-install pdo_mysql zip
COPY ./php.ini /usr/local/etc/php/php.ini
WORKDIR /work