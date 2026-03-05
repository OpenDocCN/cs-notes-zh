# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p152 p80_04_angular-property-binding -BV1tAygYoEj5_p152-

H there。In the previous video， we learned about angular interpolation。😊，Now， on this video。

 we will learn property binding and aular。So let's get started。

 Property binding is a type of one way data binding in angular that allows you to set the value of an HTMLm elements property based on a component property or some expression。

 it uses square brackets to bind a component property to an element property。

Let's see in how many ways property binding can work。

So we can bind component properties to element properties in this case you can bind a component property directly to an HTML elements property using property binding。

The value of the component property will be assigned to the elements property。

Let' us see this with an example， so let's go to the VS code here I have a basic angular setup ready。



![](img/7906396b95f6acffb03baf93105ca7f5_1.png)

And here into the template， I am inside Ab dot component ortps and in the template。

 lets create a button。And here we can use square wickets for property binding。

 and we can bind this disabled。And here， we can see。

We can mind it with this variable that is as pattern disabled we have to create it。

 We will create it in a moment。And let's see。Click me， something like that。

And let's close the button time。And this variable， we can just create it here inside the class we can say is button disabled to be2。



![](img/7906396b95f6acffb03baf93105ca7f5_3.png)

So if I click on save。You can see that the button is disabled。



![](img/7906396b95f6acffb03baf93105ca7f5_5.png)

So in this example， we bind the disable property of the button element。2。

 the is button disabled property in the component， so the component property determines whether the button is disabled or not。

If is button disable is true， the disable property of the button will be set to true and thereby disabling the button。

 If it is false， then the disable property of the button will be set to false。



![](img/7906396b95f6acffb03baf93105ca7f5_7.png)

And it will enable the button。Second way is expression evaluation。

So property binding also allows you to evaluate expressions in the template you can perform logical operations or include methods within the property building syntax。

So here let's again go to the VS code and let's understand this to an example。



![](img/7906396b95f6acffb03baf93105ca7f5_9.png)

So here we can just say。Be that。And the speed tag， let's say the result。Of。等。😊，Minus5。

And we need to evaluate this so we can say 10 minus5 here。And that's it。Next， we can say input。

And to this input， we want to bind the value property。With our function， so we can say get。

Initial value and this is the function that we will be creating in a second。

let's invoke this function here。So here what we can do is we can say get。Initial。Value。

And at this point， it will just return。Let's say a text of initial value， that said。



![](img/7906396b95f6acffb03baf93105ca7f5_11.png)

So let's test this out if I click on save。You can see that the template that we get is。5。

 it evaluates the expression and the initial value is coming as the default value here。

So in this example， we use property mining again to set the value property of this input。

Eleimate the values obtained by calling this cat initial value function defined in the component。

 the result of method call is assigned to the value property of the input element。



![](img/7906396b95f6acffb03baf93105ca7f5_13.png)

![](img/7906396b95f6acffb03baf93105ca7f5_14.png)

So property binding allows you to dynamically set and update HTML element properties based on component data or expressions。

It provides flexibility and interactivity to your applications U are。

 One thing to notice that property binding is a one way data binding。

Meaning that it only sets the value of the elementss property based on the component property or expression。

 It does not update the component property If changes are made in the U I。

 This is all for this video。 In the next video， we will learn about angular even bit。

See you in the next video。 Thank you。🎼。

![](img/7906396b95f6acffb03baf93105ca7f5_16.png)