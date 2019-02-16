FROM php:7.3.0-apache-stretch
MAINTAINER RemDav <contact@remydamblemont.fr>
RUN apt-get update && apt-get install -y \
    ruby-sass \
    libzip-dev \
    curl \
    git \
    && rm -rf /var/lib/apt/lists/*
RUN pecl install xdebug-2.7.0RC2 \
    pecl install apcu \
    && docker-php-ext-enable xdebug apcu
RUN docker-php-ext-install iconv \
        mysqli \
        zip \
        pdo_mysql \
    && docker-php-source delete \
    && php -r "readfile('https://getcomposer.org/installer');" | php -- --install-dir=/usr/local/bin --filename=composer \
    && chmod +x /usr/local/bin/composer
