# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p10 10_02_05_变量.zh_en -BV18U411U729_p10-

![](img/6927d48d11657ca52df3ec80b761ae3f_0.png)

Hello， we're going to start learning to execute code with the most basic statements in Java and build up to more complex statements from there。



![](img/6927d48d11657ca52df3ec80b761ae3f_2.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_3.png)

Here we have two variable declarations， one for an int called X and one for an int called Y。

If we execute these statements as is， we will create boxes labeled X and Y to hold the values we eventually decide to put in these variables。



![](img/6927d48d11657ca52df3ec80b761ae3f_5.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_6.png)

But in this example， we have not explicitly provided any initial values。In some languages， such as C。

 no default value is ever provided when you declare a variable。

 meaning you get undefined behavior if you use an uninitialized variable。



![](img/6927d48d11657ca52df3ec80b761ae3f_8.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_9.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_10.png)

This is such a common and significant problem that Java provides two solutions。

An initial default value of 0 is given to instance variables。

 or an explicit error is given for using a local variable before initializing it。



![](img/6927d48d11657ca52df3ec80b761ae3f_12.png)

We will see these different types of variables in upcoming videos。



![](img/6927d48d11657ca52df3ec80b761ae3f_14.png)

Now let us look at another example， which initializes the variables when they are declared。Here。

 the first statement declares an in called X。Executing it makes a box for x and immediately assigns the value 4 to x。

 We show this by putting4 in the box for x。

![](img/6927d48d11657ca52df3ec80b761ae3f_16.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_17.png)

Executing the next line both creates a box for y and puts the value 6 in that box。



![](img/6927d48d11657ca52df3ec80b761ae3f_19.png)

Combining the declaration and initialization of your variables into the same statement won't pose a problem in any language。

 and anyone reading your code knows exactly what you meant for the code to do。

 so this is a good habit to get into。

![](img/6927d48d11657ca52df3ec80b761ae3f_21.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_22.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_23.png)

Of course， variables are only useful if you make use of the value that they have here。

 the first code declares X and initializes it to4。

![](img/6927d48d11657ca52df3ec80b761ae3f_25.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_26.png)

Next， y declares and initializes it to x plus 2。To perform this statement。

 we must evaluate the expression on the right hand side of the equal sign。 x is 4。

 so x plus 2 is 4 plus 2 or 6。

![](img/6927d48d11657ca52df3ec80b761ae3f_28.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_29.png)

We show this by creating a box for y and putting six into it。

The last statement creates a variable Z and initializes it to y minus x。

So you would take the value of y， which is 6 and the value of x。

 which is 4 and subtracts them to get 2。You would then create a box for Z and initialize it to2。



![](img/6927d48d11657ca52df3ec80b761ae3f_31.png)

Great， now you know how to execute code with variable declarations and assignment statements。



![](img/6927d48d11657ca52df3ec80b761ae3f_33.png)

![](img/6927d48d11657ca52df3ec80b761ae3f_34.png)