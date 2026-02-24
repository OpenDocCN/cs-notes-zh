# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P96：4_关系数据库模型归一化回顾.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

At this stage of your database engineering journey。

 you should be familiar with the concept of database normalization when working with database tables。

 you can often encounter anomalies that can lead to inconsistent data you can solve these anomalies by applying the normalization process over the next few minutes。

 you'll recap the importance of database normalization and the methods for applying it within your databases。

 Men data and Gallo or M and G are building a database that holds data related to product orders。

They've built some tables that contain order， product， and client data。

 but these tables also contain several challenges around anomalies review the database normalization process。

 then help M&G to resolve these anomalies within their database tables。



![](img/f5ad66ffb29227df0a60042fa0dd591c_1.png)

Let's begin with a quick recap of database normalization。

 normalmalization is an important process used in database systems。

 It involves structuring tables in order to reduce data duplication。

 avoid data modification implications and simplify data queries from the database。

 As you learned earlier， database tables that don't follow the normalization process often give rise to anomalies。

 the most common of these anomalies include and insertion anomaly。

 This is when new data is inserted into a table which then requires the insertion of additional data。



![](img/f5ad66ffb29227df0a60042fa0dd591c_3.png)

An update anomaly， this occurs when you attempt to update a record in a table column only to discover that this results in further updates across the table。

And a deletion anomaly， this is when the deletion of a record of data causes the deletion of more than one set of data required in the database。

 So let's quickly recap how the three levels of data normalization can be used to help resolve or avoid these anomalies。

 First normal form sometimes referred to as1NF enforces data atity and eliminates unnecessary repeating groups of data in database tables。

 In other words， there must only be one instance of a value per field。



![](img/f5ad66ffb29227df0a60042fa0dd591c_5.png)

![](img/f5ad66ffb29227df0a60042fa0dd591c_6.png)

Repeated groups of data cause data of redundancy and inconsistency。 For example。

 M G's products table stores the engagement and diamond ring products in the same cell of the item column。

 This violates the atomomicity rule。 There should only be one instance of a value per column。

 You can resolve this issue by creating two new tables。



![](img/f5ad66ffb29227df0a60042fa0dd591c_8.png)

First， create a products table that holds all data related to the product entity。

Assign the table a productss ID column to identify each unique record。

 then create a client's table that holds all data related to the client's entity， and once again。

 create an ID column to identify each unique record。



![](img/f5ad66ffb29227df0a60042fa0dd591c_10.png)

![](img/f5ad66ffb29227df0a60042fa0dd591c_11.png)

This solution removes all unnecessary repeated data from your tables Next。

 let's look at second normal form for a table to meet second normal form or2NF。

 it must already be in first normal form， it also cannot contain any relationships built on functional or partial dependency。

The table must be defined with a composite primary key。 For example。

 the delivery status table from M and G has a composite primary key that consists of the order Id and the product I。

 to comply with the second normal form。 You must identify if theres any nonkey attributes that depend on one part of the composite key。

 The order data in the delivery status table is a nonkey attribute。

 It can be determined by using the order I column only。 This is called partial dependency。

 This isn't permitted in second normal form because all nonkey attributes must be determined by using both parts of the composite key。

 This can be fixed by removing the order date attribute from the delivery status table。

 In other words， keep the order date column in the order table。

 Your table now meets second normal form。 All non primarymary key attributes depend only on the primary key value。

 Finally， there's third normal。

![](img/f5ad66ffb29227df0a60042fa0dd591c_13.png)

![](img/f5ad66ffb29227df0a60042fa0dd591c_14.png)

Third normal form or 3NF removes unnecessary data duplication。

This ensures data consistency and integrity。Again， a table must adhere to first and second normal form before you can apply third normal form。

Third normal form resolves issues of transitive dependency。



![](img/f5ad66ffb29227df0a60042fa0dd591c_16.png)

This is when nonkey attributes are dependent on one another for example。

 the city and zip code in the M&G orders table are non-key attributes， however。

 it's possible to determine the city value based on the zip code value and if you change the zip code value you need to change the city name value This means a nonkey attribute depends on another nonkey attribute which violates the third normal form to solve this you can split the table into two tables and orders table with all related data and a city table with two columns the zip code and city name。



![](img/f5ad66ffb29227df0a60042fa0dd591c_18.png)

All non key attributes are now determined only by the primary key in each table。

 so the tables now meet the requirements of 3 NF。

![](img/f5ad66ffb29227df0a60042fa0dd591c_20.png)

Applying the three fundamental forms of normalization is a good way to resolve any anomalies that could arise within your database。

 you can resolve any issues of data redundancy and inconsistency by modeling your database so that it's easy to use。

 access and query。You should now be familiar with the process of normalization and how to apply it to your database Great work。

