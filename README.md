
# Домашнее задание к занятию "Система мониторинга Zabbix" - `Чернышев Владислав`

### Задание 1

1) Cкриншот
2) Список команд:

> wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_latest_6.0+debian12_all.deb
> dpkg -i zabbix-release_latest_6.0+debian12_all.deb
> apt update
> apt install zabbix-server-pgsql zabbix-frontend-php php8.2-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
> su - postgres -c 'psql --command "CREATE USER zabbix WITH PASSWORD '\'123456789\'';"'
> su - postgres -c 'psql --command "CREATE DATABASE zabbix OWNER zabbix;"'
> zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
> sed -i 's/# DBPassword=/DBPassword=123456789/g' /etc/zabbix/zabbix_server.conf
> systemctl restart zabbix-server apache2
> systemctl enable zabbix-server apache2

---

### Задание 2


