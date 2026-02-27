# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p72 -73-COMP6080 - CSS 🌝 z-index.zh_en -BV17RXGYuEaM_p72-

Hello， I'm Maria and this lecture is going to be covering the CSS Pro Z Inex so by now you should be pretty comfortable with positioning elements on the 2D plane on your web pages so by manipulating the X and Y values using the position top left bottom and right CSS properties so for example something like this where we have a 500 pixel by 500 pixel red box and then if we add the position relative and left 300 pixels CSS property we can see that the box moves 300 pixels to the left in this X and Y plane。



![](img/d60db0238fdfa4771e20a3df02aff170_1.png)

![](img/d60db0238fdfa4771e20a3df02aff170_2.png)

![](img/d60db0238fdfa4771e20a3df02aff170_3.png)

嗯。What you may not know is that the web page is actually more of a 3D plane and there's this third Z axis。

 so we can use the Z index to alter the Z value for elements which controls their vertical position on the web page。

So by default， all elements will be statically positioned so they have the position column static property and they will all be rendered in the same layer。

 which is what you've seen and been doing this whole time， however。

 changing an element's position value from default to for example。

 absolute or sticky or relative will alter the layer in which the element is rendered。



![](img/d60db0238fdfa4771e20a3df02aff170_5.png)

So to demo what this actually means， we have the same red box from before and it doesn't have any position attribute。

 so we know that its position is static， the default value and then we have this blue box here which has position absolute and you can see its position 300 pixels from the top and 50 pixels from the left。

And what we can see is that it's actually appearing on top of the static red element。

 And the reason for that is because we set position absolute。

 the blue box's Z index value defaults to0， which is actually above the static layer that the red box is being rendered on。

So for a summary on what said index is， it's a CSS property which allows you to adjust the vertical layer that a positioned element is rendered on and this point that it's a positioned element is very important so it can't have the position static property。



![](img/d60db0238fdfa4771e20a3df02aff170_7.png)

Setting a higher Z index means that the element will appear as though it's closer to the viewer of your web page。

 so on the top level and then setting a lower Z index value will send it backwards in your web page。

 So think of Z index kind of like this feature that they have on Microsoft Word or PowerPoint Canva。

Where you can bring layers or images to the front or send them backwards。

So Z indexdex used to be more popular back in the day and it was used often in mods and pop ups and dialogues。

 things that had to appear on top of content so that the user could interact with them。

Or however now it's generally not used as often so you may be asking yourself why are we watching this lecture the reason that I'm doing this lecture is because a lot of code bases actually still use Z index and they have a lot of elements which have this property and most people don't actually realize that Z index only works on position elements so i。

e。 not the ones that have static。Position。So I've seen Debs Chuck a Z indexex randomly on elements that they want on the top and then wonder why it doesn't work so the question to why why are we learning this it's very helpful to know the basics of Z index and it is used pretty often so you may encounter it in your front end work。

So as I've said previously generally now we don't use it as often and I would actually argue for avoiding the Z index as much as possible and the reason for this is because if you have a lot of elements with this property。

 you can often get stuck in this loop of increasing one element Z index and then having to increase the Z index of other elements that have the Z index property so looking at this image on the right we have as I've mentioned the static layer。

And then zero，1 and you can keep going， two， three， four， etc。

 and then similarly you can go into the negative numbers so you can have a negative one negative 2。

 negative 3， and these will all render under the static layer。嗯。

So as an example of why I would avoid Z index， let's say we have one element with the Z index  one。

And maybe five elements with Z index 2。 So they're above this layer。If I want to change that element。

 the first element to Z index 2， I now have to go and change those other five elements to Z index 3。

So that they render on top of the one I initially changed。

So you can see there's this constant having to change everything because Z indexes relative to the elements。

 to the other elements on the page。So ideally what you would do is use that index on maybe one or two elements on your web page and then make use of the default rendering order provided by the browser and HTML to organize the other elements on your page so we'll go through a real life example later in the lecture。

 but I thought I'd start off with a pretty simple example just containing four divs。



![](img/d60db0238fdfa4771e20a3df02aff170_9.png)

![](img/d60db0238fdfa4771e20a3df02aff170_10.png)

Okay， so I have an example here。 I have four boxes， one，2，3， and four， red， blue， orange and purple。

 and you can see they're just divs。With height 300 with 3 hundred and just some padding so that the number isn't right along the edge。

And I basically want a demo， like a really simple Z index example。😊。

Let's suppose that we want box4 to be on top of box one。

So we already kind of know how to do this with position absolute。嗯。Absolute。Oops can't spell。

 And we set maybe top 50 pixels。So we've seen this already in the slides before where we can move box4 on top of box one。

And the reason that this is happening is because remember red， blue and orange。

 the three boxes here are statically positioned and the purple box is not statically positioned and hence it's on a layer above the other three boxes。

Now， we can actually apply this to。All everything except the red box。

 and we can see that they kind of disappear， right。 So we've applied position absolute to blue。

 to orange and to purple。And you can see only the purple one seems like it's rendering。

 and the reason for that is because of this order here。So blue。

 orange and purple are all rendering on the same layer， which is the zero width layer。

 and they're rendering in this order。 So blue renders then orange and then purple。

 So because of that and because they're all in the same position， purple is on top。

So what we can actually do is maybe。Just demo this， left 50 pixels。left one hundred pixels。And left。

150 pixels。So you can see all three boxes are there and they're all on the same layer。

The zeroth layer。 And they're just on top of that red box， which is statically positioned。So now。

Here's where Z index comes in。 Suppose we want the blue box to be on top of the orange and the purple box。

嗯。What we can do is apply Z index here。So right now they're on the zeroeth layer。

So if we set a z index of1， which is greater than0。It will appear on top。Similarly。

 for the orange box， we can do the same， we can set set index2。

And it will be on top of the purple box， which is Z index 0。The blue box， which is Z index 1。

 and also the red box， which is the static layer。And then again， with purple。

 we can set Z index to three and now we have a static layer， which is the one。Z index 1。

 Z index 2 and Z 3。 And you can see they're rendering on top of each other as expected。嗯。

If we apply z index to the red box。Nothing will happen， so we can set Z index 4。

 which is greater than3， but it's not rendering on top of the other three boxes because， again。

 it's statically positioned。 So we can only apply Z index if the elements are positioned。

 So if they have absolute relative sticky， basically anything other than static。

So I'll delete this line because it's not really doing anything。

Another point to make is that we can make these numbers as large as we want so we can set this to like 30。

000 and it's still greater than two and it's still greater than one so it'll be at the top if we set this one to like 30001。

nNow this one will be on top。So it's just looking at。Basically， the the numbering of the layers。

 So just think of each number as its own layer。 And if it's a higher number， it'll be a higher layer。

So like we can go up up the positive numbers， we can go down the negative numbers。

 So what we can do is set all the z indexes to negative one。

And what we'll see is now they are positioned underneath this static default layer。

Which also can be really useful if you want to do some。Fun layering， I don't know。

 maybe a hack drop shadow。I can't really think of any like too many use cases for this。

 but again useful to know that you can go negative and say we want the purple layer to be at the very bottom。

 we can set it to negative 10 and now it's rendered underneath the red， the blue and the orange。

So that's just a really simple example of Z index in action。

 and now we'll go into like a more complex use case， something I've encountered in my dev life。Okay。

 so here's my next real life example， it's basically a knockoff Google calendar。

 so we have Thursday2nd of September 2021， we have all these slots for hours and then we have a couple of elements on the page we have this right arrow line and an event called Work。

So if we look at the starting code for the HTML， we just have a date holder。

 which is basically this box at the top which contains the words Thursday and second of September 2021 so that's that and I've applied a couple of styles to them just to the font and their spacing inside the box so font weight bold and just the size。

And then we have a div class hour breakdown container， which is this whole section here。

 all these lines。Just using。A repeating linear gradient to achieve these minds。

And then we have a now indicator， which wraps my right arrow and my now line so。We have the now line。

 and we have the right arrow and the goal of this is to basically indicate the hour that I'm in。

 So I don't know if you guys know Google Calendar， but they have a red line that throughout the day just slowly goes down the screen depending on which hour it is。

So that's what we're trying to mimic。 And we have this like little red triangle for some extra complexity。

 I suppose。 And then we have this final div at the bottom。Which is class work。

 And it has inline styles， which isn't great。 But this is what you'll see in existing code bases as well。

 Like a lot of random just。Mix of both styles， so。We have that and it just has a background color and a height and a width。

So what my goal is is to basically move these three elements， the triangle。

 the line and the work box onto this div， which is titled our breakdown container。

 So I want these three elements to be on this page。

 and I want the now indicator to be maybe 25% down work。嗯。

So this obviously has to do with layers because we want the hour breakdown to be underneath work and we want the now indicator to be on top of work。

So what we can start with is actually just moving work on top of this div。

 So if we add the position absolute。Value。We automatically move work onto the zero if layer。

And what we can do is just say maybe top to 40 pixels。So that moves it 240 pixels from the top。

So it's already above the statically positioned our breakdown container because of the examples I've given before I explained it。

 so zero is above static。Now we have this arrow line here。嗯。What we want to do first of all。

 is maybe let me zoom in a little。Align it so that the line is actually coming out from the center of the triangle。

嗯。So what we want is the now line。We want to move it up maybe 10 pixels or so。

 So what we can do is we can also position absolute。And do something like bottom，10 pixels。Oh。

 that's not what I wanted。So what I did is I moved at 10 pixels from the bottom。

Because I position absolute， I meant relative。So I want it relative to its old position to move 10 pixels above that。

So you can see now it's kind of there。 if we want to really be pedantic， we could do 10。5。

So now we've got a good triangle with a line coming out of it。😊，So now we want this element。

 which is wrapped in the now indicator to move above work。

So what we can do is we can now indicator and we can say position absolute， right？

And let's say we move it 280 pixels， right？And it disappears。

 And the reason for that is similar to the work。We've moved position， absolute。

And we moved work box 240 pixels from the top。And we move the now indicator，280 pixels from the top。

Which means it's somewhere here。which is under the work container。

Because the work container appears after the now indicator in our HTML。So what we can do。

Is just set Z index to be one。And here we go， we can see it's now spawned。Above the work。Contain。

And that's kind of a real life use case for Z index。 General， you draw lines or。Yeah。

 any kind of line or maybe some container on top of your existing U i it will generally have this Zen index property set。

And like I said。We usually want to avoid it。 So， for example， for work。

 I didn't set a Z index because if I had， if I had set a Z index to like 5。

I would have to set my now indicator to6。Whi has this cascading effect that I was talking about earlier on so we generally try and avoid setting Z index and just using the static layer and the zeroeth layer but then in some cases such as this where you have a line and it's just one element and it doesn't impact anything else then it's a good idea to use Z index to kind of just bring it up a layer。

And so that it renders on the top。And yeah， that's kind of all the content that I have for this lecture。

 I hope it was useful and you've learned something。 So thanks。😊。



![](img/d60db0238fdfa4771e20a3df02aff170_12.png)