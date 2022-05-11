# Shopify-Intern-challege

Question 1: Given some sample data, write a program to answer the following: click here to access the required data set

On Shopify, we have exactly 100 sneaker shops, and each of these shops sells only one model of shoe. We want to do some analysis of the average order value (AOV). When we look at orders data over a 30 day window, we naively calculate an AOV of $3145.13. Given that we know these shops are selling sneakers, a relatively affordable item, something seems wrong with our analysis. 

The calculation for AOV is revenue/the number of orders. User 607, who ordered 17 times, to the amount of 704000 each, increased the revenue compared to orders skewing the AOV to the high end. The other metrics that could be used are Median Order Value and Mode order value. Mode Order Value helps predict what the next order maybe, but for analysis of this 30-day window, Median Order Value would be better since this metric takes into account the highs and lows of the data. The Median Order Value is 284.

Question 2: For this question, you’ll need to use SQL. Follow this link to access the data set required for the challenge. Please use queries to answer the following questions. Paste your queries along with your final numerical answers below.

How many orders were shipped by Speedy Express in total?
Speedy Express shipped 54 orders
After joining the Shippers and Orders tables, which would show which orders were shipped by specific shipping companies, I selected the count of orders shipped by Speedy Express


SELECT Count(*) FROM Shippers
JOIN Orders
ON Shippers.ShipperID = Orders.ShipperID
WHERE Shippers.ShipperName = "Speedy Express";

What is the last name of the employee with the most orders?
The Last name of the employee with the most orders is Peacock, with 40 orders
By joining the Employees and Orders tables, I was able to see which employees made which orders, which I grouped by the last name, and displayed in descending order.


SELECT Count(*) AS Count, LastName From Employees
JOIN Orders
On Employees.EmployeeID = Orders.EmployeeID
