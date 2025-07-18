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

# **GROUP BY**
Using the sales_data table, write a SQL query to calculate the total quantity sold and the total sale_amount for each category.

Your query should return columns for the category, the sum of quantity as total_quantity, and the sum of sale_amount as total_sales_amount. Order the results by total_sales_amount in descending order.

Important columns:

category

quantity

sale_amount

``` sql

select category , 
sum(quantity) as total_quantity ,
sum(sale_amount) as total_sales_amount
from sales_data
group by category
order by total_sales_amount DESC;

```

# **GROUP BY multiple columns**

Create a query showing the total sales amount (AS total_sales_amount) and total number of items sold  (AS total_items_sold), grouped by category and sale_date. Order the results by category in ascending order and then by sale_date in ascending order.

Use the sales table with columns: category, sale_date, amount.

Note: You can assume one row in the table represents one item sold.

``` sql

select category , sale_date , 
sum(amount) as total_sales_amount ,
count(amount) as total_items_sold 
from sales 
group by category , sale_date
order by category , sale_date;

```

# **HAVING**

Find the cities with more than two transactions where the average transaction amount exceeds $150.00. List the city and the average transaction amount (AS AverageAmount), sorted by the average transaction amount in descending order.

Necessary Information

Table name: Sales

Columns to consider: City, Amount, TransactionID

``` sql

select City ,
AVG(Amount) as AverageAmount
from Sales 
Group by City
HAVING AVG(Amount) > 150 and Count(TransactionID) > 2
Order by AVG(Amount) desc ;


```


# **LENGTH, LOWER & UPPER**

Write a SQL query to find all reviews for product_id = 101 where the review text contains the word "great" (case insensitive), and order the results by the length of the review text (from shortest to longest).

Return the review_id, review_text, and the length of the review_text (use alias review_length).

Relevant table: 

customer_reviews


``` sql

select review_id , 
review_text , 
LENGTH(review_text) as review_length
from customer_reviews
where product_id = 101 
and LOWER(review_text) LIKE ('%great%')
order by review_text ASC;

```


# **Concatenate**

Write a single SQL query to concatenate the product name, category, and price into a single string for each product, formatted as: "Product Name - Category: Price". Use alias AS product_summary. Ensure the price is prefixed with a dollar sign ($), e.g. $1.99. Order the results by the product name in ascending order.

Available columns: product_id, name, category, and price from the products table.

``` sql

select  name || ' - ' || category || ': $' || price 
as product_summary from products order by name ASC

```





