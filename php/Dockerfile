FROM php:7.2.1-fpm
RUN groupadd www && useradd -g www -s /sbin/nologin www
COPY php.ini /usr/local/etc/php/php.ini
COPY php-fpm.conf /usr/local/etc/php-fpm.conf
COPY php-fpm.d/www.conf /usr/local/etc/php-fpm.d/www.conf
# ADD sources.list /etc/apt/
ADD composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer
# RUN apt-get update \
# 	&& apt-get install -y libmemcached-dev zlib1g-dev \
# 	&& pecl install memcached \
# 	&& pecl install xdebug \
# 	&& docker-php-ext-enable memcached xdebug
VOLUME /var/www/
CMD ["start.sh"]

