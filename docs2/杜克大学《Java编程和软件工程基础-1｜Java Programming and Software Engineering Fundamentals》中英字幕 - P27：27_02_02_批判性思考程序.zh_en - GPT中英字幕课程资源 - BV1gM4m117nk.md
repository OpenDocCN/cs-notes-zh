# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P27：27_02_02_批判性思考程序.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

Now， you are going to think about what it would take to turn the blue devil into a green devil。

 for example， to celebrate an an environmental initiative on campus。

 What code would go inside the forelo to make the devil green，Specifically。

 we want to end up with a background still being white and the foreground having a 0 for red， a 2。

55 for green and a 100 for blue。😊，Take a few moments to think about how to do this。

A first thought might be code that looks like this Here。 we set the red。

 green and blue components of each pixel directly to the values we want。 However。

 as the loop goes through each and every pixel， it turned them all green。

If instead you only set the green of each pixel to 255 and the blue to 100。

 you get an image that looks like this。This code made the foreground the right color。

 but now we have a yellow background。Take a few moments to think about why this happened。

Did you realize that the background is yellow because it has a red value of 255。

 making the overall color value of the background， red 255， green 255， blue 100？

Because we did not change its red value， it kept the original one。

 And since the background was originally white， that value is 255。To make this work。

 we're going to need code that makes a decision using a conditional statement like we've seen before so that it can change the foreground。

 but not the background。Here is one possible idea for an if statement。 If the blue is 2，55。

 this seems like a logical choice because the foreground is blue。

 and we want to change only the blue pixels to green pixels。

Take a moment to think about what this code does。 Do you think it will accomplish what we want it to。

This code actually turned to the background green， but left the foreground blue。

 That behavior is the opposite of what we wanted。 Doesn't that seem surprising。

It is important to remember that the computer only does what you tell it to。

Anytime your program does seem to behave oddly， there is a good reason behind it。

 we're going to take a closer look to understand what happened。

The white pixels in the image have 255 for red， 255 for green， and 255 for blue。

Because each white pixel has blue equal to 255， those pixels are set to green by this piece of code。

However， the blue pixels in this image are not pure blue。 They have 45 for red，39 for green and 225。

 not 255 for blue。 Accordingly， the condition is not true for the blue pixels。

 and they are left unchanged。To fix this program， you would need a condition that distinguishes the foreground pixels。

45 red，39 green，2，25 blue from the background pixels，2，55 red，255 green，2，55 blue。

 There are many possible conditions we could write。 you could check if red is less than 200。

 If green is 1，50。 If blue is equal to 2，55， or many other possibilities。

Here we made one such change， we changed the code to check if red is less than 200。

This code produced a green blue Dev image that we wanted。

Whenever your code does not do what you want， thinking about why it is behaving a particular way is an important part of fixing it。

 We'll talk more about debugging code soon and teach you how how to apply a version of the scientific method to fix problematic code We'll also teach you how to invest some planning time at the start of the programming task so that you can write better code the first time and spend less time fixing it at the end。



![](img/ee8ec13493173e3f329f686faad6187a_1.png)

![](img/ee8ec13493173e3f329f686faad6187a_2.png)

![](img/ee8ec13493173e3f329f686faad6187a_3.png)