# Домашнее задание к занятию "Работа с данными (DDL/DML)" - `Чернышев Владислав`

### Задание 1


1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp.

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

![z1_1](https://github.com/VladkaTrue/gitlab_hw/blob/hw_12-02/img/z1_1.png?raw=true)

1.4. Дайте все права для пользователя sys_temp.

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

![z1_2](https://github.com/VladkaTrue/gitlab_hw/blob/hw_12-02/img/z1_2.png?raw=true)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос:

    ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';

![z1_3](https://github.com/VladkaTrue/gitlab_hw/blob/hw_12-02/img/z1_3.png?raw=true)

1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

![z1_4](https://github.com/VladkaTrue/gitlab_hw/blob/hw_12-02/img/z1_4.png?raw=true)

CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'password';

SELECT user FROM mysql.user;

GRANT ALL PRIVILEGES ON * . * TO 'sys_temp'@'localhost';

SHOW GRANTS FOR 'sys_temp'@'localhost';

ALTER USER 'sys_temp'@'localhost' IDENTIFIED WITH caching_sha2_password BY '1234'; 

*В последней команде использовал `caching_sha2_password` вместо `mysql_native_password`, так как у себя поднял mysql версии 9.1.0 (Плагин `mysql_native_password` был объявлен устаревшим и удален в MySQL 9.0.0)

---


