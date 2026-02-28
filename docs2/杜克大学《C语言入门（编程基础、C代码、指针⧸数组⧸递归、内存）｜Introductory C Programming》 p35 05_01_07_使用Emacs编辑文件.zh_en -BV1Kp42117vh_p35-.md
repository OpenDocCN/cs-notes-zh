# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p35 05_01_07_使用Emacs编辑文件.zh_en -BV1Kp42117vh_p35-

![](img/7e594d45c4841d81923a46695662e497_0.png)

All right， so you've seen a video where we used Emax to write a little simple file， save it。

 We added it to get and submitted to the grading system。 Emax is a really powerful editor。

 It has lots of features。We're going to show you some simple ones like searching， undoing。

 some cool features of Emaxs undoing and a little bit more advanced features like keyboard macros。

 we're obviously not going cover all of EmX in this video。

 but we're going to show you some of the more useful features and then you can learn a lot more as you go so if I look in this directory I have a text file and a C file to work with。

 I'm going to open up this text file and start working with that。

It's just a bunch of text from chapter two of all of programming。

 you probably read most of this in your readings in course one。

So one of the things I might want to do is search if I hit control S you'll see at the bottom of my X term it says Ise Emax has incremental search。

 which means as I type a search term it will start searching for whatever I've typed so far so if I type I for example it goes to the first instance of I and highlights all the other ones if I type M afterwards it's going to refine that and start showing me things like important and sometimes and simple。

 if I were to type E it comes down here to sometimes you're finding that further。

 This is really nice when you're programming because you want to search for a function name or something you hit control S you just start typing a little bit you'll quickly get to what you want and you generally don't have to type out the whole thing。

If I hit backspace， it goes back to I am。I might want important but not this one so if I hit control S again。

 it will search forward for the next instance of I am and I can keep doing that and at this point it needs to scroll down in a normal X term this wouldn't happen X term JS has a little bit of a weird bug where it doesn't always redisplay the screen correctly if that happens just hit control L and that'll make emAC redraw the screen completely so then I can just resume by hitting control S again and searching some more that bugs a little annoying but X term JS isn't my thing。

嗯。Okay， so that's searching， you can also search backwards if I hit control R。

 they'll say I search backwards and I can search backwards and it will go backwards and I can change between these with control S control R to move forwards and backwards to my searches。

Allright， so that's searching。 What else might we want to do in our editor。

 we might want to undo things。 So if I type some stuff。For example。

 and then realize I didn't want it， I can hit control X U， and it'll undo that change。All right， now。

 that's pretty normal。Let's just suppose for a second that I made a bunch of changes。

 so I do some changes here。Blah， blah， blah， some other stuff。

And then I go and do some really important stuff。 really important， complicated stuff I want to keep。

And now I realize all that other stuff I just did， I want to undo it。

 and maybe this happens in programming， I might make some changes in one function and then go work on some other piece of code and then somehow realize that I messed up that function。

Well， if I hit control and then space， it's going to say Mark set and start highlighting a region。

And once I've highlighted a region and selected it， I can undo in that region。

 so if I undo control X U， it will undo in region and it will start only undoing the changes in that area of this file and not the later changes that I did somewhere else。

 which is really nice when you're programming or even editing other things in general。

I'm going to come down here， so sometimes I want to move to the beginning of line， C A will do that。

 Control E will go to the end of the line。I' going to take out this， this line of text。

 So control K cuts an entire line。 If I wanted to paste it somewhere else。

 control Y pasts the previous thing that I。I cut。Or copied。 If I want to copy or， or cut a region。

 I can select it。 Control space begin selecting， and then control W will cut。 control Y will paste。

 If I wanted to copy instead of cutting， I can hit escape W。And then， paste。Now。

 one of the other really cool features about Emax is after you paste。

 you can change back through previous things you've pasted。

 so immediately after pasting if I hit escape Y， it will unpastee what I pasted and paste in the previous thing and I can do that again and get back to previous previous things that I've copyied and paste it。

 So sometimes you copy and paste things and you want to paste not the most recent thing。

 That's really cool。Okay， I'm just going to revert actually。

 I'm just going to save that it doesn't matter。The other feature I'm gonna show you in this video。

 which I think is really cool。 I'm gonna open up this Eum example where I've written Eum a bunch of things。

 It has all these things in it。😊，And what I'd like to do is write a function that takes one of these takes this enum and prints out what it is。

Now。I just told you how to copy and paste。 So I'm gonna copy。 And while I'm copying。

 I can actually like search for curly brace。

![](img/7e594d45c4841d81923a46695662e497_2.png)

![](img/7e594d45c4841d81923a46695662e497_3.png)

And just sort of jump down here without scrolling through the whole thing。

 so I'm going to copy all that。 I'm going to write a function print thing。 It takes enum。

A bunch that that name was really long。 I'm kind of lazy， so I'm just going to hit escape slash。

 it's going to complete that name for me。Oops， I need to give that a name。 T， switch T。And now。

Just pasted all those things。And Emax is telling me what my curly brace matches。

 even though it's off screen， and it's not lining upright because I don't have any semicollonons in there。

 so Em knows something's wrong with the syntax of this。 This tells me what I've matched。

 Also if I hover on something，'ll it'll match up if they're on screen。

I'm just going to search backwards for this。Now， what I'd like to do is I'd like to take each of these。

Names of， of enum cases that I just pasteed in here。

 And I'd like to change each of them to look like case， that thing， print F， that thing break。Now。

 most editors， you'd have like a tedious 15 minutes of like copy and paste and change。

 and it would be really boring。But EmX has this really cool feature called keyboard macros。

 So basically， I want to do the same thing to each line。 So here's what I'm going to do。

I hit Control X open parentheine it says defining keyboard macro。

And now Emax is going to remember the sequence of commands I do。

 And let me replay that sequence of commands。 So what I wanted to do is go write twice。

 I want to write the word case。 I want to start highlighting a region to copy so I hit control space。

I want to search forwards for a comma。And then I want to go backwards。 So I hit left。

 and then I want to copy。 So I'm going to hit escape W。 Now。

 I want to come over here and replace that with a colon。Type print F。

 I'm going to paste that thing so I hit control Y。Let's say I want a new line。And break。

 And then I want to go down a line and to the start of the line with control A。

 Then I hit control X close print。 and it says keyboard macro defined。

 So that sequence of commands I just did to that line， I can hit control X E。

 and it'll do that again to this line。 And after I've done that， it says type E to repeat macro。

 I can just hold down E。Well， on this， it makes me repeat it。 But on most editor most terminals。

 you can just hold it down。And then this one isn't going to quite work because like it doesn't have a comma。

 but if I just put a comma there， make it look like the others boom。

And now that's syntactically legal， I might put like default print F。Invalid thing。Break。

But I got Emax to do all that work for me with keyboard macros。

 So there' are some of the cool features。 You'll read about more of them in your readings。

 and you'll learn a lot of them with practice。😊。

![](img/7e594d45c4841d81923a46695662e497_5.png)