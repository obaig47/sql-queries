# SQL Queries

### 1. [Problem Description](https://hackerrank-challenge-pdfs.s3.amazonaws.com/12889-the-pads-English?AWSAccessKeyId=AKIAJ4WZFDFQTZRGO3QA&Expires=1538427842&Signature=DadVShqj2QPpMDhDn3X1cm5HTD4%3D&response-content-disposition=inline%3B%20filename%3Dthe-pads-English.pdf&response-content-type=application%2Fpdf)
**Includes: Concatenation, Grouping, Ordering**
```SQL
SELECT name || '(' || SUBSTR(occupation,1,1) || ')'
FROM occupations
ORDER BY name ASC;

SELECT 'There are a total of ' || COUNT(occupation) || ' ' || LOWER(occupation) || 's.'
FROM occupations
GROUP BY occupation
ORDER BY COUNT(occupation), occupation ASC;
```
### 2. [Problem Description](https://www.hackerrank.com/rest/contests/master/challenges/weather-observation-station-3/download_pdf?language=English)
**Includes: Mod function**

>SELECT DISTINCT city\
FROM station\
WHERE MOD(id,2)= 0;


### 3. [Problem Description](https://www.hackerrank.com/rest/contests/master/challenges/weather-observation-station-5/download_pdf?language=English)
**Includes: Length function, Ordering, Aliasing**

>SELECT city, LENGTH(city) AS len\
FROM station\
ORDER BY len DESC, city ASC LIMIT 1;

>SELECT city, LENGTH(city) AS len\
FROM station\
ORDER BY len ASC, city ASC LIMIT 1;

### 4. [Problem Description](https://www.hackerrank.com/rest/contests/master/challenges/weather-observation-station-18/download_pdf?language=English)
**Includes: Round function, Absolute value function**

>SELECT ROUND(ABS(MIN(lat_n)-MAX(lat_n)) + ABS(MIN(long_w)-MAX(long_w)),4) AS ManhattanDistance\
FROM station;

### 5. [Problem Description](https://www.hackerrank.com/rest/contests/master/challenges/weather-observation-station-19/download_pdf?language=English)
**Includes: Square root function, Power (exponent) function**

>SELECT ROUND(SQRT(POWER(MIN(lat_n)-MAX(lat_n),2) + POWER(MIN(long_w)-MAX(long_w),2)),4) AS EuclidianDistance\
FROM station;

### 6. [Problem Description](https://www.hackerrank.com/rest/contests/master/challenges/weather-observation-station-20/download_pdf?language=English)
**Includes: Median function**

>SELECT ROUND(MEDIAN(lat_n),4) AS NorthLatMedian\
FROM station;

### 7. [Problem Description](https://www.hackerrank.com/rest/contests/master/challenges/weather-observation-station-11/download_pdf?language=English)
**Includes: Union, Substring function, Lower function, In clause**

>SELECT city\
FROM station\
WHERE (LOWER(SUBSTR(city,1,1)) IN ('a','e','i','o','u') AND SUBSTR(city,-1) NOT IN ('a','e','i','o','u'))\
UNION                                                               
SELECT city\
FROM station\
WHERE (LOWER(SUBSTR(city,1,1)) NOT IN ('a','e','i','o','u') AND SUBSTR(city,-1) IN ('a','e','i','o','u'))\
UNION\
SELECT city\
FROM station\
WHERE (LOWER(SUBSTR(city,1,1)) NOT IN ('a','e','i','o','u') AND SUBSTR(city,-1) NOT IN ('a','e','i','o','u'));

### 8. [Problem Description](https://www.hackerrank.com/rest/contests/master/challenges/occupations/download_pdf?language=English)
**Includes: Row Number function, Partition By, Pivot Table, Nulls Last**

>SELECT * FROM (\
  SELECT Doctor, Professor, Singer, Actor FROM(\
    SELECT name, occupation, ROW_NUMBER() OVER (PARTITION BY occupation ORDER BY name)\
    FROM occupations\
  )\
  PIVOT (\
    MAX(name)\
    FOR (occupation)\
    IN ('Doctor' as Doctor, 'Professor' as Professor, 'Singer' as Singer, 'Actor' as Actor)\
  )\
)\
ORDER BY Doctor ASC NULLS LAST, Professor ASC NULLS LAST, Singer ASC NULLS LAST, Actor ASC NULLS LAST;
