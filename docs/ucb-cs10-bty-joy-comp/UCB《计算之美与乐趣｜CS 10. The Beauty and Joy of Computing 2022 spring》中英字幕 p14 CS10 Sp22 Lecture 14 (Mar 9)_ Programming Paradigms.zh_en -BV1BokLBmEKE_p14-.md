# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p14 CS10 Sp22 Lecture 14 (Mar 9)_ Programming Paradigms.zh_en -BV1BokLBmEKE_p14-

う。

![](img/59f4e0823f8c8c01535a386676354705_1.png)

And in。See if the camera works。Oh that looks okay。And。去 the school。Okay。Yeah。不。H。So。It started in。

Just a second for everyone。是。嗯。可。Okay，Projector is。Not cooperating。It just takes time， cool。Yeah。嗯。

つけたら。chat。Yeah。All right， so。😊，Those on Zoom， if you can't hear seeing anything， just let me。

 but think were all good。So today we're going to talk about programming paradigms。

 this is going to be a little bit of a shorter lecture， so if there's time left over。

 I'll take generic questions。あ。We'll have in the same way that there are a couple short answer questions at the beginning of the request。

 you can probably expect that there'll probably be about one but no more than two short answer questions。

On today's lecture。But they'll be pretty high levels。

Just sort of a note about where we are in the class。So Monday was。

And we'll do some we'll show some snap code today， but Monday was sort of the last S lecture that was in Sap for a little while。

After the midterm。So again， next Monday's lecture will be open a Q&A。After the midterm。

 we'll start with。Transitioning from SNap to Python。

 and so that lecture will be about writing code and Python comparing Snap to Python and so on。

We'll come back to SNAP later in the semester a little bit， but as you're thinking about this。

 what I'd say is like for the next week focus on making sure you。

 you know everything you're been doing in SNAP， you understand that。

 the midterm will be of course 100% in SNAP but。Starting with next Wednesday and then for the last few weeks the semester you'll get to have the choice of whether or not you want to program in Sap or python and I can promise you that。

Having had the experience of。You know， seeing multiple people go through final projects。

 we'll talk about sort of， you know， the specs that later。But， Python itself。

 even though it's quite similar to S。The hope and general feelingme from our students from the past rate is that S is great preparation for Python。

But Snap gives you a lot of tools that you don't get for free in Python。😡。

As you're just thinking about the types of things that we can do in programming languages and what you can build。

 don't immediately feel like you want to just jump to Python because it's cooler or because it's harder。

 There are so many cool things that you can do in Sn， which of course。

 you can do them in Python as well。 But by having that environment and built in。

 So today we' gonna to talk about than is actually is programming paradigms。

 before we get to that just more update to the midterm。 So we're gonna send out an email。😊。

Either tomorrow or Friday with the exact reminding everyone of locations。

 but we do now finally it takes a while around campus to get everything confirmed。

 so we have two rooms so the midterm 2040 and 2060 Valley they are if you go sort of where 2050 is a big lecture hall one is on left one is on right。

😊，At least from that entrance by sort of FSM cafe。2040 and 2060， they're each smaller rooms。

 so we're going to split paper up even student IDs。Or let me just say what's on the slides。

 odd student IDs will go to 2040， even student IDs will go to 2060， but again。

 we'll write that out in an email if you want to take the exam remotely。😊，You can fill out the form。

You'll take it on grade scope if you took the request remotely sort of same deal as that again same exam remote stuff is proctored one thing we'll ask is that though there's not a campus requirement。

 please do wear your masks for。The midterm。And I do appreciate that most people are wearing masks in class。

In general， I think like everyone has been awesome about this on campus。

I am like a dozen feet away from the closest person。

 so hopefully like we're figuring out boundaries and what works as things go along， but yeah。

Otherwise， tomorrow in the evening there will be a midterm review session led by the TAs。😡。

that cut up that will be all over zoom so ask questions you know during the year and then Monday during lecture will be sort of any last second things to go over and then just a reminder we do the Cl policy in CS 10 so any later exam if you improve as a percentage will raise the score on your previous exam so what that means is if you got。

😊，Let's say 70% in the quest and you get an 80% on the midterm， your quest score becomes an 80%。

 Similarlyly， if you get like 80% in the final， then your midterm and Que scores would raise to an 80% if they are lower。

Of course if your previous exam scores are higher as a percentage。

 there's no drop and your final can cover the midterm or the quest。

Or one or the other or whatever it needs to。Again， exams meant to be a progress check。

 hopefully don't stress about them too much。Today we're going to talk about programming paradigms and this is one of those things where。

It's a little bit of an esoteric idea， but I think it's super useful that in thinking about why we actually talk about the constructs that we have。

 why do we like beat you over the head with mapke combined to an extent。

 why do we like you know impose topics like recursion because。When we talk about writing code。

 what we can talk about is the ways in which you write code to help us understand how to write it。😡。

A paradigm in general is just what you can say is a typical example or pattern of something so it's a model so we're really talking about here different styles of how we write code not necessarily at an individual line of code level although there are examples of that but when you think about the the programming language the environment multiple functions。

 a whole file and so on and so a programming paradigm in particular，😊。

As what we could say is a general approach， orientation or philosophy of programming that can be used when implementing a program。

What that means is。That when we look at the slide like this。

 we have three different sets of blocks in S。That all actually do the same kind of thing。

 so we have a square block， which。S we don't explicitly ask you to memorize these things。

 but these three little dots right here indicate that this x value should be a list。

And by the for each item， where you say， for each item of x。

 that indicates that this should be a list。So we have a square block that takes in a list as an argument。

 we have a map times over a list of numbers， and of course we have the multiplication block which accepts。

A list。As。A set of arguments as well， and each of these blocks takes into sets of numbers。

 returns the square of those values。😊，And each of these three has a distinctly different style。

Which one you prefer？Which one is your favorite， which one makes the most sense those are all things which are valid sort of personal views that well。

😊，Professors and people online have debated for as long as they are programming languages。

 so saying that one is necessarily better than the other is not the point but the point here is to recognize that there are different styles of these types of things so why do we talk about these styles well。

The hope is that understanding and recognizing a paradigm will help you think about what are the other types of things that this code is doing how when I see a list of data。

 how do I understand how that list might be used and by recognizing a pattern that helps you make sense of their code the other part of this is that。

Some of these patterns， while all of them are equally good in a sense that they can solve all the problems。

 is that they do different strengths and weaknesses and so whatever of our goals would be to sort of pick the right tool for the job so to speak。

 and that in this class， we're not necessarily going to ask you to always use a particular paradigm。

 we're going say like if you get something working， that's the goal in CS10。

 but you might find as you work on a lab or a project that using some of the built-in tools and Snap in one way or another age you in that goal。

And the other part is most of the programs that we write today。

 most of the languages that you'll be using this includes SnAP。

 this includes Python if you take CS620 or CS88。😊，By。Or any of the data science courses。

 Java and CS6 UN1 B。All of these languages are in many ways multipar languages and that they support more than one style and they borrow the best and sometimes the worst of all the styles that exist。

Before we continue just a word of warning that there is you know sort of no usually agreed upon list of you know programming paradigms。

 there are generally four that people mention and there's four that Berkeley typically teaches and you'll notice that this list has five so I'll highlight that difference in a second it is just worth noting as a fine example。

😊，あ分。Because it's in the slides， there's a Wikipedia Pat programming languagens。

 I will say the computeruter science articles in Wikipedia generally pretty good。

Each Wikipedia page comes with a talk page， which is how the sort of editors and community contributors to Wikipedia think about a particular problem。

 so you can kind of scroll through here and some the things that like maybe these are paradigms。

 maybe they're not what do other people think， unlike the rest of the internet。

 the talk pages of Wikipedia are on average， pretty civil， some of them。

Some of them get a little uncivil， which is entertaining。嗯。

So we have five paradigms that we're going to talk about。

 imperative functional array based object oriented and declarative and array based is the one that again。

 this is not exhaustive， but array based is the one that we don't normally talk about。

 but with some changes in SNAP there's a lot of interesting things to explore about why this is a useful paradigm so we've kind of added to this。

 but typically you'll hear imperative functional object oriented and declarative。😡，Certainly。

 functional and object oriented are things which have really strong histories。Of。

Other programming language is existing， so you may have heard that Java is an object or a programming language。

 a statement which is probably meaningless to most people， but。

We'll sort of talk about what objects are in a second， objects in snapap do exist。

 they're a little bit weird to demo。Here are the examples for the previous slide is a functional programming paradigm typically involves taking。

Taking a function and just using that result and passing it to another function。

 so when we talk about the distinction of peer functions。

 what we're really saying is we want a computer value， pass that value along。😡，は。

And that we're thinking about how we。Take some data into a function， use that result。

 we're not typically assigning variables。😡，Now we're not typically explicitly using loops。

 but we're thinking about applying a function to a list， passing data and getting the result back。

 sort of what we typically think of as just really computational tasks。A rate based programming is。

In many ways， a distinct type of functional programming or a separate category。

It's really thinking about。How do we explicitly design a programming language and an environment that works really well on？

Lists of data， so array is just another computer science term for list。

People will have arguments about what's a list and what's an array those are not worth having。

 but if you see array based just think list based in Sap we just call them lists and you'll notice though in this case like one two3 times one two3 it does the same effect but it is perhaps a completely different and distinct way of thinking about how we might write programs and so that's why it gets called out as a。

😊，Ass a separate category。😊，In Snap， actually why me just pull this up because I think it's an interesting example。



![](img/59f4e0823f8c8c01535a386676354705_3.png)

All right。In S， there is a libraries sort of browser， so S while it has。

About 170 or so built in blocks has a bunch of libraries that come with snap some of these are really simple。

Like。Where is it？呃。We have a。Oh， it's called Pel Switch。

bothers me because it's not what it does we have a Pixs library which allows you to take a photo from your webcam and sort of report the image back。

😡，That should just be called the camera library。But we also have things like this library called APL primitives。

An APL happens to be this language that originated in the 60s that's all about doing data computation on lists of data。

 so thinking about things like linear algebra where you have matrices and arrays，😡。

In the 60s its sort of in the term data science to originate。So。Are a whole bunch of functions。

 which I'll be honest， even I do not understand all of these because they are built for a particular style of programming that I don't do a ton of。

啊对。The point being here is that each of these styles comes with their own set of functions。

 their own set of a sort of useful blocks that make them happen。 And so in Sap， it really helps you。

 or it allows you to support all these different types of styles。

 So a array base is really dealing with lists as input。

 treating lists as a type on their own where we can just apply functions to a list。 So。

 so hyper blockss and S。😊。

![](img/59f4e0823f8c8c01535a386676354705_5.png)

Ananiffest of that。But there's libraries that go way， way deeper。

And the final program paradigm that's on the slide here is this imperative paradigm。

An imperative is the type that whenever you look at code online。

It's most likely to be some form of imperative programming because what imperative says is。😡。

Take a sequence of steps。One by one， execute them in order， assign whatever variables you might。😡。

Imperative just really says， here's a direction， execute that direction as the program。

Loops are a hallmark of imperative programming so for each item in list for i equals one to 10 whatever it might be add items to a list all of those things are examples of imperative programming so this is typically。

Sort of what you can think of。As。As an example of an imperative program so these next few are an example。

Of a block that takes a phrase。And turns it into an acronym。

So I believe in one of the higher order functions labs。

 you should have done acronym using mappkeing Com， which should be on the next slide。😊。

But the emed paradigm here really just sort of spells out the steps that we have a script variable。

 the result of acronym， we set that to nothing for each item in splitting a phrase。You know。

 by in this case， space。呃 we。Iterate over those phrases， we add the first letter to a variable。😊。

We'll put it back。It just do one thing， do another in a loop。

The this is a very typical imperative style program。

 I think this is fairly easy to read in some senses like this communicates to hopefully what's going on。

And one thing here is that it's a hallmark of imperative programming is that we're taking some data like this acronym value。

We're repeatedly changing that value， so we're reus a value， we're updating it as we go along。😡。

We areWe're using mutation。To。To sort of keep track of some state and some information that we have。

The functional approach to this problem。😮，These2。Use a series of functions where one result gets passed to the other。

So。哎。This is。A version of writing acronym that。Uses map keeping combined。

This one is nice in the sense that there's no variables to keep track of， it's just one expression。

 admittedly kind of a large expression。The result of each function just passes right in。

To the others。 So in this case， we say keep。The items where the length of our list is greater than three。

Over a list， which is using this block sentenced to list。 So sentence to list is。

Just a block of the split function actually。Then we map the first letter over that list。

And we combine things using join。😡，嗯。This is in many ways， new variables， right。

 it's the lines of code。 It seems simpler。But you do have to recognize that like while reading this code。

 the thing that we actually execute first。If the sentence to this block。

 then the result of that is passed to keep。 The result of keep is passed to map。

 The result of this map block goes into combine。So there is still quite a bit going on here。

 and it's not always more obvious what's going on。嗯。We also have approaches that are。嗯。

We can kind of say hybrid approaches。I think this is a real。

Challenge and also benefit in programming language。

 so that the reality that I'd say is most of the code that you look at。

Most of the tools and projects that you build in CS10 fall into this hybrid approach。You know。

 this code is kind of functional， a little bit imperative and it uses。

Some you know array style approaches too so in this case we explicitly say step one that we're going to keep things。

In an array after doing this sentence to list， so again， we have a functional thing here。

 taking a function past result but we set a variable， we take the result of that variable。

And we pass it to our map block where we map item one and the very last step we join passing a list directly into the join block。

 so this is kind of an array like approach as well where we have some functional code。

 we use some state invariable so it's a little bit imperative。😊。

And then we have this eraseed style code at the end。So you know， in practice。

 you might mix and match all of them， I will say that this is something that。In CS10。

 we do try and push you into it into this functional model where。

Not using as much state as updating or mutating variables， because every time you muted a variable。😡。

Especially in a loop right that's something where you have to sort of keep tracking your head about all the things that are going on however this hybrid approach is really a nice middle ground because what we're doing here is by saying。

Set long words to this keep is I am telling you。The reader of this code write that I intend for this expression to represent something which is a set of long words now if we mean and occasionally we mean on the exams。

😡，We will， you know。Maame variables， things like fo and bar and Gly。😡。

Don't know why those are the three words that computer scientists use。

 but they are and they've stuck with us and the variable names don't communicate anything useful。

 but by separating out step one， step two， step three。

 where we're never actually mutating the variable long words right we're setting it to some value。

 we're passing that value in to the next expression we can actually give another person ring this code some information about what we're trying to do by using good variable names and if there is one thing that you should take away from this lecture。

Is that being intentional about how you write a piece of code is a super useful thing that calling this thing wrong words。

 calling our map list of letters， right？😡，When I see set list of letters to map。

 what I should say is， okay， I think I know that the result is going to be a list that looks like A B and C。

And then you get to double check。Does that map actually give me a list of data that looks like A。

 B and C， So using good variable names is really a helpful thing in office hours。You you。

 a TA might ask you and say， hey， what you， what is that variable and it's not just what is the name of that variable。

 but it's you know， what does that represent。And na your variables in a way that helps you communicate what they represent。

😡，Can really be helpful。三。Yeah， I'm actually kind of curious of just the three styles so you can put in chat and zoom or raise your hand how many people sort of prefer just as a sense of like looking at this code。

 looking at acrom， how many people prefer this sort of iterative approach first is something that like you just think it makes the most sense。

😊，Or you think it's easy to understand or you just like the look of it and the colors or whatever it might be does anyone have a preference of this first style。

Cool， we got a couple hands in Zoom， does anyone have a preference can type in chat。

 raise your virtual hands。Thumbs up， whatever you want， cool。

 how many people sort of prefer this purely functional style？

Of like using map keeping combined to solve an acronym。Prefer the style。Cool。

 a couple hands here and Zoom， anyone on Zoom prefer our functional。

Approach the upper array over here。Couple hints there how many people sort of prefer this this last block at the bottom couple a few more hands cool I feel like I biased the room by by saying that that is。

how I also prefer things， which you know there's nothing better than a bias survey to confirm results that you want。

 that's why we have data science and statistics to figure out how to unbiass things。😊，But yeah。

 I think。I think it is worth just recognizing， right that as we go through these paradigms。

Especially these three because。You know， functional array imperative and sort of this hybrid approach that you'll see all three of them in CS10。

 you'll see all of them in data 8 in CS61A in CS621 B you know if you continue in computer science you'll see even more styles so all of these things are are worth sort of thinking about so actually before you continue on questions on sort of this idea of paradigms so far of just some of these examples or。

What we've been talking about。Yeah。These only programs do the same thing。I of like。うは。Yeah。

 in this case， yeah， that's correct， these all of these three examples do the exact same thing。

 why you pick one or the other。😡，And this case is generally a preference。

 there are certain tasks that we might say。You， where one style is optimized for another。So。Actually。

 if I have time at the end， I'll demo why some of the array programming stuff works really well in SnAP。

And that's because。We've added a bunch of features to make certain types of computation really fast and so some programming languages。

Really optimize。Their environment for a certain style， but in general all of these are correct。

 if I ask you to write acronym and snap and we're just judging you on correctness。

 you know any of these are valid solutions。And you can imagine actually that there's probably new。😡。

In between these three， right， there's other blocks we could use。

There's other forms of even functional variations。That that would solve this as well。

 so yeah all of these do the same thing it's it's in this case really about a preference since no one of them has sort of a clear clear advantage。

Other questions and Zoom。Any other questions？So。We'll take a couple examples of。

Sort of imperative first functional one thing that's tricky about this is that we can argue that functional programming is sort of a subset of imperative right that we're still doing things in a sequence of steps we can't take right we can't pass the result of one function into another until we've done the work to compute that function most programming paradigms have a subset of imperative steps。

😊，嗯。But。The thing about functional programming is that we're trying to avoid maintaining state and that we're trying to think through composing a series of functions。

In order to solve a problem。あ。You know， when we talk about。呃。

Function programming it's often that there's sort of one way that is either obvious or semi obvious of how you might want to do something。

 so that usually involves something like mapping over listeded data or filtering your listed data if we're talking about lists。

😡，嗯。Some people say this kind of feels like solving puzzles。

 right that you're trying to use a set of functions and construct them in the right way。

Because you're restraining yourselves to a peer model where every input leads to a function。

 that output is either the correct result or leads to another function。You know。

 trying to essentially write a program where you don't use any additional variables。😡。

Can be sort of a definite restriction。嗯。And。And that's why I think a lot of people prefer things like comparative programming is that some these times they feel like a little bit like magic。

Function programming tends to be a little bit shorter。This in and of itself is neither good or bad。😡。

But in general right， we want to sort of maintain some trade off between。

code if that is understandable that's a little bit longer can be useful because you can understand it。

 but every line of code that you write is a new chance for a bug。

 so there is this tension that shorter programs as long as you can interpret what they're doing。

Have a little bit of an advantage， but it's not worth。It's not worth making code short。

 just for the sake of making code short。One thing that is really useful about functional programming and why we do push on NCS 10 and in Berkeley in particular。

Is that？By avoiding using state is that your programs can be easier to debug that when we stick to peer functions when we could say this function doesn't rely on anything about this outside world that no matter how many global variables you have in your SNAP program。

No matter what time of the day or week it is or the cycle of a moon that like my function is a pure function it does the right thing and will always return the right result you think I'm joking about like the time of day or the cycle of the moon。

 but if you Google for programming bugs that occur on full moons，😊。

There is this long history of people running into sort of large systems like Google。

 like flight tracking databases。Therere programs that rely on dates and times。

Only run into a bug like once a year or when。There's some calendar event that occurs on a full moon。

 really shouldpy stuff that can happen when you write software for millions of people。

The last event or last the last reason that functional programming can be really useful is that functional programming by separating out this sequence of steps tends to lead to better parallelization so where we can do multiple tasks at once we can say。

😊，I take my map block， right where。Let's say a mapping letter one over a list of data。

Because that letter1 is a pure function， I could take letter one of one item at the same time I'm computing letter one of a third or fifth or 10th item。

 and of course， letter1 is such a quick function that we wouldn't need to parallelize this。

 but you could imagine that you're actually processing a lot of data。

And functional programming can help you run through some of those computations in a few weeks we'll actually talk about how we think about running code concurrently on our computers where multiple tasks can be happening at the same time and some of the challenges that happen there but functional programming is often a。

You know， a tool that we can use to restrict ourselves such that that we can run。

Multip multipleip operations at the same time， Google's web indexing function right where it goes out。

And grabs data about a bunch of web pages， it's all set up in a way using this idea of mapping at a very large scale that each mapper computes some information but a web page that Google has millions of computers。

😊，You know， every second， just computing。You， the same type of data about every web page generating results in parallel。

😡，Updating updating its search index。あ。So， you know。

 functional functional languages or functional programming paradigms have that a benefit over the last like。

Two decades or so， functional languages are really growing in popularity。

This is not a reason why they're good or bad， but just sort of an interesting trend that we see in programming languages。

That's functional programming。嗯。呃。Everyoneone。I's really hard to demonstrate on a particular example like something like acronym that maps really well from taking a sentence。

To return some output is this idea of object oriented programming。And audit programming。

Is this idea of organizing the types of things that we're thinking about？😡，Into。はい。

You knowIn structures that we call objects， which is a very generic term and each of these objects。

Has their own set of data， their own set of attributes。

And your own set of procedures that they can work with， so in SNAP。

It's really natural to think of each sprite as an object。 So in particular。

 if you start making games。😡，For which things like you know the graphics of snap。

 the sprites that you might have costumes and sounds that sprites have really naturally map to this idea of。

I might have a sprite that's a character and that's one kind of object。

 and I might have a sprite which is the player's enemy or something like that。

 and that's another kind of object in these objects， you know they might have a name in S。

 every sprite has a position on the stage so there's an X and a Y value。😊，は。

we can do things to those objects so we can have the object ask a question。

 we can have it say something in that say block right if I'm on one sprite and I use the say block in my current script。

 only one sprite will say something at a time。If I have another save block and another sprite。

 it can say something different and we can think of those as。😊。

Procedures that apply to each specific kind。😡，Of。Of objects。

 so there's really a lot of depth to object or programming。 So if you continue on with CS62 B and。

Cs6 to anA， you'll see some more of it， but in Python we'll see a couple of examples of how Python organizes objects and a little bit more。

Of a traditional way。あ。And what I will show is sorry。That let's see。Computer。



![](img/59f4e0823f8c8c01535a386676354705_7.png)

Pa。Wheres the screen。😔，That's why I can't find out what's going on。So in Sn。One way that。

 aside from just sprites that this shows up is in the sensing tab， there is this block called object。

And what this does is it actually reports a sprite as a piece of data that you can manipulate。

Myself is a kind of object。The stage is an oxygen stamp。

And you look that the stage is an object which has you know kind of different properties than than a sprite like the stage is just this background。

 so it doesn't have。X and Y coordinate。まあ。But every。

Every sprite has a whole set of properties that you can access and that you can manipulate。

Sprites have neighbors， which are other sprites， I only have one sprite。

 so the sprite has no neighbors。If I like add another sprite over here， I ask for my neighbors。

 it says no， I think have I do this， it'll say yes。

 I don't know what the graphical threshold is for what a neighbor is but basically you know a sprite has a function or has a set of properties that are what are the other sprites that are close to me and you could inspect that so we're treating this as an object which has different attributes and objects have。

 you know potentially sort of relationships to one another。あ。I can ask for a name， of course。

 so the name of the sprite is just sprite that's not terribly exciting。

 but the other thing that we can do with objects is。😊。

One of the nice things about object or programming is defining ways in which objects can communicate with each other。

 so SnAP has this thing called a tell block。And a tail block。Lets us take。A呃。

A script and have a different sprite run that script。

 so I'm going to go ahead and move this at least two out of the way from each other。呃。So this block。

 I'll note is a script and sprite one， but I can tell sprite two to say some message from my code within。

Within the first script so if you look at the 2048 project source code you'll see that we do this a little bit setting up the grid moving tiles around and this is one of those features of object during your program by saying。

This object is responsible for some kind of data who can better structure and separate your code out to say that the things that I'm doing in this part of my code are responsible just for。

 let's say manipulating the graphics of the game board。

 the things that I'm doing in another part of my program are。

the blocks that you built in 2048 are in a more functional style。

 but they're just responsible for manipulating the lists of the game board。

Snap has object training programming， there's a lot of different ways that you can explore it。😊。

It's not something we typically explicitly teach because it's sometimes hard to translate this directly to Python or to Java。

 but if you want to explore the idea of a sprite as an object that tools and S。

Are there actually before we continue on with other paradigms。

thoughts or questions about object rate programming？嗯。



![](img/59f4e0823f8c8c01535a386676354705_9.png)

So。The last type that we're going to talk about is declarative programming。

Dlar programming is one of these things which。😊，You don't do quite as much of。

 but is kind of a mind blowing idea。 And the idea here is。

That we always want to express what we want as a result without expressing how to compute it so even in the functional programming paradigm right we're still telling the computer how we want to compute that result and a declarative program we simply describe some rules about the world and the computer figures it out so this is a kind of interesting example。

😡，Cooring a map of Germany of each different province in Germany。

 so the program basically takes on a map where everything's gray。And。

It sets up to try and color to color the squares， so we're not going to explain how why this works。

 but this uses a language called prologue。And the really cool thing about a language like prologue that is purely declarative is that we basically say。

Okay， here are the four colors that exist， so we have red， green， blue， and yellow。嗯。

We tell prologue that what our goal of this program is is to have a few colors touching each other so there shouldn't be a red province next to yellow province and there shouldn't or excuse there shouldn't be a red province next to another red province you we should try and put red next to yellow or whatever and so in prologue the syntax is a little bit weird。

What we're just basically saying is that given this function called neighbor。

 we don't need to know how a wine neighbor works。は。

Well we say that there are two colors in here and that the color of one thing should not equal the color of another thing as much as possible。

And then what we tell prologue。Well， how do you know what the neighbors are？

We tell prologue that there's this thing called Germany， which includes a lot of provinces。

And told a prologue that in Germany some provinces are neighbors of each other。

 so if we look at this map， oops right here right？😊，嗯。These two provinces at the bottom。EW and BW。

 those things were neighbors， right？But BY is not a neighbor of ST， which is sort of in the middle。

 so we wouldn't help that， but we essentially get prolo at these list of rules。At the very end。

 we ask it for。Some answers we say color in Germany。These list are provinces。

And what we get back is a colorful map where as far as I can tell。

 this is a totally correct ordering of a map where each province is。😊。

It's a different color from the one next to it？😊，The program can output an explicit sort of w right so we can see that this BY province down here is yellow even though it looks would be one option or yeah I think that's maybe anyway know there's a couple different orderings of the map because actually that's screen so oh this is this is an output which isn't shown on the screen but could be a different ordering so the nice thing about prologue as a language is that you just say here are the rules。

😊，Here's the environment that I want。And here's you。

You just go as a program and it tries to figure out all the rules。In practice。

 working with declarative programming languages requires sometimes a specific set of problems。

It's it's a useful tool so in Sn we don't have super great ways to demo this， but。😊。

They are an interesting tool to be aware of。The goal always here is to explore sort of the end result without telling the program。

How to get the results so prologue is one of those languages SQL is a language for querying data from a database。

😊，嗯。And SQL is a really declarative programming language。

 and I'll try and show an example of that as well。Pands is a data manipulation library that if you take data 8 and data 100 and some other data courses you'll learn how to use。

 but it's a similar idea where you describe how you want pandas to make the data look。

 and then it tries to filter and process all your data。

To generate the results so Pandas is just a Python library we won't use it in CS10 because it doesn't really fit in。

嗯。But that's there。What？I want to leave with the idea here is that。

All of these paradigms that we're discussing are all equally powerful。In the sense that。

In any of these languages， if we try hard enough or any of these styles， if we try hard enough。

 we can solve a particular question， but some of them are better suited to a task than others， right？

😡，We could define some list。😡，We could write some code that tries to given some constraints。

 pick a color for the first province in Germany， pick a color for the next province。

And build this map in some imperative style， but with Pe we basically have to say like hey。

 here's what I want， you go figured out。And that nicely maps to some kinds of problems。

Not every problem here is necessarily fit for pro language， but if we try hard enough。

 all of them let us。😡，Let us solve a problem。Actually， as she't say recall。

 because we haven't talked about turn completeness yet。

 but when we talk about turn completeness later。In the semester。

 we'll come back to this idea that as long as we have a few very simple constructs。

 any programming language allows us to。To simulate any other kind of programming language so that's really why we talk about programming paradigms so we only have a couple minutes left so questions on on maybe this idea of object related programming or declarative programming that there might be any questions on zoom。

Yeah。All right， cool， so I will just leave you with one other example of a declarative。Programming。嗯。

All。And。🤢，O。Maybe annoying actually， since I got logged out。If I can log in really quickly。嗯。Yes。

 that's fine， lock me in。嗯。嗯。是。Well it's my dashboard。啊，这个。

So one thing that we're not going to talk about sort of why or how SQL works。

 but one thing that I think is really useful about declarative languages and SQL in particular is that I can have a number。

Like 171 people signed up for S。In the last day。And。What I can then do is。呃。

Let's see where the heing li。嗯，Okay， I'm trying to figure out why they edit button moved。So。系。哦。

All right， that's not I want。 All right， I don't know why this tool is no longer showing me the raw SQL。

 What I wanted to show is just that you can take something like a declarative program language to say count these things fill to this data and you get results that are really useful so though we can't show you them in S right now declarative programming languages do have a really cool spot So sorry that demo didn't work out but questions on this sort of thread on the weekend So if you have other midterm questions after the review session bring them to me Monday we' do sort of last second overview。

😊，But， mid next week， don't stress too much。You know， it'll be。It should be fine。Thanks， everyone。

Thanks everyone on Zoom。

![](img/59f4e0823f8c8c01535a386676354705_11.png)

C where。Me too。

![](img/59f4e0823f8c8c01535a386676354705_13.png)