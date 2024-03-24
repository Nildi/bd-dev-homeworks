<h3> Задание 1 </h3>
Найдите и приведите управляющие команды для:

    вывода списка БД,
    \l
    подключения к БД,
    \c
    вывода списка таблиц,
    \dt
    вывода описания содержимого таблиц,
    \d+
    выхода из psql.
    \q


<h3> Задание 2 </h3>

    SELECT attname, avg_width
    FROM pg_stats
    WHERE tablename = 'orders'
    ORDER BY avg_width DESC
    LIMIT 1;
     attname | avg_width
     ---------+-----------
      title   |        16
      (1 row)
      


<h3> Задание 3 </h3>


    BEGIN;

    CREATE TABLE orders_1 AS
    SELECT * FROM orders WHERE price > 499;

    CREATE TABLE orders_2 AS
    SELECT * FROM orders WHERE price <= 499;

    DROP TABLE orders;

    COMMIT;

Можно попробовать создать две отдельные таблицы, используя виды партицирования при создании этих таблиц. Это позволило бы нам избежать ручного разделения таблицы

<h3> Задание 4 </h3>
Один из вариантов - создание индексов, что позволило бы нам ускорить работу с этим столбцом
<br> CREATE INDEX uniq_title ON orders(title);
