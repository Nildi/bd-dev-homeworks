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
<br>        WHEN 'Иванов' THEN (SELECT id FROM orders WHERE item_name = 'Книга')
<br>        WHEN 'Петров' THEN (SELECT id FROM orders WHERE item_name = 'Монитор')
<br>        WHEN 'Бах' THEN (SELECT id FROM orders WHERE item_name = 'Гитара')
<br>    END
<br>)
<br>WHERE last_name IN ('Иванов', 'Петров', 'Бах');

![alt text](https://github.com/Nildi/bd-dev-homeworks/blob/main/db_hw02.4.1.png)
<br>SELECT c.*
<br>FROM clients c
<br>JOIN orders o ON c.order_id = o.id;

<h3> Задание 5 </h3>

![alt text](https://github.com/Nildi/bd-dev-homeworks/blob/main/db_hw02.5.1.png)

Hash Join указывает на использование хеш-соединения. Hash Cond показывает условие, по которому производится соединение. Seq Scan указывает на последовательное сканирование таблицы. . Cost (cтоимость) и оценка количества rows (строк) могут быть полезными для оптимизации запроса. Filter показывает условие фильтрации.  Каждая строка представляет один шаг выполнения запроса
<h3> Задание 6 </h3>
Создание бэкапа и помещение его в volume:
<br>docker exec -it postgres12 bash
<br>pg_dump -U admin test_db > /backups/test_db_backup.sql
<br> Остановка контейнера:
<br> docker stop postgres12
<br> Подъем нового контейнера:
<br>docker run -d \
  --name test_db \
  -v /var/lib/docker/volumes/postgres_pg_backups/_data:/backups \
  -e POSTGRES_DB=test_db \
  -e POSTGRES_USER=admin \
  -e POSTGRES_PASSWORD=1234qwer \
  postgres:12
<br> Восстановление БД:
<br>docker exec -it test_db bash
psql -U admin test_db < backups/test_db_backup.sql
