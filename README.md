# 12-03-mysql

SELECT DISTINCT * FROM address
WHERE district LIKE 'K%a'
AND district NOT LIKE '% %';

SELECT payment_id, CAST(payment_date AS DATE) from payment WHERE payment_date BETWEEN '2005-06-15' AND '2005-06-18' AND amount > 10.00;

SELECT * FROM rental order by rental_date DESC LImit 5;

SELECT REPLACE (LOWER(first_name), 'll', 'pp') as first_name, LOWER(last_name) as last_name
from customer
WHERE (first_name = 'Kelly' or first_name = 'Willie');
