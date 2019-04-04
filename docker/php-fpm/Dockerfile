FROM php:7.2-fpm

RUN apt-get update
RUN apt-get install libxml2-dev unzip libmcrypt-dev zlib1g-dev libpng-dev -y \
    && pecl install mongodb \
    && echo "extension=mongodb.so" > /usr/local/etc/php/conf.d/mongodb.ini

#Using docker-php-ext-install to install php modules
RUN docker-php-ext-install mbstring xml opcache zip gd

# Install Composer
RUN curl -sS https://getcomposer.org/installer |php -- --install-dir=/usr/bin --filename=composer

EXPOSE 9000
CMD ["php-fpm", "-F"]
