# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p153 p81_05_angular-event-binding -BV1tAygYoEj5_p153-

H there in the previous video we learned about angular property binding now in this video we will learn what is even binding。

So let's get started。 Even bindinging in Angular allows you to respond to user interactions such as button clicks。

 mouse movements， keyboard inputs and more。It establishes a connection between a user action and a method in the component class。

Enabling you to handle and react to those events。 let's see in how many ways we can work with events。

 We can use it to bind even handles so you can bind an event directly to a method in the component class using even binding。

When the specified event occurs， the associated method will be executed。



![](img/6780cd5c2d968f9c2ed6049da1d8e6dd_1.png)

Let's try to understand this to an example。 So I' am here in the Vs code with a basic Agriular setup ready。

 and I'm in app dot component do T5。 So first of all， let's create a function on button click。So。

 this method。Just prints out， let's say console lot law。Pton risk click or button click。Now。

 when to call this method for that in the template， let us create a button。

And we need to attach a click event here so we can do it like this。And then we want to run。

The method that is on button， click。So we need to invoke this。

And then this button text would be just click me。And let's close the button tag。



![](img/6780cd5c2d968f9c2ed6049da1d8e6dd_3.png)

So if I click on save。Let us see we get a button here。

 let us go to inspect and to console and let us click on click you can see that the button is clicked。

And this is how you can attach a click event here。So this example。

 we bind the click event of the button element to the on button click handler or method in the component。

😊。

![](img/6780cd5c2d968f9c2ed6049da1d8e6dd_5.png)

So when the button is clicked， this on button click method will be executed and it locks the message here。

You can bind various events such as mouseover， keydown。

 submit input based on your application requirement。



![](img/6780cd5c2d968f9c2ed6049da1d8e6dd_7.png)

The other way。Yes， event data， so even mining can also provide additional information about a particular event that occurred。

You can access this data in the event handler method by passing the special event object。



![](img/6780cd5c2d968f9c2ed6049da1d8e6dd_9.png)

So， for example。Let's go here， and。This time， let's use a different event。So， we can create a input。

And we can say， key up。And let's attach it to。A method that is on。Key up。

And we can pass here this dollar and event。And here。Let's close the input tag。

And then what we can do is we can say rather than on button click。Let's just say on。Heey up。

We get eed now from the parameter。And for now， let's say any。And then you can say print out。

Which key press， let's say we want to know about so we can say key。

Presed and you get an event object out of the event object， I want to get event taught key。



![](img/6780cd5c2d968f9c2ed6049da1d8e6dd_11.png)

So now if I click on save。Let's go here。And we have the input， lets type a。

 you can see that the key rest is he as come here if I do D， then d has come here。



![](img/6780cd5c2d968f9c2ed6049da1d8e6dd_13.png)

So in this example， we bind the key event of the input element onto this。K on kote method。

In the component so when a key is released in the input field。

 the on key up method will be executed and it will lock the press key to the console using this even dot key here。

So here， this event object provides access to various properties and methods related to events such as target。

 key key code， etc。

![](img/6780cd5c2d968f9c2ed6049da1d8e6dd_15.png)

So even mind allows you to make your application interactive by responding to user actions。

You can perform various operations， update component data。

 called methods and trigger application logic based on events。

By combining even binding with the other types of data binding such as property binding。

 you can create dynamic and responsive user interfaces in your angular application。

This is all for this video in the next video we will understand about angular data binding and specifically two way data binding。

🎼See you in the next video。 Thank you。

![](img/6780cd5c2d968f9c2ed6049da1d8e6dd_17.png)