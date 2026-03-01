# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p61 061_02_01_编程演示-平均值计算程序.zh_en -BV13E421M7FF_p61-

Let's write a program that asks the user for numbers， integers。

Then it will compute the average of those numbers。It will also allow the user to enter negative 1 to quit the program and calculate the average。

😡。

![](img/eb5ae6f6d54f0d57e0f6eb06325e9f9c_1.png)

So I'm going to store my numbers in a list。Num list equals empty list。

I'm going to count the numbers in that list so I can calculate the average later。

Initialize count to 0。And I'm going to create a flag to indicate that the program is waiting for user input。

Playing equals true。Then I'm going to set up a loop to repeatedly get user input of an integer。😡，So。

 while。Playing。😔，Is true。Enter the loop and get some user input。So we'll store this in numb。Input。

Enter an int。We're going to cast it to an int。Let's first test to see if that number is negative 1。

 if it's negative 1， we're going to exit the loop and calculate the average of all the numbers。

So if the nu is equal to negative 1。Playing。😔，To false。

That will force us to exit the loop on the next iteration。Otherwise。Add the number。

 if it's not negative one to our list of numbers。No list。Aend。Nan。

And then increment our count of numbers。I plus or equal to 1。Okay。Add number to list of numbers。

Test if number is negative one to quit the program。Once we exit the loop。

We're going to calculate the average of all the numbers that were entered。Noum sum。

 We're first going to get the sum of the numbers。N sum equals 0。For each number， in nu list。

Add it to the sum， num， sum。Plus or equal to no。As we'll get the sum of all entered numbers。

Then we're going to calculate the average。Calculate the average。We'll store that in nu average。Okay。

😔，And that will be。The sum divided by the count of numbers， I。And then we'll print it。Print。Average。

Num average。Let's run our code。Let's get the average of some numbers。Enter an int。3。En turn an int。3。

😔，Enter an int。3。I'm going to enter negative one to exit the program and calculate the average。

Average，2。0。So what's wrong with this program？I can see。That even if we enter a negative one。

We set plain to false， but we're still adding that negative one to our list of numbers。

So it's being calculated as part of the average。So what we need to do。

Is to account for this If it is negative one set playing to false。Else。Add the number。

Or append the number to our list。And then， increment the count。Let's run our code。Enter an int，3，3，3。

Negative 1， average3。 Let's run it again。1。2。😔，3。Negative 1。



![](img/eb5ae6f6d54f0d57e0f6eb06325e9f9c_3.png)

Average 2。