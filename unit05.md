### Putting it all together

Using the Dellstore2 database, complete the following queries based on requests from the CEO at your company.
Items in *italics* are to be included in an aggregate email of all of your responses to the instructor.

1 => "Get me a list of all of our products with above average sales".
*Send me the number of items in this list.*

SELECT AVG(quantity) FROM orderlines

with aboveAverage as( select * from products join orderlines on products.prod_id = orderlines.prod_id where orderlines.quantity > 2) Select count(*)from aboveAverage



2 => Based on the first list, *tell me the top 3 selling titles*.

select title from products join inventory on products.prod_id = inventory.prod_id order by sales desc limit 3

3 => Get me a list of how many orders have been placed by Sam Williams.
*How many total orders Have been placed?*

with williams as (select customerid from customers where customers.firstname = 'Sam' and lastname = 'Williams'),  orders as ( select * from orders join williams on williams.customerid = orders.customerid) select COUNT(orderid) from orders


*When was Sam Williams most active ?*

(When did he place his orders) ?

with williams as (select customerid from customers where customers.firstname = 'Sam' and lastname = 'Williams'), orders as ( select * from orders join williams on williams.customerid = orders.customerid) select orderdate from orders  

4 => What are the two cheapest PINOCCHIO movies? (PINOCCHIO is the second part of the title of many of our movies).



*send me the names and prices of the two cheapest PINOCCHIO movies*

*send me the PINOCCHIO query so I can re-use it later*

with titleP as (select * from products where title like '%PINOCCHIO') select * from titleP order by price desc limit 2


 5 => Add an auto-incrementing 'id' column to the "reorder" table, then populate that table
with two or three lines of data. Remember that when you add rows to an auto-incrementing table,
you don't have to include 'id' as one of the columns to populate. It should do it for you.
In postgres,  SERIAL is the equivalent to auto-increment.
(Hint: syntax for this is back on Unit01.md)


Question:  if you delete the final record of an auto-incrementing table, and that final record's auto-incremented
value (id) was 9, what will be the the value of the next record inserted into the table?  In other words, delete 9,
and what will the next record be?

*send me the answer to this question*

Email all of your answers **IN ONE EMAIL** to complete this assignment.
