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
