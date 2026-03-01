# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P67：67_03_08_演示：穷尽匹配.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

There is a bug in this code you might be able to catch that I already have a red curlyline underneath grapes in the match under line8 Now there's a bug and there's something that rust will just not let you do if you're not taking care of dealing correctly with a match when you are dealing with an enum In this case。

 we have an enum that is defining variance for wine grapes。

 Canet Frankranc Tat and Merlot so we have these three variants of the wine grapes and we have we want to taste the wine and we want to match it and we want to kind of like identify which one we're dealing with。



![](img/c4f97fb2806f34004ad479c15d7774fb_1.png)

So what is the deal here， why is this complaining right here。

 I've commented out both Tat or load and I actually can remove them。And I can save these。

 I'm still getting that red underline。 So let's just think about these for a second。

An enumerator and enum like a wine grapes will provide certain variants。 If we're providing three。

 then rust will want us to implement。A match， a condition that deals with all of the variants。

 if we only had two， you would expect two different ways to deal with that。

And there's one exception which I'll tell you in a second that you've actually seen before。

 but not so explicitly， so what is the deal here？We have Carnet frank thanat and Merlo so think about these like like the ability of dealing with an actual variant another option that we have to deal with possibility of either is' going to be this one or that one or that one and we have to deal with all of them but in this case we're just dealing with one type so that's not valid so this is why we need to deal with these other guys right here and let's un that very quickly。

And let's see， let's see what happened about before before I comment the last one。

 let's take a look at this missing match arm Merlo， not covered non exhaustive patterns。

 thanat and wine grapes Merlo， not covered right So if we if I do if I comment that and save。

 it will get similar similar error missing match arm， tenat and Mer load not covered。

 So if I uncommon these。Then things will work。 and that's actually aluminum formatities nicely and that will work。

 And that's that's perfect。 So I'm only passing one right here in the main function。

 If so if I run that， it'll probably just reply without one and let's see And that's correct。

 This is a carbonnerank wine which is one one grape that comes with ones perfect。

 So so what's what's the deal do we always need to do every single match well。

 not really what we can do here and you've already seen it before。

 we can do something like when I commented out and we're gonna get get the curly directly curly underline So what we can do is a catch all so we can say。

Anything else here， we can say， you know， we're interested only in carbonne franc。

 if it's dark carbonnet franc， I don't care。 And do you see how the red underline went away。

 that is because we are able to make it work because the underscore means everything else that is not this one。

 So if you had an an inum that has 200 variants hopefully hopefully you don't have to deal with something that has 200 variants。

 but if you do。You don't need to list every you know variant explicitly， you can say。

 well I'm interested in this case right here and that's it like the rest I really don't care so you can use the underscore to catch them all and now you can say well。

 the that is fine and carbonnera is fine but like Merlot I don't care。

 you can you can definitely mix a match so you can you can say that and we can actually put that1 right here。

And run it and be fine。 And now it's a still carbon Nera wine。 But we can actually change these two。

To Tenette and that we would be okay。 and if we run it again， we're going to say， yeah。

 Tenette is fine。But otherwise， we can say， you know， well， if we say the final one， Merlot。

 and we've already covered this before， but it's useful to see this is not carbon fra wine。

 of course its not because it's Merlot， So there you go。

 this is the ability of doing exhaustive matches and it is something that the compiler will complain if you're not exactly doing this to cover all the matches with the exception that you have these catch all that allows you to encompass everything else that is not already defined right here。



![](img/c4f97fb2806f34004ad479c15d7774fb_3.png)