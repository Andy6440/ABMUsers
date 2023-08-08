FROM php:8.2-fpm

# Install system dependencies
RUN apt-get update && apt-get install -y git curl libpng-dev libjpeg-dev libfreetype6-dev zip unzip

# Install PHP extensions
RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install gd pdo pdo_mysql

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Set working directory
WORKDIR /var/www/html

# Install dependencies
COPY composer.json composer.lock ./
RUN composer install --no-scripts --no-autoloader

# Copy existing application directory contents
COPY . .

# Generate autoloader and clear cache
RUN composer dump-autoload --optimize

# Expose port 9000 and start php-fpm server
EXPOSE 9000
CMD ["php-fpm"]
