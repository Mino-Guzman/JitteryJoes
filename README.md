# Group 7 MIST 4610 Group Project 1

## Team Members
1) Mino Guzman
2) Sydney Pratt https://github.com/scp31975/Jiterry-Joe-s-
3) Ally McVay https://github.com/allymcvay/JitteryJoes
4) Casey Whichard https://github.com/caseywhichard/Team-7-MIST-4610-Group-Project-1

## Problem Description 
The goal of this project is to design and build a relational database that represents the core operations of Jittery Joe’s, a multi‑location coffee shop. The Store serves as the central entity, connecting employees, inventory, equipment, customers, and daily transactions. The database models how each store manages menu items, merchandise, suppliers, loyalty programs, and customer orders. We aim to accurately represent these relationships, generate realistic sample data, and populate each entity accordingly. Once built, the database will support functional SQL queries that provide meaningful business insights into sales, inventory levels, customer behavior, and overall store performance.

## Explanation of Data Model
As mentioned above, our model is based on the structure of a global coffee chain. The Store is the central entity that represents each physical coffee shop location. Each store hires many employees, so we established a one‑to‑many relationship between the Store and Employees entities. Also, several pieces of inventory and equipment are assigned to one store, so there is a one‑to‑many relationship with the Store and Inventory and with the Store and Equipment entities as well. Finally, one store can take many orders from customers, so we created a one-to-many relationship between the Store and Order entities. 
What drives this business is sales, so customers interact with the business through order purchases. These purchases can consist of orders of food, drinks, and merchandise. We concluded that one customer can place many orders, so we created a one‑to‑many relationship between the Customers and Order entities. Orders can consist of merchandise as well, so using the same idea that one customer can purchase several pieces of merchandise, we placed a one-to-many relationship between the Customers and Merchandise entities. Finally, customers typically participate in the loyalty program to earn points with the hopes of getting deals on future purchases. Each customer can only have one loyalty account attached to their name, so this is modeled as a one‑to‑one relationship between the Customers and Loyalty entities.
Customers can make several payments on order purchases, since they can return to the store whenever they would like.So, we established a one-to-many relationship between the Customers and Payment entities. We also assume that each order only consists of one payment, so we created a one-to-one relationship between the Order and Payment entities. 
The company requires supplies on hand that go into inventory. In order to generate supplies, the company requires a supplier or suppliers to supply these items. Each supplier can ship several supplier items, which led us to establish a one-to-many relationship between the Suppliers and SupplierItem entities.
Overall, the data model, as shown below, successfully captures the relationships between the activities that take place in a global coffee chain. It provides a detailed understanding on the customer orders, inventory and equipment levels, the payment process, and hiring distributions. 


![My Image](unnamed.png)


## Data Dictionary 
 Customers
 
![Customers Data](customers.data.png)

Employees

![Employees](employees.data.png)


Equipment

![Equipment](equipment.data.png)


Inventory

![Inventory](inventory.data.png)


Loyalty

![Loyalty](Loyalty.data.png)


MenuItem

![Menu Items](menuItem.data.png)


Merchandise

![Merchandise](Merchandise.data.png)


OrderItem

![Order Items](OrderItem.data.png)


Orders

![Orders](Orders.data.png)


Payment

![Payment](Payment.data.png)


Store

![Store](Store.data.png)


SupplierItem

![Supplier Items](supplierItem.data.png)


Suppliers

![Suppliers](Suppliers.Data.png)


## Queries

![Table](table.png)



Query 1: List all Cafe Managers that are seasonal


![Query 1](query1.png)


This query allows leadership to quickly identify which café managers are employed on a seasonal basis. Seasonal managers typically work only during peak periods, such as the academic year or high‑traffic months. Knowing exactly who these managers are helps the organization anticipate staffing gaps when the season ends. This ensures that stores relying on seasonal leadership receive the necessary support, training, or replacement coverage ahead of time. By isolating seasonal managers, the café can better plan for continuity, maintain service quality, and allocate resources to locations that may need additional managerial oversight once seasonal staff depart.


Query 2: Show all items on the menu that have never been ordered


![Query 2](query2.png)


This query helps managers identify which menu items have never been purchased. Items with zero orders may signal low visibility, poor appeal, or unnecessary complexity on the menu. By isolating these products, managers can decide whether to promote them, adjust pricing, or remove them to reduce waste and streamline inventory.



Query 3: Show all orders and status


![Query 3](query3.png)


Show all supplier orders and their status. This query pulls information from the SupplierItem and Suppliers tables to show what items have been shipped, when they were shipped, and the status of the supplier. It provides visibility into the supply chain and helps track incoming inventory.



Query 4: Show revenue by payment type


![Query 4](query4.png)


This query shows how much revenue comes from each card type, helping managers understand which cards customers use most. This makes it easier to plan for reliable payment processing, manage card‑related fees, and ensure the café’s systems support the most common payment methods efficiently.



Query 5: Find the average order value by store


![Query 5](query5.png)


Find average order value by store.This query calculates the average order value for each store and pairs it with key performance metrics such as total orders received and total revenue generated. By comparing stores based on their average order value, managers can quickly identify which locations are driving higher‑value transactions. Sorting the results in descending order makes it easier to prioritize high‑performing stores and recognize those that may need additional support, pricing adjustments, or promotional strategies to improve their average order size.




Query 6: Find the most popular menu items by total quantity sold


![Query 6](query6.png)


Find the most popular menu items by total quantity sold. We ranked the popularity of each item based on the item’s total quantity sold. The query ranked each menu item by the number of units sold across all orders, while also calculating the total revenue generated from each item. The information provided became a useful way to identify bestsellers and top revenue-driving items.



Query 7: Show stores with above average revenue


![Query 7](query7.png)


This query identifies which stores generate more revenue than the overall average across all locations. By first calculating each store’s total revenue and then using a subquery to determine the average of those totals, managers can clearly see which stores are outperforming expectations. Highlighting above‑average stores helps leadership recognize strong performers, allocate resources effectively, and understand which operational practices may be contributing to higher revenue.



Query 8: Show stores with low inventory that need to reorder

![Query 8](query8.png)


This query identifies any item at a store whose current quantity has dropped below its designated reorder level. It also calculates how many additional units are needed to reach that threshold again. By sorting the results from most urgent to least urgent, managers can quickly see which stores and items require immediate restocking. This helps prevent stockouts, supports smoother operations, and ensures that high‑demand products remain available to customers.



Query 9: Show the customer who spend the most


![Query 9](query9.png)



This query identifies the customer with the highest total spending across all their orders. The subquery calculates each customer’s total amount spent, finds the maximum value, and then matches that amount back to the specific customer’s name and ID. This helps managers quickly recognize top‑spending customers, understand purchasing behavior, and potentially target these high‑value customers for loyalty rewards or personalized promotions.



Query 10: Find which menu items generate above average revenue


![Query 10](query10.png)



This query identifies which menu items generate more revenue than the average item on the menu. Like the store‑level version, it calculates each item’s total revenue and compares it to the overall average, returning only the strongest performers. This helps managers quickly see which products drive the most sales, guiding decisions about promotion, pricing, and menu placement to maximize revenue.


## Assumption
LoyaltyID is stored redundantly to preserve the customer’s loyalty tier at the time of the order/payment, since loyalty status can change over time.



