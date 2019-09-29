FROM debian:10

RUN set -x \
    && apt-get update \
    && apt-get install -y  \
        curl \
        bash \
        nano \
        coreutils \
        php7.3-cli \
        php7.3-fpm \
        php7.3-json \
        php7.3-intl \
        php7.3-curl \
        php7.3-mysqlnd \
        php7.3-xdebug \
        php7.3-memcached \
        php7.3-gd \
        php7.3-sqlite \
        php7.3-xmlrpc \
        php7.3-xsl \
        php7.3-geoip \
        php7.3-ldap \
        php7.3-imagick

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer

COPY xdebug.ini  /etc/php/7.3/fpm/conf.d/xdebug.ini
COPY project.pool.conf /etc/php/7.3/fpm/pool.d/project.pool.conf

RUN mkdir "/run/php"
ADD  run.sh /run.sh
COPY run.sh /run.sh

ENTRYPOINT ["/bin/bash", "/run.sh"]

WORKDIR /var/www/project
EXPOSE 9001
