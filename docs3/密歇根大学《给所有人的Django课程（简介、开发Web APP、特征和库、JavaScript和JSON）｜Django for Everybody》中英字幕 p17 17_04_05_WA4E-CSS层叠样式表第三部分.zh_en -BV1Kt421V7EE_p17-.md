# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p17 17_04_05_WA4E-CSS层叠样式表第三部分.zh_en -BV1Kt421V7EE_p17-

So welcome back now we're going to talk about some making our stuff look a little preter with images and how you can play with images。

 colors and fonts so CSS and images are a lot of fun， we can fool around with them。

 we can move them around actually this for me years ago was the thing that in 1994 that made me fall in love with the World Wide web。



![](img/d3ed335669f46a6aba39302c6248b43e_1.png)

So what made me fall in love of the World Wide Web was the ability to take a picture of me and I love pictures of me and then float it to the right。

 and then I put a little border around here。 And so that's what I've done with CSS。

 So let's take a look at how I've done that。 So if you look if you look in line here the navigation which I'll show you in when I go through the codewalk through how the navigation works。

 But at this point at the end of the navigation is right here。

 And I put this image in so if you were to watch this in line， the image is right there。

 But what I do is when I say float that actually and there's other things that we'll see when we start looking at fixed and absolute positions。

 you can pull it out of the regular stream。 and so this is like pulled out of here and says if it didn't exist。

And it floats the right， but then it's vertically aligned。So the next thing you see is this header1。

 this header1 Cs， I mean， oh， there's a typo there。 I got to fix that。

 So pretend that that was an H1 there， but that's okay。 So this header。Atquirks mode。

 I should have run this all through。The validator to make sure I'm okay。

 but okay so the top box of this CSS and image H1 is right here and then this floats over。

 but then it top aligns now you can change this alignment if you like。

 but it top aligns here and then it actually looks at the width in this case。

 the width of the picture but you can also control the width up here in the CSS and then it carves out this space。

And then I do a margin of 1 M。 and so on M。So it。嗯。

You sort of sometimes wish they would put default formatting on。

 but then they kind of tend not to put default formatting on。Because if they did。

 then you have to turn that off。 And so I wanted some white space。

 And so I had to put some white space around it。 And so I said I'd like a margin of 1 m。

 And so that puts a little bit of space here and here and actually here as well。

 So you see that this lines up over there。And then that talks about what is a 1 M。 So 1 M。

 I could have said five pixels，5 px。 and that would have been fine。

 But1 M is basically the width of the letter M roughly。

s it's sort of it is a width that changes with the size and nature of the font。

I think of it as the width of an M and I think that might be a soft definition of it。

 but I don't think it's a precise definition of it。

But that's what I did so float right hoist it and sends it over here and then shoves this over so that this text is now it reserves this space the text is wrapped basically and then I held out some space just for prettiness right and so that's like CSS ast making it look pretty。

Now what happens here is I sometimes you want to basically force after this float has happened。

 something back to the left margin and there's this clear equals all that says clear any floats is what it's really saying and and so it means that even though this if it wasn't for clear equals all this next paragraph would have been kind of up in here and then maybe it would have wrapped if it was long enough。

 and when you play with this you can resize it and see how the wrapping changes。

 but no matter what the size is after the BR clear equals all。

 this is going to format back to the the left nav。So that clears that hanging wrap that sort of。

 but you don't have to you could just you could not do this and then it would wrap and wrap and wrap and then it will get longer and it would continue on。

 but if you want control over that you can with the BR clear equals all。

And of course you can have images right in line and this is just from the HTML bit here。

 there's nothing fancy CSS here， images kind of are like big characters。

 I size that one so it sort of fit nicely and you could even make this a clickable link。

 but that's really just this part here is just HTML。Not CSS。

But I could have if I wanted to change the width and the height of this。That'd be kind of fun。

 make this guy be like the width of an M， and then you'd see it more like a character。



![](img/d3ed335669f46a6aba39302c6248b43e_3.png)

So there's a bunch of colors and the colors have to do with there's the simple thing for us simple folks。

 you know we just put in things like red and green and stuff like that and especially if you're doing a developer and you're just trying to get basic stuff working I often use colors in my testing that like put the border red I do that all the time to say where is that div at anyway so although a one pixel border around it red border like oh that's where it is although the Chris Ped plugin has a thing where it puts one pixel borders around everything for you automatically but whatever these are not necessarily most graphically beautiful colors even though I like them because they're super primary in terms of primary colors and strong you'll see that I kind of use those colors in my slides a lot because I'm not a graphic artist of course I just like oh the greenest I can be is good。

So there's 16 official colors and they're here once you get a little more sophisticated。

 you can use precise colors from like I think this is。



![](img/d3ed335669f46a6aba39302c6248b43e_5.png)

I don't know， 32 bit。Yeah， so this precise colors are the ones that start with Poine。

And so pound sign， and these are hexadeadecibel numbers。

 these two numbers are effectively zero through 255。But they're in hex， So hex is like A B， C。

 D E F are actually numbers0 through 9。 This is actually 10，1112，13， this is 15。

 And so E is bigger than9 and F is bigger than E but basically these are 0 through 256 That's a3 top of 0 through 256 numbers and so the more red you put in the higher this is the more green you put in the higher that is and the more blue you put in the higher that is so RGB red green blue。

 And if you're playing with like a slider inside your UI you might be changing this。

 but you're just changing these numbers ultimately And so you can find these things。You know。

 so white is all Fs and so if you turn it all on， it's white， if you turn it all off， it's black。

 the absence color is black， red， green， so you turn that's max。

 max and max and so you can make sort of a pure red。

 pure green and pure blue picking these advanced colors is sort of way beyond my ability as a graphic artist and people will pick colors。

 there are sites that help you pick palettes for your pages， etc cetera， et cea， et cetera。

 there is also a。

![](img/d3ed335669f46a6aba39302c6248b43e_7.png)

![](img/d3ed335669f46a6aba39302c6248b43e_8.png)

Sometimes these colors can have a transparency and there's a fourth set of two numbers that have to do with the how transparent the color might be。



![](img/d3ed335669f46a6aba39302c6248b43e_10.png)

So fonts are also important。 The default font is a Times Roman because that's what computers had in 1994 and I think they're ugly。

 especially on screens， they're not so bad on print but they're ugly on screens and so I tend to want a San serif font it's too bad that they and maybe they have changed some default San serif I just change it to San serif all the time they want Now if you look at fonts。

 the font family is kind of a special tag and that you ask it a set of fonts and what you're really doing is you're setting a priority and the problem is is depending on whether you're on Windows or Mac or which version of Windows or which browser or what fonts they've had installed。

 you can you know fonts might not be there and so what you basically do is you basically say okay I would like this I think this is a Microsoft font and if that font's not there then I would like this font and I think that might be also a Microsoft font and if that font's not there then there's。



![](img/d3ed335669f46a6aba39302c6248b43e_12.png)

See how much I know about graphic arts I have no idea。

 I think this might be a Mac font and if that font doesn't work default into the fallback font San serif and there is always going to be a serif font times new Roman like San serf aerial like monospace which is courierlike cursive and fantasy which are whatever and so all browsers are supposed to have those fallback fonts and so you tend to see them here at the very end and so when you see me I usually will say Arriial San serif for something like that just to get San serif although it's quite common。

 the more sophisticated a pages the more likely and the other thing that's increasingly the case is people are downloading fonts and having special beautiful web fonts and then they download them and then they put that font in here。

 but then they probably still have fallback font so fontt family is kind of a weird and unique and glorious thing that leads to some really gorgeous web pages because so much graphic arts work is going into making wech pages beautiful。

And we're going way beyond the operating system installed fonts and having pages that download their own fonts。



![](img/d3ed335669f46a6aba39302c6248b43e_14.png)

Things that you can do is set the things bold， italic， text decoration。

 member links have underlines and we can turn them on or off font sizes are kind of troublesome in that you can set them to pixels。

But then you're in danger if you get to a certain kind of a screen size or people start zooming the screen and stuff and so you can tend to use these relative ones。

 but they not as they're not as guaranteed as you might like them to be and so just these are a little bit tricky absolute font sizes are a little bit dangerous I tend to just go like。

Here's my font。 Here's the one that's a little larger。 Here's a little smaller。 if I need that。

 So most of the time I'm tending to do things that are。Like smaller。

 if I'm putting like a copyright statement and I don't want to distract from the main page。

 I'll just make it a little small。 You know， I'll say， okay， make this。

 make this small or extra small。 And you know what if it doesn't turn out to be that much smaller。

 It doesn't matter。 I'm just kind of trying to。So I'm not an expert in how to use those。

 I tend to use them as simply as I possibly can because they're not as predictable as it would be nice that they were。



![](img/d3ed335669f46a6aba39302c6248b43e_16.png)

So links were in a big part of the early web， and it's called hypertext markup language。

 hypertext transport layer， hypertext hypert hyperpertext。 And so links got really special treatment。

 they used to be blue before you clicked on them and purple after you clicked on them。

 The blue is to jump out at you and say please click me and the purple was to say I've been there because a lot of what you did in the early web as you wandered from place to place to place to place is like oh。

 I found a new thing Let me explore this。 And so you' were always like exploring by clicking links。

 Once we got to the point where people assumed the web。

 these links didn't need to be blue and garish colors to teach us these things because people just clicked on everything。

 And so it became more important to make things pretty。

 So we have a lot of control as to how we style links we can say the a tag we've already colored an a tagag with just the a at the top。

 you can basically say an unvisited link is supposed to have the color black after the visit。



![](img/d3ed335669f46a6aba39302c6248b43e_18.png)

It's supposed to be gray while you're hovering over top of it。

 it's supposed to have text decoration in none and be black white with a background of na and an active is not so heavily used it's once you've clicked on the link while the page is loaded so it's a way to kind of you know maybe disable it or turn it to color so people think oh I better wait until this next page loads and so when I do the recording you'll see this it's a lot easier to see this dynamically and so there's a whole bunch more samples that I have and I'll record some walk crews of every single one of the samples and so you can take a look at that at web applications for everybody or in the recordings。



![](img/d3ed335669f46a6aba39302c6248b43e_20.png)

![](img/d3ed335669f46a6aba39302c6248b43e_21.png)

So this has been a zoom through CSS， you know， CSS is quite the art and science and it's evolutionary I mean people are specialize in this。

 they're very good at it， it's a modern form of graphic arts the basics are there and I think every programmer who does anything on the web should know the basics of HTML you they keep moving things better with things like navtags and bootstrap etc and while there will always be like edgy new things in CSS and so you sometimes you'll see CSS with like these mas fields which are for Mozilla for the Firefox but people are always push boundary and before you couldn't put rounded corners on things but then the browsers added extensions to put rounded corners on things and then everybody kind of agreed on that so CSS is kind of always going to get better and better and better because for the mobile and desktop they really want to create as beautiful experiences possible and use standards wherever possible and so the basics are。

ThereYou can do so many wonderful things， especially if you pull in a something like a bootstrap that just kind of cleans up the rough edges of HTML and makes it generally pretty and takes a lot of responsibility off of you but you can certainly make a lifetime study of CSS if you like so I hope you found this useful I will see you on the net。



![](img/d3ed335669f46a6aba39302c6248b43e_23.png)