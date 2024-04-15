# Assignment 2: Practice with Single Row Functions
Review the CITY table structure shown below and answer the questions that follow.
<img width="536" alt="city" src="https://github.com/Kritika30032002/OracleSQL/assets/83400697/d39d636a-98be-4394-8780-1dcb489c06d3">

## Questions for this assignment


1. Considering the data exists in the city table, write a query that will return records similar to what is shown below for those cities that have the COUNTRYCODE of 'cbd' :

"NEW YORK CITY has the population of 8,500,000"

"LOS ANGELES has the population of 632,000"

Note: I'd like you to use functions in the SELECT statement to solve this problem.


2. Write a query that would show the first three letters and the last three letters of the DISTRICT capitalized and separated by a dash.

Note: I'd like you to use functions in the SELECT statement to solve this problem.


3. Review the following SQL statement:

SELECT MONTHS_BETWEEN(LAST_DAY('15-JAN-12') + 1, '01-APR-12') FROM DUAL;

Considering the database is configured for the given date format, what will be the result of executing the query?


4. TRUE or FALSE Question:

Giving the date arguments in chronological order to the MONTHS_BETWEEN function will result in an error.


5. Which of the following is true regarding character functions?

A). They always accept characters as parameters and nothing else.

B). They always return a character value.

C). They are generally used to process text data.

D). They generally have the letters CHAR somewhere in the function name.



6. Which of the following is true regarding functions in SQL?

A). They never return a value.

B). They often return a value.

C). They always return a value.

D). There is no consistent answer to whether they return a value or not.



7. Review the SQL Statement:

SELECT SUBSTR('2009', 1, 2) || LTRIM('1124', '1') FROM DUAL;

What will be the result of executing the SQL Statement?

A). 2024

B). 221

C). 20124

D). A syntax error



8. TRUE or FALSE Question:

Review the syntax of how the NULLIF function is used:

NULLIF( expr1, expr2 )

The NULLIF function returns expr1 if expr1 and expr2 are not equal.



9. TRUE or FALSE Question:

The TO_CHAR function converts data from various data types to character data. It can accept characters, a number or a date as valid arguments.



## *Do not scroll past here without trying out the assignment yourself*



Instructor Solutions for this assignment


1. Considering the data exists in the city table, write a query that will return records similar to what is shown below for those cities that have the COUNTRYCODE of 'cbd' :

"NEW YORK CITY has the population of 8,500,000"

"LOS ANGELES has the population of 632,000"

Note: I'd like you to use functions in the SELECT statement to solve this problem.

```
SELECT CONCAT(CONCAT(UPPER(name), ' has the population of '), population)

FROM city

WHERE LOWER(countrycode) = 'cbd';
```


2. Write a query that would show the first three letters and the last three letters of the DISTRICT capitalized and separated by a dash.

Note: I'd like you to use functions in the SELECT statement to solve this problem.

```
SELECT CONCAT(CONCAT(UPPER(SUBSTR(district, 1, 3)), ' - '),

       UPPER(SUBSTR(district, LENGTH(district) - 2)))

FROM city;
```


3. Review the following SQL statement:

SELECT MONTHS_BETWEEN(LAST_DAY('15-JAN-12') + 1, '01-APR-12') FROM DUAL;

Considering the database is configured for the given date format, what will be the result of executing the query?

```
-2
```

The reason -2 will be returned is that the LAST_DAY function will transform the value of '15-JAN-12' TO '31-JAN-12' and then the result of that will be added to 1. So the first argument of the MONTHS_BETWEEN function ends up being '01-FEB-12'. Difference between the 2 dates results in a -2.



4. TRUE or FALSE Question:

Giving the date arguments in chronological order to the MONTHS_BETWEEN function will result in an error.

```
FALSE.
```

You may give the 2 dates in any order you please. If the dates are in chronological order, the result will be a negative number. If the dates are in reverse chronological order, the answer will be a positive number.



5. Which of the following is true regarding character functions?

A). They always accept characters as parameters and nothing else.

B). They always return a character value.

C). They are generally used to process text data.

D). They generally have the letters CHAR somewhere in the function name.

```
Answer: C
```


6. Which of the following is true regarding functions in SQL?

A). They never return a value.

B). They often return a value.

C). They always return a value.

D). There is no consistent answer to whether they return a value or not.

```
Answer: C
```


7. Review the SQL Statement:

SELECT SUBSTR('2009', 1, 2) || LTRIM('1124', '1') FROM DUAL;

What will be the result of executing the SQL Statement?

A). 2024

B). 221

C). 20124

D). A syntax error

```
Answer: A
```


8. TRUE or FALSE Question:

Review the syntax of how the NULLIF function is used:

NULLIF( expr1, expr2 )

The NULLIF function returns expr1 if expr1 and expr2 are not equal.

```
TRUE
```


9. TRUE or FALSE Question:

The TO_CHAR function converts data from various data types to character data. It can accept characters, a number or a date as valid arguments.

```
TRUE
```
