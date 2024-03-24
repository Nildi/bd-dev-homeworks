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
<br>SELECT attname, avg_width
<br>FROM pg_stats
<br>WHERE tablename = 'orders'
<br>ORDER BY avg_width DESC
<br>LIMIT 1;
<br> attname | avg_width
<br>---------+-----------
<br> title   |        16
<br>(1 row)


<h3> Задание 3 </h3>

<h3> Задание 4 </h3>
