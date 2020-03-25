FROM ubuntu:trusty
MAINTAINER Area39@163.com
RUN echo "deb http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse"> /etc/apt/sources.list
RUN apt-get update \
        && apt-get install -y mysql-server apache2 php5 php5-mysql
COPY sql /root/
RUN /etc/init.d/mysql start &&\
    mysql -e "grant all privileges on *.* to 'root'@'%' identified by 'toor';"&&\
    mysql -e "grant all privileges on *.* to 'root'@'localhost' identified by 'toor';"&&\
    mysql -u root -ptoor -e "show databases;" &&\
    mysql -u root -ptoor --default-character-set=utf8 </root/webug.sql &&\
    mysql -u root -ptoor -e "show databases;" &&\
    mysql -u root -ptoor </root/webug_sys.sql &&\
    mysql -u root -ptoor -e "show databases;" &&\
    mysql -u root -ptoor </root/webug_width_byte.sql &&\
    mysql -u root -ptoor -e "show databases;"
RUN sed -Ei 's/^(bind-address|log)/#&/' /etc/mysql/my.cnf \
	&& echo 'skip-host-cache\nskip-name-resolve' | awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' /etc/mysql/my.cnf > /tmp/my.cnf \
	&& mv /tmp/my.cnf /etc/mysql/my.cnf
COPY webug /var/www/html
RUN rm /var/www/html/index.html &&\
 chown www-data:www-data /var/www/html -R &&\
 rm -rf /root/*
COPY httpd-foreground /usr/bin
EXPOSE 80
CMD ["httpd-foreground"]
