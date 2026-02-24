# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P123：14_MySQL事务.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

How often have you encountered an error during a critical activity forcing you to begin the task from the beginning。

 This can be particularly stressful when you're working on many related queries at the same time。

 Thankfully， you can use MysQL transaction to roll your database back to a previous state。

 In this video， you'll learn how to manage database transactions with MysQL transaction statements。😊。

Lucky shhrub are updating new sales in their orders table and the stock levels in their products table to carry out this transaction。

 Lucky Shub need to create and execute several different queries。

 but they could encounter an error at any point in the process。 For example。

 the Internet connection could fail while inserting data into the table。

 and this could result in invalid data or an incomplete transaction。 However。

 if such an event were to occur。 Lucky Shrub can roll back their database and restore it to its original state using transaction commands。

 So what are transaction in MysQL。😊，As you just saw with Luc shhrub。

 a transaction in MySQL is one or more queries that can be committed permanently to the database and the database can be rolled back to its original state if any of the queries fail to execute as required MySQL provides the following set of statements for managing database transaction Start transaction Be or begin work commitit and roll back Let's explore each of these statements in more detail Start transaction is the standard SQL statement for starting a transaction process。

 This syntax marks the point that you'll return to should you decide to roll back the process。

 So begin your syntax with start transaction then list your SQL statement underneath for example。

 Luc shhrub can begin their database updates with a start transaction statement and then follow this with a list of the required SQL queries However。

 Start transaction isn't the only way to begin a transaction with MysQL， you can also use the begin。

😊，or begin work aliases as alternative ways to initiate a transaction。

 whichever method you choose once you've finished typing your SQL statements and you're happy with the result。

 then it's time to commit the transaction to the database you can use the commit statement to commit the transaction changes permanently to the database Just type the commit statement at the end of your code block but what if you encounter an error during your transaction like Luc shrub and their internet connectivity issues or maybe you typed incorrect code。

 executed the wrong statement or entered incorrect data You can use the rollback command to roll back the current transaction and cancel the changes made to the database Just add the rollback statement to the end of your SQL statement to return to your start transaction point However it's important to remember that the rollback statement must be enacted before you commit your SQL statements once you roll back your code you then need to type the correct SQL statements and once you're happy with these statements type commit to commit the changes to the database。

😊，So let's quickly recap the process， begin your transaction with start transaction。

 type your required SQL statements and use commitit to commit your changes to the database。

 and should you encounter any errors or other issues just use the rollback statement to return to your start transaction point now that you're familiar with MySQL transactions and the related statements。

 let's see if you can help Lucky Srub update the sales and stock levels in their database tables。😊。



![](img/a84d66e174f0c8070891e9c952b05e66_1.png)

A client with an I D of C L 1 has just placed an online order for 10 bags of artificial grass。

 This item has a product I of P1 in the products table。 There are currently 100 bags in stock。

 This number must be updated to 90 once the client's order is processed。 First， type。

 start transaction to determine the point you can roll back to if an error occurs。 Now。

 you need to add the required SQL statement。 The first is an insert into statement。

 This statement inserts a new set of values into the required columns in the orders table for the client's order。

 Then type an update statement that updates the number of bags of artificial graph in the products table by deducting 10 units from the current stock level。

 The next step is to use a select statement that creates an inner join between the orders and products table using the product I D key。

 which is common to both tables。😊，Execute this statement to check if the transaction was completed as you expected。

 Unfortunately， it looks like there was a mistake。 These updates have been applied to the client with the I D of C L 11。

 It seems you typed the wrong client I D in your code。No problem。

 You can restore the data by using the rollback statement。 Now。

 check the orders and products tables again， using select statements。

 All data has been restored to its original state。 So let's type， start transaction once again。

 followed by the same SQL statements as before。 only this time。

 make sure to update the correct client details。 Once you've completed your new set of SQL statements。

 Check that the output is， as you expected。 Great， this time， all details are correct。

 You can now type commit to commit your changes to the database。

 You should now be able to manage transactions in your MysQL databases using transaction statements。

 Great work。😊。

![](img/a84d66e174f0c8070891e9c952b05e66_3.png)