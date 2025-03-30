FROM php:8.2-apache

RUN usermod -u 1000 www-data

RUN docker-php-ext-install mysqli pdo pdo_mysql

RUN mkdir -p /var/log/apache2 && chown -R www-data:www-data /var/log/apache2

EXPOSE 80
