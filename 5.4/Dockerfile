FROM php:5.4-fpm

RUN apt-get update && apt-get -y install nano mc wget openssl git

RUN docker-php-ext-install bcmath
RUN docker-php-ext-enable bcmath

RUN docker-php-ext-install ctype
RUN docker-php-ext-enable ctype

RUN apt-get install -y libcurl4-openssl-dev
RUN docker-php-ext-install curl
RUN docker-php-ext-enable curl

RUN apt-get install -y libxml2-dev
RUN docker-php-ext-install dom
RUN docker-php-ext-enable dom

RUN docker-php-ext-install fileinfo
RUN docker-php-ext-enable fileinfo

RUN apt-get install -y libpng-dev libjpeg-dev libfreetype6-dev libgd-dev
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN docker-php-ext-install gd
RUN docker-php-ext-enable gd

RUN docker-php-ext-install hash
RUN docker-php-ext-enable hash

RUN docker-php-ext-install iconv
RUN docker-php-ext-enable iconv

RUN apt-get install -y libmagickwand-dev
RUN pecl install imagick
RUN docker-php-ext-enable imagick

RUN docker-php-ext-install json
RUN docker-php-ext-enable json

RUN docker-php-ext-install mbstring
RUN docker-php-ext-enable mbstring

RUN apt-get install -y libmcrypt-dev
RUN docker-php-ext-install mcrypt
RUN docker-php-ext-enable mcrypt

RUN docker-php-ext-install pdo
RUN docker-php-ext-enable pdo

RUN docker-php-ext-install session
RUN docker-php-ext-enable session

RUN docker-php-ext-install simplexml
RUN docker-php-ext-enable simplexml

RUN apt-get install -y libxml2-dev
RUN docker-php-ext-install soap
RUN docker-php-ext-enable soap

RUN docker-php-ext-install sockets
RUN docker-php-ext-enable sockets

RUN docker-php-ext-install xml
RUN docker-php-ext-enable xml

RUN apt-get install -y libxslt1-dev
RUN docker-php-ext-install xsl
RUN docker-php-ext-enable xsl

RUN apt-get install -y zlib1g-dev
RUN docker-php-ext-install zip
RUN docker-php-ext-enable zip

RUN pecl install apc
RUN docker-php-ext-enable apc

RUN docker-php-ext-install pcntl
RUN docker-php-ext-enable pcntl

RUN pecl install https://xdebug.org/files/xdebug-2.4.1.tgz
RUN docker-php-ext-enable xdebug

RUN apt-get autoremove -y && apt-get clean all

EXPOSE 9000

CMD ["php-fpm"]
