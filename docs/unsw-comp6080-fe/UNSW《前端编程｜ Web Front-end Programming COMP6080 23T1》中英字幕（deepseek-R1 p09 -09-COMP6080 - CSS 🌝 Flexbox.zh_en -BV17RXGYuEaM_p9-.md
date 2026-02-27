# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p09 -09-COMP6080 - CSS 🌝 Flexbox.zh_en -BV17RXGYuEaM_p9-

Hi， my names Hayden， and today we're going be talking about layouts and in particular flexbox。

 which is an extension of the layouts lecture， where we talk about something similar to float and similar to position absolute relative except flexbox is for modern web。

 It's something that is much more recent in the CSs library。

 And it's a response to the need to have more responsive websites。

 which is essentially websites that look good at different sizes and have dynamic content。

 a really good examples is if you just go to the course website。

 you'll notice that as we zoom in here， these boxes all kind of magically resize and reshape themselves。

 and that's built using a flexbox。 It's a very， very powerful tool。

 it's very complicated in the sense that there's a lot of different options that you can use。

 So it will feel like it takes you a while to get used to it。

 but today we're going to be going through a few basic examples。 Now these slides highlight。😊。



![](img/79ffb9d111098a77d034f7280ff0842f_1.png)

![](img/79ffb9d111098a77d034f7280ff0842f_2.png)

Very kind of the the main properties of flexbox that you want to use。

 We've have three or four slides here。 We're gonna to check out a website where we can see more of them。

 But just to start， let us explore something that is pretty common。

 which is that I might have myself a container。

![](img/79ffb9d111098a77d034f7280ff0842f_4.png)

And inside that container， I have myself a box， and we can go and code these。

 We' got ourselves a container here。 and then we have a box inside there。

And we've got three boxes and let's just put letters inside of each box， ABC。

 and the boxes will give say we don't need to give them a width。

 let's say we'll give them a background of blue。 So now you can see we've got three boxes here ABc。

 maybe we'll give them just a little bit of a margin just so you can you can more immediately see what's going on now you might be thinking I'd really like to get those arranged in a line。

 you know， like three boxes together and you could come up with some good ideas for that you could come up with width 33% something like this might work right But then you have to figure out oh。

 how do I get them to appear one next to each other。 and then you start thinking， oh。

 we'll do what we did last time we'll display in line block。

 but then this doesn't quite work because 33% plus 33% plus 33% plus 1 pixel margins you know youve got this problem now where the one pixel margins or。

Creating havoc。 you can see they've got some padding around them。

 some white space because there's actually white like here's the funny part。

 There's actually a space between these two divs like that。

 So you kind of have to remove that space to make this work。 And then if you add the margin in。

 this will probably work because you know，33% plus 33% plus 33% So only 99。

 But once I start putting in。 and there go even bigger margins aren't helping at all。 So， you know。

 there needed to be a way to。😊，Do this better And that's where flex comes in and that's what you see on the lecture slide。

 So if we get rid of that and we just have our three boxes that are blue you can see that everything in flex generally is made up of a parent or container and children and the container is what houses the elements that you're trying to display flexibly and the children are those flexibly display items so。

😊。

![](img/79ffb9d111098a77d034f7280ff0842f_6.png)

The next step is that if we want to use flexbox， we use display flex on the parent。

 That's the key thing to remember。 So I've got these items here， and I do display flex。

 So instead of display block or display inline or display inline block。

 Flex was a new type of display added to I'm not sure which version of CSS。

 So you can see there I've got my ABC， but they're not evenly spaced。

 and the reason they're not evenly spaced is because flex has a whole bunch of properties that decide how things should be shaped。

 And one of the easiest places to go look at this is if you go to CSS tricks and flexbox。

 there's a great little explanatory website where they take you through essentially the two sets of properties。

 which are the properties for the parent。

![](img/79ffb9d111098a77d034f7280ff0842f_8.png)

![](img/79ffb9d111098a77d034f7280ff0842f_9.png)

Which is the container and then the properties for the item And if I just make this bigger。

 you'll see that。

![](img/79ffb9d111098a77d034f7280ff0842f_11.png)

![](img/79ffb9d111098a77d034f7280ff0842f_12.png)

They'll give you the basics like， okay， well， the， the parent should always be display flex。



![](img/79ffb9d111098a77d034f7280ff0842f_14.png)

And then they show you some things here like flex direction。

 And this establishes which way the content flows。 So you can see you can have it flow from left to right in a row from right to left in a row。

 from top to bottom in a row from bottom to top in a row。 And to do that。

 you had just have to add flex direction， which is another flex property of either row row reverse column or column reverse。

 Now， you can see again， everything in this left hand column of the page is for the container。

 That's really important to note。 So if you ever not sure where to put it。

 So let's say I come here and I say， well， flex direction is row。 Well， that's exactly what we have。

 But when I put row reverse。 You'll see that suddenly they all snap to the other side。

 like they're trying to come across from right to left。 Similarlyile。😊。



![](img/79ffb9d111098a77d034f7280ff0842f_16.png)

![](img/79ffb9d111098a77d034f7280ff0842f_17.png)

Similarly， if I do column。You'll see now that they kind of are how they originally were and if I do column reverse they're all swapped around so we can kind of play around with the direction that way but let's just stick with row for now row is the default one so I technically don't even really need to add that。



![](img/79ffb9d111098a77d034f7280ff0842f_19.png)

![](img/79ffb9d111098a77d034f7280ff0842f_20.png)

The next thing is we might want to actually space these children around。

 so if we have a look at this example， you can see that。



![](img/79ffb9d111098a77d034f7280ff0842f_22.png)

Justified content is another property and justifyified content is a property of the container as well。

 so as we come down here you will see justified content and justified content explains how things are placed within their direction so you need to understand that flex is a container and then flex specifies which way does this flow。



![](img/79ffb9d111098a77d034f7280ff0842f_24.png)

That's the flex direction。 And then the justified content is how is this flow spaced？

So you can see we've got one here called space between。

 so if I come back and I now say just content space between that will do exactly what this diagram is showing it。

 which is that it will kind of space things out as evenly as possible。



![](img/79ffb9d111098a77d034f7280ff0842f_26.png)

![](img/79ffb9d111098a77d034f7280ff0842f_27.png)

Sorry， wrong thing， lets see。

![](img/79ffb9d111098a77d034f7280ff0842f_29.png)

So now we've got ABC like that。 Now，BC， these boxes might be a bit bigger。

 There might be something like， you know，50 pixels in size。 and naturally。

 you can text line sent to them and。You can add like a padding of five pixels and you can climb to clean it up a little bit。

 but you see there how it kind of。You know， they all， they're all spaced between like it says。

 we could do things like center or space around or space evenly。 let's try those out。

 So let's say we do a justifyified content of center。

 Now they're all in the middle or if we do space around space like that or space。

 that's an even space around them。 So each element has exactly the same number of pixels And then this one is an equal space between them。

 Now that might look really similar to sorry， what was that space， What do I write。



![](img/79ffb9d111098a77d034f7280ff0842f_31.png)

![](img/79ffb9d111098a77d034f7280ff0842f_32.png)

![](img/79ffb9d111098a77d034f7280ff0842f_33.png)

Space between yeah， space between was where we started meant to do space evenly space。

 Some of these don't aren't as obvious when the elements are the same size。 So for instance。

 space around in space evenly， I'm pretty sure matters more when you have different sized elements。

 you can see we've also got flex start and flex end。

 And this is really interesting because this is how you get those different combinations where you say。

 you know， if you do flex direction as row， which is from left to right。

 but then you justify content to flex end。 That's saying I want to go ABC， I want my content to be。

 you know， in that direction， but I want it all to be justified to the right。 And similarly。

 we could flip that on its head， you know's say it should be row reverse with flex start。

 which will just。

![](img/79ffb9d111098a77d034f7280ff0842f_35.png)

![](img/79ffb9d111098a77d034f7280ff0842f_36.png)

![](img/79ffb9d111098a77d034f7280ff0842f_37.png)

Yeah， so。Yeah， this is kind of funny。 So row reverse puts it on the other side。

 Pay attention to the letters here， ABC， but flex start because it's going from right to left start now means put a on the right。

 So if I wanted to say do ABC that way it's like flex end because remember the justifyified content。

😊，Is within the flex direction。 So you have your flex container， your flex direction。

 and then you justify content within that flex direction。

 You can see so far that most of the things we're adding properties to happen on the container themselves。

 And then the children exist within of that。 So we've talked about flex direction。

 we've also talked about justifyified content。 But one of the things we haven't talked about is align items and align items is essentially。



![](img/79ffb9d111098a77d034f7280ff0842f_39.png)

How elements will be fixed？

![](img/79ffb9d111098a77d034f7280ff0842f_41.png)

Vertically typically， so if we come back here and we say align items center。

Now this won't do anything because the actual div the containers in has no deep that has no height。

 so it kind of calculates its height based on the inner elements。

 but if I was to say give it a height of 500 pixels now。

 thatll be center aligned there so that page is quite I've made I'm going to meet this text。W。

You know， so now that center aligned。 And just for if I give this one a background of yellow。

 you'll see what I mean。 So now that center aligned or if we want it to be instead of center aligned。

 we can make it。

![](img/79ffb9d111098a77d034f7280ff0842f_43.png)

Let's find our line items。We can make them stretch or we can make them flex end。

 So if we say stretch here。 you'll see how they appear differently there。

 So now they're the full height， whereas if we say flex end。

 that should move it to the bottom and if we say flex start that moves it to the top， you know。

 so you can see here immediately， these three， three items give you the。



![](img/79ffb9d111098a77d034f7280ff0842f_45.png)

The truer sense of what the main things you can do are， which is， you know， you got your direction。

 you got your vertical alignment within that direction， then youve got how they're spaced out。

 how they're justified， how that content is spread out so。That' that's most of the basics。

 there's a few other little properties that we might quickly chat to。

 so if you go back to the CSS Ts site you'll see that there's Fl RA。😊。



![](img/79ffb9d111098a77d034f7280ff0842f_47.png)

![](img/79ffb9d111098a77d034f7280ff0842f_48.png)

![](img/79ffb9d111098a77d034f7280ff0842f_49.png)

And flex wrap， let's get back to them。

![](img/79ffb9d111098a77d034f7280ff0842f_51.png)

Goone way too far down now。Go into the comments， I guess。



![](img/79ffb9d111098a77d034f7280ff0842f_53.png)

嗯。😊，Fix wrap。Is。

![](img/79ffb9d111098a77d034f7280ff0842f_55.png)

How you specify what happens when the content there's too much content So for instance。

 let's admit like right now this page was okay because I only had a few boxes right but what happens once I start having a lot of boxes。



![](img/79ffb9d111098a77d034f7280ff0842f_57.png)

Sorry， so let's say I come along and I say， yep， let's have like。30 boxes or something。

You see the default behavior is for it to just kind of run off the end。

Let me move this back to the top。 It's just a run off the end， Whereas if I say flex wrap。

 I would like it to wrap。 That content will start now wrapping down like this。You know。

 and you'll see as well it starts wrapping down very evenly， so because my box is 500 pixels high。

 it wants to kind of as it overflows fill that space。



![](img/79ffb9d111098a77d034f7280ff0842f_59.png)

Um， evenly， so you're like， oh， that doesn't look rightry， but typically you'll find that you know。

 nearly everything hereum。Has a property。 So， for instance， we've got this like aligned content here。

 You're like oh line content。 that looks interesting because they're lots of wrapped。

 And you can see they're all chunked at the top， chunked at the end stretch center space between space around。

 And you can see that。You know， the kind of default position is normal。

 which appears to not be any of those。 But let's try playing with that one aligned content。

 Let's see if this works align content。

![](img/79ffb9d111098a77d034f7280ff0842f_61.png)

Fleex stop。Yeah， flex start。 So now you can see it's all put up the top there。

 And if I said flex end。Then the contents align to the bottom as it overflows。 You know。

 so there's lots and lots of configuration。 There's so much。 There's so much more here。

 Most of the configurations generally on the container， of course， but。



![](img/79ffb9d111098a77d034f7280ff0842f_63.png)

There's a few items of configuration on the actual elements themselves。

Order is very interesting The two I want to quickly touch on to round this out are order and flex so quite often when you're making flex boxes you aren't going to actually specify the explicit width of your container quite often you might do something like say I'll get rid of a bunch of these。



![](img/79ffb9d111098a77d034f7280ff0842f_65.png)

![](img/79ffb9d111098a77d034f7280ff0842f_66.png)

Elements here。Instead of saying width， you might actually say something like flex1。

 Now what flex 1 means is it's kind of like a proportioning system。

 So if you have five elements or with flex 1， then that means that all of those elements are going to take up like it's like a ratio 1。

1，11。 But if you wanted to come along and say okay， well this box is going to be a large box。

So now we've got like a large box。 This might have a flex of 2。

 So that means that they're going to be in the ratio 1，1，2，1，1。 You know。

 So you can imagine it's like one space，1 space， double space， one space， one space。

 So youll see how this pans out now is that sees a little bit bigger and you could make that even larger if you'd like to。

 You know， And flex is very smart。 If you come along and you。

 you just simply make something a fixed size， like 50 pixels。 It will actually go and。

See if that works， maybe that was the current size。no。

 that's not working so if you come along and you set something to be an actual explicit size。

 flex will then usually come and might need to turn flex off that one。Ca it like small。

 Let's see how this goes。 So let's say we say flex is one。

 and we'll go and give these boxes a property of small。Okay。

 so now all of those have properties of small， let's see what happens if we get rid of this stly crisp bit。

😊，そう。Yeah， so you can see that a there， which I believe is over on the right。😊，Yeah。

 you can see it's actually 50 pixels and you notice this that has the screen and if I give it a different background color。

😊，A greenen， you notice it is actually a fixed size and as the screen grows and shrinks。

 it stays the same size， but all the other elements kind of fill out the area proportionally。

 So that's really relevant because flex is very smart with these flex properties。

 You can also change the order of things。 This is something I don't really do a lot。 you know。

 if you want to make this one like order3 or something like this。

 you can kind of move around where it is， but I generally find that can be a little confusing and you you're probably not gonna use that unless you're using a lot of ja。

 but。😊，That's that's really it The main takeaway here is that flex is very powerful。

 it can do quite a lot of things， it's important to go and read the docs and then also more importantly just play around with things A great little website is C is flexbox。

😊，Froggy， this is on our resources page， but this is a fun little game where they will give you a frog and they'll say move the frog over to the lily pad。

 So you think， oh， how do I move， if the pond is the container。

 how do I move the frog over to the lily pad。 Well， flex direction is probably row reverse。

 So it should start over on the other side。 There you go， I want， you know， and then the next one。

 the next question is like， okay， these two need to be centered。

 So then I think justified content center， It's a fun little game And it makes you really think and do things visually。

 which is good you know， youre like oh， no， this one's hard。 It's like， okay， well。

 this was justified content。 What was it what was the space。😊。



![](img/79ffb9d111098a77d034f7280ff0842f_68.png)

![](img/79ffb9d111098a77d034f7280ff0842f_69.png)

Let's go。 We go look at our CSS trick site and we think what was the one where they were kind of evenly spaced across it。

 And this is okay。 don't feel afraid to go Google stuff。

 We don't ever do any closed book exams and you think， okay， space evenly looks okay。

 so we'll go space evenly。

![](img/79ffb9d111098a77d034f7280ff0842f_71.png)

![](img/79ffb9d111098a77d034f7280ff0842f_72.png)

Yeah， oh， not quite。 What is it space between， maybe。Nope。Hm you think， I don't know what that is。



![](img/79ffb9d111098a77d034f7280ff0842f_74.png)

I've got that wrong。 You know， you just play around with it for a while space around。



![](img/79ffb9d111098a77d034f7280ff0842f_76.png)

Yeahay， you know， you figure it out。 So this is a fun little game。 Go play that。 but just try it out。

 play around。 It's one of those things you just have to poke。 So hope that's fun。

 Go use some flex boxes， big learning curve， but very powerful。😊。



![](img/79ffb9d111098a77d034f7280ff0842f_78.png)