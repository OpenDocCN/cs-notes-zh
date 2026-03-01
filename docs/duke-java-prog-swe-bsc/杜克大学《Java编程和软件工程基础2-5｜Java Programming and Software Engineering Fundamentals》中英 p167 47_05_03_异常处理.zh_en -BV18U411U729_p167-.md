# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p167 47_05_03_异常处理.zh_en -BV18U411U729_p167-

![](img/6c664718b87e0d7bbcb87a89a6bcfb21_0.png)

ose you have code， which might experience a problem。 For example。

 if you use Javas built in URL class to work with URLs。

 its constructor can throw a malformed URL exception。 If you pass in a string。

 which is not a valid URL。

![](img/6c664718b87e0d7bbcb87a89a6bcfb21_2.png)

Maybe you read this string from the user and do not want your program to crash if the user made a mistake。

 How would you deal with this exception？

![](img/6c664718b87e0d7bbcb87a89a6bcfb21_4.png)

The first thing you do is put the code that might throw an exception into a try block。



![](img/6c664718b87e0d7bbcb87a89a6bcfb21_6.png)

A try block starts with a keyword try and then wraps the code that might have problems inside of curly braces。



![](img/6c664718b87e0d7bbcb87a89a6bcfb21_8.png)

Immediately after the Tri block， you write a catch block。

 which states what type of exception you want to handle， in this case， malformed URL exception。

And then has the code you want to do whenever this problem occurs。You name the exception。

 much like declaring a parameter， which gives you access to the exception object。

 You can call methods on it。 And if you need to get more information out of it。

The code in the catch block can do whatever you want， for example。

 telling the user that their URL was not valid and asking them to enter a new one。

When the string is a valid URL， no exception will be thrown。 In such a case。

 Java will execute the code inside the try block as normal when it reaches the end of the try block。

 it will skip over the catch block。And continue to execute the code after it。However。

 if the string is not a valided URL， then when somewhere inside of this constructor。

 a malformed URL exception will be thrown， Java will then go inside the catch block and begin executing whatever code you wrote there to handle the error。

After finishing the catch block， Java will continue to execute the code immediately after it。

You can also use a finally block， which is always executed， whether or not an exceptional was throne。

Finally， blocks are often used to clean up resources which were allocated and need to be freed。

 regardless of what happened。 Java 7 also introduces a try with resource construct to simplify releasing certain types of resources。

 though we aren't going into that here。Thanks。