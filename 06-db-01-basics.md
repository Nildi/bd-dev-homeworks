<h3> Задание 1 </h3>
<br>- Здесь подойдет БД типа "Ключ-значение", так как каждый чек может отличаться по своему наполнению
<br>- Графовая БД, склады можно предсатвить в виде объектов, а дороги в виде связей 
<br>- Документоориентированная БД, так как генеалогические древо напоминает иерархию 
<br>- БД типа "Ключ-значение", например, redis или memcached, которые позволяют установить время жизни для движка аутентификации
<br>- Здесь может подойти реляционная БД, если требуется составить простую связь между клиентом и покупкой, привязывая к клиенту список его покупок. Так же может подойти БД типа "Ключ-значение", по аналогии с первым примером 

<h3> Задание 2 </h3>
<br>- AP, PA/EC.
<br>- CA, PA/EL
<br>- CP, PC/EC

<h3> Задание 3 </h3>

Хоть принципы ACID и BASE отличаются друг от друга, они могут пересекаться в некоторых системах. Например, в распределенных базах данных могут быть реализованы ACID-транзакции внутри отдельных узлов, обеспечивая при этом масштабируемость и доступность с помощью механизмов репликации и асинхронной синхронизации данных, что соответствует принципам BASE. Поэтому, можно найти способы совмещения этих принципов, которые смогут обеспечить баланс между надежностью и производительностью

<h3> Задание 4 </h3>

<br>Это система Redis. Она позволит обеспечить фиксацию некоторых значений с временм жизни и производить какие-то действия с этими значениями (например, удаление) по истечению срока их жизни при помощи механизма TTL (time-to-live)
<br>Из минусов можно выделить:
<br>Если произойдет какой-то сбой в работе сервера, то все данные из redis будут утеряны, так как они зранятся в оперативной памяти
<br>Относительный минус, так как данные хранятся в оперативной памяти, что делает сильную зависимость от объема RAM 
