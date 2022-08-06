FROM php:8.1-fpm

RUN apt-get update; \
    apt-get upgrade -y; \
    apt-get install -y --no-install-recommends \
			curl \
			libmemcached-dev \
			libz-dev \
			libpq-dev \
			libjpeg-dev \
			libpng-dev \
			libfreetype6-dev \
			libssl-dev \
			libwebp-dev \
			libxpm-dev \
			libmcrypt-dev \
			libonig-dev; \
    rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install pdo_mysql; \
    docker-php-ext-install pdo_pgsql; \
    docker-php-ext-install mongodb; \
    docker-php-ext-configure gd \
			--prefix=/usr \
			--with-jpeg \
			--with-webp \
			--with-xpm \
			--with-freetype; \
    docker-php-ext-install gd; \
    pecl install -o -f redis;

RUN docker-php-ext-enable redis;

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www

EXPOSE 9000
