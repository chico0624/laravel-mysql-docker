FROM php:8.0-apache

# mod rewrite　を有効化
RUN  a2enmod rewrite

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
RUN apt-get update && apt-get install -y \
    git \
    vim \
    && docker-php-ext-install pdo_mysql

COPY ./docker/php/000-default.conf /etc/apache2/sites-available/000-default.conf
# RUN sed -i 's!/var/www/html!/var/www/app/public!g' /etc/apache2/sites-available/000-default.conf