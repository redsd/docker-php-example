FROM php:8.0-apache

ENV PHP_OPCACHE_VALIDATE_TIMESTAMPS=0 \
    PHP_OPCACHE_MAX_ACCELERATED_FILES=10000 \
    PHP_OPCACHE_MEMORY_CONSUMPTION=128

RUN apt-get update && apt-get install -y libmcrypt-dev \
    libzip-dev zip \
    libwebp-dev \
    mariadb-client libmagickwand-dev imagemagick --no-install-recommends \
    && pecl install imagick \
    # && xdebug \
    && docker-php-ext-install pdo_mysql mysqli zip gd \
    && docker-php-ext-enable mysqli imagick opcache \
    # && xdebug \
    && a2enmod rewrite \
    && a2enmod headers

# Add jpg and webp support to GD library
RUN docker-php-ext-configure gd --enable-gd --with-freetype --with-jpeg --with-webp
RUN docker-php-ext-install -j$(nproc) gd zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN apt-get clean && rm -r /var/lib/apt/lists/*

COPY docker/vhost.conf /etc/apache2/sites-available/000-default.conf
COPY docker/config/php/conf.d/*.ini /usr/local/etc/php/conf.d/

#USER 1000:1000

#RUN chown -R www-data:www-data /var/www/html
