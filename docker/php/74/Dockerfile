FROM php:7.4-fpm

ARG WEB_USER
ARG WEB_GROUP
ARG PHP_ROOT_DIR
ARG WORK_ROOT_DIR

COPY www.conf ${PHP_ROOT_DIR}/php-fpm.d/www.conf

#RUN addgroup -g 1000 ${WEB_GROUP} && adduser -G ${WEB_USER} -g ${WEB_USER} -s /bin/sh -D ${WEB_USER}
RUN usermod -u 1000 ${WEB_USER}
RUN groupmod -g 1000 ${WEB_GROUP}

RUN mkdir -p ${WORK_ROOT_DIR}
RUN chown ${WEB_USER}:${WEB_GROUP} ${WORK_ROOT_DIR}
WORKDIR ${WORK_ROOT_DIR}
RUN chgrp -R staff ${PHP_ROOT_DIR}/php-fpm.d/www.conf

#module
RUN apt-get update -y
RUN apt-get install -y apt-utils
RUN apt-get install libtool -y
RUN apt-get install libcurl4-openssl-dev -y
RUN apt-get install libxml2-dev  -y
RUN apt-get install libpng-dev  -y
RUN apt-get install libjpeg-dev  -y
RUN apt-get install libfreetype6-dev  -y
RUN apt-get install libxslt-dev  -y
RUN apt-get install libzip-dev -y
RUN apt-get install libonig-dev -y


#extension
RUN docker-php-ext-install bcmath
RUN docker-php-ext-install ctype
RUN docker-php-ext-install curl
RUN docker-php-ext-install dom
RUN docker-php-ext-install gd
RUN docker-php-ext-configure gd --with-jpeg --with-freetype
RUN docker-php-ext-install intl
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install soap
RUN docker-php-ext-configure soap
RUN docker-php-ext-install xsl
RUN docker-php-ext-install zip
RUN docker-php-ext-configure zip
RUN docker-php-ext-install sockets

