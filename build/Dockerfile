# syntax=docker/dockerfile:1
FROM php:8.2-apache
RUN apt-get update && apt-get install -y mariadb-client && a2enmod rewrite
RUN docker-php-ext-install mysqli pdo pdo_mysql && docker-php-ext-enable mysqli pdo pdo_mysql
COPY app/Sistema-de-biblioteca-basico-php-8-y-mysql /var/www/html/
COPY apache2.conf /etc/apache2/
EXPOSE 80
ENV BASE_URL http://localhost/
ENV DB_USER biblio
ENV DB_PASS biblio
ENV DB_NAME biblio
ENV DB_HOST mariadb
COPY docker-entrypoint.sh /usr/local/bin/docker-entrypoint.sh
COPY app/Sistema-de-biblioteca-basico-php-8-y-mysql/biblioteca.sql /opt
RUN chmod +x /usr/local/bin/docker-entrypoint.sh
CMD /usr/local/bin/docker-entrypoint.sh
