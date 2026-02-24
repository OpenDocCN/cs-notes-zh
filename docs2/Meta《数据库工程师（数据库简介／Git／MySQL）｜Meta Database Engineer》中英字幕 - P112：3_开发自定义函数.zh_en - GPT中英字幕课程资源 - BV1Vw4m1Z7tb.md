# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P112：3_开发自定义函数.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

You might already be familiar with My SQL's built in functions。

 But what if none of these built in functions meet your project's needs， No problem。

 You can develop your own user defined functions。 In this video。

 you'll find out what user defined functions are and learn how to create your own。

Lucky Srub are having a sale in which they're offering a 10% cent discount on selected products。

 but rewriting the same statement for every product during every transaction would be very time consuming。

 Instead， Lucky shrub need you to create a user defined function that they can invoke when needed to calculate these discounts before you begin helping Lucky Shrub。

 Let's make sure you understand what database engineers mean by the term user defined functions。

You might already be familiar with built in MySQL functions like string or numeric functions。

 user defined functions are created to perform operations that can't be completed with built in functions。

Users develop code that implements equations or formulas to complete a task and return a result。

 Let's break this process down。A database engineer creates their own code。

 The code carries out a specific function， and the function then returns the required result to build a function in My SQL。

 you can use the create function command alongside the returns clause and the return command。😊。

These commands and clauses specify the data type and values to be returned by the function。

Let's find out how this syntax works。😊，Begin your statement with that Cre function command。

 then assign a name to your function。Follow the function name with parentheses and parameters。

 The parentheses are mandatory， but you don't always need to include parameters。Next。

 specify the return data type followed by the keyword deterministic deterministic means that the function always returns the same result for the same input parameters。

 For example， if a sum function is defined as deterministic。

 then it always returns the same result for the numbers it adds together。😊，Finally。

 you can implement the logic with a return keyword。

 Let's look at how luckyky shrub can make use of a user defined function。😊。

Lucky shhrub can use this syntax to create a function called find total cost。

 A cost parameter with a decimal data type passes a user input value of cost。

 and the returns clause defines the functions return type as a decimal number with 5 digits。 Finally。

 the return command calculates and returns the final cost after deducting 10%。

 So each time luckyky Shrub needs to determine the sale price of their items。

 They just invoke the function in a select statement followed by the current price in parentheses。

 But what if you want to develop a more sophisticated function。 For example。

 Lucky Shrub want to offer a 10% discount to customers who make purchases of 100 or more and a discount of $20% on purchases of $500 or more。

😊。

![](img/8cea56529edd8cae14bf01d4d9c5a98d_1.png)

The first step is to use the delimiter command to compile the whole function as a single compound statement using begin and keywords。

 then click enter to change the delimiter from the default semicolon to a double forward slash。😊。

Next， use that create function command and name your function， get total cost。

 include a cost parameter with a decimal data type that passes a user input value of cost。

 The returns clause defines the functions return type as a decimal number with five digits。

 and the return command calculates the final cost after the discount has been deducted。

The function is also defined as deterministic so that it always returns the same result for the same input parameters。

 The next step is to use the begin and end keywords to determine the body of the function。😊。



![](img/8cea56529edd8cae14bf01d4d9c5a98d_3.png)

Use an if else statement to check the input cost and deduct the appropriate amount。

 Then add the return command to calculate the final cost once the discount has been deducted。

 Finally， click enter to create the new function。 Then change the delimiter to the default semicolon。

 So you can use MysQL As usual。 Now it's time to test the function using a select statement。

 A customer has just made a purchase that costs $500。

 So lucky shrub need to determine the discount to be applied。

 type a select command followed by the name of the function alongside the purchase value in parentheses。

 Then click enter to execute the function。 The output result is $400。

 So this customer's purchase now costs $400 following a 20% discount。

 If you want to drop the function， Just use the drop function statement followed by the function's name。

 Click enter to drop the function。 Lucky shrub can now apply discounts to the customer's purchases as required。

😊，And you now know how to create your own user defined functions in MySQL for your own specific projects。

 great work。😊。