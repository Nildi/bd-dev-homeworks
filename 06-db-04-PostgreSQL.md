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

    SELECT attname, avg_width
    FROM pg_stats
    WHERE tablename = 'orders'
    ORDER BY avg_width DESC
    LIMIT 1;
     attname | avg_width
     ---------+-----------
      title   |        16
      (1 row)
      
(1 row)
      
(1 row)


<h3> Задание 3 </h3>

<h3> Задание 4 </h3>
