FROM mediawiki:latest
LABEL maintainer="Stefano Pigozzi <me@steffo.eu>"

RUN apt-get update
RUN apt-get install -y libzip-dev
RUN apt-get install -y zip
RUN docker-php-ext-install zip

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

COPY mediawiki-extensions-PluggableAuth /var/www/html/extensions/PluggableAuth
COPY mediawiki-extensions-OpenIDConnect /var/www/html/extensions/OpenIDConnect
COPY mediawiki-extensions-FontAwesome /var/www/html/extensions/FontAwesome
COPY composer.local.json /var/www/html/composer.local.json

WORKDIR /var/www/html
RUN composer update
