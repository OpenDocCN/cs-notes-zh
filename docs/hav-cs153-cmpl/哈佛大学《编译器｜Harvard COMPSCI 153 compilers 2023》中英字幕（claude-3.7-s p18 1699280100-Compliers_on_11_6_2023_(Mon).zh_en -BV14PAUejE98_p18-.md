# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p18 1699280100-Compliers_on_11_6_2023_(Mon).zh_en -BV14PAUejE98_p18-

It's important。I saw you。ButThat was26 than Daniel was taking one believe。



![](img/5dcee591d4d1856a223a8c603126fd83_1.png)

I'm not。

![](img/5dcee591d4d1856a223a8c603126fd83_3.png)

Welcome， everyone。Let's get started。So announcements， homework 4， as you know， is due today。😊。

With the course up to the three days worth of late minutes the standard and course as always。

 if there's any exceptional circumstances， late minutes aren't meant to cover that so feel free to reach out and let me know。

呃。I will'll also say。We're getting to a stage of the semester where people might be feeling like they're running low on late minutes。

 I will be giving everyone more late minutes with the same limit of。In general。

 up to three days worth for any。For any particular assignment unless there's exceptional circumstances。

 but you can keep on using late minutes for additional homeworks。Again， when you submit homework for。

 please fill in the same survey form as well， it's just really useful to know kind of how what your experience of the homework is like。

 just really appreciate that feedback from you。And the pace keeps on going。

 We're almost at the end of the semester， but we still have two homeworks left。

 So homework 5 is being released today。We will be going over a bit of the homework in the class at the end of the class。

 particularly the type system and talk about what's involved there but。

In brief homework  Five is continuing to extend the front end of the OT programming language。

And so the scaffolding code that we're handing out for you。

 the starting point actually includes significant parts of the work that you're doing for homework for。

😊，So what this means is essentially at a time when everybody has submitted。嗯。

Everyone has submitted homework for we'll be releasing homework 5 in the meantime if you want to get started on it please just email the course staff@ CSs153ta@cs or post a private message on Ed and we'll get you the homework 5 files。

嗯。It is due Monday， November 27th， three weeks， but that is of course。

 as was just pointed out to me the Monday immediately after Thanksgiving。So I'll say a couple things。

 one。If you want， you can of course submit something early and say I'm done with it。

 so of handing it in before Thanksgiving might be possible for you。

 the amount of time that a homework assignment takes is highly variable I think within the class often based on the bugs that you get and how long it might take you to solve a bug so。

I appreciate that it can be hard to predict the amount of time。

 one very general piece of advice that is applies to most significant software engineering projects。

 including the homework assignments here。It's often really。

 real useful to not write a single line of code。Until you know what it is you're going to be writing。

And by that， I mean， actually taking time to figure out， okay。

 how you're writing this down to functions， What are the functions meant to do。

 Do I understand how the function is going to。Compute that or do that。

 And that work actually in many ways， forces you to go through a lot of the design process that you might otherwise encounter when you。

 if alternatively， you start writing code and encounter a bug and then need to rethink something。

 So a piece of general advice is。It's often really useful to lay writing the code a little bit。

 This might help reduce some of the variability based on bugs that you come across and how long it takes to track down a bug if you're kind of clear on what the spec of various parts of your code is。

There was a tangent。 This was all to say you can of course， finish before the Thanksgiving break。

 or remember you've still got the three late days late minutesness that you can use for up to three late days so you can。

 in fact， hand in。By 1159 PM on November 30th， giving you a bit of time after Thanksgiving break。

 So hopefully you will get a chance to spend a bit of Thanksgiving， resting， recovering， relaxing。

 and otherwise helping you get through。😊，Get through the semester in one piece。Any questions？Okay。

So in today's lecture， we're going to keep on looking at subtyping。 So if you recall。

 we've been looking at type systems。 We've looking at the idea of subtyping， we're going to dig into。

A bit more details about subtyping， looking at some more complex language features。

 including subtyping for functions， subtyping for records， subtyping for references。

And then we're going to hopefully have a significant bit of time at the end of the lecture to take a look at homework 5 in particular go over some of the type system in homework 5 and make sure that we're comfortable with the ideas in there。

Okay。So we've been looking at subtyping of of various types。

 we werere kind of introducing the notion with thinking about subtypes， sorry。

 thinking about types as representing sets of values。

 thinking about subtyping as essentially being a subset relation。

 so the set of all positive integers， we made that a type pause that is a subtype of the set of all integers。

We can think about extending the subtyping relation to other types， so one would be two pools。

And so extending it to tus is actually pretty straightforward。

And one of the handy ways to think through the subtyping relation is。

When a program expects a value of a particular kind， let's say S1 cross S2， a two of two elements。

 S1 and S2。When is it okay to give it instead a value of type T1 cross T2。

 So that is what are the situations when T1 cross T2 is going to be a subtype of S1 cross S2。Right。

More generally， that。That notion of subtyping， often known as the。

The fundamental principle of subtyping。Its one is a。T is a subtype of S。

 if anywhere the program expects a value of type S， you can instead give it a value of type T。

So when we think about twoples。If the program was expecting a value of type S1 cross S2。

What are the things that could do with the twople with two elements？

All it really could do is get the first element。Or get the second element。

So anywhere a program is expecting a value of type S1 cross S2。

 all it's really able to do with it is pull out an S1。Pull out nest2 from that twople。

And what that means is。If it's got an S1， what sort of values are okay， well， any subtype of S1。

Same where there S 2， if it expects a value of type S2。

 it's going to be okay to give it any subtype of S2。

And this gives rise to the  tapping rule for twoples。If T1 is a subtype of S1， T2 is a subtype of S2。

Then T1 cross T2 is a subtype of S1 cross S2。To make that a bit more concrete。

Pause cross an egg as a subtype of int crosscentt because paw is a subtype of int。

And NAG is a subtype event。Sos we a program that took a pair of vintages？Took the first value。

 first element of the two pool。 the last element of the two pool did something with them。

 They add them together。Would be totally okay to instead pass in a pair of a positive integer and a negative integer。

Any questions about？That relatively simple example of the tuole。Okay。Right。

 hold those concepts in mind， this idea that if you expect a value a programme is expecting a value of type S。

 it's okay to give it a value of type T。When T is a subtype of S。now let's think about functions。

So suppose I have somewhere in the program is expecting a function。Of type S1 to S2。

And I have a function of type。T1，arrowO T2。When is T1 RO T2 a subtype of S1ROOS2？That is win。

If the program expects a function of type S1 R S2， when is it okay for us to give it a function of type T1 RO T2？

We have some hands， right。I think you love to because some asked too。That's。お杯？好。

So your intuition there is good。That the substyping relation doesn't go the same way。

For the argument and for the result of the function。W， did you have a。Additional。Comment okay。

So let's take a look at this and think about how to build up an intuition for， to be honest。

 the often counterintuitive subtyping rule for functions。Let's suppose that we have a function。Right。

 it's of。Type T1， arrow T2， it takes in values of type T1 as an argument。Returns values of T T2。

We want to give this function to a place in the program that's expecting。A function from S1 to S2。

That is the place the program is expecting it。It's going to be treating this function as a function from S1 to S2。

 So that is it's going to be passing in values of type S1。And expecting to get back。

Values of type S 2。So when you see it like this。It perhaps makes a bit more sense than order for T1 R T2 to be a subtype of S1 R S2。

It means that we need to be able to take a value of T S1。And convert it to a value of type T1。

In order to use as our function for it。Our function gives us back a value of type T2。

Which we need to somehow convert to a value of S2。Which is what the program is expecting。

So that is what we need is that S1 is a subtype of T1。And T2 is a subtype of vest。

Which means that the relationship is kind of the other way around。

We want the argument type to be contravariant。Is one a subtype of T1。

But we want the result type to be covariant。T2 a subtype of S2。So see that as a typing rule。

You can see it here T1arrow T2 is a subtype of S1arrow S2。As follows。

When we're contravariant in the argument， S1 a subtop of T1 covariant in the result。T2。

A subtype of vest2。Any questions about subtyping for functions。Yeah， do you extend this to。

Like functions that take an arbitrarybit in brew。Thanks， Mamo。Well。

 we actually just saw the answer on the in many ways。

 the previous slide when we thought about the subtyping for twoples。So well。

 actually there's two things going on， right？😊，One is that the argument of the function could be a tuple。

 right， You take multiple arguments。And it。In which case there's still a place， right。

 You want the arguments。S1 and T1 to be contravarit S1 needs to be a subtype of T1。

 even if that's a tuple。Alternativelytatively， you might be thinking about cur functions。

Where let's say the result type is itself a function。Turns out the same thing a place。

S2 and T2 are function types。We still want this relationship to hold T2 is a subtype of S2。

We will be using the function subtyping judgment。For two or two0 minute。嗯。

So it's worthwhile sitting down and trying an example。Let's say I have a function， in， arrow。

 and arrow in。And figuring out。呃。What types would be a subtype of that and which types wouldn't be？

Thanks for the question。Any other questions about this about function subtyping？O。Well， let's start。

 Let's move on to another， another language feature。 Let's think about immutable records。

 So these are。Records that we're familiar with from Ocael。Where you can't modify the contents。

Of a field of a record， that's what immutable means， we can't change it。

So basically it's a generalization of tuples right instead of having a field indicated by its position。

 the first， second or the third element， instead we have labels。😊，Dran from a set of identifiers。嗯。

So these are the typing rules for。Con this is the typing rule for constructing a record value。

You'd have label 1 equals E1， label 2 equals E2 up to level n equals the n。

Assuming that E1 up to EN were appropriately typed， T1 up to TN。Then this is the record type。

For that expression。And then really the only thing that you can do with a record value is。

Other than sort of passing it around storing it， passing as an argument to function。

 the only interesting thing you can do with a record is actually just project one of the fields out。

In the same way with the two pole， the only interesting thing you can really do with it is。Get the。

Pllud an element from that tuple。Any questions about？

Record tape and the typing judgments before we start talking about record subtyping。Okay。

 hopefully the notion of immutable records is clear and intuitive from your own experience。

When we think about。Subtyping。We actually have。At least two different options。

how for when to allow a record。Ariip one record type to be a subtype of another。

The first approach is known as depth subtyping。So here the idea is。If I have。Two record types。

Which each have the same set of labels。 So label 1 up to label N。With depth subtyping。

 I just require that。The corresponding type of each label。Is covariant。

So that means this record type。Its a subtype。Of this ricotype， if for label 1。T1 is a subtype of U1。

T2 is a subtype of U2 and so on。 So this is just covariant subtyping。In the in the label types。

So are we。Let's think about why the subtopping rulers sound， where it makes sense。Okay。

 so this fundamental idea， this fundamental principle of subtyping。

 is anywhere a program expects a value of the supertype。

It's okay for us to get a bit of value of this subtype。And intuitively。

 if the program was expecting a value of the supertype。

The only interesting thing you could do with it is project out one of。The fields。Right。

 so let's say I project it out。Label1 it's expecting a value of U1。So as long as it gets a value。

 that's a subtype of U1。Let'sSay T1。Then it's going to be okay。Ths will work out。

 So this is why record subtyping is covariant in the label tapes。

An alternate kind of subtyping for record types is known as width subtyping。So here the idea is。

The super type。Might haves label1 up to label M。As long as the subtype has the exact same labels。

Plus， maybe some more。Then the subtype relation is okay。Now intuitively。

 that's because if the program is expecting a value of this supertype。What could it do with it。

It could project on label 1， could project on label 2。Up to label M。Right。

It could project out those M different labels。The subtype has those M different labels。

 So anything you could do with the supertype， a value of the supertype。

 you could also do with the value of the subtype。The value at the subtype may also have some more labels。

But， that's fine。Right。They'll just never be projected when it's treated at the supertype。

But this idea， the fundamental principle of subtyping， still holds。

So any questions about these two different kinds of subtyping， depth subtyping， and width subtyping？

So I think I understand with subtyping， but let's say if we go back to positive in the integer case。

 I just thought of the subtype is the smaller。Tech， right。

 like the positive numbers are so much smaller。I'm using however in the let's say with subtping。

 right because this less than an equal to relation is sort of flipped。

 it looks like the subtype is the larger。So how do you reconcile it？嗯。

That's a really great point that I've given a few different intuitions for subtyping for types in general。

 first intuition I gave for types was it's an approximation of the computation。

Second intuition that was that you can think of types as being a set of values。

And now with subtyping， the intuition I gave was， you know， a type as a。Subtype， if of a soup type。

 if wherever you expect a soup type， you can instead have a subtype back。

These are actually all compatible。 These intuitions with each other in many settings。

 the way to think about the type for records。Is that when we have a type label 1 up to label M。

 this represents the set of all record values that contain at least label 1 through label M。

 but they may contain many other fields as well。So when you think about it like that。

Let's suppose this is fo and bar。The set of all records that contain full of type int and bar of type int。

 plus any other fields。 That's a really big set of possible record values。

 And the set that has full of type int， bar of type int and ba of type string。Is a subset of that。

So this is how you end up making sense of it。 that for these record types。

 it's saying these are the fields that I know exist。But there might be others。おします。はい。All right。

 thanks。Okay， now for those of you who took 152， even saying， yeah， yeah， yeah， yeah， yeah。

 we covered all of this subtyping stuff when we took 152。So that's great。

 hopefully have some at least some people in the class have a lot of familiarity and comfort with subtyping。

😊，But this is a compilers's class， so we're actually wanting to think about how do we implement？

These programming language features。And so what does subtyping mean for records when we think about how we actually implement？

A record。So。We've already talked in class about how we would compile astruct。

Put it into memory coniguous contiguously in memory。

 each field has a section of memory memory associated with it。

 maybe with padding if that's needed for alignment and so on。嗯。

So with that notion of laying out of astruct of a record。The idea of with subtyping。

Is really compatible with it。When we lay out。Astred with fields X and Y， let's say of type N。

 those would be contiguous pieces of memory， X and Y。And if we had a structure with X， Y， and Z。

We'd be laying it out X， Y， and Z， or next to each other， contiguous in memory。And。

The layout for the field D X and Y is the same in both the supertype and the subtype。

offset of zero bys from the pointer， offset of， let's say four base from the pointer for dealing with 32 bit integers。

So what happens in that case is for the subtype， the extra field is just ignored。 right。

 You're passing around the pointer to thestruct。You're accessing fields appropriately。

So that works out great。Let's think about dip subtyping。Well。If we had dip subtyping。

Without wood subtyping。That's also compatible。RightAs long as we assume that whenever we have A a subtype of B。

 then A takes the same amount of space as B。So if that's the case with depth subtyping。

 we have a record， let's say with three elements。Types S1 is 2 S3。

 a subtype of it would have types T1， T2， T3。Where T1 is a subtype of S1。

 but they take the same amount of space。 T2 is a subtype of S2。

 but they take the same amount of space。T3 is a subtype of S3。

 and they take the same amount of space。So this would all work out as well from the initial pointer to thestruct。

You， the first element with zero Btes offset， second element with however minibs offset。

Same with the third。Unfortunately， though， if we tried to combine with the depth subtyping。

Then we run into problems。So why is that， what would go wrong？

If you tried to mix width and dip subtyping with the kind of Cstruct， contiguous layout。Approach。

I would do verse。You were going to ask this exact question， what happens when you combine them？

So what goes wrong， Austin？We might have like if。So we have like disrupt Xyz， and XY。

 like XYZ is a subtype of XY， but it takes more space。

And you might have that as like what are the elements of a label。讲社会。

And then the elements themselves don't the same last me。That's right。

 You've got the exact right intuition there， but。Yeah， this thing about depth subtyping。

 it really relied on the fact that subtypes took up the same amount of space。

So that even if I had a subtype in there， I still knew the offset。To get to。 But， of course。

 if we're using wood subtyping， subtypes do not take up the same amount of space。

 They may take up more space。Which means that。If I'm dealing with the super type。

 it might be hard for me or impossible for me to figure out the rate offset to access a field。

So if I had a struck where the first element was itself astruct of。

And different types had different widths。How do I know where to look for the second element of thestruct？

um。So let me pull up one more。嗯。Issue on this。With with subtyping。

That is where a subtype could have more fields than the supertype。

One important thing that I gloss over is that kind of the order of the fields need to be the same。

All right。That is。The field。Coning the record containing field X and Y is not the same as the field containing Y and X。

Because in one of them to access the X field， it's an offset of 0 and the other one to access the field X。

 it's an offset of four。诶。And so again， in CS， S152。

 we looked at this a much more permissive notion of subtyping of records where you could allow。

The order of the fields to be peruted。And from a programming language point of view。

 that might be totally fine， a value of one type cand as the value of the other type。

 because all you can do is access a field by the name of that field。

But if we wanted to seestruct style implementation， laying fields out contiguously。

Then that subtyping rule isn't compatible with our compilation strategy。

So this is all to say that the design of the language。And the compilation。

Techniques that are possible go hand in hand。Right。

If you want to use a particular technique to compile values。To compile various types。

 that's going to restrict the subtyping relationships on them。By contrast。

 if you wanted a more flexible and permissive subtyping relation on records， say。

You could achieve that， but your implementation， the way that you compile it。

Would would need to reflect that。So for example， if we allowed permutation of record fields。

Our compiler would somehow need to make that work at the low level implementation。

One possibility is that you might sort the fields。Before generating code。

 that it doesn't matter what order the programmer declared them in。

You're actually going to sort them， let's say alphabetically。

 before you generate the code to try and get them in some canonical order that's compatible。

That would allow these two types to be equivalent because implementation ways they're going to be the same。

The challenge， though， is that you need to know all of the fields in order to generate code。

Which may not always be possible。And also I'm going to guess what you're going to say。

 let's have a guess for it， let's hear it I was going to ask about like in this implementation。

 what if we have onestruct like X Y Z and then you have like astruct if we're allowing like things to be。

You would have that like XY is a subtype of XYz， but then Yz is also a subtype。It would be。

You meant if it was sorted， it would be different from type right。So that's a great point where。

You're saying with these record types， you know， you can have。

Different and incompatible subtypes of them。And this approach doesn't really seem to work out。

 And that's， and you're right， that's getting to this idea that you need to know all of the fields in order to generate the code。

So you'd need to somehow know， okay， I have a。Closed set of fields that we're going to use， and。

Maybe and so when you generate the layout for the struct with Yz。

 you might need to make space for X in order to make it compatible with this layout。

 so it might get pretty complicated and you might need to make assumptions or requirements about closed world compilation。

 you know everything you know all of the subtypes， that are going to be used and so on。

So it gets complicated with that approach， you can make it work out。

I'll also mention in passing and let you think through the details that this permutation approach。

Isnt directly compatible with subtyping。I know it leads to。At least with this。

With a C struck like contiguous layout。Yeah， is subtyping causes so many errors。

Annoyances during compilation， what's the benefit of it？What subtyping gives you some very nice。Oh。

 so okay， just repeating the question，ca I was told that I need to make sure it's recorded。

Given that I seem to be pointing all of these issues with wood subtyping。

 why on earth would you want a programming language to have wood subtyping？

Turns out that it's really useful for expressiveness。 So to be able to say。诶。You know。

 the kind of classics example might be we talk about like oh， 3D point is a subtype of 2D point。

 according to width subtyping， you know， everything you can do with a 2D point， x and Y coordinates。

 the 3D point allows as well。But if you think about object orientationiented design。

 there's many situations where it kind of looks like wood subtyping。

 right superclass has a subset of the fields of the elements that you want and your subtypes。

 your subclasss enrich it。Provide additional information。 The kinds of things might be。

 I have a person。And in my system， some representation of a person。

 some people in my system are students and have things associated only with students。

 Others are employees and have things associated with employees。 Others are。I don't know。

 emergency contacts and have additional information associated with them。

 So it's a very natural way to you know， have this hierarchy。

If you will of types where subtypes include more information about things and then want to be able to write reusable code。

 I want to be able to write code that does things handles all people in a uniform way。

 even though they might be employees or they might be students and so on。

And I will say that the problems I've been pointing out are actually with a particular compilation strategy。

嗯。And I really just want to emphasize this idea that。

The design of the language and the compilation strategies that they enable， they go hand in hand。

And it's not to say one is better than the other。 It might be that there's a very efficient compilation technique。

Which is wonderful if your goal is to make things run very fast。

 but it might limit the expressiveness of the source program。

Which might be bad because it makes it harder for programmers to write clear andambiiguous obvious code。

By contrast， you might have an incredibly expressive source language that lets you express things very crisply。

 clearly， elegantly。But to compile it。Might be less efficient。

So one example of that is if we wanted to allow。The kind of width and depth and permutation subtyping of records。

We absolutely could do it。But we'd need a different compilation strategy。

So one of the things we could do is represent these records。

Say by having a more complicated data structure instead of laying it out contiguously in memory。

You can imagine having a dictionary。Something that said for this field。

 here's where you go to for the value。Right， and maybe and there's a number of up。

There's a number of implementations you can imagine。

 One would be simply you have an object that is a sort of arbitrary key value dictionary。

Or the one that are shown on the slide here。You might have a dictionary that sort of has the names of the elements and then points to let's say contiguous。

Piece of memory that for the values， just sensorly showing the permutation and showing the offsets for。

 for those particular fields。Right。So this would work out。

But of course you can imagine the downsides。 in order to access an element might require some additional memory accesses。

with the resulting。Memory pressure， poorer cash performance， and so on。

Any questions at the moment about this？Subtyping records。Okay。

So I'll note that we were talking about immutable records。RightRe where once you've created it。

 you can't actually modify the values。If we add mutability。Into our constructs。

This actually changes in an interesting way， the subtyping relation。 So think here about references。

 you know it's those like memory locations like we see in Ocal that are mutable， that mutable arrays。

 say like we have in oat at the moment。So I'm going to talk soon about subtyping and mutability。

But first， another issue that comes up when we think about。Let's say， references。And raise is。

The question of an null value。So。First of all， what is the typing rule for null。

 what is the type of null？It's。We could definitely have， say declare an integer array。

And we assign no to that array。So this seems clearly okay， right？And this is because intuitively。

 we can think of at sea level， we often think of arrays as really just being pointers or something。

 So having a null pointer means like， okay。We're just not pointing to anything at the moment。

 It's not a valid array。What about。And x equals now。그 miss。Is this like an o currency？

So you kind of got to the point that， you know， this is going to depend on the language。

 This is part of the design。 And theres， there's nothing really innate about null。

 It is actually a design choice。For what you're going to do。 So let's think about C。

 Let's get our intuitions right for C at the moment。So inter of AN null would be okay。

Isn't exercise nu okay and see？I think it is says normal zero。Yeah， it probably is。 What about Java。

What about a language with actual strong types？再家。It wouldn't be allowed in Java。

Assigning no to an int。嗯。About a string， let's say。What language are we talking about now？Yes。嗯。

The way most languages think about null is。That it actually is generic。

In some ways that for any reference type。It can have any reference type R， with a reference type。

To be honest with you typically means that it's going to be implemented viaa with a pointer。

That it's referring to something in memory， whether or not that thing is immutable or mutable。

But a lot of languages actually have this notion of reference type with the possibility of a null value。

O Caml doesn't right， It doesn't actually have a null value。

 if you want sort of a possibly null type， you actually construct a data type or an option type。

 right， You either have none or some。Value。Bden languages like C++。Java。嗯。In others， these。

These reference types do allow a null value in them。Thishich is kind of generic， and just means。

We don't have a non trivialvial value。The thing about reference types is part of all you can a value of a reference type is that you can dereence them。

 given an array， you can look up an element of the array， given a string， you could， you know。

 look at a character in the string。So this begs the question of what about type safety this idea that the situation that when we have a world type program。

 if we have type safety， it means that we're not going to get an error at runtime。

And you're all probably intimately familiar with getting no pointer exceptions or Seg faults when you try and dereference null。

At the language design level， if you wanted to have a type safety guarantee while also having null as a value of reference types。

The means you're going have to define behavior when you're dereferencing null。 In Java。

 this raises an exception。So that is it has behavior that's defined within the language for dereencing null。

And in terms of。Implementation to make sure that you have the well defined behavior。

 it typically means that any time you dereence a value。Anytime you say follow a pointer。

 you do actually need to check。That it's an appropriate non null pointer。

The way this is typically implemented in hardware is instead of doing a direct comparison。

 there's normally some lower level hardware trap mechanism that if you attempt to dereference null。

 instead of throwing a seg fault thatll allow it'll raise a trap that the program can end up handling appropriately。

Yeah， mark。Why would you implement this at the hardware level once ago go？

Where would we implement it at the hardware level rather than at the software level。For efficiency。

 so。If you're doing it at the software level。You might ask， you know， we're in the software。

Abstraction， doing end up doing it。 you can imagine actually doing it。

Very high up at the source code level with a whole lot of earth statements。Right。

 if the value is null， then。Raise nu pointer exception else and then do the thing that you know you want to with a non null value。

You can imagine doing it when you're generating assembly that you are。

 when you see that a dereence of a。Of a reference value that the assembly code you output。

Actually does that， you know， let's test this point of value against null， if it's equal。

 then jump to here else， you know where you raise an exception。

 otherwise you fall through and you actually do the operation。So those would work。

 but they end up being inefficient by contrast if the hardware is raising a trap。

 the trap might be expensive， but in the common case where you don't have that null pointer exception。

 it's typically much faster。Does that help？Thanks。Okay， so that's nu values for reference types。

Let's think about subtyping though。So if we have a reference or more generally mututable location。

 say such as in an array。What is the appropriate subtype relation？

So let's develop our intuition for this with an example。 Let's suppose that we have。No zero。

As a type， as a subtype of int。Okay， so nonze contains all of the nonzero vintages。

Which is a subset of the set of all integers。And let's suppose that our division operation has the type int。

 arrow， non zero arrow int， that is the divisor has to be non zero。So nonze is a subtype event。

 should it be the case that a reference to nonzero is a subtype to a reference event。So that is。

 is it the case that anywhere the program expects a value of type in a reference to an integer？

A mutable location that contains an integer。 It's okay for us to go of it。

A reference to a nonze integer。Hands up if you think this subtyping relationship is good。Okay。

Hands up， if you think it's bad， something will go wrong。Hands up if you're not sure。

It should have been everyone in the class kind of was。 was there another option that I'm missing。

Okay。It turns out that this relationship is not a good one。

We're going to be able to write a program that if the subtyping relationship were true。

We're going to get into a bad situation。 We're going to get to a situation where we're going to be dividing by 0。

 So let's see an example of this。Okay。So。A， variable a here。Is。An int riff。

A point to a location that contains an integer。If nonzero R was a subtype of event R。

 this assignment would be okay。 R is a nonzero R。 We're assigning R into a。Great。In the second line。

 we're assigning0 into a。This is okay because A is of type in。

It's a pointer to a location that contains an integer and 0 is an integer。 So this line is okay。

But of course， once we perform that assignment。A and R alias each other。

They both point to the same location。So when we dereence R。

Even though R is meant to be a non zero refth appointed to a location that contains a non zero winterteger。

At that point right there it contains zero， and as a result we do a division by zero and things go bad。

So it turns out that the subtyping rule for references should not be covariant。It also turns out。

The contra varianceance in the reference type。Is also bad。It also leads to problems。

I'm going to leave that for you to figure out。Like try writing a program that if you assume that intRF was a subtype of non zeroro ri。

You could write a program where something bad happens， let's say you do division by zero。

It turns out that for references， for mutable locations， we actually want。Invariance。

And the same is true of arrays of mutable records， object fields， anything that is mutable。

 anything that is upable。 you actually want to be invariant in the subtyping rule。嗯。Now。

 what's really interesting is that in Java and C sharp。They kind of got this wrong。

In the sense that in Java， for example。嗯。If C is a subclass， subtype of object。

An array of C is treated as a subtype of an array of objects。So what this means is that。

Just like with a null value， they actually need to do runtime checks to make sure that if you put a value into an array。

 even if it's well typed。That at runtime， the object。

 the array that you're using allows the value of that type to be put in it。 So that is in Java。

 they actually compensate by adding this dynamic check on every array update and throwing an exception if you do something that would lead to a bad situation。

Now， the designers of Java and C sharp are not stupid people。Though we're aware of this。

And it was a trade off。Essentially， what was going on at the time was that within object oriented languages。

呃。Polymorphism。That you need。To allow that typing rule。

 it hadn't actually really been figured out how to do polymorphism in an object oriented language like Java or C sharpp。

嗯。So what they wanted to do was allow people to write。

Programs that would operate on arbitrary arrays。But they didn't have polymorphism in there。

 so what they did instead was they allowed people to write algorithms。

 code that worked against an object array。And that allow an array of。A C array。

 an array of objects of class C to be passed in instead。

 so they deliberately allowed covariance in the array subtyping to get this code reuse。

Then a few years after Java language was released， they did figure out the polymorphism。

 Java version 5 has appropriate polymorphism that they could。

 at that point of gotten rid of covariance of array types。

But it was part of the language and would have broken backward compatibility if they got rid of it at that point。

Okay。嗯。Just really quickly on mutable。Values， mutable。Entities。

 another way to think about it to see why we need invariance is you could think of a reference cell。

It's kind of being like an immutable record with two functions。With and some hidden state， right？

So it's got like a get field that you apply this get function to unit and you get back the current value of the reference。

 and you've also got a set operation， you pass in a new value of type T， you get back unit。

 and that updates the hidden state。Okay。So if you think about it like that。

 the get allows you to pull a value out of a reference and set thats you put a value in。In order for。

A value of type T ref， sorry， Not for T ref to be a subtype of S ref。

It means that kind of anywhere would have a value of。A record get unit to S and set S to unit。

Anywhere we're expecting a value of that type would it should be okay for us to instead pass in a value of type T ref。

That is a record with。Get and set that return and take a T。So if we think about it like that。

 subtyping on these records is covariant。So we'd need。The get field。

Unit arrow T to be a subtype of unit arrow S。And would need the set field T arrow unit to be a subtype of S arrow unit。

So we'd need these two subtyping relations on functions。嗯。Which according to the subtyping。

Relation on functions means that。From get， we want covariance in the result type。

 so T should be a subtype of S。But because of contraverance in the argument type。From set， we want。

Is to be a subtype of tea。So this kind of motivates why。You know。

 we want T to be a subtype of S and S to be a subtype of T。

 meaning that they really need to be the same type， they need to be equivalent。

That's kind of the intuition for why we want this。Invariance of subtyping through references。

Curitively， it's because the reference can both produce a value。And consumer value。In general。

 when you have something that consumes a value， it needs to be contravarit。

And that and the type of the value it's consuming。If it's producing a value。

 it needs to be covariant in that type。Any questions about mutability？Subtyping for it。

One final thing I want to talk about with subtyping before we jump into homework5。

The idea of structural versus nominal typing。So。This is a design choice in a programming language is whether the subtyping relation。

Between entities is based on the structure of data。Or the name of data。So the。Clarify what I mean。

Let's think about。Type abbreviations are no camel。Versus the new type language construct in Haskell。

So I know camel。😊，Which we're familiar with， you can define。A type sense， you dollars and cents。

 sense are an integer， so we're going to define sense to the int。

We're going to define age to also be an int。 Okay， so sense an age or int。And then。

That means we could write a function that takes x of type sense， wave type H。And add them together。

 And this will type check。Because since an age of both integers， we can add integers together。

 awesome。If we tried to do something similar in Haskell using new tapes。

 we could declare sense to be essentially an integer。We could declare age to also be an integer。

And if we try to do the same thing， write a function food that takes sense and age and returns an int。

This would actually be o typed。Even though we're implementing both sense and age with integers。

 they had different types。And we can't end up mixing them like that。

So what's going on here is that an Ocal。These type abbreviations are treated structurally。

 If the types have the same structure。They're regarded as equivalent。By contrast and Haskell。

These new types are treated by name。Even if structural it's the same type。

 if it has a different name， its regarded as being distinct and they can't be mixed。In Java。

 it's also nominal subtyping。 The idea being that。The relationship between types is based on their name and essentially the subtype or subclass relationship needs to be stated explicitly。

So， for example， in Java， we could declare an interface fo。

That and any object that satisfies the interface is going to have a method on it calledF takes no arguments and returns in it。

Here's a class C。That does， in fact， have a method called fo that takes no arguments and returns an int。

However， C does not implement the interface through。That is。

 if there's somewhere in the program that expects a food。You could not pass it an object of class C。

And that's because Cd does not explicitly implement the food interface。By contrast this class D。嗯。

Has the same method and implementation of it， But D does explicitly declare that it implements fo。

 And so somewhere in the program that expects a fo can be given an objective class D。Okay， so。

Structural versus nominal subtping， great。こじ。Like idea basically what people name when they sayduct typing。

Duck typing is。Similar tostruct， structural。Typing duck typing is like the idea that comes' sort of the quote。

 if it looks like a duck， quacks like a duck， it is a duck。The idea that if you have a。诶。

A value of a given type。What you really care about are the things you can do with the operations you can do in it。

 So as long as something has the same operations。And it's okay to use it at that type。嗯。

Duck typing comes up in languages that are。Either。Essentially untyped or weekly typed or dynamically typed。

It doesn't。If you had duct type in in a strongly typed language。

It's essentially the same as structural  tapping。Cameron， do you have any， Yeah。

 I would sayduct typing in a strongly typed language ends up looking a lot like Star。

It depends a lot on how you expose it syntactically， I think， but I think at the end of the day。

 it ends up being very similar to what we just described as structure。Yes。

Thanks for confirming my intuition。Okay， any other questions about structural。

This is nominal subtyping。Okay， in that case， let's spend。

Quite possibly the most useful for you 15 minutes of the lecture。

 talking very briefly about homework 5。 So homework 5。

 we're going to be extending the Oat programming language。

 The key changes to the language that you'll be implementing are we're going to be addingstructs。😊。

Awesome， so this is a change to the kinds of values that are allowed。 Strs are going to be mutable。

 So like Cstrs， you'll be able to modify a field。We're going to be adding function pointers so that you are going to be able to do things like write a write code that expects to take a pointer to a function。

We're not going to be implementing closures。Just function pointers。

 So this is going to be kind of closer to C style function pointers than to。

Functions as values in a functional programming language。

Probably the key thing that's going to be happening is。

You're going to be implementing the type system。So in our type system， we're going to have。

Nllable references。 So there is a null value， like you've had node version 1。

 that our types are actually going to distinguish between reference types that are definitely not null。

And reference types that maybe no。And so as a result。Because of this。

The fact that we're using these is definitely not nu types。

We're actually going to add a couple of new language constructs to the language。

 First is a checked downcast。 We're actually going to have a special language construct that takes essentially a maybe null reference type。

😊，Value。And if it is not known。It will downcast it。To a subtype， the definitely not null。

A value of definitely not nu type。To let you use on the program。

We also are going to add a way of having a raise。They're clearing an array of definitely not null types。

So if you wanted to have an array of definitely not old types。

You actually need to provide a not null initial value。For every element of the array。

 normally the thing you do in a language is to clear an array， create an array。

 and it would be filled with null values， and then maybe you'd go and replace those null values with not null values。

That's not okay to do if the element type of the array is definitely not null。

 So we're going to add a construct that。Essentially gives you an explicit way of initializing every element of the array with an index。

 So it's kind of like。呃。You'll be able to have an index I。

 and then you write code that initializes the Ih element of the array。

 and essentially you'll compile it by creating a full loop。That goes and uses that code to provide a。

No no value。To be the initial value of every element of the array。

We are providing a PDF that includes the grammar。And a type system for the language。

Now there's a lot of different type judgments。In the language。

 there's going to be a subtyping judgment。 So we're going to be very clear and explicit about the subtyping relationship between types。

We're also going to have a judgment that tells you when a type is well formed。

 when a type makes sense。 The type system is complex enough that you do actually need to check if a type makes sense。

As well as things like typing rules for expressions， for statements， for function declarations。

 for programs and so on。So what I'd like to do is spend a bit of time actually going over the P D F。

For Oat version2。This is on the homework page of Canvas so you can go and take a look at it。

 even before you end up asking for the homework 5 code， you can look at the PDF。嗯。Let's take a look。

Our grammar for types include int and bull。But we also have nullable types and not null types where riff here is。

A reference type。 So so having a question mark after the reference type means that it maybe it's null。

Right， no question mark means it's definitely not no。Our reference types include string。A raise。

Function pointers。To a function that takes arguments t0 to Tn and returns a value of type Rt。嗯。

And then we can use parentheses to indicate the structure of these things。

And we also have named mutable record types， Strs， yes， we'll see that in just a moment。



![](img/5dcee591d4d1856a223a8c603126fd83_5.png)

Return types are rather。T。Or avoid。A program is simply a list of declarations。

Epsilon here is the empty list， so a program is either the empty list or a declaration followed by a program。

 a list of declarations， there are three kinds of declarations of global declarations。

Global declaration of a variable。Global declaration of a function。

 You're familiar with these from O version 1， but we are also adding a type declaration。

 So declaring a newstruct type。 I'll see that in just a moment。Global declarations。

 global I and the initializer expression。Function declaration， return type， name of the function。

 the arguments， and the block that is the function body。

Here is a type declaration uses the keywordstruct。The name of the of the type S and then fields。

 which is。Which is a sequence of field declarations。Expressions in the language。

 you can have a null value， but you do actually need a type annotation。

So this is because we mentioned that null is generic。嗯。

Ode version2 is not smart enough to figure out what type you should treat nu that。

 You actually need to provide an annotation for it。True false integers， strings， variables。呃。

These forms of declaring a new array you're familiar with。

 but here you can provide an array with a explicit initializer ID here is going to be a variable name and then the expression is going to be the expression to initialize an element of the array and as we'll see in the typing rules it can refer to the identifier here。

Creating a newstruct。It's the main things。Feel free to call out questions as I go through this。

Those are the key changes to the grammar。Oh， here we have a checked downcast。

So this is a looks like enough statement， it's got an if question mark and the guard。

You have to give it a reference type， the name of a variable， and then an expression。

 If the expression is evaluates to a not null value， it'll evaluate the then block。Otherwise。

 it will evaluate the optional else block。Yeah哋。Pick a picture question。

 but are there any like major languages that？Use this sort of。Necessarily not normal type to。

Howlp programmers or is it more of their performance？Oh yeah。

 there are some languages like Ocal where there is no null value and you need to explicitly。You know。

 have a type that allows for。Optionally having no value。嗯。

It's been a while since I programmed in rust， and even then I did pretty shallowly。

 rust has not all types， right？Nods I see nods from people who have programmed more recently with rust than I have。

嗯。U top of my head， I can't think of any others at the moment， but what do we have from people。

 go has not nu types？Yeah， thanks。I script does it。And what does Ty script has not no types。 Co。

 thanks。 So it is pretty common。 It gives you。Both a performance win because kind of statically you can prove that a value is not null so you can actually admit those dynamic checks before you do reference it to see whether it is null or not。

 but perhaps more importantly， it actually rules out really， really common kinds of errors。

I don't know if you all do this， but when I'm on a website and it doesn't work。

Pretty often I'll open up the JavaScript console and see what's going on。

And pretty often the thing that is going wrong is an oldD reference。

 the written code is that does something expecting a value to be not null， and it is， in fact， null。

 And these are you know， often pretty major sites with I'm not saying it's Google， but it's you know。

 sites with thousands of users and as in they have serious developers working on them。😊，And yeah。

 they mess it up。 and that's in part because。Those kinds of errors can often be really difficult to reason about。

Having the types actually lets you reason about it in a local way where the type is enforcing an invariant。

A useful invariant。Okay。Let me get on to。The type judgments。

So I mentioned there's a lot of judgments here are the subtyping relation between types enter the subtype event bull is a subtype of bull。

嗯。And maybe known type。RF 1 maybe null is a subtype of riF2， maybe null if RF1 is a subtype of riF2。

嗯。A definitely not null type Ref1 is a subtype of a maybe null Ref2， if Ref1 is a subtype of RefF2。

Note that these premises that I'm highlighting actually make use of a different judgment。

 a judgment that has the subscript R。Next to the tune style， and that's this judgment here。

Which is the subtyping judgment for reference types。 which is that string is a subtype of string。

 arrays are invariant。T array is a subtype of T array。The T has to be the same subtyping for strs。

You can see that we have。With subtyping here。And not depth subtyping。Subtyping for functions。

Subtyping for return types。Type wellformness。This is the typewoforminness judgment for types。

 which makes use of typewoformness for reference types。Which essentially is just making sure that。

When you use the name of astruct type。That structure is well defined in the context H。

 the set of defined types。We have typing rules for。Expressions note that Reff nu。

 we check to make sure that refs。The type annotation is well formed。

What else is useful to point out here？Well here's the  tapping rule for the explicit initializer。

 new T x1 x1， here is the length of the array， and here's the initialization expression。

You'll see that X2 is type checked。With x of type nt。

 x is the index of the position that you're initializing with the x per  two。

X2 has to be of type T prime where T prime is a subtype of T， the element type of the array。

So this is how you would construct。And not null value for an array of not null。A base type。嗯。

Know that when you are constructing astruct type， the fields may be permuted。Right。

 you don't have to。To clear the fields in the same order as thestruct。Let me。

Jump down to the bottom of the file。To kind of show you how a program is type checked。

So here's the typing judgment for a program。But actually。

 you can think of it as happening in several passes。 right， So， first of all， we use this judgment。

This is judgment to go over a program and produce H the set of defined struct types。Okay。

 so we can look up here for that judgment。Right here。You can see that here's the base case。

 empty set of declarations just taken the same age that you got passed in。 but otherwise。

 what we're doing is。If we seestruct S， we essentially addstruct S to。诶。

The type environment that we pass in to take a look at the rest of the program and get back H2。 Yeah。

 Mattdie。's H is the type declaration environment。 H is going to be the。List of definedstructs。

So it's going to be so that essentially includes the name of the struct S and the fields of the struct that were declared。

 and we're going to need that information to make sure types are well formed。So this。

What this is saying is that， first of all， you go over the program to pull that out。

And this is telling you the rules for how to pull it out。 You ignore global variable declarations。

 ignore function declarations， type declarations you kind of add into the type context。

 Keep on going until you reach the end of the program。Using that H。And G0， which is。

The initial context containing binding through all of the built in functions。Within。Pull out。

All of the function declarations from the program to produce G1。You can take a look at the。

This judgment here that essentially just goes through， ignores the global declaration。

 global R declarations， ignores the type declarations， pulls out the function declarations。

To add them into this。The global Na construct。contexttext。Once you've got G1。

 which includes the oats。Built in functions， plus the function declarations。

You then do a passover to program to pull out the global variable declarations。

You can look at the inference rules for that， that gives you G2。

So this contains all the global declarations。 You then use H and G2 to type check the program itself。

So we're going to scroll up to show you that judgment。That's this one right here。嗯。

It essentially checks to make sure type declarations are well are appropriate。

It Ty checkcks sort the function declarations， which includes T check in the function bodies。

 turns out we don't need to type check the global variable declarations because when we pull them out。

 we ended up checking them appropriately。And then you can dig in to see how function declarations are done。

Feel free to go if you need to head， I am just going to spend 30 more seconds。Telling you about。

The return analysis of functions。So when we type check a block。

When we take check a sequence of statements， we're actually going to determine whether or not。

That sequence of statements definitely returns。Or maybe doesn't return。Right。

 so this is checking to make sure that every function definitely returns。嗯。

You can go and you can check， but it turns out that。嗯。

We want to make sure that a lock definitely returns， that's the symbol capital T。嗯。

If I have a sequence of statements。Everything except the last statement has to be able to maybe not return。

Right， so that we don't get any dead code。 You don't get。

code that looks like x equals 7 return x y equals8。

 that y equals8 will never get executed because you always return。

 so this typing rule is actually preventing that situation。

So you can go through and figure out how this returns part works here。

 but the key idea is it's an analysis。The type system is making sure that your functions have return statements as appropriate。

And you can look to see how that plays out in these various taping rules。Okay。

 apologies for running a few minutes over over。 Hopefully。

 that's useful to you for when you get to homework 5。

 you'll be able to go back to the video video and look at these notes on the inference rules。

Good luck as you finish up homework4。😊，Remember， if you want to start on homework 5 early。

 feel free to reach out to the course staff。Thanks everyone， and I'll catch you on Wednesday。U。

Remember， if you want to start on homework5 early， feel free to reach out to the course staff。

Thanks everyone， and I'll catch you on Wednesday。

![](img/5dcee591d4d1856a223a8c603126fd83_7.png)

![](img/5dcee591d4d1856a223a8c603126fd83_8.png)