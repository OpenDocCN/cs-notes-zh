# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p161 41_05_03_main方法.zh_en -BV18U411U729_p161-

![](img/95ff69b51292fc01577fa041170dfe4a_0.png)

Hi， if you make a program that stands on its own， meaning you just want to run it。

 not inside of something like Blue Jay， then how does Java know where the program should start？

In Blue J， you did not need to worry about such a thing because you just click the menus to tell Blue J what objects to make and what methods to run。



![](img/95ff69b51292fc01577fa041170dfe4a_2.png)

![](img/95ff69b51292fc01577fa041170dfe4a_3.png)

In any other setting， a program starts in a method named Mainine。 When you run the program。

 you specify which class the main method is inside of。

The main method must have this particular signature。 public static， void， main string， array， as， U。



![](img/95ff69b51292fc01577fa041170dfe4a_5.png)

You are already familiar with public， which means that code outside of this class may call the method。

 Main has to be public， since it must be called by the code， which starts up the program。



![](img/95ff69b51292fc01577fa041170dfe4a_7.png)

The next word is static。 It means that the method does not live inside each particular instance of the class。

 but rather， there is just one of it for the class as a whole。

 You'll learn more about static shortly for now， just know that mainine has to be static。



![](img/95ff69b51292fc01577fa041170dfe4a_9.png)

![](img/95ff69b51292fc01577fa041170dfe4a_10.png)

![](img/95ff69b51292fc01577fa041170dfe4a_11.png)

Next you see void， which is the return type of main， it does not return any value。Next， you see main。

 which is the method name。The parameter domain is a string array。

 You are already familiar with both strings and arrays， And this works just like any other method。

 which takes an array of strings。 This parameter represents the command line arguments to the program。



![](img/95ff69b51292fc01577fa041170dfe4a_13.png)

![](img/95ff69b51292fc01577fa041170dfe4a_14.png)

When you run the program， you can specify what strings get passed into this array。



![](img/95ff69b51292fc01577fa041170dfe4a_16.png)

Now let's take a look at an example of a program written with Maine。Does this program look familiar。

 It is the hellello around the World program from the start of Java programming。

 solving problems with software， but it's been rewritten to use main， which you can see here。



![](img/95ff69b51292fc01577fa041170dfe4a_18.png)

![](img/95ff69b51292fc01577fa041170dfe4a_19.png)

Notice how it has exactly the signature we described on the previous slide。



![](img/95ff69b51292fc01577fa041170dfe4a_21.png)

The body of the main method then does whatever computation you want。In this case。

 it reads the file Hello，_ Unicode do text， and prints out each line in the file。



![](img/95ff69b51292fc01577fa041170dfe4a_23.png)

If you wanted to make use of the command line arguments to Maine so that you could change what file the program reads without recompiling the code。

 you could do so。

![](img/95ff69b51292fc01577fa041170dfe4a_25.png)

The code just uses args at0 to get the first string out of the array of arguments passed in。



![](img/95ff69b51292fc01577fa041170dfe4a_27.png)

Indexing into an array should be quite familiar by now。



![](img/95ff69b51292fc01577fa041170dfe4a_29.png)

Of course， it is generally a good idea to check that the person who ran your program provided the right number of arguments that way。

 if they did not， you can provide them a useful error message rather than just having your program crash with an array ready index out of bounds exception。



![](img/95ff69b51292fc01577fa041170dfe4a_31.png)

![](img/95ff69b51292fc01577fa041170dfe4a_32.png)

In this code， we made use of system dot exit， which just tells Java to quit the program entirely。

Here we do this since the program cannot do anything without knowing what input you want to work with。

System。 exitit is quite useful when appropriate。But use it only when you want the program to quit completely。

It takes an in indicating the success or failure of the program。By convention。

 pass in zero for success and a non zero value for failure。



![](img/95ff69b51292fc01577fa041170dfe4a_34.png)

Great， now you know how to write a main method。 So your program knows where to start if you run it outside of blue Jay。

 Thank you。😊。

![](img/95ff69b51292fc01577fa041170dfe4a_36.png)