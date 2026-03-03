# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p13 13_03_03_浏览器中的JavaScript.zh_en -BV1rNibBuEwD_p13-

So now we're going to talk about how you use JavaScript in a browser and as I said before。

 this is just only one of the possible ways that you might use Java。

 but this is pretty much what we'd call vanilla Java or basic Java or Java without view or Java without JQuery or Java without node。

 this was the original Java purpose， right it was to be in the browser augment HTML。



![](img/ea98d59cb2a7caf22889410bfc6b296d_1.png)

So here we have a happy little bit of HTML。 we got some HTML。 you got a body。

 you got a paragraph tag and we got this script tag。

 So this script tag says we're moving out of HTML is syntax and we are then writing some ja code and we are talking to the document document。

 the dom is in a sense that part of your browser that's like the pixels that you're seeing so this jascript code can write to what you're seeing on the screen by going through this this variable called document document dot right writes onto the screen And so if you take a look at this code。

 it's coming down out comes the title that comes the body the paragraph comes out。

 then it drops in a JavaScriptscript and then this little string gets written out and it goes back in the No script tag is in case there's no JavaScript which is really rare these days and then the paragraph comes out。

 So the point is is that this has created a three line web。



![](img/ea98d59cb2a7caf22889410bfc6b296d_3.png)

The and third line comes from HTML and the second line comes from JavaScript。

 not that this is a particularly useful example。It just points out that JavaScript has access to the screen when it's running inside of a web page。

 that's powerful and we're going to drive a truck through all that。

So whenever I learn a new programming language， the first thing I got to do is print a debug statement。

And the debug statement is called alertt。And you say alert， you put a string in it and it stops。

 it stops the program。 and you have to press okay。 then it continues on。 So that way I'm like。

 did that code run or not， And I just put a little alert hello world in there and then poof up it goes and then just pops up a little dialogue and you press okay。

 And it continues。 So that's really quite nice。 And so here's a little example of that。



![](img/ea98d59cb2a7caf22889410bfc6b296d_5.png)

Where we're cruising along， the paragraph is written out。

And one of the things that you'll notice is that this alert box actually stops the jascript。

 so we switch into JavaScriptscript。 The browser is still parsing the page。

 and you'll see sometimes little spinner is still spinning So it stops。

 It puts up the alert dialog box Here I am and waits until you press okay and in a sense。

 your browser is paused at that point because literally it doesn't know what you're going to do and this JavaScriptscript has every right to change every bit of this page because the JavaScript is in the page。

Using a document。So it pauses until you press OK and then it picks back up and then it will write hellello world and the second paragraph will come。

 but alert， you just stick it in your JavaScript and whatever's happening。

 bangang it stops right there and everything stops。

And so it's a pretty cool thing and so you can't use it too much。

 you can't use it in a loop and if you do it too many times your browser like。

 whyhy is this page throwing up so many alert boxes？



![](img/ea98d59cb2a7caf22889410bfc6b296d_7.png)

In a pinch， it's the simplest thing。So there's three ways to get JavaScript into your web page。

 one is in lineing the document and that's what I just showed you with a script slash script。

It can be we've done and we've done this before， it's part of an event at an HTML tag。

 I'll show you that， or you can put the JavaScript in its own little file， usually ending in dot JS。

So here's the second one， this is the one。

![](img/ea98d59cb2a7caf22889410bfc6b296d_9.png)

Where we're putting in an on clickick method。 And so we've been doing this， right。

 We've been doing on clickick methods where we'll have an Hf and then on click and then say something。

 And in this one， this part here in the middle， that is just jascript。

 And that's why has semies to end each line。 Whitespace doesn't matter。 This isn't Python。

 Don't need new lines， et cetera。So when we click on this click Me button。

 that is going to start running this code Now the page is already fully fully rendered and the clickme button is waiting to be clicked and on click that's when a click happens event driven programming。

 then it runs the alert pauses。Better change the color there。It runs the alert。How come。

 I can't get it to be yellow。

![](img/ea98d59cb2a7caf22889410bfc6b296d_11.png)

There's yellow。Clear it。

![](img/ea98d59cb2a7caf22889410bfc6b296d_13.png)

Go back up。And be yellow。 Thank you for being yellow。 So you click on it。 It runs this jascript。

 which runs the alert， which pops the box up。 Then you press the O。

 and then it continues on this code。 Now， the return falls。

Is telling the anchor tag not to follow the link。

![](img/ea98d59cb2a7caf22889410bfc6b296d_15.png)

Right and so that basically says I the uncled method have processed this particular click and so that's what the return false does。

 so we are basically just have JavaScript in the middle of a tag that's triggered when an event happens。

 so event based programming。The other thing we can do is we can make this in a completely separate file。

 So we're going to have this file called script Js。

 Now it doesn't need a script tag because it knows that it's jascript。 that's just code。

 This happens to be one line that's got a document do right hellello world。

 And now we inbed it with a script tag in a slash script。 but now we just say source equal script。

 It pulls it in。 It loads and runs and parses that whole thing。



![](img/ea98d59cb2a7caf22889410bfc6b296d_17.png)

And as a side effect， it writes out， you know one paragraph hellello world in the second paragraph。

 and of course， usually this isn't doing work， usually this is defining a bunch of functions that we're going to use later and so usually this is script。

js is a function function function function， so we're kind of loading a library of functions that we're going to use later。

 but I just put this document right， so you can kind of see when it's happening as the document is loading。



![](img/ea98d59cb2a7caf22889410bfc6b296d_19.png)

So in any programming language we can make errors as a programmer， right， we can make syntax errors。

The problem is。When you're looking at a web page and then that web page。

 there's a JavaScript syntax error。They decided a long time ago not to bother the poor user with the javascript syntax error。

 because really， the person， unless you're writing it in the first place。

 the person looking at the screen of。You know Amazon dot co or or Dr Chuck。

 co if I got a syntax air in Dr Chuck。 co， why tell you that there's a syntax there So what it actually does is it just like。

Well， I be I guess I'll stop running the jobscript because it's got a problem。

 but I'm not going to tell the user， which means my page is broken and I don't even know that。

 So it stops。 And so syndax errors happen and it just stops the execution。

So let's take a look at a little example here。

![](img/ea98d59cb2a7caf22889410bfc6b296d_21.png)

A little example where we have two chunks of JavaScript， we come in， we got the first one。

 and this first one has a syntax error。Okay， and that means the alert's not going to work。 Now。

 what happens is， is it， in effect， ignores everything after that point。

 If it's executing through a script file， it might be defining a bunch of functions if it finds a syntax error。

 a third of the way through， the other two thirds don't matter because it is stop parsing that file until the end of the script tag。

 And then when it sees a new script tag hope springs eternal， and it starts parsing it again。

 And so that's why when this page runs。When this page runs， you see first paragraph， this goes。

 blows up， which means it skips down to here。 Then you see two paragraph come out。

 And then you see the alert second time。 you never see any of these alerts because that error is on the first line of the jascript。

 which。In validateates the rest of the jascript， But until another script tag。

 and sometimes what you're doing。Thesere like including one library and another library and another library and another library。

If you have a syntax say in that library that you're including。

 most of that library won't actually be activated， right。



![](img/ea98d59cb2a7caf22889410bfc6b296d_23.png)

But it doesn't mean if you have like five libraries that you're loading with five script tags just because the first library has a syntax there。

 it can still load the other four other four libraries， but it's just，It punts。

 There could be hundreds of lines of code here， and it all is for nughaught because it saw a syntax error and ignored the rest of it up to the end of that script tag。

Now， the end user can't see the error， so when you're doing software development。

 you' got to put in extra effort because when you're like writing code and hitting and refresh。

 writing code and hitting refresh well。Yeah， that's the user hitting the refresh in the browser。

 But if you're writing jascript， you want to see what's wrong。

 And so we have places that we have to look to see if there are actually JavaScriptscript errors in our code。

 And once we start developing JavaScript， I assure you that there will be errors in your code。

 There's always errors in my code。

![](img/ea98d59cb2a7caf22889410bfc6b296d_25.png)

And so all of these situations， whether it L browsers， Firefox， Chrome， Safari。

 they all have some kind of a web developer console that you unlock。 And then you can go。

 there's always one of these tabs that says console。

 a console is all the error messages that are coming up。

 And so if you made that same bit of code and you had the console turned on。

 you would see a happy little error that says syntax error on line3 of that file。 I mean。

 it would just run the O is the later in the file。 but it will tell us that。

 So you'll find that once you start developing jascript。



![](img/ea98d59cb2a7caf22889410bfc6b296d_27.png)

You're making a big mistake if you don't have this。

 this little developer console open almost all the time， at least to the to the javascript console。

 because that's how you debug your javascript。 It'll literally just like silently。 you're like。

 I changed something and nothing happened。 I changed something and nothing happened。 I'm going crazy。

 Well， look at the console。 You change something。 but there was a syntax there above it。

 And so it didn't matter what you said after that。 It really ignores everything after that。

 So that's why it's so important to have the debugger console doing all the time。Thankfully。

 all modern browsers have a good debugger console in the old days， Firefox was the only one then。

 a thing called Firebug， which was this console which had to install it and add it。

 and it's a person wrote it as an open source project and it got so popular that people just put it into the browsers rather than making you install it so it was pretty cool。



![](img/ea98d59cb2a7caf22889410bfc6b296d_29.png)

So back to debugging， there is a。Function called console dot log。

 And it allows you to log variables and strings and whatever。 And unlike the alert。

 it just shows up in that console So you can put it inside of a loop， you don't have to press okay。

 it doesn't stop anything， it's really more of a debug print， right？

 And so in this particular example。 You know， it just runs。 It doesn't stop。

 the alert stops everything。 And so I use the alert。 Like what is going on。

 But if I'm really debugging something like in a loop。 I'll use console log。 So it comes in。

 console log comes out， It says alert， I clicked on it。 So you don't see that。

 the second log comes out And away you go。 And so this， this is a better debugging mechanism。

 And if you look at systems that I've built when I have a really complex jascript。

 I will sometimes leave console log statements in it。 So if you use Sai。



![](img/ea98d59cb2a7caf22889410bfc6b296d_31.png)

![](img/ea98d59cb2a7caf22889410bfc6b296d_32.png)

![](img/ea98d59cb2a7caf22889410bfc6b296d_33.png)

And you're at a school that uses Saii and you do console log。

 you will see error messages in your production system that I left in there because of the parts of the code that were so the JavaScript was so tricky I' like I want to be able to talk to you if your stuff breaks and I want any developer to be able to pop this window open and get a clue as to why some of the JavaScript stuff is breaking because there's just so much complex JavaScript in it so I leave a few little debugging clues and if you go into the autograder you can watch this。



![](img/ea98d59cb2a7caf22889410bfc6b296d_35.png)

I just like debugging and it's sort of not all that costly， I don't put a ton of them in because。

Then it looks a little sloppy， but I do put a few console logs in。So。



![](img/ea98d59cb2a7caf22889410bfc6b296d_37.png)

So you can use a debugger。 It's a full featured debugger， you can view the source。 you can inspect。

 you probably by now have figured out to do how to inspect elements so you can look through the and what you're looking through there is the document object model。

 but they also have the full featured debugger where if you're looking in the source code you can go on to the line that you're interested in and click and then that will set a break point and but it doesn't but usually the code's already executed So you have to set the breakpoint。

 then you got to refresh the page and it remembers where you set the breakpoint and then it stops it and so you kind of set the break point and hit refresh it'll figure it out because by the time it's all done。



![](img/ea98d59cb2a7caf22889410bfc6b296d_39.png)

![](img/ea98d59cb2a7caf22889410bfc6b296d_40.png)

It can't go back in time， it's past that line， so you have to see the line， set the break point。

 refresh the page， then it knows to break point， catch the break point。

As it's going by rather than going back in time because it doesn't remember they can't run time backwards just forwards。

So that gives you a little sense of what it is like to do JavaScript in the browser and now we're going to just look at JavaScript as if it were a regular programming language and this applies whether it's in the browser in the server and view or whatever。

