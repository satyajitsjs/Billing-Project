# Use the official PHP image as a base image
FROM php:8.1

# Install system dependencies and PHP extensions
RUN apt-get update && apt-get install -y openssl zip unzip git libonig-dev

# Install Composer globally
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install PDO MySQL extension
RUN docker-php-ext-install pdo mbstring pdo_mysql

# Set the working directory
WORKDIR /app/backend

# Copy application files
COPY . .

# Install PHP dependencies using Composer
RUN composer install

# Expose the port
EXPOSE 8000

# Start the application
CMD ["php", "artisan", "serve", "--host=0.0.0.0", "--port=8000"]
