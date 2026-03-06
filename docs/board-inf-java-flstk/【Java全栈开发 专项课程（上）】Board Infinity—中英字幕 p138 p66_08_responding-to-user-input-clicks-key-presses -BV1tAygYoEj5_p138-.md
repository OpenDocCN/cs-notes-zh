# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p138 p66_08_responding-to-user-input-clicks-key-presses -BV1tAygYoEj5_p138-

Hi there in the previous video， we learn events and even listeners in JavaScript。Now， in this video。

 we will learn how to respond to a user input。So let's get started。

When building interactive applications or websites。

 it is important to be able to respond to user input such as clicks or key presses to provide a better user experience This involves using event listeners to detect when a user interacts with the application and executing specific code in response to those events。

Let's look at some examples。So first we have click event。

You can use JavaScript to add even listeners to HTML elements and detect when they are clicked。

For example， you could have a button that when clicked triggers a pop up window to appear。



![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_1.png)

Let's also see one example in VS code。So here I am in my VS code and I have a index for HTML page ready with minimum HTML template whether script time as well。

So first， let's create a button。😊，And we can give here an I of， let's say my button。

And then we can give it。 lets say a text of collect me。

Next we can go inside the script tag and we can write some JavaScript script if I click on save first we will have a button here。



![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_3.png)

是。So what I want is currently you can see nothing is happening。😡。

I want to attach a click event listener on this button。



![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_5.png)

So what I will do is I will first target the button in the script tag， so Ill say con button。

And it would be you can use any selector you want， I will use query selector so document dot query selector。

And we can pass here the I of my button like this。Next。

 we can attach email listener so we can see button dot add email listener。It takes two arguments。

 First， the type of。The event that is click in our case and a call back function。

This callback function runs as soon as it triggers this particular event At this point。

 I just want to alert， let's say hello world。

![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_7.png)

If I click on save， if I go here and lets click on click me and you can now see that it a pop up comes why because it triggers this click event and this callba function runs that just alerts and print hello world。



![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_9.png)

![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_10.png)

So in this example， we are using the add Even listener function to attach a click event。

And then we are passing a callback function that gets executed when the event is triggered。

Second is key press events。You can also detect when a user presses a key on their keyboard and execute code in response。

😊，For example， you could have a search box that automatically updatess search results as the user types。

Let's create that example as well。

![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_12.png)

So for that， first of all， we need to have our input field。

Let's delete all this and let's create an input fee。To this input。

 I just give it an I of let's say search box。And。A type of text。Now in the script tag。

We can start writing our JavaScript code before that you can see the input has already come here on the screen。

So we can see here， cost。Search box this variable will hold the elements so we can say document dot query selected。

And we can pass here the I S search box。Next what we can do is we can just attach event listener this time the event listener would be key up。

So the event is key up and on that， this call that function will run。In interface function。

 you can just write code to update search results and that would go here。Or for now。

 we can say console dot lock。Event regard。

![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_14.png)

So if I click on save， lets go to inspect then to console and here we will see as soon as I press a key a event is triggered as soon as I print s I have not released the key as of now as soon as I release the event triggers second time so whenever user release the key this callback function will run。



![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_16.png)

So here in the Add even listener function is used to attach a key up to the search box input element。

 so whenever the user releases a key while typing in the search box。



![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_18.png)

The anonymous function passed as the second argument is executed。

 which could include the code to update search results。



![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_20.png)

So let's summarize this。Responding to user input such as clicks and key presses is an essential part of building interactive applications or websites。

This involves using event listeners to detect when a user interacts with the application and executing specific code in response to those events。

😊，The examples of how to respond to user input， including。

Click events to trigger a pop up window or maybe using key press events to update search results as the user types。

To implement these functionalities， HTML elements are used to trigger the events and JavaScript code is used to attach the event listeners and execute the desired functionality。

😊，This is all for this video in the next video we will create interactive user interfaces with events。

😊，See you in the next video。 Thank you。🎼。

![](img/ff0c3591d1e0ce8f0afbfbe5b1b2594d_22.png)