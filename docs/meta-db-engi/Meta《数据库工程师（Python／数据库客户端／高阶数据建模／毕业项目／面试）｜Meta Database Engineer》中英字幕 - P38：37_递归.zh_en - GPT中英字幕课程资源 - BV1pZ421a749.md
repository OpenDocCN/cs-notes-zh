# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P38：37_递归.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

In programming， recursion is used for solving problems that can be broken down into smaller repetitive problems。

It's especially good for working on things that have many possible branches and are too complex for an iterative approach。

😊，One good example of this would be searching through a file system， so what is recursion？



![](img/a45577bfe3d07786452ff7f646dbc794_1.png)

Recursion is essentially a function that calls itself recursion creates a pattern of repeating itself over and over and over。

😊，So what does that mean from a coding perspective？



![](img/a45577bfe3d07786452ff7f646dbc794_3.png)

In this example， a function accepts a single argument and inside the function。

 it has some logic to deal with the problem it's trying to solve。😊，The key part is the return。

In the code the return statement is returning the same function Recursion is quite similar to a for loop。



![](img/a45577bfe3d07786452ff7f646dbc794_5.png)

It will iterate or in the case of a recursive function。

 call itself multiple times but a warning when you create a recursive function。

 you must always consider the result if you don't， it will spin into an infinite loop and suck up all the memory until the program eventually crashes or gets terminated。



![](img/a45577bfe3d07786452ff7f646dbc794_7.png)

![](img/a45577bfe3d07786452ff7f646dbc794_8.png)

Let's compare how to use a looping and a recursive solution to find the factorial of a number that can be solved。

Let's start with a looping solution。The looping function accepts a single integer called n as an argument and first checks if the number is less than zero。

If it is， it returns to zero is you can't have a factorctorial negative number。

The else condition sets the factorial to one and then loops through the range of the argument。

 which is five in this case。The loop will calculates one times 2 times 3 times 4 times 5。

 which will give the answer as 120， the factor of five。



![](img/a45577bfe3d07786452ff7f646dbc794_10.png)

Now let's explore the recursive solution to the same problem。

The recursive function is simpler and more compact。

The main reason for this is that you no longer need the full loop to do the iteration of the N argument。

The first line of the function verifies that the number is one and returns one if true。

 the else condition multiplies the argument N by calling the find factorial recursive function and passing in n minus1。



![](img/a45577bfe3d07786452ff7f646dbc794_12.png)

Recursion can be difficult to understand by way of explanation。

 let's demonstrate exactly what happened as the function calls itself。😊。

The function is being called over and over， and the part that changes is the value being passed into the function each time。



![](img/a45577bfe3d07786452ff7f646dbc794_14.png)

The argument of n or5 in this case is decreased by one each time until it finally is one。

This stops the function from being called again and exits out of the recursive process。



![](img/a45577bfe3d07786452ff7f646dbc794_16.png)

So how exactly did this code get the result of 120？



![](img/a45577bfe3d07786452ff7f646dbc794_18.png)

This is provided by the return statement。It keeps a reference to the increment value。

 and this is the final return after it has been completed。😊。



![](img/a45577bfe3d07786452ff7f646dbc794_20.png)

Right， it's time to review the advantages and disadvantages of recursion。First。

 the advantages are recursive code can make your code neater and less bulky。

Complex tasks can be broken down into easier to read sub problemsble。

Generation of sequences can be easier to understand the nested loops。But there are disadvantages。

It can be harder to follow the logic in recursive code。In terms of memory。

 they are expensive and sometimes inefficient， it can also be difficult to debug and step through the code。



![](img/a45577bfe3d07786452ff7f646dbc794_22.png)

You should now be able to explain what recursion is and how it can be used to solve problems。

I believe you'll benefit from using recursions in your code in the future。😊。

