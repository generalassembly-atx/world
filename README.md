# World

Let's learn a few things about this crazy world! 

### Requirements

* The `world` example database from the [MySQL Documentation](https://dev.mysql.com/doc/index-other.html)

### ERD

Here's a model of what you now have loaded in the `world` database. The first row is the table name, the second is the primary key and finally the remaining are any additional attributes.
<img src="http://i.imgur.com/BirbWW5.png" />

## Exercises:

* Using `count`, get the number of cities in the USA 
  - `SELECT count(*) FROM city WHERE countrycode = 'USA';`
* Find out what the population and average life expectancy for people in Argentina (ARG) is
  - `SELECT population, lifeexpectancy FROM country WHERE code = 'ARG';`
* Using the `>` operator, find the countries where the average life expectancy is greater than 78 years 
  - `SELECT name FROM country WHERE lifeexpectancy > 78;`
* Using `IS NOT NULL, ORDER BY, LIMIT`, what country has the highest life expectancy? 
  - `SELECT * FROM country WHERE lifeexpectancy IS NOT NULL ORDER BY lifeexpectancy DESC LIMIT 1;`
* Using `LEFT JOIN, ON`, what is the capital of Spain (ESP)?
  - `SELECT city.name FROM country LEFT JOIN city ON country.capital = city.id WHERE country.code = 'ESP';`
* Using `LEFT JOIN, ON`, list all the languages spoken in the 'Southeast Asia' region
  - `SELECT cl.language FROM country c LEFT JOIN countrylanguage cl ON c.code = cl.countrycode WHERE c.region = 'Southeast Asia';`

## BONUS
Select 25 cities around the world that start with the letter 'F' in a single SQL query.
- `SELECT name FROM city WHERE SUBSTRING(name FROM 1 FOR 1) = 'F' LIMIT 25;`

## Licensing
All content is licensed under a CC­BY­NC­SA 4.0 license.
All software code is licensed under GNU GPLv3. For commercial use or alternative licensing, please contact legal@ga.co.
