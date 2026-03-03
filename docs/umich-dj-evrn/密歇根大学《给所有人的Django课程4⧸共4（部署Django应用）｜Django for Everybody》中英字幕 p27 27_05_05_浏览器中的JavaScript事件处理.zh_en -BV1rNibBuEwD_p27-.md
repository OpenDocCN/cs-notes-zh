# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p27 27_05_05_浏览器中的JavaScript事件处理.zh_en -BV1rNibBuEwD_p27-

Now let's talk about browser events。 We've been talking about events all along。

You we have done an on click handler， which is a shortcut to in effect register a click event handler。

 but we're just doing it with a shortcut of the oncl attribute。 And then when we do a set time out。

 we're actually。Creating a timer event so the timer starts and then when the timer expires。

 the event fires and our code is run， so we've been doing this all along。

 but there is an entire event registration system inside the browser and we can say I would like to register an event for something to happen on this tag and we can hook things in all over the place and there's a separate event registration system oncl is like a shortcut。



![](img/38df08beafe7dd347a4e0950e92c58da_1.png)

Using an attribute that eventually registers the event on our behalf。

 and that's why you see the little event when you do the inspect element。

 And so if we take a look at the code here， we're going to do the same thing that we did in 03even。

 htm which we've seen before and then we're going to do it again in 1010even Htm andre we're going to show kind of the more generic way of doing it So in 03even do Htm。

 we have an oncled method we've done this before and it calls my funk when that method is clicked and if you do an inspect element you see that that anchor tag has。



![](img/38df08beafe7dd347a4e0950e92c58da_3.png)

An event on it， the kind of more pure way to do it that where we're really explicitly registering the event。

 these two things are frontents and purposes equivalent。



![](img/38df08beafe7dd347a4e0950e92c58da_5.png)

Is we're going to instead of having that unclick method on the anchor tag。

 we're going to have an ID equals Zap， and again， we have to put the ID on so we can get our hands on it inside JavaScript。



![](img/38df08beafe7dd347a4e0950e92c58da_7.png)

So we created an H1 and a paragraph with an anchor tag in it。Then we start our JavaScript。

 and the JavaScript starts by defining a function， doesn't do anything， it just defines the function。

 and then we call document。ge elementement by ID Zap now that is grabbing that anchor tag。

And then it calls an element method called add event listener and it's got two parameters。

 The first parameter is I'm interested in the click event， I want to listen for click events。



![](img/38df08beafe7dd347a4e0950e92c58da_9.png)

And when click events happen， call my fun now again。First class functions。

 there's no parentheses on my， that is a function reference that we define three lines earlier。

 right？And so it accomplishes the same thing and if we look at 10even。htm and we take a look at it。

 you see that the anchor tag with the ID of Zap doesn't have an onclick on it。

 but it has a registered event and that's because we registered the event using JavaScript。



![](img/38df08beafe7dd347a4e0950e92c58da_11.png)

![](img/38df08beafe7dd347a4e0950e92c58da_12.png)

Now， if we click on it， it does the exact same thing。 That event is triggered， it looks up and says。

 well， when a click happens I'm supposed to call my fun。 and so this notion of。

Adding event listeners is a more general purpose notion than simply on click。

 I think I like to think of on click as a shortcut to registering it。 Now， you might say。

It's a lot shorter。 and one thing about JavaScript is it's a bit wordy at times， right。

 document do get I want by ID D do a event listener， lot of a lot of JavaScript but。

It does what you need it to do， and I'm not saying you shouldn't use on clickick。

But I want to show you the more general way of doing it There are other kinds of events that we can connect to。

And so this in this case， I'm going to just have a header and no paragraph。

 and then in my JavaScript I'm going to create a function and in that function I'm going to log the current height and width of the window。



![](img/38df08beafe7dd347a4e0950e92c58da_14.png)

Okay， when this function is called， it's only going to log it。 Now。

 what I'm going to say is window do add event listener。 now remember document dot add event listener。

 that's a different thing， right， windowow dot add event listener is adding an event to the window。

 Remember how the window is the thing that gets larger and smaller and has scroll bars， etc ceter。



![](img/38df08beafe7dd347a4e0950e92c58da_16.png)

So I'm saying I would like to register a bit of my code to be called every time the window is resized。

😡。

![](img/38df08beafe7dd347a4e0950e92c58da_18.png)

That's what quote resize quote is。 My funk is to thing to call。

 So now what happens is you display this。

![](img/38df08beafe7dd347a4e0950e92c58da_20.png)

And then you start changing the size of the window and on your console log is a boom zoom， you know。

 window height 135，136，137。 So as you're making that window larger and smaller。



![](img/38df08beafe7dd347a4e0950e92c58da_22.png)

Your code is being called every time。 Now， why might you want， why might you want to do this？ Well。

 one of the big things in website design is to do what's called responsive design。

 And that's as the thing gets narrower or heart， the higher or smaller， like mobile。

You want to change the Ui。 You might have a big screen。 You might have a more complex Ui。

 and then on a small screen， you might want to have a narrow a more narrow Ui。

 Now often things like bootsottap， take care of all this for us。

 But still bootsottap needs to get their hands on the resize event。 so they know， whoa。

 the screen size changed。 So I need to kind of tweak the mark up a little bit。

 So this is an example of a window event that allows you to render an opinion as to what you want to happen。

 Every time the screen resizes。 Now， another issue that you that's an important event to know about is what's called the content load complete event。

Modern web pages are very， very complex I mean the things I've been showing you in this series of lectures are simple because I want you to be able to see them on a slide。

 but real web pages with menus and pretty pictures and colors and spinners。

 all that stuff right there's so many things you got to download the HTML then you got a bunch of CSS and some images and JavaScript libraries and so sometimes you're going to just get like 100 assets when you download a page the first one is the HTML。

And so the problem is is it can take a while for all these things to get orchestrated by the browser。

 it reads the HTML， it sees a CSS， it loads the CSS， it sees a JavaScript thing。

 loads the JavaScript， to dota dota， and then it some images and it takes some time and it does this all。



![](img/38df08beafe7dd347a4e0950e92c58da_24.png)

Interleaved and in parallel。 and eventually you want to know， are you done yet are just are you done。

 and so if we take a look at a typical at the page ofjanangle for everybody。

 we see about 30 requests。And many requests and you'd like to know when that's all done because you can't write JavaScript that references a tag that doesn't exist yet。

 Or if you you want to write JavaScript that does something to an image like changes its size or check something or hides it or shows it。

 you gotta wait till the image is there before you start messing with it right so there is a special event。

 it's pretty simple And in this you use a script tag near the end of your body。 So。



![](img/38df08beafe7dd347a4e0950e92c58da_26.png)

So we have a function， my funk， and in that function that we console log the Dom is landed。

 and then we're going to add event listener。 And this is a document event because this is Dom content loaded。

 not window， but Dom content。 document add event listener。 The event name is Dom content loaded。

 That's a hard coded string。 And I say， please call my function。 When all the files have been loaded。



![](img/38df08beafe7dd347a4e0950e92c58da_28.png)

And we're ready and and the user can see the page。 And so in this one it's really short it's just that。

That console， the， the the myF happens after the content is loaded and after all the。



![](img/38df08beafe7dd347a4e0950e92c58da_30.png)

Derivative things have been loaded， et cetera， et cetera， et cea。

