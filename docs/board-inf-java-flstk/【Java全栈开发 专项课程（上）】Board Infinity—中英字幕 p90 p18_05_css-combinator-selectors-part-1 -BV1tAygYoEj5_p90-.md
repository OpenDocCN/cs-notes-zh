# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p90 p18_05_css-combinator-selectors-part-1 -BV1tAygYoEj5_p90-

系了。In our previous video， we talked about simple selectors in CSS。

Today we will be discussing combined selectors in CSS。Combined selectors or combbininators。

A a way to target specific elements on a web page。By combining mining multiple selectors。

They allow developers to create more specific and targeted styles of elements that may not be easily selected using a single selector。

There are different types of commators。Or we can say combine selectors。

Let's look into them one by one。The first one is descendant selector。

A descendant selector matches an element。That is a descendant of another element。

It means we have a document。To the div inside that div， we have multiple paragraph tags。

And we have some paragraph tags outside this stiff。No。

If you want to only highlight these paragraph tags which are inside the div， but not these ones。

Then what you can do either you can assign a class to them and then you can change the background color for that class or you can use a descendant selector lets just see how we can implement this in our code。

So this is our HTML document and it looks something like this on our browser。

 so what we will do for now will remove this。

![](img/f598a6e3caa8363459e6a72a02649553_1.png)

And we will make some changes over here。Let's say we' will be creating a new di tag。

And inside that do， we will have one more aent tag。Wches。I am。Inside dove。Now。

 if we want to change the color for this one， what do we need to do？

We either need to assign some unique ID to it and then apply that color to it。

If we have multiple at tags， then we might need to create a class。

 put that class into all the at1 elements。And then what we can do， we can change the color。

 but we can do something else which is called using the combbininator and which type of combinator specifically the descendant selector。

So we can write it something like this we can put。The name of the parent。

Then it's descendant and then we can write our style。 So in this scenario right color。



![](img/f598a6e3caa8363459e6a72a02649553_3.png)

Red。So you can see it is only changing the dash1 tag， which is inside。



![](img/f598a6e3caa8363459e6a72a02649553_5.png)

The di， it doesn't matter if these tags are wrapped by any other tag。 Let's say I have a section tag。

And inside that I have a data。And inside that I have an at tag。You can see。

It is still changing it why， because whenever we are using this dis selector。

It means all the dash tags， which are inside the div。Whether they are inside any other tag。

 if that tag is insideive。It will change the color for that also。So this is the descendants selector。

So letll just move forward and look into our second combinator。



![](img/f598a6e3caa8363459e6a72a02649553_7.png)

Which is child selector。A childild selector matches an element that is a direct child of another element。

 so it is。😊，Somewhat like descendant selector， but the difference is， if you have a div。

Inside that you have one P tagag， second P tagag and the third P tag is inside in another div。

And if you apply a descend selector， the color for all these three would change。

 but a child selector only see the direct child。The direct child of div。I is only this speed tag。

 it is not this one because it is inside and another tag。This is how the child selector works。



![](img/f598a6e3caa8363459e6a72a02649553_9.png)

And let me show you how we can use this in our HTMLMl code。



![](img/f598a6e3caa8363459e6a72a02649553_11.png)

This is the code that we have written。Or all lifted。So we can alter this for using。

The child selector。How does the child selector work well before checking that out。

 lets just see the current behavior。As we know the current behavior is the color for all the attachment tags which are inside the stove has been changed。

😊，Now， what we want， we want to change the color for the direct。Childs。

 not for all the a type which are present inside their。So for doing that。

 we will be using child selector and how we can do that。By just putting this greater than sign。

Between the parent。

![](img/f598a6e3caa8363459e6a72a02649553_13.png)

And the change。And now you can see only the first two at one tag has changed their color。

 not this one and the reason is we have used child selector。



![](img/f598a6e3caa8363459e6a72a02649553_15.png)

I hope you are able to understand。What a child selector and descend selector is。

And you will be using them in your next project。We have two more。Combine selectors to talk about。

 and we will discuss about them in our next video。

![](img/f598a6e3caa8363459e6a72a02649553_17.png)

🎼。

![](img/f598a6e3caa8363459e6a72a02649553_19.png)