# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P102：25_日期函数.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

M and G are reviewing some recent orders delivered to the store。

 they must determine how many days have passed between the date these items were delivered and the day they were ordered。

 they can complete this task using date functions。In this video you'll explore date functions and learn how to identify common MySQL date functions and explain how these functions are used to process and manipulate data in a MySQL database First。

 let's find out what date functions are。Date functions are used in a MySQL database to extract time and date values in a range of different formats。

M&G often use date functions to identify key time and date details for customer orders。

Commonly used date functions that M&G take advantage of include current date。

 which returns the date in year month date format， and current time， which returns the time in hours。

 minutes， seconds format。There's also date format， which is used to format a date according to a given format。

 once that format is valid in MySQL and date difference identifies the number of days between two date values。

Perhaps M&G can use the date difference function to find out how many days have passed between orders。

 but before you find out how let's take a few moments to explore the syntax for these functions。

In most instances， date functions are written as select statements。

To extract today's date in year month date format， just type select the current date function and open parenthsesis。

For the current time in hours， minutes， seconds format， type select。

 the current time function and open parenthsesis。However。

 the syntax becomes a bit more complicated with date format and date difference。

To change the date format， type the date format function and open parenthsesis。

Within the parenthesis， type today's date in standard SQL year month date format enclosed in double quotation marks。

Then input a valid MySQL format in a pair of single quotes。

You can refer to the further readinging section at the end of this lesson for a list of valid formats。

To determine the number of days between two date values。

 type the select command and date difference function followed by parenthesis。Within the parenthses。

 type the first and second date values in year month date format and ensure both are enclosed in double quotation marks。



![](img/9b1eba4fb1783d0534d18fa763c3e904_1.png)

Then run the query to create the output。Now that you've reviewed this syntax for date functions。

 let's see if you can use this knowledge to help M&G。

MNG need to complete a series of time and date tasks using date functions。

The first of these tasks is extract the current date and time。To retrieve this data just right。

 select command followed by the current date function。

And a second select command followed by the current time function。

Execute these queries to return the current date and time。

Now M&G needs you to format a date by displaying the month name of a given date。

You can do this by using select and calling the date format function。

Then pass in the order date as the first argument。Type the required format to get the full month name。

Finally， identify the required table。Execute the query to create the output。For the final task。

 M&G must determine the number of days between the delivery date and order date for their most recent orders。

As you discovered earlier， the date difference function can be used to complete this task。

The delivery data is contained in the MG orders table。

The table records delivery data within the following columns。Order ID， item ID， quantity， cost。

 order date， delivery date， and order status。To complete this task。

 you need to focus on the values from the delivery date and order date columns。First。

 write a select query and call the date differenceence function。

Pass the values from the delivery date column as the first argument。

Then pass the value from the order date column as the second argument。

Use the F clauses to target the MG orders table。And finally。

 use the wear clauses to filter out the records that do not have a null delivery date。Once executed。

 the query reveals the number of days between the delivery and order dates for the most recent orders。



![](img/9b1eba4fb1783d0534d18fa763c3e904_3.png)

M&G now know how many days pass between the delivery date and order date for their most recent orders。

 and you should now be capable of using common MySQL date functions to process and manipulate data well done。



![](img/9b1eba4fb1783d0534d18fa763c3e904_5.png)