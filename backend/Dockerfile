FROM php:8.1-fpm

# Install dependencies and extensions
RUN apt-get update && apt-get install -y \
    libzip-dev \
    && docker-php-ext-install zip pdo pdo_mysql

# Set the working directory
WORKDIR /var/www/html

# Copy application files
COPY . .

# Expose the port
EXPOSE 8000

# Start the application
CMD ["php", "artisan", "serve", "--host=0.0.0.0", "--port=8000"]
