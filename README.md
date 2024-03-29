# patika.dev SQL ödevleri. (ÖDEV 1 - 12)


# Odev 1

## Soru 1
SELECT title, DESCRIPTION from film**

## Soru 2
SELECT * FROM film WHERE length > 60 AND length < 75**

## Soru 3
SELECT * FROM film WHERE rental_rate= 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99**

## Soru 4
SELECT last_name FROM customer WHERE first_name = 'Mary'**

## Soru 5
SELECT * FROM film WHERE NOT(length > 50 AND rental_rate = 2.99 AND rental_rate = 4.99)**

*******************************************************************

# Odev 2

## Soru 1
SELECT * FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99;**

## Soru 2
SELECT first_name,last_name FROM actor WHERE first_name IN ('Penelope','Nick','Ed');**

## Soru 3
SELECT * FROM film WHERE rental_rate IN (0.99,2.99,4.99) AND replacement_cost IN (12.99,15.99,28.99);**

*******************************************************************

# Odev 3

## Soru 1
SELECT * FROM country WHERE country ILIKE 'A%A';**

## Soru 2
SELECT * FROM country WHERE country ILIKE '_____%n';**

## Soru 3
SELECT * FROM film WHERE title ILIKE '%t%t%t%t';**

## Soru 4
SELECT * FROM film WHERE title LIKE'C%' AND length>90 AND rental_rate=2.99;**

*******************************************************************

# Odev 4

## Soru 1
SELECT DISTINCT replacement_cost FROM film;**

## Soru 2
SELECT COUNT (DISTINCT replacement_cost) FROM film;**

## Soru 3
SELECT COUNT(*) FROM film WHERE title LIKE'T%' AND rating='G';**

## Soru 4
SELECT COUNT(*) FROM country WHERE country LIKE '_____' ;**

## Soru 5

SELECT COUNT(*) FROM city WHERE city ILIKE'%R';**

*******************************************************************

# Odev 5

## Soru 1
SELECT title, length FROM film WHERE title LIKE '%n' ORDER BY length DESC LIMIT 5;**

## Soru 2
SELECT title, length FROM film WHERE title LIKE '%n' ORDER BY length ASC LIMIT 5 OFFSET 5;**

## Soru 3
SELECT last_name, store_id FROM customer WHERE store_id = 1 ORDER BY last_name DESC LIMIT 4;**

*******************************************************************

# Odev 6

## Soru 1
SELECT round (AVG(rental_rate),2 ) FROM film;**

## Soru 2
SELECT COUNT (title) FROM film WHERE title  ILIKE 'C%';**

## Soru 3
SELECT MAX(LENGTH) FROM film WHERE rental_rate = 0.99;**

## Soru 4
SELECT COUNT(DISTINCT(replacement_cost)) FROM film  WHERE LENGTH > 150;**

*******************************************************************

# Odev 7

## Soru 1
SELECT rating FROM film GROUP BY rating ;

## Soru 2
SELECT replacement_cost, COUNT(*) FROM film GROUP BY replacement_cost HAVING COUNT(*) > 50 ;

## Soru 3
SELECT store_id, COUNT(*) FROM customer GROUP BY store_id ;

## Soru 4
SELECT country_id , Count(*) FROM city GROUP BY country_idORDER BY Count(*) DESC LIMIT 1;

*******************************************************************

# Odev 8

## Soru 1
CREATE TABLE employee (
id INTEGER PRIMARY KEY,  
name VARCHAR(50) NOT NULL, 
birthday DATE,  
email VARCHAR(100)
);

## Soru 2
insert into employee (id, name, birthday, email) values (1, 'Name Surname', '10.10.2000', 'email@mail.com');

## Soru 3
UPDATE employee
SET name = 'Name Surname',
	birthday = '10.10.2000',
		email ='email@mail.com'
WHERE id = 1
RETURNING *;

## Soru 4
DELETE FROM employee
WHERE name = 'Name Surname';
RETURNING * ;

*******************************************************************

# Odev 9

## Soru 1
SELECT city.city, country.country FROM city
INNER JOIN country ON city.country_id = country.country_id; 

## Soru 2
SELECT payment.payment_id, customer.first_name, customer.last_name FROM payment
INNER JOIN customer ON payment.customer_id = customer.customer_id;

## Soru 3
SELECT rental.rental_id, customer.first_name, customer.last_name FROM rental
INNER JOIN customer ON rental.customer_id = customer.customer_id;

*******************************************************************

# Odev 10

## Soru 1
SELECT city.city ,country.country FROM city
LEFT JOIN country ON city.country_id = country.country_id;

## Soru 2
SELECT payment_id,first_name, last_name FROM customer
RIGHT JOIN payment ON payment.customer_id=customer.customer_id; 

## Soru 3
SELECT rental.rental_id, customer.first_name, customer.last_name
FROM rental
FULL JOIN customer
ON rental.customer_id = customer.customer_id;

*******************************************************************

# Odev 11

## Soru 1
SELECT first_name FROM actor UNION
SELECT first_name FROM customer;

## Soru 2
SELECT first_name FROM actor INTERSECT
SELECT first_name FROM customer;

## Soru 3
SELECT first_name FROM actor EXCEPT
SELECT first_name FROM customer;

## Soru 4
SELECT first_name FROM actor UNION ALL
SELECT first_name FROM customer;

SELECT first_name FROM actor INTERSECT ALL 
SELECT first_name FROM customer;

SELECT first_name FROM actor EXCEPT ALL 
SELECT first_name FROM customer;

*******************************************************************

# Odev 12

## Soru 1
SELECT COUNT(length) FROM film WHERE length > (SELECT AVG(length) from film);

## Soru 2
SELECT COUNT(*) FROM film WHERE rental_rate = (SELECT MAX(rental_rate) FROM film);

## Soru 3
SELECT COUNT(rental_rate) FROM film
WHERE rental_rate = (SELECT MIN(rental_rate) FROM film) 
AND 
replacement_cost = (SELECT MIN(replacement_cost) FROM film) 

## Soru 4
SELECT customer_id, COUNT(*) as most_payments FROM payment 
GROUP BY customer_id ORDER BY most_payments DESC;
