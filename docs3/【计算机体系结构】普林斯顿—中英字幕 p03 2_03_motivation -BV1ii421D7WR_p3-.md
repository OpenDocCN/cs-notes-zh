# 【计算机体系结构】普林斯顿—中英字幕 p03 2_03_motivation -BV1ii421D7WR_p3-

![](img/d3b749214f63d1f7cb4eb2c25bb2bbf9_0.png)

So what is computer architecture？Computer architecture， we're trying to take。

An application or something that a human wants to do。 So， for instance， calculate a spreadsheet。

Play a video game， play some sort of music。And we want to figure out how to map it down to physics。

 So what do I mean by physics here。 Well， physics is we have in the world， we have particles。

 and they bounce around。 They interact。 We have photons bouncing around in the world。

 And we need to somehow translate。😊，What humans want to do into what the physics can do。

And one of the problems with this is。This is a really big gap。

So how do you go from an application directly to physics， You have physics bocing around the world。

 You have mechanical systems， and without some level of abstraction。

 it's very hard to go from the application directly to the physics。Now。In the broadest sense。

 what computer architecture is trying to do is is trying to come up with the abstraction and the implementation layers。

That are needed to be able to bridge this gap。 So we're going to put a bunch of different layers in here。

 And by making smaller abstraction layers and smaller layers。

 we're going to be able to solve subsets of these problems and not have to change everything here in the middle。

 Just one， let's say the physics changes or the application changes a little bit。

 We'll be able to reuse a lot of the work that we've done along the way。

 And computer architecture is the study of these layers and figureiguring out how to take the physics and turn into an applications that humans want。

Now， I wanted to point out that in the natural world。

 it's pretty challenging to directly jump from application to physics。But there's a few examples。

So one example I wanted to bring up actually。Is the compass？

The compass is a nifty little device that directly takes physics and gets pushed up into an application。

 But there's very few other examples。 I think a book is a okay example of this， but otherwise。

 people build lots of abstraction layers in between here。

And one other thing I wanted to point out here is that we're trying to efficiently use manufacturing technologies。

 So what I mean by that is。When physics changes or we move to smaller transistors or we move from。

 let's say， silicon to Galllium acinide or some other implementation technology。

That changes the bottom layer here。But we want to still be able to reuse a lot of the other work that we've done over the years。

So let's take a look at the abstractions in modern day computing systems。

We start off here with physics。 We have fundamental physical laws of how particles interact。

And we move up to devices。 So when we mean by devices， we have transistors。

 and we can build different types of transistors， moss Fas， B Jts， we can build other。

 other types of fats。And we start to build circuits， bigger circuits out of this。 And out of those。

 we go and build gates。And from Gates， we can go to RTL or register transfer language here。

 which is sort of our V log coding。And then we start to get into where this course is about。

 which is。Different types of architecture。 So there's micro architecture。

 which is how do you go and actually。Build a specific implementation of a chip。Then above that。

 we have instructions at architecture， which gives us some portability on top of that。

And then we get into operating systems and virtual machines， programming languages。And algorithms。

 And then finally， we get to the algorithm the application programmer sitting on top。

So in this course， in computer architecture， we're going to be focusing on these three middle layers here。

 instruction set architecture， or what I will sometimes refer to as big a computer architecture。

Micro architectureitecture or sometimes what people call organization。Of computing systems。

And registered transfer language。 And we' well also overlap a little bit into the。

 the abstraction layers above and below here。 So wellll talk a little bit about some operating system concerns and virtual machine concerns。

 And we'll talk a little bit about how the the technology and the gates influences the computing system。

So one important point here about computer architecture is it's constantly changing because。

Different constraints and different applications are changing。

So people have new applications they come up with。 They come up with ways people come up with different applications。

 I now want to have a smartphone。 Well， that didn't exist 20 years ago。

And this pushes down different requirements。 And these different requirements actually suggest how to change the architecture。

 If you， for instance， want to do a lot of video processing that actually can influence your computer architecture So you add specialized instructions to do video processing。

Likewise， technology constraints push up。So as we go to smaller and smaller transistors。

 we'll say the smaller and smaller transistors， let's say go faster， but the wires go slower。 Well。

 that's going influence your computer architecture。And a lot of times。

 new new technologies make new architecture possible。 So what do I mean by that， well。

Let's say all of a sudden， you get a big bump in transistors。 You get twice as many transistors。

 Well， now architectures and micro architectureits that didn't use to make sense start making sense because you can。

 for instance， fit a lot more computation on one chip。And what's the interesting thing here is that。

Computer architecture is not done in a vacuum。So computer architecture actually provides feedback up and down this abstraction layer stack。

So it'll give feedback and it actually influence the research directions that technology looks at and it'll influence research directions and influence different applications that are possible。

 So this is not all done in the vacuum。 The computer architect actually sits in a very key location in in this。

Abstraction layer stack here because you can push up and push down and you're not just forced to work with what you're given。

 if you will， from a technology perspective。 but that might take a few years。

So let's talk a little bit more about what this class is about。

 but we'll do it by way of a little bit of history。

And to put a little bit of a printing connection in here。

 we're going to talk about computers back in the late 40s， early 50s。191940s，1950s。

 So here' is actually a picture of the IA S or the Institute for Advanced Study Machine。

 which was built in the Institute of Advanced Study。

 which is maybe about a mile and a half away from this classroom。

And it was designed by John Von Neyman。And to give a little bit of。

Inight here was first Bu in Prince in 1952。 It was actually started in late 40s and took them a couple years to get to get working。

 And one of the interesting things here is that。This machine is actually built out of vacuum tubes。

 So everyone thinks about transistors today， well。Before we had transistors。

 we had little glass tubes that actually looked like light bulbs。 And inside of those。

 they were switches that could be switched。 So a very similar idea to what a transistor can do。😊。

But instead， you had an evacuated glass tube and you had a little transmitter。 I was like。

Cahode ray tube， and then you had a gate that could open and close。Inside of this。

So people were building computers long before transistors and people were thinking about computer architecture long before transistors。

And people were even thinking about computer architecture and these sorts of technologies。

 even before。Vacuum tubes。 So there was electromechanical systems。

 A good example of this actually was originally in phone systems。

 They had these cool electromechanical switches。 So when you take your old rotary phone and you sort of turn it。

 and then it goes。 What it's actually doing is it' setting pulses。

 which are turning a mechanical little mechanical arm inside of a relay system。

 And people build computers out of those electromeical relays。

 So you can have switches that turn change switches， similar sorts of ideas to transistors。

 And even before that， people looked at building mechanical systems。

 So those mechanical adding machines。 for instance。😊，And nowadays， we， of course， have transistors。

So that was computing then in the 50s。 And if we fast forward to today， we have lots。

 computers look very different。 And in this figure here， you know， this thing was the size of。

 of a room。 pretty， pretty big room to give you scale。

 sort of a person is maybe yay tall in this figure， thing。😊，Its it in a sort of normal sized room。

 but still sort of room sized。But today， we have lots of different applications。

And computing looks very different。 So we have computing， let's say， in small systems。

 We have little sensor network networks and little sensor nodes distributed。 We have fancy cameras。

 We have smartphones， We have mobile audio players and iPods。 We have laptops， like my laptop here。

 We have self-driving cars， We have big servers， we have Xbox。

 And there's a lot of variety now in what computing systems look like。

 So the influence of this technology and computer architecture。 It's been very， very broad。

 And we even go on to seeing things like routers， flying unmanned autonomous vehicles。 We have GPS。

 which are little computers that can basically fit on your wrist these days and tell you exactly where you are。

 ebooks， tablets， set top boxes。 and the list goes on and on and on。😊。

And what I wanted to get at across here is that computer architecture。It hass a very rich history。

And this history is continuing， and it's very relevant today。

 So we're not studying something which no one cares about anymore。People are sitting there， sort of。

Ready to get the next generation computer architecture people。 And it used to be， you know。

 you want your faster desktop computer。 And that may not be as important today。

 But what is important is people want their faster smartphone。

 They want to enable voice recognition on the go。 They want to be able to。In scientific applications。

 they want to go to model some health system that's really complex that you weren't able to do before。

 So it continues on and on。 It is very relevant today， and it has a very rich history。

 In this course， we're going to talk a little bit about the history。 mostly focus on the technology。

 Sometimes when people teach computer architecture classes。

 They have much more emphasis on the history。 This class， we're gonna。

Touch on history a little bit of more， more focus on the technology considerations。

So here's a chart that's from。Heennessian Pattersons。

Computer architecture or a quantitative approach。And what this graph's trying to show is is。

Something very fundamental to computer architecture。And it's what's been driving our industry。

So what we see here is we see different processor designs plotted on a log plot。 So this is 10，100。

1000。 So this is a log plot。 and it is performance。Versus years。So if you look at this， this plot。

 you'll see that。Well， this roughly looks like a straight line。

And a straight line on a log plot is an exponential increase in performance。

So we've seen computing going up exponentially faster。

 And this is really fundamental to driving what's been going on in our industry and why computer architecture is so important。

And I do want to say that， you know， this exponentialial increase is comes from two things。

 It's not all computer architects。 I'd love to be able to sit stand here and say， we did all this。

 Well， no， a fair amount of this is from getting better， better technology。

 What I mean that is the lower down layersers and the implementation technology。

 like the transistor technologies。 And some of it is from having better and better computer architecture。

 And what is really important here to note is even if you have better and better transistors。😊。

A lot of times what happens if you look at this graph is what's happening is you're getting more transistors。

 but those transistors are not necessarily exponentially faster。

So what computer architects have to do is we need to figure out how to take。

Buckets and buckets and more transistors and turn them into more performance。

And that's what this is main timess called is called Moore's law。 If you've heard that term before。

 what it is， we're trying。 Gordon Moore said。That。Every 18 months to two years。

 you are going to get twice as many transistors， which you can have for the same amount of dollars。

 That was what was originally said。 People sort of transformed that noun to meaning your computers can get twice as fast every year。

 That's not what Gordon Moore originally actually said。

He said you get twice as many transistors for a certain amount of dollars。

 and people have also sometimes taken this to mean that you get twice as many transistors on a chip every year。

 not quite what I said， but close enough approximation。And one I don't quite have the graph here。

 But if you look at computing in general across， this is all across transistor based technologies。

 But if you go farther back into the past， you can actually plot other technologies like vacuum tube technologies and relay based technologies。

 And it also fits on this， this graph relatively well。 So sort of if you continue down here。

 you're going to see vacuum tubes show up。 and it's sort of still on this exponentially increasing curve。

Okay， so let's look at there's two inflection points in this graph that we want to look at。

First ones right here， you can see that the slope changes a little bit。Well， what happened here？😡。

This was the introduction of reduced instruction set computers or risk computers。

 So we got a little bit of a crank up there when people came out with the first risk。

And another thing you notice is this graph。

![](img/d3b749214f63d1f7cb4eb2c25bb2bbf9_2.png)

Keels over a little bit here。 And we're gonna be talking a lot about this in this course is what happens or why。

 why did this happen。So what， what happened here， Well， sequential performance。

 So this is the performance of a single program。Was getting faster exponentially。

 But then I don't know， depending on who you ask， I like to use 2005 is the number。

 But somewhere between 2003 and 2007。Sequential process performance。Started to really have a problem。

But overall performance of your processor still continues to go up today。

 And what happened is we had a move to multiple core processors or multiple cores on a single chip。

And hopefully， the hope is that this graph will continue on here with multiple cores。

If we can figure out how to effectively paralyze our programs。

Versus our sequential performance tapering off。Very harmful to computer architecture and the computing。

Industry， if all of a sudden our computers stopped getting faster。

 no one would be buying new computer chips。

![](img/d3b749214f63d1f7cb4eb2c25bb2bbf9_4.png)