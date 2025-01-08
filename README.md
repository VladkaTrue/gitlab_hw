# Домашнее задание к занятию "Индексы" - `Чернышев Владислав`

### Задание 1

Напишите запрос к учебной базе данных, который вернёт процентное отношение общего размера всех индексов к общему размеру всех таблиц.

![z1](https://github.com/VladkaTrue/gitlab_hw/blob/hw_12-05/img/z1.png?raw=true)

---

### Задание 2

Выполните explain analyze следующего запроса:

    select distinct concat(c.last_name, ' ', c.first_name), sum(p.amount) over (partition by c.customer_id, f.title)
    from payment p, rental r, customer c, inventory i, film f
    where date(p.payment_date) = '2005-07-30' and p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id

-   перечислите узкие места;
-   оптимизируйте запрос: внесите корректировки по использованию операторов, при необходимости добавьте индексы.

#### Ответ:
К узким местам возможно отнести неправильность присоединения таблиц.

Чтобы оптимизировать запрос сделал следующее:

-   Использовал JOIN вместо перечисления таблиц через запятую.
    
-   Использовал оператор BETWEEN вместо функции DATE.

![z2](https://github.com/VladkaTrue/gitlab_hw/blob/hw_12-05/img/z2.png?raw=true)

![z2-1](https://github.com/VladkaTrue/gitlab_hw/blob/hw_12-05/img/z21.png?raw=true)


    SELECT CONCAT(c.last_name, ' ', c.first_name), SUM(p.amount)
    FROM payment p
    JOIN rental r ON p.rental_id = r.rental_id
    JOIN customer c ON r.customer_id = c.customer_id
    JOIN inventory i ON r.inventory_id = i.inventory_id
    JOIN film f ON i.film_id = f.film_id
    WHERE p.payment_date BETWEEN '2005-07-30 00:00:00' AND '2005-07-30 23:59:59'
    group by c.last_name, c.first_name, c.customer_id;
