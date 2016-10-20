FROM php:5.6-fpm

MAINTAINER Rafael Corrêa Gomes <rafaelcg_stz@hotmail.com>

RUN apt-get update && apt-get install -y \
	libmcrypt-dev \ 
	libpng12-dev \
	libxml2-dev \
	&& docker-php-ext-install \
		mcrypt \
		gd \
		soap \
		mbstring\
		pdo \
		pdo_mysql

RUN mkdir ~/.dev-alias \
    && wget https://github.com/rafaelstz/dev-alias/archive/master.zip -P ~/.dev-alias \
    && unzip -qo ~/.dev-alias/master.zip -d ~/.dev-alias \
    && mv ~/.dev-alias/dev-alias-master/* ~/.dev-alias \
    && rm -rf ~/.dev-alias/dev-alias-master \
    && rm ~/.dev-alias/master.zip \
    && echo "source ~/.dev-alias/alias.sh" >> ~/.bashrc

EXPOSE 9000
