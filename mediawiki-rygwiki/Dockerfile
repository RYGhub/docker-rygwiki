FROM mediawiki:latest
LABEL maintainer="Stefano Pigozzi <me@steffo.eu>"

COPY mediawiki-extensions-PluggableAuth /var/www/html/extensions/PluggableAuth
COPY mediawiki-extensions-SimpleSAMLphp /var/www/html/extensions/SimpleSAMLphp

RUN apt-get -y update

# aptitude moment
RUN apt-get -y install \
    libapache2-mod-php7.4 \
    libedit2 \
    php-common \
    php7.4 \
    php7.4-cli \
    php7.4-common \
    php7.4-json \
    php7.4-opcache \
    php7.4-readline \
    psmisc


RUN apt-get update && apt-get -y --fix-broken install simplesamlphp