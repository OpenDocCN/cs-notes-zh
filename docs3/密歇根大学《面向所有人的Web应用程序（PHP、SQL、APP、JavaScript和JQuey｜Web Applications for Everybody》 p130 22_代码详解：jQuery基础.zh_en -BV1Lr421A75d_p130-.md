# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p130 22_代码详解：jQuery基础.zh_en -BV1Lr421A75d_p130-

Hello and welcome to our lecture on JQuery APIs and JSON we're going to roll a whole bunch of stuff into this lecture I'm not going to talk long time but a long time about each thing so some of things you may have to look at twice because it's kind of compressed and you don't want to want to miss anything because they build from kind of tiny to big really fast。

So。We talked about JavaScript， talked about the document object model and how they're very incompatible in terms of their shapes and so there was a bunch of libraries that came out and you know we had this thing like get ID get get element by ID that I kind of characterized as old school JavaScript。

 it was the old way we did portable stuff but。JQury is the thing that really has solved the mess that is the browser incompatibility now it turns out that there was lots and lots of libraries that were being developed at the same time that were trying to become like the low levelve utilities for JavaScript and JQury was the one that kind of one in this space。

And the reason that many people think that it won is because it had the best documentation and it still has outstanding documentation。

 There's a lot of jascript libraries that were there and the people who wrote them could use them。

 but JQury was this thing that like anybody could use it was well enough to document it in the pattern to the point where I'm not going to put a lot of jquery slides in is that they also show you just little snippets of code that you cut and paste and then adapt and make work and so in general。

 if you need a way to animate the opening of a window with JQuery。

 you go into Google and you type animate the opening of a window with JQury and you will find。

Often on the JQury site， a little five line snippet of code that'll give you the starting point and then you'll adapt。



![](img/082512d7ca5cd7aa522f518f6c6ca68f_1.png)

So I'm not going to talk too much about that。So this is sort of some very simple jQury so what we do here is we are going to in our head document。

 sometimes folks prefer to put this down near the end of the body。

 but I'll just sort of use the style of putting in the head and you go down load a version of the JQu library and we're going to pull this library in and what it does is it jacks itself into lots of the document object model and then makes it so that this variable dollar sign。

Dollar sign ends up being a function name JQury takes over， they just picked it。

 Now you can actually tell Jqueery to pick a different one。

 but dollar sign is the one that JQury kind of picked。

And so dollar sign is a function call and document is a parameter to that function。

And it returns an object， a JavaScript object that has many methods。

 dot ready is one of those methods， so that the Jquery syntax takes a little getting used to because this is like a function call and then this is a method within that function that happens to be a function call that goes all the way to here。

And so we tend to connect these things together and we're also seeing the use in here of first class function。

 so the parameter the first parameter to the Jqueery ready method is this function。

 it's actually code Now at a high level what we're saying here。

I we are saying when the document is ready。When it's fully loaded and all the images are loaded at that moment。

 please run some of our code and we wrote this code and we have a function and it's got two lines and it ones an alert and one says in the console log it says hello Jquery。

 and this is really common because often what you want to do is after the page is loaded you want to sort of jack in various places and add interactive elements to pieces of the page using jquery and then having jQury respond to the interactive things in that page and we'll build stuff that looks like that。

 So let's go ahead and run this， by the way， you can download the code here for this set of examples on PhPenttro co s code jquery zip。



![](img/082512d7ca5cd7aa522f518f6c6ca68f_3.png)

I've got that all downloaded。And JQu 01。Oops， sorryta。Clear that so I can click。JQuery01。And。

Hello dophP， that was the code I just showed you。Let me turn on developer console while I'm doing this。

So I got the developer console， I'm going to watch the console and let's say hello dophP。

 So what happens is this page will load。It'll run the JavaScript， it loads the JQury Library out。

 let's start with the network view of this， I'll hit this page hello。phP。

And you'll see that my PhP request response happened， and then in that it said， oh。

 go load some more JavaScript。And then in that JavaScript， it executed JavaScript and said。

 when the document is finished loading， call my function， and in that function， it called an alert。

That's my alert。 So this function happens at the end of page loading。

 Turns out this is important because it takes a while for the browser to get the page all put together。

 And if you're can to write JavaScriptscript， it's going to start looking at pieces of the pages。

 it's useful。 So the first thing you kind of learn in Jquery is how to trigger things that happen after the page is loaded and that's what this ready method does。

And if I look at the console， you see that there's a console message as well， and if I hit refresh。

 I'll clear this and I hit refresh you will see you know Out comes the alert and the alert happens first。

 but we know that the page is finished loading。

![](img/082512d7ca5cd7aa522f518f6c6ca68f_5.png)

And then the console message comes out and so that's how it was in the code， it did an alert console。

 but this is basically saying wait until all the document is loaded。

 so it goes all that and it loads all the subsidiary pieces etc ce， etc cea。

 so document ready is very， very very intelligent so again we use this to jack in and we'll see some things here。

So another thing we can do， for example， is jack in to the， I keep saying Jack in。

 it's like register an event is what really is going on。And the dollar sign here is a function。

 it has a parameter of window which returns an object so the function dollar Pass in window get back JQury object has a method of dot resize and what we're saying here is we would like to register a resize event and we would like this code right here。

This code right here。From here。To hear， to be called whenever the screen is resized。

Whenever the window is resized， the window is the part of the browser that's on the screen。

OkayAnd so at while a page is loading， we're saying， connect us up so that as resizes happen。

 our code is called and there's lots and lots of things like that。



![](img/082512d7ca5cd7aa522f518f6c6ca68f_7.png)

So let's take a look at that one。Ohm sorry， got to turn that back。So the resize runs。

And at this point， we have just registered。A bit of code that we want to run on the resize event。

Okay， now the way resize happens。Got to move this little guy。And I should resize that all along。Okay。

 so this the resize event is as I move this window and make it smaller and larger and you can see my code is being called over and over and over。

 let me just clear this。And now when I resize this。My code is being called because I told JQuery。

  please call me every time the screen resizes。Sometimes it does it while you're dragging on the resize and sometimes it does it when you let go the resize。

 but eventually my code will be informed that the page has been resized。

 And so I do I did that with this。

![](img/082512d7ca5cd7aa522f518f6c6ca68f_9.png)

Window dot resize function that says， hey， Jquery。Call me。

 registerister this bit of code to be called when the resize happens， When the windows resize。

 call me。 Now， I wouldn't normally just print this stuff out。

 I might do something like resize something or show or hide something。

 Who knows what I want to do in this code。 It just shows another pattern of。

Jacking into a different event than the dot ready， which is the ready event。

 which is called when the page is fully loaded。Okay。Here is another bit of JQu。

 and this is a pattern called theQu do。And so I'm going to have this code toggle dot PhP。

And I've got a paragraph。The paragraph goes from here to here。

 and I've got this spinner inside the paragraph。And I've got it set up。

To be hidden when the page first shows up。But I've got an ID tag on the paragraph and an ID tag on the spinner。

And so then what I do is I make an A tag。So that when I hit the toggle。

 it runs this ja and this jascript is jQury。 it's a dollar， and now I pass in a string string。

 which is pound sign spinner， and that means ID tag name spinner go find the ID tag name spinner returns an object and then I call the toggle method in that ID So that flips the display none off and on so I can click this toggle button we'll see me do this in a second as many times as I like and then that will hide and show the spinner later we'll hide and show the spinner for a more useful purpose。

Here's another one here is dollar dollar go find， I have another little tag called red。

 which says go find the paragraph tag， which is this whole tag right here。And。

Call the methods CSS and change the background color to red of the paragraph。

And when I click on green， it says go find the paragraph call the CSS method。

 change the background color to green。And so these are queries that look up a piece。

So this is like a query， Do Per says grab the tag。With an idea pair， so that's what that does。

 it's a lookup and then you call a method on the tag basically you get back a jQu object which represents the tag。



![](img/082512d7ca5cd7aa522f518f6c6ca68f_11.png)

Okay， so let's play with this code。Let's play with this code。So if I say toggle。Well。

 if you do a view source， let me just do a view source here。If you use ViewSo。

 you see my paragraph from here to here。You see my spinner， which has an ID of spinner。

 and it's currently not shown because display is none。So when I hit toggle， it's going to say。

 go find that， that's was that a span？No， it's just an image tag， but it's okay。

 the image tag is hidden so as if it's not there。When I say toggle。

 go find that image tag with an ID of spinner and toggle itss visibility on off。

So I just toggle it on and I can toggle it off， toggle it on。

 I'm not changing the HTML at this point， I'm changing the CSS associated with the tag and specifically this display value of the CSS。

And if you recall， I've got this。You know when I click red， I'm going to go grab the paragraph。

 which is all of this actually， and I'm want to set its background color to red or green。

 toggly back and forth red。Green， red， green， red， green。

 so none of this is a request response cycle， and none of this is really changing the document object model。

 we will do other things that will actually add the add tags and remove tags。

 but for now I'm just changing the CSS on tags using JQury commands。



![](img/082512d7ca5cd7aa522f518f6c6ca68f_13.png)

And again， I'm just giving you the simplest of stuff。 There are literally， you know， many。

 many things you can call here。 you toggle in CSsS or just two of many things that you can do。

 You can animate， you can do this。 You can set transparency。 Who knows what you can do。

 Gotta go look at geographic query documentation。 This is the notion of grabbing a bit of。

The HTML Dom and doing something to it。Query do syntax in JQury。And the rest of it。

 just go look at the JQury documentation， there's tons of it。



![](img/082512d7ca5cd7aa522f518f6c6ca68f_15.png)

🎼Yeah。🎼う。