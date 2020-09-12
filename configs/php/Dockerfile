FROM php:7.4-apache
COPY ./local/php.ini /usr/local/etc/php/php.ini
COPY ./xdebug-2.9.6 /app/xdebug
RUN apt-get update && apt-get install -y \
curl \
mariadb-client \
wget \
zlib1g-dev \
libzip-dev \
unzip \
libmemcached-dev zlib1g-dev \
&& docker-php-ext-install pdo pdo_mysql mysqli zip \
&& a2enmod rewrite \
&& cd /app/xdebug/ \
&& phpize \
&& ./configure \
&& make \
&& mkdir -p /usr/local/lib/php/extensions/no-debug-non-zts-20190902/ \
&& cp modules/xdebug.so /usr/local/lib/php/extensions/no-debug-non-zts-20190902/ \