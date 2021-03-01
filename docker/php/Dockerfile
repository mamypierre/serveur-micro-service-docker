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