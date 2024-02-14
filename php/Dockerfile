# FROM php:8.1-fpm

# # Install system dependencies
# RUN apt-get update && apt-get install -y \
#         libfreetype6-dev \
#         libjpeg62-turbo-dev \
#         libpng-dev \
#         zip \
#         unzip \
#         curl \
#     && docker-php-ext-install -j$(nproc) iconv \
#     && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
#     && docker-php-ext-install -j$(nproc) gd 

# # Install PHP extensions
# RUN docker-php-ext-install pdo_mysql pdo mysqli

# # Install Redis extension
# RUN \
#   curl 'http://pecl.php.net/get/redis-3.1.5.tgz' -o /tmp/redis-3.1.5.tgz  \
#   && cd /tmp \
#   && pecl install redis-3.1.5.tgz \
#   && rm -rf redis-3.1.5.tgz \
#   && docker-php-ext-enable redis

# # Install Composer
# RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer


FROM php:8.1-fpm

# Install Composer
RUN apt-get update && apt-get install -y \
        curl \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

