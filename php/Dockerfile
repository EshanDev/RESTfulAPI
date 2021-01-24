FROM php:7.4-fpm-alpine

# Install Additional dependencies
RUN apk update && apk add --no-cache \
    build-base shadow vim curl \
    php7 \
    php7-fpm \
    php7-common \
    php7-pdo \
    php7-pdo_mysql \
    php7-mysqli \
    php7-mcrypt \
    php7-mbstring \
    php7-xml \
    php7-openssl \
    php7-json \
    php7-phar \
    php7-zip \
    php7-gd \
    php7-dom \
    php7-session \
    php7-zlib

RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-enable pdo_mysql


RUN curl -sS https://getcomposer.org/install | php -- --install-dir=/usr/local/bin --filename=composer

RUN rm -rf /var/cache/apk/*

EXPOSE 9000
CMD ["php-fpm"]