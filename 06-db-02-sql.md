<h3> Задание 1 </h3>
https://github.com/Nildi/bd-dev-homeworks/blob/main/docker-compose.yml

<h3> Задание 2 </h3>

![alt text](https://github.com/Nildi/bd-dev-homeworks/blob/main/db_hw02.2.1.png)

![alt text](https://github.com/Nildi/bd-dev-homeworks/blob/main/db_hw02.2.2.png)
<br>SELECT grantee, privilege_type
<br>FROM information_schema.table_privileges
<br>WHERE table_schema = 'public' AND table_name IN ('orders', 'clients');

![alt text](https://github.com/Nildi/bd-dev-homeworks/blob/main/db_hw02.2.3.png)


<h3> Задание 3 </h3>
<br>INSERT INTO orders (наименование, цена)
<br>VALUES
<br>    ('Шоколад', 10),
<br>    ('Принтер', 3000),
<br>    ('Книга', 500),
<br>    ('Монитор', 7000),
<br>    ('Гитара', 4000);
<br>INSERT INTO clients (фамилия, страна_проживания)
<br>VALUES
<br>    ('Иванов Иван Иванович', 'USA'),
<br>    ('Петров Петр Петрович', 'Canada'),
<br>    ('Иоганн Себастьян Бах', 'Japan'),
<br>    ('Ронни Джеймс Дио', 'Russia'),
<br>    ('Ritchie Blackmore', 'Russia');

<br>SELECT COUNT(*) AS orders_count FROM orders;
<br>SELECT COUNT(*) AS clients_count FROM clients;


![alt text](https://github.com/Nildi/bd-dev-homeworks/blob/main/db_hw02.3.1.png)

<h3> Задание 4 </h3>
<br>UPDATE clients
<br>SET order_id = (
<br>    CASE last_name
        WHEN 'Иванов' THEN (SELECT id FROM orders WHERE item_name = 'Книга')
        WHEN 'Петров' THEN (SELECT id FROM orders WHERE item_name = 'Монитор')
        WHEN 'Бах' THEN (SELECT id FROM orders WHERE item_name = 'Гитара')
<br>    END
<br>)
<br>WHERE last_name IN ('Иванов', 'Петров', 'Бах');


<br>SELECT c.*
<br>FROM clients c
<br>JOIN orders o ON c.order_id = o.id;

<h3> Задание 5 </h3>

<h3> Задание 6 </h3>
