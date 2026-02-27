# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p22 -22-COMP6080 - Javascript 🐻 Ecosystem.zh_en -BV17RXGYuEaM_p22-

Hi everyone my name is Hayden and today we're going to be talking about the JavaScript ecosystem this is a fun little lecture I think because it really takes something that you see as very one dimensionional which is probably JavaScript you see it as a language that you write code and you run and really helps break it out into its kind of different。

😊，Aspects in terms of。You know what different versions of the language are there。

 how are they used differently， what even is a language， because JavaScript。

 unlike most other things that you've dealt with， is so multilayed。

The fundamentals are used in a range of different applications。

 which means that there are things you can can't do and understanding this nuance is extremely important。

 I think， to getting your head around this whole crazy world that's so full of JavaScript So you know the first question。

 what even is JavaScriptscript Well it's a programming language you probably figured that much out by now。

 is it what Google Chrome has Well。We've kind of shown that you can run JavaScript in a web browser。

 so I guess is a web browser a compiler？Is it a like is it an interpreter like what even is that what is no JS and you know we run that on the command line in the previous lecture with the syntax introduction does that understand JavaScriptscript does that mean that the web browser is。

Running No JS， does that mean that no JS is like a web browser on the terminal like these are the interesting questions right I react JS different from JavaScriptscript we're going cover that in week 7 so don't worry about all that stuff now And then like what version am I even using because I've I've said in the previous lecture in newer versions of JavaScript you can do this。

So let's take a step back and really think about what's actually going on sometimes when it comes to just running JavaScript。

 right？

![](img/feb1c2ca99828bcc43307d6099b73f44_1.png)

When I have a simple piece of code and we've seen a simple piece of code like in the JavaScript syntax lecture right where we had a simple piece of code like this。

 This one was for the web browser， but similarly you know this one you could run on nodeJS。

 the JavaScript still the same what's actually going on here right Well we have our language definition。



![](img/feb1c2ca99828bcc43307d6099b73f44_3.png)

![](img/feb1c2ca99828bcc43307d6099b73f44_4.png)

This is this this kind of is actually let me start from the other side， we have our source code。

 right that's this stuff here。 that's what's written inside of text files。😊。



![](img/feb1c2ca99828bcc43307d6099b73f44_6.png)

It's a program that we write， it's just ASCI。It's just characters， right。

 These are all just ASII characters， great。The two questions。

 How does this turn into running stuff on computers。 And then why did we write this。

 So to answer that second question， Why do we write this， that comes back to the language definition。

 And a language is honestly just a set of rules that someone writes in a book。

 You don't need a compiler to have a language。 You could go and write your own programming language that couldn't actually run because a language is just a set of rules。

 You know， if savings this， you can do that， you can not do that。 If you don't like a language like。



![](img/feb1c2ca99828bcc43307d6099b73f44_8.png)

C， you could go and write a language called D and you could go and add a couple of features if you wanted to。

 and that could be your own language， you don't need a compiler。

 but that's like a language definition。Typically language definitions。

 there's like one of these things So like you know there's like the ja language。

 it's not really like a thing where different countries or different web browsers think ja is like different Everyone kind of agrees on what the language is and then those languages are kind of released in various versions So there's like an international community say for ja where they sit around and they say。

 okay this is what JavaScript is and we want to add this to JavaScript and then they all agree and then they're like this is the new version of JavaScript the language。

😊，What then happens separate will often， you know， theyre very closely coupled。

 but what happens like to think separately is that then people go and create compilers or interpreters that。

Take the source code that you wrote and you wrote it based off the language definition and they turn it into like runnable code and they do that by building a compiler or an interpreter。

 and you're pretty used to these right Python 3 node in the previous lecture GCC for C。

 these are all just programs that fundamentally take source code。AsI text。

And they follow the language rules and they produce that you know runnable code。

 so compilers are based on these language rules。Where this helps take us in our understanding。Right。

 that's just the summary of it。 where this helps take us in our understanding is now let's apply this to Javascript。

 So we understand source code。 There's going to be nothing we need to talk about there， right。

 source code is the dot Js files that we write。Like this one here。

The language definition is a bit more interesting， though。

We've just been referring to this as JavaScript at the moment。

 but more formally JavaScript is known as ECmascript。

 which is often shorter to ESS for ECma script ECmascript is the actual language that we use。

You know， if you were to Google right now， what is the difference between？



![](img/feb1c2ca99828bcc43307d6099b73f44_10.png)

Javascript and ECmascript。You would get something that's like there's you know there's not that much of a difference。

Dos。Emascript is the standard for scripting languages such as jascript， etc ce。 You know。

 Javavascript is a language based on Emascript。 And like this is kind of true right。

 Like jascript is is essentially an implementation of Escript， if you will。

 but like I don't want to get too much into the semantic partly because I'll get it wrong。

 but also because it doesn't really matter。 Javascript and Emascript think of them like the same thing for the purposes of introduction to the concepts。

 The reason that we're telling you about Emascript。

 though is because it's actually around a lot on the Internet。

 Youll actually see a lot of references to it。 So you need to understand that it's the same thing。

 Javascript or Emascript same thing first appeared in 1997。

 That's when we started to see jascript since then。



![](img/feb1c2ca99828bcc43307d6099b73f44_12.png)

There have been more and more releases of like new newer language definitions of JavaScript。

 ECscript。But for a long time， it was fairly similar。

The amount of updates have dramatically increased ever since Webs become a lot more popular。 In fact。

 some of the key ones are definitely E S 5 and E S 6。

 Youll actually see these terms thrown around a little bit。On articles and other things。

Like when you go look at， you know， when was JavaScript classes introduced。

 I mentioned before that classes。

![](img/feb1c2ca99828bcc43307d6099b73f44_14.png)

Were a new feature in JavaScript。 and like you can see here。

 what are classes in JavaScript classes were introduced in ECmascript 2015 ES6。



![](img/feb1c2ca99828bcc43307d6099b73f44_16.png)

Okay， so you see all these like different versions， right of JavaScript。So it's like ES5。

 ES6 were two big ones and then after that they started doing it by a year。

 so they called it Ema script 2016， 2017， etc， you can go and read this if you'd like to。



![](img/feb1c2ca99828bcc43307d6099b73f44_18.png)

You know， JavaScriptscript， all these things， where are we at ES10 but？



![](img/feb1c2ca99828bcc43307d6099b73f44_20.png)

To bring it all back。Ecmascript is the language we're writing。

it's what defines the language and there are different versions of that language。

And most of what we use user with JavaScript are all kind of oldish features。

 in fact in the last lecture pretty much nearly everything that I showed you was quite old feature of JavaScript except for classes。

So that's the language， okay， that's probably not too crazy。

Things get a little bit more complicated on the compiler or interpreter side of things。

And the reason for that is because。The compiler or interpreter。Is made up of。

An ECscript engine and a runtime environment。An ECmascript engine is the thing that actually understands the JavaScript right it can turn if statements into logic branches and interpret strings and casts and Booleans like it's kind of the fundamentals like Emascript is basically what the introduction to so the Emascript engine is essentially what the introduction to JavaScript was about runtime environments。

 though like a layer on top of that that takes this engine and allows you to run it in certain environments。

Sir。A web browser。Is a runtime environment。 No J S is a runtime environment。

 and they are both or can be built off the same Escript engine。

 So this starts to get into the subtlety between it。

 So if you think about the Web browser as a compiler or interpreter and no Js， the command line。

 remember， no J S is。This command line that we were doing stuff on in the previous lecture and the web browsers。

 the web browser， they are both two different runtime environments。And they use the exact same。 Well。

 I think in this case， they do， but they don't always have to。 They。

 they use a ECcmascript engine underneath。So runtime environments like the browser or O JS are built on top of these engines。

 which are engines that interpret the language and produce runable code。

 What these run engines don't have is what you would call an API or an input output layer。

 And what that means is that。When it comes to the web browser。

Web browsers have a bunch of stuff that allow you to interact with the Javascript。

 and no Js has a bunch of stuff that allows you to interact with it。 And they're both very different。

 There's some code that you can write in Nojs that you can't write on the browser。

 and we'll do a couple of of the examples of those。 So if we dig even deeper into this。

 and we start looking at some examples。 you can see there are these different ECmascript language versions。

 ES 2009 or ES5 ES6，2015 ES7， etc cea。 Then you have different Emascript engines。

 The most popular one is the Google V8 engine。 That's what Chrome is running off。

 That is what Nojs is running off。 And then you have the runtime environments。

 You know and different browsers are different runtime environments。

 So you can see here that Safari is actually like its own interpreter。

 different runtime environment built off Js called Nitro， which is a different ECmascript engine。

In reality， the engine is kind of all the same like it's not something that you have to be personally concerned about。

 you're often going to be more interested in the runtime environment and as you can see here each version of a runtime environment is built off a particular version of an ECmascript engine and each version of an ECmascript engine is built to a particular version of ECma。

So basically， a new version of ECma script comes out。

People who write these Escript engines go and update them to have newer features like classes and then people like you know who run NoJS and Chrome。

 they go and take those newer ones and integrate them in as well。

 but the language like these two things are quite tightly coupled together fundamentally。Now。

 the next two slides are just to compare Google and sorry。

 to talk about Google's V8 engine and then node JS and then the browser。

 So let's talk about the Escript engine。Google's V8 engine is an open source JavaScript execution engine。

's part of the Chromeium project， etc。😊，Essentially。

 it is a standalone system that can interpret Escript and it can be built into any kind of C plus plus application or a whole bunch of other things。

 It's very low level and its sole job is to pause， interpret and execute。

You know and compile JavaScript So if you look at the the structure of the Vt engine。

 it's quite literally something that passes interpret source code。Generates bikecode to run。

And kind of runs it。 You know， that's really it。 Like it's very low level。

 It's quite literally there to just take to do those， the hard yards of。You know。

 the adding and subtracting and function calls and function stack like when you think about all those things right。

 function calls， function stacks， if statements， conditions。

 like all of this is handled by the engine。😊，Where node Js， the runtime environment sits above it。

 And you can see on the diagram here that it's using V8 as part of it is it's a jascript runtime with an easy to use command line capability that's built on top of Chrome's V8 engine。

 So when I said before that a runtime environment has an API or an input output layer。

 You might have been thinking， I don't know what that means。 But think about it。

 It's the command line。 Like how did we interact with node Js before。

 we ran something on the command line。 You know， it's taking in these。



![](img/feb1c2ca99828bcc43307d6099b73f44_22.png)

These commands， it's actually running on the CLI。So that's where that IO is just kind of interesting and you can see that here is like you got your V8 engine and it's interacting with like our application like you know we're running some code it's got some binding all this other crazy stuff here it's like event loop event queue threads we're going talk more about what that is soon but essentially it's trying to demonstrate to you that。

😊，Some of the other features that you'll see and you'll see this in the node lecture are only actually could only work with node JS。

Like file system。For instance， which is very interesting。 And we'll talk about that in a sec。

 Let's jump between these two slides a little bit。 So the next part is Google Chrome， right。

 Google Chrome itself is a runtime environment。 It's much bigger though right Like a browser is a big thing。

 It's able to interpret and render HTML and CS S S。But ignoring all of this， right。

 So all the HTML CSS stuff that it renders has nothing to do with the V8 engine。

 And you can see here that a web browser takes an HTML。

And what it does is it's able to render a page， this is all the CSS pars you're in painting。

 this is all the rendering stuff that you've done in the previous lectures。

 but then separately to that it actually works with the V8 engine and some other stuff built into the browser to like do some more dynamic things。

😊，Right， and up until this point， you haven't really done anything with Javascript。

 So let me just show you two kind of quick。

![](img/feb1c2ca99828bcc43307d6099b73f44_24.png)

Taste of things with JavaScriptscript that'll solidify the point so as we saw in the previous lecture。

Um。We have。

![](img/feb1c2ca99828bcc43307d6099b73f44_26.png)

We have code like this that runs in both the No JS interpreter and inside the Google Chrome browser。

Now， after this lecture， the two lectures that you're going to go and watch doesn't have to be in this order or you're going to go and watch the browser introduction。

 the web browser introduction and the Javascript No JS and PMm introduction they are both the logical splits from this lecture to go and learn a little bit more about the runtime environments。

 So just to really reiterate the previous lecture with all the syntax was really learning about what's going on or what can you do with like a Escript engine。

And now it's like what are this these layers on top of it。 So when we ran this in the browser。

 it was just about running， you know， some basic stuff， really basic stuff。

 But here's an example on the web browser， let me just open up。



![](img/feb1c2ca99828bcc43307d6099b73f44_28.png)

You need to find where that Chroe window is。😔，Maybe I closed it。

Let me just find a file give you one second。So I have this file here from before， right？



![](img/feb1c2ca99828bcc43307d6099b73f44_30.png)

And that file was when we had this test at HTML。Now， with this test of HTML。

We were able to print some stuff to the console right like that three there。

 that's what we did before。 However， let me show you some if I do console log here。

 window dot in a width。This will print the width of the window。138 pixels。Right。

 that's 138 pixels between you know where my where my mouse is shaking here。

 If I meet the smaller it prints 93， if I refresh the page right so that ja's running now this window dot inner a width。

 this window object is something that is built on top。Of the ECmascript engine。 And， in fact。

 if you take that code here and you go and try and run it here。

 Watch what happens if I open up the terminal。 If I go node 0， it says window is not defined。

 So we're still writing jascript。 But this is， this is part of the。



![](img/feb1c2ca99828bcc43307d6099b73f44_32.png)

Layer both。That is important to distinguish。 You need to understand that you're writing the same language in two different environments。

 and there are different kind of Apis and nuances between those two environments。 Now。

 on the flip side， let me show you something that only no J S can do。 If I typed in no J S。



![](img/feb1c2ca99828bcc43307d6099b73f44_34.png)

呃。Right file。Right， how do I write files in node Gs， And they'll give you some code。

 I want to find one that's like。Gingna make a bit more sense。嗯。因而。There you go。

 let's go and copy and paste this， let's go to this window dot width。

So here it's like let data equals hello。So I w to print hello to a file programming dot T X T。

So I can like hash include or import this library called file system。 You。

 will'll talk about this more in the node lecture。 I can go and create some data called Hello。

 and then I can go and try and write。

![](img/feb1c2ca99828bcc43307d6099b73f44_36.png)

That data to this file。 then if I go and open the file。Noe 0。It doesn't print anything。

 but have a look， I've got a file now programming。txt， there's the file， so that worked。

That's something that node is able to do right and that it's an example of like node is set up to be able to use libraries and those libraries are able to write to the file system whereas browsers again are very different if I go and paste this in the browser like that。

😊。

![](img/feb1c2ca99828bcc43307d6099b73f44_38.png)

Com back here， I get an error， this error let me zoom in says requirequi is not defined。

 it's like what is that because require is an element of the runtime environment that no JS built on top of the ECma script engine。

That's that's what's going on here， They're two kind of different things now。

This is not to give you the impression that。No Jeess is this thing over here and the browsers over there and they're all kind of crazy different。

 Honestly， like it's all very similar。 There are just elements that are different。

 and there are also elements that are built into both。Notode and the browser that。

Are builtilt into the runtime environments， but give you the same behavior。

 An example of that's what we'll learn in week 4 about making network requests。

 So you can make a network request from the web browser and you can also make a network request from node。

 You can do it from both of those things。 And that doesn't mean just because you can do it in both that it's part of the Escript engine。

 It's actually part of the runtime environment。 And you can see that on the slides here。

 You'll see that。

![](img/feb1c2ca99828bcc43307d6099b73f44_40.png)

![](img/feb1c2ca99828bcc43307d6099b73f44_41.png)

In the browser they have their networking capabilities。

 not part of V8 and in OJS the networking capabilities are also not part of V8。

 but the intention is to give you like you know a bit more of a parity and experience Yeah that's about it again。



![](img/feb1c2ca99828bcc43307d6099b73f44_43.png)

Go you're going to go and learn more about this whole node Js kind of command line code thing with jascript by looking at the node intro node MPm intro lecture。

 We don't do a ton of this in this course。 Like honestly。

 this is like this we don't go too deep into because it's pretty straightforward to be honest。

 it's very similar to Python。 So you kind of get it。

 And then the browser intro lecture that at the moment at the time of this recording is in week3。

 it might change depending on when you're watching this recording。

 that's where you dig more into the browser stuff And you see more about what can the browser do And what is this do and various other things。

 Like how does jascript work that's unique to the browser based on that runtime environment。

 So anyway， hopefully they give some。Context bit of information about the landscape and thanks very much。



![](img/feb1c2ca99828bcc43307d6099b73f44_45.png)