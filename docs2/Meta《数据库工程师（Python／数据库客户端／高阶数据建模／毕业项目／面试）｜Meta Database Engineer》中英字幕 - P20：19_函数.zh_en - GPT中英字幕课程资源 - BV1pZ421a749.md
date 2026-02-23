# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P20：19_函数.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

So what are functions？At the most basic level， you can think of functions as a set of instructions that take an input and return an output。



![](img/0a8f00c07d046458625ee184dba341cb_1.png)

For example， the primary task of the print function is to print a value。

 this value is usually printed to the screen and it' past to the print function as argument。

In the example we have here， the string hello world is the value passed to the print function。

By the end of this video， you'll be able to declare a function in Python。Pass data into a function。

And return data from a function。A Python function is a modular piece of code that can be reused repeatedly。

You've used some Python functions already in this course， such as print and input。Both are functions。

 and each one has a specific task or action to complete。😊，The input function will accept parameters2。

 but will also accept input from the user。So how do you declare a function？

A function is declared using theDe keyword， followed by the name and task to complete。

Optional parameters can also be added after the function name within a pair of parentheses。

Here's an example of creating a function to add two values。Type the deaf keyword。

 followed by the function name of sum， then enter x and y is parameters。

 and finally enter return X plus y as the task to complete。

I'll now give a practical demonstration of functions， how to declare them， how they're used。

 and how they can also simplify your code by putting it into a reusable structure。😊。



![](img/0a8f00c07d046458625ee184dba341cb_3.png)

Let's start with a short example that explains how to calculate a tax amount for a customer based on the total value of that bill。

I'll start by declaring two variables。I type the first variable calledB and I assign it the number。

 let's say 175。00。I know this is going to be a data type known as floats because I'm using decimal points as is the norm for currency。

The second variable is the tax rate， which is the percentage tax rates that should be applied to the bill。

So I put in 15 and then what I want to do is calculate the amount of tax for the bill itself what I do is add this into another variable called total tax I then do the calculation which is the bill multiplied by the tax rate and then divided by 100 to get a dollar amount to output the value I print the total tax and pass the total tax variable and then run the program。

Total tax is 26。25， which is 15% of 175。In the real world。

 the build value will be different for each customer and the tax rates may also change。😡。

Updating each variable every time is inefficient to overcome this problem。

 I'll create a reusable function。To start creating a function。

 I use the defined command or death for short。Then I'll give it a name that relates to the task it's carrying out。

 so in this case it's going to be calculate tax。With functions you can pass in arguments and the purpose of that is to make it more dynamic。

So consider the arguments that I need to take in， I'll take in a bill。

 which would be the total value of the bill itself， and then also a tax rate。😊。

And then like I've done before， I will calculate the total tax by taking the bill。

 multiplying it by the tax rate， and then dividing it by 100。😊，Okay。

 then I do a return wrap bill in parenthesis， multiplied by tax rate and divide by 100。

Now I can remove the declaration I made earlier for the variables and the calculation。

With a function， if you run the current code as is。

 it will come back with nothing because a function is only ever run when it's actually been called。😡。

I'll demonstrate this。If I do a print， I can calculate tax and then I pass it as I've done earlier。

 175 is the total bill and then the tax rate will be 15。😊。

I'll also put in just a total tax and then click on run and the total tax rate is 26。25。

If I want to change the rate， I can reuse the same function， total tax， I'll call the function again。

 calculate tax， I'll give it a different value for a bill， say 164。33。

This time I'll change the tax rate to 22%。Clear the screen and then click on run and my total tax for the second item is 36。

1526。To clean the output up a bit and make it more visually appealing。

 I'll put in a round function which allows control of the number of decimal places that I want returned。

😊，In this case， I'll do two and then rerun the code。This is a lot neater with 36。15。

One of the nice things about a function is that you can update at once and any part of the code that caused that function will get those changes as well。



![](img/0a8f00c07d046458625ee184dba341cb_5.png)

In this video， you've explored basic functions in Python。

 how to declare functions and pass and return data to and from them。

