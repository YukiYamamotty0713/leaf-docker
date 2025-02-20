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

RUN apk add nodejs npm git

# Heroku CLIのインストールに必要な依存関係とCLIのインストール
RUN apk add --no-cache bash curl && \
    curl https://cli-assets.heroku.com/install.sh | sh

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer