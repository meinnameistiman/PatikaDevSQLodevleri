# patika.dev SQL ödevleri.


# Odev 1

## Soru 1
**select title, description from film**

## Soru 2
**select * from film where length> 60 and length < 75**

## Soru 3
**select * from film where rental_rate= 0.99 and replacement_cost= 12.99 or replacement_cost= 28.99**

## Soru 4
**select last_name from customer where first_name = 'Mary'**

## Soru 5
**select * from film where not(length> 50 and rental_rate= 2.99 and rental_rate= 4.99)**


# Odev 2

## Soru 1
**select * from film where replacement_cost between 12.99 AND 16.99;**

## Soru 2
**select first_name,last_name from actor where first_name in ('Penelope','Nick','Ed');**

## Soru 3
**select * from film where rental_rate in (0.99,2.99,4.99) and replacement_cost in (12.99,15.99,28.99);**
