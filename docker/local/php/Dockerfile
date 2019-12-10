FROM php:7.3-fpm-alpine

MAINTAINER xxxgit

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories

# Environments
ENV TIMEZONE            Asia/Shanghai
ENV LANG C.UTF-8

#PHP EXT
RUN apk update \
  && apk add --no-cache \
    $PHPIZE_DEPS \
    autoconf \
    libmcrypt-dev \
    freetype-dev \
    libjpeg-turbo-dev \
    libzip-dev \
    imagemagick-dev \
    imagemagick
    
RUN docker-php-ext-install pdo_mysql \
  && docker-php-ext-install mysqli \
  && pecl install imagick \
  && docker-php-ext-enable imagick \
  && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/ \
  && docker-php-ext-install -j$(nproc) gd \
  && mkdir -p /usr/src/php/ext/redis \
  && curl -L https://github.com/phpredis/phpredis/archive/5.1.1.tar.gz | tar xvz -C /usr/src/php/ext/redis --strip 1 \
  && echo 'redis' >> /usr/src/php-available-exts \
  && docker-php-ext-install redis \
  && docker-php-ext-install zip 


#FFmpeg
RUN apk add --no-cache \
  	yasm \
	  ffmpeg
	  