# 12-03-mysql
Задание 1  
Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.  

SELECT DISTINCT * FROM address
WHERE district LIKE 'K%a'
AND district NOT LIKE '% %';

Задание 2  
Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.  

SELECT payment_id, CAST(payment_date AS DATE) from payment WHERE payment_date BETWEEN '2005-06-15' AND '2005-06-18' AND amount > 10.00;

Задание 3  
Получите последние пять аренд фильмов.  

SELECT * FROM rental order by rental_date DESC LImit 5;

Задание 4  
Одним запросом получите активных покупателей, имена которых Kelly или Willie.  
Сформируйте вывод в результат таким образом:  
все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,  
замените буквы 'll' в именах на 'pp'.  

SELECT REPLACE (LOWER(first_name), 'll', 'pp') as first_name, LOWER(last_name) as last_name
from customer
WHERE (first_name = 'Kelly' or first_name = 'Willie');
