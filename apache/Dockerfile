FROM php:8.0-apache

# Copiar archivo dentro
COPY index.php /var/www/lamp/index.php

RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
RUN apt-get update && apt-get upgrade -y

COPY apache.conf /etc/apache2/sites-available/apache.conf
RUN a2dissite 000-default.conf
RUN a2dissite default-ssl.conf
RUN a2ensite apache.conf
CMD ["apachectl", "-D", "FOREGROUND"]

# Copy bd sentencias
COPY bd/* /var/www/lamp/