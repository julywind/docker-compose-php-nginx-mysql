FROM php:7.2-fpm
COPY sources.list /etc/apt/sources.list
RUN apt-get update \
	&& apt-get install -y iputils-ping \
	&& docker-php-ext-install mysqli && docker-php-ext-enable mysqli && pecl install -o -f redis mongodb memcached && rm -rf /tmp/pear \ 
        && docker-php-ext-enable redis memcached
COPY docker-php-ext.ini /usr/local/etc/php/conf.d/
