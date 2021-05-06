# ShopifyTechnical
Technical Challenge of Shopify Data Science Internship

Part 1 answers can be found in the jupyter notebook .ipynb file.



Part 2 answers to the SQL questions can be found below:

a.	How many orders were shipped by Speedy Express in total?

SELECT COUNT(*)

FROM Shippers AS S

INNER JOIN Orders AS O

ON S.ShipperID = O.ShipperID

WHERE ShipperName = 'Speedy Express'


Final Answer: 54



     
b.	What is the last name of the employee with the most orders?

SELECT LastName, COUNT(O.EmployeeID)

FROM Employees AS E

INNER JOIN Orders AS O

ON E.EmployeeID = O.EmployeeID

GROUP BY O.EmployeeID

ORDER BY COUNT(O.EmployeeID) DESC

LIMIT 1

Final Answer: Peacock



c.	What product was ordered the most by customers in Germany?

SELECT ProductName, COUNT(ProductName)

FROM Products AS P

INNER JOIN OrderDetails AS OD

ON P.ProductID = OD.ProductID

INNER JOIN Orders AS O

ON OD.OrderID = O.OrderID

INNER JOIN Customers AS C

ON O.CustomerID = C.CustomerID

WHERE Country = 'Germany'

GROUP BY ProductName

ORDER BY COUNT(ProductName) DESC

LIMIT 1

Final Answer: Gorgonzola Telino



