FROM debian:latest
RUN apt-get update
RUN apt-get install -y postgresql 
EXPOSE 5432
RUN apt-get install sudo
COPY ./pg_hba.conf /etc/postgresql/11/main/pg_hba.conf
COPY ./postgresql.conf /etc/postgresql/11/main/postgresql.conf
#RUN /etc/init.d/postgresql start
#RUN echo "create database zabbix;" | sudo -u postgres psql
#RUN echo "create user zabbix with password 'zabbix';" | sudo -u postgres psql
#RUN echo "grant all on DATABASE zabbix TO zabbix;" | sudo -u postgres psql
#RUN echo "grant ALL ON ALL tables in schema public TO zabbix;" | sudo -u postgres psql zabbix

CMD ["sudo", "-u", "postgres", "/usr/lib/postgresql/11/bin/postgres", "-D", "/var/lib/postgresql/11/main", "-c", "config_file=/etc/postgresql/11/main/postgresql.conf"]
