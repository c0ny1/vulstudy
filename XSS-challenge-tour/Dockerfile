FROM php:5.6-apache

MAINTAINER c0ny1 <root@gv7.me>

# set DirectoryIndex:index.htm
COPY docker-php.conf /etc/apache2/conf-enabled/

RUN rm -rf /var/www/html/*
ADD ./src/ /var/www/html/
