FROM httpd

ARG WEB_USER
ARG WEB_GROUP
ARG APACHE_ROOT_DIR

COPY httpd-vhosts.conf ${APACHE_ROOT_DIR}/conf/extra/httpd-vhosts.conf
COPY httpd.conf ${APACHE_ROOT_DIR}/conf/httpd.conf

RUN chown ${WEB_USER}:${WEB_GROUP} ${APACHE_ROOT_DIR}

RUN chown 777 -R ${APACHE_ROOT_DIR}