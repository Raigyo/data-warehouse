

## Product and category dimension (snowflakes)

### Execute sql queries

![](_exercices_img/demo-01.png)

We use the SQL in the file `Ressources/Raw-Data/01-dimensional-modeling/SQL+Script_DM_Example.txt`

We execute the queries step by step.

![](_exercices_img/demo-02.png)

### Import csv

![](_exercices_img/demo-03.png)

We import csv from  `Ressources/Raw-Data/01-dimensional-modeling/products.csv`

![](_exercices_img/demo-04.png)

![](_exercices_img/demo-05.png)

![](_exercices_img/demo-06.png)

![](_exercices_img/demo-08.png)

In case of problem check if the binary path (on Windows) for Postres.

![](_exercices_img/demo-07.png)

The query `SELECT * FROM products  ` should return:

![](_exercices_img/demo-09.png)

### Create separate table for Category

```sql
SELECT distinct
category
INTO category
FROM products
```

![](_exercices_img/demo-10.png)

Then:

```sql
SELECT 
category 
,ROW_NUMBER() OVER (ORDER BY category)
FROM category
```

Should return:

![](_exercices_img/demo-11.png)

Then:

```sql
SELECT 
row_number() over (ORDER BY category) AS category_id
,category 
INTO category_table
FROM category
```



```sql
SELECT * FROM
category_table
```

![](_exercices_img/demo-12.png)

```sql
SELECT * FROM products
```

![](_exercices_img/demo-13.png)