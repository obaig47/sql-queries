# SQL Queries

###### [Problem Description](https://hackerrank-challenge-pdfs.s3.amazonaws.com/12889-the-pads-English?AWSAccessKeyId=AKIAJ4WZFDFQTZRGO3QA&Expires=1538427842&Signature=DadVShqj2QPpMDhDn3X1cm5HTD4%3D&response-content-disposition=inline%3B%20filename%3Dthe-pads-English.pdf&response-content-type=application%2Fpdf)
* Includes: Concatenation, Grouping, Ordering

`SELECT name || '(' || substr(occupation,1,1) || ')'
FROM occupations
ORDER BY name ASC;`

>SELECT 'There are a total of ' || count(occupation) || ' ' || lower(occupation) || 's.'
>FROM occupations
>GROUP BY occupation
>ORDER BY count(occupation), occupation ASC;
