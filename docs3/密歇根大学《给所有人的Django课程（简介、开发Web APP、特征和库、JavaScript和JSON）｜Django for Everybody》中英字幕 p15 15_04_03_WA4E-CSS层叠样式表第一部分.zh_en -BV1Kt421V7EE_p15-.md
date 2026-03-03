# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p15 15_04_03_WA4E-CSS层叠样式表第一部分.zh_en -BV1Kt421V7EE_p15-

Hello everybody and welcome to our lecture on cascading Style Sheets， CSS。

 of course this follows right on the heels of our HTML lecture and I'm going to use a bunch of examples from web applications foreverbody。

com and you can just bring these up in your browser。



![](img/9356ab4d8793d3abf5574c2a91233c05_1.png)

I love to place everything that we talk about in the context of the request response cycle because that's the whole web applications for everybody you of course are out here。

 you do a click， it sends a request of HP request maybe talks to a database， get some stuff back。

 send some stuff back this is the request response cycle right here and the thing that comes back is HTML and then that is parsed put into the document object model and the thing that you then see the pixels you see on your screen are from the document object model and so that's what we've been doing so far and so far then at HTML actually we just talked about this what the format was when you parse the response so what we're going to talk about today is we're going to talk about in addition to that we're going to go and pull another file。

 a CSS file， CSS and that is going to inform the document object model and it's going to change how things look out here。

And so you we'll have some CSS in the HTML， but we'll also have some CSS in separate files that make separate request response cycles。

 but so we're going to be putting files like our HM files in here and our CSS files in here。

 so we're going to be serving them a little bit， but mostly what we're worried about is sort of the form。

 how to make the DOM look pretty and that's sort of what CSS is all about。



![](img/9356ab4d8793d3abf5574c2a91233c05_3.png)

So in addition， I would like you to install。This thing called Web developer from Chris P。

 Chris Prick has been doing this a long time before there were even developer consoles in browsers。

 and it's funny that the developer consoles don't do what this does，I don't use all of its features。

 but it has some wonderful features for CSS in particular turning on and off various styles and so it's a great way to sort of dig through CSS issues in addition to the web developer console and you can do a lot of sort of find debugging but there's some real nice stuff a web developer it's just a plug in for your。

For your safari or your Chrome or your Mozilla browser or whatever， so please install that。

 I recommend it and some of the assignments actually require it。



![](img/9356ab4d8793d3abf5574c2a91233c05_5.png)

So like I said in the HTML lecture， the HTML started out with we were just amazed in 1995 when we could see a page with a gray background in blue links and it was lists。

 long lists of links。And。Well the links turned purple and we would click on a link and another page would come up and we' like。

"Holy Macckerel， this is the future right and we were so happy。And you know our curiosity was peakd。

 we did interesting things， but you know， in the 10， 15， almost 20 years since all that。

 it's become a business and in business， the look and feel for the average non-nerd user。

 they don't care that there's a request response cycle， they just want to do a thing。

 talk to their friends or look up information or whatever。

And so the CSS is in the middle of this timeframe that the ability to precisely lay things out and make pages beautiful became super important for the web to take it' sort of leap into commercial dumb And so if you look at the Yahoo web page for example。

 this is just a screenshot I took a while back。 they do studies as to how much white spaces in between those P2 pieces。

 and they'll add a pixel and take away a pixel and they'll see how their revenue goes And so these user experiences。

 these visual looks and feels are highly tuned and highly sort of taken care of。

 And so CSS needed to be able to precisely have a pixel perfect layout in every browser。

 And so CSS is a very very precise thing。 H has become precise but we don't want to do our markup and layout in HTML I showed you tables previously and in really early versions of HTML。

Able to create look and feel， and that was never good。



![](img/9356ab4d8793d3abf5574c2a91233c05_7.png)

So one of the things you can do with the Chris Pedrick web developer plugin is you can show a page without CSS and what you should expect when you see a page without CSS is it's sort of beautiful even without CSS。

 it's beautiful in a logical and a structure and so here's my web applications for everybody website right it's got cool stuff。

 it's got these little things that go over there， it's got the little border。

 the colors gray here and it's a little lighter gray and this wraps around and looks really awesome right？

Well， turn CSS off and you should still see a page that you could effectively navigate。

 It's like going back in time to a simpler time of okay， I want to see this。

 this is really a list of links at the end of the day and there you go it's a list of links and the default is I've already clicked on lessons so lessons is purple now and here's this video and if you scroll up and down on this。

 I mean， it's really fun to go to a website and。You know。

 turn CSS off and see how good their HTML developers are and how pretty it is。

 And so it's supposed to be pretty in a simple way。

 And what's nice about this is it really leads to good accessibility。

 meaning some people do not see the graphics they hear the page read to them and this way this is how it's read and the simpler and more beautiful and elegant in your HTML is the easier it is for a person who doesn't has reduced visual a person who has reduced visual ability to understand your sight。

 And that is I remember the joy of hearing from people who are using the web and gopher in the early days。

 how they all of a sudden could go anywhere and see anything and do anything in a way that visually impaired people could never do for like hundreds of thousands of years and。

It's joyful and then what happened was is we ended up with this really nasty markup and then theyre like it was like the web was simple and they loved it and then the web became ugly and nasty and HTML became nasty and they're like the world is horrible because now you go to all these cool websites but I can't go to these cool websites because I'm visually impaired and now we're back we're back to that we're back to beautiful HTML simple HTML and then beautiful web pages and CSS is the matter okay。

 I think I've done enough advertising for CSS and accessibility and beautiful HTML。



![](img/9356ab4d8793d3abf5574c2a91233c05_9.png)

So ultimately， if you look at how this thing is assembled in your browser。

 there is an HTML page that is request you pulled down and then there is CSS sort of both inside the document。

 sometimes' CSS in the document if you look at this not that it matters。

 there's a little bit of CSS in that document and then a whole bunch of other CSS that brings all the beauty to this。

 Sometimes it even take some jascript and whatever。

 And so we understand that the HTML does not have the beauty in it， the beauty comes from the CSS。

 and that is part of what we try to do is learn CSS。

 So if you're going to be like a coder and you're not going to be a graphic designer。

 you still need to know enough CSS so that you don't write horrible HTML so that you know what a really good CSS developer is capable of doing on your behalf and on。



![](img/9356ab4d8793d3abf5574c2a91233c05_11.png)

Large projects， including like Sakai，kai project， which is a open source learning management system。

 This allows separation of concerns。 And you can have people that specialize in the back end and the Hm L。

 and then a web designer can the Web designer。 So if you think of the developer， usually。

 there's a back end。 and then they generate from the back end。 They generate the Hm L。

 And then the designer will build the CS。 The designer will often have skill enough to sort of tweet the the Hml。

 if the developer built bad Hm L。 So they kind of meet in the middle of the Hml with a developer mostly being responsible for building the the backend developer。



![](img/9356ab4d8793d3abf5574c2a91233c05_13.png)

![](img/9356ab4d8793d3abf5574c2a91233c05_14.png)

And then the front end designer can then you know， tweak the HTML a little and then tweak the CSS。

 And so this the HTML is where the backend developer and the front end developer come together。

 but it means that you can。

![](img/9356ab4d8793d3abf5574c2a91233c05_16.png)

![](img/9356ab4d8793d3abf5574c2a91233c05_17.png)

It means that you can have lots of people working and you can develop highly highly specialized skill sets in larger projects I know that my skill set is in this side I am not skilled in this side right I can clunk my way through CSS and everything that you'll see is my CSS and you'd be like whoa that's not very good and if it even looks pretty of mine I probably use bootsottrapap and I cheated and found a CSS framework and I didn't build it I just did it now there are people who are smart enough to build bootsottrap and they can build such gorgeous websites and my job is to build beautiful HTML that then they can add CSS to and make it super gorgeous。



![](img/9356ab4d8793d3abf5574c2a91233c05_19.png)

![](img/9356ab4d8793d3abf5574c2a91233c05_20.png)

![](img/9356ab4d8793d3abf5574c2a91233c05_21.png)

![](img/9356ab4d8793d3abf5574c2a91233c05_22.png)

![](img/9356ab4d8793d3abf5574c2a91233c05_23.png)

![](img/9356ab4d8793d3abf5574c2a91233c05_24.png)

![](img/9356ab4d8793d3abf5574c2a91233c05_25.png)

So the CSS basic syntax is different than HTML right HTML is less than and greater than CSS has curly braces。

 I don't really know who invented the first， I should find that out and go videotape that person but it has curly braces in semicollonons so it kind of looks like a little bit of C and it's really a set of rules and it's not sequential although the order does matter because what comes later has more importance than what comes earlier in CSS but it's not like code that gets run and so the anatomy of a CSS rule is that there is some kind of a selector and in this case the simplest selector is the tag that we want to effect we want to affect the body tag now there's only one body tag but you could have a P for a P tag and say I would like to do this to all P tags and so it's implicit kind of like SQL in that a body tag means for all body tags there's an implicit loop for the whole document and we'll see how to。



![](img/9356ab4d8793d3abf5574c2a91233c05_27.png)

Redduce that later to it so it's not always the whole document but for now a tag means tag there by itself means every tag in this document and then there's a series of rules and so this is really when to apply this is sort of what thing what aspect and there's a whole list of aspects that you can have and then what you want to do I want to make the font size on0% I want to use aerial and then say in serif et cetera。

 et cea， et cetera， holy micro my little。My little pin is undoing itself and so then these end in the semimoclolon and you can have a bunch of these right you can have just one。

 you can have more， but that's the basic idea is a CSS rule is go find a part of this document and paint it。

 I'd like to think of this as like go find a thing and then run a paintbrush over top of it That is this paintbrush That is the paintbrush that you go select a piece of the document and then paint it yellow or paint it bold or whatever that's kind of how I think about it。



![](img/9356ab4d8793d3abf5574c2a91233c05_29.png)

![](img/9356ab4d8793d3abf5574c2a91233c05_30.png)

Now I'll admit I am。Just I'm the really a very weak CSS developer and I need a cheat sheet and if I'm going to do CSS having this even a single page cheat sheet is super helpful for me just because I don't use it all the time and and so the attributes like background color and the border dash bottom you know for me。

 they're all very self-explanatory， they're really easy to understand or if you don't understand I mean just Google and you go stack overflow。

 but like for me I'm like is it border bottom or bottom border。

I just can't remember that stuff and so I just have to have a cheat sheet whenever whenever I work and this is one cheat sheet that I happen to happen to like and these are the kind of properties that we're going to be playing with color。

 the background color， how to align it vertically how to align it horizontally padding which is space on the sides。

 et cetera， et cea， et cetera。 so there's just tons of CSS properties and there's tons of great documentation on each of these CSS properties with little samples all over the place。

 and I have my own samples as well。

![](img/9356ab4d8793d3abf5574c2a91233c05_32.png)

That I'll do some recordings and show you walk you through like line by line on my sample code as well。

 but this is the kind of stuff that we're going to play with in CSS。



![](img/9356ab4d8793d3abf5574c2a91233c05_34.png)

So up next we're going to talk about how we connect CSS and HTML together。



![](img/9356ab4d8793d3abf5574c2a91233c05_36.png)