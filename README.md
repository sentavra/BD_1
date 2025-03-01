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

UPDATE products 
SET name = 'PS5' 
WHERE name = 'IMAC';

![image](https://github.com/user-attachments/assets/f70c7b6c-f2b8-418f-b86e-3fd2344adfd2)

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


