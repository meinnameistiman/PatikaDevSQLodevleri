# patika.dev SQL ödevleri. (ÖDEV 1 - 6)


# Odev 1

## Soru 1
**SELECT title, DESCRIPTION from film**

## Soru 2
**SELECT * FROM film WHERE length > 60 AND length < 75**

## Soru 3
**SELECT * FROM film WHERE rental_rate= 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99**

## Soru 4
**SELECT last_name FROM customer WHERE first_name = 'Mary'**

## Soru 5
**SELECT * FROM film WHERE NOT(length > 50 AND rental_rate = 2.99 AND rental_rate = 4.99)**


# Odev 2

## Soru 1
**SELECT * FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99;**

## Soru 2
**SELECT first_name,last_name FROM actor WHERE first_name IN ('Penelope','Nick','Ed');**

## Soru 3
**SELECT * FROM film WHERE rental_rate IN (0.99,2.99,4.99) AND replacement_cost IN (12.99,15.99,28.99);**


# Odev 3

## Soru 1
**SELECT * FROM country WHERE country ILIKE 'A%A';**

## Soru 2
**SELECT * FROM country WHERE country ILIKE '_____%n';**

## Soru 3
**SELECT * FROM film WHERE title ILIKE '%t%t%t%t';**

## Soru 4
**SELECT * FROM film WHERE title LIKE'C%' AND length>90 AND rental_rate=2.99;**


# Odev 4

## Soru 1
**SELECT DISTINCT replacement_cost FROM film;**

## Soru 2
**SELECT COUNT (DISTINCT replacement_cost) FROM film;**

## Soru 3
**SELECT COUNT(*) FROM film WHERE title LIKE'T%' AND rating='G';**

## Soru 4
**SELECT COUNT(*) FROM country WHERE country LIKE '_____' ;**

## Soru 5

**SELECT COUNT(*) FROM city WHERE city ILIKE'%R';**



# Odev 5

## Soru 1
**SELECT title, length FROM film WHERE title LIKE '%n' ORDER BY length DESC LIMIT 5;**

## Soru 2
**SELECT title, length FROM film WHERE title LIKE '%n' ORDER BY length ASC LIMIT 5 OFFSET 5;**

## Soru 3
**SELECT last_name, store_id FROM customer WHERE store_id = 1 ORDER BY last_name DESC LIMIT 4;**


# Odev 6

## Soru 1
**SELECT round (AVG(rental_rate),2 ) FROM film;**

## Soru 2
**SELECT COUNT (title) FROM film WHERE title  ILIKE 'C%';**

## Soru 3
**SELECT MAX(LENGTH) FROM film WHERE rental_rate = 0.99;**

## Soru 4
**SELECT COUNT(DISTINCT(replacement_cost)) FROM film  WHERE LENGTH > 150;**



# Odev 6

## Soru 1
SELECT rating FROM film GROUP BY rating ;

## Soru 2
SELECT replacement_cost, COUNT(*) FROM film GROUP BY replacement_cost HAVING COUNT(*) > 50 ;

## Soru 3
SELECT store_id, COUNT(*) FROM customer GROUP BY store_id ;

## Soru 4
SELECT country_id , Count(*) FROM city GROUP BY country_idORDER BY Count(*) DESC LIMIT 1;
