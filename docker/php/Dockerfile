FROM php:7.4-fpm-alpine

ARG WEB_USER
ARG WEB_GROUP
ARG PHP_ROOT_DIR
ARG WORK_ROOT_DIR

COPY www.conf ${PHP_ROOT_DIR}/php-fpm.d/www.conf

RUN mkdir -p ${WORK_ROOT_DIR}
RUN chown ${WEB_USER}:${WEB_GROUP} ${WORK_ROOT_DIR}
WORKDIR ${WORK_ROOT_DIR}

RUN docker-php-ext-install mysqli
