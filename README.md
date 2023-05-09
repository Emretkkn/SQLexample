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