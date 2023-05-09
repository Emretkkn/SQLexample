# ÖDEV 1
## 1.SORGU

SELECT film.title, film.description FROM film;

## 2.SORGU

SELECT * FROM film
WHERE film.length > 60 AND film.length < 75;

## 3.SORGU

SELECT * FROM film
WHERE film.rental_rate = 0.99 AND film.replacement_cost = 12.99 OR film.replacement_cost = 28.99;

## 4.SORGU

SELECT customer.last_name FROM customer
WHERE customer.first_name = 'Mary';

## 5.SORGU

SELECT * FROM film
WHERE film.length <= 50 AND (film.rental_rate != 2.99 OR film.rental_rate != 4.99);

---------------------------------------------------------------------------------------
# ÖDEV 2
## 1.SORGU

SELECT * FROM film
WHERE film.replacement_cost >= 12.99 AND film.replacement_cost <= 16.99;

## 2.SORGU

SELECT actor.first_name, actor.last_name FROM actor
WHERE actor.first_name IN ('Penelope','Nick','Ed');

## 3.SORGU

SELECT * FROM film
WHERE film.rental_rate IN (0.99,2.99,4.99) AND film.replacement_cost IN (12.99,15.99,28.99);