FROM mediawiki:latest
LABEL maintainer="Stefano Pigozzi <me@steffo.eu>"

COPY mediawiki-extensions-PluggableAuth /var/www/html/extensions/PluggableAuth
COPY mediawiki-extensions-OpenIDConnect /var/www/html/extensions/OpenIDConnect
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer
COPY composer.local.json /var/www/html/composer.local.json

RUN apt-get install -y libzip-dev
RUN apt-get install -y zip
RUN docker-php-ext-install zip

WORKDIR /var/www/html
RUN composer update
