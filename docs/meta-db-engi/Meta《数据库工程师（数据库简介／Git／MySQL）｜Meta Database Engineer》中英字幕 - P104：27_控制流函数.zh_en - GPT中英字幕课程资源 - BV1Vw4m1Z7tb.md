# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P104：27_控制流函数.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

M andG need to determine which items in their inventory are turning a profit and which items are making a loss they can use a control flow function to carry out this task Over the next few minutes you'll explore control flow functions and by the end of this video you'll be able to identify common MysQl control flow functions and explain how these functions are used to process and manipulate data in a MysQql database。

So what are control flow functions in a MySQL database？

Control flow functions let you evaluate conditions and determine the execution path or flow of a query。

The most common control flow function used in a MysQL database is the case function。

The case function runs through a set of conditions contained within a case block and returns of value when the first condition is met。

Let's take a moment to explore how this function operates。

The case function is held within a case block。It operates in a similar manner to an if then L statement。

Once it finds a condition that's true， it returns the result。If no conditions are true。

 then it returns the value specified in the L's clause。

If there's no else clause and no conditions are true， it returns null。

So what does the full syntax of a case function statement look like？First， write a select keyword。

 followed by the name of one or more columns that contain the required values。

 This is followed by the case function， which denotes the start of the case block。

Next is the list of conditions which are written using the when and then clauses。

 the case block is then closed with the use of an end clause。

You can also add an alias for the expression depending on the needs of your code。Finally。

 identify the table to be queried。For example， M&G can use the case function to identify which items in their inventory are loss making and which ones have turned a profit。

They can extract the sales data for each item from the sales revenue table。

Any items with a value less than or equal to $25，000 are considered loss making。

Any items with a higher value are viewed as profitable。

MySQL displays the terms profit or loss next to each item's ID， depending on the result。



![](img/982630ee5b1d3f8f2b952639bb0f5e24_1.png)

Let's take a few minutes to explore MG's database and find out how they extract sales revenue data using a control flow function。

As you've just discovered， M&G need to check which items in their inventory have turned a profit this year。

Any items that have accrued at least $25，000 in sales are considered profitable。

All other items are making a loss and should be removed from sale。

The data they need is contained in the sales revenue table。The table has five columns。

One column called item ID which identifies each item in the inventory and an individual column for each of the four business quarters。

By checking if the value of the lowest quarter is less than or equal to 25，000。

 M&G can determine which items made a profit and which items made a loss。

The easiest way to perform this task is by using the case control flow function。First。

 write the select statement and target the item ID column。

This is the column you need to display results against。

So write the case keyword to begin your case block。In the case block。

 write when and give the condition with the least function。

Then list the quarterly sales columns in parenthesis。

The next set of steps involves the operator and conditions。Write a less than or equal to operator。

 and write then to specify what information you intend to display if the condition is true。

In this instance， you need to display the word loss。

Then write the L keyword and specify what information must be displayed if the condition is false。

In this case， it's profit。End the case block with the end keyword。

Now you need to create the aliases and identify the table to be targeted。

Use an as keyword to create the profit Los alias。This is the name of the column that the results of your case query are placed in。

Finally， write the from keyword and target the sales revenue table。

Execute the query to extract the results。 The results show that items 1，4，5。

 and 6 generated a profit， while items 2 and3 mean a loss。



![](img/982630ee5b1d3f8f2b952639bb0f5e24_3.png)

M andG have now completed their database tasks with your help。

 and you should now be able to use control flow functions when writing SQL select statements。

 nicely done。