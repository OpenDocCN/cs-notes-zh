# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p19 CS10 Sp22 Lecture 19 (Apr 6).zh_en -BV1BokLBmEKE_p19-

![](img/dbf9290753328bd808fdde359f2de077_0.png)

![](img/dbf9290753328bd808fdde359f2de077_1.png)

![](img/dbf9290753328bd808fdde359f2de077_2.png)

![](img/dbf9290753328bd808fdde359f2de077_3.png)

然好。Okay。Oh， why is that up so high？Onces。All right， that's a little better。Okay， I that。And okay。

 cool looks like's doing this good cool， So today we're going to sort of just wrap up。

Some loose ends with Python， I did want to put out a couple announcements。

There'll be more info on some of these later this week The first thing is really good news for everyone the way that the drop score was calculated on the midterm for both the online and final exam the way that it was displaying gradeco meant that it wasn't actually giving you it was taking off two points instead of taking up zero points basically just about everyone took advantage of the drop score for questions one to six so everyone's midterm score went up by two points so if you look at again your score should be two points higher a few people submitted reggo requests double checking the work so thank you for that you're absolutely correct I should have given you two points back and so that mistake happened to everyone and now everyone gets。

This is why gradeScope is useful at least because if we need to correct something。

 we can give you all two points back。That's just just there the final thing on exams relating to the final。

We haven't talked about this yet normally we have an inLB midterm and an inLB final this semester we didn't do the inLB midterm there's just kind of a lot going on。

 but we will have an inLB final and the way that this will work is it'll be during your last lab section that you regularly attend。

On the slide there's a link to past paper and inL finals。

 but the way that the inLB final typically works is we give you one sort of multipart question。

 it usually means filling out two or three related blocks to a function。

 it will be in SNAP and so there won't be a Python option for the inLB final just so that regardless of how you're filling up about Python。

 everyone' sort of on the same page。哎。And basically you'll have 100 minutes。

 so all of lab time minus know the 10 minutes for work time 110 minutes to solve a question。

 you get all of snap basically just what's built into snap and。

We'll give you some instructions we'll show you you what the block should do give some explanation and you get to write a few a few different kinds of functions。

 usually it'll involve something about lists somewhere probably some kind of high order function it could involve recursion but。

It's usually a couple questions 110 minutes it's not designed to take you that long in fact many people finish you know in half the time or less and so that's the way we'll go yeah。

 so questions on inm for students who are taking who are mostly asynchronous will do the same thing as regular final exams where we have you schedule a time to take take the inL final same sort of deal where if you're taking it remotely well ask you to do zoom proctoring but otherwise。

It should be fairly straightforward at the end of it you'll upload your snap file to gradeScope like any other home assignment and basically that'll count for about 20 to 25% of the current final exam grade and it gets combined with your final exam grades so if you you can raise your midt score that way as well。

嗯。It's。It sounds a little different， but hopefully it's a good chance where if you like writing code and SNAP versus on paper you get to fully test to make sure your function is correct and of course things like partial credit and whatnot are available so if you don't get things fully correct but know you're making progress we'll give you points for that but yeah we'll have a sign up form for anyone who's not attending a regular lab section probably early next week on that and then we'll also make sure that study resources review sessions and so on having the info about that question。

But the final I assume's during。Oh sorry there will still be a final exam during the designated final time it'll just be it'll be the paper final which will feel like the midterm we will give you the full three hours but it will not be a three hour long exam it'll be probably closer you know to the midterm length。

Exam， but you'll have the full three hours to do it as well and if anyone has time accommodations。

 you know you'll have the full time that we give everyone else by whatever your DSP accommodations allow yeah the question。

哪。Yeah， it won't for there'll be a couple additional lectures on stamp。

 but it won't be at this point。You'll have learned the things in SAP that you'll need to do the final。

So if you want to just go back， review labs， go through previous homework assignments。

 that kind of stuff， the thing I'll say and we'll bring this back up again but。

we don't cover everything that's in SNAP you know in CS10 the final， of course。

 we'll only assess you and stuff that we've covered in class。

 but you there are blocks in SNap that I think are useful。

 that we don't necessarily explicitly teach if you find one of those useful in your solution you that's built into SNAP you can use it as well。

 so if you want to take some time to just study up on additional things and SNAP certainly not a bad use of your time。

 but if you look through the past exams the questions are typically you know write a block that takes in some number and or maybe one or two numbers。

And you know， compute some value in some secret， so it'll be like a for loop。Maybe some lists。

 maybe some recursion you know there could be parts of the question where say solve this using recursion and then there could be parts that say solve this using a higher function。

 but there are also potentially some parts that just say like。

Yeah solve this however you choose and in that case you know we'll we'll make sure that the rubrics sort of accordingly work for。

You know how are the questions set up， but yeah there'll be lots of the in that final there's lots of opportunities to get points because you can sort of see your code。

 you can test it， you can work with it， you know you get to sort of have a sense of how your function is going。

Yeah， other questions on enough yeah。嗯So。Yeah，It's the combined the clever policy is the combined score the two of the two parts and I'll say that usually obviously everyone's different。

 but in most semesters the average score of the in labB final is higher than the score of the paper final mostly because you have a bit more time to work on sort of one question not it's not meant to be the two hour experience we just give you all that time。

Yeah， good questions。Okay。Ba， no。嗯Okayた back。Cool， other questions on the exam。Nothing else。个色。

What I wanted to do today is wrap up a couple things about classes in Python and some additional Python syntax。

At the end of today。You know， while you're probably by no means Python experts。

 you'll have seen the vast majority of sort of standard Python syntax that we could use and。

You know thatll sort of tie up we'll finish up object programming and then tie up some things that that snap pads that we haven't covered in python yet so on Monday we left our time class。

With talking sort of briefly about class attributes。

And I went ahead and fixed them all and gave this one slightly different aim。

 which is probably a little bit more representative is。

You know in this case we want to track some value across our time class like the start of the day this could be sort of like the earliest time that you schedule from meetings or something like this。

 this I set to hour 10 if you're going to be a CS student。

 maybe you'd set it to like 12 or 13 which should be that early afternoon。

 but it's natural to write something like this， where we access some value。

that we want to be shared across all instances our class。

 and if we stick to doing this very seldomly， it can be useful and what this means is that the class time has a value。

That we can set and access and read an update like any other attribute。

But what it also means potentially。Is that Python lets us access the class attributes through an individual instance and this is one of those cases where it's just something to be aware of that if I say。

Time with a capital T start of day and T1 start of day Python says I'm going to try and be nice and I'm going to like you didn't define some attribute in this in an in it method here it's hidden you didn't define you know some other value but Python will try and look it up on the class and。

This is one of those cases where Python does something which is meant to be helpful and in some cases you it is helpful but it's really confusing because you're now accessing some value that doesn't necessarily so to speak belong to this instance so what we generally say is with class attributes things that are not in function attributes that belong to this class time not to a particular time these are things that we should really just in general avoid using as much as possible in particular we should never sort of set key1 in this example that start of day equal to some different value because what Python does there is it actually creates an instance variable with the same name as the class variable which as technically valid Python you could access two different values with the same name in this case。

 but it's just a horribly confusing situation to actually reason about when you're writing code or looking at a class。

And in particular， if I say t1 start of day in this example or equal to 12。

That wouldn't change anything about the value in the time class。

 so that value would no longer be shared across instances at our time in an example like this where it's just sort of a very simple class that tracks hours。

 minutes and seconds。You know it's hard to see where things might go wrong。

 but if you're using this class attribute for example。

 to track something like the starting account number at and some you know bank model you know that you could you could run into a situation where this leads to really confusing bugs so in general what we say with class attributes is。

You don't want to use them so instance attributes are what you should be using these are properties that belong to each instance so that would be each time that we create。

Were each whatever that we create so these are t1 to hour when we write it from outside the class with inside the class that's saying something like self。

 hourour。And。Class attributes are these things that are possible。

 but you generally want to avoid using them， so saying time start of day for example。

 is not something that we want to use。And so both of those things are valid within a class。

 I guess for Zoom， sorry about the transcript。KeepThat really quick。诶。

Yeah both come on both those pieces of code are valid。

 but you should use them very sparingly and very rarely and and in and in particular。You know。

 what I'd say is you should never use an instance attribute in a class attribute that have the exact same name。

 Python won't stop you from doing this， but if you find code you'll find that it's generally pretty confusing and for the your final project for this homework assignment right now。

 there's no need to you know use attributes that are the same。

 one of the examples in the homework assignment might use class attributes but not in a way that should be hopefully terribly confusing。

And so lab sort of this week and last week has some examples of。

Of how to use them in some cases where it is potentially reasonable to use class attributes。So。

The final just example for object Tri code that it just worth mentioning because it'll probably come up if you continue learning Python。

Not something that we're going to demo too much， but is。So far。

 every method that we've written our time class deals with a particular instance of a time object that I have something like T1 that represents the hour 17 and I want to turn it into a string I want to convert it to a number and seconds。

 oftentimes when we're writing code。We also want to address。呃，对。呃。

The potential of having some method that。Works on not just a current instance of time。

 but just convert something related to time into some other the value so in this case。

I might say we want a new method that that gave the total number of seconds in end days。

 so this would be not a current time but just any particular time object and in this case。If I。

Go over to the terminal。

![](img/dbf9290753328bd808fdde359f2de077_5.png)

And。It's actually。If I witness this。I should have our timepi file。



![](img/dbf9290753328bd808fdde359f2de077_7.png)

And's up up here。

![](img/dbf9290753328bd808fdde359f2de077_9.png)

So。😊，So what we're going to do is add。A method。That。



![](img/dbf9290753328bd808fdde359f2de077_11.png)

givess us。The total number of seconds。In in end day so however large N is will will give us a total number of seconds this 86400 perhaps we might actually write as 24 hours。

Times 60 minutes in an hour times 60 seconds in a minute is the way that we get 8400 in general。

 I would probably avoid writing not 8400 that was 86，400。

 I would probably avoid writing large numbers in your code without giving them some name because in this context we can probably figure out what this value represents。

 but in practice like memorizing that some random value in 80。

000 happens to be the number of seconds and 24 hours。



![](img/dbf9290753328bd808fdde359f2de077_13.png)

It's something that you'd probably forget over time。



![](img/dbf9290753328bd808fdde359f2de077_15.png)

So in this case， what we're going to do， I'm going to save this file。

And I'm actually just going to open。The terminal here。嗯呢。Andvis Studio code。I'll burnn it one a sec。

O。Yeah， go ahead。It's oh sorry， yes， what is， let's see。Yes second。啊， ok。So。😊。

That makes way more sense， but why was this option already selected and the lights not being reflected？

嗯。Is that better cool thank you， yeah， sorry about that。Look。

 you find software bugs everywhere in life。All right cool so let me let me try this again so in our file what I've just taken the first method that's on the lecture slides time and seconds or excuse me seconds and end days not time and seconds it's above the time and seconds method。

And this just converts a number of days to the number of seconds that are in。

That many days so inside our file when I run this。It is type Python 3， if you add Python 3 hyphen I。

 I think I mentioned this a couple weeks ago， but it runs your file and then opens the Python interpreter so you could use all the methods in that file。

Yeah。This method takes in a number of days and just converts it to the number of seconds that are in many days a lot of times when you're dealing with something like code and an object like dates and times。



![](img/dbf9290753328bd808fdde359f2de077_17.png)

You're going to want to convert between various things and so this method is actually pretty useful it's logical that it belongs inside our class time in many respects because it is a function that represents some conversion of some number to something related to time but from an object ored perspective we have a little bit of a problem and that this thing doesn't actually deal with some instance of a time right。

We cannot。嗯。We can't necessarily use an instance of a time object inside whoops in our class。

 so if I try and run this right now just to demonstrate what would happened。



![](img/dbf9290753328bd808fdde359f2de077_19.png)

If I say。T1。Let me actually drag this up。If I say t1 dot seconds and end days with no argument。

 Python thinks this is some instance method that can be called。

And so we get this fine error that says like I don't know how to multiply n times this value。

 and that's because this is not supposed to be an instance method。

Python has this tool what I call static method and all this does in Python is this little a thing is called a decorator It gives python some。

Just some directions essentially that says this method belongs to the time class。

 but it does not operate on any particular instance of a time so what I'm going to do is'm to exit out of this to reload the file and now when I call when I decorate something that static method it works the same way but if I try and call this method as an instance method I get a slightly different error that says this thing takes in an argument and if I write it this way。

I can now correctly pass in the value3。And things work correctly， so the static method sort of。

Word and python just means that this method works on things that are not necessarily a particular instance of our class it's a way of having related functionality。

😡，But something that doesn't operate on on a particular time object and I would suggest that like writing like if you have a static method calling it using t1 do seconds and end days。

This is versus saying time seconds and end days， this is definitely more clear。

I think of what the method is doing， but either work and depending on if you' were to take a job or an internship or something。

 each codeb might have might have its own standards for how you handle these things。

 but that's that's a little bit of an aside about just something that you'll see in Python it is a useful tool in particular tools like this are really nice because when you learn all of object or programming or just as you learn more of it will come to sort of recognize that。



![](img/dbf9290753328bd808fdde359f2de077_21.png)

![](img/dbf9290753328bd808fdde359f2de077_22.png)

When looking at a piece of code， having some other programmer tell you the reader of the code later on how this thing is supposed to work is a really helpful bit of information because it tells you like。

 hey， this method， this n is not some confusingly named version of self。

 this end is actually a different n。That represents some number of days or something like that。

So that's on the last sort of example on before you sort of wrap things up any questions on this or another example of opportunity programming。

Yeah， good。だた全部。Yeah， so so the static method the question for those things is just to clarify how it works so what what saying at static method does is it tells Python that。

When I have a method that belongs to my class time that this N。

Is not something that represents the value self it's not a particular instance of a class and so what that means is when I call this method。

Instead of。So like normally let's actually do something like this。

 I'm not to even going to print the value， but if I say t1。Dot time。

In seconds so normally when I call an instance method right in Python Python takes t1 do time and seconds it makes sure that that first argument of the time and seconds function that word itself is my instance of t1 when I say that something is a static method Python says I'm not going to pass my particular instance into that function as an argument and that's really what。

What Python is doing？And so those are just， this is just a way of telling Python that I'm going to call this method in a slightly different style is essentially a way of thinking about that。

Yeah， good question other questions on anything grouply。



![](img/dbf9290753328bd808fdde359f2de077_24.png)

So static methods are useful， they're a useful thing to be aware of。

 they're not something necessarily that you need for the homework assignment。

But they might come up oh that's fine， good job。As we wrap up opportunity training programming。

It's worth thinking about sort of how we would design and write classes and really object orative programming is a tool。

For。For managing complexity and one of these things is do we handle or do we allow our objects to be mutable。

 meaning that we can modify them or do we allow them to be immutable。

 meaning that every time we want to change an object we return a new instance of that object and can probably guess based on previous lectures where this is going so。

In Python， we don't necessarily have super obvious distinctions for this。

 but we can write or we could design our class in two ways， we could say T round ten nearest hour。

 assume that this is a function that picks whether the minutes are above or below 30 returns the closest hour of the day。

We can write this in imutable way which actually resets our current values of T。

 or we can write this。in a way in which T round teners hour returns a copy of the time。

That is rounded to the nearest hour and by doing this this would be an immutable function and in general what wed suggest in the same way that we suggested with the 2048 assignment with lists and snap with other things is that designing a world in which your functions are immutable in which they're peer functions。

Is always a useful thing for managing the complexity of code。



![](img/dbf9290753328bd808fdde359f2de077_26.png)

We could sort of think about this， what does an immutable function？Look like this is our lesson code。

So let's just right it up here， we could say deaf。Round。2。And near a second， that's interesting。

round to nearest hour。We could say if oh nice self administrator an hour than 30 so I have I have visual studio codes autocomp turned on and this is kind of an interesting thing。

And that it is suggesting how I might autocomplete this code。

 this is a pretty good example of mutating something in line because i'm taking selfdot hour and I'm incrementing one to it but I would actually want to do is if selfdot minute is greater than 30 what I would return is a new time object and here the autocomplete when I tell it to return is actually pretty cool it figures out exactly what I wanted。

Yeah， artificial intelligence is both impressive and very stupid at times。

 but in this case it's working pretty well。So if my minute is greater than 30。

 what I want is a new time instance rounded up to the next hour so that if I ask for a time that is let's say 2 35 pm it would give me 3 pm or 1500 if I am within 30 minutes returning a new instance would be returning a new time instance with the same hour of the day but zero minutes in zero seconds so this would be one version of。

呃。Let's see， let's without a comment here。Imutable。Aund。哎 time。

And this this method is immutable because it no longer modifies anything about our current object instead by using the word return calling it the time class returns a new instance of time so this is generally how I would think about and recommend writing and manipulating objects is to where possible and sort of where it makes sense is to return new versions of those objects。



![](img/dbf9290753328bd808fdde359f2de077_28.png)

So one thing you to ask about mutability and immutability is you know in Python there's a lot of methods on classes that are mutable and they're useful and you know some to be aware of you've seen the append method and a couple examples in lab where we say list got aend of some value and that modifies the list in place and in SAP we have mutable methods to write we have the add item to list block and so on and。

The main reason that these things exist is because if a list is a lot of data returning a new copy of that list is a lot of work。

 returning a new copy of a time object that knows about its hours。

 minutes and seconds is not really that long short gray it's just three values in this case a couple of them are zero。

It's a really easy thing to return a copy of a large list is not so easy to return a copy of and so mutability。

 the reason we talk about it and you know show examples of it is it absolutely has its place。

 especially when working with large data sets， but。But if you can avoid it。

 it is certainly nice nice to avoid it any any sort of questions about this。This example here。

CoolSo the main thing that we would sort of wrap up object joining programming is thinking about objects as things that we create that have attributes。

 these are properties of data that they manage and they have functions which get called methods。

Oh yeah， cool， so question in zoom chat before I continue do the difference between mutable and immutable functions。

When we say that a function is mutable， what we're really talking about is a function that modifies the object that that its's calling so if I say。



![](img/dbf9290753328bd808fdde359f2de077_30.png)

What did visual code do？嗯。So。Not bad。In terminal， if I say something like data it's equal to。

 let's just make a list one， two， three。Data。Dot a pen of four。

This append method is mutable because it modifies。😡，Our list of data。

 so I say data out and4 that adds an item to the data object it's changed it you I don't get a new object in return。

Methods that are immutable。😡，呃。Will do things like return a new list so or return a different copy。

 so I don't know， let's see I think。I think it's hard to see this。But because the data。

 what the copy method does is actually just return a new copy。

 so you have to trust me that these two lists are actually different lists in Python。

 but the lists objects and Python， they have some immutable methods like data copy and what this does is returns an entirely new copy of the data that's separate。

 that if you modify one you don't modify the other。嗯。

And so that's really the difference between mutable and immutable functions。

 that immutable function is going to always return a new instance of an object that。

That won't be modified or that won't modify our original object。



![](img/dbf9290753328bd808fdde359f2de077_32.png)

So yeah， if you need more clarification， but let me know。嗯。But yeah in general。

 what we've done here is we've made a time object， we've given some tasks。

 some tasks to that time object that modify or that manipulates to me。

 the time object that convert values and so on， we saw a bunch of different built in methods to Python。

You know， sort of most interestingly， things like less than and stir and in it that give some special behavior and in every programming language。

There's going to be a set of tools。That we that we want to learn and use to make something feel。

A little bit more built in if you read the news at all or you follow you know sort of tech news you might have heard this term application programming interface or APIs you know this week Apple sort of announced that they're going to have their developers conference in June and you know they're expected to announce a bunch of new APIs and all this really means is these things are the interfaces for how as a programmer you interact with different pieces of software different pieces of code so what you're doing when you're building a class like this is you're building your own interface to manipulating with time or you're building an interface to manipulate with any other kind of data and。

There's often not a single right answer here， but you get to decide as the programmer then what the set of functions are。

 how should they work， how should they sort of look and feel。

 and Oop is really just a sort of philosophy and a design pattern for how we build those interfaces and how we structure that data。

 we could have written all of this code using just functions， no sort of set of object data。

The tools that OP gives us do lend to some really nice ways of thinking about。

 and am I trying to manage the complexity of my code in a useful way and so that's the goal there。

For the last。15 minutes I want to show two different things in Python now so sort of completely separate from Boop taking taking sort of a step back。

 but two things that are really useful in python that。

Sort of exist in snaps sort of don't well the first one sort of doesn't but that that are useful useful things to be aware of and will help you write and read Python code that I think is a lot more clear and this first one is called default arguments。

And keyword arguments。呃。In in Python， this is just a little trick as we can say some string times three so if we say move times three we get move back。

 so we might want to write some function that prints out some kind of structured data。

 this just makes a nice little triangle of asterisks because we say multiply some symbol times some number of steps。

嗯。😊，And。A function like this， if you're thinking about by the way a final project and you want to make some sort of low flag graphics that exist in the terminal functions like this are actually really fun。

 you can be really incredibly creative with just text graphics which is something you know if you're thinking about going that way for your final project and you want to do Python and you want to do something in the terminal I highly recommend playing with text graphics because it's way easier to think about that than in some of the other libraries and things that exist and you could still be pretty creative so this function triangle takes in three arguments。

 it takes in the number which is the longest line here。

So if I say something like six it's eventually going to print sorry not the number of lines is on the number of lines it's eventually going to print six lines in this case。

 oh yeah， so if you're stopping by one it'll print six lines the number of dots to add at each line。

And the symbol that we're going to use in this case this is a triangle of stars。

 we could call this in a bunch of different ways so if I want a yeah it is the of long sign。

I was confusing myself for a second， it's our triangle with six hashes stepping by two gives us three lines。

 so would be one way of writing this。You could choose to write this function in any sort of different number of ways。

 or I could you know choose to make another function of asterisks triangle stopping by three this is just some example just randomly printing out data but in each of these cases we have these numbers we have six one and star we have six two and the hash we have 10 three in a star。

With three arguments with the function definition right here。

 you can probably figure out which is which， but what Python allows us to do。😡。

As in our function definition is say de triangle， some value n。

 and then we could say step is equal to one， symbol is equal to star。

And these are what we call default parameters and default parameters tell us if I don't give a function some parameter。

 so when I call this triangle function， if I don't give items two or three。

 Python will try and fill in those parameters with the defaults supplied in the function。

 so I can now just say triangle of five and what this is is a value。

Of five asterisks with a step size of one using the asterisk as a symbol and this is another way of defining functions that are a little bit easier to you so if you see code where in the function definition we sort of see some that looks like a is equal to B that B becomes the default value if we do not supply that parameter so if I say triangle7 and two it gives me n of7 a step size at two and the symbol is just filled in so essentially this makes what we sometimes call optional arguments it makes the symbol and the step values optional for for this function and that just helps you as someone reading code manage。

Some of that complexity a little bit more a little bit more easily the challenge though is that even this function72 and hash is still a little bit opaque so what we can do is in Python when we call a function。

We can use what are called keyword arguments or named arguments where。

Each of these arguments we pass in so we say triangle we could we can reorder them now we could say symbol is equal to an explanationlamation mark step is equal to two n is equal to seven and we don't have to use default values we could just use one of the other we use both but what keyword arguments allow us to do is really specify and be very clear what each argument into our function what that represents what does the。

The exclamation mark represent well that's the symbol that's going to be printed what does two versuss seven represent both those are numbers so it's pretty helpful to know that one of those things is the step size one of those things is the value n it would probably be good to name this something other than n like length or lines or something like that I guess length would be more accurate the way that this is ring but。

Keyword arguments make it a lot more clear about how a function is being used in snap I'll just pull up。

Snap really quick。呃。

![](img/dbf9290753328bd808fdde359f2de077_34.png)

In Sap we don't necessarily have keyword arguments。

 but we kind of don't need them because in SNap we don't have to have our arguments all at the end of a function right it's perfectly acceptable to say move input size steps。

Go to X input y input and so our arguments and our blocks are already labeled for us and if you're making blocks in snapap it's nice if you put the arguments inside your block in a way that's sort of logical and readable that in snap a lot of our arguments you glide number of seconds。

To to some position it's not explicitly a keyword， but it's stuck in the middle and so's it's a little bit more clear how that function is being used and so personally I think that。

This way of writing functions is one of the biggest advantages in S and you get pretty darn close to that by being able to use something like keyword arguments in Python S also oops matter if I do that。

 but if I make a block。If I call this thing my block， if I， whatever， doesn't matter matter， guess。

 it takes in some value n。In Snap right here you can actually specify a default value when you make a block so Sap has sort of the same exact functionality make a block I specify default value of n is equal to 100 Sap actually will show me that in the block spec in the same way so it kind of says n is equal to 100 if I apply this。

And I scroll all the way down here。What I get is a block which has a default argument so both these things exist in similar in different ways in Python and snapap there's no keyword arguments specifically in snapap but I would argue you don't really need them so actually we're not going to do this one today just in the interest of time。



![](img/dbf9290753328bd808fdde359f2de077_36.png)

what I will show for the last few minutes is we'll go through this a little bit quickly is。

We showed an example earlier of sorting a list of time examples。

Using usinging a list of times and the sorted method automatically called the less than function on our time instance now it turns out the sorted method is pretty cool in that we can sort any kind of data by just about any kind of of ordering if I give it text it sorts things in sort of a pseudoalbetical order so it puts the A's before the B's and so on。

But it also turns out that this sortded method is a really useful hybrid function。

Wwhich accepts this argument called the key and here key is the way that sort of is implemented is it's an optional argument where you don't have to pass it anything but we can pass in a function so sorted is a higher order function that accepts an argument called key so we could sort something by the last letter instead of the first letter that would be one way of comparing data to each other。

But。And we're going to actually skip this example for right now。

But what sometimes we want to do is we want to use something like a function that exists in line in sort of in a short manner。

 and so sometimes in Python you might want to do something like right。

Yeah a really quick one line function and we're going to revisit this a little bit more in a future lecture。

 but what Python has that is really analogous to what snapAP has is this keyword called Lambda。

And Lambda is just a short way of writing an in length function。

 so you don't use the keyword de and you don't use the word return。And so。

the final sort of piece of syntax and Python that is really important for CS10 or just Python in general is understanding how this bit lambmbda turns into into a function so in snap if I。



![](img/dbf9290753328bd808fdde359f2de077_38.png)

![](img/dbf9290753328bd808fdde359f2de077_39.png)

Go back over here。Just close that out。In Snap， a lambmbda is essentially the same exact thing as a gray ring that if I say。

Wherever you would use a lambmbda in Sn is somewhat or excuse a lambda in Python is somewhere where you might。

嗯。Where you might use a function that has a green so we don't have inside there's a library and snap that actually lets you sort data。

 but in python。

![](img/dbf9290753328bd808fdde359f2de077_41.png)

the sorted functions was built in this lambda X count of z is if I go backwards is the exact same function called count this way so it is we only have a minute off so i'm going to leave it here for today and just sort of introduce this syntax we'll do a couple more examples Monday will be social implications so maybe next Wednesday but。

Basically the last bit that what is useful to understand of Python is just Python has this tool which lets us write functions in line in a really short manner。

 we don't have to use depth， we don't use return and what it gives us are what we call sort of anonymous functions functions that don't have a name so we assign them to a variable and we use them potentially like any other function。

 we can pass them in to things like sorted that take in this key。

 we can pass them into the map and filter functions that we showed you earlier。

 lambmbdas are sort of the final bit of Python syntax that is useful to know。

We're not going to do this right now， this is on the self check this is I think the trickiest example that you'll see in CS10 with lambmbdas it looks tricky but what I would recommend doing is following the Python tutor link in the slides but all you're really doing is calling and passing functions around so we'll revisit this in a week or so but in the meantime if you go through look at the Python tutor link that'll be there so sorry' out of time but thanks everyone and we will see you all in lecture on Monday。



![](img/dbf9290753328bd808fdde359f2de077_43.png)

Okay。Okay。

![](img/dbf9290753328bd808fdde359f2de077_45.png)