
# Домашнее задание к занятию "Система мониторинга Zabbix" - `Чернышев Владислав`

### Задание 1

1) Cкриншот
![Вход в админку](https://github.com/VladkaTrue/gitlab_hw/blob/hw_02/img/zabbix_login.png?raw=true)

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

1.  Приложите скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу

![активные хосты](https://github.com/VladkaTrue/gitlab_hw/blob/hw_02/img/hosts.png?raw=true)

2.  Приложите скриншот лога zabbix agent, где видно, что он работает с сервером

![первый](https://github.com/VladkaTrue/gitlab_hw/blob/hw_02/img/log%20on%20server%20host.png?raw=true)

![второй](https://github.com/VladkaTrue/gitlab_hw/blob/hw_02/img/log%20on%20agent%20%28second%29%20host.png?raw=true)

3.  Приложите скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.

![Последние данные](https://github.com/VladkaTrue/gitlab_hw/blob/hw_02/img/latest_data.png?raw=true)

4.  Приложите текст использованных команд в GitHub

> wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_latest_6.0+debian12_all.deb

> dpkg -i zabbix-release_latest_6.0+debian12_all.deb

> apt update

> apt install zabbix-agent

> systemctl restart zabbix-agent

> systemctl enable zabbix-agent