# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p15 14_CSS中的图像颜色与链接.zh_en -BV1Lr421A75d_p15-

![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_0.png)

![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_1.png)

So now we're going to just talk a bit more about how we do images， colors and fonts。

 and then we'll start of wrap up CSS。And so。I don't know。When I fell in love with Hm。

 I didn't fall in love with the Web right away。 I didn't think it was all that great。

 It was just a way to click things differently。 We had other things like Gopher that allowed us to click stuff。

 But when we saw inline images and the ability to wrap text around images that rocked my world。

 And part of the web that was so successful。 It had to do with vanity to some degree where you could make a page that is you。

 And there is a page of me， which makes me very， very happy because you know， I'm so vain。

 I probably think this page about me。 And so one of the features that I love the most is this wrapping。

 So I love how it does auto， So as you move things back and forth， that auto lays out。

 and I think that's really cool。 I know some people want to lay out pixel perfect。

 But I love the notion of larger and smaller screens response of adaptive。 I think that's essential。

 We can argue about that later。 But what I love is the ability to float an image to the right and then have。

😊。

![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_3.png)

rapping happen around it Okay and so here we go， let's show you how to do this right and so we'll talk about the nav bar later but for here what we have is this image and so you can see that this image in the layout comes right before the header1 so the image would normally be right right there basically but then what we do is we say with the style we say float right。

And that says hoist it out of the normal flow and then float it to the right margin and then use it。

As a justification boundary。And so that pulls it over here。

And so that's why this sort of comes up here。 there's no image anymore。 And now this lays out here。

 Now the other thing that I've got is a margin of 1 m。

 and so that that gives me the margin of 1 m gives me a little space right here。

So one of the things you do in CSS is you talk about sizes and you've got pixels and sizes and the M is actually a really useful size。

 and so what the M is is the width of an M in the current font size and these fonts can go up and down as you zoom your page in and out and so what it really says is I would like。

Space that's equal to the width of an M。 So you kind of see that this is an M of space this way and an M width actually。

 sort of the M is sideways here。 and M width of vertical space。

 And so it means that if you change this and zoom in in and out。

 this space will change correspondingly。 So that's one kind of way to say one letter's width。

That that is taken from the size of the surrounding text。 So that's， I think that's really cool。

 I mean， pixels were dangerous and。Font sizes were dangerous， but these Ms are a great relative size。

 So float right pulls the image， shoves it over， changes the thing。 Now， if this was long enough。

 you would see that eventually it would start wrapping here。

 but you can also force it to clear the float and there's an attribute。On any tag you want。

 but I use a brake tag， which is， you know， break tag is like go back to that new beginning there。

 Cl equals all says whatever that float was， if we haven't already sort of gone beyond it。

 the next thing， this next paragraph here has to start at the left margin。

 even if it creates a little bit of white space。 So that's how that white space got created here。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_5.png)

The hanging indent was effectively cleared， and so this thing to be this line here had to be forced back to the left margin because of the rank clear equalal。

So that's a floating image which I think is really nice and I love it because I can resize this and it just resizes automatically and if you resize it really bad。

 it'll actually pop it up so that this picture is on top and I think it's important to do those kinds of things because you increasingly we have narrower and narrower ways to view these things and so just imagining that everything is really big and broad。

 it's not always that way that we're using a super large screen monitor。

 it's great when you can use them but it's nice to have a website that responds to changing widths quite naturally。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_7.png)

So colors so colors are important。 There is a color attribute。

 There's a background color attribute and so they have a number of built-in colors。

 These aren't necessarily the most beautiful color but I love to use them to do things like you know I'm trying to say like what happened is how come that little tag is not working or that CSS rule is not working。

 I'll say like BG color red and then it goes right I'm like oh， I hit the wrong one or something。

 And so these colors aren't really great for graphic designers。

 but they're great for developers are just one I like have something standout So you know what you're doing right so these colors are like aqua。

 black， blue fusia etc cea。 and they're the default ones that every browser supports like I said。

 they're not really officially gorgeous now。😊，There's also a way for any place that's saying color to have an advanced color。

 and you see the advanced color by this pound sign and so what this really means it's a hexadecimal。

 hexadeciimmal， you can go look that up， it's base 16。

All it is is a number system that has 0 through 9， and then A， B C， D， E， F。

 So F is actually equivalent to 16。 And so this is like the number 1616， except it's only one column。

 So hex is a way to。To sort of in a more dense way represent numbers。

 but that doesn't matter FF is the biggest number and0 so0 through F。

 there are two red numbers and this is these are 16 times 16 so this is really 0 through 256 each one of these is somewhere between 0 and 256 so that red is 0 through 256 the green is 0 through 256 and the blue is 0 through 256 and in a sense what we're capturing in this little thing is like what these sliders where you're dragging back and forth if you I mean 255。

 not 250255 right and so that's all you're doing and then you're changing this color by combining the red green and blue to the level that you want to combining them together。

And so there's also a set of colors that are just three where you say pound sign 245。

 this is the red， it's like 224455， and so that sort of reduces the color space and so you can have three hex digit colors。

 which is red， green， blue， but it just is sort of duplicates those things。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_9.png)

And it's a way to use fewer colors in the early days we used to worry about web pages that use too many different colors because the computers couldn't represent as many colors。

 but that's probably 15 years ago since that actually was a problem。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_11.png)

![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_12.png)

Fats。The default font in 1990 was Time Roman， partly because I think。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_14.png)

When Tim and Robert were inventing the whole thing。

 they thought of this as a highly respectable thing and were writing documentation like journal articles because it was physics。

 I mean， they were trying to represent physics documentation。

 So they just picked Time new Roman or maybe that was the default of whatever next computer they happened to be using。

 I don't know how I just know。That I hate Times New Roman。

 And so I just the first thing I do is switch to some kind of a s serif font because I think that just looks more modern unless I'm writing a journal article or a New York Times article。

 that's where Times New Roman comes from I think。 And so I just am always changing my fonts。

 And so the font family is one of the first things I always do in any CSS。

 And so fontt family and there's a whole other things like font size。

 And so you look at font families and it's kind of a little bit different because like if you look at margin。

 it's a width， it's really easy。 But in a font， you have a list。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_16.png)

And what happens is your list is sort of your preference in priority order as the graphic designer and you basically say。

 you know if this is trevicheyMS， I think that's a Microsoft font and then howvetica might be a Mac font an Arel I think might be a Microsoft font so you're trying to hope to find one of these things and then what's really cool is there is always a fallback。

So it says every browser must have a serif font， a San serif font monospace cursive in fantasy。

 cursive and fantasy are kind of stupid because they're kind of not predictable。

 but these three are super useful so you can always sort of fall back to some browser supported San serif。

 serif font or monospace font， and that's why you see these things at the end because these are the fallbacks。

Font size， you can have relative font sizes。 These are a little dicey。 You start at medium。

 you can kind of go down and you can go up。 Fo tend to prefer like 12，12 pixel height。

 things like that。 You can set the fonts weight， bold or normal， normal or italics。

 The reason these two things are separate is because you can do both bold and italics。 You know。

 some blah， blah， blah， blah， bold。Well， I can't really。

 I don't really know how to draw bold attacks， but you get the idea。 You can do both in italics。

 So it's not just one of the it's not bold italics or normal。 It's bold or normal， normal or italics。

 And so you can apply both of these things。 You can do things like cause everything to be underlined。

 The default， of course， is none。 You can have overline or line through and you see this a lot。

 People use line through when they're showing that they change something。 okay。

Now going back to font size pixels。 So it turns out that pixels。

 it's not like the most popular way to do it like 12 pixels tall because we can zoom our screens in and out。

 especially for accessibility on different devices and then the 12 pixels would be the same。

 But what happens is is most browsers conveniently ignore the pixels And if you're zooming it in。

 it says oh 14 pixels and then it just makes them bigger because otherwise if it really literally took your 14 pixels literally as you zoom pages in and out。

 then that 14 pixels would stay the same which is really not what you want。

 So kind of if people get sloppy and use 14 pixels， it works this is kind of zummable。

Ft size is kind of a hard thing。

![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_18.png)

Links again the whole beginning of this came down to hypertext right Hml hypertext market language and so we've got some interesting styling that we can do for links the default was blue and underline anything that was clickable and purple and underline anything after you got done clicking and it turns out that if you like look at Google searches。

 they still use this styling because it turns out it's。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_20.png)

It's not really good for every page that has every clickable element。

 but if you're actually making a list of things that are actually clickable。

 it's not a bad convention and we just all use it。 and so Google searches style this way。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_22.png)

And and so， but you can in CSS control a lot of how the styling works。

 so you can basically say every anchor tag is supposed to be bold。

If if it's a link tag before you visited it， it's going to be black after you visited it。

 it's going to be gray hover， that means when you sort of come this is our little area。

 you come across and it can change color while your mouse is there and as your mouse leaves it changes color back and so you can have a bit of animation and again part of this is to attract attention to the clickable places so you kind of come across it goes like pink back to blue right and so you can do that in this case I'm actually changing the background color changing the font color and taking away the underline active is not so useful。

It's after you've clicked on it while the next remember request response cycle。

 you've clicked on it and it's retrieving the next page。

 but it still is showing the old page during that brief instant， hopefully brief instant。

 you can actually change the color of the link while it's reading the next page which kind of is useful if it was gonna to be take a long time you can say oh you know it shows like it's kind of a red or something So don't click this because you already clicked it once。

 But most of the time the page is gone in a blink of the eye so you would so you don't really use it。

 but you can do it。 So this is like the state of a link right you can style based on the link state。

 have I visited it or not， am I hovering over it， Have I clicked on it and that you can do。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_24.png)

IThink you can do this for almost any element， but it doesn't always work the same in different browsers。

 but the anchor tags， this works really， really well and so anchor tags are a big part of what we do。

 things like Google search results like I say， make really good use of all of these things to help you because what search results usually are is a bunch of links that you can click on you type web applications for everybody and then boom you got a bunch of links and can it helps you find what you're going to do and really augments the navigation activity in a user friendly and user engaging way。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_26.png)

So。I've got these samples at code CSss and web applications for everybody and they're all the really designed so that you can sort of watch them。

 you can look， you can inspect element right click and you can see all the CSss， et cetera， et cea。

 et cetera。 And so I'm not going to go through every single one of these in the form of a lecture but there's a lot of useful stuff here so I would recommend that you go all the way through this and just kind of get the basics of CSS So again。

 I just took you through a very beginning CSS It's wonderful I am not a graphic designer。

 but I so love to use CSs because I just kind of you know throw a little little padding somewhere or a color or or move something to the right or make an image larger or smaller or put put a little border around an image It's really quite nice and。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_28.png)

I can do the stuff that I want to do and then I can say as long as I don't get sloppy in my HTML markup。

 I can just hand it to somebody and then they can hand it back to me and say。

 look I really made your stuff beautiful and that's really quite cool and you got to think that this is also not done evolving we're at a pretty good point with HTML5 and modern CSS but it's going to keep evolving as mobile and other things happen and sometimes they're like oh you got to use this webki or Mozilla options to curve buttons now those have become standard but it's always kind of an evolving thing as we come up with better ways to represent our markup。



![](img/5a0b9cd2614fbc79e29a6e109b1c96b5_30.png)