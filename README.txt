--Q1:
SELECT COUNT(*)
FROM countries
WHERE continent = 'Africa';
--Q2:
SELECT countries.continent, SUM (population_years.population)
FROM countries
JOIN population_years
  ON countries.id = population_years.country_id
WHERE continent = 'Oceania'
AND year = 2005;
--Q3:
SELECT countries.continent, population_years.year, AVG (population_years.population)
FROM countries
JOIN population_years
  ON countries.id = population_years.country_id
WHERE continent = 'South America'
AND year = 2003;
--Q4:
SELECT countries.name, population_years.year, min (population_years.population)
FROM countries
JOIN population_years
  ON countries.id = population_years.country_id
AND year = 2007;
--Q5:
SELECT countries.name, avg (population_years.population) AS 'Population'
FROM countries
JOIN population_years
  ON countries.id = population_years.country_id
AND countries.name = 'Poland';
--Q6:
SELECT name 
FROM countries
WHERE name LIKE '% The%';
--Q7:
SELECT countries.continent, sum(population_years.population) AS '2010 Population' 
FROM countries
JOIN population_years
    ON countries.id = population_years.country_id
	WHERE year = 2010
	GROUP BY countries.continent;
