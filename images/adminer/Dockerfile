FROM adminer

USER root

RUN apk add autoconf gcc g++ make libffi-dev openssl-dev \
    && pecl install mongodb \
    && docker-php-ext-enable mongodb

EXPOSE 8080
