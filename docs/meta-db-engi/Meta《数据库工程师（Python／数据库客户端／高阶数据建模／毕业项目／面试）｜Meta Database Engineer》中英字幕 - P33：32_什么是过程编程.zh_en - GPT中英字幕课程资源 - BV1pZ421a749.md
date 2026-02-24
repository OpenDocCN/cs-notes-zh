# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P33：32_什么是过程编程.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Developers can structure their code in many different ways。

 Python allows for object oriented procedural and functional programming models。

 or as they are often called paradigms。In this video I'll focus on procedural programming。

 which is like writing step by step instructions that a program executes it's an important stepping stone to object oriented programming therefore as a new developer it's important to learn more about it。

😊，The main purpose of a programming model is to structure your code that structure makes it easier to update the code and create new functionality within the code。



![](img/c0f95ed8203a4759f15319c8932efff6_1.png)

But there's no one perfect model that's a solution to coding structures。

 and sometimes a combination of approaches works best。



![](img/c0f95ed8203a4759f15319c8932efff6_3.png)

Procedural programming structures code into procedures。

 sometimes called it subroutines or functional sections of code。



![](img/c0f95ed8203a4759f15319c8932efff6_5.png)

Because of this approach， the code is made up of logical steps to complete a specific task。

 for example， adding two numbers to return their sum。😊。

I can add together the numbers five and 10 with a short piece of code。

Now I want to add together the numbers eight and four。😊，However。

 the code I wrote was specifically to add 5 and 10 for my new numbers。

 I must create another similar piece of code to do the calculation。

 That would not be a very efficient way to code。 Instead。

 I change the code into a function that will accept two numbers as argument and return the sum。😡。

With this function， I don't declare the actual numbers as variables。

 instead I use the parameters A and B， less code is needed。But something more important has happened。

 I now have the function called sum， which can be reused as many times as I like with many different sets of numbers。

In programming， there is a principle calledD， don't repeat yourself。

 and it's all about reducing duplication in code。😡。



![](img/c0f95ed8203a4759f15319c8932efff6_7.png)

The original code I wrote to add two numbers together to return their sum is a good example of what not to do because I had to write the code twice to accommodate the second set of numbers。

😡，A guideline to keep in mind is to create functions that can be reused throughout your application。



![](img/c0f95ed8203a4759f15319c8932efff6_9.png)

Let's examine another example。😊，This time for calculating the total of a bill and adding tax to it。

The code will be presented in four sections to help you focus on what each procedure does。First。

 the build total function accepts a build as a parameter and loops through it to calculate the total bill and return its total。

The calculate tax function accepts two parameters， the percentage and the bill total。

 then it returns the total amount of tax to be added to the bill。

 which is also rounded off to two decimal places。The food bill， which contains its items。

 represents a customer's bill which is static， but could also be changed to an input to accept data from the user to dynamically create a bill。

😊。

![](img/c0f95ed8203a4759f15319c8932efff6_11.png)

The last few sections will call the two functions to calculate the bill and tax and then print each out along with the overall total。



![](img/c0f95ed8203a4759f15319c8932efff6_13.png)

Could you identify the subrouts or functional sections of the code？

And did you note how these sections reuse one another？

Now let's put the four subroutines together to examine the four ways in which the footprint of the code is reduced by procedural programming。

It's best to inspect the code by starting at the end。Tax total reuses food total。



![](img/c0f95ed8203a4759f15319c8932efff6_15.png)

Food total reuses bill total and food bill。Calculate tax reuseers bill total。



![](img/c0f95ed8203a4759f15319c8932efff6_17.png)

And Bill total reuses food bill。In summary， the advantages of the procedural paradigm are it's easy for beginners to learn and get started。



![](img/c0f95ed8203a4759f15319c8932efff6_19.png)

Procedures can be reused by other parts of the code。

Coode is easy to understand because each procedure is broken into specific tasks。😊。

Procedural programming does have some disadvantages。

 including it can be harder to maintain and extend。



![](img/c0f95ed8203a4759f15319c8932efff6_21.png)

In some cases， it doesn't relate well to real world objects。

Data is exposed throughout the whole program。

![](img/c0f95ed8203a4759f15319c8932efff6_23.png)

Procedural programming has both its advantages and disadvantages as you learn more as a new developer。

 you will be better able to decide if it's the best approach to a specific piece of coding or not。😊。

