FROM php:8.0-fpm

# Install system dependencies
RUN apt-get update && apt-get install -y \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd pdo pdo_mysql


# Establecer el directorio de trabajo
WORKDIR /var/www

# Copiar el código fuente
COPY . /var/www
