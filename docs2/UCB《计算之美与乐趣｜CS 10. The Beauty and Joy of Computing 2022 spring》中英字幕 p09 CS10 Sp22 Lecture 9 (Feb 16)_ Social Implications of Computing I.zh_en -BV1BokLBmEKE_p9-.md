# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p09 CS10 Sp22 Lecture 9 (Feb 16)_ Social Implications of Computing I.zh_en -BV1BokLBmEKE_p9-

![](img/103246804d2aac6c109760fcad9eea08_0.png)

All right， I think it wonoo。Yeah。Move this to that screen。port。And okay， that's a night screen。

That's good。Yeah。Yeah。We shall。あ。Yeah。今。はい。对。Yes。Yeah。Yeah。嗯。嗯。

Just in case Ill have red opens with your time for it。Yeah。Fish。



![](img/103246804d2aac6c109760fcad9eea08_2.png)

Insure。最是。

![](img/103246804d2aac6c109760fcad9eea08_4.png)

What I was hoping to do today is to。S from。嗯。transcripts。你这。So I was going to finish up。

Algobemic complexity today from。FromFrom Monday's lecture。And then go into the next project。 Well。

 the next assignments are Project one of CS10。P which is 24 week。And 2048。

 if you haven't played have not played the game， I will go through it a little bit。

 but it is a idea is one of。第嗯。More fun projects and the sens of its， it has challenging aspects。

 but it's definitely one of those things where as you progress your way through the project。

 you get to start playing a game that you've built a game that is wildly popular。

 this is a project which。This first prototype the first semester that I taught CS10 in the summer many years ago。

 so it's been out a while。It's a。Well the bugged project。

 so I think we've over the like last few years really gotten down to a point where there are challenging aspects。

 but it's a place where you get to demonstrate and practice the things that we've been talking about over the past few weeks and of course。

 as you build your game。You really get to spend time playing it。Throughout your time。

 if you take computer science courses。There will be moments of projects where。

Some of them blue not so away from so and others， as you build them。

 you'll just find yourself spending as much time。Playing the thing that you've built。

Instead of just working the assignments。And that can be a really fun experience when you get to that point。

We'll hope to get to that。So what I want to finish up with from Monday is one。In this lecture today。

Is the last few bits of thinking about how we analyze。Or is of growth in。

Inter functionss and the types of things。That we're looking for I'm not going to go through the grade script questions today。

And I'm going to good for these first few slides。Remember that when we're talking about orders of growth？

😡，What we're trying to think through is。How do we take a？An algorithm。Whether it not we written it？

And try to understand。I is the length for this ingr， so for talking about a list。

 as my list goes from 100 items to 1000 items to me items， how much longer does it take？

That function to compute， does it grow。mean your fashion right here。

Going from one item to two items is twice as long， does it go in some really slow fashion where if we double the line from our input it only takes a little bit longer。

And we have something like this full loop。And what we're really sort of thinking about is each iteration of this for loop is one computational step。

AndThat means that if I add another item to our list that that type of thing would grow in this case in a linear fashion。

Talked about。First question here so the grade scope points for lecture seven are still there。

 I'm not going to go to the very last one。Live， but it'll be up on Gr Scs still。す？

For each person X for every other person Y。When you start to see something like this。

 we should start to think。I do have to do something x times and for every I have to do it y times and so we have this x times y number steps。

😡，Another question is， how do you relate these x and y？my phone loops to decide the input。

And in this case， they're basically just or input sizes。We said this function would be quadratic。

Because we're doing something。Thank you and。Times end timess。

It's not quite in times in if you really were to do the math。😡，You could figure that。

N minus1 times n times， but that's basically just n squared in that case。なか。We started talking about。

😡，I really left off was this idea。Research。And in， what you hopefully saw was that binary search was an algorithm。

That。When do。你的。And you're comparing it to。Let's say our lu search for something was not in our list。

That on average， this algorithm performed much more quickly that it was a lot faster to find items。

our list。And what makes binary search special in this case？

It's because binaryaries are are out there。It's because binary search is a logomic function。

Lo withic analysis is something that can be a little bit tricky。To determine。

And so I'll just go through some of the intuition in verse and well revisit O of growth throughout the semester a couple times and just coming back to this idea right now we're not expecting you to take an algorithm like binary research necessarily outside of a lecture and come up with the fact that it's algorithming。

What makes binary search logmic is this nice property that。😡，Every step of the way。

 we have a list of， let's say， 100 items。After step one。

 we focus our attention on half of the list so it's either。Sft0 items for the last 50 items。And。

That means that we're essentially cutting the list in half right。

 we not actually making you list splitting it up， but we're saying our midpoint door our left and our right values。

 whatever you want to call on。Our start and or end that we're focusing on is if our number is bigger in that 50th item right。

 we're going to focus on the latter half of the list。When we're smaller。

 we're going to focus on the first capital list。And so what binary sector is good about。

Is this idea of taking some data split you into two？And allowing us to efficiently use。

Spitting function to find information， to find the value again， as long as it're was distorted。

We can do it， so what happens now？O from 100 items。0 itemsWell our first step is to then say。

Is our value bigger than the 10th item was it smaller than 100th item so by doubleubling the size or our input with binary search。

 it only takes one additional step。To get back to a previous value of。Of our。

So if we go from most of 100 items， it's not 20 items， it's really only one extra step in our loop。

Binary research has to operate through。And that's a really awesome property because what it means is that。

If it's really quick on 100 items， then 200 items is only one additional step， 400 items。

 it's only two additional steps， right 800 items， it's only three additional steps。You can see how。

Our list can go really quickly without having that much traditional work。

 and that's our binary search。an algorithm。Once you know to look for it finds variations across all of computer science。

あの。This is the thing that makes searching for files on your computer really efficient in a slightly different way。

It's the thing that allows in various forms。Websites to search data when you type in the search box really quickly。

Obviously， at the scale of Google。Additional complexities going on to make Google as fast as it is。

But in general， an algorithm like binary research that's taking some ordered set of data spring into two parts。

Is a super useful piece。This one has a large grid property。

And that's because we get this function of splitting the data。And have something that is。

Not algorithm we can apply every data set， but it is a really useful， really awesome property。看看。

This question is not on grade scope because it is a tricky one to think about。

I want to just illustrate。How we should think about orders of growth。

And the trends that really matter。A couple lectures ago， when we talked about lists。

We talked about this idea of sorting data and how there' are multiple ways to sort data。

And one of the algorithms that we talked about。😡，We called selection sort。

fact that it's selection versus any other sort that's only matter in this case。

The process roughly went， find the most item in the list。Item to the front。

And repeat that process for the remaining。N minus one items of our list。

How do we think about analyzing the run time？A function like that and again。

 this is a pretty tricky one。Hing the small sign in the list。

We know that we can just run through a list。We had a black lecture that said found the smallest item。

It's basically for each item list。Keep track of the smallest thing， which are the small sorry。

So that is a linear process。We have a move that item to the front of the list。

Tell you that this is a constant constant time process that it's just one step where in SAP there's actually in。

To list block ats the end if there's an insert item one which adds something to the beginning of list。

Fox。Each take one unit of time。We can tell you that something like that is constant。

The fact that that's constant is something that you kind of need to know how SNAP works。

 but we would otherwise we tell you that。One the interesting parts is repeat this process for。

the remaining items so n minus1 times。This is we。这。S。はい。

What we should think about is we have a linear time process， finding the item of the list。

 we have a constant time process。And。Now we repeat that again。For every remaining item of the list。

This essentially means is that we again have。嗯嗯。Times and before we do something。

We iterated the list for each item。Was the job， so。

N times n we see that repeat loop and that tends to mean that something is quadratic in this case what's something that if you go back and lecture slides that you look at。

😊，お戻したい。What你。Looking at selection sort is it's just a full loop。Where it says you know， for。

One point of this， something like that。嗯。And it says fine smallest item。

The trickyrick is that within our loop。😡，If an inner function takes linear time。

 you still have to multiply those things together。This block would also be quadratic。

And it's one things that over time we'll start to look up a couple of additional examples。

This question is on grade scope。I'm going to walk through it now。

 I'm not going to pull it up today just so we can spend time on 2048。

Now we tell you an algorithm that。😡，呃， is。Is trying to find is an item in the list so if we didn't know that the list was sorted。

 we could just run through it linearly。😡，W say a you algorithm right now is first， sort the list。

We use the really fast binary search to determine。s our algorithm。Is the item your list。

Does it make sense to do something like this is to take a process？

It might be a little bit slower to then use a process which is really fast。

So what would the running time？Of。This kind of obscure。The item is on list function should be。

This one is quadratic， and this is the thing that。Why running time analysis really can matter for some what function is。

It's not just that we're doing a fast operation to。YouSee if an item is in our list。On the whole。

 I had to take this whole long point of time to sort a list of data。😡。

Before using our FAA binary search。In this case， what we could say is the bigger turn winds or the slower turn winds。

 they are quadratic。Is much slower than logmics， so that's the。スデ。Part that we care about most。

 right is。The thing that slows your function down。When we have multier processes。

 we always have to consider what is the slowest part？Function。

Before before moving on so what if you about this right， is that like。a step in process。

 so the example on slide is if you need to drive to Tahoe。You know。

 it takes about two hours before you actually make that drive。You have to do a small set of steps。

 like get dressed and put on your shoes。Before we actually get to Tahoe。And those do take time。

 right like in the real world， you can't know the time that it takes to get ready。

The drive is so much longer than the time that it takes get ready， hopefully。

That you could ignore that step of the process because in practice， it doesn't affect the end result。

And so。That is one of the big ideas with one time analysis。あ。Ro term is sort of the final result。

 but if we have something that's quadratic and something that's linear。

 it's always the quadratic part is the thing that we care about if we have something that is。

Linear and something that's constant， we don't really care about the concept how we just care in that case that it's linear。

我已经啊。Fction mutation， this is something where。Oh。We've been using it sort of in the abstract。

 in CS10 we'll stick to the words on the left hand side。😡，Do want to。

Read more info or start looking online or look at maybe something at 6 and E has。

 what you'll start to see is this a mutation called big O mutationation。嗯。And it's one things that。

It's really。Easy for professors and like internship interviews to come up with questions about big annotation。

So we'll find it in lots of places， but roughly what we're saying is。

How can we think about the format of what a function is so constant time is order one。

 so it's just a constant factor。 We replace the R of N。An F of n notation with a。呃。

With just the term so Winer is of N。あ。Mar Rk is like and quadratic is Anne Sw。😡，crential is。

Or oh exponentials on the slide should have been factorial would be n factorial。

 but essentially the o of n means。s the worst case performance of this function？

Can you write it in Mr。 Charminson？If you want to refer to it， this is a handiny chart。

Not necessarily something that。That you need to memorize。So。The big takeaway here is saying。

 sometimes algorithms are faster than others。😡，And in some cases， it doesn't matter。

 but in a lot of cases， this can be a tool that helps us understand。

 is there solution to the problem something that is acceptable that we can contend with？And that。

We're really trying to do in a lot of cases is find the。The overall， we can see the shape。Or。对。

The speed of an algorithm without innecess building money is looking at that code。

 thinking a little bit more theoretically about。😡，What we're trying to write to what we're trying to solve for and how that affects the running time So before we getting into 2048 in testing。

😡，There's probably a few questions， so if you have anyone on Zoom hasn't turned in yet。To feel free。

Questions in the room about anything orders is of growth related。对。And from miss San Tamp。

 feel free to shout out。so I guess remind one， this is probably the most massive that CS10 gets。

We're not looking for a rigorous mathematical analysis of any algorithms。

Hopefully some people find this interesting if you do， this is definitely a sign that after CS10。

 you should consider62 and A， 62 and B。嗯。But the point is much more to introduce the subject than to。

You know， practice all the matters， so before we on I'm curious by short of hands。Who's played 2048？

Cool， and I'm zoom， I don't know if any of you all want to react， yes or no or handss up just too。

That a sense。Oh， few more things up in Zoo， awesome。Yeah so。2048 is a really fun game。

 it is one of those games that is。😊，Simple and yet can be really sort of aing in sense。Okay。

There you go。2。There is a fun history around 2048 as well。If you have an iPhone， unfortunately。

 the game that 2040 is based off is this game called Thrs。But I believe it's in the app store。Still。

Threes was a really beautifully designed game by。It was actually designed in part by the guy who invented the pulled to refresh mechanism。

 which there was a time maybe most of people in here don't remember this but were。Well， a。

 theres a time to smartphones， which is legitimate hard around it。

 but there's a time when a smartphone you couldn't actually pull the like refresh email or a web page or something。

So。The guy who invented that mechanism also invented the game freeze， which became the game in 2048。

嗯。And that's kind of just a fun rain bit of convenient history， so 2048 is。

Did you know a very simple game？So you have four controls right up down left and right。I press up。

All the piles slide up to the top of the board。😡，And a random retail。Is added to the。

To the board in that direction so。The rules for where target added are going to be described in the specification。

If I hit up again。This tile now slides up。In， your two tile appears。And so now as I hit up。Well。

 that wouldn't be very exciting， so I hit right。Yeah。And when I hit the right。AOG。

 we see something interesting happened which is。Each pair of tunes merged into and became a4。嗯。

And so every time we merge， those two numbers add together and then our new tile becomes the sum of。

Those two tiles。So I can hit the right arrow again。The two fours merge together。都 be。

The two slides over， I guess that way。And another new title appears。On on the screen。

 someone shout out a direction， What should I do next？All right， can you have the direction right。

 up， right， right。Right。Let's go left。Right。Right。Up。So you can see that 2048 is。

The mechanics themselves are pretty simple。But the gameplay can be pretty engaging there isn'。

Next strategygy to 2048， it is one of those games that you can really quickly just run through a game。

By buttontonashing up down left the right。If you really care。

 there's a slight strategy to trying to push everything generally into onek one corner。

 but the point of this project is not to implement necessarily any particular strategy。

 it's just to get。A working game。That's how 2048 works。So when I come back to the project in。

A few minutes so the goal of 2048 sort of the CS1 version is to give you a chance in S。

Practice a thing that。We can call decomposition， so we've broken 2048 down。

Into five blocks that you need to complete。😡，こ中？Make this game。

And what you're going to be focusing on are all the mechanics of how that game board works。

 how we add tiles， how we handle logdging columns together。And so on。And really what this game is is。

An exercise in how we decompose a difficult problem。

Into a bunch of smaller and easier to reason about problems。

 And so I'll start one of the first examples that you'll do for part one of the project。

I'm not going to finish it， of course。あ。And the full spec will be out later today or tomorrow。

And there'll be plenty of time if you're still finishing up homework too。

 we do now insist1 sort of delineate between homeworks and projects。

 homework assignments are of course a little bit smaller than projects but a project is meant to encompass the fact that。

あ。It's a little bit more work， but it's also theres more code in theory to reason about some of your home assignments。

In general， what we can say is even a game that seems to as simple as 2048。😊。

If you just wrote out one giant script， let's say one green F click， do X，YZ。

Re one giant script to ahead of the game without using any custom blocks is possible。

 but it's really a lot to reason about in。😡，In one go。Part of 248 is that。

It's a game which we can decompose into smaller pieces that are much easier trea out。

 and so all of the logic of the game can be implemented in just about five blocks。

Hopefully for all of you， you'll actually build two or three additional hyper blockss。To。

You to help solve some of these pieces and I'll show you maybe a trick for one of them。

Decomposition this idea baking plumed down from parts。

 this is arguably the most important part of computer science in general，😡，Soft engineering。

 when we talk about testing functions， when we talk about understanding how to analyze algorithm。

 why higher functions are important is breaking problems down such that we can use them in multiple places。

This is the first block and allll go through an idea。Of how we might start thinking about this。啊So。

For those to decompose。This came into smaller functions and for the most part。

 the CS10 staff are the ones who have iterated on this decomposition for you。

Even for a group of people who built the game。It took a few semesters to iterate on the best way to break this down into what is now about five blocks。

当然了。And so this is one of those things we're practicing working with this。

Is a good way to understand the game so first block。Is add to or for。

And this is really a really and difficult talk。2。Yeah， and it has some notes here， 75% chance。

ItAdds two to an empty random empty space on the board and a 25% chance that adds a four to a random empty space on the board。

What you should be thinking about。It's。Well， are。A lot of different ways you know potentially of things that go on here。

 so we have to pick a two or four， we have some probabilities in here。

We have to find if a space is empty， we have to add a space to a board and then now we haven't seen anything about how this project works。

 so some of those functions will be easier， some of them will be harder but we'll take a stab at。

I'd starting this。The second thing that you'll work on and these are definitely。は。

that if you're working in new order that we suggest。

You start to practice with the different components of the game。Is rot the board clockwise。

This is the really kind of ingenious algorithm。OfHow 2048 works。Yes。We take this board。

We'll see is represented as a list of lists。Reated clockwise， such that。Everything that is on。

It's top blue。So this。嗯。16 over here when we rigid it becomes this right column。😡，And。

As soon as this ability to rotate the board actually simplifies the logic。

And in in some of the next steps， so this block every time we call it。

 we get a new game boy which rotates。😡，The board by 90 degrees。W what we have？Is blockchain？

Is what is probably the most challenging。Our aspect of。This project is large column number。

And this is meant to be a challenging block。What a goal right here is to say。These two16s。

 right when we merge this one column upward。And all we doing is one column at a time。😡。

We replace them with a 32。This4 then moves up。Into the next spot because everything else slides up。

the project spec when it's out， we'll go through all of these details of exactly what steps of Blackbes to do。

This book。Only works on one column at a time。And so Abi this block。The next block we need to build。

Is the merge up blocklock in general， which merges up the entire game board。

And withoutre doing anything about the spec， you can probably see。I might go from merger and call up。

Tomer the entire board。😡，ThatThis is one of the benefits of decompposition。OK嗯。Right。

When we have a game board like this？그。this thing。We can solve a problem like merge up。

wouldn't come at a time。Which is still challenging。

 but would be simpler to think about the merging the entire board at once。

You can use that subprom to build。The emerge entire border。you got black free。

This block floor actually becomes pretty darn easy and some of you will probably able to think about exactly how。

嗯。handlele back so。ThatNow the final block that you need to build is the new move stuff block。嗯。Yeah。

 yeah， yeah so when's left it returns true essentially when the game is over when you can no longer。

Add or move or merge a block。Yeah。In the game， so we could see。This bottom gameboard here。

 which is just。Sort of generated for the purposes of visualizing and testing this。

With that windowo is full flight and there's nowhere to merge anything。呃。

Reports true that there are no left if there's a bunch of empty spaces。

 if it could potentially merge some numbers together， this block reports false。Oh。Which is。

This block will guide you through how it is， but this is sort of medium。

 maybe a little bit harder than mediumn difficulty。Does you just think about it without。

Of the hyperer functions。😊，Without any of the scaffolding that's built into the respect。

 it actually seems like kind of a hard problem， but I hope is by decomposing the game。

To a bunch of smaller pieces。This block becomes a little bit easier to manage。嗯。

Go for 2048 is not just to get a practice with this kind of programming。

But to also think about how we start testing code in an environment that is in some ways new to us。

We set it up， like say you don't have to understand any of the drawing mechanics。

 how up down left or right necessarily themselves， you know how Sn handles that piece。

 although that's fairly simple。We want you to go through and test out each individual block。

 so on its own you can verify whether or not it works， we want you to get a sense。

Wning the whole game of course and verifying that， yes， I know that these five blocks work correctly。

 but I can also pull my game， I can verify that the whole project works together。And of course。

 the other way that we could test our code is to just submit it at the end。

 wait for someone else to grade it and give you a score back。

This is kind of a valid testing philosophy， but it kind of sucks for a project。

It kind of sucks in the real world， right if you built an iPhone app。

You never tested it and you just waited for someone to download the app and give you a one star review and say。

Hey， this thing doesn't work。It's kind of an annoying testing process， so we try not to do that one。

 but it is sort of a way of thinking about how do we know if archive code works。嗯。

And our goal here would be to write。To use a block which tells us whether or not our code works and this block will seem a little bit like magic。

 but will。あ。🤢，We'll have a sense of。How to build it so we're going to start by demoing adding two or four and so this spec will be out fairly soon。

It looks like the other specs， but it really demos。Its through all the aspects。

Blocks that we've given you so one aspect here as well is to just get practice reading through some documentation about tools that we've given you right these blocks are how the game works。

Theres a block display number。And then broken down into each part， the blocks that you need to build。

Complete。Along with some snap tips。

![](img/103246804d2aac6c109760fcad9eea08_6.png)

We're going to edit this project。So when you start with 2048。Going to clean up the colors of the box。

 so it's a little bit more clear。What exactly we need to do。Right now they're all gray。Take look。

But there will be a category here called 2048。That will be just the blocks。

That you need to build so if I click。Green fog。So like now that nothing actually happens in this case。

 actually， let me change the settings。Because。There was want some stuff。🎼ま。嗯，是哪的呢。呃，是。

We have a few blocks here that。Are going to be pretty helpful so when is there's this update display block and we'll talk about how that works。

2。🤢，And another is。We've set up the actual game mechanics for you， but you really don't need to。啊。

Necessarily。Understand or use these if you'd like to inspect。The spites over here。

 so we have one sprite here that controls the gameplay。Some of it's a little bit complicated。

 but it's not。It's not terrible if you want to spend time reading it you can kind of see when you think about like right。

😡，W is left。Versus up and down， how this rotating part of the algorithm if you read the code actually works。

It's a really clever solution for handling。Four different functions are four different operations with only two different blocks。

😊，So we're not going to get into that too much， but it's definitely something where if you'd like you explore how it works。

 but our goal today is to see how can I think about testing this game board？

How can I start to understand what happens so if I just click add to a four。Snap just， hey。ですね a。嗯。

Because it was expecting a list to not say getting number that is。Or is that actually correct？

And that's not really correct。So。啊。Fix that later so we have a block our task will be to finish。

finish this box so add to a4 to some game board and we'll start to think about what that looks like。

 but before we do that let's just think about some of the things that we have so we have this upt display for game。

And this is the part where it's worth。I going to make a new script variable called Testboard。

And if I look through the blocks that are given to us。

There is this really large block called a new4 by four board with certain values。There is。

This block called set。Two inputs of the board to some value。 So every time we see a list style input。

 we're going to think about that as a game board。Oh and。Is a useful block。Where is it？哦。

Just a new board of size4。So this is kind of nice， this newwater size forward just gives us back。

Okay， what was going say？This gives us back a full before grid。Of zeros。And。Now the trickle be。

 how do we think about？mussing。And playing this game soup。What can you use this new border size for？

So one thing we to do right here is just click this。So far this works。

 but we don't see anything exciting。That probably makes sense。So what we're going to do。

Is we're going to set。Our test board。To a new board of size forward。

We're going to display our test board and know what we want to do。Is replace some random items。

And our board， so I'm going to diitch this for now。And Sn， by the way， it's mentioned the spec。

 but there's a really nice cleanup operation which just sort of puts all the blocks in a straight line。

So。Input here is our test board and our goal here is to before we start within the game to just get a sense of what are the things that are given to us in this project。

 how might we store explorings， how might we test an individual piece of code。Just by playing around。

 just by exploring。Without necessarily understanding， so one thing that I will say is。Every time。

dealingaling with some grid， like in this case， a gamebi。Its really worth understanding。

Which square in this board is one comma one， right？There's actually。

A whole bunch of different ways that you know， we could say that one comm one is right if this were a coordinate plane where this were0。

0 right in the center， maybe this thing would be one comm1。

 and this thing would be negative two negative two。

 maybe this thing is one comm1 because it's the first upper left。A lot of computer systems。

 the first thing is the lower right and it just goes up like the sort of upper quadrant of the coordinate plane there's a lot of potential values。

Some of them are silly， like calling this one， comma one will be pretty silly。

So this game spec is not quite that silly in fact， one color one in this version is。Exactly that。

 it's just the upper left。啊。嗯嗯。Of the game board and we're just going to set a couple of values。

 so let's say。What is two kind one and we're just going to set this to for so now we can see what two kind of one is so by。

The spec will actually describe how this block works， and I believe。啊。Yeah， so。

There's a little bit of documentation， which tells us sort of how this block works。

Essentially what we can see is this thing is sitting the row two， column number one， two， four。

 row one， column number one。😊，to2。And。It's just putting that value inside the game board。嗯。

One way this meeting the spec is always going to be a really good way of filling some of this stuff out。

 but I also want encourage you all to try things and ask yourself。

 does this make sense right if I say。Let's make another thing right。嗯。in the right spot。Just。

If I say。欢。吃题。So this's just 16 so one thing to note。2048， all the tiles are powers of two。So。

While you're testing， if you don't un number them， I'll show you where you can work them up in the game board。

But you know， 24，8， 1632， 64，138 and so on are good。Doubling numbers to just get familiar with。

But there's really you need to memorize them。 So before I cryus think about where should this。

Three come four appeal。We're free。Over4。On the right hand side。

 so let me have a sense of how this one block might work where it just puts a tile。

Space got over gameboarded。we have some kind of interesting。嗯。

Th where we can perhaps test and play around with our crew。It task great now。Its two。

IComple this block。Add two or four。So。If we look at this block and we start to edit， it says。

Fillll out this by。using a start code， so what is this philosophy of 2048？

noticeice that we give you this copy of board block and in the final version of the spec。

 we're going to change this from red to1 colors of the 2048 blocks so you know that it's a helper function that we've given you。

嗯。I don work out the same way is copy of boards so one of the ideas here is that in meeting with lists。

You've talked a little bit about en and discussion idea that we can mutate this。

 but what we're trying to do here is have entirely pure functions， which take a list。

Always return a new list with a new set of data。And this is kind of an interesting restriction。

It really helps us debug and separate out the concerns。Of our。

Of our functions that we're building so。How might we think about doing this。

 well we're going to start with something this is。We're going to say that we want to add。啊。

I'm on our lecture board。But our result。We're going to add at whoops not that。is that22 for now。2。

Because we're going to start working on ad2 or4。呃，拜拜。We'll drop things up inside for now。By setting。

Our test board。To the result。嗯。Of adding two or four。

Not to Air board so now if I do this every time I've done this right now。Always going to get。嗯。

Before in the spot， but we can see that if for the of this game。

We've already actually got a bit of progress in the first block。

 we know that we need to add a block to the game board now we need to handle some of the randomness rate when the game starts out。

 our board will be empty。啊。So how do we decide whether or not to add to it for is？

Let's start with just the first thing is， how do we know？This should be a four。Or let's say two。If I。

Thank here thank you。Now it's always going to be a two。What I want you to start thinking about is。

This problem is really a bunch of smaller problems is I need to pick a random spot。

I need to make sure that spot is empty。32。Whether those should be two or four。

 and so we is going to solve that simple problem here is。

I'm going to say that this is going to be under box that I'm doing。

 we'm just going to call this block two。For。嗯。And two or four。

Is going to pick one of these two numbers randomly。It turns out for this is one of the things where。

There's a lot of ways that we could build this function， but Snap has a little handy。

Pick random function。哦。嗯啊。That just gives us backran numbers。

 so actually if you haven't used it before， if I I pick randoming one to two。

 something is going to get you one， sometimes it's going to give me two。

And one of the tricks of decomposing problems to think about。😡。

There ways in which I can take something like Pickering one to10。

And turn it into picking only a two or a four。And one way thing about this is if I say。

 let's say if else。😊，嗯嗯。So I say。Yes。嗯Sa。算不过。呃，是一口清。If I pick a number。

 I actually theyt need to duplicatecate that up or whatever。

 if I pick random from one to two and it's equal to a one。我ち看。哦。Yeah。开置。嗯嗯。

So how does this block work if I pick rang from1 to two。

 it equals a one where I say at least two options。😊，I should report a2。Otherwise。I will report。

So when I hit apply， so one of the nice things in snap when you apply a block， you can move it open。

And if I search for this， I can say two。嗯。I can just drag it out you。

And how should we think about verify that this block works？

For block like this we're just going to keep clicking it randomly and verify okay we get twos or fours that seems good Any questions so far on a block like this or any of the。

Mechanics are 2048 so far。Zoom has been pretty quiet today。

 I don't know if anyone has questions on the zoom doesn't look like it。No。So。

I'm going to finish just dropping this in at the last second now。And。Right。

What we can see now is we have decomposed this into a problem of adding two or four to one block。

 and so this is how I would start this project is making a small function。months so。

And now we can witness。You can hopefully we see sometimes it's two sometimes it's four so maybe 2048 here for today the spec will be。

in the next couple days。I think on Monday。No， there will be no cross。Yes， next Mondays a holiday。

 so be new class on Monday。We'll make sure that that is on the calendar Wednesday orll maybe spend a couple more minutes talking about some of the testing blocks and how to lose them。

 but you'll hopefully get familiar with them on on the weekends and be on a lookout for this I do think it is one of。

The more fun projects because it is just difficult enough that you should all struggle with it a little bit。

 but it is at a level for which you should all be able to really sink your teeth into this。

 complete the project and hopefully spend some time playing game。Thanks everyone。

 we'll see you next week in lecture， thank you。

![](img/103246804d2aac6c109760fcad9eea08_8.png)