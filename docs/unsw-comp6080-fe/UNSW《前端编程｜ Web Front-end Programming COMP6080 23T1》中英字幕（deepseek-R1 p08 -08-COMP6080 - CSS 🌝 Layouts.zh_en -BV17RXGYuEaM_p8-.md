# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p08 -08-COMP6080 - CSS 🌝 Layouts.zh_en -BV17RXGYuEaM_p8-

Hi my name' is Hayden， and today we're gonna to be talking about CSS layouts。

 So far we've learned how we can use CSS rules to apply certain types of CSS formatting by one of the most common ways that you're ever going to interact with CSs is by creating structures on the page with H laying things out in certain ways and there are a few ways we can do this that are both kind of old school and new school but before we get into those including in the next lecture。

 we need to talk a little bit about the box model So every div you have on the page and a div is a really important stless component that we're gonna to be using every div follows a box model and many other elements do many other tags do as well and the box models are pretty straightforward idea you have your content here in blue that has a certain width and height and then you have padding border and margin around it and every single box has these same three things a border is simply as you'd expect。

 it's like putting a colored border around your element padding is everything between the border and your content and margin is everything outside of the border so we can go。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_1.png)

can kindd create our own box， if you will， or div。And play around with it。

 So if I have a div I that I'm just gonna to call box and inside of it。

 I'm going to ask the question。 what are frogs， I can come and style my box here with say width of let's do 100。

200 pixels by 200 pixels。Now immediately when I create this box。

 it doesn't really look like a box right， it just kind of looks like some text。

But that's because the background is transparent。 So if I make the background blue， however。

 what you will see is that box is now obviously 200 pixels by 200 pixels。Now， naturally。

 as we've seen in the formatting lecture， I could go and make the text if I want to white。

 making the text white would make that a little bit more readable， which is good。

But let's play around with padding border and margin。😡，So first thing。

 we looked at creating a border to an object we did one previously。

 it was one pixel solid black like this。Okay， now it's a bit hard to see maybe if I use a slightly。

Lighter color。 you'll see that there。 Okay so now don' now we don't need the white text obviously。

 but there's our yellow box with our background。 If we add padding to this say 10 pixels。

 it's going to add 10 pixels of padding between the element which is here and the out of box。

 And if I add another 10 pixels of margin or 20 pixels of margin you'll see that the box increases So you have to kind of imagine that the element is this whole thing around the not the element。

 know the div is the whole element around the outside here then there's a margin， then the border。

 then padding than the element you'll also notice that the background itself covers the padding area。

 but not the margin area。 Now why would you use the difference between padding and margin Well。

 margin is probably a lot more common to just kind of move elements around。

 but padding is useful essentially when you want to create space either between content in a border or when you want the background to extend beyond the content a little bit more So that's the box model it's really simple。

 you can't really do that with spans。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_3.png)

You can only really do that with。Dives， and the reason for that is the div is what we call a block element。

 even though it's a stless element， largely， it does have one basic style。

 which is that it is a block。 Now， a block is essentially a component that will always start on a new line and it will stretch to the full width of the container。

Right so you have and you can kind of see this with spans and stuff here if I go and make a let's call it a text like a class text or something and I'll change this I'll change this star box to a dot box because we might make a couple of them right So if I go and have myself a few boxes。

 And I'll just make the height a little smaller like 50 pixels so it doesn't take up too much space And then I come along and make a few spans and say that spans classes taxed。

We will see this is text。 and let me close the span。

 You'll see the difference between these two types of elements。 So when I load this page up。

 you'll see that a div is always interested in。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_5.png)

Taking up the full width， and you might think it's all taking up the full width it's just taking up that 200 pixels。

 but what a div will do is if your element is only some of the page in width。

 it will kind of margin fill the right hand side。 you can kind of see this I'm going to use the dev tools。

This comes up in another lecture， but you can see here that particularly if I meet this full screen。

 that this particular div here， where is it？

![](img/09a1cfcc5feeccb105f8c2571acc9c57_7.png)

You can see that there's the element， there's the padding in that kind of green color。

 the border and then the margin on the outside， but because it's a block element it moves the margin all the way to the end for us so that's what a block element does Now you can kind of make anything a block element if you really try as opposed to these span elements down here that don't take up the full size you notice when I look at these they just occupy their immediate space spans are not very versatile compared to divs which is why we generally only use them for text and you'll see that if I try and do fun things with them like say a width of 200 pixels a height of 50 pixels you know a background of green What's going to happen here is that。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_9.png)

in you know so this is called an inline not a block they kind of don't really care about layout that's why you don't really use spans for layout you mostly only use it for text because it kind of disregarded my width and my height here now I can make a span a block by simply saying display block now display block turns it into a block element and now I start to get interesting things like this and you can see that if I add a five pixel margin to it we have now some block elements and similarly I can make my div。

And in line like a span by doing that。 Now， obviously， that's crazy。 What just happened there。

 Now what just what like what went on， Well， the height and width were basically ignored and there was no pad out margin。

 So you still see we've still got the basics like padding and margin。

And the border these can all apply to both in line and block elements but we've lost in particular the like the kind of autofill margin at the end and the width is also kind of ignored so width and height are ignored and there's no margin pad out So what we've really done here is we've just kind of made a div a span and a spanner div which is kind of pointless but I mentioned earlier that you know spans and divs are stless components but you can kind of just imagine a div。

As an element with no styles that just is display block and you can imagine a span。

 that's an element with no styles with just display in line。

 So that's why they're kind of really commonly used because they're just two fundamental types with not a lot of opinionated styles but obviously you would rarely actually use display block and display in line in your CSS you can though that's for sure。

 Sometimes you might have paragraphs or something that you want to display block with them。

 I mean most of the time you'll probably see that paragraphs are display block。

 I'd imagine I've even checked Probably a good thing to check。 but that's the basics of。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_11.png)

Block elements。And you can go and play around with these in many different ways。

 but in line and block are the two main things， there's a few other types of displays you can use。

 but generally speaking。We just stick with in line and block。

The other one of the most other ones is the inline block。

 and this one's kind of interesting inline block is this like halfway point I might touch on it is like it will give you some of the block aspects。

 but not all of it。 So if I do inline block that's kind of Frankenstein middle ground what it does is it kind of gives you the width and height。

 but it doesn't block out the lines。 So you saw before that an inline element ignores width and height display inline block will give you a width and height。

 but it won't kind of start to finish on a new line。

 That's sometimes really useful if you kind of just want blocks to exist next to each other and not take up new lines。

 but they're the three like if you use block inline block inline。

 you'll get away with most things you need to do in this space。 whilst we're on the topic of display。

 there's also another display value that you can give the display key。

 which is none which basically means to hide something。 So for instance。

 let's say I come down here and I want to add a class to this particular block。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_13.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_14.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_15.png)

？What are frogs and that classes going to be hide if I give it a display of none that will hide the box。

 So display none is essentially how you hide stuff in CSS that might sound silly for now because you're like why would I hide something why would I write the job and then hide it Well。

 this will make more sense as we touch on Java and everything later。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_17.png)

So that's displayed none， but we also have a similar thing， which is visibility hidden Now。

 the difference between visibility hidden。And display none。

Is that visibility hidden will actually place it on the page with the right size It will just not make it visible。

 So you see here this actually， it's like it's here， but you know。

 it's like the Harry Potter cloak thing。 It's just like there's something there but you just can't see it。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_19.png)

The display nu actually removes it kind of like cuts the element off the page visibility hidden is probably not as useful as display none as you'll learn in later work and assignments display none is extremely useful with kind of being able to chop and change what's visible on the page but that's the basics of block the display tag essentially Now we're going get into a few of the simple ways to layout out。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_21.png)

Blocks on your web page。 we're going to be talking about float， We might。

 and we're going to be talking about position， and then we'll also talk about tables a little bit。

 maybe。So。😊，And they're kind of mutually exclusive。 They don't build on each other。

 They're just different ways of doing something。 So firstly， float， float is a very weird thing。

 And you should probably avoid it。 It's very old。 It's one of the kind of classic ways to structure a web page。

And what it does is if you take an element and you float it to the left or the right。

 it puts it to the left or the right of the container and it allows other inline elements to wrap around it。

 So like let's just play around with this a little bit so you can get the idea。

 So what that means is that if I come up here and I create a let's call it my floater。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_23.png)

And that floater is going to have a bunch of smiley faces in it。

And I go and give some styles to my floater， which might be， say wait the 50 pixels。

 height 50 pixels background as purple。Like that， you'll see our element appears that， however。

 if I float it to the left。Here's what you'll notice。Suddenly。It kind of just appears up and above。

 It's， it's really like you can kind of imagine a web page normally is this kind of like one。

 like one piece of paper where everything has to organize on it。

 But the word float quite literally means like imagine it floating up above and like sitting to the side。

 Now， I can also give these things margins， if I want to， like if I gave it 10 pixel margin。

 you'll see that it。It kind of pushed some things away。 And what you'll notice。

 and this is very weird behaviour。 and this is why floats have to probably generally be avoided is that it pushed the text aside all the inline elements。

 but it left the block elements there。So very， very odd。 for instance。

 if I give it a 20 pixel margin。Now， that kind of like keeps pushing that across。 Now。

 you might be like， what in the world is this useful for， Well。

 probably the most common classical way that floats were used before we had better。Tooling。

 I guess you could say， is that you might actually create yourself。

 say a sidebar and that sidebar might be a， you know， 300 pixel height。

 it might be a 50 pixel width you might float it to the left And then what you'll typically do is you'll typically have an element after that sidebar。

 and I'll just use styles here that might have a margin left of 50 pixels like this。

 And it might have a height itself of 300 pixels rest of content。

So this was kind of like how a lot of old responsiveness used to happen was you'd have your kind of normal。

 I'll make that background。Pray。Like this you'd have your kind of normal content here and you'd play around a lot with the margins you okay。

 the margin top might be 10 pixels too O， it didn't like that。That's okay。嗯。

You might have to give it a slightly larger left margin because of like。

 and then it gets really tricky because you're like， oh。Now。

 I have to like do 50 pixels for the floating left and then 10 pixels for its margin。 And like sure。

 you get this nice little page now where I have this sidebar that kind of floats with the page。

 That's really how that's the odd。 It's probably one of the more original ways to use float。

 But it's it's very cumbersome and there are just better ways to do things these days。

 but you'll still see float around a lot。 And in particular。

 float is actually used probably most commonly。 I don't know why that looked up blue fish That was weird。

 It's probably used most commonly when it comes to。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_25.png)

Pages that have these like elements like this here。 Not that's that's very floaty。 These things here。

 Not like they're just kind of chucked there and text just wraps around it。 So it's it's again。

 it's a really old school thing。 and it kind of makes sense for how the Internet used to originate。

 which was these elements kind of tucked away。 So you can see it when you look for it。

 but generally you're probably not gonna find an extensive use for it。

 The only other point with float is that sometimes for instance。

 you might have an element that is not the full。 oops that's not what I want。

 sometimes you might have an element that's not the full。😊。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_27.png)

Heightened you get this weird effect here also notice this gray box I did not have to specify its width because by default all devs are full width and if you restrict the width there will be that width plus margin padding out the rest of the side but if you kind of have this float scenario and you think you know what all these boxes here with frogs I want them to just exist below the float。

You can actually use this weird style called。Clear both or clear left or clear right。

 but clear both is pretty common。It will， it will kind of be like， allright。

 let's go find the floats。 Let's just like open， but to the bottom of them。

 and let's put the content underneath， so。Cute， but again would probably try and avoid a little bit。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_29.png)

A lot of the rest of this lecture， we have a few sides on position。

It's where most of the time we're going to spend comes from。

 And position is a really interesting property。 It's， it's， I would say it's still very。

 it's an old one， but。It。It's still used relevantly today you're probably not going to use it very much。

 but when you do use it you'll be like， okay， that's very useful。

There are four different types of positions that we can give our elements on a webp page。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_31.png)

嗯。I might just kind of。Push this stuff down a little bit。Yeah。So the four types of positions。啊。

You can either do static， relative， absolute or fixed。

They're the four and they're the four we're going to talk about now every single HTML element by default has a static position and a static position does not mean much very fancy。

 it means that the position is just normal the element just behaves。😊。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_33.png)

The static value is the default property for position and if you don't so you don't need to worry about static because we never really deal with it。

 But where things start to get interesting is when we look at the other three in particular relative。

 So a relative positioned element if you put position relative on a CSS selector We'll position the element based on the normal flow but it will offset it left right top and bottom compared to its default position So we can you know play around with this as an example if we'd like。

 might just comment this out so you can still see it Well let's say I have this div in here and I'm going to call it like outer and then I'm going to create another div inside of it called inner。

😊。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_35.png)

Like that。And when I get the outer， I'm going to just maybe give it a width of 300 pixels a height of 300 pixels。

And for the NR， I'm going to play with it and say that I want its position to be relative。

Let's see what happens here。So I'm going color these backgrounds。

 different colors will'll go yellow and green because they're kind of ugly together We've got our yellow and green backgrounds。

 Okay， so there you see there's your， you know， the outer one has a certain width and height because we've said it the inner one has a default width of 100% because it's a block element but it has no height。

 but maybe let's play around with that let let's say that the width should be 50 pixels and the height should be 50 pixels。

 So now we've got this 50 by 50 element inside here。But because we've set it with position relative。

 I can start doing interesting things like giving it one of the top left。

 bright or bottom properties。 Now， what this does is this offsets the element relative to its parent。

So in this case here top of 10 pixels left to 10 pixels means move me 10 pixels down from the top and 10 pixels from the left if you say things like bottom。

 it will actually send it to the other side in this case it's a little bit a little bit sorry not bottom。

To go。Try these out。 So you'll notice what right and bottom do is a little bit confusing。

 And that's because with the relative position， everything is is quite literally relative to that top left area。

 And you'll see this as well。 if I just do say left of negative 10 pixels。

 We'll get the exact same effect。 So you can kind of picture this magical point at this top left yellow here where everything's kind of centered around。

😊，Position relative was mostly used to。Kind of move you know， pad things across from that side there。

So。You'll see。It's pretty， pretty simple。 you don't always have to use pixels。

 You can actually use percentages as well， So you can actually say 10% from the left or 10% from the right。

 not super common， but you know that's an easy way to kind of or in this case it won't matter because the div doesn't grow。

 But let's say we got rid of the width of the outer div。

 So now as we actually make this page bigger you'll see that the position of high kind of drifts towards the middle slightly So it's always that you know10% from the left。

Now， position relative， I would say， is probably not used a ton。 It is kind of interesting。

 but the much more common thing you're going to use is the。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_37.png)

Absolute position and the absolute position is a lot like relative but。With the relative position。

 let's look at the language。It will offset properties based on its default position。

The absolute position will offset properties based on the closest parent with a non static position now I find this stuff really confusing。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_39.png)

But essentially， what， what absolute means is that when you go left， top， right。

 bottom and all that kind of stuff， it will。It will look at the parent div。That is position。

 not static， and it will。 you can move it to the right to the bottom。

 whereas what we're doing with relative， you can only kind of have it relative to its normal position。

 It did like relative， you got to think of it like relative does not understand anything about the parent。

Right， so when I， when I was doing this here， even though it's in this yellow box。

 it does not really like does not understand anything。 it doesn't。

It doesn't really have a sense of the parent say a height。

 which is why when we try to do something like， say， you know。

 I want you to be 10 pixels from the bottom， it doesn't like that。

 It just kind of the bottom and the it's all the same point。 It's this a starting point up here。

 However， a really common pattern you'll see is that you make an outer element。Relative like this。

And then you make the inner element absolute。 And now whatll happen is that this element。

 you can move it anywhere around the the kind of outer parent top left， right bottom。

 So if you want this to kind of be in the bottom right， you can actually just say bottom。

10 pixels right，10 pixels。 And now suddenly we've got this element over there。

 So it's just really handy， right， Now， obviously， you can kind of do this with floats if you want to。

 But it's a bit of a nightmare。 So。Let's say you had a div and you wanted it to be， you know。

 you wanted two inner elements and you wanted wanted them to be。

 say the right element and the left element。 Well now we can， you know。

 combine a few things we've been working on and say， well， they are all the properties for inner。

 But what I'm going to say now is that。Anything inside of outer that is value left will simply be left 10 pixels and anything in outer that's class right is right 10 pixels like that。

So now we kind of have our two boxes and they'll kind of scale in and out so position absolutely super super useful。

😊，I would use position absolute for many things in terms of placements。

 Usually the only area I'd often use position relative for is maybe to do with text。

 you see some examples on the slide here in terms of relative。

 But the thing is a lot of what you do with position relative。

 you can kind of often solve with margins and padding because you're just kind of offsetting an element。

 So you probably use it sparingly， but it still has some use cases， but absolutely super common。

 I'd say， because there are just lots of times where you know。

 you might just want to put something at the bottom。 Or let's say。

 let's say we don't have these two things or you want， you know。

 like we talked about the righthand sidebar before。 So imagine what happens if we say， well。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_41.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_42.png)

I want to position absolute element。 I want it to have a width of 100 pixels。

 I want it to have a height of 100 percent， the full height。

 and I want it to be attached to the right。Like that。Now， and I'll give it a background of red。

There you go done there's like you know a really simple sidebar so super super powerful you need to remember again that all position absolutes have to exist within a position relative parent。

 you'll notice that if I drop the position relative on the parent everything starts to go whack。😊。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_44.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_45.png)

But you'll notice it still seems to be stuck to the right。

 why is that and that's because if it will it's not that like the immediate parent has to be positioned relative or not static technically。

 it's that it's going to try and look for the closest one and make itself absolute to that。

So in this case， it attached itself to the body because the body is kind of like the outermost element。

 So similarly， you know， if you。Let's say we had an element that was outside of our autoer。😊。

Right so we go and we take this and we make it even on the outside， and then we give it， say。

 a height of 800 pixels and a background of black。If we make a position relative。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_47.png)

You'll see that it will attach itself to that now， right？



![](img/09a1cfcc5feeccb105f8c2571acc9c57_49.png)

Which makes sense because this div height is the closest non static parent to the absolute elements that we were creating here。

Whereas if the outer has a position relative， it will kind of go absolute to that。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_51.png)

So a little bit of playing around。 I find you can even hear it from my language。

 I find talking about positions a little bit。Challenging sometimes I find them a bit weird。

 but you just get used to a few simple use cases and the last use case。

 which is one of those things that I use often but not march is the fixed position and the fixed position doesn't have all those fancy rules that I talked about。

 it basically just fixes itself on the screen。 So we saw before that when we were playing around with these green squares when we were setting things like left top bottom and right。

 that was all relative to the closest nons static。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_53.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_54.png)

Element， but if we make something position fixed， it doesn't really care about elements。

 It's like it's going to make itself。Relative to the the the window quite literally so let's say and this is really useful for things like say a pop up so let's imagine that I I'll show you a couple things here so let's imagine that I have an element and you know what I might make this one a class I'll call it my like pop up。

This is something you might do。 I make a pop up and inside the text is like。

 don't forget to sign up like this。But we think I don't want that to just sit up the top there。

 I want it to kind of float above things。 Now you'd think you'd use float for that。

 but not necessarily， let's give it a width of 300 pixels。

 a height of 50 pixels we' give it a background of black or make it font colour white。And we。

 and that'll just look like a black white box now， right， we will text a line， center it。

And I'll also make this a bit smaller so that it kind of looks more appropriate。Like that。

 Don't forget to sign up。 Now， the text looks kind of awkward there。

 So I might give it a padding on the top。Of 10 pixels。

Now this is really interesting because you've noticed here I've used padding top and you would have seen before I used margin left we talked previously about compound definitions and similarilely with CSS。

 you have padding bottom， padding top， padding left， padding right。

 you have all these different kinds of things and you can represent them all。

 you can kind of compress them all together， for instance。

 by just putting all four together like that。Oops not padding top。

 Like if you just use like the compound thing， you get that。

 And there's a few different ways to do padding。 if you do， like just。Padding padding X pixels。

This will apply a border to all four sides if you do padding X pixels， X pixels， X pixels， X pixels。

 it'll go top right bottom left， I don't know。Top right， bottom left， I think I'm mirrored。

 Maybe not。 It was awkward。 And if you just do two，2。

 it is really interesting because it does top bottom left right。 So in this particular case。

 I only needed one side， So I could just do padding top。 and I get my result。 Oops。

 need to just have one。But if if say I wanted to be super explicit。

 I could have used padding and been like， well， I want the padding to be 10 at the top right down left。

 so that's 0，0，0 like that。And there's padding。 Now， back to the the positioning。

 if I do position fixed， what this will do is it will now float up above everything else on the page。

 Now， you notice that I don't know where it went。 Let's， let's。

 let's get rid to this other black background。 Very confusing。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_56.png)

There you go， so you see there it's actually kind of hidden behind that。😊。

But that element isn't that interesting？Now we have a lecture on Z indexdex about this。

You should go check out that lecture。 There's some there's some ways we talk about how elements sit above each other。

 but for now don't worry about that you won't come across that at timen but you can go watch that lecture if you'd like to So we have this element now and it's fixed on the page which means you notice when we scroll it always stays relative to the viewport to the window we can do some other fun things like we can。

You can move it10 pixels off the top。Like that or say，50 pixels off the top。Easy， and then you think。

 oh， well， what if I want it to be in the middle， Well， it's a couple of things we could try。

 We could try doing this。Now this doesn't really work， but I want to show you。

 this doesn't work in this scenario， but I want to show you this as well because there's something really common you're going to want to do。

I'll come back to that， but。Let's wrap this up is you can actually say left， say 100 pixels。

But maybe you want it to be right in the middle。 So you say 50%。 That makes sense halfway。

 But the problem is that will start the element halfway through the page。

 So this line here is the dead middle。 So then you think， okay。

 I want it to be 50% the minus a little bit。 And there's so many layers to CS。

 But one really cool thing that was introduced。 I think the CSS3 was the CAc function。

 And the CA function actually that you kind of do this math where CSS would figure it out for you。

 So you can see what I've done here I said I actually want you to be 50% minus 90 pixels。

 which is half of the width here。 Now there are cleaner ways to do this， of course。

 But that's a good starting point。 So now we have this little pop-up that just kind of appears on the page。

😊，It's pretty cute。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_58.png)

And。That pretty much wraps up fixed position， like that's the kind of stuff you do with fixed position。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_60.png)

Before we get on overflow， there are two finer little kind of tidbits about CSS that are probably worth tying in to this lecture just because we're already talking about CSS and that one is how do I center a dip？

Really common thing you'll do is you'll have a 300 pixel div。 It'll be like a， a， you know， hi。

 it'll be some text like this。 And' look like that。 How do I center to that？ Well。

 if you actually give things a left margin of auto and a right margin of auto。

 it's a little bit of a bad。Confusing way to do it。 What auto means is like kind of auto fill。

 And if you put auto on both sides， it will kind of equally autofi the margins on both sides。

There's a shorthand way to do this， which you would have seen me do before， which is margin 0 auto。

 which actually makes a lot of sense because that's saying the margin is。0。

 top0 bottom and then auto left and right right because that compound one is top bottom left right。

 And that's the shorthand way to essentially send to divbs。 So you can send to divs really。

 really easily like that if you'd like to。 This is totally unrelated to the position thing。

 It's just something that kind of came came to mind。So yeah， that's， that's， that's a lot of。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_62.png)

Things on CS layouts now。Overflow。Last thing for the layoutouts lecture。When it comes to overflow。嗯。

What？We。This is mostly about text。And it is mostly when you have blocks where text may get bigger than the block can handle。

 So if we say we have a look at our high box here， let's imagine we add lots and lots and lots and lots of highs。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_64.png)

哦， run完。There we go。We have lots and lots of hides you'll see that it actually just like overflows out of the box this is pretty normal behavior this is just how kind of the standard web was designed but if you give that particular box an overflow property you can either say that the content should be visible as then it just renders outside the edges。

😊。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_66.png)

That it will be hidden， which means it just cuts it off。😡。

Or a scroll the some of the most popular ones which hides the content with a scroll。

 so if we come back to our high here we can say at a style which might be like overflow hidden which will hide it now。



![](img/09a1cfcc5feeccb105f8c2571acc9c57_68.png)

Or we could make it overflow scroll， which will make a little scrolly window， it's kind of cute。

 isn't it？

![](img/09a1cfcc5feeccb105f8c2571acc9c57_70.png)

Yeah。So that's a few other ways you can overflow。 That's just another that's a little tidbit with the layouts as well。

 Now obviously there's lots more you can do with layouts。

 There's another lecture on flex and some of the other more modern ways to lay things out a lot of the time you're just gonna have to be googling using examples looking at websites there are these great websites where like CSS tricks which we're gonna reference a few times where you can look at different ways to lay things out they've got everything here like moving backgrounds。

 fancy hover like there's so much depth like at these big tech companies。

 there will be people whose like fulltime job is to be CSS masters and they're always going be learning So it's a bit of a bottomless pit so don't beat yourself up too hard if you feel like not everything is immediately obvious but keep going and you'll slowly build up a little bank of knowledge about how to lay things out laying things out will feel like the hardest part of CSS and it just takes time to get used to it if you get stuck go try and find an example online or something you want to do or describe。

what you want and you'll often find code samples， but other than that， thank you very much。

 I hope that was interesting。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_72.png)