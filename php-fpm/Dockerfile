FROM debian:8

RUN set -x \
    && apt-get update \
    && apt-get install -y  \
        curl \
        emacs \
        bash \
        nano \
        coreutils \
        php5-cli \
        php5-fpm \
        php5-json \
        php5-intl \
        php5-curl \
        php5-mysqlnd \
        php5-xdebug \
        php5-memcached \
        php5-mcrypt \
        php5-gd \
        php5-sqlite \
        php5-xmlrpc \
        php5-xsl \
        php5-geoip \
        php5-ldap \
        php5-imagick

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer

COPY project.ini /etc/php5/conf.d/
COPY project.ini /etc/php5/cli/conf.d/
COPY xdebug.ini  /etc/php5/fpm/conf.d/xdebug.ini

COPY project.pool.conf /etc/php5/fpm/pool.d/project.pool.conf

CMD ["php5-fpm", "-F"]

WORKDIR /var/www/project
EXPOSE 9001
