FROM mediawiki:latest
LABEL maintainer="Stefano Pigozzi <me@steffo.eu>"

COPY mediawiki-extensions-PluggableAuth /var/www/html/extensions/PluggableAuth
COPY mediawiki-extensions-SimpleSAMLphp /var/www/html/extensions/SimpleSAMLphp

RUN apt-get update && apt-get -y --fix-broken install simplesamlphp
