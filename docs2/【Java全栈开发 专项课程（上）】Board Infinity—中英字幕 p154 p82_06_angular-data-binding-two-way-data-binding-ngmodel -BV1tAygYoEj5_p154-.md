# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p154 p82_06_angular-data-binding-two-way-data-binding-ngmodel -BV1tAygYoEj5_p154-

Hi there。 On the previous video， we learned about event binding。😊，Now。

 in this video we will learn angular to way data binding using engine model， so lets get started。Now。

 2 way data binding is a powerful feature in Angular that allows you to establish a bidirectional synchronization between a component property and an input element in the UI。

It ensures that changes made in either the component or the Ui are automatically reflected in one another。

 You can use Nng model directive to achieve two way data binding。

It combines property binding and even binding to bind a component property to an input element and keep them in sync。

Let's see how you can use two way data binding using Nng model。 So first。

 you need to import forms module。 So before using Nng model。

 you need to import the forms module from angular forms in your angular module。

 This module provides the necessary directives and services for working with forms and data binding。

 Second step is to bind component property to input element。 So to establish two way data binding。

 you can use Nng model directive within an input element and bind it to a component property。

And next， you can just update the component property and input element。

So where two way data binding changes made in the component or the input element are automatically reflected in both places。

So let's try to understand this using an example。

![](img/b0cbbe02dc584d28f1c800babcbb7420_1.png)

So let's go to the VS code and here I have a basic angular project ready and currently I am in app dot module or T S5 the first step is to import。

The farm's module。And this， we need to put it inside imports like this。

And now we can start using Nng model。So lets go to app or component or Ts and in the template。

 lets create input。And first of all， lets create a variable name and lets re it empty string for now。

Then in this import， we can use our engine model like this。And we can make it equal to our name。

And you can also give this input， let's say， a placeholder。Of let say enter。Your name。

And let's also have a P tag to display the output。So we can say welcome。

And let's use interpolation to pass the name。And let's close the P tag。



![](img/b0cbbe02dc584d28f1c800babcbb7420_3.png)

So if I click on save， lets go to the web page and here you can see we have input here and as soon as I type any name here lets say John you can see on the real time it is updating the UI as well。



![](img/b0cbbe02dc584d28f1c800babcbb7420_5.png)

So in this example， we bind the name property of the component to this Nng model。

Directive within the input element， the value of the name property will be synchronized。



![](img/b0cbbe02dc584d28f1c800babcbb7420_7.png)

With the value entered in the input field， as you can see here。



![](img/b0cbbe02dc584d28f1c800babcbb7420_9.png)

So the value of the name property will be updated whenever the user types into the input fee。

Thanks to the even binding part of N model。Similarly。

 if you update the name property programmatically， the input field will reflect with the updated value。



![](img/b0cbbe02dc584d28f1c800babcbb7420_11.png)

So two way data binding using Nng model simplifies the handling of user input and component data synchronization。

It reduces the amount of boiler plate code needed to keep the component and Ui updated。

So remember to import the forms module in your angular module to use N model effectively。

This is all for this video。 See you in the next video。Thank you。



![](img/b0cbbe02dc584d28f1c800babcbb7420_13.png)