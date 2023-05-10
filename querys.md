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

---------------------------------------------------------------------------------------
# ÖDEV 3 
## 1.SORGU

SELECT country.country FROM country
WHERE country.country LIKE 'A%a';

## 2.SORGU

SELECT country.country FROM country
WHERE country.country LIKE '_____a';

## 3.SORGU

SELECT film.title FROM film
WHERE film.title ILIKE '%T%T%T%T';

## 4.SORGU

SELECT film.title FROM film
WHERE film.title ILIKE '%c' AND film.length > 90 AND film.rental_rate = 2.99;

--------------------------------------------------------------------------------------------------------
# ÖDEV 4
## 1.SORGU

SELECT DISTINCT film.replacement_cost FROM film;

## 2.SORGU

SELECT COUNT(DISTINCT film.replacement_cost) FROM film;

## 3.SORGU

SELECT COUNT(*) FROM film
WHERE film.title ILIKE 'T%' AND film.rating = 'G';

## 4.SORGU

SELECT COUNT(*) FROM country
WHERE country.country LIKE '_____';

## 5.SORGU

SELECT COUNT(*) FROM city
WHERE city.city ILIKE '%r';


--------------------------------------------------------------------------------------------------------
# ÖDEV 5
## 1.SORGU

SELECT * FROM film
WHERE film.title ILIKE '%n'
ORDER BY film.length DESC
LIMIT 5;

## 2.SORGU

SELECT * FROM film
WHERE film.title ILIKE '%n'
ORDER BY film.length ASC
OFFSET 5
LIMIT 5;

## 3.SORGU

SELECT * FROM customer
WHERE customer.store_id = 1
ORDER BY customer.last_name DESC
LIMIT 4;


--------------------------------------------------------------------------------------------------------
# ÖDEV 6
## 1.SORGU

SELECT ROUND(AVG(film.rental_rate),2) AS ortalama 
FROM film;

## 2.SORGU

SELECT COUNT(film.title) AS firstcharachterisC FROM film
WHERE film.title ILIKE 'c%';

## 3.SORGU

SELECT film.length FROM film
WHERE film.rental_rate = 0.99
ORDER BY film.rental_rate DESC
LIMIT 1;

## 4.SORGU

SELECT COUNT(DISTINCT film.replacement_cost) AS sayi FROM film
WHERE film.length > 150

