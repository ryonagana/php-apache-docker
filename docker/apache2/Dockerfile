FROM httpd:2.4-alpine

WORKDIR /var/www/html
VOLUME app/ /usr/local/apache2/htdocs
VOLUME app/ /var/www/html
COPY  app/ .


COPY docker/apache2/00-vhost.conf /usr/local/apache2/conf/extra/00-vhost.conf
COPY docker/apache2/httpd.conf /usr/local/apache2/conf/httpd.conf

#enable rewrite
RUN sed -i 's/\#LoadModule\ rewrite\_module/LoadModule\ rewrite\_module/g' /usr/local/apache2/conf/httpd.conf

#enable ssl
RUN sed -i 's/\#LoadModule\ ssl\_module/LoadModule\ ssl\_module/g' /usr/local/apache2/conf/httpd.conf

#enable deflate
RUN sed -i 's/\#LoadModule\ deflate\_module/LoadModule\ deflate\_module/g' /usr/local/apache2/conf/httpd.conf

#proxy http
RUN sed -i 's/\#LoadModule\ proxy\_http\_module/LoadModule\ proxy\_http\_module/g' /usr/local/apache2/conf/httpd.conf
