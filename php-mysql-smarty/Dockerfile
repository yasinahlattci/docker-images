FROM php:7.4-apache

ARG DB_HOST=localhost
ARG DB_NAME=localdb
ARG DB_PASS=pass
ARG DB_USER=user

ENV DB_HOST=$DB_HOST
ENV DB_NAME=$DB_NAME
ENV DB_PASS=$DB_PASS
ENV DB_USER=$DB_USER

RUN apt-get update && apt-get install -y git
RUN docker-php-ext-install pdo pdo_mysql mysqli
RUN a2enmod rewrite
RUN git clone https://github.com/smarty-php/smarty.git /tmp/smarty
RUN mv /tmp/smarty/libs /usr/local/lib/php/smarty
RUN rm -rf /tmp/smarty

COPY www /var/www/html

RUN chmod 777 /var/www/html/smarty/templates_c
EXPOSE 80
EXPOSE 443
