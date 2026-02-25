# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p16 CS10 Lecture 16 (Mar 28)_ Python II.zh_en -BV1BokLBmEKE_p16-

![](img/5b9a74e9840a3a94018d66415f0d6d71_0.png)

All right， okay， let's see。 Got a few more people joining online。 That's good。最好几个。AndThat's。さど。Oh。

All right， so before we get into today's lecture， we're going to continue for this week and next week talking about Python。

We're still going to do a lot of comparing S。Two pythons so sort of thinking about how we are。

You know write in one language what maps exactly from S to Python。

 what is different so with that in mind。Wednesday we're going to release what， yes， thank you Z。

We're going to release homework three。And homework three is going to be。嗯。The topic of the project。

 it's going to be a new project or a new assignment。😡。

Sort of it's somewhere between a homework and a project。

 we're going to call it a homework because the goal instead of having you do something completely from scratch and Python is going to be taking a look at the existing project。

And then adapting that into Python， so we're going to give you a snap project。

 which is fully complete。And we're also going to give you the start of a Python project。

Which has some of the stuff built。And then some of it not built and your goal will be to take a look at the snap project and essentially sort of。

Think for the code and translate it from snap to Python and in this process。There's sort of。

Two things that I think we hope that you can go away with one is just sort of a sense of like how S and Python are both similar and different than that when we see something like a each loop in S。

 we can then start to think about like how do we map that to a four loop in Python and what we've been doing。

Is trying to go through the snap project and actually write some of the snap code using features that make it a little bit more clear you know what kinds of python constructs you should use but in that as well。

 the other thing we wanted to practice with is just this idea that like。

As we're working through code， we're doing a lot of things， we're reading it。

 trying to understand it， we're writing code， which means that like we're producing something new then we have to debug it and so don't try and like take even a smalln script and translate it to working Python necessarily all in one pass you can write some Python。

 see if it works， update your translations， there's not like a single correct answer here right the goal is a Python project that works。

 there's more than one correct way to translate from S to Python but the hope is that like as you work this project you'll see some of both of the strengths and weaknesses of each language。

三。The second thing going on at the same time so this assignment homework three。

 you'll have a couple weeks to do it， you'll have a couple weeks but it's not meant to be we're calling you a homework because it's not meant to take a significant chunk of time certainly less involved than what 2048 was however。

 the next thing that we'll be working on is our final project project three。

And this week you'll be working on project proposals。

 so the whole goal of this project is for you to propose an idea that you want to work on is something which is hopefully at least somewhat meaningful to you and your partners so this will be a partner project。

😊，And。This week you'll be working on proposals， proposals are not meant to be。Super involved。

 but they do need to give your TA a sense of like what do you think you can work on in a span of a couple weeks and the goal is for you to build something either in Sap or Python。

😡，I will get reminded that like。We choose Snap for reason you can get a lot done in S a lot more quickly than you can in Python and while you can certainly do graphics in Python。

The fact that they're built into S is a good reason to sort of continue the snap and the goal here is for you to build something that you sort of get to design and scope out so oftentimes this will be a game that we all know about so Sodoku snake you these types of things are fairly common projects some people build versions of Sodoku where the algorithm to generate a game board is the goal and then it's a project where the player actually place Sodoku some people build a version of Sodoku right where。

😊，You input a game board like from the New York Times and then you write a snap or Python program to solve Sodoku all of those things are totally cool projects it doesn't need to be an original idea。

 but the hope is that something that you think would be fun for you to work on other types of projects would be if you're taking a course。

Let's say in like biological sciences or maybe economics or something and you want to do a project which tries to somehow convey some of those ideas in a S or Python program maybe it's a little more data analysis focused maybe it's you some sort of interactive simulation those can also be really cool project so that's the goal there I think it's a really fun thing it is a space where hopefully the time that you spent on is something valuable to you and the other thing that I'll war you about is for your final projects。

That。You know。😊，We're going to really try and help you focus on getting something that works that is a little bit smaller in scope than doing something really large。

😡，That doesn't work as well so things like artificial intelligence simulations that are pretty advanced or large probably out of scope for CS10 project right I have no doubt that if you enough time you could get something working but that's not a two or three week project that's a lot of learning a lot of time involved if you want to do some sort of really simple stuff with smallish data sets there might be something there but I'd say for a project like this talk with with your partners and figure out what you want to build that you think you could do in a two or three week period and it's much preferable to build something that actually works that you can play that you can experience and use and show to a friend that has fewer bugs than something really ambitious but when you try and start it up spits out an error immediately obviously bugs happen like your project doesn't have to be perfect working code。

But lean more towards correctness than。Embition on the final project so。

If it's not up already that the specification and guides for Project3 will be up on the website today。

 TAs will mention a little bit about that in lab， but that'll be sort of the focus of this week as well。

Oh， and then was on the slide， but we had a little bit of a snack here with。

Coordinating midterm grading， so midterm grades。Spring break happened and stuff didn't happen right before spring break。

 so those will be out probably tomorrow if not by Wednesday morning's lecture。😡，Yeah。

 sorry about the delay in midterm grades those will be out soon so what we're going to continue with in Python。

😊，Talking about some of the things that Python does well and how it sort of differs from SAP and the first of these is this idea of object oriented programming。

And if you remember a couple weeks ago to the programming Paras lecturec。

We talked about in Snap how a sprite can be an object。😡，But overall。

 that object oriented programming and sort of the modern definition is not something that is super easy to explore and snaps and this will be a little bit different。

From some of the code that you've seen last time， and so we're going to look at are two of the data types。

That Python really sort of hones in on， which are lists and strings and how we can do some of the operations on there。

And so。In Snap， we have this code on the left right here， right， we have some list。

 it could just be a list to numbers list or whatever。😊，This could be a script variable。

 it could be a global variable and to add something to。We use this function add item to list。

 and we pass them the list as an argument to the add block。😡，Now in Audre's trying programming。

 the way that we we sort of flip the script is instead of passing an argument to a block。😡。

We have some function or method， which operates on。An object。 And so in this case。

An example that we have here。😡，We have some list in Python。

 so this looks like a fairly similar translation right instead of a redless block。

 we use square brackets。But what we then say is some list。Dot。

endAnd the way that this works in Python in Java。😡，In many program languages is that。

I'm going to say A dot B， some list dot append this function append is operating on this list so we can sort of think of it。

 it's not an argument to a function， it's saying this list thing knows how to do something called aend。

😡，And what can we append on this case， we are showing that you can mix and match the types of things that go into a list so we can append the word catchchup to a list of numbers。

 why we do this， probably not many good reasons but you can and this idea of saying A do B to do something is。

Is one of the hallmarks of object credit programming it sort of lets us。呃。

In this case with a built an object like a list， there's a whole bunch of things that we can do automatically from Python。

 when you take CS601 a， CS61 B， you'll learn that you can build your own objects that have their own methods。

 which do sort of things that are specific。To this。So again， how do we think about this in？

Comparing staff and Python is the in。And Snap， all of our blocks， for the most part。

 are global blocks， right， they exist in the palette on the left hand side。They take in some data。

 they have either output data or they modify our list， whatever it might be。But all all those blocks。

 you。Exist for everything that that is there in snap when we talk about object programming。

The methods or the functions that we use only make sense in the context of a particular object。

 so there might not be a global append method in Python we need to have an existing list that we then append to and。

Again， this is one of those cases where neither approach is necessarily better or worse。

But they're different。This is something that will' keep。

Experimenting with so we're going to go through a bunch more examples before we do that。

 I do think this is worth sort of diving into。If I click on the right thing。

So the slides here have links to the Python documentation。S may have briefly pulled up。

Before we left their spring break。This is perhaps， in my view。

 one of the best reasons to use a language like Python， and it is the fact that the more popular。

 a programming language is。The more examples therere online， I guess how you do stuff。

 And one of the best ways that you can learn about， you know， how do I do X， Y， Z and Python。

 What can I do is to actually go through their official documentation， Python's documentation。

 overall， it is incredibly comprehensive。Some of it is written from the perspective of like。

Peure computer scientists， it's really dense。There's sort of a lot to get through。

 but most of it are things where if you're just trying to get a sense of what can I do。

 it's really well organized so。There's a nice search function， there's tables of contents。

 it sort of structures you。Through learning everything you'd want in the language。

 but two sections that we've highlighted。In the slides。Are a section on data structures。

 so lists are a kind of data structure and that this just means something that lets us group multiple bits of information together in an easy to modify form。

There's a whole bunch of things that we could do to list this just tells us I can append to a list。

 I can extend a list， I can insert a list right you might have seen the insert at block in snap。

This is sort of an analogous block to that I can remove an item from the list again the delete block popping is a pretty common operation that returns something and removes it at the same time。

 that block doesn't exist in S， although if I tell you that it's deleting an item from list and returning that item。

 you could build the block， a reporter block called pop and snapap yourself。😊，That。

ItIn't too complicated？You can clear list there are you know things that perhaps。You know。

 some of the things that we don't have in snap but you can imagine how you might build those yourself。

 well all this needs to show is that if we're trying to think about what can I do with a particular piece of data。

In Python is there's a whole bunch of examples here。

 there's a bunch of things built in and that is one of the advantages of a learning how。

To use a language， it's not something that you should learn on one step like I don't really recommend。

😡，Reading the Python documentation cover cover， if you have insomnia it can sometimes be a good thing for that。

 although there's you know lots of textbooks that you can read if you have insomnia so you know choose your I guess the least favorite but。

😊，But what I would say is， be aware that you can search this you。

Get a bunch of ideas it talks about in this case things that we won't talk about in CS 10。

 but different ways that you can use lists。So there's a whole bunch here i'm not going to go through all of it。

 but we'll just highlight that it's there the next thing that I will pull up though is we're going to talk about strings and。

Again。Strings are a separate type of data in Python。

 so later in lecture we'll come through some of these examples of things that you could do with something which is a string and there's a whole bunch of methods here like capitalize。

You can， you can sort of center string with spaces， which is kind of。Useful for certain things。

 you can of course， count characters。not all of these things you'll have uses for， but they're there。

What？What I want to sort of do is just keep comparing a S。Python。

 and after this we can look at some examples。In Sn。We have this ask and answer。

Function right where and I'm actually going to。Yeah new。hos that？哎。



![](img/5b9a74e9840a3a94018d66415f0d6d71_2.png)

啊。Where and if I go over here。啊。We can let's move zoom out of the way so we could see this whole line。

 we would say give me some numbers and in Python we have the special input function。

This is something where the input function Python is a really nice tool to just demo something it's not something that you typically use in CS62A。

 but it's the ill way of saying ask for some input in the terminal in the same way that ask pops a little speech bubble。

😊，And in this case， what we do is we can just type a series of numbers。



![](img/5b9a74e9840a3a94018d66415f0d6d71_4.png)

![](img/5b9a74e9840a3a94018d66415f0d6d71_5.png)

And。And what if we wanted to， I couldn verify that numbers text is just this string of data。

 it's a series of characters， one space two place space loop， space four。And。

Now the question is how do I do something like turn these into lists and the way that we think about things in Python？

Is when we have a piece of data like a string。哎。I can do。

Some type of operation on those strings I again， this is not something where。going into this。

 I would at all expect you to say， how do we do this and me just answer， oh， we use number text dots。

What we should think about is I want to take this state of numbers， one， two，3， four。Turn them into。

😡。

![](img/5b9a74e9840a3a94018d66415f0d6d71_7.png)

A list of numbers。And in Snap， we can do this。Using the split walk， so we say split numbers list by。

And we can say we can type a space there to split things by a space and in Python we can we have a similar method。

 so numbers text dot split， which suggests that this is。



![](img/5b9a74e9840a3a94018d66415f0d6d71_9.png)

A function which operates on a string and what does it do is it splits the string into。诶。呃。🤢。

Into a series of individual items， so now we have four numbers。😡。

And we've turned it into a list of four items。Which is。



![](img/5b9a74e9840a3a94018d66415f0d6d71_11.png)

Gfly equivalent。To this S program over here。And again me the idea is。How do we know？

How do we know what to do in Python while we kind of have to look。😡，What am I trying to do。

 I'm trying to turn a series of text values， a string into a list of items。

 what operations do I have in S， this case I have a split block。How do I split some text in Python。

 you could literally just Google， how do I split text in Python or open the documentation to find the thes split。

😊。

![](img/5b9a74e9840a3a94018d66415f0d6d71_13.png)

And we map things from one way to like that， but again， string value numbers text， dot split。

 meaning that it is a function which operates on this value。

And it takes an argument of how we split that text， in this case。

 splitting something by space is literally just putting the space character inside a series of quotes。

So that is the argument that gets passed in。When I'm using the interpreter like this。

 when I just have Python 3 open。I just type some value array it shows me what's there。

 if I were to run this as a file， I would probably want to print。Numbers list。

 which is sort of like actually saying something like。那个。



![](img/5b9a74e9840a3a94018d66415f0d6d71_15.png)

Before I continue on with a couple more examples。Python what I've done here and it's totally cool if if there are questions or。

We're just wondering what the heck is going on。Or if're not， we can go on to more examples。

That thing。In this case， these two things pretty much do the exact same thing the main difference between snap and Python here is that。



![](img/5b9a74e9840a3a94018d66415f0d6d71_17.png)

In Python。呃。So before spring break， we talked about sort of the equals comparison using double equals。

 the main difference would be and actually let me see if I can。嗯。

Or is the lighting controls really quick？So that I can make it a little easier to see。

Where did they go？嗯。Okay。I think that should dim things up here a little bit more。

But the main difference here is that in S， whenever we use numbers and we use strings。

 S just converts between them， it doesn't really distinguish between a one。

That comes from one plus one or joining one in Python。These numbers， one， two， three， four。

A text that represents the character one and so that's the biggest distinction between if you were to do something else between Sap and Python。

 this code right here otherwise operates pretty much。



![](img/5b9a74e9840a3a94018d66415f0d6d71_19.png)

The exact same way， I don't think there's you any significant differences。

 other than the fact that you know answer itself is sort of a global special variable in Python that sticks around or in SNap that sticks around whereas in Python you don't have that。

 but if we're sticking to script variables， what's shown here is pretty equivalent and you other question Zoom。

Oh Zoom says it's lagging a bit， all right。I'll make sure everything's connected。Really quick。

So is Ethernet's connected， okay all right。I'll see if。是2。If it doesn't improve， let me know。

There are other examples that we could do comparing Python。And snap。

 And some of these are things that are not actually built into S automatically。

 but you could decide to write them yourself。 So in this case。

 we don't have a direct comparison because they aren't built into S。

 But they're useful things to think about。When you have the advantages of a programming language。

 which just has a whole， you know， set of millions of people using it。

 these things sort of get built。So when it comes to strings。

 that page I showed you list a whole bunch of things that you could do to strings。

 so here's just a few we could say。Cat upper and of course， what we might expect that to do is。Take。

All of the letters that are lowercase。Turn them all into uppercase letters and put out a new value。

There's a really useful method called count， so Abercadair， we can count the A's。

 itll tell us there are five of them。And some really cool stuff。Like， we can。



![](img/5b9a74e9840a3a94018d66415f0d6d71_21.png)

Hello。Yeah。Professor。Miel ball。Okay， sorry about that。



![](img/5b9a74e9840a3a94018d66415f0d6d71_23.png)

All right。嗯。嗯。What的。Yeah。呃。Okay， I think folks can hear me now。Sweet， okay， what？Okay。

 I don't know what's going on on zoom sorry about that that is really odd all right so yeah so onm Python instead of directly translating this using something like Python's reduced function。

😊，Again， if you're trying to figure this on your own I'd say the smart thing to start off by doing this is to just Google how do I turn a list of things into a string or into text and in Python there's this nice function called join。

😊，And this is something that is a pretty common way that other program leaders should work。

But it's not the only way to figure about this and the way that Jo works in Python is a method that belongs to a stream。

😡，And so you kind of have to think about this in my mind。

 I think this is a little bit backwards to some of you this probably makes perfect sense。

 but you say our separator value so comma space dot join with some list as the argument。

 so I'm going to take a comma I'm going to join using a comma the items of some list。

That is the argument。To join and so if we do this。The sort of output on the slide or the Python output isn't shown here。

 but what I can do here。Is copy all this。And pasting it， hi fun， I' going to verify that。

Joining by comma Space， Apple Banana cow is sort of the exact same thing as would happen。

In snap and again， these two things are。Provent expressions。

 but they approach the problem in a slightly different way and so sometimes when we translate from snap to Python。

 it's about figuring out。You know is there a better way？That exists。In。

Perhaps in an environment like Python then was given in Snap。So actually， before I go on。

 questions on。On any of our string examples。Questions， anything else on Zoom。Oh， wait。

 why screen Okay， something weird happened。 Sorry， screenreshot stopped。All right， what？Okay。

There we go， sorry about that。Well， the slides at least are all available。All right。So。

The lab or one of the next things in Python I we' going pretty quickly。

 So lab this week and in the homework assignment， you'll get practice of some of this。

 This idea is an idea that is。😊，Relatively specific to Python。But is a really， I think。

 powerful idea， it aligns somewhat with some of the things that we do with MA。😊。

And it aligns somewhat with some of the ideas of like hyperblocks。

 but shown sort of in a different format in Python and what Python has is this tool called list comprehensions before we talk about list comprehensions I think it's worth just talking about sort of how map。

ItWorks in Python。So。In Python， and we'll talk a little bit more about this funny little syntax on Wednesday。

 but we could say we have this function called reverse。

Which swaps all the letters of a string it just takes。

It takes whatever's given and turns it into a reverse of that。And in Python， we can。😊。

We can have a function called reverse and step we can have a function called reverse。

And we could say map reverse over the items。Of our list， so through reverse of I。😊，It's just I。

 of course， the reverse of Anne is mom。The reverse of alonzo。Is。うんそ。No。

 it's actually not easy to say， but in Python， if we wanted to try this， we can。



![](img/5b9a74e9840a3a94018d66415f0d6d71_25.png)

呃。🤢，Copy this okay zoo。We can copy this function directly into Python。

What we get back is this kind of annoying thing。That is this map object。

And what's going on here is that Python when we try to do a map。😡，Is Python。



![](img/5b9a74e9840a3a94018d66415f0d6d71_27.png)

呃。Python's map function returns this thing called the map object。

 and this is one of those things that is really kind of cool about Python。

 but turns out to be annoying to learn。😡，It does a whole bunch of stuff in the background to make map a really efficient type of operation where it doesn't actually compute the results that you need until you specifically ask them so in Python if order were to do a map。



![](img/5b9a74e9840a3a94018d66415f0d6d71_29.png)

We need to explicitly say list。Over map。And we get the exact same thing as we wouldn't snap so if we're comparing one to one there's a little bit of extra work。

That goes in to。Turning a map statement in SN into a functional map statement in Python。

 we say map functioned over some list。But then we again have to explicitly convert it into a list and this is like a pretty nice analogy map in Python works almost exactly the same way as in SN where the first argument is a higher order function or in this case just the name row function。

😊，Without the parentheses， so not that。😊，嗯。's that is you know if I say reverse of。Hello。

 right I can call the function hello， I can get the value back if I just type verse。

Without any parentheses where I don't call it， this is just the name of a function that it is the equivalent of something like the gray ring。



![](img/5b9a74e9840a3a94018d66415f0d6d71_31.png)

And snap so I can。I can directly sort of translate from snap to Python this case with a little bit of extra work by turning something into a list。

 but what is really common in。

![](img/5b9a74e9840a3a94018d66415f0d6d71_33.png)

In Python is to do something。Like what is called a list comprehension and this is one of those cases where there's not a super clear analogy in S you could actually build a block that does this if you wanted to。

嗯。But。哎。A list comprehension is。Is a special way of taking some data and turning it into a new list without necessarily assigning a new variable without writing an exact for loop and this is the sort of preferred method in Python and the way that it works is something which is。

哎。哎。You have to think about。The syntax is a little bit funny here， but you say square brackets。

 so think about in Python square brackets mean list。Insider square brackets。

We say reverse of x4 x in L， where L is our list。X is sort of like before each inside of a regular for loop。



![](img/5b9a74e9840a3a94018d66415f0d6d71_35.png)

And what Python does is。I'm not going to assign it to variable， but we can say reverse。😊。

Of x for x in our list is L。And this returns a new list。Where。

Each item is the reverse we could sort of think about this if we weren't going to return a list。😊。

You could say for item in L。I could say print。Reverse。Of item。And when I enter again。

 I run the for loop。So a least comprehension is not exactly a full loop。

 Python is doing different things behind the scenes， that's not so important。

 but what is important to think about is in Python。

this tool exists and so this is something where as you learn Python。

 especially if you go on to take CS62 anA or CS88， you'll start to see expressions like this that do the same kind of thing as a map but doing a little bit of a different way and this doesn't use a higher function doesn't use a map object。

But you know， it's。Dynaically uses a square bracket of things， it creates a list。

 it returns the result， and so on， and let's see what else is going on。Okay。

 cool answered answer the question yeah。😊，This is one way of also thinking about things like map statements and Python is。

 it's not exactly the same， but it accomplishes the same goal yeah， so question on this。

I probably like staff that it answer like。吔屎。好。Yeah， so for those on Zoom。

 the question is sort of is it is Python kind of like snap where it has？

I built on things that you can call if you know how to use them， I would say。In this case。

 there's a couple different things that I'd say is that a list comprehension I would distinguish from a block and snap。

In that it is。A like this is a feature of the language。That。

Implemented in Python that you sort of have to learn you know by some format exists in general。

 I'd say with a language like Python compared to S is that everything is。😡。

You know is sort of hidden in the background， so if I open a text editor。Like， well。

 any of them are fine。

![](img/5b9a74e9840a3a94018d66415f0d6d71_37.png)

But this one is Viual Studio code and yes， you're going to tell me to update。

And I just start writing code， right？呃。Yeah， the the。The downside of something like Python is that。😊。

When when I just start from blank file， right， there's really nothing there。 There's。

 there's not much to guide me in。In suggesting what。Jews language has and so to some extent， you。

 everything in Python is hidden behind something。Sometimes an editor。

 so visual Studio code is pretty decent at this of Ito this is a Python file。

It has features that will say， oh， I know what Python is。

 I know what functions are built into Python， and I'll suggest them to you。😊，But in general。

 what a lot of using a language like Python is。

![](img/5b9a74e9840a3a94018d66415f0d6d71_39.png)

iss learning through documentation， through lecture through practice， through Google searching。

 whatever it is over time， what those features are and I do think it is。

 it's a super useful practice， but it is definitely one of those things where trying to figure out what you can do in Python is not as easy as taking a look at the palette that are in snap overwhelming though they may be at times and just scrolling through clicking something。

 dragging it out and。Hopefully， you， if you're feeling frustrated by S at this point。

You always have some appreciation of the value of that you know the different challenges that you face learning Python。

 yeah， so there are sort of tradeoffs there， things like you know map and stuff like that。

All of these functions are built in what I would say is that in Python there's definitely just more stuff that is readily available。

 we're not going to talk about using libraries， but in SNAP right if you go to the file menu you could say input libraries。

 there's this browser sort of， you know a couple dozen libraries that are prebuilt that exist in SNAP。

In Python， there's also dozens， if not hundreds of libraries prebuilt into Python。

There's like one called math， which lets you import all the math functions。You know。

 if you need like a solid value of pie or something like that among other things， you know。

 so there's a whole bunch of different kinds of analogies there between what's built in and what's not。

But yeah， these are。呃。Two sort of two different ways that Python provides that that S doesn't quite。

Have for some of these。Other questions so far on list comprehensions or less strings in Python。

Anything else on Zoom？Okay cool。One thing again， to about here is whenever we see square brackets in Python。

 we're going to think about a list as the data type。

And so if we say square brackets with some code in between those square brackets。

 what we're probably doing is building a list up。So。This is。

The expression that we have is some function for some variable in some list。

And we can translate this list comprehension to a map if we wanted to directly from SNAP。We could go。

In project three or homework three， excuse me， if you see an expression like this where we say map over some list。

 you can in your homework assignment， you could translate it directly to a map。

 you could translate to a list expression or list comprehension， both those things would be valid。

Yeah， and so there's there's more than one way to do this Python extends this idea。😊，Of map and。

Keep to。A function is well called filter。And filters another one of those functions。

That it's just built into Python。Where if we wanted only be long roads。We can。

I just didn't bother changing Josh's name any slides。But we can say because I am not Josh Hgg。

 but we can then say。呃。If we have a function called longer than two。

 so this would just be the length of some stream is greater than two。啊。In staff。

 we could say keep items longer than two from some list。In Python， we can do the exact same thing。

 but instead of keep。It's called filter。And we could say filter things that are longer than two over this list L。

And then we can。Similar like what we did before is we could map reverse over that value。If I。

So here I'll just define。呃。Let's see。

![](img/5b9a74e9840a3a94018d66415f0d6d71_41.png)

just。So if I did this right again， I would get a nap up back so if I wanted to see the result。

I can turn this into a list。And I get just the three and four letter words in this list reversed。啊。

And so。In that case， again， filter。And Sn works very much like。Filter or excuse like keep in Snap。

And if we wanted to verify that without reversing。Filter is the same same structure or if I want to see the result。

 I need to turn into a list。Of course， I need to。Name it correctly。So I can filter any list。

What I get back then is another list with just the items where that function is true。But this is。

 as you might expect。😊。

![](img/5b9a74e9840a3a94018d66415f0d6d71_43.png)

Not the only way to filter data in。In Python， so Python extends this idea of a list comprehension。2。

Supporting sort of an extension where I can say reverse x for x in L。If。🤢。

Length of x is less than2 or if any sort of condition is met。

 then that will restrict by the output of our expression。嗯。🤢，Let's get back here。

And just try this out。

![](img/5b9a74e9840a3a94018d66415f0d6d71_45.png)

So。😊，And what we get back。Is the exact？The exact same， so reverse of x for x in some list。

If the length of x is less than two in Python list comprehensions are。呃。

You or tend to be the preferred style for for how you solve are they sort of map and filter problems Now sometimes you just want to filter without mapping。

And unfortunately。You know， I can't。I can't just say4 x in L。If length of x is less than two。

That's not going to quite work。Something needs to be on the very left hand side here。

 but I could say x for x and L if x is the length of x is greater than2。

And this would be the equivalent miscomprehension version of just a filter or a keep depending whether you're coming from stamp or Python and again this is just one of those things where。

😊，Each programming language has some of their preferred style in how we map things。

 but list comprehensions are a super useful super important feature and in Python their syntax is pretty special this is built into the language it does work for things other than lists。



![](img/5b9a74e9840a3a94018d66415f0d6d71_47.png)

But they get mostly used in Python on list like data。Any sort of questions on？

On this idea of list comprehensions。Anything else on Zoo cool。2。Yes。

As I've mentioned most of this before is that？Give you a map and filter。Generally， equivalent to S。

 what Python does。Is they tend to prefer using with comprehensions and this is something where there's not a direct equivalent within SnAP。

😊，But you could actually look at building a block that works the same way if you wanted to en snapap。

嗯。The one thing that will sort of end on today is that this is something that we call an idiom in a program language is that each programming language。

 aside from having a paradigm， like functional and like imperative or object oriented。

 they have idioms。That are representative of a particular style。

And we kind of compare them to idioms in spoken languages。You know。

 people say something can set the world on fire right for something that goes viral again。

 this is sort of an idiom because we are hopefully not literally setting the world on fire。

 there are aims in every language and translating them is of course， a particular task。And so。

One of the goals to show you is that when we program in a particular language。

What we're trying to show is that there's not just a complete translation of A to B directly。

That there is you know multiple correct values and so that's where I'll leave it today since we don't have time time for Python we're going to on Wednesday。

Get a lot of practice using lists， so sequences of data treating lists as items that can be accessed so some。

😡，If you saw that opaque colon and colon negative one syntax in the reverse function。

 you could choose the next couple days to look up how that works。

 but on Wednesday we'll actually talk about what that means and sort of how that works so we'll pick it up there and then we'll see on on Wednesday。

😊，Thanks everyone， sorry about the trouble zoom， these slides should still be all up on the website though。

Okay。

![](img/5b9a74e9840a3a94018d66415f0d6d71_49.png)

。