Updates
# Store-API

new implementaion for store api


Testing Api viability for consumption by frontend


. File Upload (local and cloudinary)
 Send Email (nodemailer,ethereal and sendgrid )
. Stripe Payment
 E-Commerce API
. Auth Workflow (verify email, reset password)



A simple database structure for a project with customers, products, and orders could have three tables:

Customers:

CustomerID (Primary Key)

Name

Address

Phone

Products:

ProductID (Primary Key)

Name

Description

Price

Orders:

OrderID (Primary Key)

CustomerID (Foreign Key)

ProductID (Foreign Key)

Quantity



An SQL query to list customers with the most orders first would be:


SELECT c.Name, COUNT(o.OrderID) as OrderCount
FROM Customers c
INNER JOIN Orders o ON c.CustomerID = o.CustomerID
GROUP BY c.Name




This query joins the Customers and Orders table on the CustomerID, groups the results by customer name, and orders the results by the number of orders in descending order.

To find the most popular product, you can use a query like this:


SELECT p.Name, SUM(o.Quantity) as QuantitySold
FROM Products p
INNER JOIN Orders o ON p.ProductID = o.ProductID
GROUP BY p.Name
ORDER BY QuantitySold DESC
LIMIT 1;


on the Proups the results by product name, and orders the results by the total quantity sold in descending
