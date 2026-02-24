# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P15：14_控制流 if else else if.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

In programming it's important to understand how to control the order in which your code is executed for example。

 suppose you're invited to an event you have to consider whether you need to dress formally or informally。

Another example of a control flow is to consider a light switch the flow is represented by the electrical current and the control as the switch itself with the two states of on and off。

The order in which you make decisions matters and the same applies to writing effective programs。

In this video， you'll learn how to use conditional statements to control flow in Python programs。

 so what is control flow？😊，Control flow refers to the order in which the instructions in a programme are executed all programs have decisions that need to be made as a result of this。

 the programme will take different actions or directions。In Python。

 there are two types of control flows。First， you can use conditional statements such as if else and L if or else if。

In second， you can use loops such as the for loop and the wild loop。

Let's explore these a little further now。The if keyword states that if the condition proves to be true。

 a function is performed。The L keyword catches anything which isn't caught by the precceeding conditions。

The LF or else F keyword is Python's way of saying if the previous conditions were not true。

 then try this condition。The for loop checks for specific conditions and then repeatedly executes a block of code as long as those conditions are met。

The while loop repeats a specific block of code an unknown number of times until a condition is met。



![](img/b436a246f3986675da6ae7e7501d97d9_1.png)

Let's explore conditional statements in more detail with some practical examples using the if。

 else and LF I'll now write some code for a restaurant that wants to apply different discounts based on the amount its customer spend。

To start off， I define a variable for the customer's bill。

 I'll call it bill total and a assign a value of 114 to it。

Now I apply condition with an if statement if bill total is greater than 100。

 print the statement bill is greater than 100。Next， to apply a discount to build total。

 I need to create a second variable， I'll do this above the if statement in my code。

 call itD one and assign a value of 10 to it。😡，The condition also has to change。

 so inside the if statement I add Bill total equals Bill total minus discount1。

At the very end of a code snippet outside the if statement。

 I'm going to print out what the value of the total villas。😡，To do this。

 I type a print statement that says totalal bill and then a plus sign to add the value of bill total here。

 I need to convert the integer to a string， I use the STR typecasting function to do this。

Let's click on run。Great。In the terminal two strings are printed Bill is greater than 100 and the total bill is 104。

 but what happens if the bill is less than 100 I change the value of bill total to 95 and press run。

Notice that this time because the if condition is not met。

 it only prints a statement total bill is 95， but I'd like to print a statement that says the bill is less than 100 to do this I add an L statement below the if statement。

I type else colon， and in the next line I print the statement Bill is less than 100。

Let's run the code。The output in the terminal now says bill is less than 100 and total bill is 95。

Up to this point， you've learned how to use the if and L statement to control the order in which values are assigned and printed。

You are now ready to take program flow one step further。

Say this restaurant wants to add another discount for bills over 200。How would you do that？

Once again， I first need to create a new variable above the conditions that I named discount2。

 which I set equal to 20。If I run the code now， it will still print out the same output because I haven't changed any of the conditions or values yet。

😡，Let's change the value of Bill total to 210 and click Run。Notice that both statements are printed。

 but discount one is still applied， it's clear that the if statement is still executed。

Since the value is 210， the condition is still met。😊，To change the program flow for values over 200。

 I need to add an and condition to the if statement。😊。

I change the statement to if bill total is greater than 100 and bill total is less than 200。

Let's run the code and see what happens now the discount wasn't applied。

The output just says bill total is 210， why， because the condition is not met。

Now this is where it gets really interesting to add a second condition for bills above 200。

 I'll use an else if statement。😊，In between the if and L statement， I type L if。

 which stands for Ls if and then build total is greater than 200。

Print the statement Bill is greater than 200。In the next line， I apply the new discount。

 I type Bill totalal equals Bill total minus discount2。First。

 let me clear my screen so you can focus just on the results Now I press run。

Notice how the program flow has changed， the first condition was not met so the code went to the second condition where the value of bill total was compared to 200。

And since it was greater than 200， the statementB is greater than 200 was printed。

The code then proceeded past the L condition because the previous L if condition was true。

Remember the else condition only executes if none of the preceding conditions are true。😊，Finally。

 it printed the statement to the end of the code snippet， namely totalal bill is 190。

This proves that discountcount2 was applied。Congratulations。

 you now know how to control program flow with if， else and else if。

Once you become proficient in using conditional statements， programming becomes a lot of fun。

 I encourage you to test it out。😊。

![](img/b436a246f3986675da6ae7e7501d97d9_3.png)

In this video， you learned how to use conditional statements in Python。😊。

Writing conditional statements is an essential part of programming。

 and I encourage you to practice them in your code。😊，The next time you need to make a decision。

 think about the conditions involved and how they can be represented if you were to code them in Python。

😊。