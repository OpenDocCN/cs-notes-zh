# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P135：Chapter 9 7.Morse Code Example.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll put together everything we've learned about GPIO and timers and device drivers to make a system that plays a message in Morse code。



![](img/93dc9793527b343d32430e64534c1352_1.png)

So this message will blink the blue LED on and off。

 it will demonstrate the easyy red 5IO device driver library。

 and it has some similarities to the work you'll be doing in Lab 7。



![](img/93dc9793527b343d32430e64534c1352_3.png)

So let's start out with our program， name， author。Will include。Easy red 50 dot H。

And let's define duration to be 100 milliseconds that'll be our shortest interval of interest。Now。

 let's define the Morse code for letters， so you might remember Morse code is a series of dots and dashes。

 where a dot is a short pulse and a dash is a long pulse。To spell out letters。

 So the letter A is a single dot followed by a dash。The letter S is dot， dot dot。

The letter O is dash， dash， dash。So。We define that for all the characters in the alphabet and you'll see that certain characters have different lengths than others。

 for instance， E is a single dot because it's such a common letter that it was assigned a short code。

Now let's write a function that plays a particular character。 So we'll take the ASI character C。And。

We will iterate over each of the characters for that code。So for instance， supposing。The character。

Was S。We want dot， dot， dot。So codes of C minus a。If。C was S and A is ASII code 65。

This gives us the appropriate element of the array。A would be element 0， B would be element 1。

 C would be element 2 and so forth up to S。And then we look at the Ithe character in there。

 So we have three dots and then remember a null。嗯。A0。To indicate the end of a string。

 because our strings are now terminated in sea。So while we haven't reached the null termination。

 while this character is not zero。Then， we will pulse。So first we'll turn on the LED。

And if it's a dot， we'll wait for duration， we'll wait for 100 milliseconds。If it said。

 otherwise a dash will wait for 300 milliseconds。Then we'll turn off the LED and we'll wait for another 00 milliseconds。

 and we'll go on to the next character。 Next oven， daughter Dash in the character。

We played the whole character。And then we'll wait for 200 milliseconds in between characters。

If we want to play a string， we can take a string containing a message。

And we'll start at character0 the string。 And as long as we haven't reached the null termination in the string。

 we'll play the corresponding character of the string and then go on to the next character。Finally。

 here's our main program， let's use the pin mode function to set pin 5 to be an output。

And then we will loop forever。Playing S O S。And waiting 400 milliseconds just to pause between words。

So this will play a dot， dot， dot， dash， dash， dash， dot， dot， dot。I I really is。

So now you've seen we've used the easy。risk red5 IO library to use pin mode and digital right。

And we've access to arrays and strings and put it all together。



![](img/93dc9793527b343d32430e64534c1352_5.png)