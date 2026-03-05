# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p143 p71_04_handling-errors-and-exceptions -BV1tAygYoEj5_p143-

Hi there at the previous video we learn how to use AjaX to do content dynamically。Now in this video。

 we will learn how to handle errors and exceptions in JavaScript， so let's get started。

Handling errors and exception is an important part of writing robust and reliable JavaScript code。

In JavaScript， we have try and catch keywords that are used together to handle errors and exceptions in the code。

Here is the basic syntax of try and catch block。😡，The tribe block contains the code that may potentially throw an error or exception。

If an error occurs， JavaScript will jump out of the tribe block and into the cache block。

The cash block contains code that will handle the error or exception such as logging an error message or taking corrective action。

😊，Within the cache lock， you will also notice this error variable。

 So this error variable is used to represent the error object that was thrown。

 This variable can be used to access information about the error such as its message。

 stack trace and any additional data that may be attached to it。

Let's understand this through an example。

![](img/a93b6c371dd3ab2d2dd53ee17bd5e7c5_1.png)

So let's go to the VS code and here I have a file that is a JavaScript file handling errors dot Gs。

And let's start writing a code at this point。So let's create a function divide。

And this function will take a numerator。And you can say denominator。Ass the parameter。

Then what you want to do is。We can add a check here。 We can say if。Thenominator is equal equal to 0。

In that case， division is not possible。So what we want to do is we want to throw new error。

This will throw a new object。And we can pass a message here。 we can say。Division。By 0。

You can pass any error related to it。At this point， it seems more appropriate。

Then what we want to do is we can say returnton。Nummerator。Divided by denominator。

This is the function。And then you want to call the function， but before calling the function。

 we will use try and catch。To check for any errors so we can say try this piece of code。

 this block of code， so we can say con。Reside。And result would be a part of let's say divide。

 whatever divide is returning， we can store it in result。And。We will pass here。10 comm 0。

Because we want to get an error。And then we can say console lot lock。Reult。As you can see。

 it is throwing some kind of error that catch are finally expected。

 so it is always important to use catch。Methodd at this point， so we can see catch。Eor。

And we can say， console。Tt lock。Error， it is an object。

 and we want to put a message at this point so we can say error taught message。

Let's try to run this program。So Ive flippeded on save and let's open up the terminal。Let's clear it。

 and let's run node。Handling aristo Gs and you can see we get the message here that is division by0。

You can also write here something like this to actually give a more idea about that this is an error rather than a normal message if I try to run this again you can see it says error division by0。

So in this example we define a function divide that performs a division operation on two numbers that is themerrrator and denominator and before performing the division we checked to make sure that the denominator is not 0。

If it is， we throw a new error object with a custom error message that is error division by0 in this case。

We then call the divide function with arguments 10 and 0。😊，Within a tri block。

Since this will result in a divide by0 error， JavaScript will jump out of the tribe block and into the cache block。

Within the cache log， we log the error message to the console using console do log error dot message and thats how we are getting the output here。



![](img/a93b6c371dd3ab2d2dd53ee17bd5e7c5_3.png)

So let's summarize this。In JavaScript， train and catch are used together to handle errors and exception in the code。

The drive block contains the code that may potentially throw an error or exception and the cache block contains code that will handle the error or exception。

Within the cache block， the error variable is used to represent the error object that was thrown。

This variable can be used to access information about the error such as its message or maybe stack traces and any additional data that may be attached to it。

😊，Using T catchch blockss can help us write more reliable and maintainable JavaScript code by gracefully handling errors and exceptions。

😊，This is all for this video， see you in the next video。Thank you。



![](img/a93b6c371dd3ab2d2dd53ee17bd5e7c5_5.png)