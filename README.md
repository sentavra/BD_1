# BD_1
1) Выберите из таблицы orders все заказы

SELECT * FROM orders

![image](https://github.com/user-attachments/assets/446e78e2-a4ae-40fd-b572-4fdca4359838)

2) Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in

SELECT * FROM orders WHERE STATUS IN ('cancelled','in_progress','delivery')

![image](https://github.com/user-attachments/assets/a61aecf5-fde8-4542-9f69-bb8854f5abcf)

3) Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new".

SELECT * FROM orders WHERE STATUS IN ('cancelled','new') 

![image](https://github.com/user-attachments/assets/d1ffaaa6-5b7e-4706-a13e-972277a6f919)

4) Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count). Вывести нужно только номер (id) и сумму (sum) заказа.

SELECT id, sum FROM orders WHERE products_count > 3

![image](https://github.com/user-attachments/assets/6f867443-5fa1-4b29-9e3c-92f0c6cf4045)

22.02.2025

1 Файл

1) Выберите из таблицы orders 3 самых дешевых заказа за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

SELECT * FROM orders WHERE status != 'cancelled' ORDER BY sum ASC LIMIT 3;

![image](https://github.com/user-attachments/assets/c6313568-7ea4-4af1-9645-96a3c1e79a19)

2) Выберите из таблицы orders 2 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

SELECT * FROM orders WHERE status != 'cancelled' ORDER BY sum DESC LIMIT 2;

![image](https://github.com/user-attachments/assets/f28c10ac-1f8d-4b31-9da8-bb44dabb09ba)

2 Файл

INSERT INTO orders (price, products, status) VALUES (8000, 4, 'active');

![image](https://github.com/user-attachments/assets/bcf0dda8-b8f9-45c8-93cc-a66c55c8585a)


4) Создайте таблицу products
 
-----------------------------------------------------------------------------------------------------------------
CREATE TABLE products (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    price DECIMAL(10, 2),
    count INT
);
--------------------------------------------------------------------------------------------------------------------
 # Добавьте в таблицу products новый товар — «VR-очки», стоимостью 70000 рублей в количестве (count) 2 штук.

INSERT INTO products (name, price, count) VALUES ('VR-очки', 70000, 2);
----------------------------------------------------------------------------------------
![image](https://github.com/user-attachments/assets/63a35edc-4d0c-44d2-af4c-af486c01a87a)

5) В таблицу products внесли данные с ошибкой, вместо "PS5" в наименовании написали IMAC. Исправьте ошибку.

UPDATE products SET NAME = 'PS5' WHERE NAME = 'IMAC'

![image](https://github.com/user-attachments/assets/64f69c86-5261-487c-9d6c-96e3d350dec3)


01.03.2025

3 практическая 
Создайте таблицу users с полем id типа INT и двумя текстовыми полями, которые будут хранить имя (first_name) и фамилию (last_name). Длина имени и фамилии не превышает 50 символов.
Добавьте в таблицу трех пользователей: Дмитрия Иванова, Анатолия Белого и Дениса Давыдова.
----------------------------------------------------------------------------------
CREATE TABLE users (
    id INT,
    first_name VARCHAR(50),
    last_name VARCHAR(50)
);
----------------------------------------------------------------------------------
INSERT INTO users (id, first_name, last_name) VALUES 
(1, 'Дмитрий', 'Иванов'),
(2, 'Анатолий', 'Белый'),
(3, 'Денис', 'Давыдов');
------------------------------------------------------------------------------------------------
![image](https://github.com/user-attachments/assets/900661ab-20ca-41a5-b92c-1728bc4028e6)

# 4 практика - 15.03.2025
Создайте таблицу users для хранения информации о пользователях сайта.
В таблице должны быть следующие поля:

id – идентификатор, целое положительное;
email – адрес электронной почты, строка не более 100 символов;
date_joined – дата регистрации (достаточно хранить дату, без времени)
last_activity – дата и время последней активности (с точностью до секунд).
-------------------------------------------------------------------------------------------
CREATE TABLE users12 (
    id INT UNSIGNED PRIMARY KEY,
    email VARCHAR(100) NOT NULL UNIQUE,
    date_joined DATE NOT NULL,
    last_activity DATETIME NOT NULL
);
------------------------------------------------------------------------------------------
------------------------------------------------------------------------------------------
INSERT INTO users12 (id, email, date_joined, last_activity)
VALUES (1, "user1@domain.com", "2014-12-12", "2016-04-08 12:34:54");
INSERT INTO users12 (id, email, date_joined, last_activity)
VALUES (2, "user2@domain.com", "2014-12-12", "2017-02-13 11:46:53");
INSERT INTO users12 (id, email, date_joined, last_activity)
VALUES (3, "user3@domain.com", "2014-12-13", "2017-04-04 05:12:07");
------------------------------------------------------------------------------------------
![image](https://github.com/user-attachments/assets/faa89842-2345-4304-b6e2-9417adec45e9)
-----------------------------------------------------------------------------------------------
Создайте таблицу calendar для хранения календаря посетителей.
В таблице должны быть следующие поля:
-
id – идентификатор записи в календаре, целое положительное;
user_id – идентификатор пользователя, целое положительное;
doctor_id – идентификатор доктора, целое положительное;
visit_date – дата и время визита (точность до секунд).
--
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
![image](https://github.com/user-attachments/assets/4a020e40-866c-4f9f-845f-8e1030268f75)
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
![image](https://github.com/user-attachments/assets/a357db16-8b5e-49b5-ab63-42de6a0e1148)
-
5 практическая
-
1) Выберите из таблицы orders 4 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.
-
![image](https://github.com/user-attachments/assets/94d360ae-2ae8-4474-9b00-e8a076412b41)
-
2) Выберите из таблицы products название и цены четырех самых дешевых товаров, которые есть на складе.
-
![image](https://github.com/user-attachments/assets/3d43880b-8601-444b-8908-6f038b91abf1)

-
3) Выберите из таблицы orders три последних заказа (по дате date) стоимостью от 3200 рублей и выше.
Данные отсортируйте по дате в обратном порядке.
-
![image](https://github.com/user-attachments/assets/7117acc7-0c9e-43ab-9e1a-a71657ecfa6f)
-
4) Создайте данную таблицу:
![image](https://github.com/user-attachments/assets/6f2e2c54-7633-47b9-80eb-9f0c0c5c5025)
-
![image](https://github.com/user-attachments/assets/c07d204d-54af-4827-9d0b-8ac25eb48c68)
-
5) Из этой таблицы сделать выборку на основе задания: Сайт выводит товары по 5 штук. Выберите из таблицы products товары, которые пользователи увидят на 3 странице каталога при сортировке в порядке возрастания цены (price).
-
![image](https://github.com/user-attachments/assets/cf6ced3f-93f8-4f5b-aea9-ffb6c361818e)
-

