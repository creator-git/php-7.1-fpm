FROM nsign/debian-docker:squeeze

COPY ./sources.list /etc/apt/sources.list

RUN echo 'Acquire::Check-Valid-Until "false";' >/etc/apt/apt.conf.d/90ignore-release-date

RUN apt-get update && apt-get upgrade -y \

    && apt-get install -y --no-install-recommends nano mc wget openssl git sshpass cron supervisor \

    && apt-get install -y --no-install-recommends apache2 apache2-mpm-prefork libapache2-mod-php5 apache2-utils \

    && apt-get install -y --no-install-recommends php-apc php5-curl php5-gd php5-imagick php5-intl php5-mcrypt php5-mysql php5-sqlite php5-xsl php5-xdebug php5-cli \

    && apt-get clean && apt-get autoclean && apt-get autoremove --purge -y

RUN a2enmod rewrite expires

EXPOSE 80
EXPOSE 443

RUN usermod -u 1000 www-data

CMD ["/usr/sbin/apachectl", "-D", "FOREGROUND"]
