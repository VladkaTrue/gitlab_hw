# Домашнее задание к занятию "Очереди RabbitMQ" - `Чернышев Владислав`

### Задание 1. Установка RabbitMQ

Итогом выполнения домашнего задания будет приложенный скриншот веб-интерфейса RabbitMQ.

![rmq](https://github.com/VladkaTrue/gitlab_hw/blob/hw_11-04/img/rmq.png?raw=true)

---

### Задание 2. Отправка и получение сообщений

В качестве решения домашнего задания приложите оба скриншота, сделанных на этапе выполнения.

producer.py
![producer](https://github.com/VladkaTrue/gitlab_hw/blob/hw_11-04/img/producer.png?raw=true)

consumer.py
![consumer](https://github.com/VladkaTrue/gitlab_hw/blob/hw_11-04/img/consumer.png?raw=true)

---

### Задание 3. Подготовка HA кластера

В качестве решения домашнего задания приложите скриншоты из веб-интерфейса с информацией о доступных нодах в кластере и включённой политикой.

![haall](https://github.com/VladkaTrue/gitlab_hw/blob/hw_11-04/img/haall.png?raw=true)
![rmq12](https://github.com/VladkaTrue/gitlab_hw/blob/hw_11-04/img/rmq12.png?raw=true)

Также приложите вывод команды с двух нод:
![clustat](https://github.com/VladkaTrue/gitlab_hw/blob/hw_11-04/img/clustat.png?raw=true)

Для закрепления материала снова запустите скрипт producer.py и приложите скриншот выполнения команды на каждой из нод:
![hello](https://github.com/VladkaTrue/gitlab_hw/blob/hw_11-04/img/hello.png?raw=true)

После чего попробуйте отключить одну из нод, желательно ту, к которой подключались из скрипта, затем поправьте параметры подключения в скрипте consumer.py на вторую ноду и запустите его.

Приложите скриншот результата работы второго скрипта.

![secscript](https://github.com/VladkaTrue/gitlab_hw/blob/hw_11-04/img/secscript.png?raw=true)