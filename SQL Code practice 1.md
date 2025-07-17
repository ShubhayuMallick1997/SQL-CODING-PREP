# **SELECT**
From the below books  table only select the columns title and publication_year.

``` sql 
select title, publication_year
from books;

```

# **SELECT & ORDER BY**

Given the books table, write a SQL query to:

Select all columns from the books table.

Order the results by the price in descending order.

``` sql
select * from books
order by price DESC;

```

# **SELECT DISTINCT & LIMIT**

Write a single SQL query to retrieve the first 5 unique genres in ascending alphabetical order.

Column: genre in the books table.

This query will test your ability to filter out duplicates and limit the result set.

Remember, the result should only show distinct genres, meaning if there are multiple books of the same genre, that genre should only appear once in your result set. 
Also, ensure the genres are listed in alphabetical order and limit the output to the first 5 genres.

``` sql
select distinct genre 
from books
order by genre asc
limit 5;

```

# **COUNT()**

Given the table employees, write a single SQL query to count the total number of employees in the company.

Table Name: employees

Relevant Columns: id (you can count rows using any column, but id is usually preferred for its uniqueness)

Note: To get the correct solution you need to use COUNT() in all-caps even though in reality both solutions work equally.

``` sql
select COUNT(id)
from employees;

```

# **WHERE**

Write a SQL query to find all products in the 'Electronics' category. Select only the name of the product and the price.

You need to use only the SELECT, WHERE, and ORDER BY clauses to achieve this. Sort the results by price in ascending order.

Table and Column Names:

Table: products

Columns: product_id, name, category, price\

``` sql
select name,price
from products
where category = 'Electronics'
order by price ASC;

```

# **WHERE operators**

Write a SQL query to find all products (only select name and price) that have a price of more than 200.

You need to use only the SELECT, WHERE, and ORDER BY clauses to achieve this. Sort the results by price in ascending order.

Table and Column Names:

Table: products

Columns: product_id, name, category, price

``` sql
select name , price 
from products
where price > 200
order by price ASC;

```

# **WHERE with AND/OR**

Write a SQL query to find all products in the 'Electronics' category that have a price of more than 200.

You need to use only the SELECT, WHERE, and ORDER BY clauses to achieve this. Sort the results by price in ascending order.

Select only product name and and price.

Necessary Table and Column Names:

Table: products

Columns: product_id, name, category, price

``` sql
select name , price
from products
where category = 'Electronics' and price > 200
order by price ASC;


```

# **BETWEEN**
Write a single SQL query to find all transactions from the the table sales that occurred between '2024-01-10' and '2024-02-10', inclusive. Display the transaction ID, date, and amount. Order the results by the date of the transaction.

Make sure you return:

id

date

amount

Order by the transaction date.

``` sql
select id , date ,amount
from sales
where date between '2024-01-10' and '2024-02-10'
order by date;

```

# **IN operator**

Write a single SQL query to select all distinct customer IDs who ordered either a 'Laptop', 'Tablet', or 'Smartphone'. Order the result by customer ID in ascending order.

Table Name: orders
Important Columns: customer_id, product_name

``` sql
select distinct customer_id
from orders
where product_name IN ('Laptop','Tablet','Smartphone')
order by customer_id ASC;

```

# **LIKE**

Write a SQL query to find all reviews that mention the word "love" (case insensitive) in their review text. Your query should return the CustomerName, ProductID, and ReviewText.

Table Name: CustomerReviews

Column Names: CustomerName, ProductID, ReviewText

``` sql
select CustomerName, ProductID, ReviewText 
from CustomerReviews
where ReviewText LIKE '%love%';

```

# **Aggregate Functions**

Your challenge is to write a single SQL query to find the total number of orders and the average order amount from the Orders table. The solution should include only orders made in August 2023.

Use the aliases TotalOrders and AverageOrderAmount in your query.

Column names:

OrderID , 

Amount ,

OrderDate

Remember, you know how to use COUNT(), AVG(), WHERE, BETWEEN, and other basic SQL commands without grouping.

``` sql

select count(OrderID) as TotalOrders , 
avg(Amount) as AverageOrderAmount 
from orders;

```



