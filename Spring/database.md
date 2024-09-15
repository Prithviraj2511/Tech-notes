### Batch Processing in spring boot jpa
The simplest and performant solution to tackle this issue is by performing an inner join with the temporary table created from IN clause values. In SQL/PostgreSQL, unnest function can be used to create a temporary table from an array. If array length is greater than 100, joins instead of IN clause can be considered to reduce execution time.
```text
SELECT *
FROM "contacts"
INNER JOIN
unnest(ARRAY[1,2,3,4,5, ... , 1000]) as cid
ON cid=contacts."contactId"
```
