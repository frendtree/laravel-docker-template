FROM php:8.0-fpm

ARG UID=1000
RUN useradd -m -u ${UID} docker

RUN echo 'alias ll="ls -l"' >> /home/docker/.bashrc \
  && echo 'alias art="php artisan"' >> /home/docker/.bashrc \
  && sed -i -e "s/^user.*$/user = docker/" /usr/local/etc/php-fpm.d/www.conf \
  && sed -i -e "s/^group.*$/group = docker/" /usr/local/etc/php-fpm.d/www.conf

RUN cd /usr/bin && curl -s https://getcomposer.org/installer | php && ln -s /usr/bin/composer.phar /usr/bin/composer

RUN apt-get update \
  && apt-get install -y git zip unzip vim \
  && apt-get install -y libpq-dev libicu-dev libonig-dev libzip-dev \
  && docker-php-ext-install intl mbstring pdo pdo_mysql pdo_pgsql zip bcmath \
  && pecl install xdebug \
  && docker-php-ext-enable xdebug

WORKDIR /var/www/html
