FROM php:8-fpm

RUN apt-get update && apt-get -y --no-install-recommends install \
                              wget \
                              curl \
                              htop \
                              libxml2-dev \
                              git \
                              nano \
                              unzip \
                              libpq-dev \
                              libzip-dev \
                              libbz2-dev \
                              libtidy-dev \
    && docker-php-ext-install bcmath \
                              pcntl \
                              sockets \
                              intl \
                              pdo_mysql \
                              pdo_pgsql \
                              pgsql \
                              bz2 \
                              zip \
                              exif \
                              tidy \
    && pecl channel-update pecl.php.net \
    && pecl install xdebug-3.0.4 \
    && docker-php-ext-enable xdebug \
    && wget https://getcomposer.org/installer -O - -q | php -- --install-dir=/bin --filename=composer --quiet \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

ENV COMPOSER_ALLOW_SUPERUSER=1