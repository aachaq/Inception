FROM debian:buster
RUN apt update -y
RUN apt-get install mariadb-server mariadb-client -y
RUN apt install vim -y && apt install curl -y \
    && rm -rf /var/lib/apt/lists
RUN mkdir -p /var/run/mysqld \
&& chown -R mysql:mysql var/run/mysqld \
&& chmod 777 /var/run/mysqld

COPY tools/script.sh /etc/script.sh
RUN chmod +x /etc/script.sh

EXPOSE  3306

ENTRYPOINT ["/etc/script.sh"]
CMD ["mysqld", "--bind-address=0.0.0.0"]