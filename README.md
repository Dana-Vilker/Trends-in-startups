# Trends-in-startups
Codecademy SQL Aggregate Functions Project

SELECT *
FROM startups;

--the table has 8 columns. Total amount of conpanies in the table:

SELECT COUNT(name)
FROM startups;

-- there are 70 companies in the table. value of all companies together:

SELECT SUM(valuation)
FROM startups;

--the companies are worth 974,455,790,000 dollars. the highest amount raised by a startup:

SELECT MAX(raised)
FROM startups;

--the maximum amount of money raised by a companey is 11,500,000,000 dollars. however, suring the 'Seed' stage, the most raised was:

SELECT MAX(raised)
FROM startups
WHERE stage = 'Seed';

SELECT *
FROM startups;

--the table has 8 columns. Total amount of conpanies in the table:

SELECT COUNT(name)
FROM startups;

-- there are 70 companies in the table. value of all companies together:

SELECT SUM(valuation)
FROM startups;

--the companies are worth 974,455,790,000 dollars. the highest amount raised by a startup:

SELECT MAX(raised)
FROM startups;

--the maximum amount of money raised by a companey is 11,500,000,000 dollars. however, suring the 'Seed' stage, the most raised was 1,800,000:

SELECT MAX(raised)
FROM startups
WHERE stage = 'Seed';

--the oldest company on the list was founded in 1994:

SELECT MIN(founded)
FROM startups;

--calculating the average of a company's value:

SELECT AVG(valuation)
FROM startups;

-- and by category:

SELECT category, AVG(valuation)
FROM startups
GROUP BY category;

--the average of each category, rounded to 2 decimal places:

SELECT category, ROUND(AVG(valuation), 2)
FROM startups
GROUP BY category;

-- ordered from highest to lowest averages:

SELECT category, ROUND(AVG(valuation), 2)
FROM startups
GROUP BY 1
ORDER BY 2 DESC;

--finding all the companies by category:

SELECT category, COUNT(*)
FROM startups
GROUP BY category;

--large categories (social, moblie, education):

SELECT category, COUNT(*)
FROM startaps
GROUP BY category
HAVING COUNT(*) > 3;

--finding the average size of company by location:

SELECT location, AVG(employees)
FROM startups
GROUP BY location;

--the average for larger companies:

SELECT location, AVG(employees)
FROM startups
GROUP BY location
HAVING AVG(employees) > 500;
