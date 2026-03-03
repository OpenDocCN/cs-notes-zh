# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p116 8_代码详解：文档对象模型(DOM).zh_en -BV1Lr421A75d_p116-

So here is a string chuck， it's wrapped in a span tag， and the span has an ID of person。

Okay and so here in my JavaScript I say document， everything starts with document， get element by ID。

 and then I give the ID that I'm looking for， and then that basically looks through the whole page。

 looks through the whole page and it finds the thing that has the ID of person and then。

Let me clear this。Then this little expression right here。Is this tag？

So you basically have got yourself a handle， ST is the variable， this ST variable。

That ST variable is a handle to that little part。And then you can do things and we can do stuff to the outer part to tag and everything。

 but if we just want this HTML， we have to say give me the inter HTMLt so I say dot inter HTMLtl and that dives into the tag and pulls out the actual HTML。

Text， that's the child of that tag， and I can print that out。And I can also change it。

I can also change it so I can put it on the document get element IDperson。n HTMLtl equals Joseph。

 well that is an assignment statement that's going to overwrite this part of the document object model and change it。

And I have a couple log statements， so let's play with this particular one right here。



![](img/67b2b4ea691d02be7b5467c43e1a5f68_1.png)

This is JS 12。Okay， so if we recall。It goes in it。Finds the ID tag of person。

 then it prints out unless let's switch to console， I can't oh wait， wait， wait， wait wait。

 let me switch to console here。I mean， once the alerts up。

 I can't switch right because the alert is taken over the whole browser so I'm going to switch to console so I can watch it in console and then I'm going to clear the console and then I'm going to press a refresh so that I can sort of watch it all happen in the console。

Okay。So it looked up the span with IDd equals person， pulled out the N HTMLt。

 it both logged it in console。 log and it did it in an alert box。Okay。Now this browser is frozen。

 this browser is frozen because。The alert box is up and it's not going to do anything until we press OK。

 so I'll press OK， which means the JavaScript is going to start back up again。

If you recall what it does， it first puts out a log。That shows what kind of a thing。

That object is that ST object， and then it changed it to Joseph。

 and you'll notice that it changed it to Joseph literally my JavaScriptscript code changed the document object model and the browser is always rendering whatever is in the document object model。

 So my JavaScript changed the document object model。 The browsers just poof rendered it。

 so I'll do this in faster motion。So the original HTML had Chuck。

 we looked that thing up as soon as I hit this OK， it's going to change it to Joseph。

And it just changes to Joseph。Okay， so if I didn't have the alert， it would happen instantaneously。

 it would happen so fast you wouldn't see it， and I can use console。

 log to kind of keep track of stuff， right？

![](img/67b2b4ea691d02be7b5467c43e1a5f68_3.png)

And so you can sort of work through this thing and see all the stuff that's happening。

 I make it go in slow motion by putting this alert in。

 I could also use the debugger and a break point if I wanted to to see that。

 but I just want to stop it。 So this is looking it up。

 pulling stuff out and logging it and then it alerts to stop it mostly and then it changes it and continues on。



![](img/67b2b4ea691d02be7b5467c43e1a5f68_5.png)

![](img/67b2b4ea691d02be7b5467c43e1a5f68_6.png)

Yeah。So here's another one that basically is sort of combining an on clickick and so what's going on here is I have two links。

 it's probably easier just for me to show you how this works， this is JS13。



![](img/67b2b4ea691d02be7b5467c43e1a5f68_8.png)

Oh。It's JS 13。O。So。If I look， the word stuff is in here。



![](img/67b2b4ea691d02be7b5467c43e1a5f68_10.png)

Itops buning。So I have a span。Id equals stuff。And I have an on click。The word back and forth。

RightSo I do a document get element ID stuff inter HTMLtl equals the string back if I click on that。

 then I return false remember you' got to return false and then if you click on fourth。

 it's going to change that text to be fourth So what I'm to do is I'm overr this stuff right I'm grabbing it and I'm going to change it to back。

Then I'm going to change it to fourth， I'm going to change it to back and I'm going to change it to fourth。

 and this's all done on these clicks， but it starts out coming from the server with stuff there。

 right？Because that's what's in there in the first place， then I click on this HR， this HF。

 and it changes the dom to be back， and I click on this HR and it changes it to be forth。Okayay。



![](img/67b2b4ea691d02be7b5467c43e1a5f68_12.png)

This won't be very exciting， I click on back， it looks it up in on click。

 it looks it up and then changes it to word back。Oh， sorry。There we go。

Click on back and click on fourth。I actually don't have any JavaScript to reset it back to stuff unless of course I hit refresh and then it pulls another copy from the server and it's its original form。

These are just going back and forth。And changing it。Okay。



![](img/67b2b4ea691d02be7b5467c43e1a5f68_14.png)

Fascinating， hit the back and forth。Fascinating。Okay。

 and so that's basically causing things to happen as response to clicks。

 the previous example we just sort of had straight line code that ran。



![](img/67b2b4ea691d02be7b5467c43e1a5f68_16.png)

🎼Yeah。