FROM mediawiki:latest as step-base
LABEL maintainer="Stefano Pigozzi <me@steffo.eu>"

FROM step-base AS step-dependencies
USER root
RUN apt-get update
RUN apt-get install -y libzip-dev
RUN apt-get install -y zip
RUN docker-php-ext-install zip

FROM step-dependencies AS step-extensions
COPY mediawiki-extensions-PluggableAuth /var/www/html/extensions/PluggableAuth
COPY mediawiki-extensions-OpenIDConnect /var/www/html/extensions/OpenIDConnect
COPY mediawiki-extensions-FontAwesome /var/www/html/extensions/FontAwesome
COPY mediawiki-skins-Bluelib /var/www/html/skins/Bluelib
COPY composer.local.json /var/www/html/composer.local.json

FROM step-extensions AS step-composer
WORKDIR /var/www/html
COPY --from=composer:1 /usr/bin/composer /usr/local/bin/composer
RUN composer update -vvv
