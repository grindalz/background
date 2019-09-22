FROM debian:latest
RUN apt-get update
RUN apt-get upgrade
RUN apt-get install -y apache2
COPY ./zabbix.local.conf /etc/apache2/sites-available/zabbix.local.conf
RUN a2ensite zabbix.local.conf
RUN apt-get install -y php
RUN apt-get install -y php-pgsql php-bcmath php-mbstring php-gd php-xmlwriter php-ldap
COPY ./php.ini /etc/php/7.3/apache2/php.ini
EXPOSE 80
CMD ["/usr/sbin/apachectl", "-D", "FOREGROUND"]
