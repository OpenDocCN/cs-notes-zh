# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P44：43_实例方法.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Let's try to solve a problem that may occur for managers or to restaurants。

Because the managers are busy running the restaurants。

 they have limited time to deal with the needs of employees。😊。

The current system for paying wages requires managers to update each other every time an employee requests payment。

Because this is cumbersome， they would like to implement an automated approach。So what can be done？

Fortunately， there's a way to reduce the number of steps using instances。😊，By the end of this video。

 you'll be able to explain what instance variables and methods are。😡。

You'll also know how to use them to change the state of an instance object。

So let's write some code to help those busy restaurant managers。😊。



![](img/2e2655b66b3f1ec6e2720855daa53957_1.png)

Let's start a new file called paymentmentinfo。pi。In this file。

 I'll create the class Palips and initialize three variables in it called name。

 pay status and amount。I start by typing class paylips and then on the next line I call an in its function withDe double underscore in it and then select the trigger suggestion。

For the variables， I type each one in the format self dot variable equals variable。Next。

 I'll create two functions， one to display the status of the payments and another to update the status。

The first function is written asDe pay with self in parentheses。

 followed by self dot payment equals yes on the next line。

The second function is de status and contains an if else statement。

If self dot payment doubly calls yes， return， self dot name plus is paid plus self dot amount with STR appended to the beginning。

The second part of the statement is else returnturn， self dot name plus is not paid yet。Finally。

 let's create instances of this class for the employees， I'll call them Nathan and Roger。

I typed the first instance Nathan equals paylips and in parentheses， Nathan for name。

 no for payment and 1000 for amount。For Roger， I copy and paste this instance and set the values to Roger。

 no and300s respectively。😊，I also need to make sure to pass these values inside the init method。

 so I type name， payment and amount after self。Now I'm ready to call the instant method status to check the status of the payments。

😡，I write a print statement for Nathan Dott status parentheses and for Roger Dotts status parentheses。

When I run the code， the output all appears on one line， which is not very presentable。😡。

I add a new line character between the items and the print statement， which is backslash M。😊。

This time， the output is much cleaner。😊，The output states that neither Nathan nor Roger have been paid。

But let's say that one manager decides to pay Nathan。

 so I'll use the pay function to update the status。

Remember that the pay function is set up to update the value of the payment variable。😡。

I type Nathanthan dot pay parentheses and then copy and paste the last print statement。

Above this line， I type another print statement with a string after payment。😊。

I run the code once more， and it now tells me that Nathan was paid 1000。

 whereas Roger still has not been paid。😡，That's a demonstration of instance methods in action now I'll describe the code to you in more detail。

😊。

![](img/2e2655b66b3f1ec6e2720855daa53957_3.png)

Now let's discuss what happened in that coding example in more detail。

The two instance objects which are Nathan and Roger each have their own states。

 you may have noticed that when the In method pay was called to change the state of Nathan。

 Roger was not affected。This is because the method inside the class is not affected。

 rather it provides a separate blueprint to each instance which can then be updated for that instance only in the coding example I didn't print the variable values after calling the pay function。

 but if I did it would show that the payment instance variable for Nathan changed from no to yes。

 while Roger remained no。Now， let's imagine that this code is the basis for an online payment system。

It would allow either manager to click on the paid button for an employee。

 which then update that employee status， no more back and forth calls。



![](img/2e2655b66b3f1ec6e2720855daa53957_5.png)

In this video， you learned how to use instance variables and methods to change the state of an instance object without affecting any other instances。

