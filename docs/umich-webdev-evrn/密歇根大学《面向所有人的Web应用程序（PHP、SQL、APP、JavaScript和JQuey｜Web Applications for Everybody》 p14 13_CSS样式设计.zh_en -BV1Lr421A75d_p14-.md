# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p14 13_CSS样式设计.zh_en -BV1Lr421A75d_p14-

![](img/84473f2aea6aa3d9e1d4864caae04ad4_0.png)

![](img/84473f2aea6aa3d9e1d4864caae04ad4_1.png)

So now we're going to start showing how we change our HTML so that we can use CSS So there's a couple of different ways that we can sort of reference CSS inside of our HTML first we can apply a CSS to any HTML tag using a style attribute。

 we can also take a style sheet right in the head of our document or a completely separate file the third one is really the most common。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_3.png)

![](img/84473f2aea6aa3d9e1d4864caae04ad4_4.png)

Okay， we take a look at this， we can take this paragraph tag， so this is a paragraph tag。

 and we can put a border around it， a red border and some border width， etc cetera。

 and so we see this style tag here， the style tag says。For this tag and this tag only。

 I want to make these set these parameters。 So border style solid border color red border width five pixels。

 And that leads to this particular thing。 Now， we ought to talk a little bit about the C and cascading style sheets。

 So there is style that is inherited， right， So the body style says we're going to do font family aerial San serif。

 And so that means from here down， Its font family aerial San serif。

This paragraph did not override this font family， so I could override it。

 I could change the font here to be like a fixed with font or something。

But because I didn't override the font family that means that the font family here is Arer because the default is like Sarah fontt Time new Roman look。

 And I do not like that。 So if make font family aerial everywhere。 But this， this is inherited。

 So that's the cascading part。 And it's sort of you can think of it is whatever we apply the closest one applies。

 And because we didn't change font family here， then we take the ones that enclose it。

 So this paragraph tag is enclosed in that body tag。

 And so the style comes into that particular thing。 But the key theory here is。

 is that style equals is an attribute that sets Cs on a particular tag and no further。

 So this next paragraph does not have it。 and the one before doesn't have it in the same example。

 this paragraph that's font family monospace。 the aerial would be inherited。

 But now we've overridden it。 And so this is aerial aerial aerial。

 but we chose to override the aerial in that particular paragraph。 So that's kind of cascading。

But it's all using the style equals and you'll get into interesting arguments whether or not you should use the style equals a lot or a little。

 You just got to be careful。 The most important thing is to not end up in a situation。

Where you're using it too much and saying the same thing over and over again Okay。

 and so you just sometimes though you just like say， you know。

 I want it red and I don't want to get too fancy about it。

 I just want it read and a story so you can also put the style rules in a header。

And so here's the head， remember the HTML pages have head and then a body head is metadata。

 one of the things in addition like title you can put in is a style tag and then in the style tag。

 you can just put CSS rules so you've kind of switched from HTML to CSS right in the same document right so this is very same document and so these just basically say you know go don find the body。

Paint that with this rule。 Find the header1 tag， Pain it with that rule。 And so if you look。

 there'll be no style tags style attributes down here。

 because we just know that we can make the header1， all the header ones in the document。

Be blue with that one rule。 And so we just hoist these things out from the tags up into a general thing。

 This is， is generally much better， right， If you want to make your header ones be blue。

 you don't want to say style color blue over and over and over again。

 That's what I mean by don't repeat yourself。 right， That's what I mean by don't repeat yourself。

 So you can put their style rules right in the header of the document。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_6.png)

A probably an even better way to do this because you don't want your documents to get too big。

 and especially if you have like a caching server， okay， that's too complex。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_8.png)

Is to put a link and then have style sheet and then have the file in another just a file of CSS rules So instead of putting them right here in the document。

 you put them in a separate file and then your document is kind of smaller and the fact that you're going to putting these in probably many different pages right so over and over and over again。

 so why not put the CSS in a separate file and pull it in every time you need it and the same CSS rules if we take a look。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_10.png)

Add it， it's going to do the exact same thing， right。

 it's going to do the exact same thing in there is a rule to make the header1 blue。

 It's the same rules that we had here except that those rules are not in the background document instead they're in a separate document。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_12.png)

![](img/84473f2aea6aa3d9e1d4864caae04ad4_13.png)

Okay。😊，And so here we have this stuff right and we pull this style sheet in。 I mean。

 this literally is it， but somehow this header has inherited rules that come out of here。

 right so the header is blue， so we have some other stuff， you know， links。

 we can oh that's just telling us what we got to do etc cea， the header blue comes out of rules CSss。

This is what the rules look like， but they're the exact same rules that we had in that previous example。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_15.png)

So the span of the div tags are two tags that we added to HTML at the same time that CSS was kind of like becoming the norm and so all the tags in HTML paragraph tag。

 L tag have what's called sort of predefined formatting rules。

 so if you just make a paragraph tag with no， you just say paragraph and paragraph。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_17.png)

It has some rules about like spacing and stuff and so there's all these rules and so what we needed was set of tags that did not have any default rules or default formatting so that we could sort of just add via CSS so the span tag is an inline tag and it's a way for us to grab a bit of text。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_19.png)

San and span and style it， but there was no default formatting for span。

 So you can say if you just put span around something， span。X，Y， Z。Slash band。That did nothing。

Itt doesn't change it whatever the formatting was as it came into here， same formatting here。

 etc cea， et ceter， the only time you do something is if you add a style to that span right so the span is a way to grab text and then paint it with some different set of CSS rules so span is an inline tag which means it doesn't even break justification right so it's just an inline tag like bold or italics or stronger emphasize。

The div tag is a tag that is a block tag， and the difference between inline tag and a block tag is that the inline tag。

Does not break justification， but the div tag does break justification。 Now you might think， well。

 the P tag and the div tag are very similar。 The big difference is the div tag has no default styling and the P tag has default styling。

 mostly space it has little padding that you know makes it so the paragraphs don't stick out if you put two divs together and you go div div div div div and you put no padding in or no spacing in they're going to kind of touch each other because they're going to be really close together you' like。

 oh， the paragraph tag has built in formatting but the div tag has no built in formatting And so you can kind of see this。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_21.png)

I put sort of one pixel。 and this is a common thing to do in CSss。

 I put one pixel borders around each one of these things。

 so you can sort of see the end of one div in the beginning of the other div。

 And the answer is there is no space in between。 whereasas a paragraph tag。 sees paragraph tag。

 We didn't do anything。 But the paragraph tag just kind of added that stuff right there。

 And so you see the paragraph start and stop， but there's a little bit of blank space that comes after the paragraph tag。

 So paragraphs have a default styling and divs do not have a default styling。 Also。

 you can nest div tags right， You can nest div tags and you're not really supposed to nest paragraph tags。

 I'm sure most browsers wouldn't care too much， but basically the div tag is designed to be nestable。

 right， And you'll notice that by adding this one pixel border， I do change the spacing。

 but you can see even in the horizontal。 there is zero spa in between these things。

 They're just like right next to each other。 And again。

 all this is emphasizing is that the div and the span。

Start with no formatting except the div does break。 the div breaks horizontal layout。

 It breaks as a justification， but the span does not break justification， right， just keeps on going。

 doesn't break justification。 but other than that， there's no padding， there's no color。

 there's no nothing。

![](img/84473f2aea6aa3d9e1d4864caae04ad4_23.png)

So。The next thing to talk about is classes and IDs。

 and so the idea is that we never want to repeat ourselves。

And so we have created this part of CSS is the creation of this class attribute。

 and the class attribute itself does nothing。 It just marks a set of distinguished。Tags。

 so you say class equals more space or class equals shout loud or ID equals third so ID so the difference between class and ID is you can use a class on more than one tag in a document and we'll see later ID is another one of these CSS attributes that we can use but you can only have one ID per document。

One tag with an ID attribute of third right， ID attribute of second， ID attribute of first。

 but we can't have two of them have first right these the ID have got to be unique across the whole document。

 but classes do not have to be unique。And also just hear this little bit of class right here。

 you can have more than one class， this is not a class called shout Lou。

 this is a class of shout and loud， and it means apply the rules for shout class and loud class to this particular tag and so if we take a look at this。

When we say body， that's a normal tag pound sign first， that means ID。

 So Pt sign says go find the thing with idea first right here。And paint that with monospace。

 we'll see this in a second。Second， we're going to make everything in the second div， which is here。

 we're going to paint that all green。So that's how I think of these is like and then go find all of the things with the more space class。

And then have a left margin 20 pixels and a right margin 20 pixels， and you go find all of them left。

 right。And so shout is going to transform it to uppercase。 loud is going to transform it to red。

 You could have shout by itself， you know， shout and loud are sort of independently applied。

 so this is going to be both uppercase and loud。And then you can even have cascading that says that within a tag that has the idea third。

 paragraph tags are're going to have a background color of red， so let's go find where that one's at。

So ID tag a third right here， ID tag a third， so that is。

 I guess we're not seeing a slash give there， but then a paragraph tag。

This paragraph is to be painted。With a background color of yellow。So you can see this is like。

Grab do， grab， do， grab do， and we're just able to do that， not that any of this makes any sense。

 It's just an example。

![](img/84473f2aea6aa3d9e1d4864caae04ad4_25.png)

So let's take a look at how that really looks right within the ID of third div of third all the paragraph tags R have a yellow background and so that was like I spray painted this yellow background on that a away you go right and so like the more space guys look at the more space right the more space applied to these two paragraphs and they sort of shoved in both on this side and this side because I did a margin left and a margin right to shove those both in。

So the div of second， which is a whole bunch of stuff from here to here， the div of second。

All of that。 it's actually all this。 So basically， we spray painted all from here to here green。

 But then we overrode that by a more local CSss rule。 This one is closer than this one。

 So because we're in second， we're supposed to be green。 But because of shout and loud。

 we're supposed to be red。And so this is red。 So red one here。 If you didn't have this。

 this would be green， but you have this thing that's closer。 the closer it is to the tag。

 the more power that it has， and that's how it overrides okay。So up next。

 we're going to talk about colors and images and fonts， and again there's so much to learn。

 but these are sort of the basics that I want you to know。



![](img/84473f2aea6aa3d9e1d4864caae04ad4_27.png)

![](img/84473f2aea6aa3d9e1d4864caae04ad4_28.png)