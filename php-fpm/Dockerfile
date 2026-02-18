FROM php:8.5-fpm

WORKDIR /var/www/html/

ENV PHP_INI_DIR /usr/local/etc/php

RUN apt-get update && apt-get install -y \
    libzip-dev zip $PHPIZE_DEPS git

RUN pecl install xdebug
RUN docker-php-ext-install zip 
RUN docker-php-ext-enable xdebug

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# for git
# RUN git clone https://git.example.com/repo.git ز

# for composer
# WORKDIR /var/www/html/app/
# RUN composer install
# RUN composer update

ENV APP_ENV production
ENV APP_DEBUG true

LABEL maintainer="Mohammed Saleh <mohammed.saleh@tuta.io>"
LABEL version="1.0"
LABEL description="Docker image for PHP 8.5 FPM"

# laravel shit ig?
# RUN chmod -R 775 storage bootstrap/cache
# RUN chown -R www-data:www-data storage bootstrap/cache

# COPY ./php.ini-production /usr/local/etc/php-fpm.conf

COPY ./xdebug.ini /usr/local/etc/php/conf.d/xdeub.ini

EXPOSE 9000

CMD php-fpm