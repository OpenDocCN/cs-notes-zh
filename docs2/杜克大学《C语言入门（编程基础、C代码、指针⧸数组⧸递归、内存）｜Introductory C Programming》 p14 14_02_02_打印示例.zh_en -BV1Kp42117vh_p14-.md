# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p14 14_02_02_打印示例.zh_en -BV1Kp42117vh_p14-

![](img/ae52a0b232b85a9e1effd029a21400ef_0.png)

In this video， we show an example of how you can use the print F function to print output to the terminal。

We have our usual frame for main， as well as a box for output。

 and the execution narrow is at the start of Ma。 We begin by declaring and initializing a to 42。

Then we reach a printF call。We're going to print this string Hello world。

 It will just print this string directly。 There are no format specifiers at all。

 So our output is Hello world。The next print F call will print the string A。

 Note that this prints the literal letter A， since it is enclosed in quotation marks and is therefore a string literal。

 This has nothing to do with the variable A。 So our output is a。And we return 0， and exit main。

What would you do if you wanted to instead print the value of the variable A？

The F in Prif stands for formatted， and there are several format specifiers you can use to format your output。

In this example， first we declare and initialize integers a to 42 and B to 7。

Then we reach a print F call with a format specifier。In this case。

 percent D percent D formats integers as decimal numbers。

 and you'll learn later about other format specifiers。

Percent D means print F will look at the corresponding argument to see what integer format as a decimal number。

 In this case， it is given variable a。So， it prints。

The decimal representation of the number 42 in the location in the string where the percent D is。

The next call to printf has 2% Ds。 The first refers to B， the next argument after the string。

 which is 7， and the second of these refers to a plus B。

 which is evaluated like any other expression。

![](img/ae52a0b232b85a9e1effd029a21400ef_2.png)

So it's 42 plus 7， which is 49。So the output is b is 7 and a plus b is 49。 We return 0 and exit main。

Another important thing to know about printf is escape sequences。

 An escape sequence begins with a backslash。 The most common one is backslash in。

 which means new line。 This printf call has two backslash ends。

 so it should print two new lines after Hello world。This statement declares and initializes b to 7。

This print F call has a backslash T in it， which means a tab is useful for lining up output。

 The output is， my answer is tab 7。We return and exit May。

This introduction has shown you a few uses of the print function。

 and you will see more later in the course。

![](img/ae52a0b232b85a9e1effd029a21400ef_4.png)