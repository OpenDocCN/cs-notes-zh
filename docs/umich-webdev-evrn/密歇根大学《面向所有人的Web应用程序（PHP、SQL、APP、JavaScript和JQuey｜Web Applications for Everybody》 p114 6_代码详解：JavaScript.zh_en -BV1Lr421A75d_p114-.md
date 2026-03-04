# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p114 6_代码详解：JavaScript.zh_en -BV1Lr421A75d_p114-

So one of the first things I always like to do when I am programming is how to get a debug statement。

 okay and the alert function takes as a parameter， a single string and it prints it out。



![](img/682937fc9d942667d8beb22634565c69_1.png)

So here's a very simple bit of JavaScript。The browser sort of runs this， oops。

Tur the scribbler back on the browser kind of runs this and it stops and depending on your browser。

 it may actually stop when。In the middle， while the page is still displaying。

 so let's take a look at this particular one。Let me clear this and go and run this one。



![](img/682937fc9d942667d8beb22634565c69_3.png)

Here's the sample code。We'll run this。First one， we already saw that one。

You make this just a little bigger here。And so you see and you see this little thing is still spinning right over here it's still spinning and that's because it's sort of still processing the page and the alert has actually completely stopped the JavaScript so that the thing iss going to happen right after the alert won't happen until I press OK and then it finishes。



![](img/682937fc9d942667d8beb22634565c69_5.png)

So the alert stops。Right now and it's really stopping the interpretation of this page so alert is。

It doesn't just print out output， but it stops JavaScript processing。

 so it's a pretty strong form of debugging if that makes any sense。

 and so alerts just an executable statement。

![](img/682937fc9d942667d8beb22634565c69_7.png)

There are three ways that you can put JavaScript into a document。

 one is in line within the document using the script tag。

 you can also put it on things like on click methods on things like HRs， etc。

 or you can include a whole file we'll see all of these examples。

This is some code that we've sort of been playing with all along。

 but now it is time to sort of understand what's going on here。

 So this is an anchor tag that is this tag right here and we have an onclick method So this is within the anchor tag right and it says when someone clicks on this anchor tag I want to run this JavaScript right here So the bit in between double quotes is JavaScriptscript and JavaScriptscript can use single quotes or double quotes as strings so we tend to reserve the double quotes for HTML So uncl equals double quote something double quote that's HTML and then。

Quote high quote， single quotes in this case is some JavaScript and we're calling alert now returnturn false has to do with normally if you were to click on an Hf。

 it would actually follow that link okay。But if you say return false。

 it won't follow a link and it'll just run this code and not file the link。Okay。

 so let's take a look at that one。

![](img/682937fc9d942667d8beb22634565c69_9.png)

Oh。So if I click it's going to actually run the JavaScript rather than doing what it normally would do。

 and if you recall it would go to jSO1。htm， but it's not going to because we did the return falses。



![](img/682937fc9d942667d8beb22634565c69_11.png)

Okayang。So return false is the way。To indicate that we don't actually want to do what normally would have happened if the click happened。

 so you can do both oncl method and then let the tag do what it normally would do。

 or you can say I'm taking over and doing that。 So so this is just one form where we're putting ja right on a tag。

So here's another way to do it。And。And so。This when we show before where we just did a script tag and an Nscript tag and then had document right。

 you might see something like this in HTML5， we tend not to do this。

 but this is validation to make sure that the ja passes a strict HTML4 validation but that's less important as we're moving to HTML5 So we talked about this one and then the third way to do this is to actually use the same script tag and say I would like to load this file and then script。

js has to be a file that has some content in it， and in this case we just have one line of JavaScriptscript we don't have a script tag its just JavaScriptscript itself。

 It knows that it's jascript by the fact that we're inlining it and so that's as if we typed all that stuff here Now this is kind of a silly little example it actually just you moves that document right into the file。

 but that's another form of including JavaScript that you will commonly see。

So syntax errors and JavaScript are a little bit different。I mean we can make mistakes。

 it's a programming language， but the problem is is that most of the time you're using a JavaScript page that you did not write。

And you're just using you know Twitter and if there's a JavaScript error and a Twitter page。You。

 as the Twitter user， it doesn't do much good for you to be told that there's a jascript error because you can't fix it。

 synyntax error， missing semicolon， Who knows what it's going to be。 So the browsers tend to be very。

 very silent about any kind of a jascript error。 but the code dies。

 Sometimes there's a little red icon that shows up in the in the lower left hand corner。

 So here's just an example of a bit of bad jascript where。



![](img/682937fc9d942667d8beb22634565c69_13.png)

Where we're just going to have a double quote that starts and ends in a single quote。

 so that's a syntax error and what we will see is that this will run。

 it will die here so this code doesn't finish but then it actually gives up on that script block and then continues and you'll see that this this one will run later okay so let's go ahead and show this。



![](img/682937fc9d942667d8beb22634565c69_15.png)

In JSO5s。So it did not tell us anything about that first syntax error but it didn't run that second alert and then it actually finishes。

 okay？

![](img/682937fc9d942667d8beb22634565c69_17.png)

So like I said， the end user is really not supposed to see the error。

 but we as a developer need to look for errors。 And so as we're writing jascript。

 you instinctively something won't work， you'll make a change and it won't work and your brain's got to go like。

 oh wait， wait wait I made an error。 I've got to actually explicitly look for it。

 And so there are developer modes in all of these browsers。 I'll play with the Chrome one here。

 So let's take a look at how you turn on developer mode。 And sometimes。



![](img/682937fc9d942667d8beb22634565c69_19.png)

You have to enable this little message to just show up， but at the end of the day。

 I can like to view JavaScript。Console， and I'm gonna hit refresh and you will sort of see what's going on here。

 It runs， but it's I see the error and I can even click right here and I can see the exact place that the error happens。

 So increasingly these browsers all have nice debugger modes in them。

 and I've just popped up a debugger and it's got this little thing。 and I can look at the console。

 I can look at the code。And go back and forth。 And so this is。

make that a little bigger yeah so this is a useful thing and you as a developer。

 you'll tend to often just leave this sitting down here at the bottom when you're working on code all the time where it's like。

 you know I just leave this on all the time you kind of do it with console and you run it and you see something like oh wait wait wait wait and then you know how to go look for that error okay？

So that's very important because there's no good way to see these things unless you've got this console turned on sometimes your browser will say go look up JavaScript errors but it really wants to hide these from end users you as the developer。

 the website have to get this stuff right。

![](img/682937fc9d942667d8beb22634565c69_21.png)

So alert is kind of a blunt instrument in that it's。

It stops running the code and sometimes you got you have a loop or something。

 you want to put some debugging in it。 And so these debuggs have added a console log method and you can pass in a string and can you can console log all kinds of stuff and and so basically what you can do with a debugger turned on is you say you know console log and it'll come out in the log and so this same console log that we were seeing allows you to see things and it just runs。

 so that console do log is a very useful thing and it allows you to even inside of a loop or inside of an event or an onclick method to be logging stuff without stopping if you do an alert it stops but if you do a console log it just streams by in the debugger window and if you don't the end user doesn't see this。

 Only developers might see it So I tend to in some of my sites you can go look at them and you'll see the。



![](img/682937fc9d942667d8beb22634565c69_23.png)

talking and you can see， you know， a play by play of what's going on inside of one of my sites。



![](img/682937fc9d942667d8beb22634565c69_25.png)

Now， depending on the browser， the console object may or may not always be there。

 sometimes it's there when the debuggers on， sometimes it's not there when the debuggs off so my favorite thing to do is whenever I'm going to do a console log。

 I say windowt console which won't cause an error and so that means that if a console exists。

 then I will call console log， this is just a real succinct way of saying that windowcon and console log another way to do it。

 you can look up all kinds of ways to do with console。 log， this is my preferred way to do it。

 but you can also just if the console is doesn the console function doesn't exist。

 console variable doesn't exist， it sort of sets that up and sets a log function。

 but this is my favorite way to do that。So the debugger， as we mentioned。

 is a great tool for debugging JavaScript， you can pause the debugger。

 so let me show you how to do that。

![](img/682937fc9d942667d8beb22634565c69_27.png)

![](img/682937fc9d942667d8beb22634565c69_28.png)

Let you go back， you can pause code。Oh， sorry， I got to clear that。Pause code。

So here's JavaScript 01 right， and I can look at the source。

And I can put a breakpoint here by clicking right there。

So I now have a break point at that point now the page is already run， so once I set the break point。

 I've got to hit refresh once to load the page now that it knows where the breakpoint is supposed to be。

 it'll run up and stop at the break point。And so now it is paused in the debugger。

 you can see it is paused in the debugger， you see this little spin guy meaning the page isn't done loading yet because we've stopped it and we can look at variables and global variables。

 there's all kinds of stuff that we can look at。Document object model， all kinds of things。

 and I just click right here to continue the debugger and so the page completes Now that's a very。

 very， very simple introduction to using the JavaScript debugger， but it's very。

 very valuable and you'll get used to how this all works after a while。



![](img/682937fc9d942667d8beb22634565c69_30.png)

![](img/682937fc9d942667d8beb22634565c69_31.png)

![](img/682937fc9d942667d8beb22634565c69_32.png)

🎼Yeah。🎼。