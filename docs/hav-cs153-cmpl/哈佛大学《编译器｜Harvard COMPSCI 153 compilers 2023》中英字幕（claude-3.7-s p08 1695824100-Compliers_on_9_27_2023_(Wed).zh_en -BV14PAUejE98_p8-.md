# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p08 1695824100-Compliers_on_9_27_2023_(Wed).zh_en -BV14PAUejE98_p8-

haven't I don't actually remember your name correctly。

Although you are going to need to use a Shopie so I can actually read it from up the front。

 sometimes say Anthony。Okay嗯。Announcements， homework 2， as you know， is due today and of course。

 up to three days of late minutes。 and we'll be trying to get you the graded results back within 10 days of today。

 So a week after the last， the last one can be handed in。😊，I will be。

Sending out a survey just about how homework2 went in particular I' wanting to。

Know how the study groups went， we had almost everyone in the class participating those your feedback on that would be really useful and if you have any suggestions on how to improve the functioning of the study groups that'd be great。

 I appreciate that the homework three study groups have already gone out without that feedback but I'm very eager to hear what you all think。

Speaking of homework 3， homework3 is released， it is on Cans。😊。

So you can download it and start working with it after lecture。呃。

It's going to be due in almost four weeks， so October the 23rd。But。😡，It's a hard homework。

 so you should start early。And moreover， homework 4 is actually going to be being released October 16。

In a little under three weeks。 So there's kind of this period where homework 3 is still out。

But homework 4 has been released。 This is to give you flexibility。

But really what I strongly encourage you to do is start homework3 early。

And then be ready to say it's done， it's good enough and submit it and start working on homework 4。

When you feel it's done。Any questions about homework two， homework three， any of the admin side。

 homework three study groups？Okay。So in today's class。

 we're going to be continuing to essentially think about how we compile sea level data structures and constructs down into assembly。

This is for a couple of reasons。One one is to really understand some of the design of LLVM。

So in particular we'll be as we talk about data types in L of VM。

 it's going to be really useful for us to actually understand。

How structured data and C is typically represented。At a low level。

In order to understand the LLVM instructions。But also。

 that's essentially what you'll be doing for homework 3。

 What you'll be doing is compiling L L VM into X86 code。 And so as we see how。

Da and data is represented at the YaLVM level。And how we compile that down into assembly。

 this will give you high level ideas for what you should be doing as you。In homework 3。

 as you compile L of VM2X86， so towards the end of the class， we'll go briefly over homework 3。

 some of the ideas in there。So at the end of last class， we were talking about a raise。

How a arrays can be laid out in memory， that if we had multidimensional arrays。

 we could either be in a room major order。And how that affects the computation of a particular location or in column major order。

Or represented as an array of pointers， each of which is points to an array。嗯。

We talked about the various， at the end of class， the various advantages and disadvantages of the approaches。

 Any questions on that。Okay， one of the things that we want to do in some languages is ensure that our array excesses are safe。

That is when we access an array， we're accessing it within bound。

So not before the start of your array， not beyond the end of the array。So languages like ML， Java。

 C Shop will do this。 so check。Typically， at runtime， that the excess is within bounds。

 And if it isn't， they'll raise some kind of runtime error， a array index out of bounds。 for example。

 C And C plus plus do not。Enforce the balance checks。

So in the languages that do enforce bounds check。One of the questions is。

 how do we actually implement this？So， clearly。We're not always statically going to know the length of an array。

Sometimes we will， in which case we can discharge the check statically or at least insert runtime checks that are comparing the index against the non length of the array。

But a lot of the time we'll be actually receiving an array that's a variable then we won't know how big it is。

So we need at runtime， some mechanism to give the size of an array。

And what that really boils down to is where do we store the array。

 where do we store the length of the array？One answer。Is to actually store the size。

Of the array in the word before the beginning of the contents of the array。嗯。

Why might this be a useful approach？you try to access the element？If you access like El gate。Or9。

something large， you can compare it with seven。Yeah。Right。

 so the nice thing is it lets us implement these ray bounds checks。

 right that we have the size of the array and is conveniently located with the array itself。

Right so that we given an array， we will know where to find the size。

 But this particular choice of the representation that we put the size in the word preceding the beginning of the contents。

This is an interesting design。 Abe， I I think of maybe two things like at the end doesn't make a lot of sense if we don't know how long the ring is。

And then also like maybe for behavior， if you know that you're gonna be access net in the array anyway。

 accessing the size probably close to the Yeah， great So there's a couple of points。 One。

 one is we can't put it to the end because we don't know where the end is without knowing the size2 storing the size with the array might lead to nice locality properties based on cache behavior。

 maybe a couple of other things that might be that are useful here is that the representation of an array in many ways remains the same。

 The value of an array that we're passing around as a pointer to the beginning of the array contents。

😊，So in some ways， this might allow us to be。With care compatible with say。

 see representations of array。呃。Calculation of the index is nice and straightforward。

 We continue to have the value of a rate being appointed to the beginning of the content。

 So all of the sort of arithmetic we were doing based on indices we can continue to do。😊，嗯。

You can imagine an alternative approach is to represent an array as a pair of the say stores the size and then say a pointer to the contents。

Which。Might lead to another memory D reference。So more memory access。

 less good cache behavior that you had and incompatibility with。呃。With maybe C or legacy code。嗯。

If you store it as a pair of the size and then the contents of the array。And treated。

The value is pointing to the beginning of the pair， again， you might lose。

Some of the years of computation。And maybe some of the compatibility。

Some languages that are a little more restrictive， Pascal only allow statically known array array sizes。

And this turns out to be really painful when you sort of go beyond。

The CS101 introductionuction to programming class and have applications that ideally would love to have dynamically sized arrays。

You need a little care， maybe with thinking about the implementation for multidimensional array。

And how you end up going about。嗯呃。Go about thinking about it。 There's a few options you could use。

More expressive encoding of the size， say dimensions， or maybe just less precise encoding。

 the total length of the array as opposed to the exact dimensions that make it up。嗯。

So in this representation， it's stirring the size immediately before the array contents。

The implementation of array checking is， is pretty nice。 So let's assume that we have in R A X。

 the base point is to the array。And that we're trying to access index I being held in register ECX。

So it ends up being nice because what we need to all we need to do is from R X。

 we can access the size。 So going one word earlier and memory minus-8， RA X。

RDX now contains the size。 we can compare that to the index we're trying to access。

 If the index is not okay， we'll invoke some error out of bounds error。

 otherwise we just perform the normal array access。So pretty compact rays to check。It's， of course。

 more expensive than simply just directly accessing the array。 You know， there's an additional load。

Hopefully nice cache behavior， but it's nonetheless an additional memory access。

 and then there's this compare and jump instruction。U。

Compilr optimizations and architecture or chip design end up alleviating a lot of。

A lot of the overhead here， for example， by prefeting。

 by predicting which branch you're going to take in the common case。呃。

And also issues like optimizations。Such as if this ist a loop。呃。

Which is a common case as we go through every element of array array， the index increases。

 what this means is we're perhaps performing checks really。

 really frequently in the inner body of a loop。Some compiler optimizations that we'll look at later in the course are able to pull the check out to the beginning so that instead of doing an rebounds check for every single operation。

You might just do one at the beginning of the loop and be able to reason that all of the accesses within the loop are going to be within bounds。

I mentioned already hardware support。 so the implementation of the instruction set can lead to。诶。

Immproved performance， branch prediction is one of the key things with this jump。Pretty much。

Every single access is going to be within downs。 so the normal cases the access will be within downs。

 So these days most chips will realize that most likely we're just going to jump to this okay branch and keep on going and so they'll actually end up speculatively executing that branch so that。

The comparison and jump doesn't cause much of it delay delay。That said， though。

 who's aware of the spectter in meltdown？Vulnerabilities。These are some。

Fulnerabilities in computer systems that are。Essentially due to speculative execution。

Due to chips just trying to ring out every last ounce of performance， they go ahead and say， well。

 let's assume that's going to be okay and keep on going and executing。 And if it's wrong。

 we'll just roll it back。 but most of the time we're going to be right。

It turns out that that speculative execution can reveal sensitive information。

I'm not gonna go on the details here， but the long and short of it is。

Sptro and meltdown are like really serious bugs that， for example， can reveal in cloud computing。

 allow somebody a coten， somebody who happens to be running on the same machine as you to get a lot of information about。

 say cryptographic keys that might be on the。😊，おね。嗯。Right。呃。So anyway。

 it turns out there's a trade off at the moment between security and performance。

Any questions at the moment on rebounds checking？Okay， a related data structure。Is strings。

 so strings and sea。ARepresented as a rays of characters。嗯。These arrays are null terminated and C。

 so that is the last character of a string has to be the zero byte。Z bytes driverva？嗯。

Within a C programs。String constants typically represented as global data。

They're often put into the text segment。The same segment that code is in。U。

Which is generally read only。Have。This ends up allowing more efficient implementations of constant strings。

 that if two constant strings have the same pointer。You know they're equal。嗯。呃。

So this turns out this kind of low level implementation detail。

 the idea that string constants are stored in this read only segment。

Actually leads to some perhaps confusing behavior。 And see。For example。

 if you said declared a pointer P， cha star P equaling P。This is going to wind up pointing to。

Most likely， ending up pointing to an address in the tech segment。

So a memory address in a region of memory that is read only。So if you try and modify an element。

Of that array。Change food taboo。You'll end up getting。

Some type of sick fault that you're trying to modify or reddotly sick。

So what that means is if you want to do， you， start with a constant string and modify it。

 you do actually need to create a copy of the string。So code down here is showing how you can。

Create on the heap， an appropriate size array， appropriate size chunk of memory。

 four times the size of a character。Stng end copy copies over the string。

 it's good practice to explicitly state the number of bytes that you're going to be copying。

And note that it's sorry， the number of characters that you're copying。Another way' using。

Four bytes here to include the null B at the end of the string FO0 null B。

 and so this code at the bottom does work。 We've copied it into the heap and their memory is ratable。

Yeah， so help。放圈。If you。Declared a character array as a local variable that would likely be on the stack。

呃。I need to think through and refresh myself on it。 if it's a。嗯。Yeah。

 typically for both constant size arrays and if you have an array of dynamic length。

This declared locally， it would be allocated on the stack。The interesting thing， of course。

 is if it's dynamically allocated， then it's not going to be until runtime that you know the size of the stack frame that you need。

 and so the。And so this might complicate， for example， where your stack slots are。呃。

But that would be a common。Compilation strategy to have this local。

Buffs with a static or denimly size being allocated on the stack。Okay。

 any other questions about strings or arrays？Okay， let's move on to another data type。

Tgged data typesd。Many languages have something like this in C in Java， these are enum types。

 so for example， in C this might be how you declare an enumerated data type inum。

The days of the week。In M L， this would be a form of。An algebraic data type。In this case。

 simple enough that the data constructors don't take any parameters。

A common approach to implementing enums this type of tag data is to simply associate an integer with each of the possible tags。

 so in this case and C associating zero with sun， one with mu， two with Q， so on and so forth。嗯。

And see this variance of NNum where the programmer can actually choose which values are going to be used to represent the tags。

In M L， of course， algebraic data types can carry data with them， right， so that。诶。

So if we had a more expressive data type， foo， two constructors， bar and Bs。

So it's similar to you know， an enumerated data type in the sense that there's only two possible constructors。

But the two possible constructors have a value associated with them。

 in itt in the case of bar and in int and another food value in the case of baz。

So the way that we would typically implement this is as a pair。

The first element of the pair is the tag， the integer indicating what data constructor is being used。

 and then the second part of the pair is the data。For it。Now， of course。

 what this means is that by looking at the first element of the pair。

 there's enough information there to figure out how should you interpret the rest of the bys of memory。

 what type of data constructor is it， What tag is it for the data。

 and thus what other data should you be looking at in the subsequent byits。嗯。

So just make this a little more concrete。Suppose we have a value bar 3。

We could represent this in memory as a pair。The zero indicating that the data constructor is bar。

 and then because bar carries with it an int。The next bite is three， the integer。With bez。

If we had bas with the pair 4 and F， the previously constructed value of type。Foo。

Wouldd represent it as follows， a pair where the first element。Is the tag1？

The second element is itself a pair。so not the same size as the data for。With the tag fo。

Containing the int for and a pointer to。The value for F。Right， so what that means is in。Ml。

A value of type food is always going to be a pointer。To a pair of。

A tag indicating which data constructor only any data that's carried along with it。

Any questions about the representation？Yeah， burial， you have an aium type。So， how's that you。

You have。Do you take the biggest， the size of the biggest？Innubereration， and then。没。

Every block like that and then hat or a line。I imagine you could make a completion strategy like that work。

 it gets harder in a language that would allow you to extend types and allow you to somewhere else in the program to add another constructor。

Wwhichch some languages do allow What happens in M and Ocal， rather， though。

 is think about a food value as being a pointer to a pair。

 So an array of foods would be an array of pointers。So that is。

 we know what the size of an element of the array is。 If you have an array of fo， great。

 that's going compile down to an array of pointers。 So， it's a nice， easy。

Representation where you don't have to do anything smart to figure out which indices you're jumping into。

So nice， simple representation， of course you're following a lot of pointers。

 you're chasing pointers all over the place。嗯。Yeah。Okay。So one of the key uses of tagged data types。

 and let's think about CEums first。Is switch statements。In case you'd be。

Switching on some expression and then having a bunch of cases based on the。On the tag。

So how would we go about compiling。A switch expression。I do just want to point out quickly。

It's common that these cases will be terminated by a break。

Which essentially means jump to the end of the switch statement。If a break is omitted， though。

The behavior on C is that you simply fall through into the next case。So for example。

 if this breakup here was omitted。And we fell into the case Sunday， we'd execute the statements S1。

Full through into the next case and start executing the same's S2。Okay。

 so we need to make sure that that was implemented。Appropriately。Okay， so compiling this。

Remember that。We're representing Sunday， Monday， Tuesday， and so on simply as integers。嗯。And so。

There's a few different options we could use to compile。The simplest is maybe just to。

Have a whole bunch of cascading if statements。 So that is we。

In the switchitch E to compile switchitchy， And that's what I'm using the double brackets for。

It's showing how we compile switchsheet we would first of all。Evalu E with a compilation of E。

And get the value that we're meant to be branching on。

You can then imagine that all we do is for each of our cases in order， we simply see， hey。

 is the tag equal to this case？If it is。If it is equal， we jump and start executing the case。

 So we start executing S1。 Otherwise， we jump to the next case。And do another comparison。

To implement brakes here at the end of this block label would be1。That is the code to executive。

The first case was met。 at the end of it， we could。Implement a break by branching to。Emerge label。

 merge being the label at the end of the switch。And if you had a break inside S1。

 you could translate it the same way， simply branching to。The merge label。So this is nice and simple。

 right， We get the intended behavior。嗯。We evaluate E。And then we see if does Z match tag1， if not。

 we go to does it match tag 2， No if not we go to。Tag three， so on and so forth。嗯。

Good or a bad completion strategy。姑娘。Could be bad诶。Your。

The case you want is like what is it was Saturday at the end， every single time。

 then you would have to go through Sunday as Tuesday， et cetera。Okay， then7 execute that case。

Right while， you need to do like seven or six if。Right。So the cascading ifs。

Might end up with a lot of comparisons to simply get down to the last case to the case you need to do in comparisons。

 so that's annoying。嗯。Turns out that it works okay for short。Numbers of cases。That in general。

 if you have less than about 16， it's not too bad， you might be like jumping all the way down。

But it doesn't get terrible。The thing is， though。Not infrequently。

 you might have hundreds or thousands of case statements。

 particularly in code that's been generated and indeed。On。

Monday we're going to start looking at pasing。And Leing。

 and what we're going to find is that we have positive generators。

They will end up automatically producing code， and they quite frequently are implemented using switch statements with hundreds。

嗯。Of cases。So。Let's suppose we had a switch statement with hundreds， thousands of cases。

 What's another compilation strategy we could use instead， So have a minute to think。Next vote。

It's a。Heypothetically， you could have like kind because。The variable in question will be an end。

So you can have an array of like which？Like mapping each in value to the where you would go。

It'll be one array access in。Nice， so in a lot of the cases。

 the ins that you're going to be using are going to be pretty dense right， you might actually。

 if they're the enumerated tags and you have one case per tag。

 then you're actually going have all of the ins from 0 to n minus-1 or something。 So youre。

 you could imagine like implementing it as an array。 simply for a given case。

 you simply look up the index of the array and jump to the appropriate label。

 jump to the appropriate address。 fantasticastic。 that would work well for。😊，You know。

 for dance values。嗯。呃。So there was this case with with a den。 it doesn't even need to be0。

 if you could of course imagine some other range in there。If you're not dense。

 if you still have a lot of cases， but maybe they're all over the place。

 you could actually just create a table。And then do some linear or binary search through it。

Or you can imagine。You might want to end up with a hash table instead being able to jump directly to the value you want。

Let's say it's without having the overhead of an array for every single possible value。嗯。

What often happens is there's some heuristics to combine these techniques。

 So you might imagine that you have switch statements where portions of it are dense。In which case。

 an array might make sense and other places you might use another technique and maybe even come up with a sequence of statements to figure out。

Which section you're falling into？Okay， so that's for。Switch and a case statement。嗯。

This similar tube are not quite the same as pattern matching that you're all familiar with an Okennel。

And pattern matching is really powerful from a programming perspective。

 You can actually have these really deep matches。 Has anyone implemented like a red black tree ever in any language。

😊，So it's a data structure that gives you a balanced tree。

Implementing a nocal is actually really nice because you end up using pattern matching。

To check the various cases。 And so the way that a red black tree works is I can't remember the details was things like。

 if you have a red node that has a black left child。

 then you want to rotate it in this particular way。

 and you to complicated it invariance of the data structure， it ends up being balanced。

So patent matching is incredibly powerful。And one of the questions is how do we end up compiling？

Paent matching down to the assembly level。They're like switch statements。

 except for the fact that you can nest them deeply。

 right A pattern matches can be more than just the top level constructor。

 you can match things deeper and also you can bind variables to the data that's being carried with a data constructor。

😊，So one compilation strategy that you can take is simply to flatten the match out。To。

Instead of having these nested patterns， you can imagine essentially a source level transformation。

So that every match is only on the top level constructor。And then if it matches。

 you are then matching on。The data that's carried along with it。

And once you've kind of broken her down into that level。

You can imagine a straightforward compilation strategy that's essentially the same as。

Translating a switch statement， they just happen to be nested switch statements。Of course。

 you need to be careful about making sure values arebound correctly as if you match something to make sure that a variable is referring to the data carried along with the data constructor。

 but at least the idea of figuring out which case you're in。I is relatively straightforward。嗯。

That's it， there's a lot of opportunities for optimizations。

 And so there's actually a lot of papers about。How to perform。Paent match compilation。

One of the nice things is a lot of these optimizations actually happen at the source level。

 so at a level where we're still talking about algebraic data types and match statements and you do a whole lot of transformations on those maybe changing the order of that we're matching and transforming them。

As we did here in this example， it's still staying within a high level representation to make the pad matching more efficient before we end up going down into an intermediate representation。

 any questions about。About this incredibly brief overview of pattern matching。

 which many people have spent a lot of time thinking about and implementing and making sure your Ocaml compiler goes fast。

😊，ok。So with this knowledge under our belts， with this knowledge about how we're going to take essentially these C level constructs。

 a few M L constructs and how we translate them through into assembly。Let's turn back to LOVM。

Our intermediate representation and see how we end up representing this kind of structured data in LLVM。

嗯。So。The LOVMIR is typed as we talked about last class。嗯。That is there's a lot of type annotations。

In in the IR。The types that we commonly have are void。That's a special type。

 It's not quite unit in M L。 Its kind of， you can think of it in some ways as being only a single。

Void is a type with only a single value in it， but normally it's used to represent the idea that as and C。

 a function doesn't actually return a value。So in general， we're restricted in how we can use void。

We have in B integers， I 64，64 B integer， I 8， a cha， a single by。 I1 for a booleion。

 We talked about how I1 is the result of a comparison。A razor represented。With these square brackets。

numberumb of elements。 So this is a integer constant greater than a equal to0。

The lowercase character X times。And then a type T， the type of the element of the array。

We'll dig into this in a little more detail。The size of the array here is not actually used for any sort of array bound checking。

L ofVM doesn't。On its own， do any insertion of a rebounds checks。

 This syn here is simply used in the calculation of addresses。 So， for example， if you have。

A multidimensional array。That would be represented as nested arrays。

 and it would use the size of the arrays in order to figure out the pointer arithmetic。

 We'll get to that soon。Pretty frequently low， you have as where you don't know the size of。😡。

And that's typically represented with the constant zero。So zero times。The type T。嗯。

Typically means an array of unknown size。We have function types in the language。

 so a function type is using C like notation， a function that takes arguments T1 through TN。

And returns the value of type T。嗯。There are some restrictions， so， for example， T can be void。

 meaning the function doesn't return a value， but T1 through T in could not be void。

It doesn't make sense to have a。An argument of typhoid。

That's definitely a restriction we have in the version of LLVM for the homework。

I should say I'm not entirely sure if that's a restriction in the full LLVM。嗯。We have structures。

 These are represented using curly braces and a list of types。

 So think about these as representingstructs， you know， so Cstrs。

One of the key things to note is that there's no field names。Yeah， right。

 so when we're referring to an element of a struct， it's purely by the index， right， the zero width。

 the one， second and so on。We' can have pointers。T star。And finally， we can have named types。

 so that is within LVM， you can at the top level。Come up with a name and have a type definition for it。

This gives you a convenient way to refer to a particular type， so for example。

 in C if you declare a struct， that would normally get translated into a name type an L of VM。

Named types also allow you to define recursive types。

 So imagine that you were defining astruct that was a node in a linked list。You'd have， let's say。

 astruct with two types in there。Let's say an in， that's the content of the list。

 And the next one will be appointed to。A linkless node so that would be a recursive type and the name allows you to tie the no in the recursion to refer back to itself。

So hell。跟。Functions take function types of argumentss。🎼嗯。I need to， the short answer is no。第。

I need to double check the results。 Remin me we're to look at the homework 3。

 I want to make sure I'm not giving you incorrect information。 My recollection is that。No。

 these would have to be simple types。 Arguments would need to be simple types。

 Sple types include pointers。 So you could， for example， take a pointer to a function， but。

Not a function value itself。嗯。But by my in we'll look at the specter。

Make sure I'm telling you the exact correct information。Sa look at some example types。

 which might help。Clarify things。 So an array of 42 integers。

64 but integers is represented as follows bracket 42 x a 64。A two dimensional array。

This is an array of。With six elements， each element of which is itself an array of seven elements。

Here's a structure for representing。An array with with its length。

 right So a pair first element is a 64 bit integer the length。

 Second thing is an array of unknown size。Zero across I64。

And here written out as an example of a sea styleyle linked list。

A node is a pair of an integer and a point to a node。诶。

You may remember from last class we had an example with points which were pairs of integers and a rectangle which contained four points。

 here as it translated pretty directly into LVM tapes。

So when we say we don't know the length of the area。

 we just mean that it will be cop runtime right now that it's dynamic。It could be either。

 It could be that in the。Context that we're in， we get past an array。Whose length is always the same。

 Maybe it's， you know， been。Is coming from somewhere else in the program where it might be statically computed。

 but we just don't know it here。Or it could be we're at a place where we get given arrays of different sizes on different ins。

Or it could be we' getting an array of dynamic size。All right。

 so there's a number of reasons why statically we may not know the size of an array。

One of which is that it's。The array is determined dynamically。Mdie。For the two dimensional。

 does it go like row column column row。That is a great question。 In some ways， it's the。

It's abstract and it's going to be a compilation strategy。

 an implementation issue about whether you are implementing it in room major or column major order。😊。

嗯。But it's almost always physically layout out in real major order these days。

 I don't know of any architecture that would。The would sorry。Common is real major order。

But that's an implementation detail about kind of how you translate LVM into。

A lower level un assembly。Conceptually kind of at the LVM level。

 it's agnostic as to how it is actually laid out。Does that make sense？

Any other questions of the moment about。LOVM types。He。So you should be an I1， I8， I4。

 or I 16 and 32 as well。There are， I should point out that。

I'm kind of giving you just the parts of the LVM that are relevant for what we'll be doing in this class for the homework。

 so there are definitely other sized intes and there。Yes。Okay。Now about to。

Go to one of the most confusing parts of LVM slash what you'll be doing for homework 3。And that's。嗯。

Given。A pointer。To a data structure。Let's suppose I want to access some element of that data structure。

The I element of an array， the field fo of astruct and so on。

So we talked last class about pointer arithmetic。That is given a pointer to the start of an array。

 to the start of a record， to the start of an array of records。

How you would go about figuring out the address of the memory location that you want to access。

LLVM provides an instruction to do this。Abstractly。RightBecause of the L of VM level。

 as we've talked about。We're not。Specifying how it's laid out in memory。

And there's a number of different compilation strategies we could use。

 whether we're using row major ordering， column major ordering。

 whether what padding we're using in astruct in order to make it meet particular architecture's requirements。

So at the LVM level， we don't actually know the。Actual layout in memory， but nonetheless。

 there's an instruction。It kindind of abstractly， says， give an a pointer to a structure。

Here is how here is an LVM instruction that represents the calculation of a pointer to a particular element of that structure。

Now， this instruction is called get Element pointer。Often abbreviated GEP。呃。

This is like the load effect of address of X 86 or more generally all of that address computation we saw for okay。

 if I'm accessing this index of the array， I'm skipping over you know， the size of each element。

 times I， the index， and so on and so forth。You're going to be spending a lot of time thinking about this because you're going to be translating get element pointer as well as as other VM instructions down into X 86。

 So I'm going to spend a better time on this and try and make sure that we are。

Comfortable with what it is doing。Okay， so first of all。

 let's talk about the syntax and the intended meaning of get element pointer and then we'll talk about more details and we through some examples。

😊，嗯。The instruction that it takes is get element pointer。And then a pointer。A value Val。

 which is a pointer to the， let's say， the start of。The data structure。Okay， we've got a type here。

 T star has to be a pointer。If it's an array， T is going to be an array type。

With intake a sequence of indices。And the idea is that。

 let's suppose we had a multidimensional array。And were。

 let's say a two dimensional array of integers， we're wanting to access one particular element。

Then this first index would be。Essentially。The row index。

 the second element would be the column index。Okay，More generally， if the type was a record type。

A struct rather than the syndax will be telling us which element of that struct， first， second。

 third， and so on。嗯。So here's some concrete examples。呃。

Let's suppose that we have a pointer to a rectangle。Now remember a rectangle is。

Astruct with four points。And a point is astruct with two integers， an excellent Y dimension。诶。This。

This line of code is essentially。You're going to get us the， the first element。Of the rectangle。

Put it in temp1， and then this line is going to get us。The X coordinate of it。

You might be wondering why it has two indices in order to do this。

 We'll get on to that when we walk through an example of GEP。

Any questions at the moment before I go into a worked example。

 So hell So is the for the index very much。退唔住。Oh， thanks for the question。😊。

The type of the index has to be in in 32。😡，ItTs out a N of V M。For simplicity。

 we're only going to have N64 values。嗯。But in order to make sure that the output of our that our LOVM light representation is actually compatible with the LOVM compiler。

 we're still going to use these A32 annotations and you just better always make sure that your 64 bit value is representable as a 32 bit value。

Com。Yeah。Mtdie what。Val is the pointer， so it's a value of type T star。

 a pointer to an element of it's a pointer to a value of type T。Yeah。

The key thing I want to make sure that you've kind of internalized is get element pointer。

Is purely doing point arithmetic。Right，It is not accessing memory。

If you see a getm on pointer instruction。You should know that it's not going to be dereencing the pointer。

 it's not going into memory。When you implement your translation of get element pointeder to x86。

You should be having no loads in stores。Right， given a pointer。

All you're doing is point to arithmetic to figure out， hey， this is the start of the data structure。

😊，What？How do I add things to that pointer to access the correct element？Yeah。

 Ta I just where you're storing。欢。Vel is here on this example is a temporary。

 so remember a temporary is like this you know local variable that's written to exactly once kind of like a let。

Expression and MLl。嗯。And。Also remember that in LLVM， these instructions have a result。And it's。

Assign the result into another temporary。So the result of gethetto element pointer is going to be a pointer。

To whichever element you've ended up specifying。The type of the result is going depend on。

What the type of tea is and how many indices you have。Does that make sense？Next well。

 am I have just missed it for the point， the second one， why two parameters instead of one。

Let me get to that with a worked example， it's a subtlety of GEP。O。All right。

 so let's suppose that we have the following strucks， Rie。Containing an in a。

A two dimensional array of vintages， B。And another in C。And a structure ST。

That contains an element of it RT。An integer Y， and then another struck RT。So if we think about this。

 you know， kind of laid out in memory， a value of type。Struck ST。Has， first of all。X dot A。

 single integer， x dot B， which is itself an array of 200 ins。Followed by X dot C， another integer。

Followed by。Why an integer？Followed by。Z dot A， z dot B， z dot C。Okay。

A value of type struck S T or other。Suppose that we have a pointer S。

To the beginning of the value of tapestruct ST。And suppose we want to access some element within thestruct。

Particular， what we're wanting to do is。嗯。We have a pointer to ST。呃。

For those who are very comfortable with C， you may know that there's this fluidity。

Between arrays and pointers。And then if I have a pointer。To。Astruct ST。

 this is often thought of and C as being appointed to an array。Ostruct S Ts。

And so this first index here is actually saying， well， let's interpret this as an array ofstruct STs。

And this is indexing into the month element of the array。

If I actually was taking a pointer to a single。Struck， not an array of them， just a single one。

I kind of I could write something equivalent that was just S of zero。And then the same thing。

So the way that L of VM get element pointer works is。It always。

 you can think that it's always assuming that the pointer that it's given is a pointer to an array of T。

And that's why the first index is often zero。Right， that if it's not actually an array。

 you just a pointing to a single element of it， Well that's equivalent to saying the  zeroth element of the array of。

This thing。 So what you'll actually see in a lot of code is get element pointer。

 the first index to it is0。 And indeed， that's what we saw in the example on the previous slide。

This is a subtlety of get element pointer。You'll probably want to go back to this example and think you way through it。

To make sure we're understanding what's going on。O。Let's go through and see how。

The elements in the C expression。Correspond to the things in the LLVM get element pointer。

First of all。S here is an aer to， as I said， an array。🤢，Ostruct S T。

So here we're saying get on when pointer is taking as its first argument。The point to。

To an array of ST。Here I guess we should see the translation of the typesstruct RT。A32。

 two dimensional array。In an 932 ST consisting of an RT。An A32 and another RT。This a。

Getting an element of the array pointed to by S corresponds to the first index。Of。Of get El pointer。

The next。Oh， and I should point out that the type of S1 is， of course， a struck ST。Right。

So we can access in either field X Y or Z。We're accessing the field Z。

Which in the translated type is the。0，1。Second element， so that corresponds to the index2。Okay。

 the field Z。Is this one here？The type of that sub expression， the result of the dot Z access。

Is a value of typestruct RT。So at the sea level， we're able to access。Aray。B。Which is the。0。

The one element of that struct。 So that corresponds to the index1。Over here。From there。

 we're accessing the fifth row。That is。呃。At the sea level， that。Dot z。b expression is of type。

An array of a two dimensional array of vintages。10 by 20。Right。

So we're accessing the fifth row of it。 that five here corresponds。To this index 5。

The result of that is an array of integers of length。20。Of which we're accessing the 13th element。So。

A coupleup of things I want to point out with this。 One is that。The translation of this。

Access of an element of the data structure。Was translated。

In a pretty direct way to get element pointer。And the LVM types allowed kind of， if you will。

 a more uniform representation we simply used。Intergerenddices into the appropriate field of a structure or into the appropriate element of an array。

I also want to emphasize that。This instruction at the sea level。

You'll see it's actually taking the address of。This location。If you were to execute this。

 this would not actually do any memory access。Given a point of value， S。

All it's doing is computing another pointer to return back。Point it to this element。And indeed。

 in LVM。That's also happening Remember get element pointer does not access memory。

 all it's doing is pointer arithmetic。Now， the pointer arithmetic that we would actually be doing。

We translated in the。Ovious way into assembly without any padding。Would be that。

From the base address。The S contains。Would be。Skipping over one entire copy of ST。

Because of this index， we're skipping over the zero with entry to start pointing to the month entry。

We are then looking at the second element of the struct。

Which means that we're skipping over the first element。A value of type Rt， so the size of Rt。

Then we're getting to be the multidisional array， which means we're skipping over the first element。

The integer A。That is， we're adding the size of an I32。嗯。爸爸。Oh， I'm sorry， I misspooke。

 the say 32 is from the field in way。Over here。Then we skip over the field in A and RT。

 and then we are accessing the appropriate row。Fif row， so five times the size of a row。

 that is 20 times the size of mint。Within that particular row， we're going to the appropriate column。

 13 times the size of the element of the array， which is an I32。Right。

So if we had a straightforward representation of the trucks。And room major order。

This would be the address computation that we'd be using。And again， just emphasizing。

No memory access going on。 This is really just about。嗯。Figuring out the pointer address and moreover。

诶。Doing the size computation here is actually based on how we're doing the layout。 So it's。

 if you will， a lower level assembly level notion。Gett element pointer is allowing us to kind of abstractly refer to。

 hey， the pointer that takes us to this element， whatever you happen to translate that to an assembly。

So。If we don't know the length of B， then we can't actually have a struct like this。

We at the language level， we wouldn't be able to have an array of unknown length。Instead。

 the way you do it is you'd have a pointer to an array and you know the size of a pointer。今日。

Any questions？Tk just to confirm S TY gets computed in the。Compilation。Right。

 so when will you end up compiling LVM2 assembly and you end up making concrete choices for how you're going to lay outstructs and memory。

 what padding you're going to use， whether you use room major or column major layout。

That's what's going into this actual address computation。Up here， though。

 we're kind of abstractly thinking about it。 We know it's going to be allowed out in memory somehow。

 and we know that from the base address， yes。You're going to be able to compute the memory address of the element you want to access。

Okay， so that's kind of how to think about get elementement pointer。Given a pointer to astruct。

Implicitly an array ofstructs or an array of some data type。

 Gi element pointer lets you compute an address into some element of that。

It doesn't dereference the address， okay， only doing point arithmetic。

 it doesn't actually traverse any links of a data structure。

If you have a data structure that does have pointers。Like let's say， a binary tree。

What you'd be needing to do is use get elementement pointer to get the right element of the node that you're looking at。

And then。Follow the pointer， that is load from the pointer， do you reference the pointer？To get。

A new value。Or to get the point of value of the node you're pointing to and then do another get element point to compute the appropriate field access there and so on。

So if you have a data structure with pointers， you're going to be needing to load to get the point of value and perform another GEP on it。

 GEP does not access memory。Okay。You might be thinking that I spend a lot of time on that。

I'm sure that you'll be going back and looking at these lecture slides and maybe the lecture video as you're working on homework three。

😊，Okay。When we compile a data structure from C into LO VM？The basic idea is that we would。

Or from any high level language rather， not just see。

 the basic idea is that we would translate the high level language types into some LOVM representation type。

For C， this is pretty straightforward。😊，But for other languages might end up being relatively complex。

 So we talked about how an Ocal array types might be translated into a pair that explicitly represents。

The size of the array and the array， multidimensional arrays are going to be translated into an array of pointers to arrays events and so on。

When we access the data， we're going to be translating them into get element pointers and depending on how we're translating the data structure。

 we might need to do some loads。So， for example， our multidimensional array is an array of pointers。

To arrays。 and we want to access a particular element。

 We might translate that into a get element array， followed by a load。

 followed by another get element array。So the type system of LLVM is pretty neat。

 it allows us to translate a lot of the structured data we've been talking about。

In a relatively straightforward way， just by having thesestructs， arrays， pointers， named types。

There are times though， when the type system of LOVM is not expressive enough。For what we want to do。

 So in particular， we might have a source language that say has subtyping。

So when you have two differentstructs and you're allowed to treat a value ofstruct A as if it were a value of typestruct B。

So it allow you to do this。 L O VM has a bit cast operation。 This essentially allows you to take。

A value of a given type。And cast it into a value of another type。So here we have two strs， let's say。

 a two dimensional point and a three dimensional point。And if I have a three dimensional point。

In many ways， it's okay for me to treat it as if it were a two dimensional point。

Any read or right could do to a three dimensional point， access the field。Sorry， either way round。

Anything I could do with a two dimensional point， I could read from X。The first field。

 I could read from why， the second field， I could write into them。

Any of those operations would also be okay with astruct with three dimensions， X， Y， and Z。And so。😊。

呃。Let me appraise that as anytime I have a value with。Of type rec 3。

 it's okay for me to treat it as a rec2。Because anything I can do with erect rec2。

 it's okay to do on a rec3。So here's a bit cast， I've got a pointer to erect three。

 I can simply cast the type。From a point to a rec3 to a point to a rec2。And then use it at that type。

In this third line。What is that percentage one？Percent one is remember that the percent is how we refer to a temporary。

Value， like a local variable that is assigned to exactly once。 So percent one was the result of this。

Stack allocation， so this is creating memory storage on the stack for this struct with three integers。

So percent one is a pointer to a 3， right so percent rec 3 pointer is the type of percent one。呃。

Very soon you'll be reading these L VMIRs。Easily and yeah， you'll be used to them very quickly。

Any questions at the moment？Yeah， Maxwell。If you were to go in the other direction with the third field。

 just be whatever happens to be in memory。Oh so why is this cost safe？

Why is this cast okay or or I guess that if you cast from rank three direct two。

 you just take the first two fields？The same as they were， if you were to go in the other direction。

Oh so one of the things I want to emphasize is。The value in percent2 is exactly the same as the value in percent one。

P1 is appointed point to some memory location。Percent2 is appointed to the exact same memory location。

So when we talk about taking the first two elements。We're not actually moving any data at all。

 It's really just。Hey， this region of memory that I was interpreting as being astruct with three integers。

 I'm now going to interpret it as being astruct with two integers。And that turns out to be safe。

 You can look at， you can take C， S 152 for those in the class who haven't to learn about why that's the case。

嗯。If you went the other way， if you said， hey， I've got a regional memory that has。

Then I'm interpreting as a rec too。That is， as a pair of vintages。Hey。

 I want to treat it as if there were three integers in there。That's when you might be in trouble。

Becauseuse suddenly， what you're saying is。You know， I'm going to treat that next。

Double word in memory as if it were an integer。And maybe in the actual memory， it's not an integer。

 maybe it's a pointer。And so I'm suddenly starting to override a memory location。

 treating it as if it were an integer。And somewhere else in the program is interpreting as a pointer。

 So that would be an idea of an unsafe cast。So casting from rec2 to rec 3 would be unsafe。

And could cause all kinds of problems in your program。So I'd say in general。

 bitcast needs to be handled carefully， but the idea is it's this escape hatch on the expressiveness of the LVM type system to let you encode source level invaris。

Appropriately or maybe compilation in variance。 you， as the compiler writer。

 might be enforcing various things in your program， and you might know that it's safe to。

To do a cost。To treat value at a different type。Any more questions？Okay。We've got lake。30 seconds。

 so。You know。I'm not really going to do much of an overview of Home 3。

 but it's available for you to download。Just like。诶。

You can take a look at the readme to find out what's going on。 You can read the documentation。

That's with it a。诶。Explaining what the homework is， the files that are in。

In the directory and suggestions on how you go about implementing the compiler。嗯。

There is also in the documentation。The speck of LOVM light。Okay。

 so trying to be a clear and thorough explanation of the limited subset of LLVM that we'll be dealing with in homework3。

嗯。One of the things that we have in the homework is an LLVM interpreter。

 you can actually directly interpret LLVM code to see what it's meant to do and there's kind of an explanation of the abstract machine that you're dealing with so that you can kind of understand here's what it means to execute an LLVM program and your compilation。

 your translation to X86 should be doing analogous or equivalent behavior。



![](img/60f1668b5989d516af954497a9ced61c_1.png)

When you do it。嗯。We've got a。嗯。The driver has some interesting。Command line options， you can end up。

嗯。Invoking your compiler， that's the CS153 back in， the thing that you'll be implementing。

 but you can instead use the claim compiler， so use LVM's compiler from LVM to X 86 assembly to see what that does。

 you can end up interpreting the LOVM code directly， you can end up printing X86。Code， so if we。

 for example， run。嗯。Try to compile a simple LOVM program。

We get a failure because we haven't implemented the compiler yet。But we could end up。

Compiling it with clang。And then even executing it within this driver harness。

Getting us the result of 5 plus 9，14。And there's more things you can。ItsRight， come on。툭。So again。

 I encourage you to start the homework early and don don't hesitate to reach out to course staff post on  Ed for any clarifications。

 And in particular， if you have any trouble setting up the development environment。

 you do need playing installed Lium installed if you have any trouble with that。 just post on  Ed。

 Thanks very much， everyone。 Good luck with those who are finishing up homework too。

 And I'll see you all on Monday。😊，そきや。か。我た毎。

![](img/60f1668b5989d516af954497a9ced61c_3.png)

![](img/60f1668b5989d516af954497a9ced61c_4.png)