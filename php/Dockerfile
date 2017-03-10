FROM php:5.6-fpm

COPY redis.tgz /home/redis.tgz

RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install pecl install /home/redis.tgz && echo "extension=redis.so" > /usr/local/etc/php/conf.d/redis.ini
ADD composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer

WORKDIR /opt
RUN usermod -u 1000 www-data

VOLUME ["/opt"]