FROM php:8.2-apache

# Arguments defined in docker-compose.yml
ARG user
ARG uid

# Update apache config
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf
COPY apache2.conf /etc/apache2/apache2.conf

# Install system dependencies
RUN apt-get update -y && apt-get upgrade -y && apt install libapache2-mod-rpaf && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

# Install PHP extensions
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/
RUN install-php-extensions pdo_mysql mbstring exif pcntl bcmath gd && \ 
        apt-get clean -y && \
        rm -rf /var/lib/apt/lists/*

# Install composer
COPY --from=composer /usr/bin/composer /usr/bin/composer

# Apache mods
RUN a2enmod rewrite proxy proxy_http ssl && \
        a2dismod --force autoindex && \
        chown -R www-data:www-data /var/www

# Create system user to run Composer and Artisan Commands
RUN useradd -G www-data,root -u $uid -d /home/$user $user
RUN mkdir -p /home/$user/.composer && \
    chown -R $user:$user /home/$user

# Set working directory
WORKDIR /var/www

USER $user

EXPOSE 80