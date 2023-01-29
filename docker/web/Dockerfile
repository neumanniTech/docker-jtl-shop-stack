# Get selected PHP image
ARG PHP_VERSION
FROM php:${PHP_VERSION}-apache AS build

# INSTALL XDEBUG
RUN pecl install xdebug && rm -r /tmp/pear/*

# PHP EXTENSIONS Imagick, intl, bcmath, soap, opcache, pdo_mysql, xdebug
RUN apt-get update && apt-get install -y nano unzip libzip-dev zip libicu-dev libxml2-dev libmagickwand-dev --no-install-recommends && rm -rf /var/lib/apt/lists/*
RUN printf "\n" | pecl install imagick
RUN docker-php-ext-install intl bcmath soap opcache pdo_mysql zip \
    && docker-php-ext-enable imagick xdebug

# DOwnload and install selected shop version
ARG JTL_VERSION
WORKDIR /var/www/html
ADD https://build.jtl-shop.de/get/shop-${JTL_VERSION}.zip .
RUN unzip shop-${JTL_VERSION}.zip
RUN chown www-data:www-data . -R


# COPY JTL php.ini
COPY php.ini "$PHP_INI_DIR/php.ini"

# COPY XDEBUG INI
COPY xdebug.ini "$PHP_INI_DIR/conf.d/docker-php-ext-xdebug.ini"

# ENABLE apache mod_rewrite
RUN a2enmod rewrite
