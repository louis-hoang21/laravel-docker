# Set master image
FROM php:7.3-fpm

ENV TZ Asia/Ho_Chi_Minh

ENV INSTALL_PATH /var/www/blog/

# Set working directory
WORKDIR $INSTALL_PATH

# Change current user to root
USER root

# Copy composer.lock and composer.json
COPY composer.lock composer.json $INSTALL_PATH

# Copy database
COPY database $INSTALL_PATH/database

# Install dependencies
RUN apt-get update && apt-get install -y libmcrypt-dev\
    build-essential \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    locales \
    zip \
    jpegoptim optipng pngquant gifsicle \
    vim \
    unzip \
    git \
    curl \
    libzip-dev \
    libicu-dev \
    libxml2-dev

RUN pecl install mcrypt-1.0.4
RUN docker-php-ext-enable mcrypt

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install extensions
RUN docker-php-ext-install pdo_mysql mbstring zip exif pcntl intl xml
RUN docker-php-ext-configure gd --with-gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/
RUN docker-php-ext-install gd

# Install PHP Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    composer install --no-scripts

# Copy existing application directory contents
COPY . $INSTALL_PATH

# Expose port 9000 and start php-fpm server
EXPOSE 9000
CMD ["php-fpm"]
