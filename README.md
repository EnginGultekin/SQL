<br>
<br>



![Image](https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Postgresql_elephant.svg/160px-Postgresql_elephant.svg.png)  

<br>


 # SQL All Queries

> #### In this repo [Patika](https://academy.atika.dev/) all the assignments you have done in SQL training are available.

<br>

 - **SQL Practice 01 | WHERE and Comparison & Logical**

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