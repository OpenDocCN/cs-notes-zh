# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p07 -07-COMP6080 - CSS 🌝 Formatting.zh_en -BV17RXGYuEaM_p7-

Hi， my name' is Hayden and today we're going to be learning about CSS formatting so far we've learned about the rules that we can use to apply CSS properties to particular elements based on selectors。

 but we haven't talked a lot about those properties themselves and what we can do with it。

 which means we haven't talked a lot about how we can actually make pages colorful and interesting and dynamic in terms of their visuals and aesthetics Now today we're not going to be covering everything you can do in terms of CSS formatting。

 we're going to be really focusing in on just text and background images。

 but that's okay because it should give you enough of a taste and a flavor for what you can do in your own time。

Now I mentioned text so let's have a look at some text Tex is probably one of the most versatile elements of what you can tweak on a page because there's just a lot of variance and we'll kind of just look at a really simple example so let's make ourselves a span we'll give it a class say my text。



![](img/3bff1ae818210ef9e048824205c08b9c_1.png)

And that can say hello， you know， maybe we'll， maybe we'll add a few extra things in here。 So。

 for instance， inside of this span， maybe we'll add a paragraph， hello。How are you like this。

And then at the top， let's make ourselves a custom style and my text here and we'll just start with a red colour you know。

 so that text will have a red colour and I've got the page up here So we've got hello， how are you。



![](img/3bff1ae818210ef9e048824205c08b9c_3.png)

Now， I'm just gonna start launching off a bunch of different things you can do。

 You can make your font bold if you'd like， that's one obvious one。 You can change the font family。

 That's like the font， as you would in like。Microsoft Word or Google Sheets or something like that。

 So it can be aerial。 Now remember these fonts are actually on your system computer。 So these fonts。

 the web browser will actually talk to your operating system to see if that font exists So it's not something that just kind of exists within Google Chrome or edge or Firefox or something Safari。

 It actually is on an individual computer。 Now this is usually okay because nearly all computers have the same basic fonts but it's much more relevant if you're using a more obscure font And there's actually an entire lecture on fonts that you can go and look at where we talk about font sizes in a lot more detail and font families and everything else。

 So we' we won to go too far into fonts。But speaking of size。

 you can also change the font size Now previously you would have seen me do something like font size 200% There are a few different ways that you can express font sizes again。

 go check out the fonts lecture but in general the way I'd probably recommend you do it is that 1 em is the standard font size and if you want your font to go bigger or smaller you simply treat that like as a factor so for instance。

 1。5 is 50% bigger than normal and 0。5 is half as big as normal and you can use that as a kind of general scale。

We can I already mentioned that we have the colour you'll see a few more examples up on this slide include the font style。

 the text decoration again， some of these you might have seen before so you know you' got text decoration underline that will make your text have a line underneath it you got font style italic So that's how you get your like kind of italic slanted text we also have things like line height so for instance。

 if you want your your text you know across many different lines to have。



![](img/3bff1ae818210ef9e048824205c08b9c_5.png)

![](img/3bff1ae818210ef9e048824205c08b9c_6.png)

Extra height。You can do something like that。 So now it's like got extra height。

 or you can make your even smaller。 You can make them， you know，50% size or， you know，0% size。

 which is no gap between them。 You can often make line height actually kind of creep up on itself。

 Similarly， you can do the same thing with ladder spacing。

 So letter spacing can be 100% or 200% if you want it 200%。 Let's look up ladder spacing， CsS。

So a letter spacing will have。It's probably in pixels。 Y。

 so letter spacing actually needs to be a certain number of pixels。

 So let's say you go like 03 pixels。 That means it's going to try and put three pixels of space between each character。

 If you go like0 pixels， you get normal， you can go negative three pixels or something like that。

 that's how you get text overlap。 So occasionally you'll actually see websites where kind of text looks stylized like this。

 And they can just do that by playing around with letter spacing。

 maybe you don't want it to be underlined， for instance， and you've just got something like this。

 Now this text here is really small， Maybe we'll make it a bit bigger。

ll make it and something like that That's also why you might have noticed you I don't know if you were paying attention。

 but when I did three pixels before it looked like the gaps were really big like when I add went from three to five and you might be thinking gosh you know some of those gaps look bigger than three pixels well that was because I was zoomed in because that's the actual size of the text here So when we go negative one pixel all it does is actually shift the characters just literally one pixel to the left and negative two negative three you know now suddenly it starts to look。

Quite tired and cute。Um。So that's just some basic examples。😊。



![](img/3bff1ae818210ef9e048824205c08b9c_8.png)

There's really not a lot to text generally a lot of what you'll be doing is colour size and font weight There's a lot more than that but won't go into it Probably a more fun one is playing around with background image background image is something you'll generally apply on divs So if I have a div down here and I'll give that div a class of like you know my my pick or something you know we've kind of explored previously how you can use CSS to。



![](img/3bff1ae818210ef9e048824205c08b9c_10.png)

![](img/3bff1ae818210ef9e048824205c08b9c_11.png)

I'll leave that alone for now。 But like how you So how you can use H to include an image。 So like。

 let's say a look up， you know， mini rabbit or。Yeah， what's a cute， tiny rabbit。

Yeah so let's say we've got like a tiny rabbit like this then you've probably seen previously that。

 you know， we can do something like say image source and we can paste that image in and you know there's our image of the rabbit it's now on the page and we can play around with say you know the width is 400 and make it a little bit a little bit smaller like that but a really common thing you won't want to do is not actually just。

😊，Put that image of the rabbit on the page。 But you'll actually want to kind of use that image as a background for some text。

 So let's imagine here that I have this， this div。 And I'm like， even betterty， you know。

 let's take this text and let's put this text inside the div。 So now we've got this div down here。

 And let's play around with some of the divs properties。

 So maybe the div wants to have a width of 300 pixels。 Maybe it wants to have a height of 300 pixels。

 Maybe it wants to have a。Background。Color of。Green that's going to look really bad。

 that looks horrifying。get rid of that line height thing。 There we go。 So I can't even look at that。

 Maybe let's try blue something that doesn't。That's manageable so let's say we've got this deal here。

 but like。😊，Background colour is already a whole new property that I mentioned。

 but let's say you want something else like you actually want a background image Well you can actually give it a background image by passing in a URL。

To that background image。Property and now instead of being blue， it's actually going to be a rabbit。

We need to play around with these background image properties because as you can see here。

 the rabbit kind of like what's wrong with this background image。

 What's actually wrong is that all background images will try and display at their natural size unless you specify otherwise。

 So， for instance， here， I actually need to now say that。The background size is。 and you think， oh。

 I don't know what background size should be。 So I Google it。 It's like background size C S S。

 And we'll find out just for a quick Google that。I know how to do this right。

 but it's like I'll show you it's like the two values syntax， the first values。

 the width of the image， the second values is the height， Okay， so let's say I want the background。

The background to be。400 pixels by 300 pixels。And it's like， okay， well， there's the rabbit。

 Now obviously my actual background is 300 by 300， so I might need to do something like that or I need so my actual div or I might need to change the div so maybe the div I'll make it 400 pixels and I'll make the background image 300 pixels like that。

So now I've got this kind of cute little rabbit backgroundy thing like this。We can do more with this。

 but we'll kind of discuss that in another lecture in terms of the layout。

 but I just want to show you a lot of this stuff keeps going deeper and deeper。

 Let's imagine that the background image size is only say 200 by 100。

 What's going to happen It's actually going to repeat itself like this Well how do I tell it how to not repeat。

I go background。Repeat and I write no repeat like this and now it won't repeat or。I can say repeat Y。

 which will repeat things vertically， or I can say repeat X， which will repeat things。

Horizontally or I can just say repeat， which will repeat things always or I could change my background size to be you know 100% 50% which will kind of give it a funny look you know you can really do quite a lot of different things with it and。

You know， a lot of formatting properties and we'll see this in future actually have these kinds of compound。

Definitions where instead of writing things out like this where I'm like background image。

 background size， background repeat， I can actually write out a shorthand version of it。

 or I'll say like actually， you know what， the background is that URL， No repeat 100%，50%。

 Now I might have the ordering of this wrong。 Let's see if I do。Yeah， I do have that slightly wrong。

There's a particular order that you need to follow。

That order you can find just by like CSS background。 So if you say go look up the actual docs。

 it'll show you the go。 It's like。Where is it background green， Yeah。

 so you can see how it's like background is URL then repeat Y So you need to kind of get these things right in this particular case。

 for instance， we might just say you know the background is 30% if you have it kind of 30%。

 20% you see these have different kind of effects but if you actually pay attention。

 I haven't got this right here， you notice that the image isn actually getting bigger and smaller it's actually moving across because one of the other properties that we haven't explored like let's say we start this you know100% is that you can actually move the background position because obviously this image of the rabbit right now extends way beyond the frame。

But if I say create a background position of 10 pixels，10 pixels。

 what that actually does is it offsets the position。 So like every background image starts at0。

0 up on the top left。 And when you say 10 pixels 10 pixels。

 it kind of shifts it 10 pixels in and then 10 pixels down and you do all kinds of crazy things with this。

 for instance， you know， you might think oh， that's kind of useless but you can actually go negative pixels here So I could actually start moving the image across And I could start being super creepy by like making it negative 500 negative 500 And I'm like。

 oh， that's cute， that's the rabbit Can I make it negative 600。😊。

Maybe bring it in a bit and then maybe make the negative 400 to bring it down。 There you go。

 That's a cute background。 So the actual background property。Expect something more like this。

That's like the kind of compound property here so it's like the URL， the repeat。

 the background position and you'll see a lot of these compound properties have really specific expectations in terms of like the ordering you pass things in and again we'll explore a few more of these as we go on I think font actually has a similar one so if you look up CSS font。

The font property typically you'll see that similar thing here like in this case it's specifying italics more caps bold。

 the font size， the font family that's another example of these I don't think they're called compound properties I just call them compound properties Yeah so the font property is a shorthand property for the style variant weight size family。

So all that information is really there So if you're like I don't know how to do it。

 you could just come here and be like okay well style is italic variant I don't have weight as bold size as to a family as aerial okay there's my there's my font and now that will behave like that So that's certainly very useful Another case that you'll see this is for border So for instance you have border width might be a pixel border style might be solid and border color might be black。

Like this。So you see you've got this nice little black border there Obviously I could make the border much thicker。

 I could make the border instead of solid I could make it dashed， which is like little lines。

 I could also make it do dotted if I want to like this， but there's a shorthand property as well。

 which is with style color， three pixels。Doted。Black。



![](img/3bff1ae818210ef9e048824205c08b9c_13.png)

Like that。 So border our background。 these are all like nice ways to kind of add style to your divs as a few other fun ones。

 like for instance， everything has a box shadow a box shadow takes in four properties typically which is like if you imagine there's an element。

 there's like a shadow behind it that shadow is gonna have a certain X offset a certain y offset and then it's gonna have a certain spread of the shadow they call it and then it's gonna have a color of the shadow。

 So for instance， let's say I do 0，05 pixels black for a black shadow。

 let's have a look at how this turns out。 and you can actually see that little slight shadow there。

 So there's00 means a shadows right in the middle。 but you'll see if I come down here and I go say 10 pixel 10 pixel that's now 10 pixel across 10 pixel down。

 the shadows now down there。 And this five here is kind of how you know。

 when you like have like a flashlight or a torch and you like as you pull it further away。

 the torch gets weaker but it spreads out like the light whereas when you bring it really close。

 it's like really tight and really looks just like a solid shape。It's kind of the same thing here。

 So if I go to 15 pixels， you'll see that the shadow is bigger， it's more spread out。

 And if I do something big， like say 35 pixels， it's like a super spread out shadow。 And similarly。

 I could move the shadow kind of up into the top left by going negative when it comes to the spacing。

 So now it kind of looks like the image it's coming out this way off the page。

 So lots and lots of ways you can configure that。😊，你儿。唉。TheseThese are all different types of。

Foratting obviously you could also actually do things like you could set the color here we've previously talked about inheritance so you don't need to have the text be read you could actually just have the P B blue and all of the text inside of it will inherit that property for instance if you'd like to so that's just some basics of the background image we cover position size repeat image。

You know here go you've also got other like for the background size。

 you don't have to specify percentages like I did， you can also specify with keywords like contain and cover so that contain will scale the image to fit the element cover will scale the image as large as possible and crop the overflow part So that's really useful so let's say we come back here and we're like well okay that was the size that was the position we had can we add contain here。



![](img/3bff1ae818210ef9e048824205c08b9c_15.png)

Okay， well， let's try and do that separately。 background what was a background position size。

 was it positional size， it was。

![](img/3bff1ae818210ef9e048824205c08b9c_17.png)

![](img/3bff1ae818210ef9e048824205c08b9c_18.png)

Size， okay。Background sizes contain。There we go。 Let's maybe try and get rid of the position。

There you go。 so that's what contained does is it tries to to stretch the image out there and then we got cover。

 which so remember contained we'll try and。Kind of fill it。

 but include the whole image and cover will try and remove all of make sure everything's covered and it will profit slightly。

 So that's a really nice shorthand way。 And you'll often see this with CSS like you're gonna to learn a bunch of CSS now but what CSS can do in five years is very different。

 So in the past， for instance， containing cover didn't exist they were added in because people realize that there were tons of developers who were constantly having to like figure out what percent you know it's just like we were doing before where we're like we got to make it 400 by 300。

 So covers really nice， it just kind of plops it in there and you'll see what happens with cover if I make the high 200 it will just kind of keep doing very smart things to me if I make it 500 it'll grow the size of the image that wouldn't happen with what I had previously。

 for instance。

![](img/3bff1ae818210ef9e048824205c08b9c_20.png)

So that's really that's really helpful and interesting。

 We did talk about background position already， but we mainly talked about background position when it came to。

😊。

![](img/3bff1ae818210ef9e048824205c08b9c_22.png)

Like we had before， it was negative 500 background position is mostly。Relevant when you have a。

Background that's smaller than the element itself。 So， for instance。

 let's say that I have a background size of 50 pixels by 50 pixels。



![](img/3bff1ae818210ef9e048824205c08b9c_24.png)

So this little rabbit's going to be really tiny。The background position。

Which we were playing with before with percentages， right。

 we were like negative 500 pixels and stuff like this。

 The background position you could also say is just like top center or something。

 which will put it in the top or the center center。Or the center right。

And this is really important because you know， for every CS property， like， CS background position。

 you will find that there is a whole bunch of different values you can have。 And then quite often。

 the values aren't just all left right。 There's many different ways that you can express those values。

 So you can just say top bottom left right or you can say percentage values as to like how percent in should you move it。

 or you can give it absolute things in centimeters or em or pixels。

 or you can be super specific and say I want it to be 10 pixels from the bottom and 20 pixels from the right。

 You know， there's just lots and lots of different ways you can express things。

 So there docs are really important to read if you want it。 But most of the time。

 you'll probably find a way of expressing yourself。' that's pretty okay。

 and you'll just get used to that。 For instance， pixels or percentage。

 and it really depends on what problem you're trying to solve at the time。

 But this gives you like a really quick。Kind of overview of。Some CSS formatting properties。 again。

 there's a lot more。 You can just go and look up CSS properties and you will see an absolute mountain of them and it's important to look at the docs too because not all of these properties apply to all of the elements In fact。

 there's a ton here that don't really apply to a lot of things and we're going go through more in future lectures but you see here you've got things like letter spacing line height。

 we covered those list style list style type that's to do with unordered lists and stuff so you can go and change the list style for list margins we're going to talk about in the layout lectures outline color outline width we've also got overflow X。

 which is essentially what you do if your text flows too far over the side and horizontally or overflow Y because sometimes you'll have divs or spans that are a certain size but the text that's entered gets too large。

 you cut it off。 you use dot dot dots like there's a lot you can the on there position。

 lots of layout staff text there's a lot of text here text。

L position you can move the position of the underline for instance。

 you know we talked about that text decoration there's text shadows so we can add shadows to text too if we'd like the oh that's a cute shadow right so we look at an example。

😊，Where did they have the code for it， CS was very complicated， isn't it， So， you know。

 say we take this one。 And we say， well， we want my blue text to have that kind of text shadow。

 that's very retro， isn't it right this is just a whole bunch of shadows all layered。

 So it's demonstrating here that you can actually layer shadows。 And then you think， oh my God。

 does that mean I can layer layer shadows elsewhere。

 I can have like a yellow shadow on my box as well。 And it's like， yeah， wow， you can。

 you can actually have like these interesting yellow and black shadows。

 So I've got like a black shadow up in the top left and then a yellow shadow down in the top right。

 it's like， oh wow， it's just like a bottomless pit。 You know。

 there's things you learn every single day and you'll never stop learning。

 unless your' full time job for years， is's gonna be CS， you'll always be uncovering you things。

 So let's put a hot there。You can format many things in many beautiful ways and many unbeautiful ways all you need to do is a quick Google bit of experimenting and。

😊，You know， sky's the limit。 Hi， sorry for the abrupt cut。

 but there's one more thing we have to talk about before we wrap up， which is color。 So far。

 everything we've been doing with color looks like this。 It's been saying background green。

 And we've just been using words to describe the color。

 But there are other common ways that we describe color。 One of the obvious ones is the RGB。

 RGB is where we give it。😊，3 different values from 0 to 255 that represent the red。

 green and blue color。 For instance， we might say we want 200 red，100 green，0 blue。

 The higher the number is up to 255， the more kind of potent it is。 So this means like really red。

 kind of green， not blue。 And what happens when you get really red and kind of green。

 You get this kind of like funny。Orangey colour like this。

 The other way to describe backgrounds is by using a hex code。

 and a hex code is actually the exact same thing as RGB。 It's just represented as hex。

 So if you would ask yourself， okay， what's the， you know， hex for 200。 It'll say C 8。 So， you know。

 you go right C 8。 And then you say what's the hex for 100。 Well， it's gonna be like 6，4。 Obviously。

 And then 0，0，0， So these two things are actually completely identical and just slightly different ways of representing colors。

Like， you know， so that's the same colour。 Now you might be thinking， well。

 that was quite a big jump from， you know。Aie， you know。

 black white purple to like all these crazy codes， the good thing is you don't really have to worry about figuring out what they are because you can just go online and use colour pickers。

😊，Coour pick are tools like this where and you know you Google a million of them。

 They're in like lots of different websites。 you can just kind of find a color like that and be like that's a nice color。

 And then when you click on it， it'll show you， that's the Xcode。 that's the RGb code。

 There's more things you can do like Q saturation lightness。 I think that is So you're like yep。

 that's a nice color。 And then I come along here。 And then I'm like oh cool there you go done that's the color I want So if you don't want these kind of socks stand blue。

 black， purple green yellow， you can go and actually use one of these many many know255 to the power3 colors that exists So go play around lots on Google。

 never gonna be hard to find。 But hopefully that makes things a little bit more fun。 And thank you。

 hopefully you've learned a lot about formatting today。😊。



![](img/3bff1ae818210ef9e048824205c08b9c_26.png)