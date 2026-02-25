# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p22 CS10 Sp22 Lecture 22 (Apr 20)_ Limits of Computing.zh_en -BV1BokLBmEKE_p22-

![](img/38973c9290e59118316a19cdde220a1c_0.png)

All right。嗯。Yeah。诶，觉。うんなんだ。一し？Okay， cool， so and let me dim。Lights a little bit。嗯。

All right so just some notes self check today I made it worth three points since this is kind of it's a little bit of trickier stuff i'm going to go back through and also just make sure that like we are overshooting the self check points for between attendance and participation by the end of the semester so like next week i'll send out an announcement to make sure everyone has points but today's has a couple more questions and it's worth three points so if you're doing it you're getting more participation credit so on Monday。

I kind of messed up the discussion of Amel's law， so I wanted to reapproach that slides got messed up and then I confused myself so。



![](img/38973c9290e59118316a19cdde220a1c_2.png)

![](img/38973c9290e59118316a19cdde220a1c_3.png)

Oh， okay， hit forward too many times。Oh yeah someone asked in zm is it okay if you don't do the self checks in time yeah the self checks are open and will be open through at least the end of dead week and you can do any of them in the past there's really like there's a due date of a week after lecture just to sort of keep on track but I don't take off any points for late self checks they don't count against slip days I would just rather you do them use them as a reference to study and so on so。

You can complete them at any time， but obviously sort of closer to lecture is sort of you the goal here so the problem that we are working on on Monday。

As we're talking about parallelizing and doing multiple things concurrently and the question is like how much possible can we make how much。

How possible is it to make our programs that much faster and the way that you can kind of visualize this is that in every program there's some sequence of steps right that need to happen。

You know this could be downloading your data from a server this could be you could almost imagine this if you've like heard of like Bitcoin mining or cryptocurrency that like there's some setup that needs to happen and then you have a whole bunch of computers that do all this computation to mine cryptocurrency and then at the end you do some you know collection based on the results and so we have parts of a program where they have to happen in order what we call serial one thing after the other in process and there are parts of the problem that are in green。

That we can very evenly divide up across multiple computers in CS10 one of the things that we sort of teach you is using tools like the map block and like and higher order functions and one way that you can kind of think about this is that if you have a math block that is really complicated right where we're mapping some really complicated function over a list of 100 items that function is applied to one item at a time right it's map it's applied the function to the first item apply the function to the second item and we could spread out that computation in theory across multiple computers and so。

What this means here is that our our blue bits are the things that happen in ce and our green bits are the things that happen in parallel and so the question is how much possible can of a game come and get and。

There is a formula here， but it's actually， I think。

A little bit it's a little bit deceptive in its complexity because what we're really just asking is if I take the total time that it takes my program to run。

And I am able to reduce part of that time what is the percent or how many times faster is that so the way that we think about this is our program has two parts。

Our serial and our parallel parts and the total time that it takes to run our program is just the sum of those two parts right if I say there's a and B。

The total is just。A plus B。And in this case， it's P for parallel， S for serial。

And one thing about this sort of framing is that the serial time we can't do anything about it。

 so we just say that is the total time that it takes to run our program。

You can't do anything about that， so what happens？To the speed up。

 if I am able to parallelize the parallel portion of my program so the way that we think about this is we take the parallel portion and we divide it up over how many segments we can parallelize it over so that could be the number of cores on our computer that could be the number of processors it could be the number of computers in a server farm so in this example we took the parallel portion and we parallelize it over four computers I guess we'll just say。

 but you know that could be all sorts of things。And so what we then say is the total time is now our serial portion plus our parallel portion divided by the number of computers。

 that we have。And the speedup is just one over that total time so the example that we can use right is if our total time is 50% of our original value that is a two times speedup and depending on how you look at am loss some will ask for the speedup a whole number。

 some will ask for the ratio， the total time decreasing by 50%。

 really what that means is just do you divide something by just one over over this total time。

And and the trick that sometimes are're interested in is like assuming everything went perfectly。

 what is in theory， the maximum amount that I could speed up this computation by and what that means is like if I had an infinite number of computers。

 how much faster could I make this thing go and really what that means is that that parallel computation。

 we can kind of treat it as almost instantaneous that it takes。Almost zero time。

And what it means is that no matter how hard we try our program can't get any faster than the serial portion of our program and it's really useful to understand because if we have something where。

We have a serial portion that takes an hour long and we have a parallel portion。

 it's useful to understand that unless we fundamentally change the program。

 things aren't going to get faster than an hour like we might be able to go from 10 hours to eight hours to five hours。

😡，To close to one hour， but if we know that some portion of our program has to happen in order we're going to be limited by that number and in practice for most of our programs like they're not going to be an hour long。

 but it is useful to understand sort of what those tasks are， particularly if you。😡，In the future。

 work on large like if you study data science and you go work with some of these large data sets。

you won't need to explicitly perhaps calculate out what is the theoretical possible speed up。

 but it's useful to understand when you're writing and analyzing some data like how much faster could I could I make this happen if I need to and what is maximum possible rate that I could get so we'll do a couple examples and so what really this is showing is just that this graph here is as the number of cores or processors that we have or computers again technically right how you parallelize something there's you could parallelze it over a bunch of different systems。



![](img/38973c9290e59118316a19cdde220a1c_5.png)

But as we go from one processor， everything that's 100% time to two processors we only have the parallel portion of our code so this in this case I don't know what this is like 25% maybe 30% let's say this is 25% we go from 100% to like 75% so this isn't getting twice as fast but it's getting quite a bit faster we take our 75% here。

 we divide it three times so maybe that's twice as other now feels I don't know I don't know what the ratio up but the point is where we go from 100% to something like 70% 75% to something like 50 to 60% of our time and ultimately each processor or each core that we add to parallelize that portion more that time keeps shrinking by quite a lot but we're never going to get our program faster than what's shown in green here。

And so。

![](img/38973c9290e59118316a19cdde220a1c_7.png)

That's what Am's law is trying to capture so on grade scope I have the question from Monday but tweaked slightly differently on Monday we asked。

嗯。嗯。What happens if we had an infinite number of processors。

 but today I want to think about what happens if we have just four and if you can do know one of these you can start to translate between between the two of them so。

Let's say that we have 20% of our program， which is serial。

 What is the maximum seat we have if we get four cores in our program and whenever we give you percentages。

 you can always sort of translate these to real numbers so let's say our program takes 10 minutes to run overall but two minutes of that or 20% is done in serial what happens to the remaining eight minutes if we have for computers or four cores to process that that 20% so take about。

呃。诶。Let's say 30 seconds or so and you can think about the answer to question all of these questions today will be on grade scope I don't know exactly how far through today's lecture will get if not we'll pick it up after the alumni panel。

对。So we're taking 10 minutes of program trying to parallelize 80% of those 10 minutes。All right。

 folks on zoom do you want to write an answer in the chat A through D can just sort of all type it once people in the room does anyone want to vote for a as being a potential correct answer here that we don't get any speed up in this case。

Anyone want to vote for B as our potential speed up here？Cool couple os。

 anyone want to vote for C as our potential speedup。And anyone want to vote for D？

Any't want to not vote at all。Cool， so I saw a couple votes in Zoom chat。For B。

 I saw a few vote in the room for B， in this case B is the correct answer。And。

The way that I think about this is。There is a formula here。

 but if I tell you that something can be done in parallel is just try and sign a number and divide it up by some kind of task。

😡，If I told you that eight minutes of our time can be broken up across four computers。

 what that means is simultaneously all that work can happen in two minutes of time。😡。

And so if we have two minutes of time as our serial portion plus two minutes of time as our parallel portion。

 what we get is a total of four minutes of time to run a program。And so to go from 10 minutes。

2 four minutes we say that that is a two and a half time speedup because one over 40% is two and a half times on an exam if we ask you a question about As law we would make sure that like you don't need a calculator to do any of this math so wed simplify things numbers don't have decimals or the nice sort of around things so I wouldn't worry about like the specific math and more about this fundamental idea that as we add more processors we can speed things up but only to a point that we still have that limit no matter how many times no matter how many processors or computers we add we can never get below that that two time or that that two minute threshold and so that's why on Monday the question was if we had an infinite number of computers the maximum was still5 x and so if you were to build a product or runoff service right you'd have to think about like。

With four computers， I go from 10 minutes to four minutes。😡，With let's say。You know。

 thousands of computers and thousands of times more money， I only go from four minutes。

To two minutes and no matter how many computers you add you never would get below that that two minute mark and so it's useful to think about that because that means that you do in some cases have a fundamental limitation on the problem that you're trying to solve so。

😡，Before we continue on， I hope it was a little bit more clear about how to bridge the problem。

 any other questions or any questions at all about sort of what's going on here。Yeah。

 go ahead so the way parallel。Every computer is one part stuff。Yeah。

 so the way to thing about this is every one of these steps is happening at the exact same time and so if we had four green bubbles here。

 we would be doing one fourth of the task all this one time if or at least of this portion right if we had an infinite number of these they would just be spreading out that work all at the same time before continuing on and so。

The way to think about it is yeah that like each of those tasks happens at the same time doing a smaller portion of our work and so the total the total amount of things that we need to compute or that we need to solve for never really changes。

 but a whole bunch of it we could just do simultaneously。Yeah， good question， any questions on zoom？

This is one of those things which。The math， I think。

 seems a little bit more tricky than like the fundamental idea here。

 which is that if you can identify and we're not going to try and do this in CS 10 because in practice it can be a little bit tricky。

 but if you can identify what portion of your program has to happen before you get a result that can't be split up or shared beyond any sort of computers that can't be broken down into more parts。

 you get to understand what your fundamental limitations are。So。😊。

One of the things that we want to finish up with concurrency。Is。

Think about what happens if we do have code that is running at the same time？😡。

We've already kind of established that snap， the way that it handles things is it lets us sort of fake concurrency by always having multiple sprites that can be running at the same time。

 but it's really just handing off between sprites it's doing one task of sprite A。

 one task of sprite B and switching back and forth really quickly so。

If we just sort of think about this imagine that we have three headstrong artists who are all going to paint a door and they're all going to work on the same yeah this is going to be some like collaborative art piece each of them has this sort of following plan that they're like you know what like when I start a project I want to start from a blank white slate so I'm going to paint the door white。

And then I'm going to paint my third of the door。嗯。

And then they're going to go on and the next artist is going to come and they're going to take their plan and they're going to be like。

 okay I'm going to paint the door and then I'm going to paint my third and the third artist is going to come and it's like I'm going to paint the whole door white and then I'm going to paint my third。

And。我。2。You what can happen here right is in this model you have three people who all want to do something similar。

 but one of them could paint their third and the next person come in if they all have the same plan of painting the door white。

😡，Can erase the other person's work。This is kind of a silly example because hopefully as a human you would recognize that like you shouldn't paint over someone else's work。

 but computers obviously don't have don't have that sort of hindsight and so one of the things that can happen。

With concurrency with computers is that。We have to be careful about what happens when code is running in parallel and so we're going to simulate and snap some of these tasks so imagine now that a version of this problem we're going to draw the same smiley or the same sort of winking smiley face。

And this face can be drawn in sort of three steps right we draw or we clear the stage so that we start with a blank slate。

Then we draw the left eye， which is just a circle， we draw the right eye， which is a line。

And then we draw the math。And。Each of these things is one block just moves the sprite goes to the right spot and so on and so now what you think about it's like if I have one sprite right I can draw I can draw an eye。

 I can draw the second eye and then I can draw the face。

 but really if we look at our picture each of these three things。

Happens in a separate part of the picture。What if I had three sprites right could I then draw this entire face basically three times faster could we do that and if you think about this problem like we should be able to draw draw this picture three times faster and indeed indeed we can draw this picture three times faster so you could。

You definitely could draw this picture three times faster， but if you notice。

Something about this code， our first block。Is clear， right the first thing that we want to do。

Is clear the stage before we start trying and so。And the question is。

 if we have three sprites all drawing this code at once。

And each of their sprites has a step which is clear， then draw the left eye。

 the second sprite is clear， then draw the right eye， the third sprite is clear， then draw the mouth。

If this happens， how many different possible combinations of。

Of faces could be drawn and in our code here what we're going to do is we're going to simulate different sprites doing things in a different order by picking a random number of seconds to wait between each step if we don't do this the things that snap does the rules are actually consistent so this simulates by using pick random and waiting a random number of seconds。

This simulates basically that the fact that things can happen in different orders and it gives us a case to something that like if I know that i'm waiting a random amount of time before continuing on。

We can handle we can see more options happening concurrently unfortunately I don't have a project that that these examples are based on i'm going to try and find it and link it to the slide so you can play with it but。

And we can still sort of imagine what would happen， so given this code， we click the green flag。

We'll get one version this picture， we could get a full smiley face。

 but how many different versions are theoretically possible given this code。

 how many different possible outcomes are there， given code that waits a sort of random amount of time so if you've been thinking through it take a few more seconds and think through this problem of what are all the possible faces that can be drawn by these three sprites running the code at the same time。

And we'll give people， let's see。Give people another like 10 to 20 seconds。All right。

 folks on Zoom want to put your answer in Zoom chat。And let's get a few more responses this time。

 so what is your guess for the number of different possible outcomes that could happen？All right。

 we've got one vote， let's get a couple more votes。

Can also feel free to private message me if you either。All right。

 I let those come in folks in the room， does anyone want to vote for that there's one possible outcome that there's only one different face that can be drawn at the end of this。

All right， is there three possible outcomes， answer B？F possible outcomes。

 I want to vote for four possible outcomes。And I want to vote for seven possible outcomes。

Anyone want to vote for eight possible outcomes？not too many votes in the room。

 we get a couple more votes on zoom so I think we can get a couple more votes from from folks who are just listen in this case。

This one is a little bit hard to reason about， but the correct answer is there are seven possible faces that can be drawn from the Somali face。

And the way to think about this is。We have。We have eight different steps， right。

 we have three steps that are clear。And we have three steps that are drawing a part of the face。

 and so we have to think about what are all the possible orderings that can happen？Ideally。

If we want this face。Now where did my cursor go？If we want this face right here， right。

 what we have is we want to clear， clear， clear， all across the board， then we draw then we draw。

 then we draw， that would give us this face right here。And that's hopefully the outcome that we want。

If we think about this， what can happen is。Because of the way that we're saying wait a random amount of time。

😡，We can we can do all of block one， so let's say we clear and then we draw what is this the first block is yeah。

 draw our mouth or we can do that first。And then then all of Sprite one finishes our mouth is drawn now it's Sprite2s turn because the way that this is sort of a random ordering sprite two goes it clears the mouth so now we're at a blank slate。

Then it draws the what is this first， our right eye， so our winki eye。

And now we've got an image which has just the right eye and then our third sprite comes along after that as like all right。

 I'm going to clear a thing first。And then I'm going to go ahead and now I'm going to draw just the left eye and our final result could be that we end up with just a circle for the left eye and that would be a second possible outcome。

And we could imagine right is that if we do all spreadr one， all of sprite two， then all sp three。

 that we now have three different new possible outcomes we have。

We have we have one of each part of the face that's sort of like the the painters clearing a door before they paint。

 but what's also a little bit trickier is to think about。The orders in which different things happen。

 we could。Let's say do all of Sprite one。Where we draw the mouth。

Then what could to happen is we clear on Sprite2 we clear on Sprite three then we draw Sprite two's eye then Sprite three draws their eye and we have two thirds our of our face sort of drawn on the stage in the right way and so what this means is that we have an image where everything is correct that's one option we have three different images where we have each component of the space that's up to four。

Different possible options and now if we assume that one spray happens。

Then we have this case where two of the sprites can successfully draw the image。

 we have three new possible outcomes， we have both eyes。We have the left eye and a mouth。

We have the right eye and a mouth。呃。And that would be three new yeah that would be three new outcomes So we have left eye right eye that's one option left eye in mouth is two new options right eye in mouth is three new options and basically what we have to consider is that there are。

All the different possible combinations of two thirdds of the image being drawn correctly so in this case we end up with a complete picture。

 the three options for one third of the picture and the three different ways in which two thirds of the picture can be drawn and so we end up with seven possible different options for for what can be drawn in this scenario。

And this is one of those sort of tricky things where。

The lab this week you'll sort of practice reasoning through code with with random weights at a time。

 but you sort of just have to think to yourself if I take a sheet of paper and I list of all the possible outcomes A BC D E F what order can things happen in and in this case。

There's eight different steps， you might initially think that there are eight possible outcomes。

 the trick to realizing is that at the very last step we always draw something so we can never end up with a completely clear we' going to end up with a completely clear screen because one of these three blocks at the bottom has to happen last。

But in this case we have seven possible faces that can be drawn。

 so that's how I would reason about a problem like this。

 questions about this sort of framework of how we think about code with random pauses。啊呢。

Questions on z啊。All right， well， if there's no questions we'll continue on this is definitely a。

One of those tricky puzzles of thinking through what can happen and so I would say too is if you're working through this in lab like this is another case or grab a piece of scratch paper。

 draw all the options。嗯。So。One thing to ask yourself is if you're dealing with the sort of multiple sort of processing world。

 what are the ways in which we could prevent this bug from happening and the concurrency lab will walk you through a little bit of this。

 but one way to think about this is before I draw。The next block I might say let me check to see if the other scripts have gone through and done their first step。

 so if I start adding some logic here right I could say after I clear I could say step one is done or sprite one is ready to continue after I clear here I could say sprite two is ready to continue。

After I clearance Sprite three， a good sense variable that says Sprite three is ready to continue。

And before I then go and draw the remaining part， I could say。Let me wait until。

Not necessarily a set number of seconds， but let me wait until each other sprite says that they are ready for me to continue and this is a really useful technique that a lot of programs use to manage things happening concurrently unfortunately it's a incredibly tricky thing to get right professional programming systems constantly have bugs where they are waiting for one system to finish computing something before they can continue but the next system is also waiting for the other system to finish before they can continue and this is what we sometimes call as deadlock where two people are waiting for each other to to compute their answer before they move on but theoretically saying。

Yeah。I'm going to wait until you tell me that it's okay to go is a really useful tool it occurs all over the place in computer systems。

😡，One thing to note in Snap at least is that because SnNap runs in a web browser。

 because it runs in a tab， everything in SNap is actually happening in this sort of single thread and model and so one thing to recognize is that trying to actually split up computation across multiple sprites is not going to help you solve a computational problem any more quickly。

 we use multiple sprites， we have things happening concurrently because that's what makes games and projects interesting but in SNap at least don't reach for concurrency to solve a particular problem。

嗯。In fact。嗯。嗯。What I would say is this is just an aside。But since the question comes up。

Of how to solve。

![](img/38973c9290e59118316a19cdde220a1c_9.png)

Or how to make SAP projects go faster？I forget if this is in lab somewhere， but in Sap。

 there is this work block。And what the work block says is actually。

Don't trade off computation between my sprite and another sprite quite as quickly don't wait to do someone else's work before continuing on the workb tells staff that like I want to prioritize the code that happens inside inside the script like if I were to have you have some for loop。

 do a bunch of stuff over here。😡，The workp block tells SNap that actually what I want you to do is focus on this current sprite first before trading off and switching to some other updates that could happen so the work block can actually be a way by limiting the concurrency and S or limiting the tradeoff between managing multiple sprites that you can speed up certain kinds of code with the side effect that when you do use warp what that means is it draws updates to the screen less frequently so it'll wait Sle will wait to update and display some information and exchange for solving some piece of code a little bit a little bit more quickly so in general don't reach for concurrency to make things faster。



![](img/38973c9290e59118316a19cdde220a1c_11.png)

![](img/38973c9290e59118316a19cdde220a1c_12.png)

But you know， one of the reasons that it's still worth thinking about is there are lots of times where even if we're not solving a computational problem。

 having multiple objects working concurrently is really helpful snap。

 if you give it a forever loop or these hat blocks， you know， that say like one green flag click。

SSttaamp for the most part， tries its best to make it seem like it's very seamless that multiple sprayites are working at the same time with kaleidoscope at the beginning of the semester when you move your mouse。

You know， SNap is drawing updates for one sprite， drawing updates for a second sprite。

 the third sprite and the fourth sprite， but computers are so fast that that happens know virtually simultaneously and you don't really have to think about what's going on。

 what's going on there。So before we continue on to talking about some of the limits of computing。

You knowThe main thing I have to take away here is that doing things concurrently is a super useful important thing for programs to be able to do but。

It's a really hard thing to get correct so ultimately in CS10。

 the programs that you write you don't need to worry about。Concurrency in your S or Python projects。

 but if you continue on taking computer science， it becomes a pretty interesting program or problem that you can wrestle with。

And because of this we have lots of tools to sort of fundamentally understand currency and because computers get so fast it becomes a challenge that we really can take advantage of to make you know modern programs and websites and things feel like they work really really quickly if you take computer science courses CS61C it's called machine structures and you can think of the classes sort of bridging the divide between hardware and software is a really。

A really interesting place where we get to understand at a very low level how to implement and design around it and address some of these issues so before we continue on and sort of context switch any questions about yeah concurrency yeah go ahead does。

Yeah yeah it's a really good question so for those of the question is how does a computer know how to how to handle multiple programs running at the same time if things go line by line there's two parts of this。

One is that your computer and indeed sort of any computer is really good at just rapidly context switching between things so one of the things to recognize is that like。

What you see on the display， right， whether that's one monitor， two monitors。あ。

Your computer is constantly doing some work in the background to make sure that that display is always up to date with what should be presented and so that's a process that happens。

Dozens of times a second。To do all that work and computers are so fast that we just don't even have to think about the fact that literally refreshing a projector like this is millions of computations a second to calculate pixels and colors and fonts and wherever everything should go but behind the scenes computers can handle essentially billions and trillions of operations per second that do work and now that computers have multiple cores in them。

 what's often happening is you have a tool like a GP or graphics processor that's handling just the display you have a multi corere processor that's handling things like wfi。

And sending that information back and forth and that could be happening in one in sort of one piece of your computer and then another part of the processor is managing something like Safari or but ultimately at some level there's so many things going on at the same time that the computers just doing five instructions of sort of five lines of code of whatever your web browser is doing then it's doing five lines of code zoom and switching back and forth so quickly that you don't even necessarily realize the fact that it's not doing things one at a time and languages like Python and snap and stuff the way that they interface with the operating system is。

You they don't necessarily have like you don't have to always say wait until i'm ready the Python environment sort of just handles that for you the environment that snap is the browser just handles that for you so everyone gets to sort of think about the world as being the straight linear set of steps even though in reality what the computer is doing is quite a bit more complicated there are certain things where you really do need to take into account that certain processes can take a long time。

So in Sn when you if you've ever seen the URL block to like load in a web page S when you use that URL block will just wait for you it'll just say you know you probably just need the result of this URL block and your sprite doesn't continue its computation until that result happens behind the scenes making a longer process like that happen takes a little bit more work so sometimes programs get more complicated to handle to handle concurrency but for the most part。

 a lot of the code that you write even as a professional software engineer you can assume it sort of just a series of steps unless you're working on a specific kind system。

But yeah it's it's a really interesting a really interesting sort of challenge to think about how how much is going on in a computer all at once and also you know I mentioned a processor and a graphics card。

 but every computer now has like，Dozens of specialized essentially mini processors to like wfi is a wfi card has its own little processor that is handling that signal which is communicating with the main processor and so you know what really looks like one big computer。

Ass a bunch of miniature systems all trying to communicate and talk to each other as well。

 so you know there's even more going on sort of under the hood than just whatever your programs are doing and so。

That's yeah， it's a little bit more about how that works before I actually continue on any other questions about concurrency or this idea of multiple things happening at once。

Cool， so for the last few minutes today， we're not going to get through everything。

 but and so I'll pick this up next week。We're going to talk about what problems we can solve and what problems we can't solve in computer science。

This is another one of those things where there is a fundamental limitation on the approach to certain kinds of problems。

 so remember a while ago we talked about orders of growth for an algorithm。

And suppose without knowing anything about a particular problem。

 we gave you a question sort of what is the best order of growth that we could have for any particular problem。

 like if we could choose how fast this thing would be。

 what would we choose does anyone want to sort of shout out or guess or on Zoom。

 if we had our choice of options between linear quadratic Cic and exponential。

 which of these options do we want our programs to run if we have a choice？

Someone can just shout it out cool we've got one vote in zoom yeah we want we wanted things to run in linear time right as our inputs grow that means it doesn't take much longer to run our program but we don't always have that choice and so。

One can sort of think about what happens。This is sort of assuming we're not able to parallelize something。

 so don' don't't think about this question in the case in And's law。

 but let's say we have a company that has 100 users。And each week we run an algorithm that。

For those users that takes a cubic order of growth。

 so with  a000 users it takes one day of computational time to do some processing on some data。

And we said that this this algorithm takes a cubic order of growth。

 what happens if we now grow to 10，000 users？How many。

How many more computers do we need such that our problem。

Could still happen in a day that that so I should say if we assume that we can parallel I kind of first off。

 if we can assume we can parallelize this question， don't think about the speedup。

 but how more how much more computation would we need to sort of keep that to keep that time happening in the same way。

That if we go from 1000 users to 10，000 users。How much more computation is necessary when our algorithm is a cubic time and the way to think about this is just to sort of say what is the growth in our number of users。

We went from 1，000 to 10，000。So that's 10 times。As many users for a cubic order of growth that means we need 1000 times as many computers to solve this problem or we need or itll take 1000 times longer to solve the problem in general having this question published has been separated a little bit further away from Amel's law what that means is that we would need 1000 times as many computers to solve this particular problem and in this case。

100 computers for a large company might actually be something if something potentially reasonable。

 but it also kind of sounds like that's a little bit unreasonable in terms of the cost that it takes to compute something and so earlier in the semester。

We had。We talked about orders of growth and one thing that gets that we sort of classify。Is that。

If something is of what we're going to say within cubic time or within sort of something some sort of polynomial time。

 we'll talk a little bit about that， what that means don't worry about the math terms。

That as the numbers grow larger， these are things that we can still roughly compute it's not ideal like taking a thousand times longer。

 you know， that's kind of a lot of money if you're paying for computers。

 but it's still a solvable problem。But if something。If something takes exponential time。

Then we start to get into this place where。It is almost impossible to solve a particular problem in a reasonable amount of timeframe。

 so if we think about。For exponential time， let's say something like2 to the n。

That if our input goes。From N of 30 so that would be two to the 30 operations to and of 50 we go from。

18 minutes to 36 years just in one step right here looking at this column and what this means is that there are whole classes of problems which unless we change the problem that we're solving we cannot actually get a solution in a reasonable amount of time it is theoretically possible perhaps to find a solution but we can't do it in a reasonable amount of time。

You've seen this perhaps with recursion when we talk about the Fibonacci series。

 which you can nicely implement recursively， but it's terribly slow and so that limits。

How much you know could we could solve that way， but it turns out something like the Fibonacci series。

 there's a much easier non recursive or I should say a much faster non recursive version。

I it doesn't have this problem， but what we're going to do is sort of divide。

Divide our problems into easy and hard cases， just based on the orders of growth。And so。

What we do is we call these things tractable problems and these are things where the order of growth is some kind of what we say typical polynomial expression。

 so that is x x squared x cubed， you could say x the fourth although we don't really talk about you that particular case too much。

 but it's saying is that the order of growth even if it's slow is within the order of growth is it basically not exponential。

 it could be even faster， it could be logarithmic， but there are things that if we draft。嗯。

That our order of growth is n to some power of in this case B。

 but it doesn't really matter what it is， but so all those things count are quadratic。

 what we're saying is that the time that it takes to run our algorithm，Is within and spread time。

The time that it takes for some algorithm， we don't talk about this case。

 but there's a lot of algorithms that run an n times log n time if you take CS61 B。

 you'll see examples of those。But if there is some algorithm that runs in。True to the end timeframe。

That end is is now an exponential time and all of these algorithms。

We want we want them to be what we call sort of in polynomial time and this is just kind of a funny distinction that computer scientists make but we say that these problems are NP because they are solvable in polynomial time and so。

We're going to leave it there and say that we have these problems which are solvable and some weeks are not and next week well finish up with the idea of trying to understand what problems are so hard that even if we know how to theoretically solve them we can't actually solve them with the normal computer so if you're curious you can look ahead on the slides。

 but we'll finish this up next week， and with that we'll see you next week please on Monday if you can make it in person there'll be a few people here in person for the alumni panel。

 there will also be some folks over Zoom but you'll have opportunities to ask questions of a bunch of alumni from CS10 some of them who are more recent than others some of them who have been in industry for a few years so if you want to come with questions on Monday that would be that would be great。

Thanks everyone。I'll see you next week。

![](img/38973c9290e59118316a19cdde220a1c_14.png)