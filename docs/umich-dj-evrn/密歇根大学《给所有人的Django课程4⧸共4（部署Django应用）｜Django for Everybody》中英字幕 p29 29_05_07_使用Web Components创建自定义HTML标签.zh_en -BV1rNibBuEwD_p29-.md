# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p29 29_05_07_使用Web Components创建自定义HTML标签.zh_en -BV1rNibBuEwD_p29-

![](img/79c552fe4d5a2f07c4fbb87f68b35112_0.png)

![](img/79c552fe4d5a2f07c4fbb87f68b35112_1.png)

Now I want to talk a little bit about how you or us。

 we can create our own tags and then use them throughout our markup。

So what is this whole thing about creating new tags， Well。

 programmers hate to repeat themselves that just from the third week of learning how to write software。

 it's all about don't repeat yourself， DRY。And that's because if you write the same code over and over。

 especially if there are tiny changes in that code or little like if then else's。

 it really causes errors。 And if you have a bunch of code。 And by now。

 you've seen this in this course， If you cut and paste and make small changes and then paste and make small changes and paste and make small changes。

 it's convenient。You're repeating yourself and then making changes。

 But what if you started with a bug and all that stuff you past it， or you find a bug later。

 And now you got 40 places and you got to make the same tiny change。 It's really frustrating。

 And this just means that a big part of software is how to avoid repeating ourselves。

Things like functions with parameters， Ob or approaches with base classes that were extending The class base views in Django versus just function views。

 I mean。The function views are simpler and easier to understand。

 Class B views are beautiful and elegant， but hard to understand。Like templates。

 like the navigation that you've been building。 And we say extends base Botra do Hm L。

 That's a way to not put the same navigation tech H in every page。 And like the percent URL。

 You can change the remap URLls and Us dot P Y and not have to make changes in your templates again。

 we don't like to repeat ourselves。So what we've been doing up to this point is we've been doing all of our templating in the server。

And so if you go way， way back to when were just looking at views for the first time。

 this is a function based view here。 But you see this render。

 Now if you recall what render does is it takes a template plus a context。 In this case。

 it's a dictionary that's mapping Zap to 42 and says render this give me back some HTML and then we send it back to the browser。

 And if you look at the template， you see we've got these little curly braces。

 double curly braces that says Zap says go into the template and grab the zap value and put it in here。

 And so this is just kind of our model view controller。 And this is the big picture。

 I promised you wouldn't see it very often after the middle of the class。 But here it is again。

 and we take these templates。 we pulled data into the templates from the models。

 We make context and we send that back to the browser。

 classicic request response cycle model view controller。 So what we're going to do now。

 is we're going to take a little tiny。😊。

![](img/79c552fe4d5a2f07c4fbb87f68b35112_3.png)

![](img/79c552fe4d5a2f07c4fbb87f68b35112_4.png)

Of that template processing and move it into the browser。

 We're still going to have a server based template。

 but we're also going to have a little tiny template。



![](img/79c552fe4d5a2f07c4fbb87f68b35112_6.png)

In the browser， let's take a look at how we would do this。

 And we're doing this by creating our own tag。And so we have a tag。 See。

 it says less than DJ free dash greeting greater than That's a tag。 It's a tag we invented。

And so we can pass some parameters， attributes。 We get to define what those attributes do。

 We can have a tag that has an ID on it so we can mess with it。 I put up a button that says click me。

And that script type equals module source equals dot slash 16 DJ free greet I Js。

 That's the code that adds the DJ free greeting tag to the browser。 So once that's imported。

It goes and creates the tag， and then we can use the tag。

And then the little script is simply changing the name attribute。

 And so we're passing almost as a parameter。 Think of it like a function or a macro。

 It's like a HTMLm template， which we're about to see in a moment。

 So name is the thing we're passing in。 And not only are we passing it in。

 but we can change it dynamically based on a dom event。And that's what the due change is doing。

 So let's take a look at what this template is。

![](img/79c552fe4d5a2f07c4fbb87f68b35112_8.png)

And so the concept of a custom element， that's something that's been in browsers for quite some time。

 And if you just write your own custom element， you can do everything we're doing here。

But it's a lot more of verbose。 And so what we do is using object orientation。

 We're grabbing a little tiny library called lit element。

So lit element is a custom element that has a lot of base capabilities into it。

 And so we're extending lit element to make a class called simple greeting。

And that just means there's a lot of boilerplate that we don't have to repeat。So in it。

 we tell it our interaction with the outside world， and we say there is a property called name。

 which turns into an attribute on the tag。 if you look back at the tag。

 we have a constructor and we in that constructor， we call our parent super。

 that's the constructor of lid element， and then we set our default value， so it's named somebody。

And there's this whole thing， I won't go into it in great detail。

 there's a thing called a shadow dom。

![](img/79c552fe4d5a2f07c4fbb87f68b35112_10.png)

Where you can inherit the C， S S and other styling from the enclosing document。

 or you can have your own C S S inside the lit element。 I'm choosing not to isolate my mark up。

From the enclosing document。 and so I'm doing this create render route that says， just put my macro。

 put my text into the enclosing document and whatever HTML， whatever CSS。Javascript libraries。

 et cetera。 They're just inherited into my code。 You can make these web components in a way that they can go into any H T mail and they bring their their styling with them。

I tend to use these where I'm want to build an application， and I want my styling， I want my font。

 and I want my colors and my spacing and whatever I want that to be like bootstrap across the whole thing。

 which is kind of how we're doing it in this class。And so I don't like shadowow Do。

 but that's another。That's another approach is to make these templates。Super isolated using Shado。

But the meat of all this is the render。 And again， let's go back and think about the render in the view that I just showed you。

 What is the render to， It takes some templated H T M L， and it makes replacements。

 And you'll notice that this one has curly braces Do this dot name。 While， this is the jascript。

Object instance variable and dot name is a an object attribute。 Let's go back。 That's name equals。

 the attribute name equals world。 name equals first。 And then later， I set that to be second。

 And the return Hl back， the back quote's very important。 It's not a forward quote。

 It's a dynamically rendered template and what's cool about this is it's responsive。

 which means that if you change the name attribute on this DJ  free greeting tag That text in the browser will re rendernder with the new stuff。

 And so that's what's happening。When you say click me and it turns from Ho first to Ho， second。

And so this is。We're not going to have you write too many of these。 I'm going to give them to you。

 I'm just showing you how this sort of works。 Now， this may seem familiar。

 and you may have taken other classes， or you've may learned about things like react or view or Svelt。

Or even。Java server faces or JSP template tags or spring time leaf。

 There's all kinds of what I'll call custom component ecosystems。

 ways that you can have a tag that you invent right， like in react。

 you can make a function called my button and then you have a new thing called my button and then you can use the My button tag right and so it's。

There's many ways。 And I'm not going to tell you not to use reactor viewers feltelt。 I like lit。

 and I'm including lit here because it's kind of the simplest。

 It's really almost a foundational capability rather than a fancy custom component ecosystem。

 And going forward， you know， this seems to me to be just a cool part of the browser。

 And we can use it， however， we want。 And if you look at the trend and a templating not just the little bits of the template。

 but eventually whole templates。 And then。😊，Much of the view。

 much of the controller moves into the browser。 And in the most extreme。

 the controller and view end up completely in the browser。

 The model is partially in the browser and partially in the server。 And then we have。



![](img/79c552fe4d5a2f07c4fbb87f68b35112_12.png)

Json and Web services so that the actual persistent and permanent data is still stored in the server。

 but pretty much all the mark up is in the browser， and that makes it so that it can be very。

 very responsive。 And ironically， Json is the next topic in this class， so。

We're first learning about how to make these tags， and then we'll learn how to feed data from the server in these tags。

 And so a kind of a very modern， futuristic application will tend to have the model view in the controller often running mostly in ja any little bit from the server to get it started。

 But then you have this thing called Re web services。

 And the views will read and write data in the database using rest web services。 And so。

That's kind of what we're going to go do next， and that is how to talk and exchange data from the browser and JavaScript and the server。



![](img/79c552fe4d5a2f07c4fbb87f68b35112_14.png)

So in this section， we talked about JavaScript and the browser document object model。

 What is the window， adding handlers， adding Dom event handlers， window event handlers。

 how we can grab and change data in the document object model。

 how we can extend the document object model， how we can fiddle with the CSs like show and hidede。

 and then how we can use fetch to make network requests， and we finished making web components。

 So there's a lot to this。And it gets really fun when we start moving model data back and forth between the server and the JavaScript。



![](img/79c552fe4d5a2f07c4fbb87f68b35112_16.png)

![](img/79c552fe4d5a2f07c4fbb87f68b35112_17.png)