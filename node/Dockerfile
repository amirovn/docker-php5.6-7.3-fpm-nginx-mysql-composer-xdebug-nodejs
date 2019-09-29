FROM debian:10

RUN apt-get update -y
RUN apt-get install -y \
 build-essential \
 curl \
 bash \
 nano

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
RUN apt-get install -y nodejs

RUN npm i
RUN npm install -g @vue/cli

CMD [ "npm", "run", "serve" ]

WORKDIR /var/www/frontend/
EXPOSE 3000