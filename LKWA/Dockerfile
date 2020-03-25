FROM ubuntu:18.04
MAINTAINER weev3
ENV TZ=Europe/Minsk
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update
RUN apt-get -y update && apt-get install -y apache2 php
COPY . /var/www/html/
RUN chmod -R 777 /var/www/html/phar_deserial/uploads
COPY config/start.sh /usr/local/bin
COPY config/apache2.conf /etc/apache2/apache2.conf
COPY config/php.ini /etc/php/7.2/apache2/php.ini
RUN rm -rf /var/www/html/index.html
RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf
RUN a2enmod php7.2
RUN a2enmod rewrite
RUN chmod +x /usr/local/bin/start.sh
RUN service apache2 restart
CMD ["/usr/local/bin/start.sh"]
EXPOSE 80
