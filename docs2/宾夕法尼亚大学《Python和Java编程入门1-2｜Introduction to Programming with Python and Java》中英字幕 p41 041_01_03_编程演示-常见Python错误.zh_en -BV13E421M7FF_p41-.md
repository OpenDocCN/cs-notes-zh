# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p41 041_01_03_编程演示-常见Python错误.zh_en -BV13E421M7FF_p41-

Let's take a look at some typical error messages we often see in Python。

Let's define a variable A and set it to2。Then let's print the value of a。Print a。

Now let's run our code。Whoops， we got a name error。 Name A is not defined。

 I could see the error is in the current Python file on line， too。Let's take a look at line2。

This is because when we tried to print the value of a， we used uppercase A， which is not defined。

 Let's change that to lower case A and rerun our code。And here we print the value of lowercase A。

 which is 2。Let's define a variable B and set it to3。Now let's print the value of B print。B。

Let's run our code。Whoops， we got a name error， name print is not defined。

I could see the errors in the current file， on line 5。Let's take a look at line 5。

This is because we capitalize the print function call。Function names are k sensitive。

 and the print function should have a lowercase P。Let's rerun our code。

And now we've printed the value of B， which is 3。Let's get user input of an age。Age equals input。

Enter。Your age。Then let's print whether or not that age is greater than 26。Are you older。Than 26。

And then print the boolean result of age greater than 26。Run our code。And to your age。I'll enter 25。

 whoops， We got a type error greater than not supported between instances of string and int。

You can't compare the age variable to the number 26 in this way。First。

 cast the age variable to an int。 then compare it to the number 26。Then we'll rerun the code。

Enter your age。25。Are you older than 26， no。Again， let's get user input of an age。Age equals input。

Enter。Your age again。Then let's print what the age will be in one year， print。How old。Will you be in。

One year。Let's also print the result of age plus1。Let's run our code。

This is the first enter your age prompt 25， you are not older than 26。 and your age again。

I'll enter 25 again。Type error， you can only concatenate a string to another string。Line 12。

You can't directly add the age variable to the number one。 So first cast the age variable to an int。

 then add it to the number one。Let's rerun our code。Here's the first enter your age prompt 25。

 You are not older than 26。 En your age again。How old will you be in one year，26。Let's try something。

 I'm going to run the code again。First， prompt and to your age， the number 25。Enter your age again。

 I'm going to enter the word 25。Let's see what happens。

Looks like a value error invalid literal for int with base 10，25， on line 12。

Python is not able to cast the word 25 to an int。 so we get an error。

 but we can handle this kind of error with a try except。 Let's add that。We'll add try。Colon。

And then indent the code that might cause the error。

And then we'll use except to handle the possible error， except。Value error。

 That's the specific type of error that we're trying to handle。If we do get the value error。

 meaning we're not able to cast the given age， let's print something。Print。The given age。

Is not valid。Let's rerun the code。First， prompt 25。Enter your age again。25。

And we get the given age is not valid。Python wasn't able to cast the word 25。

 so we captured the valueer and printed the given message。



![](img/03c9294e4802b6938a8c0e110bcfade2_1.png)

![](img/03c9294e4802b6938a8c0e110bcfade2_2.png)

![](img/03c9294e4802b6938a8c0e110bcfade2_3.png)