# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p142 p70_03_using-ajax-to-load-content-dynamically -BV1tAygYoEj5_p142-

H there in the previous video we learn how to create and remove dom elements using JavaScript now in this video we will learn how to use AjaX to load content dynamically。

So let's get started。Ajax or asynchronous JavaScript and Xml is a technique used in web development to load content dynamically without requiring a full page refresh。

This technique allows web pages to load new content or data from the server in the background without interrupting the user's current interaction with the page。

To use Ajax in a web page。We typically use the XmL STTP request object in JavaScript to send an STTP request to the server and then process the response using JavaScript。

We can use this technique to load content from a server and display it on the web page without having to reload the entire page。

Let's look at an example of how to use Ajax to load content dynamically from a server。



![](img/25314f89c724d8f98398715027d7e75c_1.png)

So let's go to the VS code and here I have a basic HTML file ready。

Let's start creating a basic template here。 So let's say I wanted H1 and in this H1。

 you can just give it。Aheading of， let's say， users。And then we can just have an unordered list。

 Let's give it an Id of user list。And let's re it empty for now。

Next what we will do is we need to write JavaScript now so we will go inside the script tag and we can capture this user list using Dom selector。

So let's say cons usually。Equals to document。Dot query selector。And we can pass the ID that is hash。

Use the list。Then we can say Po X， HR R， and we can create this new。Ximl request， object。

So it is X Ml。StDB request。And we can create an object like this。Next word。

We want to do is we can say X H R and we need to have an event that is on ready state change。

And on this， we need to run a function。So let's use a function here。 and we can say if。X， HRR。

Thought ready state is。Equal equal to。Xma。S shouldB request， dot done。In that case。

We want to have one more in if condition。 So here we can see if X HR dot status is。

200 the queens week got the response successfully。So we can say con user data。And at this point。

 we can parse it。And we can pass what we can passse the response text that we are getting from etc object。

So we can say response text here。Next， what we want to do is。We can say user data。

And we want to look through it so we can say for each。And here we can get a single user。

 and then you want to run this call back function for every single user。

 And then you want to say con new user。And you want to create an all element for it so we can say document dot create element。

😊，And the element that we want to create is ally。And after that， we can say con。New user， let's say。

B。And this would be equal to document dot。Create。Text node and。

The load we want to create is coming from user that is name。

 so lets use the name as the text that we want to append。And now we can see new user。

Dot append child。 and let's append new user text。And then we can say user list。Dot append child。

 and let's append new user。So this is for the if condition。

 what if you want to have an else condition as well？So after this， we can just say else。

And we can say console dot lock。And you can say， there was。A problem with the request。

Something like that kind of an error message。After that。

 what we want to do is we want to make the request so we can say X chart to open。

And we want to make a request of type K。And you want to pass the URL。



![](img/25314f89c724d8f98398715027d7e75c_3.png)

So the URL that we would be using is from JN type code， so you can search for JNT code。com。



![](img/25314f89c724d8f98398715027d7e75c_5.png)

And here we want the endpoint as slash users。

![](img/25314f89c724d8f98398715027d7e75c_7.png)

Here you can see we will get list of users， so let's copy it and let's paste it here。

And then what we want to do is we just need to say exc chart dot send that will send the request。



![](img/25314f89c724d8f98398715027d7e75c_9.png)

So if I click on save， we should get a user list here in the web page。



![](img/25314f89c724d8f98398715027d7e75c_11.png)

So this means it is working perfectly fine。So in this example。

 we use AX to load a list of users from the JSN placeholder API and we are displaying them on the web page。

We start by using XmL STP request object to create a new STTP request。

 and then we define a callback function to handle the response when it is received from the server。

Now， when the response is received， we check the status of the response to make sure that it was successful and then we pass it using dot pass the response data into a JavaScript object。

Finally， we loop through them。😡，And dynamically create ally elements for each user which are then appended to the user list。



![](img/25314f89c724d8f98398715027d7e75c_13.png)

That is U on the Web page。So let's summarize this。Overall。

 using AjaX to load content dynamically from APIs is a powerful technique that can greatly enhance the user experience of web pages by allowing them to load new content in the background without requiring a full page refresh。

😊，This is all for this video in the next video we will see how to handle errors and exceptions in JavaScript。

See you in the next video。 Thank you。

![](img/25314f89c724d8f98398715027d7e75c_15.png)