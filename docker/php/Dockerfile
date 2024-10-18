FROM php:8.2-fpm

RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"

ARG WITH_XDEBUG="true"

ARG UID
ARG GID

ENV UID=${UID}
ENV GID=${GID}


RUN addgroup --gid ${GID} --system user
RUN adduser --ingroup user --system --disabled-login --shell /bin/sh -u ${UID} user

RUN chown -R user:user /var/www/html

#CHANGE GROUP PHP-FPM
RUN sed -i 's/user = www-data/user = user/g' /usr/local/etc/php-fpm.d/www.conf
RUN sed -i 's/group = www-data/group = user/g' /usr/local/etc/php-fpm.d/www.conf

#enable PHP Errors
RUN sed -i 's/php_flag\[display\_errors\] = off/php_flag\[display\_errors\] = on/g' /usr/local/etc/php-fpm.d/www.conf

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install pdo pdo_mysql; \
    if [ $WITH_XDEBUG = "true" ] ; then \
        pecl install xdebug; \
    fi ;

