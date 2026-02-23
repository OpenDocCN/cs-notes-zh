# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P85：17_存储过程快速回顾.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Storward procedures provide database engineers with a useful way of storing and recalling code when needed。

 Over the next few minutes， you'll receive a quick recap of MysQL stored procedures and how they work。

😊，Let's begin with a look at how stored procedures can help little lemon。

Little Lemon checks the online bookings in its database every morning for a list of customers attending the restaurant that day。

They rewrite the same code each morning， to extract this data。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_1.png)

But they could instead invoke a stored procedure that extracts the required data without the need to rewrite large blocks of code every morning。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_3.png)

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_4.png)

Before you find out how they can do this， let's recap the basics of stored procedures。

A stored procedure is a block of code or one or more pre prepared queries that can be stored in your database。

 You can then invoke or call a stored procedure as required。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_6.png)

As you might already know， this is similar to how a function works。

 but don't forget the key difference between the two concepts。

Functions can only have input parameters， but a stored procedure can have both input and output parameters。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_8.png)

There are three main steps to complete when using stored procedures。

 You should already be familiar with these。 First， you create a stored procedure。

 Then you call a stored procedure。 And finally， you can drop or delete a stored procedure。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_10.png)

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_11.png)

Let's begin with a recap of the benefits of stored procedures。Your code is more consistent。

 The same code block is used each time it's invoked。 You know exactly what to expect from it。

 Your code is reusable。 You can use it as many times as you need across all your database tasks。

 and your code is easier to use and maintain。

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_13.png)

It's stored as one block that can be invoked， edited or dropped as required。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_15.png)

Next， let's quickly recap the syntax for creating a stored procedure。To create a stored procedure。

 begin with the C procedure command。 Then write the procedure name and a pair of parenthses to hold the parameters。

 Make sure that you include all required parameters within the parenthses。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_17.png)

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_18.png)

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_19.png)

Finally， write the rest of the procedure logic。

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_21.png)

Then when you need to invoke the procedure， you'll just type the call command followed by the procedure name。

Don't forget to include the parenthses。And if you need to remove or drop a stored procedure from your database。

 then just type the drop procedurec command followed by the procedure name。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_23.png)

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_24.png)

In this instance， you don't need to include any parenthses。

Little lemon can use this code to create a stored procedure that extracts the details of the customers due to visit the restaurant。

They begin with the create procedure command。 Then they name the procedure， daily。

 underscore customer， underscore details， and add the parameters。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_26.png)

Finally， they write the logic of the procedure。 Now， each morning。

 they just need to type the call command followed by daily underscore customer underscore details。

 The stored procedure then extracts the required customer data from the database。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_28.png)

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_29.png)

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_30.png)

So now that you've reapped the concept of stored procedures， you might be asking yourself。

 how do stored procedures relate to Python。Storward procedures increase the performance of Python applications and reduce traffic between the application and the Mysql database。

 The application only needs to send the name of the stored procedure and parameter to the database instead of a large block of SQL statements。



![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_32.png)

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_33.png)

![](img/ae8b8e0b0d44b7b99a0f57ad155b917e_34.png)

You're now familiar with the benefits of stored procedures and how to create。

 Invoke and drop them in a database。 You are now ready to learn how to perform these actions using Python。

 Great work。😊。