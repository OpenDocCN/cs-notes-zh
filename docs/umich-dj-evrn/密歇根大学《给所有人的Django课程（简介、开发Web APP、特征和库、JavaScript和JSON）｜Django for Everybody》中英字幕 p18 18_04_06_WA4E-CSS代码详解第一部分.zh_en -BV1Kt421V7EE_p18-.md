# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p18 18_04_06_WA4E-CSS代码详解第一部分.zh_en -BV1Kt421V7EE_p18-

Hello and welcome to Web applications for everybody We are taking a look today at cascading style sheets。

 you can download the source code and unzip it on your computer if you like。

 or you can browse this code and just play with it in the browser because it's all static content so it's just as easy to play with it in the browser and of course we're going to want to take a look at this in the developer console it just makes a lot more sense to get into this and so you。



![](img/c9c6b8fde670dc006d36d88d35a33eca_1.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_2.png)

And so here we go。We're taking a look at CSS。 There's a couple of ways to do this。 We can see here。

 We can see the style attribute， style color equals blue。

 and there's all kinds of various CSS parameters。 color is the parameter in blue is one of the values。

 And you' got to look all these things up。 One of the nice things that we can see is we can see over here as we move between elements in the document object model。

 We can see what the CS values are。 And so aerial sense， like for example， this is cascading。

 the body on here is aerial。

![](img/c9c6b8fde670dc006d36d88d35a33eca_4.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_5.png)

mAriial or sand serif， and that means an aerial font， if we can get it， San serif is a fallback font。



![](img/c9c6b8fde670dc006d36d88d35a33eca_7.png)

And so that this H1， this little bit right here， this H1 is being colored。

 this it's colored this is ours。Browsers have their own default， so display block， font size 2 em。

 which is twice as big as the rest of the font， et cetera， et cetera。

 And so those this came from the browser。And then this came from the style sheet so this is cascading and the bottom ones here are。

 I mean this is the most important one because this is the one we said that's closest then that's how the cascading works。



![](img/c9c6b8fde670dc006d36d88d35a33eca_9.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_10.png)

You already saw that。I saw that。

![](img/c9c6b8fde670dc006d36d88d35a33eca_12.png)

And then the cascading is， again， we take a look at this this little guy here right here。

 And so the closest one is we want a monospace font family。

 but the body said the font family is Arel and San Serif， but this one has been overridden。

 and we can kind of see that。 And that's why this particular text is monospace。



![](img/c9c6b8fde670dc006d36d88d35a33eca_14.png)

Another thing we can do is we put border style now when I'm working with this stuff。

 I tend to remember border a lot because it's a good way for you to to mark something out say。

 what am I doing here and we'll see like when we're moving text around border。Solid border。

 a red border and a five pixel of order and so that's what we see and you can also see that there's some extra padding around there as well or some extra margin。



![](img/c9c6b8fde670dc006d36d88d35a33eca_16.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_17.png)

And margin top that's another one。'll scroll this up a bit margin top throws five ms of space the above the text and so this is a normal paragraph we got five extra Ms Now what's an M M is the height of a character in the current font so Ms is a really convenient measure there's Ms and pixels and and percent So so margin before that's one M over here the paragraph already has an M margin before and then come down here down to here we've added the margin top So this margin top overrode the margin top that was part of the。



![](img/c9c6b8fde670dc006d36d88d35a33eca_19.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_20.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_21.png)

Part of the paragraph tag automatically so that's these style rules， let's keep on going。呃。

While this is technically possible， this would really be overwhelming to put a style on every tag。

 And so one of the things we tend to do is we want to put style rules that are generic。

 So we'll say we would like the body tag。 and this is a style rule。

 This is a selector body and then font family and again。

 font family works is please give me the aerial font。 And if that's not available。

 give me San serif font。

![](img/c9c6b8fde670dc006d36d88d35a33eca_23.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_24.png)

Curly brace， curly bra H1 tags want to go through the whole document and paint H1 tags blue go through the whole document whole document。

 find every paragraph tag， set the border style a solid border color to red five pixels so you see that every paragraph and we're going to change our anchor tags to have green and have no text decoration because they're defaulted by to have。

Their default to have underscore and we're gonna make the background color like great why just so we see it so you can see that particular thing up there and then if you look down into the text here。

 we have paragraph tags and and an anchor tag and no style equals down here so what we've done ignore that little part there that's what puts this little thing in the corner so that's not what we're talking about we put no style tags whatsoever and we put all the style tags up here but now we've also done something that all the paragraphs have to have the same style which sometimes is what you want and sometimes it's not what you want Now it happens again now if you have multiple pages as we who have here。

 it gets little tiresome to put this text in every page and so what's really common instead so now we have the same basic rough paragraph stuff here nothing in here we have a pretag of course we have a paragraph tag there's no style equals on these things but up in the head we have one line right here。



![](img/c9c6b8fde670dc006d36d88d35a33eca_26.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_27.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_28.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_29.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_30.png)

Basically says let's take a look at this style sheet and if we were to look at the style sheet got CSs。



![](img/c9c6b8fde670dc006d36d88d35a33eca_32.png)

It is in the same folder。Rules do CSsS， it's in the same folder as that HM file。

 and it's exactly the stuff we had there。 It's just a set of selectors and then a select of key values。

 we want color blue border style border color， et cetera， et cetera， et cetera。

 And so it really is the same as what we what we showed before。



![](img/c9c6b8fde670dc006d36d88d35a33eca_34.png)

except now that we have we have to put this into every file and you'll see we'll put this now from now on and everyone that I'm looking at。

And so， but now our problem is is that we've done something with this to do all the headers， right。

 all H1s， all paragraphs， but we need better ways to mark text and so。



![](img/c9c6b8fde670dc006d36d88d35a33eca_36.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_37.png)

And so we have these tags and these tags that we use just to put handles on and in the old days。

 like this paragraph tag has this border see that has the margin up there。



![](img/c9c6b8fde670dc006d36d88d35a33eca_39.png)

I mean it has has the border but it has this 1 m margin that' that's that space that you're seeing that makes paragraphs look good I mean it's not a bad thing and so if so if you look at that we have all these colors。

 we've got this strong tag。

![](img/c9c6b8fde670dc006d36d88d35a33eca_41.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_42.png)

By default， the thing use a serif font， I don't like that。



![](img/c9c6b8fde670dc006d36d88d35a33eca_44.png)

So let's get down to here and this。Let's just look at it here。

 the span tag inspect element right there。

![](img/c9c6b8fde670dc006d36d88d35a33eca_46.png)

Okay， so the first thing is is the span tag is an inline tag that has no styling。

 The problem is is before CSS， which is a long time ago， all these tags had default styling。

 but the span tag is an inline tag with absolutely no styling whatsoever and then the div tag is a tag a block tag that has no styling whatsoever and it can be nested so it's kind of like a paragraph tag but it has no styling whatsoever I've added a one pixel style and you'll see that these div tags don't have any extra space like the paragraph tags came with space now some people would go and turn off the space on a paragraph tag and there's even CSS files that you can to take all the styling font styling off tags but you'll notice these divs don't have any space they're really kind of a block when I put these pixel on。

 you'll see the border if you look really close， you'll see that there's a one pixel blue line and a one pixel orange or Santa line right there。



![](img/c9c6b8fde670dc006d36d88d35a33eca_48.png)

But the divbs can be nested and they don't themselves start so you'll notice that here they don't start with any kind of formatting that comes from the browser。

 whereas if we look at paragraphs there is formatting that comes from the browser and so the divb tag are and。



![](img/c9c6b8fde670dc006d36d88d35a33eca_50.png)

The div tagag and span tag are just our ways to put handles around blocks of text or chunks of text and then style those。

 but then we still have to figure out how how to grab our handles and make it so that our styling doesn't just touch one thing。

And so here I've got a couple of things I've got the body tag and I'm setting font family you'll see me do this all the time and now I have a pound sign and this says go find all the tags name body this says go find all the tags with a attribute of first ID equals first ID equals second and then class and shout So if we take a look at the text。



![](img/c9c6b8fde670dc006d36d88d35a33eca_52.png)

There is the notion of an ID tag okay an ID tag that can is unique within the document。

 so we're going to call this div first we're going to call this div second and this div third and they correspond to first。

 second and third okay and so you know first is。

![](img/c9c6b8fde670dc006d36d88d35a33eca_54.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_55.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_56.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_57.png)

嗯。

![](img/c9c6b8fde670dc006d36d88d35a33eca_59.png)

First is monospace， what is it first is monospace， second is green。



![](img/c9c6b8fde670dc006d36d88d35a33eca_61.png)

So everything that's in this block that' second has been green。



![](img/c9c6b8fde670dc006d36d88d35a33eca_63.png)

And then but you can only have one ID name first， but class you can have all over the place so we can have。

We can put them more space class。On a couple of different tags。



![](img/c9c6b8fde670dc006d36d88d35a33eca_65.png)

So this tag more space， all more space does is shove it in from the left and the right。

 margin left and margin right， so it's kind of pushes this in and so you can put this on here。

 you can put it another place and so the more space pulls in something here。



![](img/c9c6b8fde670dc006d36d88d35a33eca_67.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_68.png)

So here's another paragraph that's got more space， that one has more space， this one has more space。

 see that one。

![](img/c9c6b8fde670dc006d36d88d35a33eca_70.png)

And so you can put more space on as many times as you like and then you know， div third。



![](img/c9c6b8fde670dc006d36d88d35a33eca_72.png)

So the hierarchical section。Means。In this case here， this one's a little bit and loud is red。

 so where's loud at， so let's Lis that one。Spect element。



![](img/c9c6b8fde670dc006d36d88d35a33eca_74.png)

Yeah， so that's and this the loud is not only red， but it's also forced uppercase。

 text transform to uppercase。

![](img/c9c6b8fde670dc006d36d88d35a33eca_76.png)

嗯。

![](img/c9c6b8fde670dc006d36d88d35a33eca_78.png)

Shouting out loud， and you can have more than one class on。



![](img/c9c6b8fde670dc006d36d88d35a33eca_80.png)

嗯。On a tag， and then you can be even more precise with your selection。This is basically。

 this says find a third ID and then only paragraphs within that tag third make their background color yellow。

And so that means that background color yellow does not apply to this tag。

 it does apply this paragraph doesn't to apply to this to paragraph， but when you see divID third。

 we have selected this paragraph。

![](img/c9c6b8fde670dc006d36d88d35a33eca_82.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_83.png)

In this paragraph， and they have a background color of yellow。



![](img/c9c6b8fde670dc006d36d88d35a33eca_85.png)

So continuing on let's take a look at a simple navigation bar now there's this navtag that's an HTML 5 thing and if you look at most navigation on pages let's go to the next one they prettyti and they got colors and they move around and stuff but what we don't we want to be careful when we build our HTML for these kinds of things to make them very very simple and so what I've got is a navigation is usually we describe it。

 we use a navtag which is a block tag that says hey this is our navigation useful for screen readers etc and then we're going to say we're going to have we're going have two a list of two。



![](img/c9c6b8fde670dc006d36d88d35a33eca_87.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_88.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_89.png)

Two links and so that's what we're doing unsigned list unordered list and a list element that's just no paragraph here just just an include。

Just a anchorer tag。 And we're going to put a class equals back and class equals forward so we can style these two things differently in the future。

 And so this is what this looks like with no Css whatsoever。 And so this is a nice， elegant， clear。

HTM and so if you were just looking at this HTML， like a screen reader might be looking at。

 you can see what this really intends to mean。Now。Then what we do is we add a little bit of HTML to this。

 and so for now we're just not going to bother， but in navbarcss。



![](img/c9c6b8fde670dc006d36d88d35a33eca_91.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_92.png)

嗯。Is the HTML or the CSS that。It makes this pretty and so there's a whole bunch of stuff and we'll come back and take a look at that in a second okay and so so there's our styled navbar so I'll come back in another video and pick up right here。



![](img/c9c6b8fde670dc006d36d88d35a33eca_94.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_95.png)