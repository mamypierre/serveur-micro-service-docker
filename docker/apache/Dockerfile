FROM httpd

ARG WEB_USER
ARG WEB_GROUP
ARG APACHE_ROOT_DIR

COPY ./conf/extra/httpd-vhosts.conf /usr/local/apache2/conf/extra/httpd-vhosts.conf
COPY ./conf/httpd.conf /usr/local/apache2/conf/httpd.conf

RUN chown ${WEB_USER}:${WEB_GROUP} ${APACHE_ROOT_DIR}

RUN usermod -u 1000 ${WEB_USER}
RUN groupmod -g 1000 ${WEB_GROUP}

RUN chown 777 -R ${APACHE_ROOT_DIR}

RUN chmod u=rwx,g=rwx,o=rwx -R ${APACHE_ROOT_DIR}