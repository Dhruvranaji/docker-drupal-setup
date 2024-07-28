# Use the base PHP 8.2 FPM Alpine image
FROM php:8.2-fpm-alpine

# Install dependencies and GD library
RUN apk update && \
    apk add --no-cache \
    libpng-dev \
    libjpeg-turbo-dev \
    libwebp-dev \
    libzip-dev \
    gd-dev \
    zip \
    unzip \
    curl \
    git \
    patch && \ 
    docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp && \
    docker-php-ext-install -j$(nproc) gd pdo_mysql mysqli zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Enable OPcache
RUN docker-php-ext-install opcache

# Configure OPcache settings
COPY opcache/opcache.ini /usr/local/etc/php/conf.d/opcache.ini    

# Set the working directory
WORKDIR /var/www/html

# Copy the application code to the container
COPY . /var/www/html

# Expose port 9000 for PHP-FPM
EXPOSE 9000

# Start PHP-FPM server
CMD ["php-fpm"]

# Install Drush via Composer
# RUN composer global require drush/drush

ENV PATH="/var/www/html/vendor/bin:${PATH}"
