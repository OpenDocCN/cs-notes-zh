# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p32 32 - Future of Computing I.zh_en -BV17jcReyETC_p32-

![](img/90a11b3d4307147c99ff501589970328_0.png)

这就这样。这什？It like， that's where it'sberg it basically like if he wants to write like。



![](img/90a11b3d4307147c99ff501589970328_2.png)

反也不是。没以。因我不是。

![](img/90a11b3d4307147c99ff501589970328_4.png)

所的合避。This is excellent， which is really important。Okay。This lecture may or may not have video of me。

 but it doesn't really matter。So we're getting toward the end of the course and hopefully you're well along on your final project so we've really covered all the core material for the course and now what we'd like to do is just。

Give a few talks that sort of point the way toward where technology is going what the future challenges is。

 because you people are looking to 40 plus years of what's going to happen with technology and a lot can change if we just look back at how much things have changed over the for past 40 years it's pretty easy to predict that there will be a lot of changes over the next。

Although I'm not a great predictor， I don't claim to be a predictor of the future。

 there's some things that are even within the coming decade going to be fairly difficult challenges that will change the way technology。

Progresses at the hardware level and that has a lot of impact at the system level at the product level and things like that so I'd like to cover some of that and my idea of it is basically I've merged two different talks that I've given in a number of settings one is about the hardware technology behind what now chip design manufacturing is like。

And based on a set of trends that have been going on for 50 years now called Moore's Law。

 you've probably heard that term。And then the other is sort of direction of if you really want to use computers to do the most demanding computation。

 how do you build and design those， what's the characteristics of those and how those will look in the future。

So。Let's start with Moore's law， Gordon Moore was one of the founders of Intel Corporation。

 which was founded in the early '70s。And even before that。

 he was one of the first people to really be involved in the very new business of semiconductor manufacturing。

So in 1965， he wrote an article about magazine called Electronics。

 which really is essentially just a trade magazine， it's not a scholarly journal at all。And the。

It's actually instructive to look back at that paper， you can find it online。

 and at the time he optimistically predicted that they'd be able to get up to 65，000 devices。

 think transistors onto a single chip。And that was a pretty radical statement。

 so how did he make this prediction？Well， it was a pretty basically there was an extrapoation based on two data points。

So his paper shows these curves， which。Take a while to understand what the heck they mean。

 but basically what he observed and this was based at the time， this is 1965。

 so he had a curve from 62 and 65。And that was given his experience at the time he was working at a Fairchild Semiduct。

There's a sort of basic tradeoff when you're making chip design that you can increase the density。

 how much stuff you put on a circuit。Up to some technical limits and that there's sort of a trade off。

 it's like a lot of things in the world that the more you try to sort of push the state of the art。

 the advantage is the more things you can get on a chip。

Then the relative cost of manufacturing them goes down up to some point， but beyond that some point。

 then it goes up because you're pushing the technology beyond where it's really comfortable。

 So one important point of this is Mosbo is a combination of a technical argument of what they're able to manufacture and also an economic argument of what they're able to produce at minimum cost and both of those components are really important to why things have gone the way they have。

So anyways， he basically had these two data points， 62 and 65。

And then extrapoed to that to 1970 that it would have been a thousand00， and somehow， as I mentioned。

 he's optimistically then scaling from that to say， oh， and if we look clear forward to 1975。

 we'll be up to 65，000。So here it is in 1965， basically。

 he was only willing to project 10 years into the future。

But what his claim was basically was that they'd be able to double every year at the time and just a few years after that he said。

 well maybe that was a optimistic， we'll be able to double how many things transistors we can put on a single chip in an economically viable way every two years。

 and so it's called war's law but there's no law involved， it's not a law of nature。

 it's not a law of the land， it's not a law of some you know passed down to Moses on the mountain or anything like that。

 but it was a bit of the law that this was one of the most influential people of his time。

in terms of technology， and since then he's created a it was a basis of a very large business。

 a many billion dollars a year business that had sort of taken this as okay。22 x every two years。

 we can do it and a huge amount of technology has pushed into doing that。So in particular。

 you've probably seen various versions of this， but I went to a pretty interesting Wikipedia page that with a whole bunch of chips over the years。

And provides how many transistors on them when they were introduced， and if you map that out onto。

A semi logg plot， you get a trend line that is really pretty solid and you can tweak which what your samples are and things。

 but it's a pretty solid number of hitting his prediction of twice，And doubling every year。

 this goes back only as far as 1970， the first。microcroprocessor came out in 1971， the Intel 4004。

 and these all are based on some versions of microprocessors。

It's a little harder basically before 1970， they used a different technology called bipolar transistors。

And it's a little harder to track back into there， but from 71 on。

 there's a very  clear progression that it's easy to get data from。

And I've also partitioned these basically on what type of chipsies were for these are all various types of processors。

 So the early days like the Intel 4004 was intended to be used。

 It was actually first manufactured by Intel to supply a Japanese desktop calculator company where they realized it was easier to produce a。

Programmable processor and then write the calculator functions in software than it was to。

Build a chip， whose only function in the world was to implement a desktop calculator。

And so those are embedded systems and they continue today that cell phones and I'll talk about that。

 smartphones are one of the biggest drivers of ship design today。

Another class is system are desktop systems which still persist。

 but they're no longer the sort of leading edge today。

 more recent design are GPUs graphic processing units and they tend to be big drivers of some of the most biggest。

 most expensive， fastest highest performance chips。

And servers are also like that would include the sharp machines or sort of out outdated servers。

 But all the Linux Andrew machines。 those are all servers of some kind。

 Theyre machines that are meant to sit in some room that you never go to。

 and you access them remotely。And so those are just categorization。

 but you see that across all these types， the transistor count has followed this line pretty well this black line shows what if I just started at Moore's point and doubled every two years what I would have gotten and the grain line shows the actual trend。

Based on the real data and you'll see the two are parallel。 They both are doubling every two years。

 it's just where the the starting point was that。In that compared to where Moore was starting from。

So the point being that this is a prediction he made about a10 year was a fairly radical prediction at the time based really on pretty limited data。

 but it's really held for now slightly more than 50 years。So what does this mean， Well。

 if you go back and look at sort of what people got excited by even 10 years ago。

 they look pretty pedestrian today， and so in particular what's designated as often considered the first real supercomputer。

 was produced in 1976 by a prison named Seymour Cray who was legendary in many ways。

 but he designed the Cray one and the first one was installed in a national web in the United States。

 and this was absolutely。The best machine ever built。 It was about the size of。

It's six feet in diameter， two meters in diameter and about this high。

 and it had benches around the side， which you probably didn't really want to sit on。

But underneath it all was the cooling system that would then run free on， you know。

 refrigerant up through the。The processor part in order to keep it from getting too hot because it consumed。

115 kilowatts， that's a lot of power。I mean， your usual house sort of on average consumes about average is about a kilowatt over the course of a day。

 so this is a lot of power it weighed 5，000 kilograms over 10，000 pounds， cost 9 million dollars。

And it was designed actually， a lot of the wiring was done basically by literally a bunch of women in Wisconsin。

 and all the wires were exactly six feet long so that they'd have the same distance and were handwired in this amazing amount of wiring because there were 170。

000 chips。But if you look at the numbers， you see by today's standards。

 even compared to the laptops that you have here， it was pretty scrawny that it could do at the time what was considered a lot of operations。

 but nowadays it's no big deal。And over the entire career of the Cray1。

 there're a total of 80 manufactured。So now if you look the statistics for the most recent。

 we announced and delivered Apple iPhone and there's counterparts in the Android world， as you know。

 too， I don't know exactly how many operations per second because there's actually six different processors。

On an iPhone chip too fast， force swell， but low power。 There's also some GPU。

 There's graphics processing units and other components。 It's actually not just a processor chip。

 It's what's sometimes called a system on a chip has many functions integrated onto it。

 So if you summed across it， you'd get some huge number of operations it can do。 The phone itself。

 this， this main chip。Is the heart of it， but there's also a total of 16 chips for the whole phone packed into this package。

 doing things like the touch sensor and the phone， you know it is actually a phone not just computer and all the other stuff that the GPS and all the other features the CPU alone and I'll talk about the chip for it is 4。

3 billion transistors。But the whole thing， I mean， a phone weighs a couple hundred grams。

 well less than a pound and its power consumption can go up to five watts。

 but it won't stay there if it kept it five watts， actually you get kind of uncomfortable having it in your pocket。

 you get too hot for。And also as you know， it's a big deal everyone complains about this being the most expensive phone ever。

 almost $1，000， more if you get more memory， but compared to $9 million， it's peanuts。

Especially if you look at the relative inflation impact。And also just in the first three days。

 they were actually disappointed that only three million units were sold。

 and I just read last Black Friday， so last Friday9 million of these were sold in one day。

So the numbers dwarf it and that actually makes a big difference that the scale of production has a huge impact on where the technology can go。

So if I go back to， I am actually old enough to remember。When I was in junior high。

 it was a really cool deal to get a transistor radio as a gift。😊。

And you'll see that this transistor radio。Haad was proudly announced it had nine transistors in it。

 It could actually only play AM was not stereo， pretty crappy sound。But that's what you know。

 the teenagers listening to rock and roll music were listening。

And so that was sort of a consumer product of its era， whereas now we have。

 say a cell phone as a consumer product。And so like I said， it has 4。

3 billion transistors on this chip it's called the A11 Apple actually designs their own chips and that's one of their huge competitive advantages relative to other companies that they are。

They they。They have very good。 They actually acquired a company。

Where I know one of the principles from it， and they were really good at producing these very high performance chips。

So anyways， it's really hard to think about 4。3 billion as a number。

 and so here's one way to think about imagine every transistor was the size of a grain of sand。

They're actually a lot smaller than that。So if you go back to the original chip。

 the 4004 I mentioned and had 23 transistors on it， you could kind of， if you blow up that picture。

 you can kind of count the transistors。And so if you think about that in terms of grains of sand。

 it's just a very， very small pinch again， you could， if you were so inclined。

 spread out and imagine counting up to 2，300 grains of sand。嗯。4。

3 billion is a lot bigger number its like。189 kilograms so almost 400 pounds of sand。

 and if you went to Home Depot and wanted to buy that much sand。

 it would fill up actually about eight and a half of these bags， each of which weighs 50 pounds。So。

It's still some like' a lot of sand and you wouldn't want to carry that much sand in your pocket。

But it's still， you know， you could with effort in the。You could pick it up and move it。

 maybe making a few trips。But like I said， that the important one of the takeaways is economics actually has had a huge impact on where our technology has been and in general。

 there's a sort of cycle of。That if you can sell more stuff。

That generates more money that can be invested in improving the technology。

And improving the technology leads to being able to produce better products。

That then sell more and so the whole world of electronics has been in this cycle of and that's why I mentioned consumer products have really become the most important thing out there。

 You can look at the supercomputers that are in national labs and get excited by those。

 but they're manufactured in such minuscule quantities that they don't really attract the attention of the industry that much。

 The industry would rather be trying to help Apple produce its chips or Samsung for。

Than to worry about these guys that are building supercomputers。So like I mentioned。

 it's $300 billion a year industry。And so for example， the iPhone's been out for 10 years now。

 and in that time they've produced 12 different generations and if you were to be given one of the original iPhones and try to use it you'd go。

Wow， this thing really sticks。Even though back in that time there was like the coolest thing you could have。

 people waited in line for hours to get one of these and so they've created a whole business where all of us sort of get really excited and spend money on these bright shiny objects and then within a couple years we're saying oh man。

 time for a trade in this thing's just no good anymore and so that keeps us spending money that they can use。

A to make money， but B to invest in the technology that will make us want to get the next one three years from now or whatever year own refresh rate。

So can we imagine if we were in 1965， we're now a little over 50 years from then。

 what if we looked at 100 years from then， so in the year 2065？48 years from now。

 what would a consumer product be like？And of course， if you think about 65。

 there were no mobile phones。Individual people did not own computers， they were。

 if you look at even the semiconductor business， their main customers were industry and the defense。

Military things。But now， like I said， the main customers are consumers。So。What， what would it mean。

 you know， could I go， how could I extrapolate from a nine transistor AM radio to today's phone to something that would be that much more of 50 years from now？

Well， I don't know， I won't claim to no， I certainly won't look like this。

But I think you can assume a few things it will be。Taken for granted。

 whatever we use will have to be portable where we and it will have to be reasonably low power。

 not just because。batteriestteries， it might not be based on today's battery technology。

 but if it's going to sit in our pockets or our。Or we wear it on our bodies。

 it can't have a nuclear reactor powering it。Because it'd be too hot。And like I said。

 I claim that things that are manufactured in vast quantities。

 either consumer devices or things like the Internet of things where the whole world will be connected by devices that are all do it。

 you need that kind of scale。 something that will be measured in millions or billions of units to really drive the marketplace。

 That's where the industry will pay its attention。 So it will be either individual consumers presumably owning one or many of these or something where computing is just so ubiquitous。

 It's just exists in every little object that's out there。 Those will be the drivers。

 I claim this is all。Just my assertions and this may or may not prove to be true。So like I said。

 it has to be something suitable for portable low power operation and right away。

 you know people get all jazzed about quantum computers and you might hear the buzz about it and I personally have various reasons I'm skeptical about them。

 but you're not going to have a personal quantum computer that you're carrying around because it has to be run at liquid helium temperatures and I'm just not going to have a cryogenic you know personal device。

It won't happen also has to be very inexpensive to manufacturing。

 I'll talk more about just the sort of fundamentals of how chip technology works。

 but the main take home is that they can spit out these chips literally like potato chips coming out of Frito away。

 that even though the technology is way more sophisticated。

 the point is that they could just pop these out of machines in very short order and that the cost of manufacturing even as they scale how many devices there are on a chip。

 the cost per manufacturers stays roughly constant。啊。And one thing to say it。

 and a lot of people talk about Moores fo's dad。 blah， blah， blah， they say this。

But I think a lot of them are thinking too small， they're assuming that it will be more or less the same technology we have today。

 things that look like what we call transistors， but I'm not making that assumption。

 All I'm assuming is that there' will be some kind of technology where we want to put a whole bunch of them into a small system that is a useful system of some sort。

The other thing I'll point out is there's some people go， well， you know， well。

 who would want more computing power than we have today， you know that doesn't make sense。

 but I think we can all believe that no matter what。

What we think of is a lot of computing power today in the future。

 we'll think that we'll have just a whole different calibration of that。

So one great thing about plotting things on log sum log is you can just extrapolate to your heart's content and so just imagine that trend continues until the year 2065 and the number you come up with them is 10 to the 17th so right now we're at around 4 billion。

And so that would be four times 10 to the ninth。So imagine something times 10 to the 17th。

And I don't know what that little something is I'll give you that， let's just call it 10 to the 17th。

🤧咳。So again， if I use my sand analogy， then this is a picture you got to love Google imageage search that I found of a young man on a beach in Brazil making a sand castle shaped just like the Empire State Build and just looking at it without actually being able to go there and use a ruler。

 I'd estimate that it's around，A10th of a cubic meter。

 which would work out to several billion grains of sand。 So roughly what an apple chip is today day。

You know， if it were in grains of sand， it would be like this structure。But what would it take。

 What would 10 to the 17th mean in grains of sand？ Well。

 if you were actually to build a not just a scale model of the Empire State Building。

 but an accurate real life model of the Empire State Building out of sand。

That would be about a million cubic meters。And I'd estimate that it would be something like a third 0。

3 times 10 to the 17th grains of sand。So now I'd have to build three of those。

And I'd have 10 to the 17th， so that just tells you that's a lot of devices。

 10 to the 17th is a really big number。So let's look a little deeper at how have has Moore's law taken place this doubling every two years？

What's happened。 And there's certainly two factors。

 One is that chips have actually gotten bigger over the years， but not that much。

 So roughly speaking， if you extrapolate about every 10 years， they've doubled in area。

And what's been more significant is that transistors of devices have gotten smaller and able to pack closer。

 and so basically the trend is every two and a half years， the number doubles。

Per area every two years， sorry， two and a half。Yeah， two and a half。

 so over a course of 10 years a decade you get four doublings there and that's how you get five doublings in 10 years or one every two years。

So let's just look at that a little and see what that means。So like I said。

 if you look at chip size and chip size actually varies a lot。

 but the original 4004 was only 12 square millimeters。 It's pretty small，3 millime by4 millime。

 you can imagine is。A pretty small thing， much smaller than， say a fingernail。

Whereas the most recent Apple， they also have to be reasonably small because they have to fit it inside of this and they actually most of the area volume inside of here is filled with batteries。

 by the way， this is not an iPhone 10。嗯。So there's only so much space。

 so it's about 89 square millimeters， so it is like the size of。Kind of a big thumbnail。

And this is all these are scaled relative to a dime。 Now， if you go。

 the biggest chip that's manufactured today is made is a GPU chip made by Nvidia and it's 815 square millimeters。

 so it's a big beast and you see it's got 21 billion transistors and 815 is pretty much as big as the technology will let them do right now in this time。

So partly GPUs in general they're not portable at all。

 these aren't you know the big NviD ones and they're very high power， they're pretty expensive。

And pretty big， and so part of the reason why they can really push the state of the art is because they can be big like this。

嗯。So imagine if you take all these chip I mentioned。And you do the same log log plot， first of all。

 you'll see it's a little bit of a。Ficction to put a trend line through this。

 because as you can see different chips， even in a same given year。

 you can put a big chip if it's going to sit as part of a server in a room where you can provide a couple hundred watts of power versus something that's going to be in your pocket and run off of a battery。

So even in a given year， you'll have quite a range of chip sizes。But overall， you'd say yeah。

 they've been getting bigger like I said every。The trend line is every 9。8， so call it 10 years。

 chip have basically doubled in area。So will that continue？Well。Again。

Run the numbers and you come up with 147 square centimeters。

 which for those of us who aren't sort of born in the metric system that doesn't necessarily have any real sense of how big that is So just imagine that Apple said oh great I'm going to have a chip in the year 2065 there will be 147 square centimeters and 10 to 17th transistors and I lost track of their numbering system for both the phones and the processors。

 So what's call it the iPhone 30 and the Apple A 111 chip。There's no problem with that。

Which is 147 centimeters square is really like pretty big。 and in particular。

 it's way bigger than this。It's about  two and a half bills and so no， no， not going to work。

 you know， I need something that's portable， I don't know if it's going to be in my pocket or in the node。

 you know， here or there， but it's not going to be that big。So clearly。

 that trend isn't going to be where we're going to look for growth over the long haul。

So the more important one， as you saw is the bigger news is that things have gotten smaller。

And so one metric to use for it is what I'll call the linear scale。

 which is defined simply as the square root of the area divided by the number of transistors。

 so one way to think about that is if the transistors on a chip were just laid out in an even grid。

 which they're not。Then the spacing between them， either in the x or Y dimension。

 would be this linear scale。So in some measure， you've probably heard people talk about like they say that the Apple 11。

A 11 is based on a 10 nanometer process。But the only there's nothing actually built in。

That means nominally that。You can put pairs of wires as close as 10 nanometers to each other on the chip。

 but it's still a bit of an artificial number， so this is a real number measured by how densely are you packing things onto your chip。

And if you run that number for all these different things， you'll see a pretty tight trend line here。

And like I said， the linear dimension is shrinking by a factor of two every five years。

Which is equivalent too， since it's the linear area and our transistors are measured by transistors per。

Square unit。 so that overall means that we're。Every five years， we're reducing we're。

Squeezing more things， increasing the density， the transistors per square or centimeter by a factor of five or equivalently every two years where every two and a half years we're doubling。

So and that trend， as you can see， is independent of whether you're making a giant chip for NVIDdia or a little chip for Apple。

 it's just based purely on the technology and so that's why it's a more clear trend line。

And so if you go back like to the。Original microprocessor。The linear metric there was 72。

000 nanometers or 72 micrometer， sometimes called microns。Whereas today the。Apple chip is 144。

 as I said， it they call it a 10 nanometer process。

 but the actual effective use of space is more on the order of 144 nanometers apart。

A nanometer as you know， is 10 to the9meters。And so if I take that just again。

 to give you a sense of of what these linear metrics mean， let's say that anything between。呃。

1 thousand and a million nanometers is a submimeter， right， a million nanometers is a millimeter。

And 1000 is a micrometer called a micron， and so that's the submimeter range and you see that chip sort of at this metric sometime around 2005 or so went from being at a millimeter submimeter scale to a sub micrometer scale。

And just to give you a sense， these are you know， this one picture shows six orders of magnitude。

 so that's a lot of。You know， in the physical world， that's a huge range。

 and one of the really interesting things about this technology is it's been gone。Over these years。

 they've been able to just keep charting along and start reaching these dimensions that would have been unimaginable just a few years before。

So for example， if like a large protozoa an themeter would be about half a millimeter， 500 microns。

 the average size of a cell in the body is around 50 microns and this went in toll number which seemed pretty dense at the time would be on that scale。

 the sort of smallest thing you can see visibly would be a strand of spider silk and that's five microns。

 the thickness of a sheet of plastic wrap like sirran wrap is around 10 microns。

So just that's sort of where things were up until around 2005。And now we're well into this subm。

Grometer range。 and so all visible light is actually in a pretty narrow wavelength band。

So between 400 and 700 nanometers and now the apple chips are even at this scale are well below visible light。

 which。You go， oh， I thought they used white to make these chips。And it's true。

 they're way below the first of all they use ultraviolet。

 but even then they're actually the features they have to pattern on these chips are actually smaller than the wavelength of the lasers that drive the exposure。

And if you kind of keep pushing down， you get down to sort of the smallest。

Kind of things you'd imagine a biological system would be the diameter of a DNA molecule， which is。

A DNA molecule itself is actually pretty long。 They're all kind of in there， I mean it's long like。

This wall kind of numbers， but they're really sort of crunched into a cell pretty。Tightly。

 their diameter is two mi nanometers and a carbon nanotube that people get excited about again。

 that's about one nanometer， so that's the range of where things are headed。

And as I mentioned that the current technology is to try and pattern things as small as 10 nanometers。

So let's play our games again， let's say can this trend continue then until 2065 and the number you get out of that is 243 picometerters。

 piCO of course is 10 to the minus 12 so can we pattern things on a chip if we can do it you know in 72 they could do patterning things that were measured in tens of microns and now they can do it measured in tens of nanometers。

 so why not do something that's measured in tens of picometerters， another 50 years from now？Well。

Physics has this nasty way of getting your way。嗯。The problem is like the spacing。

 the kind of smallest spacing between two molecules you can imagine， is a hydrogen atom。

And that's like 74 picometerters in a hydrogen molecule。

 if you look at silicon that silicon is not a uniform grid。

 but the sort of average distance between any two silicon atoms in a。

In a molecule is a couple is 500 something pico meters。

 so there's no way you're going to be putting things。As coast together as 243 pico meters。

 even 50 years from now， so the technology does not extrapolate the way it did in the past。

And you know， we can imagine technology， but physics kind of gets in the way。

So that gets us back then， okay， we can't grow the chip much bigger than。Today's chips。

 let's be a little bit generous。 we'll say that we'll allow it to be 400 square millimeters is the biggest chip we're going to allow two centimeters on a side。

That would be a lot like more than four times bigger than today's chips， but yeah。

 we can probably deal with it somehow。啊。We're not going to let it grow to the size of several dollar bills。

 right？嗯。Well， it works out actually you'd have to be therefore even more closely spaced than what I was extrapoing。

 it would have to be and we wanted to get our 1s 17th devices we'd have to be at a scale of 63 pico meters。

 which is。Coloser than the spacing between two hydrogen molecules。Atoms。

 so I think we can pretty safely say， not going to happen， you know。

 not with by just taking today's technology and just running it out。

 meaning it's you'll notice it's all based on two dimensions。

 it's all based on patterning on a flat surface。These complete circuitry including all these devices。

 so two dimensions just isn't going to cut it。But let's say， okay， well， you know。

 there's nothing magic that we live in a three dimensional world， what if we allowed？

A three dimensional stacking。And so we allowed a package that was five millimeters high and 20 millimeters on the side。

 and it's almost exactly the same size， shape and volume as three nickels stepped up。You know。

 that still sounding plausible。And let's imagine we could put these layers in this 5 millimeter package。

 We could fit 100，000 layers， so they'd have to be 50 nanometers apart from each other。

 which actually sounds kind of plausible， it's going to be future technology。

 but you can imagine that 50 nanometers being possible， but those are what I'll call logical layers。

 meaning that layer just like today's chip， it's not just a single layer of stuff。

 it actually has these whatever these devices are， it has some wires that can connect them。

 in multiple layers， it has some insulation so that you don't create short circuits between the layers and stuff。

 so there's more there， I'd say it would be something on the order of a million。

Like 10 physical layers， per logical way to do it。But still， it's sort of remotely plausible。

And that would now reduce our linear dimensions that we have to achieve down into 20 nanometers。

 which is smaller than is possible today by a factor of 10 or so。

 but at least it doesn't seem to violate any laws of physics so this at least seems yeah。

 we could somehow create in this size package of three nickel stacked up of 10 to 17th devices。

 it seems at least vaguely possibleus let's explore that。Well， there's a couple of problems。

 but I don't think any of these， these aren't all impossible to overcome they're just challenges one is。

Right now， if a chip has more than a very small number of defects， the whole chip has to be scrapped。

And especially for a standard microprocessor basically has very low tolerance to any flaws。

 something like a memory chip， they can put in spare cells。So that if one of them is bad。

 then they can just program in and just use a different one and same with NVIDA。

 one of their advantages is a GPU has many identical processors and so if they find that some of them are faulty。

 they put some spares into those so that they can basically make these chips do what they do and that's part of the reason why it's economic for them to be producing these very large chips。

But。Once you get up to 10 to 17th and a million layers of patterning。

It's pretty hard to imagine having consistency of quality that's not going to have many more failures。

Another， and this is a serious will be the manufacturing cost。A million layers is a lot。

 and I'll get into that and then the one that will be actually the biggest challenge period。

 no matter how you work at is power。As I mentioned。

 we can't just scale up power if these are going to be consumer devices， the least of which is heat。

 you don't want things that are too hot to hold in your hands or put it in various places。

So just to give a sort of background lesson of how the tips are produced。

 it's by a photographic technique， so it's more or less equivalent to how photographs back when we had them were printed。

That they pattern layers， they start with a very highqu piece of silicon nowadays。

 and they can pattern things by basically putting a mask down。

 which is some kind of a goop that they pour on it and exposing it to light where some parts get exposed and other parts don't and then using chemicals to wash away and depending on the type that's called a photoreist it can have either positive or negative what's left after you washed away are either the things that were hit by the light or were not hit by the light there's both possibilities So basically you've been able to create a pattern and now you can put more stuff you can put a layer of metal in there or different type of material or you can implant some ions or put in various chemical impurities is all kinds of things you can do so after about 50 or 60 of these steps you've produced a chip that has transistors。

It has wires that connect them and it has insulator that can keep them from shorting against each other and so the point is that right now it's about 60 steps。

But 60 is still a relatively small number if I can do 60 steps。That。

And produce something with 4 billion transistors or I can do the same 60 steps and produce something with 21 billion transistors。

 So what I mean is it the cost。Is roughly， actually。

In terms of how much work it takes to produce a chip is fairly constant。

And the biggest sort of critical piece of machinery and hardware in there is what they call a stepper or a scanner。

 it's a combination of a scanner or a stepper。And。What that does is the wafers are about this big。

 they're 30 c， so about a foot in diameter of silicon。

 And then there's these machines that cost a lot of money that can go through and so that the most difficult part of this is。

 like I said， they'll spread the photoresist that's just a chemical thing。

 But then they have to step through and do this patterning。And so。That sort of the most expensive。

 highest tech machine involved and the one that limits really the throughput of the production process。

 So if you work out the numbers of a fab line， it's about 18 seconds to do this for a whole wafer。

 So I've actually never seen one of these。 and they're all in these boxes。

 you can't really see what's going on。 But if you think about they have to take this 30 cm chip and wafer and kind of move it around and zip expose all these little positions in it because the exposure area is。

A little over 800 square millmeterters。 Basically， each of these NviIDdia GPUs is。

Is one exposure it's called the reticle， in other places they'll be patterning multiple chips within that reticle。

So very high tech， very expensive machines， very sophisticated。

 but this is the thing that sort of limits how fast they can pump things up。

But the point is right now you do 60 layers， you step them through。18 seconds apiece。

 so you can imagine you're producing a lot of chips at an effective rate that's pretty hot。

And then you're done。So but the problem is I can't do this a million times right。

 I can't run a stepper over something a million times that will first of all。

 not get the quality you need and second and more significant， it's going to cost too much。嗯。

So right now， it costs on the order of 10 somewhere between $10 and 20 for that's how much Apple pays to its manufacturer。

 which is a company in Taiwan for each ship。Yeah， I know the phone costs $1，000， the chip cost $10。

That's sort of the economics of it and Taiwan semiconductor manufacturer makes good money doing this。

 so that's sort of a realistic number of how much it costs。But you can't then say， okay。

 go from 60 layers to a million and do this same process。 All of a sudden。

 your cost is going to go out the window。 And like I said。

 this whole business is so cost driven because of consumer products that you can't afford to do anything very exotic。

 So somehow they're going to have to get away from this exposure business of doing layer at to time。

Either the chemicals will have to kind of somehow absorb themselves。

 or there'll have to be some tricks that you can pattern not just one layer at a time， but multiple。

And actually， that second part is already taking place with the more recent generations of flash memory。

 they actually do this really pretty clever technique where they pour these various layers of stuff。

Of variousar different structures and make a sort of stacked layer of alternating types of material。

 And then they start patterning from the top。 And it's as if you had a。You could start drilling down。

A whole bunch of holes in a whole bunch of places at once because it's all done via photolitthography and then ion mill that goes but they're just shooting these ions down。

 using the mask to stop， block the ions in some place and let them go in others and they go through all these layers。

And then they can pour in some goop into there。 And that makes the vertical connections。

 And they basically make the transistors are like a post with these like donuts around them are the actual storage devices for the flash memory。

And hook them all together and so they can do this all using the same trick actually about right now the most recent Samsung process can do 64 layers of memory cells using a total of around 30 masking steps。

You can imagine at some scale， you are doing something better than just one layer exposure at a time。

 Now， it happens that this technology is very much。

specific to the circuitry that you need in flash memory。

 it't you can't make microprocessors this way in particular none of these areas can have metal enough。

 so it's very specific to this technology but at least gives you a glimpse of different ways to sort of move into three dimensions and avoid the cost of photolithography。

But like I said， power is a problem that a phone can go up to five watts。

 but if you run it at5 watts first of all use zip your battery out quickly and worst of all。

 you won't want to be holding onto you know think of grabbing onto a light bulb and trying to hold it it's only a five watt bulb but it's enough that you wouldn't want to do that all the time。

You can look at the brain， which is Z of a。A marvel of low power engineering created by evolution。

 and the numbers look kind of interesting that there's still a lot more neurons in your brain than there are transistors on most chips on any chips。

But that part of the way it can work is that the clock speed， there's no ca。

 but the sort of rate at which neurons fire is measured in the。700 hertz range。

No more than 100 per second for a given neuron。 so these things operate at a much lower frequency。

 and that's possible then to greatly reduce the。The power requirement。

 but still a brain actually consumes when you're sitting here like you are now。

 about a quarter of the energy， you're consuming about 60 watts of energy， just sitting here。

And you're all 60 watt bulbs。And about a quarter of that is firing your brains。

The human brain is by far the biggest power consumer of the body。And so you say， oh， gee， well。

 why doesn't my head get hot well， it's because you have blood running through。

You have a very clever。A liquidquid cooling system that。

I don't think we're quite ready to wire the chips into our bodies so that the blood flows through them and keeps them cool。

 but maybe that's what you'll end up doing。But even then that gets you up only into the 15 to 25 watts。

 that's not going to get you really far and then you'll have to worry about these chips。

Taking all that。Using up heat， and so then you'll need more air conditioned rooms。And。

That won't be good with climate change。 So anyways。

 the point is that even achieving that the level of the brain would be a pretty big leap from where we are today。

But if we want to get up to 10 to the 17th， somehow we have to not just hit brain level numbers。

 but hit way more numbers than that， 23 million times more devices than the current chips of today。

And without going， maybe you could push it to 25 watts by some clever cooling techniques。

 but it's not going to go much past that。So that's sort of one part。

 another part is again pure economics， this picture I got out of somewhere and it's a little out of date。

 but it shows something very。Very significant， which is you'll see along the bottom those numbers on the black bars are what technologies I mentioned。

 the nanometer spacing of between two wires， and so this only gets you as far as a 20 nanometer process。

 which is about five plus years ago。But this shows all the companies that are capable of manufacturing chips at that level of sophistication。

And you see that there used to be quite a few of them。And now there's only four。

 so in the whole world right now there's only four companies that have the resources to make stay the air chips。

And a lot of them。It mightight be companies you've never heard of and you're not so the one that you'll recognize of course that Intel makes all its own chips and it's always been a leader in technology and still is。

Samsung， you know pretty well at many levels， they're actually one of the best semiconductor companies and produce a lot of the memory chips and flash memory chips as well。

 as well as producing consumer electronics Samsung is a giant company and then the other two companies。

 TSMC is Taiwan Semi manufacturing， which is you might guess is in Taiwan。

 and global foundries is a company that was bought created relatively recently。

 meaning within the last 10 years。By basically consolidating a bunch of the other companies that had reached the point where they just couldn't afford the capital investments needed to keep their technology moving forward。

So Global Foundries is actually owned， wholly owned by the United Emirates Sovereign Wealth Fund。And。

Like I said， it includes companies like AMD， Motorola， Siemens。

 all kinds of companies that historically made chips and no longer do。

And you'll see a lot of companies have dropped off， so IBM got out of the business。

 they sold out to global foundundries a few years ago。Japanese companies Fujitsu Toshiba gave up。

Except for doing some， Toshiva does some flash memory that they're probably going to have to sell because they lost a lot of money and on nuclear plants in Pennsylvania。

STM was a European company that became part of global companies。So you think Apple。

 wait Apple is not on the chart， Apple doesn't make its own chips。

 its chips are made mostly by TSMC and a little bit by Samsung。

 which is a little bit interesting to think that Samsung。Stapll's biggest competitor is。Saamung。

 so they're competing at the phone level， but they're cooperating at the。Jen the chipa。

And sort of some very strange things， Nvidia uses TSMC。

 actually TSMC has over 50% of the business for what's called foundries。

 companies that produce chips other for other products。

So there's a trend here that might be a little scary that gee。

 if it's four and hour is its going be three and then two and then one。

 and if there's only one company， what's going to motivate it to kind of keep driving forward this economic growth the competition is a big part of it so that's a little bit scary to think about and again the reason for it is this huge capital costs that one of these fabrication facilities costs billions of dollars to do and the only way they can then be selling chips at $10 apiece is by getting a lot of chips through it。

 And so that's part of the reason why they need these consumer products that。You measure the counts。

 how many chips in millions。Instead of tens。Okay。Oh yeah， while this looks a little scary。

 actually there's another problem that's even worse。

Something that's sometimes called dennard scaling。And one simple way to say this is a state of the art microprocessor of 2004 ran at about two gigahertz。

A state microprocessor of today runs at about2 gigahertz。I mean。

 maybe Mike I bought a Mac that has four gighertz clock。

But it's not been that dramatica of improvement in corporatera。

And that has to do with this thing called Dennard scalinging， so Robert Dennard is。

 he's a pretty old man， but he still works at IBM and was actually a graduate here he got his PhD in electrical engineering。

I think in the 50s。Maybe you're early 60。So back in 1974， he kind of。

Figured out what it is that Gordon Moored had laed on about why this galley is so beneficial。

 and he came up with a very simple model that's taught in all sort of first yearear semiconductor courses of what it means if you shrink all the things。

 the linearier dimensions by some factor of K and also while you're doing it， you reduce the voltage。

 the supply voltage by a factor of K as well， so that all electric fields are constant。

And basically all times good things happen since the linear dimensions shrink by a factor of k。

 it means in a given area， I can get k squared more of it。

It also will let me run these faster because the combination of。あ。

The way resistance and capacitance scales， I can just run about k times faster。And yet。

 the power per chip is going to stay constant。 So this is why it's so great to have been able to stuff all this stuff closer and closer as I get more stuff running faster without consuming more power。

😊，And that was the rule of the land。Until 2004。And then it's a little hard to see in this chip。

 but basically。This top graph shows the Moore's walk curve， the number of transistors doubling。

But this blue one shows。Actually。The cock rate， you can see。flatlatened at 2004。

 and they show this extrapoation this was done in 2010 of its shrinking a bit。

Excuse me and it's about right and what it means is how much you can get out of a single processor core has gone flat。

And。The only thing that could be done to kind of make more use of these more transistors on a chip was to put multi that's why they did this transition to multicot。

Process， it's not because people really wanted them， it's just。

 they knew how to build them and they couldn't make any single processor go any faster。

So that's been sort of the trend that happened。 And 2004。

 there's basically a big Intel project that was going to be their next generation。

 and they had to can the whole project because it was just going to consume too much power。

 So there really was a date in time when this scaling stopped。 And the reason is they got to evat。

 And because semi。Sililicon has particular properties on voltage。

 it meant they couldn't reduce the supply voltage below that and still get reliable transistors。

So there's sort of a hard limit， again， physics got in the way。I was resorted。So anyways。

 my point is we can project out 50 years from now and kind of vaguely imagine using some fancy three dimensional technology that will be able to hit this trend line of 10 to 17th devices。

But that's going to be a lot different than if you look at the past 50 years。

 even though it's pretty remarkable what they've done at some very high level。

 they haven't done anything。 They've just incrementally improved their ability to pattern transistors on silicon on a two dimensional surface。

And so we're talking three dimensions and as I mentioned， how just a lot of unknown system questions。

 not just at the。Deevice level， but even questions like what will be their architecture。

 How will computation be done， will they be based on DNA or some other know fundamental property of。

Of computation， what mean to program these， it'll look very different from where we are today。

 almost certainly。Okay， let me now jump into the second part here。

Which is high performance computing。I spent some time。是。Two and a half years ago。

 I spent a year in Washington， DC working at。Pice called the Office of Science and Technology Policy。

 which is part of the White House。 I was actually next door to the White House this time。

 So this is an area I actually spent some time looking at。

 But if you look at sort of what are the biggest computers that are built today， they sort of。

Tend to follow in two very distinct categories One is what are known as supercomputers。

 these are things that are designed。Purely to solve some of the most challenging computational problems out there。

 and you want to apply all that computing power you can to solving one problem。

Whereas something like a Google data set actually bigger in terms of。

How much hardware and volume and power they draw， But those are really designed to。

Serve millions of customers， each of whom is doing a relatively small amount of computation。

 So they're pretty divergent in what their purpose is， and therefore。

 they're very different in how they're built。And so you can sort of in a very crude way sort of。

Draw the two axes of what they'。Their purposes and so the traditional supercomputers。

 it's all about computation nowadays， how many forwarding point operations per second can you do？

And the amount of data they deal with， although it's significant is not the biggest issue。

 that it's really just how much raw computing power can be apply。By contrast。

 Google's and its companies and by Google I also include obviously any web company。

 but Microsoft increasingly Facebook。Amazon， any company that's sort of a data driven company。啊。

they're much more focused on is how much data can they deal with， how much can they bring in。

 how much can they manage， how much can they information can they then extract out of all this data that they're collecting。

And of course， we tend to interact via the cloud much more with the data center class machines than supercomputers。

 so at some level we have a more direct understanding of what's going on there。

But let's look at these supercomputers who at one time were the driving force and computation。

 but aren't anymore。What are they there for Well， they're sort of mostly running various simulations of some kind of physical。

system so for example， there's people here at CMU and the physics department who are cosmologists and they're trying to come up with various models of how the universe was created and where the dark energy came from and all this stuff and what they do is they'll come up with a model and then they'll run a simulation and see。

 oh yeah that matches sort of what we would have expected or not and that's a way to validate scientific theories industrial products。

 if you have something like complex airflow over an aircraft wing or even a consumer product。

 you model that by running simulation。There's people at the Pi School of Public Health who modeled a propagation of disease namely flu by modeling basically every man woman and child in a given geographic region as an agent and simulating that agent with rules that say if there's two children in a classroom that have the flu。

 then there's a 20% probability that each of the other 28 students in that classroom will also get the flu。

 they have all these rules， they basically it's a little like SimC。

 they just let it run and see what happens。So those are sort of the types of computation that these supercomputers mostly do。

 they're very much driving， typically simuulating a lot of times partial differential equations or some other way of modeling the physical world。

And so the hardware for that is sort of like you know a racing car kind of class thing that they're beautifully engineered products that are carefully designed to be able to run at very high performance。

 getting very reproducible， reliable results， they don't break down much。

But roughly speaking the way Titan looks from a computational point of view is there's some number of nodes。

嗯。Coast to 19000 Titans， by the way， is a bit obsolete， it's only the fourth fastest in the world。

 but it's the one I happen to know something about the design。嗯。

And each of these nodes is about the same computing capability as one of the machines in the Gates clusters。

Literally， meaning it has a CPU and a GPU， and they're more or less comparable to what those gateates cluster machines are。

Even though the gates cluster machines are newer and so overall。

 this thing costs them about $200 million to build and draws seven megawatts。嗯。

And so if you take 418， you'll get to program GPUs。

 but the basic idea of how you program this to run a simulation is you take some physical representation and make it discrete into a mesh。

 say， and then you partition that physical representation into distinct regions and map each of the modeling a simulation of that region of the mesh onto a separate processor。

 and then you run the sort of cycle where first you model what's going on within that region。

That's computation。 And then you exchange data between the different regions to sort of describe what's going on the boundaries between them。

 and this sometimes referred to as bulk synchronous processing that you do this cycle of compute。

 communicate， compute， communicate， all locked together in this very tightly synchronized loop。

So what that means is if you can get this thing running fast。And everything firing well。

 then you basically can run， and that's the art of programming these things is to make them all sort of you do about the same amount of computational work per step。

And have them all work together very effectively。One problem that happens then is if you have any load imbalance。

 like you have to do a little more work in one part or the other。

 it has the effect of slowing down everyone so that you can only run at the speed of the slowest win and because of the physical models they can't they have to be kept up to date with each other so they can't just say。

 oh well， we'll just skip this one for a step and pick it up later。

So that's a problem and part of the challenge of programming these things is keeping im balance。

The other problem is that they're really a pig to program that you have to basically program these things at three different levels at the top level。

 these nodes all communicate with each other by sending messages and so the programming interface for that is called MPI。

At the node level you have a multiprocesor core that you can program and then you have to program the GPU usually using a different language so in all these computational models it's pretty different the sort of optimization strategies you use for and what it means is I can map this code。

 this program and run really fast on say Titan but in a couple years they're going to come up with some new machines that will have sort of different relative performance of all these levels and it means I have to rewrite huge parts of software。

 major rewrites just to sort of keep up with the machine and so there's a lot of people who spend their lives just rewriting the same programs over and over again to move from one machine to another。

Not time。And just to give you a sense。I need to speed this up。

 but this was my own experience doing programming on a GPU that I found I started at running it up one gigapop and by tweaking and tuning and suffering in various ways。

 I got it up by a factor of 700 so these are things it's not like I can make it 50% faster。

 we're talking orders of magnitude changes depending on how you program things。On the other hand。

 something like a data center is it very different that it's not that it sort of raw computing performance that counts so much。

 it has a lot more to do with managing data and also a much wider variety of applications so I don't want to spend all my life。

Tweaking and tuning the same program over and over again。A lot more emphasis on。

We've just got a lot of hardware， don't worry about raw speed， just use it。

 get your software up and running in quickly。And of course。

 there's a lot of companies that make their living in this kind of market of internet computing。

And a lot of applications， both commercial applications， social media applications。

 and also increasingly scientific applications that can similar to modeling universes。

 there's also a lot of data coming in from future telescopes that need to be analyzed in various different ways。

And one of the problems is there's no simple model of how these operate， they're all over the place。

 some are very structured data， some are very unstructured。

 some require a significant amount of computation others don't some have to have very perfect repeatable quality and others you can be more wax about。

 so it's much more diverse but these are sort of the drivers that the biggest computing resources in the world nowadays are actually driven more by how much power can they get for cheap than by how much can I put in a given place。

嗯。But at some level， they look kind of the same。 It looks like a network connecting a bunch of nodes。

 One thing that's different is these nodes typically have disk drives in them。

 which are considered really terrible in a supercomputer because disk drives fail and they have highly variable latencies。

 So they won't work in that bulk synchronous model I described。 And this picture is a little bit old。

 But if you open up the box of a node and a Google data center。

 It looks kind of like the inside of a desktop machine， it's got a couple disk drives。

 it's got a couple CPUs， it's got some memory chips。It's got a power supply。

 And so it looks pretty pedestrian。 It's， it's really built out of consumer grade parts。

 taking advantage of， again， this economy of scale that if I can latch onto technology that's。

Being driven by a much bigger market。Then I can get all kinds of efficiency and cost advantages that you can't do by special purpose。

 thanks。And then if you take a distributed systems course or other places。

 you'll learn about distributed file systems that sort of logically link all the disk drives across these entire cluster and give it the image of a shared resource。

And so the final part is there's a trend that both sides want what the other one has。

 that the simulation people would like to make much more use of data。

 so you don't want to just run simulations of the weather。

 you also want to take in data from a bunch of satellites and match that to your sulator data and see how well they work and adaptively refine the model as you go。

Similarly， the data analysis people are throwing in。

 actually throwing in a lot of GPUs are now custom building hardware because the rage is all neural networks。

 a deep neural networks look more like a supercomput application that you have a very regular structure that you're evaluating doing numeric computation on。

 and the training is very resource intensive， and so actually as of five years ago at least NVIDdiaA's biggest customer is Google。

And now Google is doing its own chips， so this has become a much more computationally intensive activity as well。

So the problem is if you sort of compare these side by side， the sort of way the hardware works。

 the way the runtime system is implemented， the way you write programs， they're pretty different。

 you can't just say， oh， I'm going to map Hadoop onto a supercomputer and get a great data analyst system or I'm going to use a Google data center。

 throw a bunch of GPUs into those boxes and have a great supercomputer。

 they're pretty different and people really haven't figured out how to make these both work together。

 so that's one of the challenges that even right now is driving a lot of interest today。Okay。

 so we've run out of time and I appreciate your patience and this is my last lecture。

 but I hope you all got something out of the course。

 I will say that you enjoyed it and good luck on the final exam and on your final project。



![](img/90a11b3d4307147c99ff501589970328_6.png)

![](img/90a11b3d4307147c99ff501589970328_7.png)