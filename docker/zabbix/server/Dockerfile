FROM debian:latest
RUN apt-get update
RUN apt install -y zabbix-server-pgsql
RUN apt install -y sudo
COPY ./zabbix_server.conf /etc/zabbix/zabbix_server.conf
RUN mkdir /var/run/zabbix
RUN chown zabbix:zabbix /var/run/zabbix
EXPOSE 10051
CMD sudo -u zabbix /usr/sbin/zabbix_server -f
