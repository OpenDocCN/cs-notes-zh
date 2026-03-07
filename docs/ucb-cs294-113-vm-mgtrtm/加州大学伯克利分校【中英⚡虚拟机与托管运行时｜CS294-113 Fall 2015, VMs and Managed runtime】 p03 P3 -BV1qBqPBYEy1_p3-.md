# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p03 P3 -BV1qBqPBYEy1_p3-

Okay， I thought we'd just start this week with a little bit of review of the assignments you've done so far。

呃。Okay。So this is assignment1 is just the。Were' program Fi。 So we'll start talking about that soon。

 But for people who've done the second assignment， can I get a show of hands for about how many hours you've spent on it？

So like over 10 hours。Like total， you total 10 hours。ok。All right， and less than。Less than three。H。😊。

Okay， alright， good。 Alright， so we're shooting。 that's。

 that's good 'cause that's what we're kind of shooting for。😊，U。😀Yeah。Okay。

So this is just a quick review。 The first sign wasn't very hard。

 so we can just go over the questions。So the first one was talking about。

That weird part of F where null means false and returns 0 for true。 So like I said。

 that was kind of weird。 So that's the current semantics。 So one's less than 3。

 that returns 0 and one's bigger than 3， that returns null， right？ And I ask you， well。

 how else can this be designed。So a lot of you guys， you've covered every the whole spectrum。

 basically。And here are the big ones that stand out。

So this one is like many other languages where there's this special object called true。

 So one less three returns true and ones bigger than three returns nu。Okay。

 and this one's a perfectly fine design is actually the one that I prefer。😊，Because。

That's quite clear。And also， and the only trade off is that you have this extra data type， right。

 which is just a few extra lines of code to your interpreter。 It's not a big deal。

Here's another design choice。 We can actually interpret numerical values as bulls themselves。

 So this is coming from maybe you're more familiar with C。So like one， less than three。

 this will return some non zero value。And once bigger3， this will return zero。Okay。

So from the perspective of a C program， this makes a lot of sense。 And as far as pho goes。

 this is also fine， however。What I don't quite like about the solution？Is that。

When we start extending Fi with other data types， like say floating point， right？

 So we know that integer 0 is false。But would 0。0， would that also be false。Okay。

 so there's N like when we extend it with strings， would the empty string also be false or would the MT array also be false？

And some languages did decide to go down this route。 So there's many， many things that can be false。

 And I think in retrospect， people have。Seeing that as a bad design choice。 Okay。

 so that's why I don't quite like this solution， but it is a common solution that is used。Here is。

A very elegant solution， but maybe with some performance trade offs。 So this is where。Right。

 so our current axis is， is one bigger than three。 where we return null for that， right。

 and is one less than 3。 Well， we just need some non null value， right。

 The actual value is kind of meaningless。 We just need something that's not null。 So we turn 0。Here。

 we actually， we just make the value that we return a little more meaningful。 So one， lesson than 3。

 if it's actually true， it returns the。Lesser of the two numbers。

 So it's kind of like a min function almost， right。 So in this way。

The value that gets returned has some meaning which you can use to play some tricks on， so。

The possible performance trade off is that。Often， you're just doing a predcate test anyway。

 you don't actually care about the value that gets returned。 So why bother calculating it。

 So you now you need to go through this extra step of analysis to throw away the result that you computed。

 right Okay， so that's about the space of there's one other case。No is false and nonnos。Right。

 so that's that's what we have no， but no， buti at zero is true。Oh， right。 Okay。

 So the way the if statement works is always like， as you said， noll is false。 No， no is true。But。

But even if you take that， the A statement does work that way。

 but you still need to decide what this should return。Right， so I mean。

 you can pick an arbitrary value for the predicate。

 but like invent your own predicate that returns something that's more useful for it right。

 so thats that's kind of this this solution。Kind of yeah right or I guess there's just there's two things here that we're talking about。

One is what is the if statement， how does the if statement interpret what it's given and the other is predicates。

 these are just arbitrary predicates so if we just treat them like they are anyways。

 which is just functions then all you have to do is define。

You can define what that specific one returns right。Exactly， right。

 But the two questions aren't coupled， right， because if you take this design choice。

Then your if statement will have to accommodate that yeah。Okay。First question。

 here's the second question。 I asked you to read through the implementation of complex numbers。

 and I asked you specifically， what does this function do and how might it be done in other languages so。

It is a function that creates a。Complex object， right， So essentially。

 it's acting like a constructor。And in other languages， this would be called a constructor。嗯。

Fenney doesn't have constructors for very explicit purpose。 Constructors are kind of weird。 Okay。

 so I'll go over why later。 But that's the main thing。 So this is taking the place of a constructor。

 even though Fii itself has no concept of constructors。Okay。Okay， I asked you。

 what possible advantage does the implementation complex numbers have over a Java implementation？

The only one I can see really is operator overloading。

So because we have some syntactic sugar for expanding this into this。

You can use your complex numbers as if they were part of the language， okay。So。Justs nice。

The next question was about inheritance， specifically。

 what is it Da Fii can do with its inheritance model that。Other statically type languages cannot。

So not everybody got this one， but mainly I was looking for something about。

There's there's a distinct difference between prototype based object systems and class based object systems。

 Okay， so here's an example that you can really only do with a prototype based object system。

So here's a function called make barkable and you get an object。

And all it does is it returns a new object that has all the same properties as the original object。

 but now can alsowoof。Okay。So you can call this thing on anything。

 You can give it like a complex number。 Complex numbers can't wh。

But you can pass it to make marketable。Right and get this new thing and now this thing I with。Right。

 but it can also support all the original functions that complex numbers do。Right。So。

 this is something that。Prototype aisms are known for and is the selling point that they always talk about it。

All right。The next question was Java has a big section in its spec about default values。 Fi doesn't。

 Why doesn't it， And most of you said that it doesn't need one。

Because it's actually impossible to refer to a uninitialized variable。 right？

 So when you create objects， you have to give it initializing expressions for every single slot。

 When you create variables， you have to give initializing expression。

So really there's no way to refer to unlitalized variable so you don't need to worry about defining what happens if you do。

This is almost true。 Does anyone know one case where you might refer to a variable that's not initialized。

We have an expression， which is a Y loop。That's， that's an example of a variable that's not initialized。

 but you can't。 you don't read from it either because because the wild number executes。Or something。

E will do and you can have involve a wide expression。嗯。okay， alright， so。

 so the one case I can think of is for global， the global scope is。Different， right。

 So the global scope， you can declare a。You can declare a variable。

Ahead of when you're going to use it。So if you try to read from it before you actually get to the line that declares it。

 then you're reading from something that doesn't exist yet。So in this back。

 I said this is just semantically defineders。You're reading from a variable that doesn't exist。

And there should be an error。Okay。嗯。But an alternate way to define it is if you read from a variable that doesn't exist yet。

 it returns some default value。And this has nice performance properties because you don't need to do this extra check。

 is this variable initializes the variable not initialized。Yep。

It be a better solution to ra initialize it。成析い。言っていい。You can lazily initialize it。

 but if you think about it from an interpreter's point of view， every time you read this variable。

 there will be this flag， has't been initialized yet。Right。

Instead of just this straight load from memory。Okay。

 and then the biggest question was the difference between closures and objects。So like I said。

 for Fi， I wanted you guys to implement objects now closures。

 but I made this point that they're basically the same thing。

So here's an example with some made up syntax of what a closure looks like， right， So here's。

A function， F。And it takes an argument X and what it returns， it returns a new function。Okay。

 so this function has no name yet， it returns a new function that adds its argument to x。So， we can。

Call F， assign that to a variable G。And then called you with 11。Okay。So this should return。

 let's see x is 10。So x is closed over。 That's why it's called a closure。 So 10 plus 11 is 21。 Okay。

 so that's what this code should return。ベストスネクス。This does not exist in the pho。

 so this is some made up syntax。So if you had， if you were putting a language with closures into Fi。

How would you do it？ And most people said something like this。Whenever you create a closure。

 you create an object instead。You copy in。All the closed over variables that it needs， right。

 And then you have a single method called call or apply or something like that。And you just go。

 you read out。The variable that's closed over is nott x plus I。Right。

And then you can call it by explicitly saying G。 co。rightSo your modeling closures as objects。

So this is a perfectly good solution。This is quite a robust solution， actually。

 so we can extend the solution a bit。Here I create two functions， right？So GNH are global variables。

We're going assign G to something that adds its argument。

 We'm going to assign H to something that subtracts this argument。So this is a closure code。

And the object code will be very similar。G will be an object。 You copy in。You copy in X。

That's what you close over and call as I。H， you copy and X。 also， when you call。It you subtract I。

 right？ So really， it's just the syntactical difference， yeah。So on the left， though you can't refer。

That's true， right， So this is actually。Less restrictive than the pure closure sense， right。Exactly。

It's yeah。 so the behavior given by this code will be more rich than what you need， right。

 which means you can always port code over to this。

But it won't give you the same restrictions that it used to have。Yeah， that's a good point。Okay。

All right， so this is。An incomplete solution， actually。

 So there's one other half to the closure problem。Let's say。The closure code actually mutates X。Okay。

 so first， it mutates x。 X is equal to x plus I， and then it returns the new value of x。Okay。

 same for H。Okay，So this is typical actually JavaScript code and people do this all the time using closures。

So now we try to translate this into Fi。And the straightforward approach is。You just set x， right。

 this dot x is equal to this dot x plus I and return the new value of this dot x。Okay。

Can anyone point out why this does not work？Give you。I'll give you a minute to stare at this。

In the x。Do different。Yeah， right。 Yeah， these are， these are two different x's， so。And this code。

 right？When you call1， I hear it increments x。And then when you call one on H， it detriments x。

 And now x is back where it used to be。 It's the same x that's closed over。Whereas in this version。

Right， you're gonna copy X into this object。 So now it has a copy of X。

 and then you're gonna copy X into this object。 And now it has a copy of X。

So when you call G doll call this increments is coffee of X。

 I mean do H doll call it increments is coffee of X， right， So you lost this sharing of。Data。Okay。

So for those Java programmers here， how many of you have used anonymous internet classes？Yeah， right。

 Okay。 so a Java makes this restriction where if we refer to a closedover variable。

 it has to be declared final。 Why is that。This is why， right， because this is how they implement it。

Okay。So。So these are just some things that fall out of implementation。

If you actually want to solve this， right， the trick people normally do is。

Whenever you see a variable that's closed over by closure and the variables is mutated。

 you actually put it in a special cell or array。So you can think like。

The first thing that this code does is create a new array with one element and store X inside it。

Okay。And then。Sorry， so it'll go here。 You'll create a new array with one element with X inside it。

 And then instead of copying in X， you actually copy in a reference to the array。

And then you update this array。是色以高。个院过は。U。Yes， you can， sorry。Because currently。

 you are translating global functions directly to the Phoenix global function。

You have defined half on the that。Yes。The right out into and out there also。い災？

I'll translate this into an object as well。A。Yes， that would be fine also。

 So then you instead of saying this out X， you go F thoughtt X。 Yeah， so that would also work。

So this is another implementation technique that people use。

So this is the main reason why I didn't want you guys to implement enclosures。

 It's just this extra analysis phase， but it doesn't actually change your VM at all。Okay。

 so that's it for the first assignment。 You guys are working on the second assignment and do today。

 This is talking about。The third assignment。That's the wrong number。So in the third assignment。

 you're going to implement the bycode interpreter for Fi。Um。

The semantics of the bycode interpreter are specified in this abstract way。Wch。

Should give you the semantics that you need， but it doesn't give you all the concrete details that you need。

 So I'm going to just talk about that here。So the machine state of the Bcode interpreter consists of three things。

So first， you have your。Global variable map， okay？And that's where we're going to store the current value of all the global variables in the program。

 Okay， so it's mapping from names to values。The context。

That you're currently running in will be stored in the local frame。

And the local frame has a few things。First， it has a pointer to the parent frame。Okay。

And it has the return address。That's going to be executed when this function returns。

And then it has a number of slots for holding all the values of the arguments and the local variables in the function。

Okay。And then finally， there's an up stack that you can push and pop values onto。Okay。

So this is the how the semantics of the by contributor is defined in the spec。

But when you actually come down to implement it。What you should do。Is the current local frame。

 You should just allocate a giant array to hold the local frame， okay。

And the local frame appointed to the local frame will just be an index into this array。Okay， so。

The frame pointer will be an integer index into this array。

And this will just be one slot in the array， the return address will be another slot in the array。

 and all the slots following will be more slots in the array。Okay。

So don't actually create a link list of。Sttros。Okay。Here's a few hints。So。

The bycode is not really designed for you to interpret directly。

 It's not gonna be fast enough for you to do that。So。You should go through this analysis phase first。

 sometimes it's called the quickening phase， where you convert the bicode IR into your own internal IR to make it easier for yourself okay。

And here are some of the things you should do。So。Retrieving and setting global variables in the bycode。

 it's by name。But when you load it， you should just give them a numerical index， okay？

So you should turn like。Get global variable X into get global variable 17。Okay。

 and that makes it much easier for you guys。U。Right now， the instructions are all grouped。

Together according to their method， so every method has a bunch of instructions following it。

To make it easier for yourself， you should just allocate one single array and dump all the instructions in there。

And then you just remember which index。Each method starts at okay。

And this will also give you a good way to identify a specific address in the instruction stream。

 So a specific address will just be an index in this instruction array。Alrighty set this。

 allocate your local frames in a array， don't make a big linked list。Okay。And also。

For control flow instructions， there are labels。Based on strings and the controlful instructions jump to a label with some given name。

 Okay， so the biggest part of your pre analysis phase is resolving all of these labels ahead of time。

Okay， so instead of saying。Branch to label。En。Go， like。Branch to instruction address，217。

So these are the biggest parts to do for your pre analysislysis phase。 and the more analysis you do。

The easier the interpreter part of the actual VM is。Which means。

As you start compiling the interpreter portion of the VM into assembly instructions。

 that part also becomes much easier。So do as much as you can during the quickening phase。

I think that's it。Okay， that's it。 al right。Afternoon。Hope you all had a pleasant Labor Day weekend。

And spend too much of。Coding up interpreters。嗯。Lets。Change this。

Where is that bloody mirroring option？😔，Thank you。Okay。佢知道。哎。Where are you looking， Oh， yeah。

 well you know。There's a lot of stuff on this Mac。So we were looking at this last time and we were a good way through it。

 let me。😔，Skiip ahead。Think our last looks at Gettfield and put static。Yeah。😔，So the two。

Or the dissection， as I prefer to think of the VM， will continue。So as we progress today。

 the instructions will start getting a little bit more complex and there'll be one or two topics at the end which are not。

 you know， I can't explain just by pointing at sections of the manual。

And then what we'll do after that is we'll talk a little bit about the reading assignment。

 the Gosling paper， and then we'll move on to dynamic languages and the challenges of dynamic languages and that will hopefully set you up。

For the reading for next week and next week's session， which I'll talk about towards the end。

So we looked at Getfield and static。 so we've still got to look at some array processing stuff。

Some type stuff， Nothing here， particularly。Tricky， it's really just kind of give you the quick look。

And point out some of the strange anachronism。 So here's one。There are。

Typed load operations to load elements from an array。For all of the primitive types。

 but curiously Bi and Boleion are the same instruction。And even in the speck， it says。

 you can implement Boolean arrays as packed arrays of bits。But you don't get a different bikecode。

 You still have to use this bikecode to access them。

 So you're going to have to do basically a type check in the bikecode at some point to figure out whether it's really a boolean or a bike or array。

If you've implemented those two differently。So that's a little bit weird。Character array load is。

Only unusual in that characters are 16 bitts in Java in case if you didn't know that。

 they're not bytes， they're unicode。A couple of type checking instructions。

 instance of and checkcast， which vary only in small details。

 This is the stuff that allows you to dynamically test whether you have an object of a given type and branch depending on that and the check cast instruction says I assert this object is of this type。

Please assume it's of this type from now on and throw an exception if it isn't。

 So the real real differences are only in the。The treatments of。Noll in the failure case。

 So otherwise， the fairly straightforward instance of just takes the object reference and gives you a result back。

Whereas check has， do I have a slide， Yes， checkcast takes the object reference and gives you back now in its new type dressing。

 but throws an exception。If it can't be converted to that。

 that so another just the little pi part of where the type system surfaces again。Stack management。

 nothing particularly。😊，Exciting here， the， the。The really。

 the only point I wanted to make here is wow， what a lot of stack management instructions。

 So you you'd expect there to be something to pop things off the stack。

 you'd expect there to be something to duplicate elements and maybe a swap with the six flavours of duplication。

It's like Baskin Robs for button codes。U。So pop， okay， pops the top value from the opera end stack。

 but has this mysterious little statement here， which we'll get back to。

The pop instruction must not be used unless the value is a value of category 1 computational type with a cross reference。

 What's that all about。And if we look at dupe， the simplest du。It's also like that。

 notice there isn't an I du and an A du and an F du and a D du and an L there's just dupe。

But it also has this mysterious little sentence。 So you think it's type agnostic。 But actually。

 this is where the strange stack layout decisions come back。To us。

 because what are these computational types in their categories there's actually only two of them。

1 and2。And broadly speaking， one is 32 Bs and two is 64 Bs。

 but they don't say that because there's this one in the end of category 1。

 which is a return address， which is machine dependent。 So it may be 32 Bs。 It may be 64 Bs。

If you've built your own weird hardware， it might be 43 Bs。 You know， it's whatever the。

 whatever you choose to implement it as。 So this is another place where the。

The decision to choose partitioning， of slots based on size shows through。

 But with this weird exception that this thing of unknown size is arbitrarily dumped in in the 32 B category。

 even though it not really might not be 32 Bs。So it's kind of interesting to go back a couple of versions in the spec because in the original spec。

 it was very explicit。 there are 32 bits lots and 64 bits lots except these row turn addresses。

 which may or may not fit in 32 bits， but that's where you're going to put them。

And then for some reason， they flip the whole spec into values。

 so there are these values on the stack， though that may have sizes and computational types。

 they're both equivalent and just a different presentation of the same same information。

Havingttingway to stuff。Yeah， there's。Go back another one。There's pop  two。

So pop and pop2 are you know pop is pop the type one thing， pop2 is pop the type 2 thing。

 similarly dope and dope 2， and then the extended forms of the dupes allow you to。

 I can't remember now what they do。 I think they give you more more reach。

So you can dope stuff that's further down the stack。There's a swap， but there isn't a swap too。嗯。

Yeah， yeah， it's your problem right， if you met at 64 bets。It if it's a return address on the stack。

 it's a type 1 thing。 and then you have to choose how you're going to deal with that。 if you made it。

 you know what how you're going to represent the stack to accommodate a thing that's not the same size as all the other things。

Okay。And then when you find that section about computational type。

 you also find this table which I think is also a little illuminating。

 so type support in the Java virtual machine instruction set and the various VM types are listed across the top and the various types of bike codes with the T standing for the type are listed down the left and you can see how irregular this is there's kind of lots of there's not an awful lot of consistency or pattern to this。

嗯。Some things can apply to all types。Some things can apply only a couple of types and the choices vary an awful lot by from category by code to category。

 so it's a little bit strange。Where's the I2T？I2 T means integer to some type other than integer。

Okay， so now this， this strange type stuff shows itself with Dukepe 2。

 which originally in the old manuals said pop the two top slots。Dpe。

 the two top laps off for the stack on the assumption that each was 32 Bs。

 unless one of them was a return address， in which case it got complicated。 Now。

 it says dupe the top two values， except it's like， well。1 or two。

 because if one of them is a 64 B value， you just dupe that one。And if they're both 32 bit values。

 you dope them both， and if there's a return address， well those camp for 32 bits as well so。It's。

 you know， it's， they're kind of pushing the dirt to different parts of the rug underneath。

 but the dirt， you can't make it go away。Okay， so type conversion instructions are also provided to convert between all of the obvious。

Sort of primitive types we'll only look at one of them。

 There's nothing particularly exceptional here other than that you can't do pointer to number type conversions。

 as you can indeed， because that's the basis of the security model that you can't just get， you know。

 get an arbitrary number and suddenly access a pointer an object using that number。

So I to L convert into long， just as the obvious thing takes a value。

 which is an in and gives you a result back， which is a long， which is now one of the。64 bit things。

先生？little for a bite or short。So for example， we just say byte x is equal to2。

It's going to happen to do the di。Well， not necessarily because if you look back here， there's。

 I didn't go into them。 but way up at the top left there's B I push and S I push。

 which pushes literals that are shorter。Sizes onto the stack if you're lucky， you'll end up there。

Okay， control transfers。Somebody asked last week about the fact that there were only comparisons on noninteitude types。

 well this is where the integer comparisons come in。

 you have conditional branches on only integers and reference comparisons。

 So if you look here in this list there are some that are if underscore a and those are comparing references。

And obviously， you can only compare references for equality or inequality。

 And the rest are comparing ins for。For some kind of ordering relationship。

And there's two families here， if E Q and its parallel， if IC MP， E Q。

 And we'll'll I'll explain what the difference between those two are are。

 And then we've got a couple of。Bike codes that are used to implement switch statements。

 and then the the。The uglyly family。Where all the hidden secrets and unpleasantness lies。

 that'll take us a while to go through those。😊，We'll start with the go to， which is fairly planned。

 but JSR and Re， I want to talk about a little bit as well。 So we've got two kinds of if。One kind。

 just as a comparison of the thing on the top of the stack against 0。

And so there's a by code that encodes the， the， the sense of the test。

 and then a couple of bytes that tell you where you're going to branch to if the test succeeds nothing particularly。

Surprising there。 And there's all the obvious cases spelled out in detail here。 again。

 nothing particularly surprising。In all of that。So， you know， if the comparison succeeds。

 just construct construct an offset using the two branch bytes and then calculate that has to go to another valid bycode。

 So one of the things stipulated very carefully in this spec is you don you only get to jump to the beginning of a bycode。

 you can't start interpreting the bytes from the middle as some other kind of bycode。

 as you can on real hardware where， you know， can any any instructions。

 any bits can be interpreted as as an instruction sequence。

 So one of the things the verifier here has to do is check that all of the branches branch to a the place that's the beginning of a bycode。

Okay， so the other flavour of if is the one where you're comparing two things on the top of the stack。

 So if underscore is comparing 2 ins on the top of the stack and then doing a branch based on。

 on the result of that。 So that's doing the。The the more general comparison。

So pretty much what you'd expect。 both things have type in。

 They're both pop from the stack and they're compared。 And if the comparison succeeds。

 then you proceed to the。Byite code identified from the。Address and the instruction。

And then you get the flavors for comparing references， again， just equality and inequality。

They'll look pretty much the same as the comparisons。Hem。😔，Table switch and lookup switch。

Are very different。Very different。 You won't find anything like this in any piece of hardware。

 I'm pretty sure。 So the what we're implementing here is implementing a dispatch。

 a switch and the bike codes accommodate two flavors。

 One is where the the cases are are densely packed。 And so what you really want to do is。

Represent the dense packing as a bunch of target addresses in an array and just index into the array。

 And the other one is kind of like an association list， a list of pairs of associations。

 a table switch is the dense packing one。 And you see that there are a jump offset sex listed at the end。

 Let's have a look at the description。So it's a variable length instruction immediately after the table switch。

 there's some padding to get you some kind of alignment， not quite sure why that's there。

 that seems a little odd。And a byte code set。But if you figure out the simple implementation of this。

 you'll understand why they did that。嗯。So then what happens is there's this list of。List of offsets。

 and these bytes represent the maximum and minimum values in effect that you're indexing with。

 And so then you do a calculation using。Low and high to figure out where you're indexing into the table of offsets。

 And that gives you the， the way you do this the dispatch。 And if it's outside of that。

 then you have a default that's lifted listed explicitly here， which is。

 is the sort of the default arm of the case statement。U。Kind of complicated for a byte code。

 And this padding thing。You know， if you think about the straightforward interpreter implementation of it。

 if you're going to do this array look up directly in something like C or machine language。

 then you want the values to be aligned but。That's sort of a strange implementation detail list。

Surfaced at the the level of the bikecode。 So it says something here in the notes。

 the alignment required of the four by opera ands。Guarants 4 by alignment。

 If and only if the method that contains the table switch starts on a 4 B boundaries。

 And there's a little warning for the VM implementer better align your methods because otherwise。

It's going to be bad。And then lock ups， which is sort of the same， except it's a list of pairs。

 which the standard implementation sort of searches down the list of pairs looking for the corresponding match。

 so I wouldn't go into the。The gory detail go to is sort of what you'd expect from a go to。

 but of course you can only go to something out other place within the same method。

 you can't jump into the middle of another method， you can only jump within a method so the offsets here are within the method of the instruction you're executing。

So， nothing too。Unsurprising， we'll get back to JSR rate in a little while。Okay，The heart， really。

 of any V M， as you'll see， as we progress， is really invocation。

 how you call things and how you return。And， and Java has。Currently。

 five different ways of doing that listed in the introduction to this section are all called invoke instructions。

 There used to be only four， but one of them got added a couple of versions ago， invoke dynamic。

So the four have been there since the dawn of time。And well look at those in a little bit of detail。

 Invogue dynamics， sufficiently weird and different。

 I'm going to leave that until we cover dynamic languages。

 sort of advanced topics because it it's a little bit complicated。 And then complementary， of course。

 the calling。 you have to have some way of returning The return stuff is fairly unremarkable。

 and we'll just look at one example。 So let's look at the the four cases。

The first one is is the common case， the one that you normally think of as invocation in Java。

 and that's invoking instance methods on objects。Which the name is invoke virtual。

 taking the cu from virtual methods of C plus plus and in fact。

 even that was derivative of the original implementation in similar。

 a long long forgotten language by most most people。So at the top is the sort of the， the。

Aretypical code that you'd be writing in Java。 You have a class that you're declaring with an M。

 a method M that you're either declaring right there or you're inheriting， and you invoke a method。

 And that will translate to one of these bikecodes and invoke virtual。

 So that invokes an instance method。 and the dispatch is based on the class。

 So it's a dynamic lookup based on the actual object that you have in your hand at the time。

 So on the stack， you push the object。That's the target of the dispatch and then however many arguments the method takes。

And then。5 pages of text。Describes what happens after that argumentsguments are， you know。

 transferred method frame， new methods are located based on the type of the the object。 you know。

 a new stack frame has to be created。 It's， it's really long。

 And I'm certainly not going to go through all of the detail of that。

 It's pretty much what you'd imagine though there's nothing terribly。Surprising there。

 what I did want to talk about， however， was the。The basic lookup technique。

For finding virtual methods， because this is very common and it's used in many， many systems。

 not just in virtual machines， but also。In non VM compiled based systems for。

For object oriented languages。 So it's worth knowing a little bit about this。

 And then we'll compare it in the dynamic language section with what you have to do for dynamic languages。

 So， so let's do a little detour through this to begin with。

 So let's assume we have statically typed language with single inheritance。And you know， here's。

 again， a little bit of Java， framework that gives you some idea of what's going on。

 So I've declared two classes A and B， B is a subclass of A。 I've declared a couple of methods in A。

 F and G， G calls F。And then in B， I've overriden an F and I've added a new method H。

So which means that I'm inheriting， I'm inheriting G。

 So we've got F G and H defined on instances of B and just F and G defined on instances of A。

So how does that？Oh， the other thing worth mentioning is you。

 you can't remove stuff as you go down in here it It purely additive。

 And that's important for this implementation technique。So how does that typically represented。

 He is a， here is a sketch of how it's done。 So here on the left， I've got the instance objects。

Which are typically laid out in contiguous memory。They have some head of stuff。Which is VM specific。

 And typically in in the head or somewhere， there is a field that references a structure that represents the class of that object。

These are not the same necessarily as the values you get when you do a dot class or or a reflection。

 Usually those are things that front these objects。

 So these things usually are not directly visible to the programmer sort of implicitly there。

 but obviously concretely there in the implementation。

 So for each class there's going to be one of these things which has you know header and metadata for the class of some kind。

 but usually at the end， there's or offering a side table。

 there' is a thing called a E table and this the terminology。

 I think originates with C plus plus and this is basically a list or the entry points of the methods of that class。

 typically in the declaration order that they came in prefix by whatever whichever were inherited。

 So if we start with a A has no superclass I'm cheating a little bit here because really it would have the object methods here too。

 but I'm alllaiding that just for the purposes of the。The presentation。

 So A has two methods F and G we have two slots， F and G and each one of those points that the corresponding code for those methods in an interpreter that would be a reference to Btecode in a compile system。

 it would be a reference to machine code。And if it was a just in time compiled thing。

 it'd be a stub that would trigger a compilation when you try to invoke it。

So but I'm ahead of myself a little bit。 So that's the fairly straightforward structure for the top class。

 the subclass looks like that， but then adds the new methods on at the end。

 So F and G are just in in this V table in the same order they were in the parent class and then you add on the extra methods at the end So they're in the same order and the order is typically the declaration order in the source code。

 but you know it doesn't have to be as long as there's some canonical order。

Which is preserved as you go down the class hierarchy， would that would work fine。

So we're adding the new methods at the end。And then what we do is in the metadata of the system。

 we have the mapping from a method name to the index into this V table kept off to the side。

 so when we want to call， say F from the middle of G， we're doing something like this。

 at the machine code level， we're taking the thing that we have in our hand。

 which is the reference to the receiver B at an instance of A or an instance of B。

And we're doing an index through that to get to its class and the classes are all stored at the same offset in the layout so that instruction will work on any kind of instance。

And then from that， we do a load of the pointer to the code that we want to invoke by taking the offset that's known at compile time of F。

In this structure and adding on the base of the V table。

 the way I've done it here is I've assumed that the class and its V table are contiguous。

 which gives you the fastest speed rather than having another indirect。

 Some some V Ms have another indirect。 and then they do the indexing。 But this is the。

 this is the optimal。Version。And then once you've done that load。

 you now know where you're jumping to and then you can just call it。

So we have this double load going on before we actually figure out where we're going。 and。

 and those of you who implement hard hardware will appreciate the， the difficulty。

Of trying to predict this other than by， say， looking at the previous versions of the execution and using those as predictors。

 because， you know， you have to wait to resolve this。 You have to wait for the loads。

 the dependent loads to finish。So it's potentially a long time before you know where you're going。

Yes。These classes are concrete classes。I feel like he can static come。Yeah。

 so the reason I put on the restriction in the previous slide。

 single inheritance static typing is in with those restrictions， you can do the。

Mapping of names to offsets。 as soon as you see the class。

 So as soon as I have this class in my hand and I've loaded it， then I can compute this mapping。

 And this guy is going to inherit the same mapping。 but with extensions。

 So I don't need to worry about him until I've got instances of B around。

 And then I just inherit his mapping and add the things in the end。

 And it's this sort of monotonic process。 throughout a hierarchy of classes。 Now that F。

In this hierarchy might have a completely different slot from an F in a completely separate type hierarchy。

 Soupp Bo we had classes P and Q， each with our own F， unrelated by inheritance。

They might have different indices。 But that doesn't matter because it's a statically typed language。

 We can never mix those up。So there's no danger that I invoke F on a P when I'm assuming I have F on an A and thats that's the benefit the static typing gives us it gives us a restriction as to what we might be calling based on the type information rather than just。

 you know， we're calling something by this name that could be anywhere。Question。

So it's also better for a B to have coffee。A not。你同我车系诶 had a lot边。有一次好不考。

Because it' also be fastered。Well， so， so， so this is just， this is just a pointer。

 and they share the code。So will， so， so if you inherit a method from A and you don't override it。

 you just have a pointer to it。 So in this case， they both point G in the because this isn't overridden。

 They're both pointing to the same G method。You would only have like the methods that were defining you and if you can't and if you can't find a method。

 then you would。Well， you could do that， but that's slower because now you're having to put a loop around everything。

 So instead of just doing a look up and call， you're having to do a lookup if your look up fails。

Look up the super class。 do another look up there， et cetera， et cetera。 So this is， this is the。

 this is the fast way of doing V table calls。 And this is what's used in something like C plus plus。

Yes。These references are actually symbolic references。呃。What's the theses in this？

What's the these in the sentence。So so this is actually a programme counter in a compiled implementation。

 It would be the address of the entry point。 So literally the thing that you pass as an opera and to call。

If it were an interpreted system， it would be an address of a method or a byte code or whatever it is that the interpreter is expecting to be handed when it invokes a new method。

 probably a method object because it needs to know the metadata as well as the。Well， so this is。

 this is a generic。Way of doing dispatch of virtual methods in statically typed languages used in Java。

 but it's also used in C plus plus and pretty much any other statically typed single inheritance language。

So it's a， it's a common pattern for implementation。

 and actually gives you when we look at the dynamic languages， we。

 we're striving to make it as fast as this。Whenever we're implementing the dynamic language， right。

 because this is， this is sort of the best you're going to do given a virtual type dispatch on an object。

 You know， you have to somehow。Track down the thing that you're calling。

 And that's dependent on the specific。Class information of the specific object that you have in your hand at that point。

Okay， I've all it from this obviously pushing arguments and gathering all of that stuff。

Any questions of this？Just to be clear， the semantics of G if you go back one slide。

I don't know Javava very well。Since G calls a。Piv a class of A， that's telling A's of。

class of B when I call G it's going to call B， yes， exactly。

 So the F depends on the specific instance of the object that's the target。And what its classes。

 you cannot resolve it statically。So if I write， it's like this。Yeah。

 yeah so if I write if I have a variable bound to either an A or a B， so the variable is of type A。

 if I bind it to a new A and call G， G will call A' is F。

 if I bind it to an instance of B and call G， it will call B's F。😡，So that's what this。

 this is giving us。 It's giving us the way of dispatching to the class specific variant。

No matter which one it happened， which particular kind of instance you've got in your hand。

You can have the same code for G because it's being passed。Yeah。

 because of the so I haven't gone into the detail of this。

 but basically the same prefixing arrangement is typically used for the fields。😊。

So if we had fields in a， there would be declared here in a certain order and there would be offsets to them。

 and then this guy would inherit that and append its own layout。

 but I'm not talking about layout just now， but that's why the code is shareable because the layouts。

 the layout of the superclass instances of the superclasss a prefix of the layout of instances of subclasses。

Back to what you're saying for fields， so you're saying B， it would copy As fields， and then outs。

Yeah。You don't want it to copy a field because well if you change the field with A。

 then it should also change Well， so the way。Almost all， not all。

 but almost all programme object oriented languages work is if I declare fields in here。

Then an instance of B gets its own copy of those fields。 Doesn't have to be like that。

 And we'll see probably somewhere along the line prototype languages that do it the way you just said。

 But this is the common pattern in most object oriented languages that that。

You get copies of the fields in every object。Okay。So number two or four or two or five。

 but we'll only cover four for now is the static invogue。

And this is used for invoking static methods in classes。 So if we look at the top。

 we have a class fo。 it has a method M that's declared static。

 And that means you can invoke M without having an instance， right， you just call or M。

 you don't need an instance of foo that you're dispatching on。 And because of that， well。

 an other decisions that were taken in Java。 that binds always statically to that method。

 Okay so so M will always invoke the method M in fo。 There's no no dynamic lookup required there。

 So if you look at the signature of the bycode， there's no object reference。

 there's just arguments being passed and the target methods determined statically。

 So that's that's like a conventional call except。The naming is a little bit different because it's not a global name space of。

 of methods。 It's a class specific name space， but otherwise， nothing surprising there。

Number 3 is the interface invoke。 And this is pretty complex。 I won't go into the。

Have these are implemented until much later， but I'll explain what this is trying to do。 So in Java。

 you can declare interfaces， many different interfaces that define methods that have to be implemented by the classes。

To implement those interfaces。 So in this example， I have an interface F。

Which says all things that are of type F must have a method called M that's avoid with no as。And so。

 when F implements。So went through implements F， it has to provide a definition of M。

 And then we can invoke M on。Any fo， or indeed， we can invoke it on any F because all Fs are supposed to do that。

 And one of the interesting twists here is that Java allows multiple interfaces to be implemented。

Which makes the look up now not a straightforward linear type thing as we did in the in the invogue virtual。

 And so this needs its own special bike code， which， which denotes that that's what we're doing。

 It has all some interesting。Anachronisms。And it's design。I thought I'd copied the note。呃。Rats。

 there's an interesting note that says。呃。Zero in the Opt code。Like what's that for。

 it's just there because they needed some space in the original implementation and so they reserved a bite。

And it's the lab。And then the count is actually redundant。 this is the argument count。

 It's actually redundant with the the interface signature that you get。

 the method signature thats that's indexed by the indexed bytes。

 So so there's like a couple of bytes that so they don't really belong there。

 but they're still there and they got bakegged into the standard。まあ、すすきな。Yeah， so。

 so these parts are the ones that look up into the constant pool to give you the， the。

 the signature of the thing you're calling。 But the。

 the other two are just like historical leftovers。It was last time， is there a constant pool per？Yes。

 yes， so when you load a class file， it's actually mostly constant pool。

 there's a little bit of structure at the beginning that gives you the indices into the constant pool for the fields and the methods and any other metadata。

 but then the bulk of the file is the actual constant pool entries is that they things like signatures of methods and type descriptions of fields and stuff like that and theres one there's one in every class file。

Okay， so we'll get back to interface dispatch a later date and then the last of the four that I want to talk about is a thing called invoke special and this sort of fills in the gaps that are left in the other bycodes so for example。

 if you have a class B that extends a and provides its own definition of M but wants to invoke the inherited M then you have to do that using the super。

Dispatch， you can't implement that using invoke virtual because they would just be a recursive call。

 You'd end up coming back to the same M。 So it needs a separate bikecode to do that。

 And that's what the invoke special is for。 It's used for invoking methods for super classes and also for another sort of other random stuff private methods and instance initialization methods。

 which are basically methods with special names。 and it has a similar kind of signature to to invoke virtual but a different dispatch。

 So invoke virtual locates a method based on the class of the object invoke special。You know。

 uses the， the current class to figure out。What the superclass is and invokes the guy in that。

 So it's just a form of static binding。 Yes， this is probably a competitive question。

 but how aggressive is Java in mining private functions。Well。

 that depends on the implementation in the bike code， you know there's no inlining at all。

 there used to be an option on Java C that did some limited amount of inlining， but in general。

 the bikecode doesn't because you might have different versions of libraries and you don't want to inline code and then switch the version。

 but VMs or at least the high speed VMs are extremely aggressive about inlining。

Relationship between private。So you can declare those various different flavors of privacy。

 you know protected and private and public and if you want to invoke a private method。

 you can't do an invoke virtual because that doesn't let you see private methods。

 so you need to do and invoke special to do that basically you can only invoke methods of the same class or inherited ones protect if they're protected in inherited ones。

And there's， you know， lots of fine little twidly details because there's package protected and various other flavors。

 which I can never remember。Okay， returns well， let just returns。

 nothing particularly exciting there， there's a return an I return and air return and D return and you know all the usual types and it just returns。

A little bit of a twist。 We'll get onto synchronization。

 It has to do special stuff with synchronization。 We'll get we'll talk about that for a couple of minutes。

And it also has to do stuff around exceptions and we'll go over exceptions in detail， yes。

It taking an argument。Becauseuse this is a this is a method that's avoid。

 So if you return a specific thing， it's either an I return or an air return or a D return or an L return or R。

I forgot one。So if we go back to the list。They returned。呃。There's all the flavors。

And return is unusual in that this is the only place where void appears。 You know。

 in all of the other cases， you can't have like a void ad。

How many uses it take to develop what call this job？knowing like how how many types of like。

LikeHow do you？This was a couple of people for a year or two。It's not as hard as you might think。

Especially when it's this messy makes， that makes， that makes it easier。

 If you want to do it non messy， that's harder。Smaller is harder。Okay， so synchronization。

 let's say a little bit about the bycode level。Implementation of synchronization。

 You've probably all written synchronized methods where you put synchronized at the beginning of a method declaration。

And you probably know that you can have synchronized statements。

 which just look like a compound statement with synchronized and an object。Level。

 an object mentioned at the beginning。 And that's implemented in two different ways。

 A synchronized method is basically implemented by a special attribute。In the metadata of the method。

 there are no special bikecodes for synchronization so when you invoke one of those methods you have to check this thing and do the appropriate locking。

 but for synchronized statements you have monitor enter and monitor exit bycodes and they implement。

 you know you bracket a bunch of bikecodes with monitor enter and monitor exit and that gives the locking around。

Blocks of code。So monitor enter。Take the object that you're gonna to use as the monitor。

 the lock and the lock set， you know， following the Java semantics。

 So the object has to be basically takes the object and associates a monitor with it。

 Now monitors of these things that are in the implementation。 You don't see them as a Java program。

 They're implicit by the fact that you're doing synchronization。

 but they don't appear as objects in their own right。

And so the implementation is free to implement them either as separate structures or bits in the head or various other techniques。

 high speed synchronization is a topic of its own and we'll cover that。

If we get to it much later in the course。 So I'm not going to go into the detail of how this works。

 only sort of roughly what it does。So the monitor has the notion of an owner associated with it and the thread that enters Mon enter for the first time gains the ownership and then everyone who tries to enter the monitor while it's owned has to wait until the ownership is revoked using monitor exit。

So typically the way to think about it is you have an entry count and the count is incremented and。

Only the first guy in gets to execute the code everybody else has to wear。 So threads block on。

On monitors that have non zero counts until their fall to zero again。是。

For those of us that have never heard。Or least never used that。What does it look like write？

Do you write enter No， no， you write synchronized and and a reference to an object。

 which is the object that you're synchronizing on like you were invoking a method on it。

 except you just write the code right there of the method in curly braces。

 so synchronized pres the thing you're synchronizing on open curly brace and a bunch of statements。

And then yeah， that's right and what's the thing synchron。Like a lock team。Well。

 so it that's the implicit monitor that's associated with objects that are being synchronized upon。

There's just any object。 You can synchronize on any object。So you any， any object type is valid。

But you don't really like。But the synchronization isn't tied to the object。 It's just， Yeah， it is。

 it is。 The monitor is bound to that object， and that object then is the only way you can get to the underlying monitor。

 You can't get to the monitor independently。 between the brackets doesn't have to have anything to do with the object。

No， you can do what you like in that。 It's， it's， it's mutual exclusion just do like。Typically。

 you access the fields of that object because that's the thing you're trying to not race on。

 That's the normal practice， but you don't have to。Yeah。So。

So monitor enter and monitor exit are used together to implement the synchronized statement。

 they're not used in the implementation of synchronized methods as it says。

 so that's one little quirk in the way the definition is provided。

 even though they provide equivalent semantics。And。Monitor entry on invocation。

 all that stuff of when you invoke a synchronized method。

 all that stuffs handled implicitly by the JVM。 So it's as if there was a monitor entry and a monitor exit around the。

 the method being invoked。So monitor for exit。Is sort of what you'd expect。

 It takes the object that you're exiting the monitored region of。

And then if the thread here's some interesting stuff。

 If the thread that executes the monitor exit is not the owner of the monitor associated with the instance referenced by the object。

 then it throws an exception。 Can you imagine。How you might。Get into that state。What what。

What situation might we get here。Yes。什么？Because of some of our， we have like many。Yeah。

 except in this case in Java， the only way you can enter these critical sections is either as a part of a method。

And so whatever you exit at the top， you have to whatever you enter the top of the end method。

 you have to exit at the bottom or as a synchronized statement， which is similarly symmetric。

What's the problem being addressed here？Could generate by。Yeah， exactly。 if you like。

 you can write bikecode generated that's not from Java code that does a whole bunch of monitor enters in a loop。

 you know， as many as you like on different things。 And then the exits that come after that。

 You know， there's no guarantee in the structure of the bikecode that they're paired up because it's just a bycode。

 And so what this is saying is you can write what you like。

 but you better have matched exit enter pairs when you actually invoke the thing dynamically。

 Otherwise you're going to have this strange state that you're trying to exit a locked region you never entered。

 and the VM has to find that dynamically check for it and raises an exception。

 which which is a little bit more complexity in the locking implementation that isn't implied by the semantics of the language。

我觉得那。Would try to write the。Compiler said using。Well。

 so you can either have an implementation of some other language on the JVM or you're trying to steal someone's bank account。

 right。I mean， those guys exist， too。 And if you， they can use this to get access to your bank account。

 and they'll do it。 So the。The VMS to defend against that behavior and that's only because the structured control in the language is not represented here as structured operations at the low level。

 if they'd had synchronized and a lambda around it。

Then they could have done this as a synchronized lambmbda。

 but Lambdas didn't exist in the first version。 And these bikecodes had to be around something。对か。

The balance monitor。い。It's yeah， because it's dynamic because I could put the enter in a loop with an arbitrary account from a variable I read at runtime that says I do so many enters。

No， it would say that's fine。It wouldn't complain about that at all。The verifier。

It could exclude that， but it doesn't。 but it doesn't。

 It's the dynamically that they have to dynamically match up。Monior exit。

And then you could just be like this starts。Well， then you'd have some complex rules。

Enforcing the nesting of。Nestted sets， you know， can imagine you have something that looks like this with an enter and an exit and an enter and an exit。

I mean， I don't know if that's necessarily bad， but。like can generate。Yeah， well。

 so so so this structure， I think， is not possible at Java source level。

 but it is legal in the VM because they're matched pairs， right， All what says is that when you exit。

 you have to already be the owner。So in this case， you take ownership， you take ownership。

 you release the first thing you took ownership， and then you release the second。

 which is weird from the point of view of parallel programming to do things in that order and you're opening yourself up to all sorts of bugs that way like deadlocks。

 but， but you you。Feel free to email James Goffling and ask him Timler。 who knows， Who knows？

 I don't know。You know， maybe this was like the Friday afternoon。Part of the bikecode design。

I hope by now。嗯。You view this whole thing with a little bit of sism because it it's while a lot of effort has been put into this to make sure that it's internally self consistent and tight and that there are no holes。

 it's incredibly complex。For what it does。Was there another question？Now。

How many working Java virtual machines aren there， but fully compatible with？I don't know for sure。

 but it has to be in double digits， at least。Yeah， at least in double digits。I mean。

 this is actually not hard to implement， it's hard to make it fast。That's the tricky part。

In the cases that are common where they are matched。呵。'Lot of corner cases here where you know。

 you just throw more programmers at it， right？Yeah。

You know working it's the best of the knowledge anything that has a， you know。

 a coffee cup logo and is compliant has gone through， you know。

 a very elaborate test set that tests all the corners of these things。

 And I I would say there's at least a double digit number those。 I'd be surprised if it wasn't。

 certainly of that order。And at all point， Sun alone had 10 different Vemla implementations。

Although some were derivatives of others。 So maybe an a fair metric。Alright。

 so let's wander into another。 Actuallys， let's take a break。 now。

 we've been going 90 minutes and you take a 10，10 minute break，15 minute break，2022，4。Sure。

I'll take an exception。How much more time will take in。But what you are saying， like。

 oh if you're a hacker and you w to get like someone's bank account。

 I didn't look at how that worked like Not sure you can take classes at nap。😀は。Yeah。

You kinda have to read between the lines， usually。ItNo， didn't。Well， so。

 so the kind of nightmare scenario would be to have a situation where you know。

 back in the days when Java apples were common if a bank was giving you a Java applet and and you managed to like do an attack where you substituted some other variant。

 you know， then for that to then access other parts of the VM and and get like， you know。

 account numbers or passwords or whatever out of it。 that's， that's the sort of scenario。So you like。

Yeah， yeah。 Once upon a time， when you logged into some banks that you got a Java Apple it downloaded from the bank。

 So it was Java code running and it had to be doing the thing that the bank wanted it to docause otherwise。

 you know， bad stuff could happen。That or， or， for example。

 imagine you had a web page with an ad which might also be running some Java code。 though， you know。

 can the Java code in the ad get access to the state of the banking， you know， stuff like that，Well。

 but in a browser， that's not the case， right？You usually everything running on the same web page runs in the same address space。

Well。boy like。So you example。方向 that。cannot again have the then。

it's very it's very it again thinking thinking you all't return just。

you could make the I sort of just。just returns like a value。So basically， I assume stand a through。

なやりつきスて。I environment。IThe things when you're exhibit doctor， it's an。

If there are more than one statement， it comes as a sequence， so then you evolve environmentally。

one part in the。But this seems the first part call。That's because the first time。Okay。

 let's let's resume。There is a difference they're doing。But don know that。Okay guys， let's resume。

Okay， look at exceptions。 one of the。One more complex parts of the machinery to understand。And。

 and to implement。So a little refresher on how you write exceptions in Java and then we'll look at how they're reflected in the virtual machine spec and how that works。

 So's start with a simple example。 So I have a function here that has a try catch block in the try block we run some code which we're going to call some function somewhere and not listed here called try out and that's going to eventually call this thing down here can't be zero。

And if an exception is thrown of type test exception in this block。

 then this handler will catch it and run the handle exception function。And then our。

In a function here can't be zero is declared to throw the test exception and if the I that's passed is0 then it throws the exception otherwise it doesn't。

 So the behavior here there is two cases we call less and I wherever I came from isn't zero in which case we just run try it out and then we fall off the end of the function in the case where I is0 this guy gets interrupted and then immediately control transfers to the handler the catch block here and the code in the catch block is run。

It's the third part to it writing and something else falls。And have to。Yeah。

 if there's a unrelated exception thrown in here， then this doesn't match because this。

 this type has to match this type for it to catch if they're different。

Then some other handler is going to deal with it， hopefully。Okay。

 so that's sort of how it looks in a simple case。 How does this look when you compile it？

Let's start with the can't be zero thing which throws the exception。

 So this is pretty small at the back， but I hope I hope you can see oh you have a copy of the slides from the resources section。

 So this compiles into a little sequence of of bikecodes。 So here's the the throwing part。Of the。

Of the function。 And here are the bike codes that correspond to that。 So in this case。

 we make a new instance of this class test exception。

And then we invoke the initializer on it because it's a new object it has to be initialized。

 and then we have the air throw bycode， which just takes that object and throws the exception and then that has to somehow do stuff the matching part。

Let's see if I got my animations working。 Yes， so the matching part is down here in the two pieces。

 We have the tri block where try out is compiled into these three bycodes that just。

Pushes the this onto the onto the stack and invokes the virtual with a with the appropriate signature to call。

 try it out and then does normally would do a return。Now。What happens next。

We also have the handler here， which is compiled into a separate piece of the same method。

 and that is going to invoke a handle exception， putting this and the E onto the stack。

And then doing its own return。 So because they both end at the beginning of the method。

 And we have at the bottom。This exception table。 And this is part of the metadata of this method。

 So every method can have an exception table associated with it。

 An exception table always takes this form with rows that look like this。

 So the first part of the row says gives us a range of bike codes that we're guarding over。

 So it says in the range of 0 to 4， if you see。呃。Whoops。Damn， if you see。This type of exception。

Come on faster。If you see this type of exception， you're going to go to this bycode。

So basically the way the exception table is structured is this list of coverage regions with an associated handler。

 and you can have lots of these in a method and they can be nested and composed in all sorts of funky ways。

So that's the basic mechanism here。 So if anything in here throws that exception。

 we're going to resume execution at Bcode 5。So if you're a compiler writer。

They're stitching together all the way。Make all the basic logs。For the， well。

 you can have multiple rows of the exc。 you know， you can cover all the different pieces with different lines of the table。

 So you don't， they， they don't have。 It doesn't have to be minimal。

So you need a list of exception tables or a stack of exception tables。

 say it's not in this range you go to the next。Yeah， so these are processed in order in some way。

Again， if you go into the detail， it will give you exactly how the table it works。

 but you know the bikecode that we already saw in that listing was Erow that takes the object that is the object that represents the exception。

 it pops it off the stack and it has this unusual semantics that it pops it off the stack in the frame where it was thrown。

 but it pushes it back on in the frame where it ends up being caught。

So even though this looks like we're just taking the thing and doing nothing on the stack the reason it's depicted here is because we're throwing away all the intermediate frames until we find the handler and that's。

 I think what the text says。 So it pops the throable。

 which is the generic class of things that can be thrown from the stack and then it searches down the frames。

 cutting the stack back until it finds a matching handler and then pushes the thing back on the stack and goes to the target yes。

ご人は。今属。Going on with the up for here， 01。So these bike codes are not single byte length。

 So invoke virtual has a2 byte。offsetffet a displacement index into the constant pool， sorry。Yeah。

 so those are byte code indices。Yes。So within a method。The stack has to。It has to be。

Bifier has to be able to say that。At all merge points。Exception can be a。Yes， and that has to be。

Inherit。If instead of this。Being caught here time。Yes。じゃあ、どぞは。But how would you how， how， so look。

 given this structure， how would that， how would you express the inheritance of the handler。

I don't think you can do that。Because the code has to be in yeah。Yeah， yeah。Because。

So the handler has to be declared in the method that's doing the handling。 It can't。

 There's no sort of implicit handling of stuff that isn't literally listed。Yeah。It was very separate。

Yeah， I'll get to that that adds an extra special twist。😊。

One more observation so the opera branch stack here that it's just a pop and a push。

 but it's also popping the exception and then popping everything else right。

 because you might be in the middle of doing some。Yeah。

 you're throwing away all the stack frames until you yeah， yeah， yeah。

 you're sort of throwing away if， if， so the the stack of this method just disappears， right， Oh。

 so if the catch was around it， Yeah， it has to， yes。 Yes， Yeah， yeah， yeah， exactly。

That's a good question， does if you're writing a naive interpreter。

 how do you know how many vows are all？Don't be naive。 You， you have to。

 You have to look at the metada very， very carefully to know exactly kind of where you are and where you're going and how to match。

It's， it's， you， you're basically consulting this and the。呃。The， the stack。

 in effect of where you are in the method。Yeah。Okay。So finally adds a little twist and in fact。

 an ugly one， at least in the initial implementations。 So in a final clause。

 you can write a try and a catch I've omitted the catch here。

 but then finally is the final clause is called either way。

 So whether you completed successfully or whether you executed the handler。

 you always want to run the final block after。 So there's two ways of getting into the final block。

 there's the standard fall through from the tri block。

 and then there's the exceptional path that takes you into a handler and then brings you into the into the final。

 So you've got capture that in the bike code。 And for that in the initial version of Java。

 there was a specific mechanism that was used all the time。

 which was the JSR and the Re and JSR W is just the same kind of thing。

 but with wider constant pool indicess and that was used to call the final block in a tricatch finally。

From both situations。 So let's， let's have a look at an example of that。 So here's a， a try。 again。

 it's minimized just so that I can fit things on the slide。

 I have a try and a final with a neural handler。 And so the code of the tri block。You know。

 looks familiar from the earliest earlier slide。 It just invokes the virtual and returns。And then。

Here is the finally block， which it would normally。呃。Go to using this JSR。

 Now JSR is a it stands for jump subroutine。 So it's a linkage thing。 It calls this。

 And then when you see a rat， you come back to wherever this came from。

 So the flow of control here is airload invoke virtual JSR takes you to the final block。

 which does the air store airload and invoke virtual of wrap it up。

 and then that returns back to after the JSR， which then has the full return out of the method。

 So JSR and Re or a subroutine mechanism。 within a method right there's no new frame being created here。

 It's just a linkage technique，Now。What happens in the exceptional case。So， imagine。

We have the exception invoked from the middle of the invoke virtual。

 then our table our exception table will direct us to bytecode 8。

 which is where we have the the handler for Erow and in this case even though we didn't write one。

 the compiler has to put one in for us to do the right wrap up code and what that's going to do is that's going to do the JSR to the finally block which comes back and then it's going to throw the exception because there isn't a catch in this case so in this case what's happening is we're sort of catching it what we're not really catching it we're just going to run the final block and then continue rethrow the exception so that whatever handles it outside of us has to deal with it。

So why do they do this JSR in RE so that this piece of code doesn't have to be duplicated。

 because if you look at the way this is structured， if you didn't have the JSR RE。

 you'd have to compile this in line in both of those two situations and you'd end up with duplicate code and you can nest tries inside of other tries and so finals can get inside of other finals and every time you nest it would duplicate the duplication and you know maybe it would blow up into some horrible space footprint。

 we'll see a little bit about that later。And instead。

 you have this other mechanism now with JSR and RA。😊，So。In this， in the exceptional case。

 the invoke virtual is throws an exception that's caught by the compiled in handler。

 That does the JSR So the finally block that returns back into the handler。

 and then that rethrows the exception goes out。iss JSR a new stack？No， same stack， same stack。

So the spec is that the address of the op code instruction immediately following the JSR is pushed onto the opera end stack as a type value of type of return address。

 Wow， look at that。So we have another place where we can get return addresses from now。So。

 here's another。And it's pushing a return address， but within the same stack of the same method。

 So we're not making a new frame。 So were have in effect subrouts within methods。U。Rat。

Doesn't do quite what you might expect。 So rat takes the of index。

 which is an index into the local variables， pulls a return address out from there and then uses that as the target。

 So this is kind of like a funky go to。 actually， because there's nothing being popped at all here。

It's just taking an address out of a local variable and doing a go to to it。

And it has this weird asymmetry that's noted here and。Prior to Java S6， this was used all the time。

 if you look at a more recent implementation and you compile these examples。

 you actually end up with a code copied， you don't end up with JSR and REs。These are pushed。

But rat doesn't pop it。Yeah， you have to look at the code。So JSR goes to 14， and then this。T。

Takes the thing that was pushed and stores it in a local variable。And then when it does the red。

 it pulls it out the same local variable。 It's using the local variables as a linkage I don't think anyone here is old enough。

But once upon a time。In the foreran of old， when recursion was not allowed。

 the way you called a subroutine was there was a location in memory reserved for the return address of that subroutine。

 And when you did a call， you stuck your current PC plus whatever offset in that thing And you called the function。

 And then when it returned。 it pulled that slot out and it did a go to to it。

 And that's what this is doing。 right， It's a nons stackack based linkage mechanism。Yeah， yeah。Yeah。

 so it's a non stack based。Call and return。I usually don't call it JSR。Cor。Late night， Friday。

 maybe after the。You， you'll see there are many implications of this design。

 which are much worse than anything you've seen so far。嗯。Okay， so they were abandoned in Java S E 6。

 And now they're just。Duplicated so one of the reasons is when we we'll see this when we get into GC。

 that should say GSR， not J is that if this mechanism complicates garbage collection enormously because in particular you can you can call into a subroutine。

 one of these GSR rat things。😊，With different stack configurations。And as long as they're they're。

 you know， they're local to the calling context， that's allowed because the finally can be invoked from different places。

 And you might end up with a different thing on the stack。

 And suddenly G C gets really difficult because in the two different paths。

 the local variable on one path might be an int and another same local variable might be a pointer。

 So now we have to disentangle less mess in in garbage collection。 So the abandoned this in S E 6。

What about the duplication problem。hoAs everyone read the Goslington paper。

 what was Java called before it was Java meant O。So if you look in the class files。😊。

Everywhere in the class files， there are signatures of methods in the class libraries that say Java slash lang slash。

 you know， bh with a method signature or a class name or something。 Before that。

 they all said O slash lang slash。 So when they renamed it。

 they added one bite into every method of constant pool entry。That had the language in Nemen。

 Someone told me that they did the analysis and that loss of space by that one character extension of Nem was bigger than all the space that were saved in the standard J K through this technique。

So， this was。All the duplicated code， when you copied it out。

 was smaller than just the extra character in every the name sprinkled through all the class files。

Fo。Probably probably wasn't worth the complexity。 Probably wasn't worth the comp。Yeah， yeah。 yeah。

 one character language namess。 that's definitely the way to go。Basic beat you to it。Oh。嗯哼。😊，ok。U。

Ps are like more powerful than just implication because the naive was implemented would be。

Is it more powerful， I don't think so。 I don't think so。

 It just saves you those extra byte codes because， and especially in the case where you can reuse the stack signatures。

In the two cases where you'd have to duplicate to pass the verifier otherwise。Okay。

 just to pour a little salt in the wound。 they interact。

 Excepts and synchronization all have an interaction。

 So when you throw exceptions from within a synchronized method。

 there isn't a monitor exit explicitly， It's implicit in the semantics of the synchronized method。

 and the exception handler has to all undo the monitor acquisition as part of the cutting the stack back as it's unwinding the exception。

 So throwing an exception and catching it is a fairly expensive kind of thing in this Vm。

 there's a lot of stuff going on under the covers to deal with exceptions。

 which is why using them to implement you know loop constructs in the interpreter probably isn't such a great idea。

😊，So exit from。You know， exit from a synchronized method has to do one thing an exit that in the middle of a synchronized statement has to do another。

Okay， so one thing you might want to do。With all the stuff。

Is poke around in some class files for yourself and see if you can figure out how all these pieces fit together。

There's a couple of ways of doing that in the standard JDK there's this thing called Java P which prints out the contents of a class in a descriptive way。

 if you give it the dash C option it will also disassemble the bycode and list it out for you and so you can take any class file do Java P dash C the name of that class file and you'll get a readable listing of the methods and the bycodes in that class and you can kind of try and match up what's going on there isn't alas in the JDK the inverse of this that takes a readable description and generates a class file other than the Java code via Java C。

But there are a variety of open source assemmbbllerers that will do that if you want to noodle with bikecode by yourself so you can type in your own bikecoded methods and assemble them by hand and see whether you can get them through the verifier。

So speaking of which we should say a little bit about verification。 What is it doing， Again。

 it's a big， complex process with a lot of。A lot of detail to it。

 but the overall principles are fairly straightforward， so the idea is that when you load a class。

 you want to check that the class is in the right format that includes all the right structure and that it's internally self-consistent and that it's consistent with all the other things that you have loaded already into your system so that you're not doing you're not doing things in one class which are inconsistent with the behaviors of another class of the types all match。

 for example， you can't you know by passing an int to a function you're calling。

 if that function is declared as receiving an object reference。

 you're and doing an implicit conversion from one to the other， all the types are matched。

So it has to do a load of the class file and pause the class file。

 read in and build up structures representing the content of the class file and then do a bunch of checks that static constraints are met so the consistency checks are one kinds of things that I already mentioned branches have to go to a valid bikecode there are plenty of other structural checks that are required and they're listed into copious detail in the manual and then all the operations that you're invoking all the bikecodes a type check to make sure they match with the the declared types。

 the inferred types。Type inference I wasn't aware of no。So let's go into that。

So the JVM knows about certain kinds of basic types。

 these are sort of the way the JVM thinks about the type world。

 are the primitive types it knows about there's return address and there's reference and then reference is decorated if you like with the actual your declared type as you wrote it in your Java code well actually even that's a little bit of a lie in that if you wrote a parametric type that doesn't appear here because paraized types were added to Java after the JVM was designed and Java C just removes all that stuff and maps it down to some other bit more basic types so you won't see any parametric types at this level but you will see these。

And I mentioned， you know， return address is this weird thing that's dealt with by a number of bycodes and they're pointers to op codes。

 but you know who knows how big they are， that's your problem to deal with when you when you when you implement the VM and they're never supposed to be mixed or intermingled or modified by the running program that is generated by the VM and used by the VM。

So how do we do the type checking We have a whole bunch of type stuff that's in the class file how do we know that it's consistent with the bycode and consistent with everything else in particular we have all these typed up codes that are assuming types we need to make sure that those are doing the right thing and so we go through a process that's known as abstract interpretation and because it's related to interpretation it seems worth explaining in this course you might have come across this in other contexts because it's actually a common technique in a variety of disciplines for example in compilation abstract interpretation is sometimes used。

But the idea of abstract interpretation is you interpret the program。

 but you're not interpreting it using the normal domain of values that the programme is going to run against when it really runs。

You're interpreting against some simple， abstracted state that throws away some of that detail for the purpose of computing some other idea or some other answer。

So an example is， suppose you interpret the bycode， ignoring the values that were being computed。

 but only modeling the types。So use this to verify type correctness。 And here's an example。

 Remember our little expression language where we just had four functions and simple variables。

 Let's make a simple modification Now。 We're gonna have four trans style typing。

So I to n are ints and everything else is aloat and a variable can hold a float or an mint depending on what name it is。

 how can we check that the bycode for an expression respects these types well one way to do it is through abstract bycode interpretation。

Looking at the types of the things on the stack。 and here is the guts of the former bycode interpreter redone to model this。

 So we have now two literal bikecodes。 One that pushes an int to one that pushes a float because obviously。

 we're dealing with ins and floats。 And so we have to be able to write ins and floats in an our abstract interpretation of those doesn't care about the values。

 It just skips right over them， but it pushes onto our abstract model of the stack。

 The appropriate type。 So a lit in pushes int an int tag onto the stack。

 A lit flow pushes a float tag onto the stack。If we have a get int bycode。

 then we can check whether it's correctly type by looking at the name of the variable that it's getting。

 So in this case， this hasn't been typed and run。 So you might find errors in this。 in this case。

 I'm just doing a simple comparison of the variable name in the bike code。

 See whether it's in the range I to N， which is the fourran integer range。 And if it isn't。

 then I throw an error because those are the only things that are supposed to contain ins。

 Otherwise I push int onto the stack。Similarly， if I store。嗯。Into a variable。

 I'm going to do a number of things。 First， I'm going to check whether Im remember， put it。

 put pops an element off the stack。 I'm going to check whether the stack is emptytive。

 The stack is empty。 and I'm trying to do a pop。 That's wrong。 So that's an error。

 If the top of stack type is not an int， that's wrong because this is a put in by code。

 If the variable is not an int v， that's basically this expression repeated again， that's an error。

And then finally， I just pop the value off the stack， and I proceed on。

 I don't need to do anything else。 And the same is true for the gets and puts of the。

Of the float types Now， how do we model an ad or any other arithmetic operation in this。

 So an ad takes two things from the stack and give you one thing back of the same type。

 an add int is supposed to take two ins and give you back an int。

 So if the stack doesn't have two things on， that's a error。

 if the two things on the stack or not int。 that's an error otherwise we as an error should put an int back on the stack。

 No， that's correct， I'm only popping the top one。 So I pop the top one and I'll leave the other int behind float would look just the same as this。

 but within float instead of int。 and let's imagine a bikecode that does an in to float conversion on the stack。

 How would that look。 Well， it would have to check whether the stack was empty it is then that's an error if the top of stacks not an int that's an error otherwise we just replace the top of stack with a float。

 And if you run an interpretation like this over our expression system。

 it will tell you whether your expression is correctly typed at the bikecode level irrespective of what。

So I said。So remember， someone else got to compile the bike code from the source。

 and you don't know whether it's been messed with in， in the meanwhile。

 So you don't know that it corresponds to a legal program。 This gives you a way of checking whether。

It respects the assumptions and the invariance of the virtual machine。 And this works just fine。

In this form， so long as it's a straight line program， we run it from top to bottom。 at the end。

 if we get to the end， it tells us what's on the stack and it says， okay， if we got an arrow。

 it tells us there's an arrow。Now。We have end here。😡，There are some choices here。

 Can anyone think about what I could have done in end。So at the end of the program。

 maybe there's one thing on the stack and maybe there isn't。

 It's up to us what we define the state of the stack at the end of a program。 In this case。

 I chose to flag an arrow of the stacks。呃。Empty， sorry， not empty。

So the assumption here is that it's empty， but I could have checked just as well to say there should be one in one value on the top of the stack。

 and that's the defined result of the program。 It's entirely up to us what we define as the semantics of the VM at this level。

 As long as we make the language compiler for the expression language match up with this。

 we should be fine。Notice also that when this is wrapped in the wild loop。

Of the standard interpreter， the structure of this looks just like the structure of the previous interpreter。

 It's just the detailed actions of change， right， The PC manipulation is all the same。

 The continuouss are all in the same place。 It's just the stuff between the label and the PC and the continue is different。

And in fact， this is very common。 You see abstract interpreters of bikecodes in VMs all the time。

 I've seen a VM with 10 of these in it doing different abstract interpretations of different things with the exact same case switch structure。

 and it's a maintenance nightmare。 You want to add a bikecode。 you know。

 you have to find all 10 of them and add a case arm in every single one of them and make sure they're all consistent with each other。

 And unfortunately， there's really no good way of abstracting a structure like this in a conventional systems language。

 right， unless you use macros or something。 But if you imagine doing this virus C macro I'm not sure it would be any better than just having copies of the code because it would be horribly complex。

So that's that's sort of a thing from real life。 this structure is very common。

 and you do abstract interpretation for all sorts of different reasons， including during compilation。

 verification and various other places so the structure of the interpreter when you write it。

 That's a good reason to make it nice and clean and put lots of abstractions about stack manipulation and program counter manipulation because you might want to redefine the guts of what's going on by redefining those those things。

You also find in some places they rather than write this out by hand in some systems。

 they have in effect a higher level description language。

 a DSL for interpreters in which you specify the actions and you have a separate file that specifies the bikecodes and the layouts and the decoding and a program generates。

