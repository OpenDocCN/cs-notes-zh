# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p129 21_jQuery基础.zh_en -BV1Lr421A75d_p129-

![](img/72c7df03f88a5d0caa9944627b34fcd1_0.png)

![](img/72c7df03f88a5d0caa9944627b34fcd1_1.png)

So we've learned JavaScript。 We've learned about the document object model。

 We've learned how flawed the document object model is。

And we learned JavaScript object oriented programming。To some degree。

 all that is so that we can use Jquery because Jquery makes our life really simple。

 So if we place all this in the grand scheme of things， right？ So we get some HTML。



![](img/72c7df03f88a5d0caa9944627b34fcd1_3.png)

We parse the response some of it goes into the dom and some of it actually is JavaScript。What Jquery。

 And so jascript talks to the Dom。 and we've shown all that stuff。 What JQury is is a library。

 a clientside library that makes javascript easier to use。

 So everything that we're going to do in jquery， which is manipulate the dom and eventually going to talk back and forth to the server is just easier in jquery。

 You don't worry about browser portability etc cetera， et cea， et cetera， et cetera。

 So jquery is just like it makes the things that we could do if we really wanted to do it the hard way。

 we could do it。 but nobody wants to do it the hard way anymore。 So everybody uses jquery。

 So away we go。 So again， jquery is all in the browser And again。

 you'll notice that most of the files and all this are all these sample code are just HM files。

 they're not PhP code because they're not really running anything in the server。

 we just have a static file in the server， which we return that includes javascript。

 And so all the coding that we're doing is coding that's running in the context of the browser。



![](img/72c7df03f88a5d0caa9944627b34fcd1_5.png)

![](img/72c7df03f88a5d0caa9944627b34fcd1_6.png)

So that's sort of where we're at right now。 and literally for the rest of this course and in even in other courses。

 we're gonna the tendency is going to kind of focus in this direction。

 We're going to do more and more cool stuff in the browser and less and less in the server。

 We started out by doing everything in the server。 We certainly still have databases to deal with。

 but we kind of move toward the browser and web applications in general are doing more and more their interactivity in the browser because it's a better user experience。



![](img/72c7df03f88a5d0caa9944627b34fcd1_8.png)

You could argue you know， do you want to do it all in the browser， that's a different argument。

 but certainly there is no argument that a lot of the stuff is becoming interactive in the browser because it's so dynamic and it works more like a desktop application。

So by now， or if you haven't， please watch the video of John Russig。

 I give you these interviews because I want you to understand the mentality of what produced this。

 right， Jaquery is a piece of code。 Yes， but it's also an expression of a personality in John Russig is a person that created this。

 And so it's an expression of who he is。 So John Russig is a really smart computer scientists in 2005。

 he was just tired of building interactive web applications that use jascript and he was tired of doing nonportable stuff。

 and he also saw the elegance of jascript itself。 how jascript's object orient pattern work。

 stuff I just talked about in the last lecture。 He's like， well。

 this jascript is not a crappy language。 It's actually an impressive language。

 And so as a computer scientist is a young undergrad computer scientist at RPpi。

 I think Rinsseer Polytechnic in upstate New York。 He's like this is kind of a neat computer science place to do kind of respectable work。

 is。

![](img/72c7df03f88a5d0caa9944627b34fcd1_10.png)

Something it is not just crap work if you go and listen to the Brendan Ike talking about JavaScriptscript。

 he'll say， oh， JavaScriptscript originally was thought of as the crappy language and it sort of does silly things and puts on pop ups and annoys you and how scrolling and whatever。

But in this 2005，2006，2007 timeframe， JavaScript is sort of coming in the browser was coming into its own as a respectable place that talented computer scientists would want to work and certainly sitting here 10 years after that。

 we see things like Angular and react and all these things where JavaScript is really the focus。

 and then JavaScriptscript is taking over the server as well with things like No do Js。So。

John Ressig was like what are the kind of things we have to do in the browser all the time？ Well。

 one is you got to go find stuff in the dom and do stuff to that。

 like change its color or hide it or show it or whatever。

 And the other thing is is that there's events。 And that's that's the events that we've looked at so far like oncl equals or on change equals。

 those kind of events and jacking into those events。

Was the simple things like clicking that worked all pretty well， but things like。

Knowing when the document fully loaded。And all the images were done that turned out to be very different in every browser。

 And so， so Jquery standardized that as well about knowing when the document is loaded enough so that you can run jascript to start playing with a dom。

 You want the dom to be complete。 You don't want jascript to be looking for things that aren't quite there yet。



![](img/72c7df03f88a5d0caa9944627b34fcd1_12.png)

So it came out in 2006， which is about 10 years after JavaScript was created， John。

 as of this moment works at Khan Academy and some of you who have high school students may have taken some of John Razig inspired computer science classes on Khan Academy and he is like me。

 a big fan of everybody learning to code and he like me is also a big fan of moving coding down into high school。

 you know eighth， ninth，10th grades in high school。

 and so he's a great guy and it's a fun interview so I encourage you to take a look at John Raig。



![](img/72c7df03f88a5d0caa9944627b34fcd1_14.png)

This lecture is not going to sort of give you speeds and feeds for JQury。

 One of the things that John talks about is there were other competitors to JayQury in 2005，2006。

 like prototype and mood tools。 and they were like religions。

 And JayQury was just one of the religions。 But Jay Kery in a very short period of time one。

 And John credits。 And I think I agree with him that he credits the reason that JQury  won in 0506。

 was that it had better documentation， and he put a lot of time into documenting what he did。

 not just writing great code and making it so he could use it， but making it so others could use it。



![](img/72c7df03f88a5d0caa9944627b34fcd1_16.png)

So literally， you'll say things like。How do I animate an image to appear and slide in from left to right with JQury。

 You type that in and then bang you're on stack overflow or you're on a Jquery page。

 and the jquery documentation is superb。 It's it's both thorough。

 but it also gives you these little tiny snippets of like five lines that doing pretty much what you want to do。

 So you just ask the question into your search engine。 You either go to stack overflower Jquery。

 You copy and paste five lines。 You stick it in your thing。 It starts working and。

 then you change two of them to do exactly。 So I'm really going to just spend this lecture talking about the real basic things that jquery does。

 knowing that you can this out on your own。

![](img/72c7df03f88a5d0caa9944627b34fcd1_18.png)

![](img/72c7df03f88a5d0caa9944627b34fcd1_19.png)

![](img/72c7df03f88a5d0caa9944627b34fcd1_20.png)

So here is the first kind of JQury thing Okay， so the first jQury thing that we got to do is we got to load the JQury library。

And that's just a。 so you have to have this file somewhere。

 You can actually load it off of the Internet。 Google has hosted copies of it。

 There are things called Cdn content data networks， which are unlimited， superfa bandwidth things。

 So you don't even have to load it off of your server if you don't want to。

 So if you go look at the jQury documentation。 They will give you a couple of versions of how to pull JQury in to your application and there's different versions of jquery。

 and there's plugins。 But for now we're just going start with a copy of Jquery somewhere。

 And we'll stick it right on in this， I'm just giving it to you in the file。

 So that's got a version of Jquery in the file。 So we just load it。 Now including stuff like this。

 it probably shouldn't like put it to any output or anything like that。

 It just as function function function function， or maybe some classes that are being created。

 but no objects and no output。 And so that's what that does。 It just defines Jquery。 Now。

 the interesting thing about Jquery is the biggest thing that it does。

 is it defines a global object with the name of dollar sign。Now。

 when you look at JQury and you look at how the code of jQurry looks like。

 you see this dollar sign parentheesis， dollar sign parenthesesis。

 And most people look at that and say， oh， that's just like a jascript magicism。 It's not。



![](img/72c7df03f88a5d0caa9944627b34fcd1_22.png)

It's actually a function， an object。Named dollar sign。 If you go all the way back in JavaScript。

 you'll say， oh， variable names can be letters。It can start with upper and lowercase letters or underscores or dollar signs。

 And if you recall， what I said was。Dollar sign is tacky because it reminds us of pearl and bash and all these other scripting languages。

 And so for the first 10 years of jascript， no one used anything with a dollar sign。

 And so along comes John Resig and he goes like， what should I name my object。Whoa。

 no one uses dollar sign。 Turn out about that time people were figuring it out and there was a couple other things that use dollar sign。



![](img/72c7df03f88a5d0caa9944627b34fcd1_24.png)

But take where use dollar sign and so it looks like language syntaxt， but it's not。

 that's just the name of an object。 and now we're calling that object with parentheses。

 and so we're passing in a parameter。Okay， and so that helps us understand。



![](img/72c7df03f88a5d0caa9944627b34fcd1_26.png)

And I'll tell you what when I first looked at JakeQury， I was like。

 it's just a bunch of curly braces， semicollons and parentheses that just like someone threw a bunch of punctuation。

 there was a car accident and a box full of punctuation just fell all over the place。

 and you'd picked it up。 And that's what JakeQury looks like。But when you write this stuff。

 you've got to have it work， so let's understand really quickly what's going on here。



![](img/72c7df03f88a5d0caa9944627b34fcd1_28.png)

Dollar is the name of an object。 We're calling the object with a parameter。

And the parameter is document document is the JavaScript concept that is the document object model that's predefined in all the JavaScript that runs in a browser。

 That's sopassing document in。 That's one of the predefined values of predefined objects that's in the browser already。

And how we're doing is this is returning code。 Remember， first class functions。And。

We're going to within that call the Read method。That's from here to here is the ready method。

The ready method has one parameter， ready。We could call it X。But that's not what we're calling。

 We're still passing in one parameter， but we're passing in is code。Because the function。

In JavaScript， because of first class functions， returns code。So this bit right here。

Is in effect a constant？That's being passed into ready。

And what we're supposed to pass into Read is code that we want to have executed。

 So this is delayed execution。 This code doesn't execute until Jquerry decides that the document is fully loaded and ready to be viewed。

 And so it will call our code when and only when This is registering an event。

 The event is when the document ready。

![](img/72c7df03f88a5d0caa9944627b34fcd1_30.png)

And so we register the event， and then we have to put the code in to run。 So we're passing。

 So at this point， when the code runs， Jakequerry simply retains this code and remembers it。



![](img/72c7df03f88a5d0caa9944627b34fcd1_32.png)

It runs it later some time after this body is done and the things have loaded， et cetera， et cetera。

 et cetera。 And then it runs our coat。 So this is delayed。Execution。This is an event。

That's another way for it to say the same thing， delayed execution， event， it's also asynchronous。



![](img/72c7df03f88a5d0caa9944627b34fcd1_34.png)

You don't know exactly when the code is going to run。

 Jaquery knows the moment that your code is supposed to run。

 You have handed it the code that you want to run when this thing happens。



![](img/72c7df03f88a5d0caa9944627b34fcd1_36.png)

And its first class functions。If you understand it， it's absolutely gorgeous。

 And you can kind of see why early sort of folks like Rssig who are building Jake where you're like。

 oh， wait a sec。

![](img/72c7df03f88a5d0caa9944627b34fcd1_38.png)

This is a gorgeous language。 and first class functions make this different than any other programming language that you've experienced。

 Like I said earlier， small talk and other and Lisp and others had this concept。

 But Javascript is like the first language that first class functions are like right here， okay， so。

😊。

![](img/72c7df03f88a5d0caa9944627b34fcd1_40.png)

Now， let me clear the screen and let me explain to you what this does。So that's the syntax。

 But after a while you're going to be cutting and pasting。 you'll be like， oh， cut paste。

 cut pasteing you'll stop thinking about it。 And all you'll think about is this stuff right here。

 So at some level， this becomes a magic idiom that we just do over and over and over again。 Okay。

 And so we're loading the jQury library。This line right here is like an idiom that says when the document is ready。

 run this code。 This is also an idiom that sort of。Completes the print， the season。

 semi Colons and all that stuff。So what we're telling JakeQu is when after the body is done and when other stuff is finished。

 come and run our code okay that's what we're asking。 And so when it happens。

 we're going to run an alert， we're going to do a console log Okay and that's just so we can see what's going on and if you run this you'll see that happen Okay so if you run it you'll see that happen。



![](img/72c7df03f88a5d0caa9944627b34fcd1_42.png)

So。The next concept， again， one of the two things that JQury does is sets up events so the first thing we saw is setting up an event。



![](img/72c7df03f88a5d0caa9944627b34fcd1_44.png)

In this one， we are going to ask to be called whenever the window is resized。 So again。

 we just load the JQuy Library。 and this this time we pass the window。

Let me see if I can draw this picture this。So the window is what you're seeing。

 and there is the document object model is all the stuff。 And so if you have a scroll bar。

 the window is only seeing some of the document object model。 So you've scrolled up or down。

 maybe you're seeing this part， maybe you're seeing this part down here。

 so not all the document object model is showing in the window at any given time。

 So the window is the part you can see window。Dm document object model。 And so， for example。

This window has width， and height。The document object model does not have width and height because the window is what you're seeing。

 Docu object model is what is the entire web page that's behind it。

Part of the document object model is what is being shown in the window， but it's not the thing。

 So there is no width or height for the document。 So youd have to say， hey。

 how wide of a window am I in right now。 And so we pass window in to Jquery。

 and we have a different set of events that we can jack into so we say， okay。

 I would like you to call me whenever this window is resized and what resizing means as you grab the corner of this and made it bigger or smaller。

 right， You made this bigger or smaller。 When the window gets resized， call my code。

 So this is sort of an idiomatic way of saying， I have a couple lines of code that I want to run every single time the window gets resized。

Okay， and so the code that we're going to run every time the window gets resized is this code。

 We're going to console dial， say it's been resized and you run So the width Do window dot width。

 That's a method within Jquerry's window object that tells you how wide it is。

 So now we're looking at that window。 and we're seeing the width。 And we're seeing the height。 Now。

 it turns out。 And again， document object models over here。Window， dom， not nom， right。

 It shows a subset of this， right， So a subset of this is actually what you're seeing。

But if you move this， it's going to call this code。 You change this size is' gonna call this code。

 What it's also going do is this turns out to be hard to calculate。

 go Google on stack overflow and say how do I find the windows width without using jque。

 and they'll give you like this much code。 and they'll tell you， well。

 what browsers do you want it to work on you want it to work on i。e 7， blah， bh， bla， bla， bla。

 Here here's what you write in i。e 7。 Here's what you're writing in blah， b bh。 And you're like， no。

 don't do it。 use jquery window dot with。 It tells you exactly the number of pixels。

 And it tells you window dot height tells you the exact number of pixels。 Now。

 generally not going print this out， you might have to resize some of the stuff that you've got in the dom or something so that if you make it small。

 you want to like hide a column or something like that。

 you're doing something like that in this code。 But it's another example of jacking into the event structure of the document object model in the window to say call me back right。

 This basically says call me back when they resize the window and run this code when they resize the window。



![](img/72c7df03f88a5d0caa9944627b34fcd1_46.png)

![](img/72c7df03f88a5d0caa9944627b34fcd1_47.png)

And these top this part and this part are kind of just like idiomatic things that you cut and paste from one thing to another。

 even though you should know what the syntax really means。



![](img/72c7df03f88a5d0caa9944627b34fcd1_49.png)

Okay， the other thing you can do other than jacking into events is you can change the document object model。

 So if you go back a couple of lectures where I use get element by Id and we change the document object model。

 this is kind of doing that same thing。

![](img/72c7df03f88a5d0caa9944627b34fcd1_51.png)

So this is an example of， you know， those little animated spinners that are spinning around that you see all the time it's kind of you're indicating you're waiting what we're going to show you is how to hide and show those things right and so what we do is we put out a image tag。

Right here and we're going to give an ID。 Remember ID equals， there's only one per document。

 and we're going to have spinner dot G。 we're going to height a width。

And then we're say displayed done。 And that means by default on this page。

 that spinner is there on the page， but it's hidden。And then we're going to have a little toggle。

And we're going to have an event， an on click。There's a way to register events in Jquery that I didn't show you。

 This is an old school on click， but it's okay because whenever we click on toggle。

 this jascript is going to run So it's going to be jQury。 And so we say dollar parentheesis。

 and instead of sending the whole document or the whole window。

 we say quote pound sign spinner and that says， go look up the I spinner and that grabs this whole tag。

And then this is a jQu function called toggle。 What toggle does is it looks at display none。

 It checks it。 If it's not currently display， it changes it。 And then if it is displayed。

 it sets a display none。 So it's toggling。 If you were to watch this in your inspect element。

 you'd notice that this is changing。 And you don't have to remember。

 you'dt have to write a variable to figure it out， you're just saying， like。

 show it or don't show it。 There's a dot show and a dot hide as well。And dot hide。

 if you want to hide it and show it， you can do that。 So this is a way to grab a chunk of the dom。

 and then you have certain methods that you can execute on that based on you have to go read the jQu documentation to see them all。

So that's hiding and showing an element。 We can also grab something and change its color。

 So here we'll have a little button called red。And we're going to grab this paragraph because we're going to say dollar pound sign paragraph that says。

 give me this paragraph。Now， this has no C SS on it。 No no other Css。

 And then once we grab that paragraph， dollar pound paragraph dot Css。 This is a jQury method Css。

 And we pass in a Css variable background dash color。 And we set it to red。

 And so that means that whatever this paragraph is， is going to have a background color of red。

 Every time you click that button。 And similarly， if you click this green button。

 it's going to go grab that， set the background color to green。 So you go red， green， red， green。

 red， green in this little paragraph is going to pop back and forth as red and green。



![](img/72c7df03f88a5d0caa9944627b34fcd1_53.png)

And so that's basically how JakeQury works to grab things and operate on them and again。

 that's just very much the beginning。So the next JQury example we're going to show is how you actually can look at forms and auto submitmit forms and talk to the server in JQury。



![](img/72c7df03f88a5d0caa9944627b34fcd1_55.png)