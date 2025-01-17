# Database Queries

### Display the ProductName and CategoryName for all products in the database. Shows 76 records.
SELECT ProductName, CategoryName FROM Products as p JOIN Categories as c ON p.CategoryID = c.CategoryID

### Display the OrderID and ShipperName for all orders placed before January 9, 1997. Shows 161 records.
SELECT o.OrderID, ShipperName FROM Orders as o JOIN Shippers as s ON o.ShipperID = s.ShipperID WHERE o.OrderDate < '1997-01-09'

### Display all ProductNames and Quantities placed on order 10251. Sort by ProductName. Shows 3 records.
SELECT p.ProductName, od.Quantity FROM OrderDetails as od JOIN Products as p ON p.ProductID = od.ProductID WHERE od.OrderID = 10251 ORDER BY p.ProductName

### Display the OrderID, CustomerName and the employee's LastName for every order. All columns should be labeled clearly. Displays 196 records.
SELECT OrderID, CustomerName, LastName as EmployeeLastName FROM Orders as o JOIN Customers as c ON c.CustomerID = o.CustomerID JOIN Employees as e ON e.EmployeeID = o.EmployeeID

### (Stretch)  Displays CategoryName and a new column called Count that shows how many products are in each category. Shows 9 records.
SELECT CategoryName, COUNT(p.ProductName) as ProductsCount FROM Products as p JOIN Categories as c ON p.CategoryID = c.CategoryID GROUP BY CategoryName

### (Stretch) Display OrderID and a  column called ItemCount that shows the total number of products placed on the order. Shows 196 records. 
SELECT OrderID, COUNT(p.ProductName) as ItemCount FROM OrderDetails as od JOIN Products as p ON od.ProductID = p.ProductID GROUP BY OrderID