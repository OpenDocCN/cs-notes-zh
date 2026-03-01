# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p23 023_01_10_类型转换.zh_en -BV13E421M7FF_p23-

In Python， you can convert from one data type to another。 So let's look at a problem，1，2，3，7，4。

 divided by 6，2，1。

![](img/956c5ee0532927c1f9ca0902b1781a09_1.png)

![](img/956c5ee0532927c1f9ca0902b1781a09_2.png)

We get 19。925925，9，2，5，9，2，5，9，2，7。 This is a float。 Well， what if we want to cast that to an int。

I can use the int function to built in Python function。



![](img/956c5ee0532927c1f9ca0902b1781a09_4.png)

The same problem。 And I get 19。 So whatever this number is as the float cast it to an int is 19。

 Note， it rounds down to the closest integer。 So this was rounded down to 19。

 If we really want to round a float to the nearest integer。

 we should use Pythons built in round function。 So round。



![](img/956c5ee0532927c1f9ca0902b1781a09_6.png)

![](img/956c5ee0532927c1f9ca0902b1781a09_7.png)

That problem。

![](img/956c5ee0532927c1f9ca0902b1781a09_9.png)

We get 20， so it rounds up to the nearest integer。You can also cast from a string to an integer。

 So int the string 1。

![](img/956c5ee0532927c1f9ca0902b1781a09_11.png)

Gives me the number one。

![](img/956c5ee0532927c1f9ca0902b1781a09_13.png)

More printing this time with numbers， I can print the value of4 divided by 2。



![](img/956c5ee0532927c1f9ca0902b1781a09_15.png)

Here I get 2。0。 No problem there。 I can print with strings and numbers。

 So print the string  for mod 2。Equals and print the value of format mod 2。For2 equals 0。

 No problem there。 What happens when I try to print with strings and numbers concateated。

 So if I try to print。The string format 2 equals。Concatenated with the value of For 2。



![](img/956c5ee0532927c1f9ca0902b1781a09_17.png)

Here I get a type error。Because Python doesn't know what to do when I try to concatenate a string with a number。

 So in this case， I need to cast this number to a string。



![](img/956c5ee0532927c1f9ca0902b1781a09_19.png)

![](img/956c5ee0532927c1f9ca0902b1781a09_20.png)

To fix this， we can use the STR function。Put the value or the result of4 modd 2。

 feed it to that function that will cast it to a string and concatenate that with the four modd 2 equals。

 and I get4 modd 2 equals 0。

![](img/956c5ee0532927c1f9ca0902b1781a09_22.png)

And you can print with strings and booles concatenated。 So print。Is for even。

Concatenated with the string value of4 mod 2 equals 0。Is for even true  one string。

Concateated to another string， which is the casted version of4 modd 2 equals 0， true。



![](img/956c5ee0532927c1f9ca0902b1781a09_24.png)