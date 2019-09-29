FROM debian:10

MAINTAINER Vincent Composieux <vincent.composieux@gmail.com>

RUN set -x \
    && apt-get update \
    && apt-get install -y  \
    nginx

COPY nginx.conf /etc/nginx/
COPY project.conf /etc/nginx/conf.d/

RUN echo "upstream php-upstream { server php:9001; }" > /etc/nginx/conf.d/upstream.conf

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
