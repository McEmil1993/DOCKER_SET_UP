FROM php:8.1-fpm

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg-dev \
        libpng-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd 

RUN docker-php-ext-install pdo_mysql pdo mysqli

RUN \
  pecl install redis \
  && docker-php-ext-enable redis

# # Install Composer
# RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer


# FROM php:8.1-fpm

# # Install Composer
# RUN apt-get update && apt-get install -y \
#         curl \
#     && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
#     && apt-get clean \
#     && rm -rf /var/lib/apt/lists/*

