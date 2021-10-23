FROM mediawiki:latest
LABEL maintainer="Stefano Pigozzi <me@steffo.eu>"

RUN docker-php-ext-install -j$(nproc)

COPY mediawiki-extensions-PluggableAuth /var/www/html/extensions/PluggableAuth
COPY mediawiki-extensions-SimpleSAMLphp /var/www/html/extensions/SimpleSAMLphp
