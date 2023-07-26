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