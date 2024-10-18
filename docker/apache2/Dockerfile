FROM httpd:2.4-alpine

WORKDIR /var/www/html
VOLUME app/ /usr/local/apache2/htdocs
VOLUME app/ /var/www/html
COPY  app/ .
RUN chown -R www-data:www-data /var/www/html/
RUN chown -R www-data:www-data /usr/local/apache2/htdocs/

COPY docker/apache2/00-vhost.conf /usr/local/apache2/conf/extra/00-vhost.conf
COPY /docker/apache2/httpd.conf /usr/local/apache2/conf/httpd.conf
