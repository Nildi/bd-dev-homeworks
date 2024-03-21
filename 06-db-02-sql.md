<h3> Задание 1 </h3>
version: '3.7'

services:
  postgres:
    image: postgres:12
    restart: always
    environment:
      POSTGRES_DB: mydatabase
      POSTGRES_USER: myuser
      POSTGRES_PASSWORD: mypassword
    volumes:
      - db_data:/var/lib/postgresql/data
      - db_backups:/backups

volumes:
  db_data:
  db_backups:

<h3> Задание 2 </h3>

![alt text](https://github.com/Nildi/-sdb-homeworks/blob/main/db_hw02.2.1.png)

![alt text](https://github.com/Nildi/-sdb-homeworks/blob/main/db_hw02.2.2.png)
SELECT grantee, privilege_type
FROM information_schema.table_privileges
WHERE table_schema = 'public' AND table_name IN ('orders', 'clients');


![alt text](https://github.com/Nildi/-sdb-homeworks/blob/main/db_hw02.2.3.png)


<h3> Задание 3 </h3>

<h3> Задание 4 </h3>

<h3> Задание 5 </h3>

<h3> Задание 6 </h3>
