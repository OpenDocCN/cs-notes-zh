# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P101：24_字符串函数.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Regenta and Gallow or M&G are performing an inventory review；

 they require a list of item names and their available quantities。

They can extract this data from their database using common MysSQl string functions。

Over the next few minutes， you'll learn how string functions can be used to perform tasks like this。

 and by the end of this video you'll be able to identify common MySQL string functions and explain how these functions are used to process and manipulate data in a MySQL database。

Let's take a moment to find out what database engineers mean by the termtrain functions。

String functions are used to manipulate string values； for example。

 adding strings together or extracting a segment of a string。

Here's a few examples of some commonly used string functions。

The concatenation function is used to add several strings together。

 and there's also the sub string function which extracts a segment of a string from a parent string。

 uppercase converts a string to uppercase and lowercase converts a string to lowercase。Next。

 let's explore the syntax of these strings to find out how they're used in a MySQL database。

A very simple example of a concatednation function begins with a select command。

 which calls a concatenation function。You then type a pair of parenthses in which you include the string values to be concatenated。

Ensure boat are contained within double quotes and separated by a comma。

Then include the Fr keyword and the name of the table that contains the data。

You can also use the wear clauses to specify a condition。

A more complex example of the concatenation function might involve extracting string values from two separate tables。

For example， the data that MG require is on two separate tables， items and MG orders。

M andG can pass their arguments in the select clause。

 identify the two tables they required in the F clause。

 and specify the condition in the where clause so that SQL filters the required data from the combination of the two tables。

This example might seem complicated， but don't worry。

 you'll explore it in more detail in a few moments when you help M&G query their database。

Let's continue to review string function syntax with substrs。

The syntax of a substr function is similar， but there are three arguments contained within the parenthesis。

 The first of these is the string itself。The next one is the start index。

 the point in the string at which the soap string must begin。

 and length refers to the length of the string portion that must be extracted。Next。

 let's review the syntax for the uppercase and lower case string functions。

M& G often convert the values in one column of a table to uppercase and the values in a second column to lowercase Here's how they perform this task。

An upper case string function begins with a select statement， an upper case function。In parenthsesis。

 write the name of the column whose values must be converted to uppercase。Finally。

 instructs SQL which table to target。A lower K string function is very similar。

The only difference is that the parentheses must contain the name of the column whose values are to be converted to lowercase。



![](img/e2b3f55fd548bc2b8b266f8841f208f6_1.png)

Next， let's look at how MG make use of string functions in a MysQL database。As you learned earlier。

 M&G need a list of item names and their available quantities ordered in the format， item name。

 order quantity。The item details are in the items table and the order details are in the MG orders table The items table records information on items in MG's inventory within the following columns。

 item ID， name and cost。The MG orders table records data on deliveries within the following columns。

 order ID， item ID， quantity， cost， order date， delivery date， and order status。

You can extract the required data from these tables using the concatenation string function。

Begin with a select command， then call the Concad function and write a pair of parenthheses。

Within the parenthses， pass the arguments， name and quantity。

These are the names of the columns for your output。

These columns stand for the Its table and MG orders table respectively。

Then add a hyphen in between the arguments to combine them。

Use a pair of single quotes for the hyphen and ensure all arguments are separated by commas。

Use a Fr keyword to specify the two tables。Finally。

 use aware clause to specify a condition that filters the required data from the combination of the two tables。

Then execute the query。MySQL extracts a table that shows the total quantity of each item in the inventory。

 the next task is to retrieve all string values in the order status column of the MG orders table in both upper and lower case。

You can target the string values from the order status column using the upper and lower K string functions。

In your select query， call the uppercase function and pass in the column name order status。

Then target the MG orders table with the F keyword。

Execute the query to retrieve all values in uppercase。To retrieve all values in lowercase。

 just type the same query again， but this time call the LK function。

Execute the query once more to retrieve all values in lower case。As part of their next task。

 M and G are reviewing an order from a client。They need to extract the first name of this client from the client's table。

The client's table records key information on clients and stores it in the following columns。

The clientient ID column in which the required client is assigned an ID of one， the client name。

 address， and contact number columns。You can retrieve the information M&G need by using the substring function to extract the relevant part of the string from the table's client name column value。

First， write a select statement and call the substr function followed by a pair of parenthsesis。

Then pass in the client name column as the first argument to the soap string function。

Pass in the start index as the second argument， which is the letter K or character one of the string。

And pass in the length of the string portion you need to extract as a third argument。

The client's name is Kisen， which is six letters long。So six is our third argument。

Then identify the table to target with the Fr keyword。Finally。

 add the wear clauses with the client's ID as of the condition。

Run the query to extract the client's first name。

![](img/e2b3f55fd548bc2b8b266f8841f208f6_3.png)

You've now helped M&G to complete their database tasks using string functions。

 and you should now be able to identify common MySQL string functions and explain how they're used to process and manipulate data great work。

