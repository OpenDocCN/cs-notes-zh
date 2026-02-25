# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p17 CS10 Lecture 17 (Mar 30)_ Python III.zh_en -BV1BokLBmEKE_p17-

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_0.png)

Okay， that looks good。嗯。So。Okay， so。Today we're can make。Basically just continue on with Python。

We're going to do some auditoryed programming， but before we get there。

 we're also going to finish up some of the data structures topics from Monday。Basically。

 for this lecture and there's going to be a couple more。

 we're kind of just going to be continuing on the tour。The things that you can do in Python。

Some of them will have career analogies to snap， some of them won't。

Today's stuff are going to be things that are a little bit harder to represent directly in SNAP。

 but there are oh yes thinking there are some sort of similarities still。

The first thing we want to talk about are sequences of data， so those next three things are all。

Data types that Python provides that allow us to treat them as not just a single entity。

 but a sequence of individual items in a single package。Perhaps we to be slightly more。

Slightly less obvious types of sequences， but still turns out to be really useful。

Is the fact that a string in Python。a sequence type。And。In SAP。

 we don't have necessarily built into SnAP。😡，Exactly the tools。That Python does for。For text。

 but in Python strings。Strings are。呃。Are types that you can？呃。

That you can sequence data in and so we're just going to do a couple。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_2.png)

It's going to open up Python。We'll see a couple demos。呃。

I actually don't want to name class because that's a special word in Python。

I'll just type that out so a stringing python is just any series of text characters in in one go。

And streams support this idea that we'll see a lot today。

 which is called slicing and indexing so in the same way we had a list in Python。

And you're going to do some more of this in lab today and tomorrow， but we can use square brackets。

To get a particular position of something。In a string。

 in the same way that a list is a bunch of items， a string is typically what we call a series of characters。

And so。😊，Character zero。Is just the first character in our string。Character， what is this？

Like let's say three should be the zero in CS 10 because that's the fourth item in our string。

 since we count by starting in zero， that's item three。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_4.png)

And strings let us do all of these。😊。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_6.png)

Potentially useful things what strings also let us do。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_8.png)

Is。Something that we've demo a tiny bit， I believe， just before a break， but we work the same way。Is。

Is they let us use this slicing notation， So slicing in Python。Is giving us a start position。

 an end position。And what we get back from the string CS10， we started to。

We end at four except in Python our end position。😡，Hes always exclusive。

 So this is really saying give me the values index two and three from our string because that final value。

Is。Is excluded so if youve use sort of you know mathematical terms right。

 we could say that this is like inclusive two and exclusive of four。😊，Is。

Is the way that this gets described in this pattern in Python where we include the first thing。

We'd say everything up to but excluding for。As the last item will show up again in a moment so so those are strings they support coning in the same way that lists do and it doesn't matter what the string is。

 whatever sort of characters， however long they are we can get back a sequence of multiple characters at once we can get back a。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_10.png)

Single character at a tongue。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_12.png)

Python is pretty flexible with all those now what we can't do with this stream。Is， I cannot say。

Something。Like。I can't change CS 10 to DS 10 because strings in Python like most programming languages。

Have this property that we call them immutable， but essentially it just means that we can't change them if we have a string that string is set by Python。

 we can rename a variable and assign it to a new value。

 but we can't change just a single letter of a string at a time a list of course we can change the values。

Like we can stop。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_14.png)

But this is something to note just because we can。Access individual values doesn't mean we can reset those values。

Strings don't want us do those kinds of things。Compared to。Snap in Snap if you haven't seen it。

 you go to import library or you go to the file menu you click libraries。

 there is a library called Word and sentences and another one called string processing utilities。

 they add a bunch of functions to S。That let you do。Some of these things they have。

Sentence to list block that exists in snap sentence to list and snap is just split text by the space character。

 so it's not a particularly。Advance block。对。2。🤢，The point just goes that strings themselves are another data type。

In Python， and they have their own series of functions。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_16.png)

That potentially makes sense so like on Monday we did upper and lowercase。

We can always do something like length， this tells us how many characters are in a string。

How many letters essentially？

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_18.png)

Many of those things map。Pretty similarly from Python。To snap。Now。

 what's nice about sequences in Python？This is true。lists。

And of strings and of the range function that we'll see in a bit。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_20.png)

Is。That we get all similar kinds of behavior for free。

 so I could say something like is the phrase CS。of course。And this is true because。

What the in function is， it says， take the thing on the left hand side。 I this in some component。

Of our sequence。On the right hand side。I could ask for， you， is the phrase data？In our course。

 and this would be false since there's no phrase data inside our string。

The good thing about Python and recognizing this is that strings and lists two totally different things。

 but the ways in which we access that we treat them as data can be really similar so in S we have you before each loop where we have for each item in some list。

😊，We might start thinking about that。As some ways that we can translate stuff。

 so I could just say four。Letter。Pse。Print。我的。And this just follows right that strings and lists。

HeSo that the both sequence is because we can access a single character at the time。

 we can write a form in Python in pretty much the same way in S this would require us to turn。

That string into a liston strings are a sequence will just give us the tools automatically and what that means is when we see things like in。

 when we see things like four loops， the brackets for slicing and accessing values。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_22.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_23.png)

We should kind of start thinking about these data types operating in similar ways。And so。

Strings and list two of the most common， what Python also provides。Its a really。

 really useful tool called rangenge。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_25.png)

And。Range itself is one of these things， which is built in as they sequence。

 So I could say range from 0 to 10。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_27.png)

Rang。10 also gives us an item which is exclusive at the end。 So if I just say range show to 10。

 Python。W me to first convert it into a list。诶。To see all the values， but if I say range zero to 10。

What I get back are 10 items， but it's the numbers zero to9 because we include zero。

 we exclude the value 10 sort of thinking about this as everything。U2， but stopping right before 10。

And this range itself is also a sequence， so I couldn't write something now that we know about the in keyword I could perhaps say。

😊，Is B value5？In range zero to 10。Given that we just saw that list above right。

 we can see that five would be in that value set。But， of course。

Something like 5 would not be that value set。And because these orange ranges。

 we can also do things like if I just hit the up arrow a few times。Item index three。Of this list。

 so the range zero to 10 starting at zero going to nine， if I ask for an index。

 it's just going to be the value， the same value back。

 but we could sort of dis verify that the types of features that we expect，Work pretty similarly。

Snap， it's not quite the same， but similar enough is the numbers one to10 block。

And Snap is a very similar version to the range function of Python， right it gives you a list back。

Remember're starting from Sun value any at sun value。Snap， of course。

 I think it's a little bit more intuitive that if you ask for a list to include one。

 you want it to end at 10， you get both items back。And you sort of use it sort of the same way。

And Python， because we start counting at zero， we typically will write range。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_29.png)

In in this kind of format。嗯。And because this is a sequence。

 it is pretty common for us to say something like four， you know， some number。

In some range as a for loop。And in Sn in the。Homework three that will be released soon。

 you'll actually see a couple patterns like this where。In Snap code。

 you might not have had a need to do this yet， but you can actually write for each number。😡。

Numbers one to10 or whatever it is。Those two things translate。Pretty prettyt much I。

You knowIly to one another。Oh。Yeah。😊，Any questions on sort of these things as sequences， yeah。好的。

那么就是这。So you mean that this list includes the value 10。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_31.png)

Yes， there is。Going to。So if I want this thing to include it， are you 10。In my output。

 I just changed the。Where it stops this kind of a simple answer。

 but illustrating the fact that this is when when we' programming and when。

When we're thinking about like how languages work。Given that staff or。

 given that Python starts at zero。The way that I like thinking about this expression is if I say zero to 10。

 I'm going to get back。H values and I want something which is。

So  zero to 11 would write den new back。11 values if I want。0210， excuse if I want one to 10。

 I would say stood at one。Give me。And then increase the end function or the ending value by one you will actually see this quite often in Python code that depending on the context people take some value increment it or decrement it by one depending on you know what direction they're going so there's not necessarily like a built an approach。

 but this is， you know what I would think about is that you'll see something in snap that it's going to say like one to 10。

And Python， if you want it to be one to 10， you'd have to translate that to 1 to 11。😡。

Perhaps you actually just went zero to 10， which represents the value zero to nine。

 because that's how you would index them。Right if we want this value 10。

 we just have to be careful because a list of 10 items won't have an index value 10。

And so that's why Python leaves that off。The end。This is one of those things that like as I'm going through this feels really nit pickky。

 it's pretty easy to get hung up on some of the details of like。Why does this stop here。

 why does this you know translating back and forth what I would say is that this is one of those things that gets。

The more you practice with Python。or any other programming language that starts counting at zero。

 the more sort of second nature this will become and that no matter how second nature it becomes。

 you'll still make mistakes I constantly，have some off by one error in code that I write。

But you'll start to sort of get some intuition behind。You know。

 thinking from counting at zero and adapting code that way， but yeah， good call out， other questions。

是。Right right， so。One other sort of gotcha in Python。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_33.png)

Comp here to snap。Is that？Python has。Very explicit rules around the types of data。That exist。

In S if we start。Using things like the ad block。And the join block。

Snap will try and do what it thinks is sensible oftentimes this is the right call。

 Sap does something that is sensible and occasionally。

You knowS is something that we think is nonsense， but in an example like this。Whoops， if I。

Go back you。2。Oh， that's。Fantastic。啊。How great of you sure。嗯。Dro， that's weird。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_35.png)

Where was I？here。So impacton。我。Copy， paste， cool。呃有啲啊。All right， so in Python， we have two values。

 we have a number in a text and snap。😊，These two things are totally different。😡。

They're totally different variable names， but if we say join a number and a text value。

Snap just decides， yeah， I know how to add some values together。In Python。We get this message。

 which contains a lot of detail。But is a really useful one to understand， so type error。

Unsupported opera types for plus int and stir。 And what Python is telling us here is that I'm trying to add some number to some string。

😡，And that it doesn't know how to handle that conversion automatically。

This is one of those things where if you see a message like this， it's really useful to take。

The 30 seconds to minute to read it and follow， you know sort of what's happening。

 So do I understand that in this print statement that I just wrote that this thing is actually some int。

 some number and that this thing text is actually a string that I expected it to be in this case。

If I。Vify this right number is five。Text is something that looks like a number。

 but because it's in quotes， it is actually just be lital character  six， it doesn't have。

A value of six。And if I wanted to。I could say。Use any number of functions to convert these things。

So I could say stir of number， and if we notice here。That stir of。

Five is the value five but it shows up in quotes， single verse double quotes don't matter in this case。

 that's just sort of the default output uses single quotes， but if you write with double quotes。

It doesn't matter， but these two things are they are different types of Python。

 even though as humans we can interpret them in either way。

That means that if I want to now combine them together。I couldn't say stir。Of number。Plus， text。

In this case， I get the string representing the characters 56 or five and six together。

Which may or may not be what I want if I wanted to add the values five and6。😡。

I would want to do something。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_37.png)

A little bit different。Which in this case。perhaps if I wanted to treat the value6 or the string six as a number to get the result 11。

 I could then use this other function。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_39.png)

Yeah。I could say int。Of text。This would give me big value。Six as a number。

So I can then write in of text。Plus， our number。If I type it correctly。

 and this is the value6 plus the value5。😊，Is 11 as the result。

And this is why when we're talking about different types of data。

 we're talking about converting from one thing to another。😡，All right。

It is important to sort of make sure that we understand what way we're going。

 what direction we want that conversion to happen。Because if you start converting numbers。

Or strings to numbers and then adding them together。😡。

56 is probably not what you intended if you wanted to compute5 plus six。😡。

But maybe it is more likely you wanted something like 11 is the result， so Python provides functions。

😊，あ。So we have int， which we'll take。😊，Here， any。Any string and do its best to convert it into an actual integer value。

 we have stir， which takes。Any kind of object， whether that's a list or number or something else and turns it into a string。

 this is the exact same thing。As the list function。Which we used on the range object earlier。

 so Pyth has these conversion functions built in for pretty much it。know。

 prettytty much every type of data that Python has and we're not going to do it through all the types that it has。

 but those functions exist。A questionest in Zoom chat how do you access Python。

 All I did to open Python today was to just type。Python， in my case， Python3 is。

I Python version three， some computers you just type Python if you get Python version three。

 it depends on how it's installed， but for like most Macs。😊，Most sort of other installations。

 Python 3 is what you type to。To open just a Python interpreter。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_41.png)

啊，So。So those are the different types。呃。Each function that some。Ojectite support may or may not work。

For example。In。And lab， and I believe just before spring break。

 I don't know if we got to the example orre pending to a list。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_43.png)

But。We can。We could say x is equal to range。啊。Also， by the way。

 just leave off the leadinging zero and I get the values。Z2 four。So if I say x dot aend。

Af this is not going to work。For。啊。🤢，A list acts is equal to a list。Just so I can see this。

So list x is now the values zero to four。So I could convert something to a list first。

 the append function just takes whatever value I have， it sticks it on the end of that list。

And in Python， because lists are a mutable data type in the same whether they're in Sap right。

 this is like the add item to list block， so if I look at list。X again。

I've just added a value and this is just to illustrate that in Python。

It is sometimes necessary for us to convert from one type to another。

But the type of the thing that we're dealing with can have an impact on what。😡。

What Python allows us to do？For most of the builts and types。

 you'll just use the name of that type to convert it from one thing to another。And and that's。

 you know， over time you'll sort of see an error， you've got a right， okay。

 I need to convert that first， but you'll usually get some kind of message where it tells you that some object doesn't support somebody in this case。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_45.png)

The error is a little bit different， it says attribute error。

 and this really just means that this data type range does not have a function。

That it has defined called append。Sometimes it'll be the error message will look a little bit different。

 but the outcome is the same and all of these error messages are sort of， programmers speak to say。

 hey， something's gone wrong here and over time you'll get a sense of when you see a certain error message what you should do。

I'm going to go through in a ton of detail。About twos， but just to illustrate that they exist。

Tupils are instead of using square brackets and Python they use parentheses。

Temples are another sequence of data that could have multiple items in the amount of time。Like list。

 they can have numbers and strings and other tros and other lists inside a single tuple。

 but what a tuple is is it's just a list that we can't modify after we've created it。And。

Now what we mean by that is we say that tus are mutable， so we've made this object called some tuple。

 I can no longer change the values of some tuple， I can say some tuple equals something else entirely different to we assign some value to that name but I can't actually change the values of this tu and why do we do this well sometimes it's really useful to have that protection that says。

 hey you programmer， I'm creating some set of data， I really don't want this to change if。😡。

You might see。If you do some data analysis or some research where you're loading data from a file。

 you might。L bit data from the file and store in something like a tuple such that you never accidentally modify your original values。

 right， You don't want to。To be doing some data processing on a data set and accidentally overwrite。

Somere results or something like that， so Ts give us some protections that say I don't want this list to change if we do try to change the list or excuse the tuL will get an error from that。

And so that's。Just one of the other Minnesota data types that exists in Python。

So we're moving that along。や。Get this。我 again。So why have all these things。

 the goal here is really to give us programming languages。That are expressive。

To years a programming that there is something built into Python that probably solves at least the basic problem that you're trying to address。

 but also that you know we say that we want code to be beautiful in the sense that we want it to be。

Concise and we want it to be readable and communicate its meaning。😡。

One of the things that you'll hopefully continue to realize as you program。

Because that the better you get at programming in a lot of ways。

The code that you write can be much simpler and that you'll recognize that。

Instead of saying if a return true else return false， you might just say return A。Or。

You recognize the ways in which if you previously wrote a full loop， you can probably perhaps use。

Map or keep expression to communicate the same type of ideas and。In general。

 our goal is to give you the tools to simplify things， so similar to SN。

And Python willll try and avoid generally using global variables so we'll pass inputs to functions。

 we'll have functions return the results。Those are。

Pretty much the same way that blocks have inputs and they can report a value in S。And as well。

 Python gives us these tools of having twopos that are notable that don't quite exist in SNAP in the same way。

 and those can be a really useful way。😡，sort of restricting these set of problems that can go wrong。

 but there's lots of different ways to write code and over time。

 you'll find the things that work for you that work in the project。三？

We're going to go through all of this， but this is just。

 I think something that is sort of fun to understand is that every programming language has a philosophy that's built in。

This one is called the Zenev Python。And it sort of is。

Like this high level guide for how the Python team thinks that Python code should be written in a Python interpreter you can type import this and you'll get back the whole thing。

 but some of the guidelines I think are really just worth thinking about and these honestly apply not just to Python but pretty much any time you programming。

Explit is better than implicit， simple is better than complex readability counts。

Although practicality beats purity。And I think that these are some things to think about like when you're writing code。

 you're not。You are in some ways perhaps just writing a project for yourself。

 trying to do some simple task that no one else cares about and in that case you could do whatever you want。

 but when you're working with a partner on say your final project in CS10 right？

They need to understand what was going on inside your head and。You。

 that can be a really challenging thing to communicate。 And so trying to write code。

 which is simpler， which perhaps does。A little bit less or uses it built in Python function。That's。

to solve all these edge cases for you， those things are really good things to take advantage of。

 I also really like the fact that you know。The statement， if you read through it。Some of the lines。

 you know， although practicality is better than purity is we teach you functional programming in CS10。

 it has a lot of value in that if you do things in a purely functional model。

 you don't have to worry about global state， you don't have to。

You're less likely to sort of have a bug that comes from a global variable。

We'll see all over the place that， it's practical to have a global variable。

 like a game board in 2048， where it's practical to have some sort of global state。

Because it makes our programs a little bit easier to use。

All of this is to say there are goals when you write programs， but being dogmatic is of course。

 not super helpful。嗯。So moving right along before we finish up with a couple different types of objects in Python。

あ。And we'll finish up today with the start of object related programming is Python supports two different kinds of objects。

That are。We need to use。あ。Give us some different sets or some different functionality。

 one of these is a set。ASe in Python or in some other program line use is pretty similar to a mathematical set and a set is。

Similar to a list。Only one instance。Of of。Of an item can be in a set Importantly。

 a set is not a sequence， so we can't necessarily access。Item zero， item one， item two。

 but it is a collection of items。And otherwise， there's not necessarily。Some magic。

There's no built in syntax for creating a set， but sets are a useful thing。

If I ask for a set of the values。One， two or one three and five。I get back。A。比东西。诶人。哎。So。😊，不知。到哪里去？



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_47.png)

Yeah。啊。So。If I ask for a set of values， what I get back is that list of values。

 but with all the duplicates removed automatically。

 sometimes people use sets just as a really simple way。To remove duplicates。

I can see what set one is。Because it's a set。I can't do something like access。

The the third item of our set and this is because sets in python don't have an order。

 so if order matters to your data they're not a good choice， but they are super useful。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_49.png)

就是。So sorry。I'm not going to run this example， but they are super useful to do things like this。

 take in some text。And give me all the unique words， you could write a full loop to do this yourself。

 of course， but perhaps you want to just say， I want to know all of the unique words in some text。

Take that text， split it by space， turn it into a list of words。😡。

And use the set function to restrict all of the duplicate values。 So those types of things。

Are really useful。Purposes for for a site now， the other data type that Python has。

That you'll get some experience with the lab。YouThis week is a dictionary。Dictionaries are， I think。

 one of the most useful types。That exist in Python and other programming languages that don't really exist sort of natively。

In Snap， you can write a block that builds dictionaries if you'd like。

 but what a dictionary does allows us to assign what we typically say is some key to some value or some mean to some value。

These keys。Are just strings， in this case our phone book maps the name of some person to some theoretical phone number and all these phone numbers。

Or of course， fake。三。So dictionaries are one of these tools that。

Over time as you can use your problem， you'll find you can just pull them out and solve a water。😡。

A lot of particularly interesting use cases。So in a dictionary。NowBecause of this。

 we often want to do things like know， what are all the things in my phone book。

 who are the people that I have saved there， so dictionaries provide us a dictionary do keys method。

 this returns all of the things in our dictionary that we know about just the names。

Dictionary values is a method that returns all of those values disassociated from the names。

 so maybe you just want a list of。If it's a homework， just all the lists of numbers。あ。

But with a dictionary。You can let's see。I actually choose to。To run this example。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_51.png)

members。Yeah。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_53.png)

So in our dictionary。Ks and values returned。Just。Meanwhile， it's not numbers。Yeah。So。

This just maps some， in this case， number two some letters。啊。🤢，Or。

And we can use another method called dot get in Python， which is。A really useful thing that works。

Alongside our square bracket mutation， so I can also say。New ruless。呃，I。To access a particular value。

 so dictionaries work。Like a list in that sense， but instead of accessing items。By some position。

 we have a N which。Hopefully gives us a little bit more description。About some type of thing。That。

What we're doing。We might see dictionaries that if this is a phone book。

You can group things based on name。Based on， let's say， email address， whatever it might be。是。

Im going to go through all the things today that you can do with dictionaries。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_55.png)

But pointin out that they are super useful。That's yeah， so before we continue on let questions about。

Other kinds of sequences or data types that exist in Python and today is kind of going through。

Wlwind of features that exist。So。嗯。Hい。My name today。

I would say these two elections are a lot of just。There are things that Python does and here are ways that it's a little bit different from SAP。

 but for the most part。There are things that we can map。Very straightforwardly， from one version。

One piece code snap to one type of thing in Python and the goal of all of these tools。

Is to give us some way of expressing ideas， not just in Python。

 but in a way that is hopefully a little bit more concise。

It givesive us some new techniques that we haven't seen before。And。嗯。What。Going to do now。

Switch over to。Talking about object or programming and we're going to continue with this on Monday of next week because it's a pretty big topic there's no way that we're going to do everything today。

 but object or programming，Now answering the question if I made some list called L。

And our list L has this method of pen， I can keep calling a pen to modify that list。

I could print out， I could see the result， how do I make my own functions and my own objects that work kind of like a list。

 how do I make something that has its own unique methods that are a part of that？How do I make。

 for example， this thing that we're going to work on for the next couple of。Lectures that represents。

 let's say， a time object in this case。Our times are hours， minutes and seconds。

 but we'll get to all of that。And what we want to be able to do with our time method。

Is have it work in a similar way or time object， have it worked in a similar way to other。

Other objects in Python， so Python provides actually a method called sorted。

Which takes a list of data。And sorts it and we'll talk about why next week this will work and how to make it work。

 but for right now what we want to get started on is just thinking of this idea of making our own objects。

And objects are。A a way of giving a name to some particular kind of value。😡，So。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_57.png)

呃。And in particular， what they do is。And。哇。Is they allow us to do something specifically。

 which is to say。That。This thing has its own new type， so if I say print and you're going to just。

Introduce this function。Called the type functioning。And for this example。

 I'm actually going to work on this file。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_59.png)

So I'm going to say Python。Swing。诶 timed up pie。And when I run this， because I'm knowing the file。

 I will explicitly print things that come out， our time dot pi file creates some object here。

So we'll go back。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_61.png)

All。So let's。It's a little bit smaller。嗯。MaybeYou not can to cooperate， that's fine。

And what we get back。It tells me that this thing is class。

It tells me that there's some really thinkingky main method we'll see that return or we'll see the double underscore thing return a little bit。

Its name is Ma that time and that's because I have a class。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_63.png)

The nameme time。And as we go through and do this。What we'll be able to do is today we're just going to work on a time object。

 but you can think about how if we're building a more complicated system。

 perhaps we're work in a project where，😡，You have a game board。

 you might have some piles in that game board， you might have players having a clear way of organizing。

Each of those ideas into some concrete representation can help make your code more readable。

In Pyon to make a class， we use this this word class。 we give it a name。

 the name in this case is time and everything that belongs to this class will eventually fill out is indented in a similar way to a function。

 But what we're first going to do is just start adding。Some attributes。

AndEventually I won't paste these in the file， but for right now。

 this code has links to Python tutor， Python Tutor， the tool at CS62 A， you use pretty heavily and。

But Python treaty will show us。Is you could just go to Python Cer。com or tutor。cs6winname。

org of the same thing。Python tutor runs each line of Python code step by step and it shows you a loose representation of what Python is doing under the hood。

 so this global frame sort of just always exists in Python it's where。

Our global variables are stored。We create this thing it tells us that we have an object。

That is a time class。We say t1 equals time， we get this instance。

It tells us it is an instance of time as I click forward， I say T1。

 let's scroll over here about hour 17。T1。M is 10 and t1。

2s 22 what this will do is it shows us just that we're taking our class and we're storing attributes inside we call these things attributes。

They essentially work。Similarly to storing data and something like a dictionary。

 but we have a name where in this case we say objectject that name of something equals some value。

And if we don't use the equals function， we can read that value back by saying t1。 hour。

 and so what this will do is our final thing will print。😊，Some string that says T1 is。17，10。

22 separated by a colon。And。Oh。What we have now is。哎。

Is a series of attributes that are stored with this class。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_65.png)

So。어。Yes。还定。So if I want to， I could just run this file。

 I can pick names of whatever sort of whatever class。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_67.png)

Attributs you want。Oh。For the last few minutes before I pick this up on Monday。

I will just introduce a or briefly introduce this concept。A tool that Python has。

 which is really awesome。This is one of those things where in SNap， you just use the join block。

 it converts between text we just drop variables in。In Python doing things like saying a clusterster。

See and so on。This can get pretty messy to read。And so Python has a bunch of tools that help us format text。

And one of these is。We can replace all of our variable names with curry braces。

So we say1 we say T1 is curly brace， colon curly brace， curly brace。

Dot format and when say dot format， we pass in the names that we want to format in the string。

 so our first curly brace here becomes our our second becomes minute。Third becomes the second。

Value our second space， meaning our second cur race is not the second value of our time。

And so this is something that you'll see。There's actually so much core that exists。🎼嗯。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_69.png)

In in Python now and this exists in some other languages as well， so if you go on。Two， let's say。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_71.png)

呃。🤢，Let me save that file。え。It whoops。Let me rerun it。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_73.png)

So you can't tell here。That is the same result。If you go on to learn languages other than Python JavaScript in the web browser。

Ruy on railils for building web applications， plenty of languages support this kind of syntax。

 so we call these format strings because we start with this funny syntax of just writing new letter F before our opening quote。

😊，So we often call these F strings and we say F quote time is and instead of saying that format at the end。

 we just put our variable names right inside of curly braces， so this is special syntax。

 it is one of those things to sort of learn about how Python lets us combine all of these tools together。

But this is a case where。Over time， the programming languages community to sort of figured out there are nice ways that we could actually make it really easy for programmers to write code。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_75.png)

which is a little bit more readable so you know these have only been to around on for like seven or eight years now in Python but this idea also exists in other programming languages and so you'll see this in slides and lab and it is。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_77.png)

A much nicer approach to formatting code， so that's where we'll leave it today is classes have attributes。

We can write some nice texting format then。Any sort of before we go last second questions anything。

 I mean I'll be around afterwards as well， but next Monday we'll pick up with building out all the things that we could have an object in Python do on our own。

我现在呢。Everyone onm Zoo。What。Yeah。Chrisions from Zoom。



![](img/d4476a1b4a8b6dd5aff75cfaa8062541_79.png)

嗯。