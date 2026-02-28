# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p36 036_01_07_代码练习-计算账单总额.zh_en -BV13E421M7FF_p36-

Let's write code that calculates the total bill at a restaurant。 meal plus tax， plus tip。

We're going to prompt the user for the bill amount， the sales tax percentage and the tip percentage。

And then we'll print out the total bill amount in the format that total bill is and some dollar amount。

Make sure you apply the tip after you add the tax amount。

And round the total bill amount to two decimal places。For example。

 let's say you went to a nice restaurant and ate a $30 meal。PA's sales tax is 6%。

 and you want to tip the waiter 18%。This should print the total bill is 37，52。



![](img/181980278a7c513a0e6d63f53b18c533_1.png)

First， let's define some variables based on user input。

So we'll create a variable bill and we'll set that to the result of some input。How much。Is the meal。

Remember， the input function returns a string by default。

 so we're going to actually cast that to a float。Will allow the user to enter a decimal。

We'll create another variable tax。Input。What is the。Sales tax。As a percentage。

And we'll cast that to a float as well。😔，And then， tip。We're going to cast that to a float。

And it's going to get user input。How much。Of a tip。As a percentage。Okay。

The first thing we're going to do is calculate the tax amount and then add the tax amount to the bill。

So let's create a variable tax amount。And that's going to be the value of the bill。

Multipliied by the tax。Divided by1 hundred0。So， this will calculate。😔，Late the tax。

And then we're going to create a new variable total。Which will be the bill。Plus。😔，The tax amount。

So here we're calculating the tax amount based on user input， the user enters the bill。

 the user enters the tax amount or the percentage。And then we'll divide by 100。

 That will be the total tax amount， and then we'll add that to the bill。

 and we'll store that in the variable total。So。Add tax amount to。Final bill。😔。

Then we're going to calculate and add the tip。Soll say tip amount。Equal2。😔，Take the total。So far。

 multiplied by the provided tip。Entered by the user。Again， it's a percentage。

 So we're going to divide by 100。is。Calculate。😔，The tip。And then we're going to add that。

 So the total。Equal to total。Plus， the tip amount。And。Tip amount to。😔，Final bill。

Then we're going to round the final bill amount to two decimal places。

 So we'll do that with the round function。 So total。Equals using the built in round function。

 We'll give it the value we want around。 That is the total itself。To two decimal places。

 the second argument to the round function is the number of decimal places。So， here we're round。

The total。Amount。Then， finally。😔，Let's print。The final amount。 So print。The total。Bill is。that。

ComaThen the second thing to print is the total itself。I will print the final amount。Check our code。

Let's go ahead and run it。How much is the meal。Well say。$30。How much is the sales tax？6%。

And how much to tip the waiter？18%， the total bill is 37，52。 There's a little space in here。

I'm gonna fix that。By adding。A separator between the values that are printed in the print function by default。

 It's a single space。 Let's override that using the S E P or the separator argument。We'll run that。

How much is the meal，30？Percentage。six。😔，Tip 18%， the total bill is 37，52。Let's run it one more time。

How much is the meal，30，52。Sales tax， let's say 8%， and I'm going to tip 30%。The total bill is 42，85。



![](img/181980278a7c513a0e6d63f53b18c533_3.png)