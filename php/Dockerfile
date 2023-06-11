FROM php:8.2-fpm
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        mariadb-client
RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install pdo pdo_mysql mysqli -j$(nproc)

RUN docker-php-ext-install exif
RUN apt-get install libmagickwand-dev libmagickcore-dev -y
RUN pecl install imagick
RUN docker-php-ext-enable imagick
RUN PHP_OPENSSL=yes
RUN docker-php-ext-install xml
RUN docker-php-ext-install filter
RUN apt-get install libzip-dev -y
RUN docker-php-ext-install zip
RUN docker-php-ext-install bcmath
RUN apt install libwebp-dev
RUN docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp
RUN docker-php-ext-install gd
RUN docker-php-ext-install intl