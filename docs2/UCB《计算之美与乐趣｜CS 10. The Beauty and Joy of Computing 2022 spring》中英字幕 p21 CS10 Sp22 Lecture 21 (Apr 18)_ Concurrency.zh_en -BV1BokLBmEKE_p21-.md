# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p21 CS10 Sp22 Lecture 21 (Apr 18)_ Concurrency.zh_en -BV1BokLBmEKE_p21-

哦。Yes。Okay。Oh。

![](img/f791bda5e13aa1be57610a8ca78f79e5_1.png)

嗯。Alright， testing。 Okay。Yes。Yeah。Alright。Okayッ。不是。Yeah。Yeah。对。Alright， let me share the screen。Okay。

 cool， so。嗯。Today， what we're going to do just sort of to wrap up the last couple of weeks。

Today we're going to talk about concurrency， which will be primarily in SAP and so the reasoning the thinking about concurrency will do things in snapAP all of this technically applies to Python or almost all of it applies to Python and other programming languages。

 but for。Simplicity we're going to focus on SAP and so today's lecture Wednesday's lecture Wednesday's lecture will be about sort of the fundamental limits of computing those two things are in scope for the paper final exam that's Tuesday May 10th neither of these two topics will be on the online in lab final exam next Wednesday。

Next week in terms of lectures next Monday will be an alumni panel so we'll have a good group of former CS10 TAs some of them have been graduated for a few years now and have been working in industry others from more recent graduates one or two of them might actually still be upperclassmen at Berkeley I'm not 100% sure what our final sort of set will be but please do come to that if you come in person that'd be great a few people will be in person a few people will be over zoom so we'll have sort of a hybrid discussion。

And then in two weeks during dead week Monday and Wednesday will both be review sessions i'll be doing one of them the Ts will be doing another so you'll have opportunities for。

Well those yeah the in class final exam will be will be all snap it'll be it'll be all you know snap stuff that you've learned so far so building functions returning functions it'll basically look like a question on a midterm type thing except instead of sort of you know reasoning about it on paper you'll reason through writing some code in lab。



![](img/f791bda5e13aa1be57610a8ca78f79e5_3.png)

Today where we're going to talk about is this concurrency and this is the idea of how our computers and how our programs handle multiple things going on at once so you know in the old days sort of before all of us ran but computers are there programming and programs essentially were。

Things that just ran one at a time it was computers were slow enough that you could literally see each individual step happening they were big enough and expensive enough that you didn't have things like multiple processors and so。

You would run a program and you would see it output each step essentially or as much as you wanted to see the output and。

And for a while even if two people wanted to share the same computer today。

 we don't really think about this too much， but multiple people can log into the same computer。

 you know for the most part， if you log into like the lab machines。

 you're using account someone else could be log in virtually to the same computer。

 even though you wouldn't see their work because they have a different account。

 but computers all basically had sort of one system。

 you would have to schedule time on the computer and so。



![](img/f791bda5e13aa1be57610a8ca78f79e5_5.png)

You didn't really have any sort of definition or any model for multiple things going on at the same time。

And of course， it turns out that multitasking is an incredibly useful thing to have， right？

For us as humans， whether or not it's good for us we multitask all the time and what that also means is that our computers probably need to reflect that while a computer is just running。

 you may be using the keyboard and mouse or trackpa， whatever it is， that is some input。

 a signal that needs to be processed by the computer by whatever programs by your operating system。

 while that's happening it is probably reading and updating data on your hard drive。

 it's probably doing things。Like downloading or uploading information over wfi and in general you probably have multiple programs running on your computer at once right so right now I've got like Safari and zoom most importantly the applications which is not up here。

 but I have a whole bunch of other programs which actually me。

coupleSo I don't get any notifications but。Your computer is really good at switching between multiple things going on at a time。

 and for the most part it does this in a couple ways and this is a pretty simplified model。But。

If we're switching between a bunch of applications， so I don't have Spotify open right now but。

All right mostly what our computer can do。Is。See if there's some task to be done in some application。

 is there any keyboard input so。or is there any mouse input if so move it reflect on the screen is there some information that needs to be downloaded or shared of a Wifi which in this case I'm not using Wifi but is there any network activity and this ethernet thing has little blinking like to suggest that yes。

 of course with zoom there's a bunch of network activity going on record and save it。

Now run some of the tasks of an application， switch to another application， run some of those tasks。

 switch back and do this repeatedly and modern computers are so fast that the version of multitasking is actually just take all the things that need to be done。

Try and figure out some order to do them and just do them in some order and instead of。

Instead of doing all of the zoom tasks at once because Zoom running in the background is not necessarily an open and shut task nor is browsing the web。

 right， it is switching between things。You know just hundreds or millions of times a second to be able to accomplish what needs to be done modern operating systems are really good at doing this。

 so even though we have multiple processors multiple cores on our processors。

 sometimes dozens of them， which we'll talk a little bit about computers largely still simplify the work of doing multitasking to letting programmers think about doing one thing at a time and。

This is really useful because when you're writing a program you don't have to consider what happens if someone is running zoom in the background what happens if they're also watching a YouTube data does that affect how my program wants in reality it probably does at least a little bit affect the time that takes your program to run from start to finish but as you write lines of code whether that's blocks and snap or lines of python you as the programmer don't need to think about it and you can kind of think about this way。

You know as a student going through life right you're taking a bunch of classes you have a bunch of tasks to do you're probably only doing one thing at a time。

 even if you're sort of actually multitasking you're generally what multitasking means for a human is instead of spending an hour just on reviewing the readings for CS10 you're probably spending an hour and a half reviewing the readings for CS10 while watching a bunch of YouTube videos and what that means is you're going back and forth between paying attention to a video paying attention to a reading or something like that you know our brains are pretty darn good in ways that computers are not at sort of simultaneously processing multiple students with input but they're also not as good as it feels to us so a lot of times multitasking as a human is really just context switching really rapidly and in our programs。



![](img/f791bda5e13aa1be57610a8ca78f79e5_7.png)

![](img/f791bda5e13aa1be57610a8ca78f79e5_8.png)

It's pretty interesting to see how this works so this is an early lab right if I click on a script this bug will start dancing and I can click on this one and this bug will also start dancing and we'll sort of go next to each other and no。

Oh thank you Google drive so while stuff is going on and I can even。If I like， let's say。

We can drag out one space pressed here。And here as well。And so now whenever I hit the space bar。

 right， there's multiple things going on。At a time。

And what's really happening is SAP and our operating system we're making sure that these sets of blocks while there are two different sprites it's finding a particular order to do each individual instruction that we've asked SN to do and it is just rotating back and forth between Sprite one and Sprite two as fast as it possibly can and so a lot of the times when when talk about things happening concurrently at the end of the day there's still some implicit ordering that happens when we run our code and so that is one of the fundamental challenges of thinking about things in a concurrent model is how do reason about when something happens in that order versus out of order。



![](img/f791bda5e13aa1be57610a8ca78f79e5_10.png)

And unfortunately in CS10。Getting to world where really interact with multiple processors is pretty difficult so we're just going to talk about some of the challenges for that。

 but you know there are ways of doing multiple computations simultaneously and we'll have ways of sort of demoing some of the challenges so in this case。

In Snap， if we have two sprites that are animating between each other， we can just。

 we can see those animations， it's pretty clear that both of them are making some movements。

 their pictures are changing， one sprite doesn't really affect the other sprite。Now。

 SnAP does have mechanisms to simulate。

![](img/f791bda5e13aa1be57610a8ca78f79e5_12.png)

Running things in parallel or running two operations at the same time。

 so in this case we have two blocks these are really。

These are pretty simple blocks that we have here。So one of these is just a count down block excuse me count up block。

 it just keeps counting numbers， I believe that's just one to 26 and one of them just says the letters of the alphabet。

So。These two things each say one thing at a time for a few second or a fraction of a second we could actually see here right 035 seconds。

And of course， normally we could just execute one block after the other say all say all of our numbers。

 then we could say all of our letters now what snap provides us with is this block called launch in the past so far we've seen。

Call right， which will let us take some hire function and tune that in from some piece of data and actually execute that reporter block and。

We've seen the run block， which is analogous to call， but for command blocks。And of course。

 we could actually just verify that if I duplicate this。

It does the exact same thing what launch does is launch says tell tell this block to start being executed automatically。

 but don't wait before continuing off so launch will take these two blocks count up an alphabet and execute them exactly at the same time。

And we'll see what happens so when I click this。They're going to run both of these at essentially the same time。

 so take a second or two and i'm actually going to。And哎。嗯。

Actually we are not going to do that because this will be harder to see what happens if I add something below that'll mess up the point。

 but。Well let's just say what will happen here。If。If I run with run right it runs through this entire block will'll say all of our numbers and eventually at the end it's going to say the。

The phrase done。How when does it stop I guess this doesn't this goes further on than I thought so it eventually say done these two will run simultaneously but they each say something so if you haven't thought about what happened take a guess i'm not going to ask you to say what you think will happen but just think about it for now and what do we get here。

Okay。In this case。The sprite is very rapidly swapping between letters of the alphabet and numbers until at this point it's just counting numbers because there's number letters of the alphabet but what is happening there is snap is taking two blocks that are supposed to happen the same time and switching back and forth as instantaneously as possible between one and the other what's interesting is that snap in this case does a pretty darn good job of figuring out that there's two tasks going on and so。

It probably means that the best thing to do is to alternate between the first half， the second death。

 first half second task， but we don't necessarily know exactly how SNAP is going to handle things alternating from one to the other makes the most sense that seems the most sort of fair so to speak that if two programs are running at the same time they each alternate between their priority。

 but SAP in its own implementation could in theory choose to do something else。

 but in this case what we have is two things operating concurrently and note that normally。You know。

 we could see。The the numbers sort of stay around a little bit longer。

 but they swap they start swapping numbers pretty quickly so in this demo。



![](img/f791bda5e13aa1be57610a8ca78f79e5_14.png)

The launch block and S lets us run two different blocks at the same time。

 and SN just figures out how to swap between them。So when we have。

When we are thinking about concurrency， one of the things that we're trying to do is figure out。

How do we handle multiple things at the same time and doesn't matter if they end up with this implicit ordering behind them so in this case。

 we can normally just click two blocks。We could launch them in the lab for this week and the concurrency lab what you'll also see is using snaps broadcast mechanism you've probably used the broadcast block before。

 but broadcast is。A similar type of mechanism that launch does instead of taking a hyper function it tells some other script to broadcast some action if I go back over to SNAP and we search for something like broadcast what you've probably seen is that there's broadcast。



![](img/f791bda5e13aa1be57610a8ca78f79e5_16.png)

And there's also broadcast and weight and these two things are exist in the same way that we have launch and run because they give us control as programmers over the concurrency of error code so in the lab we'll basically say do I want two things happening at the same time where broadcast makes sense do I want to execute some script in some other sprite but wait until I have a result before continuing on broadcast and weight is probably the better the better function to use in that case because。

That will wait until that entire script is done so snap is like many programming languages gives us the tools to say do we want things to happen in parallel or do we not。



![](img/f791bda5e13aa1be57610a8ca78f79e5_18.png)

And so we have those those two functions of course in general concurrency is really handy in the same way that we've done a bunch of labs that implicitly use concurrency you've probably used it in some of your projects where you have multiple things going on at once in 2048 snapap is waiting to receive。

You know， key inputs from a bunch of different keys right up down left right。

 you can click with a mouse。In your final projects。

 you will probably have multiple sprites moving at the same time。

And the really nice thing is that SAP goes through automatically and just handles all of that for us。

So。All right。The question is， what happens when things actually should happen in parallel？

And in this case。This is of course not actually true。

 but consider someone building a house entirely solo and on their own。

 it would probably take a lot of time for someone to build a house as a person of one， right？In fact。

 realistically with the sizes of stuff that you need to lift and move you probably actually couldn't do it solo so in practice you have a team of people and if you sort of take a look and think about what's going on in this picture。

You have a bunch of different activities going on at the same time， you have some tasks， perhaps。

That requires something to be done before others but in this case we're able to have a bunch of people in this case probably a couple dozen in this photo working together to solve a problem faster than anyone could do on their own Of course we have to ask the question if we had a team of 10 thousand people building a single house could they do it faster than a team of just 10 people so to speak I don't know what the average number of people building houses but suffice it to say that for a single normal family house right it's probably somewhere between a couple dozen people in a hundred and for a large buildings right it's probably in the thousands but if we multiplied that number to just add a hundred times more people working on this construction site would things actually improve？

And in general they probably wouldn't improve that much right at some point the site just gets too crowded to work there's not as many individual tasks that can be done and every person that you add adds overhead of coordination and communication and some tasks right you just have to wait for something to be done you can't plum a house before you have walls you can't put up walls before you have architecture diagrams and engineering reviews and so on so just adding more people doesn't necessarily speed up every part of the process。

😡，And it turns out。This analogy is almost exactly the same as when we think about the programs that we might want to write now in CS10 you probably won't get a chance to write many of these programs。

 but if you continue on especially if you get to work on larger systems if you get to do research if you go take a job that's related to data science or building web applications you'll find lots of tasks that have these kind of mechanics so。

嗯。in general， we could think about tasks though that that do break up you know a little bit you know a little bit more easily。

 so I'm not going to go through all of these right now just we could get through more things right but are there tasks that 100。

000 people could do the Great wall of China is something that we can imagine is thousands of miles long。

We could pretty easily add a bunch more people to work on it in smaller segments most of the time at some point you need some coordination so you can't just sort of you can't add an infinite number of people and have a task be completed in zero time practically speaking。

 but you some tasks get closer than others。😡，Um。You're in。In some tasks。

 if our goal is to just make more of something， you can make more noise by adding more people。

 itt take it doesn't necessarily save you time， but the volume of your output is greater。

 so if you're just trying to produce more of the same thing at the same time you can usually parallelize that pretty quickly right you can imagine something like an iPhone production facility。

 assuming you have the parts which given this is 2022 is a pretty big assumption but assuming you have the parts and it takes。

 let's say one day to make one iPhone you can make and you have one assembly line。

 you can make one iPhone a day you can make hundreds of iPhones a day by having hundreds of assembly lines in the same way that if you wanted to consume a pizza if you go from one person to eight people you could eat eat one slice and roughly the same amount of time aside from eating hum。

isions。But there's also lots of tasks where。You can't necessarily speed up the process right so driving a car two people don't generally drive a car faster than one person because only one person can realistically be driving at a time I feel like marathon running things I suppose you know you don't have to sleep but you still can't increase your speed beyond what's safe or what the car will do depending on how you look at that and so the thing to think about here is that some of our tasks parallelize very well。

And some don't and we're going to look at how computers handle some of these things。In general。

Our goal will be to have multiple computers or multiple processors on a computer be able to divide up the work if possible。

So could we have multiple lab computers work together on a single task and practice is a little bit hard to coordinate。

 but if you continue taking computer science courses of CS61C。

 the sort of third course in the sequence， you get to spend time discussing and actually understanding how that communication happens between multiple machines。

U。😊，So we have a bunch of lab computers they could work together in practice what also happens is places like Amazon and Microsoft and Google rent out thousands or hundreds of thousands or millions of computers to people who run websites and other largescale projects on them and all those computers that someone rents are working on similar problems all at the same time so every person that goes to Amazon。

 co I don't know how many people visit Amazon at the same time but let's say there's thousands of people visiting Amazon you every second you could easily parallelize a process like that to have1 thousand different computers。

Responding to those requests so that everyone gets a result basically instantaneously instead of having to wait for the server to respond to one customer then waiting to respond to another and then another when site when a website goes down and it doesn't load for you it's typically because too many people are trying to load the website at once and so if you had more computers you can generally make a process go faster so how that happens we're not going to get into the details but websites data computations。

 certain things like that definitely parallelize very， very quickly。上。

One thing that we will only very briefly talk about that today。

 but you know can a single computer divide the work amongst itself and we're going to talk a little bit about how processors and how things work on the inside on the insides of computers because some of these things are just interesting to be aware of but also fundamentally affect how we're able to use how we're able to use computers so these next two slides are going to be a simplification and not something you need to fully understand the details of but just for background if you're interested on how。

In sort of how a process works。Every processor is made up of billions of these things called transistors and technically they have these three things。

 they have an emitter a collector and this base， but basically voltage flows into a transistor and when the voltage is high that's equivalent to it being on or a one and when there's no voltage it's equivalent to sort of being a0 or something being off and。

Transistors by allowing voltage to pass through them are able to represent these values of on and off and if you think about that that ends up being how we get binary。

 that's a pretty high levell simplification， but using these collections of transistors we're able to build processors that accomplish various kinds of tasks and。

And one of the things is that every transistor allows us to do sort of one very。

 very simple computation on or off on or off and billions of transistors allows us to do billions of very simple computations。

 but when we have billions of computations and we do a whole bunch of crazy stuff that is way beyond the scope of any class we take at Berkeley。

 you can actually sort of build a processor that computes useful kinds of information in so this is here mostly mostly for interests you want to watch the video。

But modern modern processor technology uses a whole bunch of design software。

 this really cool process called lithography to sort of print using incredibly incredibly precise lasers to essentially print layers of transistors on what is actually the silicon that processors are made of and to sort of build up a very minuscule 3D version of how of a processor that has billions of these elements so you can watch the video after class if you're curious。

But when we make these circuits， what modern technology has been able to do is to pack more and more transistors in smaller and smaller spaces and for us as humans that's great because what this means is that over time our computers basically get faster and faster and so one of the pioneers of processing in general。

Is Gordon Moore who is one of the co founders of Intel Gordon Moore was a Berkeley。

I believe he was a graduate of the physics program in the late 40s or early 50s because computer sciences the department。

 certainly electrical engineering， these types of things didn't really exist back then。

 at least not in their current form， but Gordon Moore is one of the coents of Intel they graduated from Berkeley。

And in 1965， he predicted that， well， first， he observed that the density of transistors had increased from roughly 16 per chip in 1962 to 128 per chip in 1965。

 which given that I've said billions are on something like the chip in your iPhone has billions of transistors。

 this is a pretty astonishing trend and his observation was。

That this trend has increased incredibly rapidly， so what he predicted was that by 1965 the density of transistors on a chip would increase to 65000。

And when we say density， what we really just mean is more transistors in a smaller area so that if you have。

 and I don't know what his exact area was here， but basically even if you make processors smaller to fit into smaller devices。

The amount of transistors that you can pack in one space。

Decreases or the amount of transistors that you can pack in a space increases over time。

 the size of each transistor keeps increasing and most of the technological advances in the past few decades have all been around shrinking shrinking the size of the lasers that print chips so that you can print more and more transistors on on a single chip and so。

What he said is this trend he thought would continue for a long time。

 and this became known as Mor's law that roughly every two years。

 the density of transistors on a chip。ul double and it kind of became a self- fulfillfilling prophecy if you write software what that meant is as a programmer that roughly every two years your computer would get twice as fast and that's not quite what Moores law says but in the early days especially twice as many transistors meant chips that were twice as fast and that was a really good thing because it meant that the more software you could write。

The faster it would become in the future that even if you had the same software in two years。

 it would basically run twice as quickly。These same kind of transistors are the things that power the memory on our computer。

 so if you have 8 gigabytes of RA or 16 gigabytes of RA or maybe even 32 gigabytes of RAM on your computer。

That RAM is also made up of transistors and so the reason that that increases so much over time is because the more transistors we get on the chip。

The the faster or the smaller we can make them， the cheaper that we can make them the more processing power we have in terms of things doubling so we've said that Moore's law that the number of transistors doubles every two years。

What kind of a？A of a growth pattern is this so it's a constant logarmmic linear quadratic or exponential so take about 30 seconds and I will pull folks in the room and on zoom。

For the answer to this question。So if something doubles every two years， what is the order of growth？

Of。Of this pattern。All right， so folks on Zoom， if you can just write ABC D or E in the chat。

 anyone in the room it' not too many today， but anyone want to vote for a。And want for B。

One want to vote for C。See anyone want to vote for D？And anyone want to vote for E？嗯。All right。

 so we've got a few votes for C in the room， we've got one vote for E on Zoom。

 not too many votes on Zoom。The correct answer in this case is E that this is an exponential pattern。

 and if I actually go back over here。This graph is lying a little bit because the scale of years is compressed。

 where it's not a perfectly linear plot， but doubling every two years。Means that it's not。

It's not linear， so I need to add， I didn't have time。

 but I will go back and at a perfect exponential graph is that at year one。

 let's say we have two transistors。Two years down the line we would have four transistors because we would double that and then two years after that we'd have eight transistors。

Trues after that we'd have 16 transistors then 32 64 and doubling if we can really take some value and double it every two years。

 meaning we're doubling the previous value that gives us exponential growth and that is the reason why over the past。

Let's say 30 to 40 to 50 years computers have gotten so much more powerful is that whether because it was destiny or because it became a self- fulfillfilling prophecy。

 the ability to pack more power or more computing power in smaller and smaller spaces in this exponential fashion has made it incredibly beneficial for us to be able to do the kinds of things that we do on computers today。

 so that one is exponential growth and what this means。

Is that we get a bunch of advantages so of course， more transistors in the same space。

 given that these things are what does the computing are good。

But what it also means is that we can do。We can have smaller chips that run just as fast so things like smartwatches would be wouldn't be possible without smaller transistors。

 it also turns out that we can make for things like servers and desktop computers we can make larger processors that have more chips in them because we have more space。

And so。One of the challenges though that comes that we can keep doubling things every two years。

 but processors also hit this issue of what we can call power density。

Or power use so computers today are incredibly powerful。

 but what that also means is they use a fair amount of power and we're not going to go through an look at this entire entire graph。

 but one of the things to know over time is that this。呃。

This graph just shows a bunch of things that happen with computers。

 so they show the number of transistors going up。But that's not quite quite as interesting。

 but what they do show is in red over here is they show the power consumed sort of leveling off in this graph stops at about 2020 so computers sort of or computer designers have sort of hit a wall where we don't want to consume too much more power in an individual computer that's。

Arguably very good for things like energy efficiency and the use of power that we don't want to waste。

The number， the frequency or the speed， so if you've heard the term four gigahertz， three gigahertz。

 that's the frequency when I can time too much。Individual chips stop getting faster。

 but what does happen is we compensate by doing things like whatts in black here is the logical number of cores or。

😡，Multi corere system so instead of having one processor。

 we now have a dual core processor or a quad corere processor。

 or if you have a recent Apple laptop that's based on their own sort of the M1 Mac。

 you probably have a processor that has anywhere from eight to 32 cores on a single chip and what this does is it changes the game。

From not just the number of transistors， not just a single processor。

 but to multiple things going on at the same timeframe and so this ends up leading to concurrency being important in a different way。

 so just for a little bit of context，嗯。U。Over time we were able to just cram more transistors into a smaller space and somewhere around the year 2000 the game had to change from individual chips to multicot chips so that's loosely what shows up in this like little inflection point right here on this graph。

And this is because over time， the amount of heat that an individual processor used。

 which is so great that。We couldn't keep pumping more power into individual processors and so one way to measure this obviously this is kind of a funny graph because it doesn't really accurately capture the amount of heat but if we talk about density processors are so small that if you measured whoops oh okay so the animations here not showing up but in。

Let's say the year 2000 or so。嗯。The Petium 6 processor was now a very old slow processor。

 but it had about the heat density of a hot plate， which a hot plate produces something like a thousand watts of electricity to warm an entire thing of food and cook it。

 if this trend continued， the density of a small chip。

Would approach some obscene things like the density of a nuclear reactor which produces a ton of heat。

 but it's very large so chip designers basically realize that we can't keep pumping more energy into a chip。

And so what they did was to speed up computers， they went to start designing multicore processors and that's where concurrency becomes an issue for us today。

 so we give more transistors， but we can't run them any faster if we're still limited by this sort of two to three gigahertz or two to four gigahertz number。

It means we have to be doing multiple tasks at the same time to able and take advantage of multiple processors running on our computer and so today modern operating systems。

Are less simple than that simplified view， but they allow us to take advantage of multiple processors happening at once。

 so the good thing here is that we get a bunch of tasks happening at the same time you know for essentially one one processor and in some cases we get a very nice speed up。

But the bad part is that a lot of tasks still don't speed up very well。

 and so we don't get to realize the full speed up。Concurrency itself can be tricky to get right and so what we're going to think about is。

Theoretically。How fast could we speed up a program？And actually， let me go to the next slide first。



![](img/f791bda5e13aa1be57610a8ca78f79e5_20.png)

This speedup or this theoretical speedup is known as Andel's law and so we're going to probably finish with And's law today and we're going to talk about concurrency and S on Wednesday a little bit more visualizing some of that but every program that we write has two parts or we can sort of simplify into two parts。

 something that we could do in serial， something that has to be done in order at the beginning that is sort of a startup task and everything else that can be done in parallel that can be split up into as many different kinds of tasks as possible。

 so。Ael's law is。It feels a little bit complicated， but it's a relatively sort of simple equation。

 which is。What is the maximum speed up that is possible for our program？And。If we have one processor。

Then we don't get any speed up， but if we have two processors。

We get some amount of speed up but we have three processors。

 we get more speed up but what Ands law says is we have to separate out a program into two parts。

 a serial part and a parallel part。And our maximum speed up is determined solely by what percentage of our program is parallel and how far can we speed that up。



![](img/f791bda5e13aa1be57610a8ca78f79e5_22.png)

呃。The real way that this is written out is our total speed up is one。

Over the percentage of our program。Or I should say it's。诶。

It's roughly one over the number of processors， so what percentage of our program。



![](img/f791bda5e13aa1be57610a8ca78f79e5_24.png)

Can weight books actually let's go back to this the way to think about Am's law and let me start that over because I started reading P the wrong way is given a number of processors the speedup that we can achieve is one over the number of processors in theory right so if we have five processors we can in theory achieve five times speedup if our program is 100% parallel if our program is 100% parallel we have five processors we could theoretically speed up our program by five times but in practice we have the serial portion and so we have to subtract out our serial portion in our formula shows up as I'll go back to one minus S and if we have。



![](img/f791bda5e13aa1be57610a8ca78f79e5_26.png)

嗯。1 minus some serial portion over some number of processors how much faster can we make our our program and Amel's law gets us to。

gets us to think about what if we had an infinite number of processors what is our theoretical maximum percentages that we get to beat things up so we're going to do one example of this and then i'll take some questions so i'm going to walk through this because the math is。

呃。Simr than it sounds if we just sort of break this down into parts。2。

If we have 20% of our program is serial， so if the first fifth of our program has to be done before the second before the remaining four fifth of our program and we think that we have an infinite number of processors。

 what is the maximum speed up that we could achieve？Inside our program。So。This question。

Is sort of the heart of how we think about building parallel or how sort of programmers can think about sort of building programs that are parallel so if a fifth of our program if if a fifth of our program is is serial the remaining 80% can be done in parallel。

What is the maximum speed up that we can achieve？This assumes that we have an infinite number of processors。

 which in practice is not really ever going to be the case， but if you have the ability to。

 let's say contract out to Amazon or Google and buy some cloud computing you actually have pretty close to an infinite amount of processors。

 so how much speed up could we realistically achieve in this example。

The nice thing about an infinite number of processors is that we can assume that that 80% of time that it takes can be done instantaneously。

 so if I can assume that 80% of the work can be done instantaneously。

Then the maximum speedup that I have is limited purely by this serial portion of our code。

 the part that needs to happen before the rest of our code。

 which should mean one over one fifth of our code would be a five time speedup so if we have a five times speedup in in our code or excuse if we have one fifth of our code is serial and the maximum speedup with an infinite number of processors is five times which should just be one over one fifth I'm going to do a couple more examples because the formula on here a little messed up so it's a little bit less clear。



![](img/f791bda5e13aa1be57610a8ca78f79e5_28.png)

![](img/f791bda5e13aa1be57610a8ca78f79e5_29.png)

But。Yeah， so。Any questions so far on this idea， I know that today was a little bit fast。For lecture。

 but questions on this idea of parallel and serial。Parts， we'll come back to this on Wednesday。Yeah。

Yeah， just explain again why we use that formula。

![](img/f791bda5e13aa1be57610a8ca78f79e5_31.png)

Yeah， so the idea here is。If I have half my program or let's say a fifth of my program。

 whatever it is， that has to happen before some other part happens。

Then I have to split up the part the problem into essentially two parts what has to be done first that has to happen in order versus what has what can happen in parallel and Ambel's law lets us say by separating a program at into these two ways I can reason about how much speed up I can get overall from the portion that happens in parallel now in a program that we write it can be really hard to raise about what needs to happen first versus what needs to happen second or third or in parallel and so in。

In some cases you might think about like if we're processing a bunch of data right the first step that I need to do is download and load in all that data and I can't do anything until I have that data on my computer but once I have that data I can probably split up some I can potentially at least split up some of the task into multiple parts and so that's the reason that we that we break this down into a serial and and a parallel portion。

On Wednesday when we talk about some of the limits I'll spend a little bit of time referencing things like our Mac and combined blocks and why if we do functional programming we actually get to take advantage theoretically of some of these tasks a little bit more easily but yeah we'll keep working on on this on Wednesday so if there's any other questions i'll take them but it is newon so we'll see you on Wednesday we'll wrap this up and then we'll have just one more topic of CS10 thank you thanks。



![](img/f791bda5e13aa1be57610a8ca78f79e5_33.png)

Thanks everyone on Zoom。

![](img/f791bda5e13aa1be57610a8ca78f79e5_35.png)