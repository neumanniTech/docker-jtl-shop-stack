FROM php:8.1-apache

# INSTALL XDEBUG
RUN pecl install xdebug && rm -r /tmp/pear/*

# PHP EXTENSIONS Imagick, intl, bcmath, soap, opcache, pdo_mysql, xdebug
RUN apt-get update && apt-get install -y nano libzip-dev zip libicu-dev libxml2-dev libmagickwand-dev --no-install-recommends && rm -rf /var/lib/apt/lists/*
RUN printf "\n" | pecl install imagick
RUN docker-php-ext-install intl bcmath soap opcache pdo_mysql zip \
    && docker-php-ext-enable imagick xdebug

# COPY JTL php.ini
COPY php.ini "$PHP_INI_DIR/php.ini"

# COPY XDEBUG INI
COPY xdebug.ini "$PHP_INI_DIR/conf.d/docker-php-ext-xdebug.ini"

# Copy htaccess to document root
COPY .htaccess "/var/www/html"

# ENABLE apache mod_rewrite
RUN a2enmod rewrite
