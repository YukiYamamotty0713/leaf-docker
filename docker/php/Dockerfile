FROM php:8.3-fpm-alpine

RUN set -eux; \
    \
    apk add --update --no-cache --virtual .build-deps \
        freetype-dev \
        gmp-dev \
        icu-dev \
        libintl \
        libjpeg-turbo-dev \
        libpng-dev \
        libxml2-dev \
        libzip-dev \
        linux-headers \
        $PHPIZE_DEPS \
    ; \
    docker-php-ext-configure gd \
        --with-freetype=/usr/include/ \
        --with-jpeg=/usr/include/ \
    ; \
    docker-php-ext-install -j"$(getconf _NPROCESSORS_ONLN)" \
        bcmath \
        gd \
        gmp \
        intl \
        opcache \
        pdo_mysql \
        pcntl \
        sockets \
        zip \
    ; \
    php --version

	
#RUN curl -sL https://deb.nodesource.com/setup_18.x | bash -
RUN apk add nodejs npm git


COPY --from=composer:latest /usr/bin/composer /usr/bin/composer