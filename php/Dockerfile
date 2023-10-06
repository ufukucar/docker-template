FROM php:8.2-fpm

RUN apt update && apt install -y curl nano git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install PHP extensions
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd opcache

# Install composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer

# yaml dosyasında laravel kısmında ne yazdıysak onu girmeliyiz
WORKDIR /var/www

COPY  . /var/www



# php fpm in default portu 9000'dir. NGINX bu 9000 portundan fpm e ulaşabilecek
EXPOSE 9000


CMD [ "php-fpm" ]
















