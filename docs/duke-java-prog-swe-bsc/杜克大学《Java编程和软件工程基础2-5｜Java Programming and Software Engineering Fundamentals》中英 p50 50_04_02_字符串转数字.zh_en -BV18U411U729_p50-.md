# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p50 50_04_02_字符串转数字.zh_en -BV18U411U729_p50-

![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_0.png)

Welcome back As you work with data and CSV files， you may encounter numerical data， such as this。

 Here we have a variety of numbers such as years。 However。

 the libraries you use to read a CSV file will read this data in as a string。

 the sequence of characters 1493， not the integer 1493。

 If you want to manipulate this data numerically adding values。

 finding the largest or some other task。 you will want to work with the data as an int or a double。



![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_2.png)

So what would happen if you tried to write a line of code like this。

 int value equals rh dot gett year？

![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_4.png)

When you try to compile it， you would get an error message here that the types are incompatible。

 You are trying to send a string to an int。 Let us look a bit more at this error。



![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_6.png)

If you look at the documentation for the CSV reader， which we show here。

 you will see information about the get method in particular。

 you can see that its return type is string。Because that method returns a string。

 This entire expression wrote I get year has type string。

 Java knows that it will be a sequence of characters。 However， that is not the same type as it。

 which is the type we declared value to be。This raises two questions we will answer for you。



![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_8.png)

First， why is this a problem？ Sometimes Java can automatically convert between two types。

 So why can't it convert a string to an int？ It seems like if we have the string 1，4，9，3。

 Java could just figure out that that should be the number 1493。 However。

 it cannot do this in this case。 The second question is， of course， how do you fix it。



![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_10.png)

To see why Java cannot automatically convert a string to an in。

 consider what would happen if the string did not have numerical digits in it。 For example。

 supposeupp our CSV reader read the string hello， instead。

 what would you expect Java to do for this line of code。

 The rules of Java require the compiler to reject this line of code。

 because there is no guarantee that you can meaningfully turn any string into a number。

Another consideration is that the string 1493 has a very different representation from the number 1493。

Even though everything is a number， the type of a piece of data describes how that number is represented and interpreted。

 We will not delve into the details of the representational differences here。

 but it takes some work to convert between the two。



![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_12.png)

Accordingly， we would have to execute some code to perform the conversion algorithm。

Such an algorithm would examine the digits in the string and compute the integer that they represent。

We are not going to write this algorithm ourselves because。It's already built into Java。

 You can just call integer dot parsson to convert a string to a number。Even though it's Bill 10。

 you still have to call it explicitly to tell Java that that is what you want to do。

Here you can see an example of how you can use the integer dot parsson method。

 You pass in the string you want to convert， and it returns the integer value。



![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_14.png)

If you need to work with numbers that have fractional parts， you can use double dot parse double。

 which will accept a string like 42。56， and convert it into the corresponding value of type double。

 The type to use to work with non integer numbers for either of these methods。

 the string could be invalid， it could be something that does not represent a number。 For example。

 if you passed hello to integer dot parsson。 The method cannot turn hello into an integer。

 So what happens。The method throws an exception， which indicates that an error has occurred。

 If your programme throws an exception， then it will crash。

 There are ways to make your program handle the exceptions specifying what to do instead of crashing。

 But we are not going to go into that more advanced topic here。



![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_16.png)

So now you know that you can just assign a string to an int and that if you need to convert a string to an int。

 you should use integer。parsant。Likewise， for real numbers you have learned to use double。

 parsse double。Now you are ready to manipulate CSV data with numbers in it， Thank you。



![](img/9be0e9c548d3fd8ca1fc22ba9d5ce726_18.png)