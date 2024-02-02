SQL - Types of joins

Innerjoins

the first type of join that you might perform is an innerjoin. INNER JOIN returns rows matching on a specified column that exists in more than one table.

It only returns rows where there is a match, but like other types of joins, it returns all specified columns from all joined tables. For example, if the query joins two tables with SELECT *, all columns in both of the tables are returned.

Note: if a column exists in both of the tables, it is returned twice when SELECT * is used.

The syntax of inner join:

To write a query using INNER JOIN, you can use the following syntax:

    SELECT *
    FROM employees
    INNER JOIN machines ON employees.device_id = machines.device_id;

you must specify the two tables to join by including the first or left table after FROM and the second or right table after INNER JOIN

after the name of the right table, use the ON keyword and the = operator to indicate the column you are joining the tables on. It's important that you specify both the table and column names in this portion of the join by placing a period (.) between the table and the column.

in addition to selecting all columns, you can select only certain columns. For example, if you only want the join to return the username, operating_system, and the device_id columns, you can write this query:

    SELECT username, operating_system, employee_id
    FROM employees
    INNER JOIN machines ON employees.device_id = machines.device_id;

Note: in the example query, username and operating_system only appear in on of the two tables, so they are written with just the column name. On the other hand, because device_id appears in both tables, it's necessary to indicate which on to return by specifying both the table and column name (employees.device_id).

Outerjoins

outer joins expand what is returned from a join. Each type of outer join returns all rows from either one table or both tables.

left joins

when joining two tables, LEFT JOIN returns all the records of the first table, but only returns rows of the second table that match on a specified column.

The syntax for using LEFT JOIN is demonstrated in the following query:

    SELECT *
    FROM employees
    LEFT JOIN machines ON employees.device_id = machines.device_id;

As with all joins, you should specify the first or left able as the table that comes after FROM and the second or right table as the table that comes after LEFT JOIN. in the example query, because employees is the left table, all of its records are returned. Only records that match on the device_id column are returned from the right table, machines.

Rightjoins

When joining two tables, RIGHT JOIN returns all of the records of the second table, but only returns rows from the first table that match on a specified column.

The following query demonstrates the syntax for RIGHT JOIN:

    SELECT *
    FROM employees
    RIGHT JOIN machines ON employees.device_id = machines.device_id;

RIGHT JOIN had the same syntax as LEFT JOIN, with the only difference being the keyword RIGHT JOIN instructs SQL to produce different output. The query returns all records from machines, which is the second or right table. Only matching records are returned from employees, which is the first or left table.

Note: you can use LEFT JOIN and return the exact same results if you use the tables in reverse order. The following RIGHT JOIN query returns the exact same results as the LEFT JOIN query demonstrated in the previous section:

    SELECT *
    FROM machines
    RIGHT JOIN employees ON employees.device_id = machines.device_id;

All that you have to do is switch the order of the tables that appear before and after the keyword used for the join, and you will have swapped the left and right tables.

Full out joins

FULL OUTER JOIN returns all records from both tables. You can think of it as way of completely merging two tables.

you can review the syntax for using FULL OUTER JOIN in the following query:

    SELECT *
    FROM employees
    FULL OUTER JOIN machines ON employees.device_id = machines.device_id;

the results of a FULL OUTER JOIN query include all records from both tables. Similar to INNER JOIN, the order of tables does not change the results of the query.

Key takeaways:

when working in SQL, there are multiple ways to join tables. all joins return the records that match on a specified column. INNER JOIN will return only these record. Outer joins also return all other records from one or both of the tables. LEFT JOIN returns all records from the first or left table, RIGHT JOIN returns all records from the second or right table, and FULL OUTER JOIN returns all records from both tables.

You've explored a lot about SQL, including applying filters to SQL queries and joining multiple tables together in a query.  There's still more that you can do with SQL. This reading will explore an example of something new you can add to your SQL toolbox: aggregate functions. You'll then focus on how you can continue learning about this and other SQL topics on your own.

Aggregate functions
In SQL, aggregate functions are functions that perform a calculation over multiple data points and return the result of the calculation. The actual data is not returned.

There are various aggregate functions that perform different calculations:

COUNT returns a single number that represents the number of rows returned from your query.

AVG returns a single number that represents the average of the numerical data in a column.

SUM returns a single number that represents the sum of the numerical data in a column.

Aggregate function syntax
To use an aggregate function, place the keyword for it after the SELECT keyword, and then in parentheses, indicate the column you want to perform the calculation on.

For example, when working with the customers table, you can use aggregate functions to summarize important information about the table. If you want to find out how many customers there are in total, you can use the COUNT function on any column, and SQL will return the total number of records, excluding NULL values. You can run this query and explore its output:

    SELECT COUNT(firstname)
    FROM customers;

    +------------------+
    | COUNT(firstname) |
    +------------------+
    |               59 |
    +------------------+

The result is a table with one column titled COUNT(firstname) and one row that indicates the count.

If you want to find the number of customers from a specific country, you can add a filter to your query:

    SELECT COUNT(firstname)
    FROM customers
    WHERE country = 'USA';

    +------------------+
    | COUNT(firstname) |
    +------------------+
    |               13 |
    +------------------+

With this filter, the count is lower because it only includes the records where the country column contains a value of 'USA'.

There are a lot of other aggregate functions in SQL. The syntax of placing them after SELECT is exactly the same as the COUNT function.

Continuing to learn SQL

SQL is a widely used querying language, with many more keywords and applications. You can continue to learn more about aggregate functions and other aspects of using SQL on your own.

Most importantly, approach new tasks with curiosity and a willingness to find new ways to apply SQL to your work as a security analyst. Identify the data results that you need and try to use SQL to obtain these results.

Fortunately, SQL is one of the most important tools for working with databases and analyzing data, so you'll find a lot of support in trying to learn SQL online. First, try searching for the concepts you've already learned and practiced to find resources that have accurate easy-to-follow explanations. When you identify these resources, you can use them to extend your knowledge.

Continuing your practical experience with SQL is also important. You can also search for new databases that allow you to perform SQL queries using what you've learned.

Key takeaways

Aggregate functions like COUNT, SUM, and AVG allow you to work with SQL in new ways. There are many other additional aspects of SQL that could be useful to you as an analyst. By continuing to explore SQL on your own, you can expand the ways you can apply SQL in a cybersecurity context.
