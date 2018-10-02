# SQL Queries

### 1. [Problem Description](https://hackerrank-challenge-pdfs.s3.amazonaws.com/12889-the-pads-English?AWSAccessKeyId=AKIAJ4WZFDFQTZRGO3QA&Expires=1538427842&Signature=DadVShqj2QPpMDhDn3X1cm5HTD4%3D&response-content-disposition=inline%3B%20filename%3Dthe-pads-English.pdf&response-content-type=application%2Fpdf)
**Includes: Concatenation, Grouping, Ordering**

>SELECT name || '(' || SUBSTR(occupation,1,1) || ')'\
>FROM occupations\
>ORDER BY name ASC;

>SELECT 'There are a total of ' || count(occupation) || ' ' || lower(occupation) || 's.'\
>FROM occupations\
>GROUP BY occupation\
>ORDER BY COUNT(occupation), occupation ASC;

### 2. [Problem Description](https://www.hackerrank.com/rest/contests/master/challenges/weather-observation-station-3/download_pdf?language=English)
**Includes: Mod function**

>SELECT DISTINCT city\
FROM station\
WHERE MOD(id,2)= 0;


### 3. [Problem Description](https://www.hackerrank.com/rest/contests/master/challenges/weather-observation-station-5/download_pdf?language=English)
**Includes: Length function, Ordering, Aliasing**

>SELECT city, LENGTH(city) AS mlen\
>FROM station\
>ORDER BY mlen DESC, city ASC LIMIT 1;

>SELECT city, LENGTH(city) AS mlen\
>FROM station\
>ORDER BY mlen ASC, city ASC LIMIT 1;
