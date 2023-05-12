# ÖDEV 1
## 1.SORGU

```sql
SELECT film.title, film.description FROM film;
```
## 2.SORGU
```sql
SELECT * FROM film
WHERE film.length > 60 AND film.length < 75;
```
## 3.SORGU
```sql
SELECT * FROM film
WHERE film.rental_rate = 0.99 AND film.replacement_cost = 12.99 OR film.replacement_cost = 28.99;
```
## 4.SORGU
```sql
SELECT customer.last_name FROM customer
WHERE customer.first_name = 'Mary';
```
## 5.SORGU
```sql
SELECT * FROM film
WHERE film.length <= 50 AND (film.rental_rate != 2.99 OR film.rental_rate != 4.99);
```
---------------------------------------------------------------------------------------
# ÖDEV 2
## 1.SORGU
```sql
SELECT * FROM film
WHERE film.replacement_cost >= 12.99 AND film.replacement_cost <= 16.99;
```
## 2.SORGU
```sql
SELECT actor.first_name, actor.last_name FROM actor
WHERE actor.first_name IN ('Penelope','Nick','Ed');
```
## 3.SORGU
```sql
SELECT * FROM film
WHERE film.rental_rate IN (0.99,2.99,4.99) AND film.replacement_cost IN (12.99,15.99,28.99);
```
---------------------------------------------------------------------------------------
# ÖDEV 3 
## 1.SORGU
```sql
SELECT country.country FROM country
WHERE country.country LIKE 'A%a';
```
## 2.SORGU
```sql
SELECT country.country FROM country
WHERE country.country LIKE '_____a';
```
## 3.SORGU
```sql
SELECT film.title FROM film
WHERE film.title ILIKE '%T%T%T%T';
```
## 4.SORGU
```sql
SELECT film.title FROM film
WHERE film.title ILIKE '%c' AND film.length > 90 AND film.rental_rate = 2.99;
```
--------------------------------------------------------------------------------------------------------
# ÖDEV 4
## 1.SORGU
```sql
SELECT DISTINCT film.replacement_cost FROM film;
```
## 2.SORGU
```sql
SELECT COUNT(DISTINCT film.replacement_cost) FROM film;
```
## 3.SORGU
```sql
SELECT COUNT(*) FROM film
WHERE film.title ILIKE 'T%' AND film.rating = 'G';
```
## 4.SORGU
```sql
SELECT COUNT(*) FROM country
WHERE country.country LIKE '_____';
```
## 5.SORGU
```sql
SELECT COUNT(*) FROM city
WHERE city.city ILIKE '%r';
```

--------------------------------------------------------------------------------------------------------
# ÖDEV 5
## 1.SORGU
```sql
SELECT * FROM film
WHERE film.title ILIKE '%n'
ORDER BY film.length DESC
LIMIT 5;
```
## 2.SORGU
```sql
SELECT * FROM film
WHERE film.title ILIKE '%n'
ORDER BY film.length ASC
OFFSET 5
LIMIT 5;
```
## 3.SORGU
```sql
SELECT * FROM customer
WHERE customer.store_id = 1
ORDER BY customer.last_name DESC
LIMIT 4;
```

--------------------------------------------------------------------------------------------------------
# ÖDEV 6
## 1.SORGU
```sql
SELECT ROUND(AVG(film.rental_rate),2) AS ortalama 
FROM film;
```
## 2.SORGU
```sql
SELECT COUNT(film.title) AS firstcharachterisC FROM film
WHERE film.title ILIKE 'c%';
```
## 3.SORGU
```sql
SELECT film.length FROM film
WHERE film.rental_rate = 0.99
ORDER BY film.rental_rate DESC
LIMIT 1;
```
## 4.SORGU
```sql
SELECT COUNT(DISTINCT film.replacement_cost) AS sayi FROM film
WHERE film.length > 150
```
--------------------------------------------------------------------------------------------------------
# ÖDEV 7
## 1.SORGU
```sql
SELECT film.rental_rate, COUNT(film.film_id) AS sayi FROM film
GROUP BY film.rental_rate;
```
## 2.SORGU
```sql
SELECT film.replacement_cost, COUNT(film.film_id) AS film_sayisi FROM film
GROUP BY film.replacement_cost
HAVING COUNT(film.film_id) > 50
```
## 3.SORGU
```sql
SELECT customer.store_id, COUNT(customer.customer_id) AS musterisayisi
FROM customer
GROUP BY customer.store_id
```
## 4.SORGU
```sql
SELECT *
FROM(SELECT city.country_id AS sehirid, COUNT(city.country_id) AS sehirsayisi
FROM city
GROUP BY city.country_id ORDER BY sehirsayisi DESC LIMIT 1) AS tablo
```
--------------------------------------------------------------------------------------------------------
# ÖDEV 8
## 1.İŞLEM
```sql
CREATE TABLE Employee (id SERIAL PRIMARY KEY,name VARCHAR(50) NOT NULL,birthday DATE NOT NULL,email VARCHAR(100) NOT NULL)
```
## 2.İŞLEM
```sql
insert into employee (name, birthday, email) values ('Calhoun Guiduzzi', '1981-07-24', 'cguiduzzi0@ifeng.com');
insert into employee (name, birthday, email) values ('Albertine Mapples', '1997-04-15', 'amapples1@archive.org');
insert into employee (name, birthday, email) values ('Luelle Saleway', '1953-06-10', 'lsaleway2@aboutads.info');
insert into employee (name, birthday, email) values ('Arleen Thody', '1970-12-25', 'athody3@slashdot.org');
insert into employee (name, birthday, email) values ('Dru Marguerite', '2003-07-03', 'dmarguerite4@psu.edu');
insert into employee (name, birthday, email) values ('Inger Kilalea', '1990-03-11', 'ikilalea5@umich.edu');
insert into employee (name, birthday, email) values ('Clarie Pritty', '1991-06-24', 'cpritty6@free.fr');
insert into employee (name, birthday, email) values ('Jeff Duerdin', '1956-12-20', 'jduerdin7@ft.com');
insert into employee (name, birthday, email) values ('Eli Labba', '1984-05-11', 'elabba8@youtu.be');
insert into employee (name, birthday, email) values ('Rycca Strivens', '1956-08-24', 'rstrivens9@macromedia.com');
insert into employee (name, birthday, email) values ('Zechariah Bleyman', '1965-09-14', 'zbleymana@java.com');
insert into employee (name, birthday, email) values ('Cammie Jeeks', '1956-06-13', 'cjeeksb@usa.gov');
insert into employee (name, birthday, email) values ('Jere Aarons', '1988-01-13', 'jaaronsc@simplemachines.org');
insert into employee (name, birthday, email) values ('Filip Shergold', '1989-08-11', 'fshergoldd@hao123.com');
insert into employee (name, birthday, email) values ('Marvin Ketcher', '1984-07-09', 'mketchere@bing.com');
insert into employee (name, birthday, email) values ('Lon De Meyer', '1984-02-22', 'ldef@harvard.edu');
insert into employee (name, birthday, email) values ('Brendan Farnorth', '2001-03-07', 'bfarnorthg@slideshare.net');
insert into employee (name, birthday, email) values ('Isador Bristoe', '1965-07-28', 'ibristoeh@google.com.hk');
insert into employee (name, birthday, email) values ('Alvis MacGiolla Pheadair', '1954-07-27', 'amacgiollai@printfriendly.com');
insert into employee (name, birthday, email) values ('Frasier Ashman', '1953-07-18', 'fashmanj@is.gd');
insert into employee (name, birthday, email) values ('Dunn Seaward', '1984-01-11', 'dseawardk@woothemes.com');
insert into employee (name, birthday, email) values ('Heriberto Riccardo', '1978-01-25', 'hriccardol@amazon.com');
insert into employee (name, birthday, email) values ('Giraldo Killock', '2004-05-16', 'gkillockm@last.fm');
insert into employee (name, birthday, email) values ('Nevil Rope', '1964-04-08', 'nropen@sciencedirect.com');
insert into employee (name, birthday, email) values ('Pren Coggill', '1974-07-17', 'pcoggillo@loc.gov');
insert into employee (name, birthday, email) values ('Kimberli Gaytor', '1969-05-20', 'kgaytorp@chicagotribune.com');
insert into employee (name, birthday, email) values ('Shayne Simonett', '1979-03-06', 'ssimonettq@instagram.com');
insert into employee (name, birthday, email) values ('Thornton O''Bruen', '1974-01-27', 'tobruenr@salon.com');
insert into employee (name, birthday, email) values ('Fabiano Marguerite', '1954-03-25', 'fmarguerites@google.co.uk');
insert into employee (name, birthday, email) values ('Lenore Jedrzaszkiewicz', '1973-06-27', 'ljedrzaszkiewiczt@sogou.com');
insert into employee (name, birthday, email) values ('Hatty MacInherney', '2004-10-10', 'hmacinherneyu@icq.com');
insert into employee (name, birthday, email) values ('Jacinta Kovelmann', '1975-10-12', 'jkovelmannv@studiopress.com');
insert into employee (name, birthday, email) values ('Elicia Bonnette', '1998-07-30', 'ebonnettew@illinois.edu');
insert into employee (name, birthday, email) values ('Farrell Ginn', '1955-03-11', 'fginnx@wix.com');
insert into employee (name, birthday, email) values ('Warren Caney', '1974-12-25', 'wcaneyy@wikispaces.com');
insert into employee (name, birthday, email) values ('Madella Mewrcik', '1953-05-13', 'mmewrcikz@cmu.edu');
insert into employee (name, birthday, email) values ('Rozelle Boreham', '1974-04-22', 'rboreham10@wsj.com');
insert into employee (name, birthday, email) values ('Catherine Dellow', '1982-05-11', 'cdellow11@columbia.edu');
insert into employee (name, birthday, email) values ('Lynne Moyle', '1975-02-14', 'lmoyle12@a8.net');
insert into employee (name, birthday, email) values ('Cordi Bryce', '1987-02-10', 'cbryce13@amazon.de');
insert into employee (name, birthday, email) values ('Klement Loade', '1977-08-14', 'kloade14@adobe.com');
insert into employee (name, birthday, email) values ('Christiana Haberjam', '1982-12-14', 'chaberjam15@go.com');
insert into employee (name, birthday, email) values ('Augustin Sainsberry', '1965-05-29', 'asainsberry16@bloglines.com');
insert into employee (name, birthday, email) values ('Allie Crippill', '1966-01-31', 'acrippill17@bloglines.com');
insert into employee (name, birthday, email) values ('Theodoric Coldbathe', '1962-04-06', 'tcoldbathe18@unicef.org');
insert into employee (name, birthday, email) values ('Vi Record', '1956-03-26', 'vrecord19@yolasite.com');
insert into employee (name, birthday, email) values ('Mitchel Moncrefe', '1964-04-10', 'mmoncrefe1a@fc2.com');
insert into employee (name, birthday, email) values ('Darleen Rosenfarb', '2004-03-05', 'drosenfarb1b@zimbio.com');
insert into employee (name, birthday, email) values ('Thomasina Spurritt', '1950-12-09', 'tspurritt1c@booking.com');
insert into employee (name, birthday, email) values ('Malchy Ethridge', '1978-10-15', 'methridge1d@dedecms.com');
insert into employee (name, birthday, email) values ('Cassey Raulstone', '1976-03-17', 'craulstone1e@pcworld.com');
insert into employee (name, birthday, email) values ('Ashley Dell Casa', '1971-01-21', 'adell1f@sourceforge.net');
insert into employee (name, birthday, email) values ('Constantina Keenlayside', '1999-05-25', 'ckeenlayside1g@disqus.com');
insert into employee (name, birthday, email) values ('Fred Crosseland', '1972-02-03', 'fcrosseland1h@shutterfly.com');
insert into employee (name, birthday, email) values ('Tammie Rothery', '1971-10-20', 'trothery1i@eventbrite.com');
insert into employee (name, birthday, email) values ('Patin Aldersley', '1996-07-01', 'paldersley1j@webeden.co.uk');
insert into employee (name, birthday, email) values ('Chelsy Concannon', '1953-01-03', 'cconcannon1k@posterous.com');
insert into employee (name, birthday, email) values ('Sandro Soar', '1953-03-12', 'ssoar1l@ft.com');
insert into employee (name, birthday, email) values ('Emmey Norewood', '1999-08-02', 'enorewood1m@imdb.com');
insert into employee (name, birthday, email) values ('Chucho McHale', '2003-09-16', 'cmchale1n@discovery.com');
insert into employee (name, birthday, email) values ('Aggy de Nore', '2000-09-25', 'ade1o@mysql.com');
insert into employee (name, birthday, email) values ('Elene Viegas', '1981-12-13', 'eviegas1p@youku.com');
insert into employee (name, birthday, email) values ('Filide Saggs', '1992-06-05', 'fsaggs1q@arstechnica.com');
insert into employee (name, birthday, email) values ('Danell Kingaby', '2004-09-29', 'dkingaby1r@phoca.cz');
insert into employee (name, birthday, email) values ('Maggy Geelan', '1974-03-19', 'mgeelan1s@about.me');
insert into employee (name, birthday, email) values ('Damian Claughton', '1974-01-04', 'dclaughton1t@cbc.ca');
insert into employee (name, birthday, email) values ('Shannen Pember', '1979-02-01', 'spember1u@google.pl');
insert into employee (name, birthday, email) values ('Megen Huggin', '1976-09-01', 'mhuggin1v@gravatar.com');
insert into employee (name, birthday, email) values ('Jessi Mancktelow', '2001-09-10', 'jmancktelow1w@ezinearticles.com');
insert into employee (name, birthday, email) values ('Jasmin Steynor', '1960-11-03', 'jsteynor1x@tinyurl.com');
insert into employee (name, birthday, email) values ('Titus McLardie', '1959-12-10', 'tmclardie1y@gmpg.org');
insert into employee (name, birthday, email) values ('Joli Lonie', '1950-10-19', 'jlonie1z@google.es');
insert into employee (name, birthday, email) values ('Lucius Nuccii', '1965-12-11', 'lnuccii20@plala.or.jp');
insert into employee (name, birthday, email) values ('Waiter Acres', '1954-05-01', 'wacres21@google.cn');
insert into employee (name, birthday, email) values ('Barclay Biggar', '1990-01-23', 'bbiggar22@youtu.be');
insert into employee (name, birthday, email) values ('Carmine Ettels', '1962-05-28', 'cettels23@ezinearticles.com');
insert into employee (name, birthday, email) values ('Zia Jiruca', '1979-09-02', 'zjiruca24@mozilla.com');
insert into employee (name, birthday, email) values ('Elmore Raddish', '1981-08-25', 'eraddish25@sourceforge.net');
insert into employee (name, birthday, email) values ('Yolanthe Coulthard', '1997-06-23', 'ycoulthard26@imgur.com');
insert into employee (name, birthday, email) values ('Manuel Hastie', '2000-11-26', 'mhastie27@opensource.org');
insert into employee (name, birthday, email) values ('Alyss Scotchmur', '1969-06-15', 'ascotchmur28@newsvine.com');
insert into employee (name, birthday, email) values ('Whitaker Welfare', '1968-11-07', 'wwelfare29@ustream.tv');
insert into employee (name, birthday, email) values ('Marya Dowse', '1967-01-02', 'mdowse2a@jalbum.net');
insert into employee (name, birthday, email) values ('Gerri Callender', '2000-09-06', 'gcallender2b@amazonaws.com');
insert into employee (name, birthday, email) values ('Laurie Smuth', '1997-01-26', 'lsmuth2c@icq.com');
insert into employee (name, birthday, email) values ('Adrienne Collibear', '1983-07-18', 'acollibear2d@samsung.com');
insert into employee (name, birthday, email) values ('Huberto Desaur', '1971-11-12', 'hdesaur2e@nymag.com');
insert into employee (name, birthday, email) values ('Calli Castelow', '2000-02-05', 'ccastelow2f@bloglovin.com');
insert into employee (name, birthday, email) values ('Averil Markos', '1984-07-23', 'amarkos2g@mit.edu');
insert into employee (name, birthday, email) values ('Gasper Rysom', '2000-04-20', 'grysom2h@ted.com');
insert into employee (name, birthday, email) values ('Philippa Follacaro', '1975-07-15', 'pfollacaro2i@google.es');
insert into employee (name, birthday, email) values ('Rosana Lehenmann', '1980-02-18', 'rlehenmann2j@google.nl');
insert into employee (name, birthday, email) values ('Codie Plait', '1981-07-01', 'cplait2k@uol.com.br');
insert into employee (name, birthday, email) values ('Othella Craigs', '1956-04-17', 'ocraigs2l@economist.com');
insert into employee (name, birthday, email) values ('Karyn Sleeford', '1988-03-31', 'ksleeford2m@nba.com');
insert into employee (name, birthday, email) values ('Mel Hollingsbee', '2000-10-11', 'mhollingsbee2n@chronoengine.com');
insert into employee (name, birthday, email) values ('Anet Kirlin', '1951-03-26', 'akirlin2o@tiny.cc');
insert into employee (name, birthday, email) values ('Richmound Bark', '1955-03-03', 'rbark2p@weibo.com');
insert into employee (name, birthday, email) values ('Terry Pear', '1975-01-14', 'tpear2q@phpbb.com');
insert into employee (name, birthday, email) values ('Rodrigo Bottrill', '1996-03-23', 'rbottrill2r@yelp.com');
```
## 3.İŞLEM
```sql
UPDATE employee SET name = 'Emre Tekin' WHERE id > 30
UPDATE employee SET email = 'emretekin_35@outlook.com'  WHERE EXTRACT(YEAR FROM now()) > EXTRACT(YEAR FROM employee.birthday)
UPDATE employee SET name = 'XX' WHERE birthday IS NULL
UPDATE employee SET email = 'AA@gmail.com' WHERE name ILIKE '%a'
UPDATE employee SET name = 'CC' WHERE 3 > 5
```
## 4.İŞLEM
```sql
DELETE FROM employee WHERE id > 5
DELETE FROM employee WHERE name ILIKE '%A'
DELETE FROM employee WHERE length(employee.name) < 5
DELETE FROM employee WHERE EXTRACT(YEAR FROM now()) < 2024
DELETE FROM employee WHERE email ILIKE '%A%A%'
```

--------------------------------------------------------------------------------------------------------
# 9.ÖDEV
## 1.İŞLEM
```sql
SELECT city.city, country.country
FROM city INNER JOIN country ON city.country_id=country.country_id;
```
## 2.İŞLEM
```sql
SELECT concat(customer.first_name,' ',customer.last_name) AS "Full Name", payment.payment_id
FROM customer INNER JOIN payment ON customer.customer_id=payment.customer_id
```
## 3.İŞLEM
```sql
SELECT concat(customer.first_name,' ',customer.last_name) AS "Full Name", payment.payment_id
FROM customer INNER JOIN payment ON customer.customer_id=payment.customer_id
```

--------------------------------------------------------------------------------------------------------
# 10.ÖDEV
## 1.İŞLEM
```sql
SELECT country.country, city.city
FROM country LEFT JOIN city ON country.country_id=city.country_id
```
## 2.İŞLEM 
```sql
SELECT concat(customer.first_name,' ',customer.last_name) AS "Full Name", payment.payment_id
FROM payment RIGHT JOIN customer ON customer.customer_id=payment.customer_id
```
## 3.İŞLEM
```sql
SELECT concat(customer.first_name,' ',customer.last_name) AS "Full Name", rental.rental_id
FROM customer FULL OUTER JOIN rental ON customer.customer_id=rental.customer_id;
```

--------------------------------------------------------------------------------------------------------
# 11.ÖDEV
## 1.İŞLEM
```sql
(SELECT actor.first_name FROM actor)
UNION
(SELECT customer.first_name FROM customer);
```
## 2.İŞLEM
```sql
(SELECT actor.first_name FROM actor)
INTERSECT
(SELECT customer.first_name FROM customer);
```
## 3.İŞLEM
```sql
(SELECT actor.first_name FROM actor)
EXCEPT
(SELECT customer.first_name FROM customer);
```
## 4.İŞLEM
```sql
(SELECT actor.first_name FROM actor)
UNION ALL
(SELECT customer.first_name FROM customer);

(SELECT actor.first_name FROM actor)
INTERSECT ALL
(SELECT customer.first_name FROM customer);

(SELECT actor.first_name FROM actor)
EXCEPT ALL
(SELECT customer.first_name FROM customer);
```

--------------------------------------------------------------------------------------------------------
# 12.ÖDEV
## 1. SORGU
```sql
SELECT COUNT(*) AS "Ortlama Film Uzunluğundan Büyük Filmlerin Uzunluğu"
FROM(SELECT film.length 
	 FROM film 
	 WHERE film.length > (SELECT AVG(film.length) FROM film)) AS tablo;
```
## 2.SORGU
```sql
SELECT COUNT(*) AS "En yüksek rental rate değerine eşit olan film sayısı"
FROM(SELECT film.rental_rate FROM film WHERE film.rental_rate = 
(SELECT MAX(film.rental_rate) FROM film) ) AS tablo;
```
## 3.SORGU
```sql
SELECT *
FROM(SELECT * FROM film WHERE film.rental_rate = 
(SELECT MIN(film.rental_rate) FROM film) AND film.replacement_cost = 
(SELECT MIN(film.replacement_cost) FROM film)) AS tablo1;
```
## 4.SORGU
```sql
SELECT concat(customer.first_name,' ',customer.last_name) AS Musteri, COUNT(payment.customer_id) AS "Toplam Ödeme Sayısı"
FROM customer INNER JOIN payment ON customer.customer_id = payment.customer_id
GROUP BY payment.customer_id, Musteri
ORDER BY COUNT(payment.customer_id) DESC;
```

--------------------------------------------------------------------------------------------------------
# GENEL TEKRAR
## 1.SORGU
```sql
SELECT film.title, film.length, film.replacement_cost
FROM film
WHERE film.title ILIKE 'k%'
ORDER BY film.length DESC, film.replacement_cost ASC
LIMIT 4
```
## 2.SORGU
```sql
SELECT film.rating
FROM film
GROUP BY film.rating
ORDER BY COUNT(film.film_id) DESC
LIMIT 1
```
## 3.SORGU
```sql
SELECT concat(customer.first_name,' ',customer.last_name) AS Customers
FROM payment INNER JOIN customer ON customer.customer_id = payment.customer_id
GROUP BY Customers
ORDER BY COUNT(payment.customer_id) DESC
LIMIT 1
```
## 4.SORGU
```sql
SELECT category.name, COUNT(film_category.film_id) AS "Film Sayısı"
FROM category INNER JOIN film_category ON category.category_id=film_category.category_id
GROUP BY category.name
ORDER BY COUNT(film_category.film_id) ASC
```
## 5.SORGU
```sql
SELECT COUNT(*) AS "İsminde en az 4 tane 'E' bulunan film sayısı"
FROM(SELECT film.title
	 FROM film
	 WHERE film.title ILIKE '%e%e%e%e%') AS t1;
```
