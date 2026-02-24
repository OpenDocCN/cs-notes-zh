# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P28：27_异常处理.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

In this video， you will explore how to handle exceptions in Python。

 You will learn how to change error messages and how to wrap your code within try and accept statements。



![](img/1766e9e70c45a4701b34edaef1f7063f_1.png)

As an example， I will write a simple math function。

I define a new function called divide by and allow it to accept two parameters A and B。

The purpose of this function is to return the value of the division of bold numbers。

 so in the next line， alt type return A divided by B。

Now I add a print statement for the divide by function。Inside the print statement。

I'll also add a new set of parentheses with a value of 40 and 4。

These are the values that will be divided by the function。

I click on run and the value returned is 10， which is correct， because 4 goes into 40 10 times。

Now let's test what will happen if I pass in the values of 40 and0。Now when I click on Run。

 I get an error or an exception。The exception in this case says zero division error。

 division by zero。It gives this error because in math， you can't divide a number by0。

You might agree that getting cryptic errors could upset users， so the question is。

 how can you handle errors in a more user friendly way？

How can you prevent a user from seeing the actual exception being printed out。

 You do this with Python's try and accept statements。 Simply type try， colon。 and in the next line。

 accept colon。You add the code that you want to run within the try statement。

So I delete the print statement at the bottom and cut the divide by zero function within the try statement。

 I type A and S equals and paste the function。Now， in the accept statement。

 I will add my own error statement， I add a print statement for the string， something went wrong。

Let me just clear the terminal so you could focus on the output。

I click on Run and now the error statement is printed。So what's happening？

The try statement will try and execute the code that you added inside it。 If an exception occurs。

 it will trigger the accept line and execute any code added underneath the accept statement。

But Python allows you to make the accept statement more specific。

If you want to trap the exception itself， you could add the base class exception right after accept。

The base class exception is used for all exceptions that are written within Python。

You can gain access to the exception information by using the as E after exception。

The E variable acts as an alias for the exception。I can use E to print out the exception in the print statement。

So let's edit the print statement。I add E at the end of the error message。

 I press run and what happens。Our custom message is printed out。

 but the contents of E are also printed， so this time it reads something went wrong。

 division by zero。In Python， you could also get access to the actual type or class of exception that's occurred to do this。

 I add another print statement of E dot underscore， underscore class， underscore， underscore。

I run this statement one more time。This time， the output includes the class of error as well。

 namely class 0 division error。Let me clear the terminal again。

Let's take this one step further to provide even more specific feedback to the end user。

In the accept statement， I replaced the base class exception with the actual error that was printed out。

 namely0 division error， I will change the print statement so that it first prints the actual error by adding E at the start of the statement and now I'll add some user friendly text saying we cannot divide by0。

I click on run， and now the output is division by zero， we can divide by zero。Up to this point。

 you've covered how to wrap your code with a try and accept statements and how to optimize the message that a user sees。

But how can you handle more than one exception without knowing what they are ahead of time？

Fortunately， you can change the accept statement by adding another accept statement。

 say the code doesn't trip the zero division error in the first accept statement。

 you can add another accept statement that tests for a generic exception。

Now I will add the base class exception。Again， I add a print statement with E and a message with some general information。

I'll click on Run and in this case， because there is still a math error。

 the function will still trip at the first accept statement。

 but this gives you a good idea of how you can test for more exceptions。



![](img/1766e9e70c45a4701b34edaef1f7063f_3.png)

Congratulations， you now know how to wrap code in the try and accept statements to handle all potential exceptions in your code。



![](img/1766e9e70c45a4701b34edaef1f7063f_5.png)