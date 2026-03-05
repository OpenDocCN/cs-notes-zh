# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p139 p67_09_creating-interactive-user-interfaces-with-events -BV1tAygYoEj5_p139-

Hi there in the previous video we learn how to respond to user input such as clicks and key press events now in this video we will create an interactive user interface using events。

So let's get started。Creating interactive user interfaces with events is a key part of building engaging web applications。

😊，Events are actions that happen in the browser such as a user clicking a button or scrolling the page。

 and they can be used to trigger specific functionality in your application。In this context。

 events are used to create interactive user interfaces that respond to user actions in real time。

Let's create an interactive interface。😡。

![](img/5b20c68a76f60f69f3b6d50099ef6173_1.png)

So I'm here in my VS code and I have a basic HTMLl setup ready along with script tag。

Let's say that you are building a to do list application and you want to allow users to mark items as completed by clicking on the item。

Let's see how we can do that。So first in the body， lets have an H1 and we can just create a to do list。



![](img/5b20c68a76f60f69f3b6d50099ef6173_3.png)

At this point， they should be coming in the web page。



![](img/5b20c68a76f60f69f3b6d50099ef6173_5.png)

Next， we can have some unordered list。And inside this， we can have list items。

 let's say we want to buy groceries。Or you can say we want to do some laundry work。

Or we can have one more ally item， let's say clean house。

So we have a to do list and we have these three items in our to do list。Next。

 we will go to our script tag and we can start writing our JavaScript foot。

Here I want to target all of the list items so I can use。😡。

Different methods like class name or query select all， so I will say cost。List items。

And here I will use document dot query selector all。And we can pass the tax selector here。

It will target all of the list items。Then we can run a loop。So I can say list items dot for each。

And for each item， it takes a call back function。 We want to do something。So on each item。

 what we want to do is we want to attach an event listener so I can say item。

Dot add event listener and the type of event would be click。

And then we want to run a callback function。So here we will say item dot class list。Drt toggle。

And we will。Add a class that is completed。Proling means。Just like us on and off button。

If the class is there， it will remove it， if the class is not there， it will add it。

So we are talking about a completed class。We have to create this class， so what we can do is。

Below the title， we can have a style tag。And we can set dot completed。And we can say。

 text decoration to be。Line through， and we can give it a color of gray， as well。If I click on save。

 let's test it out。

![](img/5b20c68a76f60f69f3b6d50099ef6173_7.png)

So if I go here， if I click on， let's say buy gries， it cuts， it has a line through here as well。

 here as well， When we click on again since it already has the class， it will remove it。

So this is how you can create interactive applications using JavaScript。



![](img/5b20c68a76f60f69f3b6d50099ef6173_9.png)

In this example， the HTML page contains an unordered list with three to do items。

 so when a user clicks on the to item and even listener is triggered that toggs a CSS class on the item causing it to be displayed with a line through and a gray color。

The CSs class is defined here in the head of the HTML using the style tag。



![](img/5b20c68a76f60f69f3b6d50099ef6173_11.png)

So let's summarize this。Using events is a crucial part of creating interactive user interfaces in web applications。

Events can be used to detect user actions such as clicks and key press and trigger specific functionality in response。

By using event listeners to handle user input， web developers can create engaging and dynamic applications that provide a seamless user experience。

We have seen some examples of how events can be used to create interactive features in real world applications。

Such as to do listist app。This is all for this video， see you in the next video。Thank you。😊。



![](img/5b20c68a76f60f69f3b6d50099ef6173_13.png)