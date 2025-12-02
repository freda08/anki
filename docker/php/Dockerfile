FROM php:8.4-fpm

# Установка системных пакетов и PHP-расширений
RUN apt-get update && apt-get install -y \
    git curl libpq-dev unzip && \
    docker-php-ext-install pdo pdo_pgsql && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /var/www/html

# Копируем Composer из официального образа
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

CMD ["php-fpm"]
