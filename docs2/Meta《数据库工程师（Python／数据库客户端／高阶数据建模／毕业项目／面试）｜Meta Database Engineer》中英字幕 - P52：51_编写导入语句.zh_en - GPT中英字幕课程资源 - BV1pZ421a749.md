# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P52：51_编写导入语句.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

![](img/0fba8ea37b4d52affdabf2a063a7bc86_0.png)

Let's explore how to use modules with the import statement I have already created a file called import。

pi， I will now import the built in math module by typing importm Ma。

Just to make sure that this code works， I'll use a print statement。 I do this by typing print。

 importing the math module After this， I'll run the code。The print statement has executed。

Most of the modules that you will come across， especially the built in modules。

 will not have any print statements， and they will simply be loaded by the interpreter。

 Now that I have imported the math module， I want to use a function inside of it。

 Let's choose the square root function， S Q to do this。 I type the words math dot S QT。

When I type the word math followed by the dot， a list of functions appears in a drop down menu。

 and you can select SQRT from this list。I pass nine as the argument to the mathth。 SQrRT function。

 assign this to a variable calledRoot， and then I print it。The number three， the square root of 9。

 has been printed to the terminal， which is the correct answer。

Instead of importing the entire math module as we did above。

 there is a better way to handle this by directly importing the square root function inside the scope of the project。

This will prevent overloading the interpreter by importing the entire math module to do this。

 I type from math importm SQRT。When I run this， it displays an error。

Now I remove the word math from the variable declaration and I run the code again。This time。

 it works。Next， let's discuss something called anallias。

 which is an excellent way of importing different modules here I assign an alias called M to the math module。

 I do this by typing import math as M。Then I type cosine equals M dot。

I then select Cos COS from the list of functions after which I add the number 0 in parentheses。

On the next line， I'll print cosine and then I run the code。The result is the cosine value of 0。

 which is 1。This is possible because I used the alias called M。If I tried writing mathth。tco。

 it wouldn't work because the math module is now recognized as M instead。

Let me remove this code from the screen and clear the terminal before we continue。

An alias can also be used for a function that's imported。For example。

I can type from math import factorial as F to alias the factorial function。Now I assign F of 10。

 typed as F opening parenthesis， the number 10， and a closing parenthesis to a variable called factorial 10。

I'll print the variable and see if it works。When we run the code， we see that it works just fine。

Using an alias in this way reduces the effort of typing factorial every time。

 After I remove the alias， I can import as many functions as I'd like from a given module。

 I'm going to import log and S Q R T。I create a variable using the log function to find the value of log base 10 of 50。

 I do this by typing x equals log 10， opening parenthesis， 50， and closing parenthesis。And again。

 I print the variable on the next line。And when I click Run。I'll see whether or not it worked。

Once again， it worked just fine。Now， what if I want to import all the functions inside a given module？

I can remove the functions I added earlier and replace them with a star。

This basically translates to importm all from the math module。When I run the code again。

 let's see if it works。 and it does。 However， this practice of using a star is not the best approach in certain cases。

 For example， this is a small file， and I know that the log 10 function is present inside the math module。

But when you work with a large code base， it could be difficult to track where the log 10 function came from。

Additionally， when you're importing other modules， it may get confusing。

Importing packages is very similar to importing modules in Python。

 just like you can have imported functions， you could also import variables and classes from a given module。

 Now I replace the star with a variable called some variable。

 which may be present inside the given module。Let me try to run the code again。

Since the math module doesn't have such a variable， it throws an error when I print it。

The interpreter is not able to import some variable from math In this video。

 you explore different methods that can be used to import modules in Python using keywords like import from star and as。

This enables you to use the modular structure of Python in object oriented programming in general。



![](img/0fba8ea37b4d52affdabf2a063a7bc86_2.png)