# patika.dev SQL ödevleri. (ÖDEV 1 - 3)


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
