<br>
<br>



![Image](https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Postgresql_elephant.svg/160px-Postgresql_elephant.svg.png)  

<br>


 # SQL All Queries

> #### In this repo [Patika](https://academy.atika.dev/) all the assignments you have done in SQL training are available.

<br>

 - **SQL Practice 01 | WHERE and Comparison & Logical**
 - **SQL Practice 02 | BETWEEN and IN**
 - **SQL Practice 03 | LIKE and ILIKE**
 - **SQL Practice 04 | DISTINCT and COUNT**
 - **SQL Practice 05 | ORDER BY | LIMIT and OFFSET**
 - **SQL Practice 06 | Aggregate Functions**
 - **SQL Practice 07 | GROUP BY | HAVING**
 - **SQL Practice 08 | Creating a Table | Updating Data**
 - **SQL Practice 09 | INNER JOIN**

<br>


## SQL Practice 01 | WHERE and Comparison & Logical 

<br>
<br>

1-)  Sort the data in the <strong> title </strong> and <strong>description</strong>  columns in the <strong> film </strong> table.


```

SELECT title, description FROM film

```

<br>
<br>
<br>

2-)  Sort the data in all columns in the <strong>film </strong> table with the film length (length) greater than 60 <strong>AND</strong> less than 75.




```

SELECT * FROM film
WHERE length > 60 AND length < 75

```

<br>
<br>
<br>

3-) Sort the data in all columns in the <strong>film</strong> table with <strong>rental_rate</strong> 0.99  <strong>AND</strong>  <strong>replacement_cost</strong> 12.99  <strong>OR</strong> 28.99 

```

SELECT * FROM film
WHERE rental_rate = 0.99 
AND (replacement_cost = 12.99 
OR replacement_cost = 28.99)

```

<br>
<br>
<br>

4-) What is the value in the <strong>last_name</strong> column of the whose value is 'Mary' in the <strong>first_name</strong> column of the <strong>customer</strong> table?


```

SELECT last_name FROM customer
WHERE first_name = 'Mary'

```


<br>
<br>
<br>

5-)  Sort the data in the <strong>film</strong> table whose <strong>length (length)</strong> is <strong>NOT</strong> greater than 50, <br> but whose <strong>rental_rate</strong> is <strong>NOT</strong> 2.99 <strong>OR</strong> 4.99.
```

SELECT * FROM film
WHERE length <= 50 
AND NOT (rental_rate = 2.99 OR rental_rate = 4.99);

SELECT * FROM film
WHERE 
NOT length > 50 
AND 
NOT (rental_rate = 2.99 OR rental_rate = 4.99);

```

<br>

- **To Return - <a href="https://github.com/EnginGultekin/SQL">Click</a>**


<br>
<br>

## SQL Practice 02 | BETWEEN and IN


<br>    
<br>

1-)  Sort the data in all columns in the <strong>film</strong> table provided that the <strong>replacement_cost</strong> value is greater than 12.99, equal and less than 16.99 (use BETWEEN - AND structure).

```

SELECT * FROM film 
WHERE replacement_cost BETWEEN 12.99 AND 16.99

```

<br> 
<br>
<br>

2-) Sort the data in the <strong>first_name</strong> and <strong>last_name</strong>  columns in the  <strong>actor</strong> table provided that <strong>first_name</strong> is 'Penelope' or 'Nick' or 'Ed'. (Use the IN operator.)

```

SELECT first_name, last_name FROM actor 
WHERE first_name IN ('Penelope', 'Nick', 'Ed')

```

<br>
<br>
<br>

3-) Sort the data in all columns in the <strong>film</strong> table with <strong>rental_rate</strong> 0.99, 2.99, 4.99 <strong>AND replacement_cost</strong> 12.99, 15.99, 28.99. (Use the IN operator.)

```

SELECT * FROM film 
WHERE rental_rate IN (0.99, 2.99)
AND replacement_cost IN (12.99,15.99, 28.99)

```

<br>

- **To Return - <a href="https://github.com/EnginGultekin/SQL">Click</a>**

<br>
<br>


## SQL Practice 03  | LIKE and ILIKE

<br>

```

~~    LIKE        "Implements what is written"
~~*   ILIKE       "Applies what is written regardless of lower or upper case"
!~~   NOT LIKE
!~~*  NOT ILIKE

```
<br>
<br>


1-) List the country names in the <strong>country</strong> column of the <strong>country</strong> table, starting with the <strong>'A'</strong> character and ending with the <strong>'a'</strong> character.

```

SELECT country FROM country
WHERE country ~~ 'A%a'; 

SELECT country FROM country
WHERE country LIKE 'A%a'; 

```



<br>
<br>
<br>

2-) List the country names in the <strong>country</strong> column of the <strong>country</strong> table, consisting of at <strong>least 6 characters</strong> and ending with the <strong>'n'</strong> character.

```

SELECT country FROM country 
WHERE country LIKE '_____%n' 

```


<br>
<br>
<br>

3-)  In the <strong>title</strong> column of the <strong>film</strong> table, list the film names containing <strong> at least 4 'T'</strong> characters, regardless of upper or lower case letters.

```

SELECT title FROM film 
WHERE title ~~* '%T%T%T%T%'; 

SELECT title FROM film 
WHERE title ILIKE '%T%T%T%T%'; 

```


<br>
<br>
<br>

4-)  From the data in all the columns in the <strong>film</strong> table, sort the data that starts with the <strong>title</strong>  'C' character, has a length greater than 90 and a <strong>rental_rate</strong> of 2.99.


```

SELECT * FROM film 
WHERE title LIKE 'C%' 
AND length > 90 
AND rental_rate = 2.99

```



<br>

- **To Return - <a href="https://github.com/EnginGultekin/SQL">Click</a>**

<br>
<br>


## SQL Practice 04 | DISTINCT ve COUNT

<br>
<br>


1-) Sort the different values in the <strong>replacement_cost</strong> column in the <strong>film</strong> table.

```

SELECT DISTINCT replacement_cost FROM film

```

<br>
<br>
<br>

2-) How many different data are there in the <Strong>replacement_cost</strong>  column in the <strong>film</strong> table?

```

SELECT COUNT (DISTINCT replacement_cost) FROM film

```

<br>
<br>
<br>

3-)  How many of the films <strong>(title)</strong> in the <strong>film</strong> table start with the character <strong>T</strong> and at the same time the <strong>rating</strong> is equal to <strong>'G'</strong>?

```

SELECT COUNT(*) FROM film 
WHERE title LIKE 'T%' 
AND rating = 'G'

```

<br>
<br>
<br>


4-)  How many of the country names (country) in the <strong>country</strong> table consist of <strong>5</strong> characters?


```

SELECT COUNT(DISTINCT country) FROM country 
where country like '_____'

```

<br>
<br>
<br>

5-) How many of the city names in the <strong>city</strong> table end with the character <strong>'R'</strong> or <strong>r</strong>?

```

SELECT COUNT(city) FROM city 
WHERE city ILIKE 'R%'


SELECT COUNT(city) FROM city 
WHERE city ~~* 'R%'

```

<br>

- **To Return - <a href="https://github.com/EnginGultekin/SQL">Click</a>**

<br>
<br>


## SQL Practice 05 | ORDER BY | LIMIT and OFFSET

<br>
<br>


1-) List the 5 longest (length) film in the <strong>film</strong> table and the film name (title) ends with the <strong>'n'</strong> character.


```

SELECT title, length
FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5

```


<br>
<br>
<br>

2-) List the shortest (length) second(6,7,8,9,10)  5 film(6,7,8,9,10) in the <strong>film</strong>  table and the film title ends with the 'n' character.


```

SELECT title, length
FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
OFFSET 5
LIMIT 5

```


<br>
<br>
<br>

3-) Sort the first 4 data, provided that store_id is 1 in the descending order according to the <strong>last_name</strong> column in the <strong>customer</strong> table.

```

SELECT *
FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4

```


<br>

- **To Return - <a href="https://github.com/EnginGultekin/SQL">Click</a>**

<br>
<br>

## SQL Practice 06 | Aggregate Functions 

<br>


```
 MIN, MAX, SUM, AVG, COUNT ...
```

<br>
<br>


1-) What is the average of the values in the <strong>rental_rate</strong> column in the <strong>film</strong> table?


```

SELECT ROUND(AVG(rental_rate),2) hacer
FROM film

```



<br>
<br>
<br>

2-) How many of the film in the <strong>film</strong> table start with the character <strong>'C'</strong>?


```

SELECT COUNT(*)
FROM film
WHERE title LIKE 'C%'

```

<br>
<br>
<br>

3-) Among the film in the <strong>film</strong> table, how many minutes is the longest (length) film with a <strong>rental_rate</strong> equal to 0.99?

```

SELECT MAX(length) 
FROM film 
WHERE rental_rate = 0.99

```

<br>
<br>
<br>

4-) How many different <strong>replacement_cost</strong> values are there for the fims longer than 150 minutes in the <strong>film</strong> table?


```

SELECT COUNT(DISTINCT replacement_cost) 
FROM film 
WHERE length > 150;

```

<br>

- **To Return - <a href="https://github.com/EnginGultekin/SQL">Click</a>**

<br>
<br>


## SQL Practice 07 | GROUP BY | HAVING


<br>
<br>

1-) Group the films in the <strong>film</strong> table according to their <strong>rating</strong> values.

```

SELECT rating, COUNT(*) FROM film
GROUP BY rating;

```


<br>
<br>
<br>

2-) When we group the films in the <strong>film</strong> table according to the <strong>replacement_cost</strong> column, list the replacement_cost value with more than 50 films and the corresponding number of films.


```

SELECT replacement_cost, COUNT(*)
FROM film
GROUP BY replacement_cost
HAVING COUNT(*) > 50

```

<br>
<br>
<br>

3-) What are the customer numbers corresponding to the store_id values in the <strong>customer</strong> table?

```

SELECT store_id, COUNT(*) 
FROM customer
GROUP BY store_id;

```

<br>
<br>
<br>

 4-) After grouping the city data in the <strong>city</strong> table according to the <strong>country_id</strong> column, share the country_id information with the highest number of cities and the number of cities.


```

SELECT country_id, COUNT(*) 
FROM city
GROUP BY country_id
ORDER BY COUNT(*) DESC
LIMIT 1

```

<br>

- **To Return - <a href="https://github.com/EnginGultekin/SQL">Click</a>**

<br>
<br>


## SQL Practice 08 | Creating a Table | Updating Data"

<br>
<br>

1-) Let's create a table in your <strong>test</strong> database with <strong>employee</strong>  name column information id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100).


```

CREATE TABLE employee (
  id SERIAL PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  birthday DATE,
  email VARCHAR(100)
)


```

<br>
<br>
<br>

2-) Let's add 50 pieces of data to the <strong>employee</strong> table we created using the 'Mockaroo' service.

```

insert into employee (name, birtday, email) 
values 
    ('Costa Catto', null, null),
    ('Kariotta Sainsberry', null, 'ksainsberry1@gov.uk'),
    ('Sunny Newland', null, 'snewland2@prweb.com'),
    ('Kelcie Harmstone', '1962-09-23', 'kharmstone3@reuters.com'),
    ('Allister Gullis', '1953-03-21', 'agullis4@disqus.com'),
    ('Stephine Gelletly', '2001-07-07', 'sgelletly5@japanpost.jp'),
    ('Torrey Rickarsey', '1965-04-10', 'trickarsey6@t.co'),
    ('Carney Havesides', '1951-11-02', 'chavesides7@theatlantic.com'),
    ('Alejandra Morstatt', '1987-02-06', 'amorstatt8@ftc.gov'),
    ('Tobi Freeborne', '1973-05-20', 'tfreeborne9@ask.com'),
    ('Beverie Slowey', '1999-04-07', null),
    ('Muhammad Donnett', '1968-11-22', 'mdonnettb@yahoo.co.jp'),
    ('Gale Obbard', null, 'gobbardc@mail.ru'),
    ('Alfredo Joddens', '1961-03-11', 'ajoddensd@blog.com'),
    ('Darcy Klimkin', '1986-09-19', 'dklimkine@ihg.com'),
    ('Fanechka Ebunoluwa', null, 'febunoluwaf@prlog.org'),
    ('Jerrome Bealing', '1958-08-23', 'jbealingg@ustream.tv'),
    ('Arnold Turn', null, 'aturnh@myspace.com'),
    ('Ingram Meyer', '1968-09-03', 'imeyeri@yahoo.co.jp'),
    ('Gisella Stickles', '1999-03-16', 'gsticklesj@free.fr'),
    ('Nick Monk', '1978-08-24', null),
    ('Flint Godrich', null, 'fgodrichl@flickr.com'),
    ('Alvina Fiennes', null, 'afiennesm@fotki.com'),
    ('Guido Erickssen', '1975-08-15', 'gerickssenn@hubpages.com'),
    ('Dallas Cowley', '1993-03-27', 'dcowleyo@multiply.com'),
    ('Gordon Adamsen', '1947-08-06', 'gadamsenp@reuters.com'),
    ('Flynn Ausher', '1985-06-24', 'fausherq@imdb.com'),
    ('Jeffrey Bougen', '1959-04-11', 'jbougenr@illinois.edu'),
    ('Philippe Belfelt', '1960-09-10', 'pbelfelts@fc2.com'),
    ('Olive Connor', '1978-12-25', 'oconnort@edublogs.org'),
    ('Broderick Drain', '1970-09-12', 'bdrainu@google.cn'),
    ('Brandais Bassill', '1986-04-18', 'bbassillv@bigcartel.com'),
    ('Jasmine Cayzer', '1996-09-12', 'jcayzerw@tripadvisor.com'),
    ('Fred Clayton', '1978-10-06', 'fclaytonx@shutterfly.com'),
    ('Noreen Phizackarley', null, 'nphizackarleyy@1und1.de'),
    ('Rabbi Royston', '1955-01-07', 'rroystonz@va.gov'),
    ('Scott Getcliff', '1977-10-18', 'sgetcliff10@jigsy.com'),
    ('Bernetta McComish', '1983-11-05', 'bmccomish11@dell.com'),
    ('Allys Ingliss', '1980-01-22', 'aingliss12@stanford.edu'),
    ('Clare McKinless', '1980-01-19', 'cmckinless13@merriam-webster.com'),
    ('Calhoun Montague', null, 'cmontague14@google.com'),
    ('Alaine Foulks', '1964-12-12', 'afoulks15@seesaa.net'),
    ('Barnard Glendzer', '1999-05-11', 'bglendzer16@php.net'),
    ('Ferris Goreway', '1960-10-31', 'fgoreway17@phpbb.com'),
    ('Vachel McCarly', null, 'vmccarly18@arstechnica.com'),
    ('Ailina Eadie', '1952-05-04', 'aeadie19@godaddy.com'),
    ('Timmie Rutter', '1998-11-08', 'trutter1a@nytimes.com'),
    ('Darrin Gladdish', '1989-01-23', 'dgladdish1b@meetup.com'),
    ('Elga Worboy', '1955-10-03', 'eworboy1c@macromedia.com'),
    ('Preston Mellers', '1951-10-18', 'pmellers1d@mail.ru');


```

<br>
<br>
<br>

3-) Let's do 5 <strong>UPDATE</strong> operations that will update the other columns according to each of the columns.


```

// Update the (name) column:

UPDATE employee
SET name = 'Alfonzo David'
WHERE name LİKE 'A%'
RETURNING *;


// Update the (birthday) column:

UPDATE employee
SET birthday = '2000-04-26'
WHERE name = 'Costa Catto'
RETURNING *;


// Update the (email) column:

UPDATE employee
SET email = 'beverie@mail.com'
WHERE id = 11
RETURNING *;


// Update the (name) and (birthday) columns:

UPDATE employee
SET name = 'Darwin Smith',
    birthday = '1988-12-12'
WHERE email = 'snewland2@prweb.com';
RETURNING *;


// Update all columns:

UPDATE employee
SET name = 'Gumball Watterson',
    birtday = '1999-01-10',
    email = 'gamball@wat.com'
WHERE id = 8
RETURNING *;


```


<br>
<br>
<br>


4-) Let's do 5 <strong>DELETE</strong> operations that will delete the relevant row according to each of the columns.


```

DELETE FROM employee
WHERE name ='Alfonzo David'
RETURNING *;

DELETE FROM employee
WHERE id = 36;

DELETE FROM employee
WHERE 
name = 'Darwin Smith' 
AND 
birthday = '1988-12-12';

DELETE FROM employee
WHERE email = 'beverie@mail.com';

DELETE FROM employee
WHERE id > 14
RETURNING *;

```


<br>

- **To Return - <a href="https://github.com/EnginGultekin/SQL">Click</a>**

<br>
<br>


## SQL Ödev 09 | INNER JOIN

<br>
<br>

1-) Write the <strong>INNER JOIN</strong> query where we can see the (city) and (country) names in the <strong>city</strong> table and the <strong>country</strong> table together.



```

SELECT city, country
FROM city
INNER JOIN country ON city.country_id = country.country_id;

```


<br>
<br>
<br>

2-) Write the <strong>INNER JOIN</strong> query where we can see the <strong>customer</strong> table and the (payment_id) in the <strong>payment</strong> table and the first_name and last_name names in the customer table together.


```

SELECT payment.payment_id, customer.first_name, customer.last_name
FROM customer
INNER JOIN payment ON customer.customer_id = payment.customer_id;

```


<br>
<br>
<br>

3-) Write the <strong>INNER JOIN</strong> query where we can see the <strong>customer</strong> table and the (rental_id) in the <strong>rental</strong> table and the first_name and last_name names in the customer table together.


```

SELECT rental.rental_id, customer.first_name, customer.last_name
FROM customer
INNER JOIN rental ON customer.customer_id = rental.customer_id;

```


<br>

- **To Return - <a href="https://github.com/EnginGultekin/SQL">Click</a>**

<br>
<br>