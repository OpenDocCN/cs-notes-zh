# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p07 P8 -BV1qBqPBYEy1_p7-

系咩冇想て。好应该。嗯。You guys should have finished the garbage collectioning assignment by today。

Which is great because this is when you finally have a completely working implementation of he。

Back to front， okay。呃。嗯。I think you should visited so quite a lately。 I think he is actually。

Not about language， I think it's a lot。And I thinks a lot better than a lot of my you family use。

 but the bar is low。Like for example， I heard someone just mention Python。

Python doesn't have a compact gotulator。It has a reference count collector。Even worse than that。

 the semantics that the reference collector leaks out。

So there are some Python programs that won't even run unless it has。Couned。

Oh you you can fake everyone。So， you， yeah， strings， yeah characters， bulloles。

Fenie has basically the same features as all these other three。And it will be fast。

 especially after you do your job。嗯。So last time I made a joke about how you never finished a garbage collector。

real joke。You guys think it's a joke。Right， so this week's assignment is the T primitives optimization。

 so now we're on to the author。The tax criminals optimization is supposed to be you do everything right。

20 minutes。It really some people have already gotten to that。

If you happen to have this one dangling little bug in your garbage collector that somehow wasn't tickled yet。

Then putting this to someone on top， might takele ahead and then we'll just really to confuse you。

So if you implemented and things don't seem to work。

Make sure you also consider your garbage collector because things just keep on。对啊。嗯。So we do ait。

That's going to interface with the garbage collector。When you。

To final FFI is going to interface with the garbage collector if you would allow to add threading and interface with the garbage collector。

If you want to implement hash tables， even。Andter with the garbage collector so basically from here on out。

 everything's concerning the。And that's what I made， like you're never done。O。

So next week is the tech room is assignment。And then after that， we'll be doing co generation。嗯。

So you did something which I do sometimes， but I always try and point out one people do。

 which is confusing a language with its implementation。There is this phenomenon computing。

I have observed over the last number of decades。A language always gets labeled with the properties of its first implementation。

 if you make it slow， everyone good our language is so slow。

 really it's really hard to turn people around on those things。So， you know， fast， slow。

 ups and all language right。Yes， I know you are working， Fie， you can do major programming projects。

嗯。Okay， so today。We're going to close up on interpretation。

 this will be more or less a fit for interpretation。Some material on a bunch of techniques。

 which if you are faced with the situation of having to build a fast interpreter。

 which sometimes happens。Some of this stuff might be useful。

And then we'll start on compilation proper and there'll be an introduction to compilation techniques。

 which hopefully will set you up for kind of the big exercise。Which is coming up。

 which is to build the gym for your system。啊。So that's the goal there。Okay。

 so actually I have a Q does anyone having their heads。

sortrt of speed up factors of their implementations as they've involved， you know。

 what did you go from AST to bikecodes， you know how much did youGC slow things down。

 any optimizations， anyone who care to volunteer， any numbers from the head？

Porex full initial two current。4 x， okay。Okay。Okay， okay， anyone get as much as 10。Really， okay。

Okay coolol， well， we'll see what you got from。Compfinement， okay。

 so as you've probably discovered while you've been debugging。There's a lot of overheads。

 but there's affectionly called dispatch bike， I was going to talk up of stepping through a sequence。

 but you' always seen this so much you。Needs this anymore so you know it's a lot of overhead and in some situations you actually do want faster interpretation when we talk about ti compilation。

 which should be probably next week。You'll see the first level execution mechanism。

While it's not critical can be important on performance。

 so you know having a fast interpreter can be significant also if you don't have the opportunities to compile either because you have。

Resource constraints where you're。You can't generate bulky code or you have environment constraints that preclude that so you know you may be running on a system where you're not allowed to generate code driving for security reasons you don't get writeriable text。

Then you want to make your owning fast。And there's a whole bunch of techniques。

I'm not going to go attempt to go exhaustively through the literature because there's a lot of it and frankly。

 as you get to the peripheries， you know you get to the kind of， does this really matter。

 you know if you present in an interpret it when you can get， you know， factors？

Integer factors by moving to compilation。So I'll give you the main things。

 at least the ones that I think。There are significant ones and try and tie them together and some of this stuff is relevant for compilation too。

 you kind of it's helpful to know one before you going to the other。

So the first technique I'm going to describe is threaded code。

And the idea here is very simple instead of doing fetch， decode and dispatch to your routine。

You do that once and then you just store a pointer to the thing you're going into so you don't have to do the decode it's already decoded you already have an address。

 so there's some amount of expansion factor in this usually from bycodes to machine addresses but might not be that much。

 might not be punitive。And there is usually a pretty significant improvement in performance the technique is really old。

 the first published description goes back to 73。One of these。

 if you don't look at CS SM papers from the 70s， you， you should， you know。

 people wrote in a very different way back then。 I think this is like three pages long or four pages long。

 It took me about 10 times reading it。 figure out what he was trying to say because there are all these examples in machine code。

 you don't know for a source language。 you don't know。know， using terminology thiss long past。

 and it was actually originally a technique for a compiler。

 this was done in the context of a fourran compiler。

And the idea then was because of the machine architectures。

 it was actually pretty competitive with direct compilation。Back then。

 that's no longer really true anymore on what nonprofit， but。Nonetheless。

 a fascinating read in a short paper。So the idea here is we're going to do this transformation here is a sketch of some bycode program mnemonic terms right it's really bites in memory and here's a sketch of what your loop of your interpreter looks like as you currently have it what we're going to do is we're going to transform this into a bunch of addresses of routines and one of the things about the section is it's very。

 very hard to express most of these techniques in even C。

 you know as low level C is as a highlevel language it's still not lowlel enough really to capture some of the idea so I'm I'm going to use some assemler here in there I've tended to use sort of spark。

Because I'm familiar with it， but it's kind of generic risk as so it shouldn't be that hard to follow if there are any mnemonics I've used or any conventions that don't make any sense。

 please stop me and ask。Okay， so we go from bike codes to addresses， basically point us to code。

And he is an example of。In this particular case， we still have our interpreter loop。

 so our interpreter loop now our target is a register that contains a pointer。

To the thing we're executing point through here， this is now a PC previously we had a PC that was stepping through bikecodes and now we're stepping through these machine addresses。

 so each one of these is a whole word。In size。We're going to have this thing our target that's pointing through there and what we're going to do is we're going to load it and then just jump through it。

And at the far end of that， after we've done the work part。

 which is overlied because that's not important to this point。

 we just increment the thing to the next word and jump through that。So you can see的是。

There's a lot of stuff that's simplified。We can go fairly trivially。

 even further and eliminate the loop entirely by just copying that code that was in the loop。

To the end of the loop and put the increment and the jump there and then each routine is just fetching。

 decoing and jumping to the next one。And in fact， in the original paper。嗯。

That was just one instruction anyway， so copying it didn't really matter where you put it at the beginning of the end of one thing or at the end of the other was the same cost。

 Why is it cold thread？呃。The kind of， yeah，'s so it's a use of the word that predictates the modern use。

Buy a lot。 So this has the dibs on the word， but it's sort of fallen into disuse。

 And if you think about， well， you'll see when I I've got a couple of the pictures from the original papers。

 La， you'll see it sort of looks like you're sewing a thread through all the have。Okay。

 so that's pretty straightforward， but we can go even further than this so in this case we're just we point to the first thing we're going to execute and then that'll figure out the next thing and jump to that and thatll figure out the next thing and jump to that etc。

嗯。Yeah， so on a ci machine as an original paper， this sequence of add indirect load and then Joan can be expressed usually as a single instruction and that's how it was done on。

In the paper I think it's a PDP11 instruction in the original paper it's just one instruction so you know one instruction is one instruction or at least it was back then it was pretty inexpensive。

 you could put it anywhere and it was more or less the same cost as doing something simpler。

Back in the days before pipelines。Okay， so these are the pictures from。One of the original papers。

 this is actually from the next paper I mentioned。 but you can see in the original scheme we have。

 there's our loop， which is going round round except the the bottom of the loop， it jumps off。

 does something come back to the loop， jumps off， Come back。

Comes back to the loop whereas in this game now。We're basically just threading through all of the routines using in the example I showed you a data address。

 which we they using as a branch target。And for the modern。Micro architectures。

This thing is basically kind of impossible to predict， really。

And these things now become harsh to predict because now we're fretting through， you know。

 if we're not't going through。嗯。A loop， then each time we call an action routine。

 the following the action routine it calls is going to depend on what the next bicode was。

 so it's just going to go up。So and you know these are shared amongst so this this say this is a description of an ad。

 this is all the ads point to this ad so that branch at the end is going to be used for every had in the program。

So it's going to be very， very knowledge to predict。There is a modern trickk， which we can。

Employ to make it a little better。Which is to replace the addresses here with。colds。

And that has a couple of good effects。The first is now we're actually executing through the thread。

 not just fetching data and using that as a target for an address。

 which means a predictor how much easier the time certainly should be doing really well on these and REs usually are very well predicted too if you've got enough work for them to do in here because usuallys a kind of a longish gap between。

You know where the thing is really executed and by expansion。

But this certainly makes things better on most modern architectures。So we're just aligning that R PC。

 we're just using the native PC。T包都 and。And executing directly。In all these cases。

Where we're doing the threading the back end of the action routine。

 we have to do some amount of deviousness to implement branches。In this case。

 sort of the naive thing is to manipulate the return address。But instead， the。

Generator of this curve can generate jump， right， we're now in this kind of blurry line。

Between interpretation and compilation， is this an interpreter is a compiler， you know。

 and if you think this is a compiler way you know sort raise hands， who thinks this is compiled？

Where did we cross the line， you have to know the ISA and it's be to do this way。Well。

 you have to another I say it's assembly code so where did we well you know， is this a compiler？

I would have said no， right， This is just data memory， right。

 There's no new instructions being generated here。 this is this can be all this code can be in a read only tech segment。

This has to be generated as data， I would say that's not a compiler。

That one I'm not really sure about。And that one， the last one does seem like a compiler now。

 but it's kind of a blurry line and if you look back at the original definitions when I was guessing at definitions for an interpreter。

 this other definition which is an interpreter does the same thing for each。

Thing being interpreted by that definition。 This is an interpreter because the same action routine is being executed for every ad in the program。

 We're not doing anything different to any of them。

 So it's a a really good example of how blurry the gray the black is in the white where they being gray boundarying。

So is the slowest disruptionion here？It's the only thing that what lasts very。Iecture specific。

Because everything else seems pretty easily predicted well。

 this is easily predicted using a return address。If you're pushing， if the fetch pointer down here。

Is able to grab， you know， the pushed return address through some bypass and feed it into the fetch unit before you've actually drained the pipe of whatever's in here。

 this will go really quickly。So then the basic question， what is。Why is the compiler of the Jt。

 why are we able to take advantage of this for the compiler of the Jit as opposed。

 like the example where you have like a subroutine。Assembly and other sub assembly， why are we able。

 what's the performance improvement that we get there？

That the compiler of our interpreter couldn't want it done。Oh， where did where Yeah。

 where we All right， So， so in the first case， if you look at the this case。

We're fetching bites from memory， we're doing bitwiddling to look at them and figure out what we're doing。

 we have some kind of a case statement implementation and there are many ways of implementing that but we still have to do that and then after we've done that。

 then we take this jump。In this case we just go jump jump jump jump jump jump jump。

 we're not doing any of the bikecode stuff at all， in fact you can throw the bikecodes away if you don't have to reflect on them because your language doesn't require it。

 you can stick with just the thread of addresses once you've generated them if that suits。

So that's one big source of speed up， you know this stuff。In this alert。Okay。

 so then we pushed the unpredictability of this branch sort of outer here。But with the calls now。

 we've made the branches and the returns much more likely to be predictable。嗯So啊。You know。

 if you have the time and the interest， go implement some of this and measure it。

 or' just build a little example and measure and see how much difference it makes on a particular architecture。

 but I think you'll be surprised at how significant it can be and you have to set up a realistic test。

Because like I say， if I don't put any instructions here， if this is just rat。

There's no architecture in the world with any depths of pipeline we'll be able to predict this in time to avoid a pipeline。

But if you actually do some work in there of significant significance。

 then you can make So at the high level， the reason that we can do this is because we've structured it ahead of time。

 and then it just follows the structure。 Yeah， yeah。

 we basically we basically executing the structure。

 Yeah we've done the decode of the bycodes once and replace them with a much more machine friendly representation。

 and if you go to the calls， we basically。Transform from a loop interpreting bys and data memory into direct execution calling the individual action routines and we haven't done anything to the action routine you can try at all。

 other than deal with a return sequence。And to make this writing。

You can actually express this in GCC。啊。GCC has this facility。

 which maybe you sign in one of the papers。Send， which is that you can have labels。

And we use them as targets of computer computerd go to。 So there's an extension to see in G。

 But it's a go to example。 Yeah， that's right。 It's a go to。 That's right。 So you can， you can do。

That会。With头 lawyer。That one with a loop by replacing this with sea code that's goes through branches。

 you can't do the， I don't think you can do the call version as you said。是。

Mar an interesting note about that is in the paper they talk about using the computed GoTos as sort of a clever use of this feature when they just GCC had this feature and we saw that we might be able to use it。

If you go now and you look at the GCC documentation。

 the documentation explicitly says threaded code as the motivation Yeah why would you want computer go's just like it's how tofuscate your programs？

嗯嗯。Well， interpreters aren't the only use。I switch to that。If you just use a normal switch statement。

 yeah， you're stuck right with this in direction， but'。No。

 most programs don't require I want that performance sensitive on the individual switch say statements。

Okay， so to generate the thread code， we're going to run an abstract interpretation over the bycode and then that' will limit the addresses of the action of routine team you've seen an abstract interpretation before。

 and as I said at that point if our language doesn't require or environment doesn't require access to that bycode。

We can throw out the way because we have an equivalent representation of。

If you have a languagegu in that you consider say reflect on the bycode or you can change code dynamically at runtime or whatever you might。

 you know that will constrain your freedoms in what you do here the other technique don't if you're not able to throw the bycode away is you can throw the generated code everywhere and just regenerate because the generation routine here is really fast。

It's an N one abstract interpretation， which is going to be certainly no slower than a full interpretation of the code。

 unless the individual bycodes do more or less nothing。

 so you should be able to generate code really， really quickly here。

 which means if you're on out of space， you can always throw some away and regenerate it when you need it。

Okay， so。In the original paper， as I said， it was going to be used by a compiler and it would have these fixed routines to do things like ads off in a library。

 what it would generate the code to do。The the tailored things because if you think about if you bikecode suppose you have a bikecode set which has push local variable onto this deck。

 well it's going to be push local variables here or push local variable on push local variable here and some flavor that goes up to some fairly high number Well in this scheme we have no decoding capability now so you'd have to have all of them there all the time which is fine if there's only 156 if the 64K possible variance。

 then you know things are beginning to get a little painful now。So in the original scheme。

 they weren't doing that at all they were just generating the act of the simple action routines on demand based on the indices that they knew the program had to begin with。

And so the question then arises， well suppose you have the same constraint as I mentioned earlier that you want to have。

 you know a read only binary， you're not able to generate and execute code。Can you use this。

 is this even feasible， Well， there's a number of sort of escape acts？

You can pull off to go down that path， you know， how do you deal with the spec that you'd have to have a massive explosion of cases？

So one of them is。The hint， at least for how to do this comes from the paper only a couple of years after the first one calledIndirect threadic comb。

And the trick here is like all computer science tricks， which is the interaction。

So instead of having to pointer directly to the action routine。

 they will point her to a little chunk of memory。And the trunk of memory contains a pointer to a getter and a setter and the value of the variable that it's getting and setting and now instead of jumping here。

 we jump through here to here。And we could share these things depending on where what our program is trying to do。

 so this example is doing B equals B plus C， so it points to the getta for B。

 it points to the getta for C， it points to the haveer， and then points to the setter for B。

One way of thinking about this。I you can think of these as objects right this is the meme for an object。

 data and code point us to the code for the routines for the object。And if you bear that in mind。

 that will solve an additional problem。So this is the sort of schematic of how this would work。

You have now the。Your code is pointers to the appropriate gasters and setters， but not directly。

 indirectly through。Through those data objects， so for each variable you need a separate couple of words one pointing to the get and one pointing to the center because these are you know this is I'm assuming a st machine there there's just a pair for each and these then point off to the routines that are shared by all of the variables and assessment。

And the ones that don't need any data are just of the interaction point。

the appropriate action routines and now the threading says， you know grab the pointer， load that。

 go to the target， this is the code here， load that and call the a thing that's a point in table。

So it's a little， this is now， this thread is now。A little slower because we have an extra load in that。

 Well in some machines， this is still one instruction。Just depends on your address。

Now there is a problem with this。It's fine for Fortranran， Fortrann of 1975。

 because for the Fortrann of 1975， and only two things more or less it had statically allocated variables。

And he had a raise。And that was really it right， there wasn't a stack because you couldn't call the recursion wasn't the allowed。

Every。Function could have its variables allocated at fixed addresses known at compile time。

And so this is great because for that， because you could just make each of those locations instead of being one word。

 three words with the getters and the set and you know who cares about an extra two words for every variable in your program。

 variables just are not that common， right， code is much more。Bulki variables and for the arrays。

 you just need a get or in a set which takes an index as a parameter。

 so you're passing an indices through some convention。

But if you think about doing this for a language where a functions stat。For example。

 our methods stack， it suddenly gets a lot less appealing because now when we create a stack frame。

For every data slot in the stack frame next to it， we have to a point it to a get and a point it to a set and we have to fill that in when we call a function。

Which is not so appealing So the trick to get out of that is you know use this observation that I mentioned earlier。

 which is think of these things as objects right we already showed how to abstract behavior out using the map。

 put a pointer rent to something else。And。We we can make these be anything we like when we're doing the implementation right。

 so this could be a stack frame as long as we can somehow pass an index to see which。

slott of the stack frame we've got， and now we're only putting two pointers in post stack frame rather than two pointers per variable which is much more attractive。

So at that point， really， you end up with。You have to change your instruction set。

 but remember this is a generated instruction set， it's not the original bycode。

 we can decompose what we execute into smaller pieces if we want， so for example。

 instead of having a branch to offset end bycode which means we'd have to have N action routines depending on the field width of that upper end。

 we can just push N onto the expressions deck and use that as the parameter to a single branch bycode that takes that from the expression step。

Now， as we add more indirect。And more of this stuff。

 we' sort of going to farther away from the original high speed。Implementation。

 so now this is where things get sort of very sensitive to the specific implementation and the specific architecture and the specific organizations it's harder in a scheme of this complexity to say this will be a win right you might through all of this extra stuff you have to do you might get lose what you gained earlier。

So that's that's why this， I don't think I've ever seen an actual indirect threaded implementation。

They're pretty obscure in these there。So this is what the bikecode would look like instead of。嗯。

You know，Bt push local free， we'd have push a three and then。

Get the local whose index is on the state。But we didnt end up with a system in which only mutable sta is in data memory。

The code itself can be in affixed。Built ahead of time binary， even in a realm， which。林point。

So friended code。Even though it dates back to the mid-70s。

 it really gained in popularity with its adoption by fourth， which I think dates from 78。呃。

How many people are familiar with Forhand？Okay， a sprint claim was once upon a time where like everyone in their room would have raised their hand because it was extremely popular in the 80s。

It was developed by an astronomer for a way of controlling these radio telescope writing programs that would be easily modified and yet run with reasonable performance for which the compiler was more or less trivial。

And it caught on really well in the 80s， and then the technique was adopted by Adobe in the Postscript language。

 which is， you know what's inside every PDF。So every time you。You render a PDF。

 you're running more ugly than not running a threaded code interpret， In fact。

 if you're using the Go script implementation， you're using Peter Deuts's threaded interpret。

If you haven't seen postric， it's kind of fun， it's a little wacky mind bending when you so once point a time。

Before things like。呃。Printer drivers were common， we used to handr this stuff。To make diagrams。

 so this is actually code lifty Da from a postscript file。Of mine from the 80s。

 which is part of a diagram for a paper。 This is how you drew a diagram in a paper that you were going to laser print。

 You wrote a program to render the diagram by hand in post rate。

And so this is the things where the slashes are symbols。

 so they're just pushed onto the stack as pointers too of the underlying atom that contains the string and then it's the left to right you know。

RPN type evaluation。 So so this， if you call cold size， this is， this is a definition。Of a function。

 right death defines that guy。 the percentage of comments。

 So this is it has to be heavily commented because you don't write comments。

 You can't figure out how it's doing even 10 minutes later。So this is taking four and5。

 30 seconds and multiplying them by 72， which is the unit of coordinate system in proscript Pi。

 sorry points。72 points per inch that's how I get four and five 30 seconds of an inch that gives me an inch and then this is a longish method and after every line I write a description of you know what that line is going to do to the stack。

There's a comment to figure out what's going on。And it's you know those divides and multiplies and variable fetchs and then calls into the graphic system might moved to。

 which is moving the drawing point in the coordinate system。And。Yeah， it's， it's kind of fun。

When I was a grad student， the fastest machine we had was a laser printer。

 the processor in an Apple laser writer was faster than anything else we had on our desk。

 so some people actually ran the programs in the printer。😀ふ。

A friend who wrote a theorem paper that ran the printer and then printed out。それ。对个。But it is。

 you know， it' it's a little sort of mind whoing to write lots of posts， but it's very media。

 especially if you're talking to the command line of the interpreter。Okay。

 so that was walk technique， let's move on to the next。

So the next one is called stack caching and the idea here is to try and exploit a phenomenon。

 which is that in a bikecodeed stack machine， most bikecodes are doing something to the top of the stack。

You're either getting it or you're writing it or you're doing an ad with it or you're putting something back or whatever。

And that means if you implement it in the way you guys have probably done it。

 that the top of stack is， you know， a location in memory indexed by a variable。

 you probably you're offsetting to it an array， which means you're doing the load in a store every time you access that thing。

Well， one of the tricks you can do its dad is to say， aha。

The top of stack is not going to live for where it should。

 and it's going to actually live in a register。And the rest of the stack will live where it should。

 and then you rewrite all of your code with that assumption。

So you rewrite your bikecodes to use that registered directly。

 so an ad instead of doing a pop and a pop。And then in addition and a Porsche grabs the register under does a pop。

 and then in addition puts the value back in the register whos going register to register at the top of stack。

And again， there's another one of these things， which is darn difficult to write express in a high level language you tend to have to write assemblyly or generate assemblyly。

没有。There are a number of variants of this which will come in， one is that？

Most hardware were politicians it's register set so that there isn't any single good place to keep this off of stack。

Because if the top of stack is an integer， it wants to be in an integer register a floating point number。

 it probably wants to be in floating point register。

On some machines you might even have separate registers for addressing and memory operations and then like well。

 where do we put it， there's really no good place。What you can do then。Is you can。

Put it where where it sort of wants to be and track that stage in the code。 Now。

 the easy way of doing this is by having some state variable。

 But then you have to test and set the state variable。 and that's wasting time。

 a different way to do it。Is to actually change the dispatch table to reflect which state you're in。

 So so you know， if you can't infer stay from the bycode， which in most bycodes， you can't。

Even in Java， you're calling。嗯。You go down this other route。

 which is to have multiple dispatch tables。 So again。

 you currently probably do your dispatching through a switch staman。

 but in asem what you probably do is have a vector of addresses for for your dispatch or threaded coat。

That's that's doing the dispatch。 Suppose you have the vector of addresses。

 which is indexed by bycode， pointing off to the action routines。

 where you can have multiple one of those laid out such that there's an index。

Pointing to which is the current Bcode dispatch table。

 and you change that as according to the type of the thing that's the top of the stack。

So suppose you have two du bycodes in the Java file。

 one is known to dupin in and the other ones duping aflo。How do you know that。

 well that's because the thing that preceded the du。

 first du must have pushed it in onto the top of the stack。

 the thing that preceded the second you must have pushed the floor onto the top of the stack。Well。

 when each of those executes， it can set up the dispatch table。

 the first one would point to the dispatch table assumes the top of stack is in the in register。

 the second would point to that dispatch table assumes the top of stack is in the flow register。

Dianagrammatically， it's like this。So these are the dispatch tables。

 so if it's by code it'd be 256 entries。Each of the entries would be appointed to some code that's executing the appropriate action for that bikecode。

So this is Cine table， that's the FP table If we look at say the addd column， which is this one here。

 there'd be an I addd here and an F ad， sorry。M， you can know that if we look at， say the du column。

 there would be a。Dpe bycodes in each of these， but the behaviors are different because we know ahead of time。

If this guy is going to dupe an in， then this guy is going to dupe a floating point number。

So what we do is in the ILO code， because we're currently in the case。

where we're in the in top of stack when that guy is executed。

 it's going to assume the current top of stack is init so has to push that aside onto the stack and it's going to load the variable。

 put it in the in top of stack， but there's no state change because we didn't change behavior。

If we were in the FP state， then that would have to。

Spill wherever it keeps the floating point off the stack to the stack， it would load。

The value of the variable into the endtop of stack。

 and it would change this point in there the point to this table。And next time。

 we would dispatch through the other table and the duplicately code would assume that the top of stack was in the right place and with the top of stack register。

I'm not sure I did a good job of explaining that， you get it。Yeah。

 but so it requires this pre analysislysis to convert all your dupes into either。 No。

 not necessarily。 that helps。But you don't have to。Because in this particular case。

your du bikecode is the same bikecode， so it's indexing into here。

 it's just going to pick up the right one。The pre analysislysis only helps if they don't line up nicely。

So we've got two behaviors for Ilobe zero for the two different cases。

 we've got two behaviors for de。Why isn't there a second behavior for A？In the floating point vector。

Why do I have a pointer in that box？Yeah， we know by the prophecies of the bikecode。

 we can't possibly be there。Executing an Iadd with a 1 floating point number on the top of the stack。

So if you look at something like Java Bcode， how many extra opt codes are you？A you。Well。

 you're basically taking all of the types。呃。You're multiplying by how many different caching。

Vance you have I mean you have to fill out the matrix for all of the legal possibilities like this isn't had legal possibilities。

 but most of the possibilities is legal the preponderance so and these are all now going to be specialized based on that behavior many of which are going to just be you know I've got the wrong thing I'm going to switch to another step I'm going to spill something to this do what I would have done and then push the new thing into the new location So that's going increase your code Oh yeah absolutely。

Yeah， but cash is are big。At X86 could translate。Essentially risk。

You mean trace cash cash is one thing， but the white progress is 1500。Yeah。

 you're probably below that， but I can't imagine a Java。Interpreer would really in that out of space。

 anymore。it's not clear we get how what was。Yep， so if you assume something like Bfur verification has happened ahead of time and I'm not mistaken and you can even figure out when Duke construction is seen in that's J JV。

 that is going to be duplicating in approach because you put the handle then couldn't you instead of having just one entry for the du bytefoot。

 right？Your bikecode might be compressed because you want more clothes sizes but then when you're if you can expand it。

 if you can expand the bike into you know the problem is that the thing is already failed。

 if it's packed， then there's nothing you can do if you have spare entries here and actually there are some spare what's in the Java bike say you could reuse some of them by rewriting an in a generic dupe into the tight du flavor。

If you really wanted to， but the nice thing here is you can make this one point to an arrow。

And that means you sort of get an extra level of redundancy behind your verifier。

 that means that even if something got through the verifier。

 it would not attempt to do a floatingir point out on an in。好快。O。So that's trick number two。

The generic set of tricks number three is make in each bikecode do more so another way to reduce that overhead is to have more work in between the parts that are all overhead so you sort of fatten up the bikecodes to do more work and in some bikecode sets there are already instructions that do a lot of work if you look at small talkadeing for example。

 many of the bikecodes like Java bikecodes they're just stack manipulation there's nothing much there。

But there there's one， actually a small family of graphic blackcodes within underlying one being a bit b。

 which is a bit boundary block transpo in from the Xerox Alto。Many years ago。

 that basically takes some rectangular chunk of a bitmap。

And copies and blends it with some other rectangular chunk of a bit map into a destination and you know that's how the screen is filled right one instruction fills the screen with gray。

So you know that instruction， the interpretation overhead really isn't important because that thing's going to touch you know a megapex a lot more there isn't an extreme form of this just turning your entire program to single bycode yeah。

But you have to then generate a VM mix excuse that whole you know。

 you need a different fan for every program then which mean you generate assembly then。D。如讲你咁快嚟啊。

traditionally there's actually two instructions they're called solve problem print answer。Yeah。

It's almost a risk。Yeah， now now there are these things that already do a lot of work。

 if you another example a better example actually is R and especially it's predecessor has。

which was designed20 years more than 20 years ago， the idea there was that the statistical language would basically just be a glue that would wrap around a bunch of stats operations on vectors and matrices。

They were written in fortron and CNC++ and all the performance was in those things。So the glue。

 kind of who careed what the interpretation overhead was if an individual bycode was you know calculate some statistical property of a megabyte of data。

 ala， things have not really worked out like back over the years。

 but the performance of the interpreter actually is much more important because surprisingly enough。

 people would rather write our code than forran。ま。我 shock。Now there's a way of actually doing this。

Semi or even fully automatically， the technique given to the name is called super instructions。

So the idea here is to synthesize。Bigger or fatter instructions from common sequences of smaller ones。

And you know， you start typically by getting some big corpusive bikecode programs and the brain and analysis over them looking for common pairs and triples and those things obviously I have to be entirely content within the basic block because you're not going to be able to jump into the middle or out with the middle of a super bikecode。

So you look for these pairs and triples and quadruples and you know， however many。

However long sequences you are， and you statistically analyze which are the most common sets。

And then you can either by hand， go in and modify the bikecode compiler and the interpreter to omit and execute those things if that's a possibility。

 or you can take a single pass over the original bycode sort jamming the patterns together just before you execute them for the first time。

 either way it works。It's kind of tedious to do this by hand。嗯。

So an example might be push local ink pop local that's probably a very common sequence in any bycode set of any language。

 you know， increment variable。Well you could replace that with by a single new instruction called ink Lo。

 the dissolve for a all in one go when you could encode that name。

Match on those sequences and emit that thing and it's kind of the opposite of the risk right you're trying to make the instruction set fatter and heavier because the dispatch cost。

 the decod cost is more or less constant even as you know you go from hundreds to thousands of instructions。

 it's not really a big deal in software， but you get more work done in each of the outcomes。

There was a whole bunch of papers written on this。嗯。Around the early 2000s。In fact， there was a big。

Sort of wave of interpreter tweaking and improvement from the mid-90s through the mid-2000s。

 mostly done by paragus in Europe， Anton Ertl and David Greg who coroll papers。

 so you'll see Er to and Greg as a common。Com on hair and they did a big thorough analysis of what this technique and。

And all the other techniques and figured out， know at least for their languages and their implementations。

That they had。あ。You know what worked and what percentage？I have to get 10 or。How。So the。

The next one is like kind of a combination of that and threadtic code。

And this is called rather blandly except selective inlining， this was actually。

 it was first described in a paper。By a former student of mine actually in Pita and his colleague then Faabon Ricard in 1998。

 it was independently invented by the initial hotspot team and implemented in the very first hotspot system and there they called it snippets which also is great end because it sort of means many things to many people in that。

The term has been reused in many places so there isn't really a great name for this。

 but the canonical paper is this one on selective inlining the idea here is it's sort of like threaded code except instead of replacing one by code with one pointer to an action routine。

So're going to replace multiple bot codes。With one pointer to the action routines all concatened together in。

And thereby save on the threading between them。The best example of this is actually in the original paper。

 so over here we have C code for a little table that's pointing to three op codes， push three。

 push4 and add so this is doing the  three+ four and you can see the C code of the interpreter which is the usual kind of thing a switch statement。

 a little bit of code for the action routine and then some macro that's going to go on to the next one。

And what the rewriting system logically does is it transforms this into this。

 takes the action bodies out， jams them all together。

 and then does the normal dispatch at the end of that routine and it has to rewrite。

The threaded dispatch to skip over the ones that know are no longer there as individual instructions anymore。

 because now you've replaced what three instructions in the original sequence with one。In the。

In the final sequence， there are some restrictions on this。Firstly。

 if you're going to be doing this jamming together on concatenation。

 obviously the code you're copying to do the concatenation has to be real oable。

 but otherwise it's not going to work， it can't contain relative branches outside the sequence because they're not going to work either。

The control flow changes can only happen in the last form if。

 but if there's go to kind of in the middle， there's kind of pointless have it in the middle one from a sequence。

And the top branch targets have to still be viable branch targets at the heads of sequences。

 so one simple way of restricting this is only translate basic blocks at a time using this。

 but you can you know if you get lucky， you get one basic block it's translated into one instruction with the code。

Associated with that action。 And because it's such a fast technique。

 you're just generating threaded pointers and concatenating regions of memory。

 you can throw away the code fairly。You know lightly because it didn't take a lot of time to generate so you know you could turn over the code very quickly if you really wanted。

 you don't have to amortize the effort of generating over many。

 many executions so in their implementation and also the hotpot one they're cached and reuse the generated macro op codes so what you want to do is once you've generated one of these sequences if you can find the same sequences again you you can reuse it as long as you're careful。

Now all of these techniques。As I said， it's pretty much impossible in a high level language。

Even in C which is barely a high level language because you have to control so many levels so if you look at the way things have been done in the past。

 typically the approach is either to write a generator in a high level language that sort of builds the interpreter and mix it。

As a gl of machine code。Or you invent your own DSL in which you can capture。All of these things。

 and then of course， then you still have to write a generator it for your DSL。

 but presumably it's not quite maybe not so quite as coned as it was in the first place。

And there's a really nice one that came out in 2002 again from the Itle and Bgg crew called VMG。

 in which they sort of invent their own DSL and they build a big system in which it can express。

 I think all of these optimizations and know。Spits out a piece of。Pce of code that will that will。

Do your interpretation。The other approach of having a generator is the walnu's used in Hpot。

For those of you who've looked at hotspot， there's kind of both flavors。

 the generated and the static， but the generated one is like the the version， the static one is this。

Swe them under the carbon thing。I don't think it's maintained or supporting or anything about that。

But the generator one has been there since the early days and it does a lot of this stuff。

 it uses stack caching， it has different states for the various different JVM types that can be on the top of stack and it has dispatch tableables。

Per all of those， it's written in C plus plus with templates， so it's kind of everything on。

There's an adventure in doing the C++。It doesn't directly compile the C++ into the interpreter。

 you know when you build a VM， when the system bootss。

 an internal generator sort of reads these descriptions from the C++ code and emits the associatedci action routines。

 so the C++ is kind of thin like disguised assembly language and it can do clever things like if you find you're on a pentium 6。

3 or whatever the flavor is with a foodbar instruction。

 well now you can use the throughbar instruction if you really want to。

Because you know which machine you're on， whereas if you write one and you just distribute a binary ahead of time。

 you have to be used typically you're sort of in the lowest common denominator model。

So it does that too， it used to do the selective inlining trip， they took it out。

 I'm not entirely clear as to why they took it out， but would be。

We can table that question for when the law is random。Okay。

 so final word before we take a break is you know all this stuff will definitely speak up your interpreter and there are you know a small number of other。

 I think marginal techniques which are in the literature too。

 which are worth knowing about if you really really want to squeeze out the last， last damn speed。

 but you know， I don't think any of this will get you can remotely close to where a decent compiler will get。

You can get fairly close to a simple j， fairly close。

But you'll never get to anything there's a any decent level of optimization。

 so after the break we'll make a start on compilation which I'll take。Several which probably。

Any last questions before we break。One of Anti papers made this claim that。

The difference between expected。ございます。A Naive jit that just copies these segments is all in controlling the branch。

是留单。Yes， no， it might be true on some specific microbi is actually。嗯。If，If you can。

If you can play games and max the bru， predict it carefully。Yeah。

 you can get performance of a really good interpreter that approach is a really bad yet。有很多。You know。

 it's really hard when each has equal effort pull him。To make them。Live parity。 that's。

 that's my take on。 I mean， there there are all sorts of bizarre things you can do。

 One of the things we did。 So， so I worked on。The pre hotpot。

Sn JVM that was shipped on Spark and Solars， which was a cob written in C。

 the interpreter there was handwritten in asemler。And it was carefully written such now。

The branches or the action routines laid down in the eyec so that there were no bad eye cash conflict。

Right because you can put many address， right there's just a table pointing to them so you rearrange memory everyone was aligned on the appropriate boundary front to at the beginning of a cash line and the analysis was done to say。

 oh， these two are common。You know， pairs， but they'll land on the same cash line。 Let's。

 let's move this one to a different address。 You know， so you can do。

 you can do a lot of work to try and， you know。But that's specific one specific chip。you know。

 and that's not going to， that stuff isn't going to work on the thing that follows out of the thing that precedes。

 it's a lot of work per thing， whereas a compiler is just like this bigha ironing。빨我知道。No。

 but he doesn't need it。It doesn't need to， it's going to get be several times faster without breaking a sweat probably。

So you know， that level of fine tweaking。Just这是。Just isn't necessary。So。

In the context of interpreters， there was one technique that。Was hoping to see it。

 I know it's from the company that shouldn't mention and stole some stuff。The other code。Generalizes。

All of these interpreters， all of these pcodes were kind of like。And。

St so he uses a register it the 90s when when the weren very very register。

I would argue that there were plenty of registers on Spark， you know， when Java was invented。

 the reason stack machines are adopted is because it's neutral it doesn't that's why they were adopted。

 but why we。Because once you compile， it doesn't make any difference。It's as good an IR as any other。

 really。So going to all the bother of trying to do register allocation in the distribution format。

 only to have to do it again when you find out the real machine and how many registers its really gone。

他户外包的。M relocation isn't free。And you're doing it at one time。Yeah。

 but we have to do it at runtime anyway， because only at runtime， do you know what you're on。

If you're not distributing a binary， you're only going to discover the underlying architecture at the point where you start executing it and you have to make your decisions at that point。

You， you could argue。 and there were some studies done that said， okay， let's。Let's devise an IR。

 that's an infinite register thing and we'll prioritize them。

 So the thing we want most to be in the register will be in register  zero。

 then the next will be one and the next in two then when we。Generate machine code。

 most of the work is done for us， we just take the first hand and put those in registers。

 I mean you know， no difference but not。Oh much not when you're compiling because there are all these other issues that you have to deal with when you're compiling。

那来。买家水就我跟呢个。Okay， well， we'll change that。掘ってるちすす。嗯。Okay， let's take 10 minutes。我。Make sense。

They argue that their relates。はロレです。对。那我点。It's kind of amazing that I took lot of the course together get this。

Because when I envisaged this course， I thought I'd be there in week two。So。All right。

 so some apple pie。We need to get past interpretation right if we're going to get more performance。

 you can whittle away these few percent these techniques。

 but as you saw from the interpretation techniques you get more and more machine specific and microarchitect specific and you lose some of the advantages of port and things so if we're going to get performance。

You have to break out of this one at a time mentality and go into compilation and compile a whole bunch of stuff at a time and that will give you once you put your hands around more of the program。

 then you can figure out more what's going on and take advantage of the behaviors。You know。

 and special special care， you know， compilation is it can be expensive。

 but the goal is to try and amortise the cost of stuff that's being executed many times it's generally not a good idea it compiles stuff that's kind of。

Rund onces are a few times very hard to build a compiler that will win in that situation and other stuff that's never run is。

Never不。Okay， so why are we doing dynamic compilation。

 hopefully this' is all fairly obvious you know the world is。

Seeings dominated by static compilation of binaries and these reasons should all， I hope be obvious。

 you know a binaries are notla。You hard to verify for security properties for some languages you might not know enough ahead of time to be able to generate good code because of the way the language is designed。

 you they're big， you end up compiling everything， you it might never be executed and the encodings are often not compact compared to bycode there's always GSE。

Some other advantages， a little more elusive， but nonetheless。

Real one is that you know when you're compiling your program is now running right you can look at the actual data that are being manipulated and you have you know the pieces of the program if it's fits you know like Java with class loaders and dynamically assembled from disparate sources well the only time you get to see all of the pieces together is at that point。

When the program is actually running， in fact， sometimes not until the program has been running quite a long time。

嗯。And you also know things like you know the specific model of the CPU you're on。

 so you can select model specific instructions I imagine earlier you know the size the memory you've got。

 you can know the structure of the memory hierarchy all sorts of tricks here this seam has been relatively likely mined from the point of view of dynamic compilation most of the low hanging fruit has been elsewhere in just trying to figure out how to get good code。

On sort of the generic processor and mining this kind of knowledge is still fairly open so you know any if you have an interest in this。

 this a be a good direction point for some research。

Especially in conjunction with people who are building machine。Okay。

 so we have a bunch of actually there are many， many compiler design choices and I'm certain that I'm not going to enumerate the entire list。

But I'm going to make a size start on these and we'll cover a few this time。

We'll see more or less but you know one choice you have to make is what's the unit of compilation。

 what are you going to compile or when you compile something。

 you want to put your arms around some piece of code， how big is it？我不知道会是。

But basically but generally speaking they're too small but just isn't enough there to do anything useful with them。

 you don't see enough going on to really get some good optimization opportunities this is fine for you know the selective inlining technique that I described are a very very。

 very simple jet， but beyond that sort of just doesn't seem to be enough。

So a method or a functional or whatever。Whatever your programming language naturally decomposes to is a better place to start。

 but of course the variety of grain sizes there is immense right。

 the smallest methods might be just like itself a variable。And they might be really big。

 so that still has some problem， the method of high compilation you might not be seeing enough to do something much more interesting and where we're going to get to hopefully next week is many methods all related to each other via the call graph and potentially in lineable because now you can really get your teeth into something worth compiling a whole different branch。

 a whole different fork of compiler design is compileiling traces of execution so this is the idea that you watch as the program steps through a bunch of instructions you know and you gather that list of instructions and it can span methods it can span loops。

 it can do all sorts of interesting things you gather that thing and you do something to compile that trace which originally will be something like a bikecode trace into a machine code trace trace compilation is quite different。

In many ways from all of this， it has its own sort of literature and topics and I'm planning to get a guest speaker and is Israeli expert about this。

In a few weeks。So I'm not going to say any more about trace compilation until then we're going down the other path of compiling methods or。

Groups of methods。 So another important distinction and probably the one which you。

Maybe more familiar with。The previous one sort of people just take is granted that it's going to be a method often。

But the more explicit choice， which is。Present it is when， when do you compile。

 you can either and Ive broken， you know， into。Into three， there's actually four here。

 I'll guess of that。One is you compile ahead of time。And before your method executes， you know。

 there is a long time there it can be any time between the program being written。

And the program being executed and that typically where it's written is not the same place where it's executed。

So it can be compiled by the developer at the developer side。

 which is the traditional static compilation model， but it can also be compiled ahead of time。

At the application site， other rooms， other customer site， so for example。

 compiling at install time is an interesting choice。嗯。

You know you can compile Java code at the point of which you finished loading a class， right。

 you haven't executed anything。Yet in that class you just will load to that。

 you don't know what you're going to execute， but you can go ahead and compile a few want。

So that's sort of an interesting choice point。嗯。There's also this。

Second choice just in time and that to me has a very very specific meaning and I will describe that on the next slide and it excludes these meaning。

So the other just in time means compilation triggered by the first execution so you get to some piece of code and you're just about who executes and well we know we're going to execute it now so it's not a complete waste of time to compile it it's not like compileiling something that's never going to run because you know you're going run it at least once and you compile it at that point and of course you have to wait for the compilers man before you can execute the compile code。

The other end of the spectrum is to let it run once or many times and then do some compilation and the advantage is there。

 making things run once often。Clarifies a bunch of information that might be uncertain before the first run。

 So in job， you've got stuff you're going on called Resution。

Whi if you try and compile a method that hasn't been through resolution yet。

 you're in a world at heart because kind of come across a piece of code and you just have no idea what it's going to do because you haven't resolved what it's referring to。

So many compilers for Java wait until resolution to been performed before doing a compilation。

 there are other languages that have similar things where the first execution tells you something that you couldn't have guessed before the first execution but you don't even have to wait for a second。

And then you'll see especially next week that you can wait a long time。

 many executions to gather information about the program behavior and then do a compilation and of course these are not exclusive right you can be doing compilation and recompilation over time and we'll get onto the techniques for that as though。

Section progresses。 There is a fourth choice， which of course， is never。You can， you can。 And that's。

 that's。That's sometimes a good choice， right if you know something's only going to be executed at once。

 like a static initializing a Java class file。Probably not a good idea to compile that。

Or sometimes you look at a piece of code and it's like it's just too bad， it's too hairy。

 it's too big。The thing about building a compiler in this environment。

 if you have an interpreter you put to fold back on， is that a compiler does not have to be complete。

 it doesn't have to be able to compile everything because you can always punt to the interpreter if you really want to。

Or if you have multiple compilers， you can you know。

 there has to be one level of execution that's complete that does everything。

 but the others can just throw their hands up and go ah， it's too difficult， I give up。Okay。

 choice number three is the level of optimization and the stuff we saw earlier was really I think interpretation because we were doing same thing for each bikecode that we would have done before so minimal compilations like macro expansion of bikecodes if you do a little bit of people optimization then really then you're doing compilation and typically in a simple just in time compiler you're doing something in this space。

The register management is kind of done by hand， you preallocate which registers are going to be used for what purpose you don't run a register allocator or the code later you kind of have some convention as to where stuff lives and you just follow that convention many things might still live on stack and not in registers but it's easy to write it's fast to generate the code and you know it's good at eliminating the interpreter of the head which is the first limit if you want to go beyond that well then the list is。

Very， very long。 And we'll see some of the elements of the of the list in the coming weeks， but。

This is another fertile gra for。For thinking now I'm going to， this is my opportunity to rampt。

I have had this rant building me for 20 years。Which is that around the time that Java appeared。

 this term just in compilation suddenly popped out of thin。

 if I ever find the guy who invented this going to kill because it's the worst term。

I've ever seen in that it's not only wrong。Not not only wrong in that it's actually not descriptive's that it's also universally misapplied or it shouldn't be。

 So， so it's not just in time compilation， right if you look back at the term the origin of just in time。

 it comes from the Japanese manufacturing and Toyota and that stuff how I have this book。

 This isn't just an ending。And the idea in just in time manufacturing is at the point where you want to assemble the thing you're assembling via a car。

 all of the parts arrive just in time for that action。In just in time compilation。

 we don't compile just before the first execution， we don't know when that's going to happen and just arrange for the compiler to start its work so it's ready。

 we start just too late。We're starting at the point where we know we missed the boat。

So that's not a good use of the term also you see this term absolutely universally misapplilies to every form of dynamic compilation under the sun and certainly compiling a thousand executions in is not just in time by anyone's definition so I hate this term。

I hate the use of the wordJit as name， if anyone uses that in anything they give me written you will fail the course instantly。

I have a concrete compromise suggestion error because I've been ranuting on this for 20 years without much success and here's the suggestion I have。

 which is to use the termJit in lowercase now as a new noun。Because it's English we can invent nouns。

 so this is a new noun， it's law case， and it means dynamic compiler。

It has no relation to JIT in uppercase。And if you guys ever go into research and write papers。

 I hope you start using this and if anyone pushes back on you from the referees you say。

Justify the other use。Explain why J just in time has a noun makes sense or this particular term makes。

 looks a lot like git。So the appeal of the word as a noun is you know， it's a simple syllable。

 single syllable iron that of done now mean compiler right it's a long syllable rather than sex which is gray and you can type it quick。

I capture that advantage， I embrace and extend this tone， so the alternative might have been lazy。

And lazy doesn't sound very good either La doesn't sound good Yeah hard to go to your manager and say I want to start a new project in Laziness。

はははは。嗯。Yeah呀。I actually my research group used to be called the Kban research group and people thought it was because we did compilers。

 it's just that we well this is how we lived our lives doing things at the last minute。😀。live choice。

 so ran over， thank you for listening。是的。So the jet compiler eliminates interpreter overhead that's。

 the big advantage， that's what know Peter and Alan came up with and why it's you know。

 caught on in the last 20 years to nearly 30 years since then。嗯。So more than  first0 years。

So we end up， we decodebon by code only once we generate code， there's no interpreter loop。

 and there's no other， you know， there's no thread to dispatch or any other form of dispatch。

 it's just code。So that's great。嗯。In a simple J compiler。

 a resulting code can be no more complex than just the interpreter actions glue together lies in that selective thinlining case。

But it's usually worth making at least one pass over that just to eliminate very simple people inefficiencies。

 simple， constant folding tricks， just a bit beyond。嗯。Macro expansion， so。

Why does this work there's a very simple model which you can build so this is。Number of executions。

Over a time of。Of a piece of code， then here's the time。And the idea is of an interpretation。

 we're doing the same thing every time， so it's linear right， one execution costs。

 one unit to execution costs， two units， three， you modular。

 micro architectitectural effects and caing and branch。and all that。

 but more or less if you you actually do this， you've got something that's pretty close to a straight line。

 you know it'll be noisy， but it won't you asymptotically go this way or up， right？

Will be more or less constant。The idea with compilation is we're going to invest some time in your compilation。

 we're going to invest some time upfront to do some compilation。

 but the code we generate is going to be faster so after some number of executions we break even and after that we're ahead。

So the important thing is， you know， where is this point？

How do we know where that's going to be and we got three parameters。

The speed in which we can interpret the cost of a compilation and the speed of a compile code。

Now in the real world， life is complex and there are millions， you know of， well。

 that's an exaggeration， but many。You know， confirmfounding effects。

 but there's a nice simple way of cutting through that and abstracting over it。

 which is we're going to think of the average bycode and think of everything in terms of that so the way you do it in practice is you find some benchmark suite that you think is important。

 you know so if you're an academic you find whatever it is that that's widely accepted for publication。

 if you're a commercial company you find youever it is which benchmark suite is considered good marketing。

You know， if you're an actual user， you run programs that you care about。

And then you measure the performance across those benchmarks we subtract now it starts getting to be hard work。

 you have to subtract to all the stuff that isn't execution like GC and native code。

Other stuff that might be going in the runtime， but it is possible to do this and you end up with the time it took to execute the bikecodes。

And you simply divide that by the number of backcodes that were executed， you know。

 you put a counter into your thing counter the path length， if you have threads。

 you have to do a little bit more sophistication to deal with the threading。But you can。

 you can measure what is the average bikecode or， you know， millions of billions of them。And。

Rather than counting time directly， a common thing to do is to just count clock cycles。

That really gets from the time when。Clock speeds were changing quickly。

And so if I report it time this year， next year， it would be half the time and the time year after that it might be a quarter of the time。

 now like it's not really so important to do this， but you'll find papers in which stuff gets normalized clock cycles so I'm going to continue that direction。

So we have three metrics， which。The three I mentioned earlier。

 the time it takes to interpret a bycode measured in cycles。Time it takes to compile a bycode。

 time it takes to execute the compiled code for that bycode。Okay。

 and then you can boil that down from three to two by taking just ratios。So in this case， I have To。

 which you can think of as translation time， so the time it takes to compile the bycode relative to the time you took to interpret it。

And execute， which is the time it took to interpret it relative to the time to to execute the compiled code and both of these numbers。

 ratios are chosen so that they should both be more than one。

So if you get out the back of an envelope。Do a little arithmetic， you end up with these。

 this formula， says the break， even number of bike codes。Is。

Compile time over the difference between the two executions or in terms of the ratios。

 it looks like this。And。Is an example， suppose it takes one clock to execute the bikecode compiles。

 two clocks to execute it and interpret it， then10 to compile it。

 then tau is5 because 10 over2 is 5 row is 2 to01 and the base of the break even point is 10 so we need to execute in this case 10 times before we're a break break。

哪了。Maybe doesn't speak to have the curve looked。 So I plotted the curve， which give me some idea。

Of the range。 and this is kind of covers the typical space of implementations。

 So on this graph I've got。The Im plotting the logarithm of the breakeven point on the Y axis versus the。

Compile a speed up over interpretation， right， although it's inverse rather it's interpreted over。

Over compile it。Relativeivity different curves of the translation time。So you know。

 if you could write a compiler that compiled in the same time， it took to interpret ws。

 then surprise anyway。You know， you get your investment back really quickly。

 but you know that's unrealistic toys one is， you know you can just treat that a as a band。

 but it's not unreal realistic scenario even toys too is probably not achievable in many systems。

Generally speaking， but as you can see as the compile time goes up。

 the amortization time also goes up。And as the speed of the compiled code approaches the speed of the interpreter。

 the breaking point or shoots up so if you're in compileries。The same speed。

 the compiled code is the same speed as the interpretive code。 Well。

 then you'll never get your compiled on back。 So there's this accident terms。

 you want to stay out of this region。 your code has to be minimally。You know。

At least some faster than the interpreted code and you want to try avoid having the really long compile times because it's just going to be。

You're going to end up spending time compiling stuff that you don't。

 it doesn't get you and it's anything back。 Yes， isn't this a largely a function of。Grannularity。

 which you file， you compile just one by code instruction versus 10 versus 20。

You mean you mean the red， surprisingly not。Meaning if I choose to file 1 versus file 10。

 I can do other optimization like register allocation that's better if I compile several instructions to have。

Well so。The way to think about that in terms of this model is if you're doing more optimizations。

 you're moving up。On one of these curves。 and you typically think about having multiple curves。

 depending on the level of optimization， that might even be embodied as multiple different compilers right many of these systems have two or more compilers。

So yeah， you would change as you're doing more optimization， but for something like a simple Jit。

Module of the startup time to get the compiler going。

 the rate at which you compile whitecodes is almost independent of the number you compile or the complexity of the individual bikecode。

 certainly averaged over a large， large set and it's， you know。

You can elaborate this model with all of those details if you really like。

 but this is just a good simple way to start thinking about things。

So you can turn this round into a different picture， which is speedup。Okay。

 so if a bycode is executed n times。And the speed up is given by these formulae。

And now for any individual N， you can plot this curve。Which gives you the speed up relative to。

To end。So in this case， a logarithmic scale， one is breakeven。 So for these particular parameters。

 if I execute 125 times， this is a sish compiler to 100。In fact。

 execute 125 times I' a break even it generates really good codes。

 it's five times faster than the interpreter， asymptically it'll reach five， any less than 125。

 you know， I'm wasting my time， I could have been doing something better。So， this is the。

This is the game。 Yes， times is better goals。可。So it doesn't tell me about how expensive。 Well。

 a loop， you can call the method once， but it can move。Right， so is it times mes or well。

 this is at the bikecode one at the bike。So if you call a method once。

And it has a loop in it that runs 10，000 times then the 10000 is what you're compiling for。

 you sort of wasted your time doing the prologue and the alogue。

 but you know if you compile the granularity is a single method， you have no choice。Okay。

 let's look at。We actually comp because you're going have to do this。Remember this。

 this is our little bycode interpret person for the expression language。

simplest thing and what we've got is the。The loop and the switch and the actions and the management of the program counterer。

And what we're going to do here is basically factor out the parts that have to be done at runtime。

 but leave the rest of it more or less in place as it is we're runnings for a simple jetit anyway it's just an abstract interpretation or the bytecodes。

 and when we interpret a bytecode in this form， we just admit the machine instructions that are equivalent to the action routine。

 So let's go through some simple examples again I'm using assembly code because it's just。

More concise as a way of explaining it so here's is the interpreter code for that literal bycode which grabs you know four bytes from the instruction stream and pushes them onto the stack and increments the PC but we're still grabbing our four bytes because that's a static program property and we're still incrementing our PC but in the middle we're going to do something different to emit the code or whatever would be left。

 which in this case， it's very simple it's just the push part right。

And so you don't end up admitting code， something like this， the simplest cases are these first two。

You're going to increment the stack pointer， which in a hand managed situation。

 you know which register containss the stack pointer。

You're want to grab the literal and store it into the top of stack and you know you can either choose to put literals off to the side in some special area。

And grab it from there and out， manage that area and figure out what the index is of the lital in that area。

Or you can construct it from pieces using whatever literal instructions are available in your instruction set。

Or if it's small， then it can be media。You just emit the code that emits that literal directly。

 and it's kind of a compiler choice as to。And you manage stuff and which of these you make， you know。

 you can get through，'ll certainly run fine with either one with these choices。

 this is like just an optimization。This sort of typical simple people style optimization that makes a real difference in performance。

 but that isn't very complex and it's not going to。

Resulting you having to restructure your compile city or something。Simply enough， yes。

See some other examples。Same thing we're going to convert our interpreted。啊。Pop。Pop and push。

Into something that emits code that does that， and but a part that manages the abstract interpretation is the same。

We grab a word from the top of stack， we on the point of down， grab the word next down。

 add the two together and store and in this case， you know， one of the things you would do in your。

Compilr is you assign certain registers for temporary working。Because you're only dealing with。

 you two or maybe three operas， you only need two or three of these。You'， you don't need。

You don't need a full balloon register out of past because the real expression stack is on the stack still well。

Conttro that方 now。And we can go on， these are all pretty simple。

The get takes the address of the thing we're going to get， which in this particular language。

 remember the simple expression language where we just have 26 variables and we can compute the address of that。

Up front and then just past the address's' in the image that's actually very little all of these are structured in such a way that you're really just taking a piece of assemler。

 doing a tiny better tweak into the assemler to fill in an address or something like that。 It's very。

 very straightforward。 It's not full blown。You know， intermediate representation compilation is very。

 very simple and this is all you need to do for the the jet for ph， this level of conilation。

Potlo is just like a gang except。We've replaced the load with the store。

The store rather to the location rather than the stores of the stack。

We have a few other things you might have to figure out。You want to be able to call into the runtime。

Because you don't want to compile everything that's in the original program。

 probably you think about。The implications of what's going on in your bike coating are particularly you're not trying to eliminate。

 you know， gut the whole internal structure and replace everything and everything it calls。

Because something like， you know， you't going to inline your collector， you know weren' right。

 the assembly goes for the collector and include it would base in the action routine of an allocator。

You want to be able to branch out into the runtime whenever you get into a situation where the performance difference really isn't important。

 so for example， if you're doing bomb allocation and you try and make the fast path in line so your allocator and compiler when it sees an allocation point emits the thing that tests。

For the pointer you know， not reaching the end of the space and doing the allocation。

 but if it does reach the end of the space， then jump back into the runtime and like a generic runtime handling。

This is no point you trying to o code for all the time。嗯。

It will make only ex faster if it's whole and' a whole lot of pain。Okay。

 so we also have to deal with managing our code because we're in the situation there where。

You haven't been with the traditional static system。

 which is the management of code is the developer's problem right you just get a binary。

 the code arrives as a bb。And all you have to do is load it and link it and where you go it。

 now stuff is being made at runtime， so we have to put it somewhere。

We have to be able to find it again when we need to call it or link to it。

 dispatch to it and optionally we have to be able to throw it away if we're an outer space right you can not throw things away and simply die if you're an out of space if you want。

啊。But in a sort of a production system you want to manage a space more carefully and throw all stuff away。

 either if you run out of space or if the program， if that really becomes unreachable， for example。

 in Java， know you can have a class unloaded after garbage collection and you don't want all the code from an unloaded class line around taking that memory space So you want to be able to discard so we need some kind of a structure to manage things in。

 know you could just mall stuff and throw it randomly memory but you'll soon find that that becomes kind of painful。

How big is this stuff typically get， it seems like it wouldn't be more than enough。

ItHow big is your program？Right， and the programs is okay good。然这这。I mean。

 it's hard to reason about a million lines of code。

 but a million lines of code is still like a few does you know， we have stuff a oracle with 100。

000 classes loaded from a single V。It still seems just like as it's not like gigabytes it's not going to be gigabytes。

 no， it's going to be megaytes it's not gigabytes， but it can be many megaabytes。

2 garbage collection techniques supply cartoon。我 get to that。

So and the band gain that we're getting is that。Let's phrase that the compiler is also going to generate the exact same sequence as the microwave。

Those assembly instructions the main gain is definitely that we're removing the branching yeah yeah and any people optimizations that you can perform and you know making things compact and directly executable yes so it's just the control flow that we're optimizing yeah。

you can and we will look at systems that do much more than that。

 but I'm not going to ask you to write an optimizing compiler in the last six weeks。你呢呢边。

Insane if you didn't walk out。就是。Okay。So this function。

 that set of functions is typically performed by something what's called codec。

 so it's a data structure。In your VM that manages the code in your system。And so the compile。

 the way it's structured is the compiler that you're write is going to emit the code into some kind of a large buffer because generally speaking。

 you don't know how big the code is going to be ahead of time。

 you can't size the amount of code until you've generated it because you've got variable amounts per bycode and you need extra stuff at the beginning and the end so you have some single big Laish buffer you know it might be I don't know many kilobytes or megabyte or something like that some reasonable amount for the biggest method you're willing to compile。

And the compiler is going to emit code into this buffer。When it's done and you know the size。

 you're then going to copy that off into the codec， find some place for it to live。

Copy it over there， link into it from whatever structures you need to link to to dispatch into it。

 like the lockup tables if you're doing method lockup。

And then you can reuse the buffer for the next comp。

So one of the things to observe is we're doing copying right， which means。You know。

 the code might run correctly in place in the buffer， but it's not where it's going to run。

 It has to be reallocable。 It has to be prepared to live and run somewhere else。

And unless you're willing to invest some extra complexity。

 you won't know that address until actually you're compiled。

So best thing is to make your calls into the run time。

 the parts outside of the code cache use absolute address so that the code can live everywhere but make everything else reallycateable。

Okay， so we're going to go into the structure and the techniques here in some detail and I'm going to call the thing that gets emitted。

Buy the compiler and end method， distinguish it from the source level method or function or whatever is in your original language。

So N methods comes from the Deuts Schiffman N code V code distinction and itself this was actually the C++ class in which these things were encapsulated and the term seems that were stuck through a whole bunch of V now。

So。So as I mentioned， in some languages， GC can lead to your code being unreachable。For example。

 Java class unloading， it's good to free the end methods when that happens。Also。

 if your codec is full。If you made it so that it has some fixed limit or you let the user site set the limit。

 then at some point you're going to reach， you know，'s going be。

 it's going to be normal more room life， so you've got to flush existing things out of there。

To make room and it's not just the question of freeing the memory and proceeding on。

 you have to delink the old code from wherever it was linked into the system like in the method tables。

 typically that will in mean installing a new link。To either trigger lookup or compilation。

 you know so that when you run that thing again， you know， with throw away the code。

 but that doesn't mean you're not going to use it you going to attempt to use it again when you try and attempt to use it have to either fall back to the interpreter or trigger the compiler again。

So you have to prepare for that at the point where you throw the code away。But doesn't even。

Harry a problem。Which is suppose this thing is actually currently running。

We have a method which we're trying to throw away， but it's somewhere on the stack。

 there's an activation record。The next thing is active， what do we do now。

 there's a few answers to this， few approaches。嗯。One。

 which seems well first we have to find out what makes。

I really find out whether method is active before we decide what we're going to do it。

An easy way is you can simply increment a account every time you enter a method to say it's active and decrement every time you exit the method。

 you have to be a little bit careful here in that the exit you know are many ways of coming out with method usually only one way in。

 but it's often many ways out。And there's ways of terminating things that don't even involve the method like。

 terminating the thread or exceptions that cut the stand back or。

 and you have to make sure you take account of all of that。

But the price of this is that hidden these increments decrements。And as you'll see。

 you're probably going to have to build a stack scanner anywhere if you're building a sophisticated system。

 so the alternative， this one is the one that seems to be used most in practice， which is，嗯。

If you want to find out whether a method is active。

 you scan the stacks of all the threads looking for the activation record。走还一觉得。Well。

 the Col convention has to allow for the linear scan of the stack of a suspended thread。

 you don't want to try this on a running thread。大请问一好。You want the threads to be suspended。

 it's a passive in memory， like if you have a single threaded system。

 then the scanner is the thing that's running and it can scan everything。

Below the stack because it's not going to exit， so that's nice and easy。

 but if you have a multi threaded system， you want all those other the guys to be suspended。

So wherever they're suspended， you grab the registers， you have to find the registers。

 extract the stack point or frame point or whatever it is that's used in the calling convention and then you know figure out how to walk down the chain of those things looking at each tram you have to find the。

U the like if the return address is going to jump back into the method you're trying to delocate because that's a good way of tracking whether that thing is active。

Obviously is very very highly machine dependent and it's also very highly calling and batch dependent so if it's the stack only contains frames that are corresponding to the stuff that you did in your compiler then you can arrange for this to be relatively straightforward but if the system allows callout to arbitrary code that can do some arbitrary things on the stack you know that can make life very very difficult and there are ways to manage this next week I'm sure Cliff we'll talk about this because this is a complex topic。

But it is possible to do this， but it just makes life much more complicated There is this worst case unfortunately where it just becomes impossible to do this and I've actually seen this in practice under certain circumstances。

 certain os。Under the right conditions， you know a page full or the right moment during the thread switch。

 the registers are not in user space， they're in the kernel space。And you can't get them。

 they just don't provide the system code to get them， all you can do is resume this threat。

So at that point， this technique is now impossible。

Could you send a signal to the thread and have it scan itself， basically like。

 you'd have to get it to wake up to do that， you know， the case where it's。

Suspended in this particular example was something that was it was in the middle of an IO call and a page fault and an inopportune moment would mean that you know wait for all that Yeah。

 well right so and it might know right because if it' was reading from the keyboard like what you going to do。

 you know zap the chair and say type something dummy。对对对。You know。

 it's not banded right you can't you can't force it to happen。

 You' going have bought it and then you have to write compensations and CO it says oh did we have bought from a system call and we have to figure out to be able to restart and red。

Yeah， they guess on。I think where you're supposed to be that anyway。What about just skipping that？

Is it possible to just well， so the danger is progress the danger is that the thread contains the frame that you're trying to dispose of。

So if you don't know， then。Well if you don't know， you can't dispose of anything。

 if you don't know well it's up in the thread， you can't dispose that frame or that thread。Right。

 but the thread couldn't have any stack frame on how do you know which stack frames。

 which methods are active in as specific thread the threads sharing？Yeah。別 notな。Locly。

 this is fairly rare， although when you discover in the middle of production， it's not ice。然后。Okay。

 so suppose you've been able to successfully stand the stack or you've used the counter or whatever to detect active end methods。

 then you have the choice， well you can do two things you can either say I found it and it's active and okay let's not dispose of that one。

 let's find another candidate to dispose it we could just skip that one and try and make a all somewhere else。

That's okay the alternative is you get into this other level of complexity which you willll get into you next week of a week after which is you're going to fake as if it was never there to begin with。

 so you discard the method。You rewrite the activation。So that when it's resumed。

 it either resumes in the interpreter or triggers another compilation to put you back where you were。

 and you have to recover all the state and the activation in just the right place and the right way such that it looks like you were never in the compiled code to begin with。

Thats a Ns dynamic the optimization。 It's an extraordinarily powerful technique。 It's very。

Tricky to implement， there's a lot of subtlety in it。But once you've got that。

 it's an immensely powerful hammer and you'll see in future weeks。

 once you've got this what you can do with it because it really is incredibly powerful。

And one of the assigned readings will be the people that described this from first。

 so we'll get to this。And you'll be looking at it some more。

But it's kind of scary to go down this path for the first time，二是。No。

 ont replacement is kind of a flavor of this。We'll get to that。

 but we don't have enough context yet to。这个玩去了。ok。All right， so you've。You've freed up the methods。

 you know stuff is being compiled and allocated and freed and etc。

 but you're now going to use the same problem that you have in IEAP system which is you've got turnover in this cache and you can lead to fragmentation so when you come to compile a method you find there's plenty of free space and you good cache but you can't find a space big enough to put your code。

This leads to another fork in the path， another design choice。

 which is do we compact the code cache or not？到。You can try and write a compactor。

 there's some extra complexity， you suspend all the threads。

 you shuffle all the end methods around to make a you know the hole all holds on the。

Join together at one end， you update all the dispatch links so that everything's still self consistent。

 you rewrite all the stack frames， so the return addresses are correct。

And you know you can make this work the self PMM did this， it works， it's possible。

 right it's not it's not impossible， but it's complex and but there's another approach which is let's just throw away some mo code。

We just keep throwing a away coat until we got a hole big enough。

and the thing is you can be selective， right， if you have a backup execution mechanism or it will trigger recompilation。

 you can say， well， this hole is not quite big enough。If I shot that guy next to it。

 then I'd have a hole big enough and you can always throw code away。

In this kind of a scheme because you can regenerate it later in some other place now there's a performance cost been added at that。

 but you're saving yourself the complexity and that's the path of the hotspot being went down。

 you know， same guy implementing in both， you know last back worked on self and。

When he did hotpot said， I don't want to do that again。But you can do it either way。

 this gets even worse if it's multith itself。It's not been done any time。Another choice you have is。

Are you going to put the end methods in a separate managed area or you just put them in the heatap with all the other stuff？

The latter has some attractions， you already have a compactor and a collector although they need to be extended with a lot of extra material if you're going to compact and collect methods because you've got all this extra work to do when you move them it's not just copying bitts from here as to there。

 you have to fix up。这下部分。So but there is the attraction that you're managing all of the space in this uniform manner instead of having。

 you know， the other kind of fragmentation， which is tons of room in the heap。

 but none in the code cache or tons of room in the code cache and none in the heap and when that happens。

 you know， you can't kind of start moving methods into the heap and objects into the code cache。

 so that's what you're host。So this avoids that kind of fragmentmentation problem。

 but at the cost of some more complexities， it gives you this unified heat matter。You know。

 the damnmside。 one of the damnmside is that the。Most garbage collector systems are built with some assumption about the longevity and the demographics of the objects and code tends to be very long left compared to other objects and so if you have a system that's doing a lot of copying。

 you don't want to be copying your code around a lot and really gives because it's very expensive to do that。

Another thing that might get you little nervous is if you put the generated code in the heap。

All you have to do is run off the end of that into the data part or have the data run off the end into the code and suddenly you have a really nice attack surface for someone to get into if you've got a bug in there。

Whereas if they're very far apart it life is at least a living one。

So while we're talking about garbage Collect， we have the other problem there that we have stack frames。

Associated with compiled code。And we have to find pointers。嗯。

To the objects represented by those stack frames as roots for our collector。And in fact。

 if you have a moving collector， then only do you have to find the ponds the after。

Fix them to point to the new locations that the objects are moved to and you have to get this exactly right。

Now， because you can't start wandering down in stack and rewriting arbitrary words to point to other things。

嗯。Because the words you're rewriting might not be a reference。

 it might be you know a return address or a floating point number or something。

 so this makes for a challenge in precision in locating all of the pointers so the pointers can be in registers。

 they can be in the stack locations for the end methods and they can even if your compiler was structured in that appropriate where they can be embedded in the end methods as literal remember that example I had earlier where I was writing the spark to assemble a 32 bit。

Object pointer in a register right you've got 13 bets of that are in one instruction and the other parts in another instruction in some weird alignment。

If that's an object referenceence， you have to find it and you have to rewrite it when nothing thing moves。

 which is another challenge。if that isn't bad enough already， worse。

 you can get into the situation where。If your compiler has to do things like tagging or de taggging or it has to do some of address arithmetic to index。

 the structure， suppose you suspend。That compiled code in the middle of that sequence。

 halfway through one of these things， you end up with something that's you know half tagged or untagged or pointing into the middle of an object rather than to the header。

You can get into all sorts of complexes here。And how do we deal with that？

Why is it easier if we have a non moving collector？What does that， What problem does that solve。

You化 yeah。If you have a non moving if you'd like to， you're not rewriting any of the references。

 you just have to find them so you could be a little bit in error on the conservative side。

If you're in error and you find something and you mistakenly think it's a pointer and it isn't。

 that'll just mean that thing doesn't get garbage collected in quite as timely way。

 but you're not going to break the program。Whereas in a moving collector。

 if you get one single rewrite wrong， you know， the next GC， you'll probably discover that。

Or before that， when that frame returns or something。Okay。

 so we have to look at the roots in all these places until there are different techniques for this。

One simplification is that by definition， all the activations in the thread except the one on the top are at a call sign。

So that makes all but one of them。Degenerate into a simple case。

 which is how do you find routes and registers that are suspended at calls？

In frames that are suspended at cold。 So one technique for this is to emit a map a simply bit map。

Basically describes which registers alive and if the pointers can be untagged。

 this has to be a map of live pointers so you want the things that the collector has to find and rewrite mapped very precisely and the compiler can admit this。

The each call sign， for example， in the selfcomplir， when it emits a call。

 it actually puts the register map in a word after the call where you would think would be the return instruction。

 but it modifies the return convention to always return to an offset after where it would normally return so the return is bumps the pointer up a few to skip over the data that's associated with with each call sign so。

So that's one trick， you just took them in the slots。Yeah if you replay that trick。

 can you still use a process retry？It depends on your processor on Spark。

 I think you RE like a general risk thing and you can give it an offset。

One of the downsides there though we discovered is the hard work guys treated that as such a weird case they don't predict it properly there a return addresst。

So basically all of those reps misprod on a certain generation of spa processes。什么逼。Okay。

 so that deals with the the all but the top frame， the top frame in theory。

 could be suspended anywhere， right the scheduler can go。Stop。

 I'm going to run somebody out there be any instruction boundary if you're relying on the OS schedule information all of that stuff。

So you could think about making a register map for every single instruction。

 but that's kind of prohibitive in space now you're building a lot of extra data to go along with your code。

 maybe you don't care to your point earlier that the code isn't you know what's if the code isn't big what's to X the code right because it's only a word code instruction？

But I don't think I know anyone's actually calm down that。啊。

There are other approaches to this documented in the literature。

 some of which I think are just paper designs， some of which have actually been implemented。

The most common one which has been implemented many times is to designate certain places as GC safepoint and you make a register map for the safe points in the instruction stream and you ensure that when you do a tax can。

 the thread is always suspended at a safe point and we'll get to how you accomplish that。

Another idea is to keep the maps of various places in the code and if you happen to stop in between two of those places。

 you pick the one previous to it， you know a dominator。

In terms of the instruction flow and then you abstractly interpret the machine code to figure out where the pointers could be from that point in the code。

 So you know， you interpret the ads and the loads and the subtracts and the stores and everything and you figure out from that register app what the register app would be that instruction there's obviously a lot of complexity in that you're basically building an interpreter for the underlying hardware in software and you have to。

Ts very carefully about where these maps are known with certainty and where they can be derived with certainty rather than。

Because if you're loading like from an element of an array。

 you don't know what's in that element but the type system might save you， so it's complex。

 you have to think very carefully。There are certainly published descriptions of this。

 I'm not sure if anyone's really built this。This in production and。And then another。

Possible approach is just replay the compiler again。But now say， oh。

 I need another register app of this instruction because I have a thread suspended there and assuming you built the compiler in a deterministic manner。

 which is harder than you think。And it generateds the exact same code in it last time。

Then at that point it will give you you know the map at that point and you can use it。

 but in general that's not used because it's just expensive to run the compiler unless you have a very。

 very simple compiler that you're using for everything and you're doing no optimization if you are then that seems perfectly reasonable and those circumstances it probably is determined。

All close， close enough。So。Okay， so let's look at the GC save point track。

 so the simplest approach more or less。I don't know of anyone who's really studied this you know in kind of a very careful you know。

Comparing all the techniques approach， but certainly this has been used in many cis gun is to designate a safe。

A safe point at the entry of every end method。And at the backward branches and the end。

 the idea here is code runs， it will reach one of these points in some reasonably bounded amount of time。

You know， you can insert more of them to make it。ToTo decrease the latency of reaching these points。

 So you could sprinkle them through a bit more。 But this is sort of the minimal set right。

 This gives you the sense that， you know， every loop is going to stop at there the tail of the loop and every。

 know recursive thing is going to stop when when the recursion is true。

So that gives you some coverage and then at that safe point。

 you emit a little bit of extra code that tests the global flag that says。

 should I be suspending myself？Usually you just have to look at a single bit somewhere in memory。

And if so， then the thread when it reaches that point branches off to some other code that suspends itself and if you like。

 it can even say， oh I I suspending myself because we're doing a GC should I scan my stack and tell me to tell you all the routes because you're already there in the thread and it's not going to return and undo the stack so that's a good place to scan the thread scan its own stack from that point downward。

から。So why any thoughts as to why we do？And methodth entry rather than return。There was many returns。

 but only one in terms， Yeah， exactly。And there's code that has to be planted to do this。

Now there's many different techniques for this that require。

More or less invasive tank surgery on threads and we'll cover those in the future。future lecture。

 but this is good enough to begin Yes， Im a bit confused about the interplay between OS threads and your sort of VM concept of。

Because the OS has its idea of a thread， Nick can interrupt you at any time for any reason。

So of versus so and with this technique， it doesn't really matter how you do this because what you do is at the point where you want something to suspend itself。

 if the OS has suspended it， you just you just either let it pick it up and run it or force it to run by his you know calling the appropriate thread resume thing。

So you should be a way of making it make forward progress unless it's stalled in a system call whatever then that should be discoverable too by examining stack。

So there's a lot of complexity around the determination of the condition here it's dualable So pretty much so far when we're talking about looking at the stack。

Suspension and kind of all these sorts of thread associated terms。

 we're talking about the virtual machines concept of a thread and the OS concepts of a thread are sort of like we're sticking with the Po P thread Well it can be either the two common situations are either the VM manages its own threads and it runs on only one thread So it's just in effect。

 the co-routs you're just calling this sort of thing that changing back point。And that's very common。

 a lot of the papers from the field from the days before multiprocessors。

 and a lot of the literature talks about things in those terms。

But if you go into the situation where you have multiple underlying， you know。

 you're using the O to manage your threads and presumably because you have a multiproces underneath。

Then a lot of these techniques apply， but you have to alter the appropriate synchronization things。

 I'm going to leave almost all of that stuff to a separate talk on dealing with concurrency because it's really hiring in many places and it's sort of。

It just complicates everything。So it's easy just to bring all that won't go is here are all the things you have to think about when you go multi process or use underlying the line or as things。

Is it possible that when the stars are dense， the memory got screened because you execute some instructions and built into a actually ease？

Sorry， the threat got advanced and all threats are advanced into the system。

And what if when during the events then you drain the memory？

There are some instructions that Lps a lot。Well， so at that point。

 what you would have is a safe point before an allocation。

 because you're writing the allator or you're omitting the allator at any contest at that point。

 just before you're about to allocate whether this guy is supposed to suspend re allocation。Well。

 they're not that common， names are not that common。And in fact。

 there's another technique which we'll describe in the concurrency thing。

 which is a common technique in a multiprocessor system is you allocate for each thread。

 its own private allocation buffer and it allocates out with that。

 so it can make progress in there without actually having to consult the world outside。

That's solve some of the problem。Okay， you also need to find roots on the stack。

 so you need to have some way of scanning the stack and finding the things that are stored in stack frames as to whether they're pointers or oops if you have a tax system。

So if tagging is used， then typically what will happen is in each stack frame。

 there's some region which will all contain some uniform。Games。Number of oops。

 you know the ta pointers because you're over writing the compiler you can manage your own stack and so when you do that you can simplify the problem and not having to scatter all the points over everywhere。

So either way， you mean some way of knowing within a particular stack frame where the pointers are。

You can keep that information off in science structure if you like。

 typically a list of descriptors tagged at the end tap onto the end of the code of the end method。

 you know reachable by some data structure that might be one way doing it or you stick point into that thing in that block after each call site。

Because you're walking down the stack anywhere so you can find the calls corresponding to the stack from the return addresses。

 if immediately after the call， youve got some handy dataer that describes the GC sta。

 it's right there。So if your language allows you to specify object literal objects and GC object and Gable objects in the code。

 you may choose to emit those things as literals in the code stream。嗯。You know。

 usually if you're building a word up， you don't get to do that。

 You can load a word from a side table。 But if you're doing。

assesembly of from immediatemedia usually there's a piecemeal bitfield in the instruction stream and if you go down that path well then you have to bite the bullet and emit them into a side table where those instructions live。

 you emit them in a very you know sort of co consistent manner and have a piece of code that knows how to look into those instructions are extract the bitfield for the corresponding。

Object pointer and then be able to rewrite them back another thing which is there' is another thing which is not bound on a green thread type system。

It gets a little somewhat hairy or if that code can be running。Because then you somehow want to it。

You have to suspend that f while it's doing me while you're doing the rewrd。

So there's a couple of ways of addressing that， hopefully in none of this。

 if you don't emitm code pointers in as immediate， then you'll don't have this problem。

So that's all I'm going to talk about this time。In a week， I think。

 after the tagging exercise is done。You'll be off writing your own simple jet for f in your own VM and some of this stuff will be necessary。

 you won't need the very fancy stuff and next week we'll talk about even fancier stuff that you won't need。

 but you should know about because you're going to need it for later when we use it。那个研究。But for now。

 the exercise in a week is going to be。Build one of these and make it one。Okay， any other questions？

Thank you。