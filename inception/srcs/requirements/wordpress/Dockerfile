FROM debian:buster
RUN apt-get update
RUN apt-get upgrade
RUN apt-get -y install wget
RUN apt-get install -y php php-fpm php-mysql php-cgi php-pdo php-cli
RUN apt install vim -y

RUN wget https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN chmod +x wp-cli.phar
RUN mv wp-cli.phar /usr/local/bin/wp

COPY ./conf/www.conf /etc/php/7.3/fpm/pool.d

RUN mkdir /run/php

COPY ./tools/script.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/script.sh

ENTRYPOINT ["/usr/local/bin/script.sh"]

WORKDIR /var/www/html/
EXPOSE 9000
CMD ["/usr/sbin/php-fpm7.3", "-F"]
