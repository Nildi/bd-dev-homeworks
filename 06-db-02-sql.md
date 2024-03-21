<h3> Задание 1 </h3>
<br>version: '3.7'
<br>
<br>services:
<br>  postgres:
<br>    image: postgres:12
<br>    restart: always
<br>    environment:
<br>      POSTGRES_DB: mydatabase
<br>      POSTGRES_USER: myuser
<br>      POSTGRES_PASSWORD: mypassword
<br>    volumes:
<br>      - db_data:/var/lib/postgresql/data
<br>      - db_backups:/backups
<br>
<br>volumes:
<br>  db_data:
<br>  db_backups:

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
<br>   ('Шоколад', 10),
<br>    ('Принтер', 3000),
<br>    ('Книга', 500),
<br>    ('Монитор', 7000),
<br>    ('Гитара', 4000);



<h3> Задание 4 </h3>

<h3> Задание 5 </h3>

<h3> Задание 6 </h3>
