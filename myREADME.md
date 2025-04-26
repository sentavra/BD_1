[shpori.md](https://github.com/user-attachments/files/19920471/shpori.md)

#Удалить из таблицы products все товары, которых нет на складе.

delete from products where count<1;
--------------------------------------------------------------------------
#Удалить из таблицы cars все автомобили начиная с 2010 года и старше

delete from cars where year<=2010
---------------------------------------------------------------------------
#Измените статус (status) заказа под номером (id) 5 с delivery на success.

update orders set status='success' where id=5
---------------------------------------------------------------------------
#Увеличьте цену 5 самых дешевых товаров на 5%

update products set price=price*1.05 order by price limit 5
---------------------------------------------------------------------------
#теперь самых дорогих:

update products set price=price*1.05 order by price desc limit 5
---------------------------------------------------------------------------
У отмененных заказов status равен "cancelled". У новых заказов status равен "new".

номер (id) и сумму (sum) заказа.
---------------------------------------------------------------------------
NULL – это особое слово в MySQL и в отличии от "cancelled" или "new", его нужно писать без кавычек. 
А чтобы сравнить значение в поле с NULL, нужно использовать не символы равенства (=) и неравенства (<>), 
а специальное выражение IS NULL или IS NOT NULL.
---------------------------------------------------------------------------
Новые записи в таблицу можно добавить не только с помощью VALUES, но и с помощью SET. 
Следующие два запроса идентичны: 
 
INSERT INTO table (field1, field2) VALUES (value1, value2); 
INSERT INTO table SET field1=value1, field2=value2;
---------------------------------------------------------------------------
#Добавьте в таблицу users нового пользователя

insert into users SET id=10, first_name='Никита', last_name='Петров'
---------------------------------------------------------------------------
#Добавьте в таблицу products новый товар

insert into products (id, name, count, price) value
---------------------------------------------------------------------------
#Добавить таблицу с данными

CREATE TABLE table.name (ID INT, FIRST_N VARCHAR)
---------------------------------------------------------------------------
#Удалить таблицу 

DROP TABLE table_name
---------------------------------------------------------------------------

[Uploading] 
Удалить из таблицы products все товары, которых нет на складе.
-
delete from products where count<1;
-
Удалить из таблицы cars все автомобили начиная с 2010 года и старше
-
delete from cars where year<=2010
-
Измените статус (status) заказа под номером (id) 5 с delivery на success.
-
update orders set status='success' where id=5
-
Увеличьте цену 5 самых дешевых товаров на 5%
-
update products set price=price*1.05 order by price limit 5
-
Теперь самых дорогих:
-
update products set price=price*1.05 order by price desc limit 5
-
У отмененных заказов status равен "cancelled". У новых заказов status равен "new".
-
номер (id) и сумму (sum) заказа.
-
NULL – это особое слово в MySQL и в отличии от "cancelled" или "new", его нужно писать без кавычек. 
А чтобы сравнить значение в поле с NULL, нужно использовать не символы равенства (=) и неравенства (<>), 
а специальное выражение IS NULL или IS NOT NULL.
-
Новые записи в таблицу можно добавить не только с помощью VALUES, но и с помощью SET. 
Следующие два запроса идентичны: 
-
INSERT INTO table (field1, field2) VALUES
(value1, value2); 
-
INSERT INTO table SET field1=value1, field2=value2;
-
Добавьте в таблицу users нового пользователя
-
insert into users SET id=10, first_name='Никита', last_name='Петров'
-
Добавьте в таблицу products новый товар
-
insert into products (id, name, count, price) value
-
INSERT INTO table (column1, column2)
-
VALUES (value1, value2);
-
INSERT INTO table (column1, column2)
-
VALUES (value11, value12),
-
(value21, value22), ..:
-
INSERT INTO table1 (column1, column2)
-
SELECT (col1, col2) FROM table2;
-
UPDATE table1
-
SET column1 = new_value;
-
UPDATE table1
-
SET column1 = new_value
-
column2 = new_value
-
WHERE condition;
-
DELETE FROM table;
-
DELETE FROM table
-
WHERE condition;
-
Типы данных:
-
![image](https://github.com/user-attachments/assets/f69b6183-236a-4591-b79f-23f4e4ae07df)
--------------
Создайте таблицу users для хранения информации о пользователях сайта.
В таблице должны быть следующие поля:
id – идентификатор, целое положительное;
email – адрес электронной почты, строка не более 100 символов;
date_joined – дата регистрации (достаточно хранить дату, без времени)
last_activity – дата и время последней активности (с точностью до секунд).
--------
create table users (
id int(10) unsigned,
email varchar (100),
date_joined date,
last_activity datetime
);
insert into users (id, email, date_joined,last_activity)
values
(1,'user1@domain.com', '2014-12-12','2016-04-08 12:34:54'),
(2,'user2@domain.com', '2014-12-12','2017-02-13 11:46:53'),
(3,'user3@domain.com', '2014-12-13','2017-04-04 05:12:07');
----------------------
Создайте таблицу calendar для хранения календаря посетителей.
В таблице должны быть следующие поля:
id – идентификатор записи в календаре, целое положительное;
user_id – идентификатор пользователя, целое положительное;
doctor_id – идентификатор доктора, целое положительное;
visit_date – дата и время визита (точность до секунд).
-
Create table calendar (
id int unsigned,
user_id int unsigned,
doctor_id int unsigned,
visit_date datetime);
Insert into calendar (id, user_id, doctor_id, visit_date)
Values 
(1, 1914 , 1, '2017-04-08 12:00:00'),
(2, 12, 1, '2017-04-08 12:30:00'),
(3, 4641, 2, '2017-04-09 09:00:00'),
(4, 784, 1,'2017-04-08 13:00:00'),
(5, 15, 2,'2017-04-09 10:00:00')
-
Создайте таблицу users , в которой будут следующие поля:
id — идентификатор, целые положительные числа.
first_name— имя, строки до 50 символов.
last_name — фамилия, строки до 60 символов.
bio — биография, текст до 65000 символов.
-
create table users (
id int (10) unsigned,
first_name varchar (50),
last_name varchar (60),
bio text
);
INSERT INTO users (id, first_name, last_name, bio)
VALUES
(1,'Антон','Кулик','С отличием окончил 39 лицей.'),
(2,'Сергей','Давыдов',''),
(3,'Дмитрий','Соколов','Профессиональный программист.')
-





