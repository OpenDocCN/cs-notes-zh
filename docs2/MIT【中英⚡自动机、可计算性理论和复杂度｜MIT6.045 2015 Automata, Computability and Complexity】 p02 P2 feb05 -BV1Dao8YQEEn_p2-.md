# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p02 P2 feb05 -BV1Dao8YQEEn_p2-

嗯。系y。Alright， so。maybe I'll just get startedcause I just have some。

 some administrative stuff to go through， which is， you know， on， on， on the Web anyway。 But since。

 since you're since you're here on time， you can have the treat of hearing me say it in person。

 So so we， we have figured out a a recitation schedule。 so。

 so the recitations will start tomorrow and you have three choices。Something rat on。Thanks， okay。

 all right， thank you。So， so， so you can， you can， you can choose which recitation just by showing up for one of them。

 You know， if， if it's too unbalanced， then we'll have to do something about that。 But and the。

 the T As also each one has office hours。 And those are， those are listed on the syllabus。Okay。

 and the， and the office hours are in the open space， just just outside of my office。

 So it's an J G6 theta。My。This is the that's my office。 Okay， so I I， I。

 I realized that yesterday I yeah sort of went through a lot of basics of the course。

 but I didn't say anything about whether you should be taking the course or not。

 So so just briefly the the， the prerequisites for， for the course。 So the。

 the only one that's listed formally is 60，4，2， So so basically a 60，4，2 or some， you know。

 equivalent mathematical background。 so， so basically， you know， it's。

 it's good if you come into this course， you know， knowing your way around a proof， you know。

 knowing how to knowing how to prove something you know， knowing what， what induction is。

 things like that。 it is it's certainly helpful， you know， if you have。

Programming and you know algorithms experience。 we're not going do any actual programming in this course。

 but， you know you know that experience is helpful。

 But the main thing is just you know some mathematical maturity Okay so okay。

 so one thing that a lot of people ask about is whether they should take 604，5 or 68，40。

 which is sort of the graduate version of this class that's taught by Professor Spser。

 So so there is a lot of overlap between them。 but， but they're also different， you know。

 and I'd say the main difference， you know， beside just differences in style。

 is that this course has sort of less depth but more breadth。 So we do a lot of stuff in this course。

 like cryptography and quantum computing that's not done at all in 68，40。

 So if you want to take like one course on。Theoretical computer science that will sort of maximize your exposure。

 you know， to things。 then I'd recommend this one6，8，40， you know， has you know。

 a little bit more mathematical rigor like they'll'll。

 they'll prove things that will be okay a hand wave in this course。You know。

 and and that that one pretty much covers exactly the the contents of of Siper's textbook， whereas。

 you know， in this course， we just will just sort of dip in and out of it。 And， you know。

 also do plenty of stuff that's not in the book。 you know。

 if youre really serious about theoretical computer science。

 then it would not hurt you at all to take both courses。 and by the way， 604，6 has very。

 very little overlap with this course。 you know， 6046 is about， you know。

 finding ways to do things to solve problems And， and this course is about， you know。

 understanding what you can't do， you know， understanding let's say what are the ultimate limitations。

 Okay so so so they complement each other very nicely in that way。 And， you know。

 you can take either one of them for your header。 but but again， you know。

 wouldn't hurt you at all to take both if you have room for it Okay so。

So what I wanted to do today is， do like our， our， our first drill examples of models of computation just。

 you know， to get our feet wet， but， but also。See some， some really interesting models。 So， I mean。

 I think the， the， you know， maybe the， the， the most basic model of computation that there is or。

 you know， the， like the， the simplest one to to talk about is， is that of circuits。

MaybeI'll leave this up for a little for people who are just coming in。Okay， so。

 so just Boolean logic circuit。 So， so what's a circuit。 Well， so if you've taken doubleE classes。

 you know， you've seen circuits that have things that look like this or something or something like this or I don't know exactly。

 Okay， but in any case， you know， they have all these different components in them， you know， and。

 and there's always a closed loop， right， because you know。

 the the electrons have to flow all the way around in a circle。 Okay， in。

 in theoretical computer science， ironically， circuits are never closed loops。 Okay。

 that's like the one rule about them that they have to be acyclic。 not contain any cycles。 Okay， so。

What we mean by a circuit， basically， is， a sort of a network of logical operations。

 So where you start out with some bits that are given to you is input。Like， let's say X， Y and Z。

 And then you can do operations on them。 So we have。The not gate， for example， that just， you know。

 if x is 0， then it outputs 1 and if x is 1， then it outputs 0。No。

 and there are symbols for all these things。 But I'll。

 I'll just write the names of themcause that that that， that's easier。 We also have the and gate。

Which outputs one， if it only if， you know， both of the inputs are one， okay， and。We have the orgate。

 which outputs one if either or both of the inputs are1， and otherwise outputs zero。呃。

We have the X or gate， which outputs one if the two input bits are different and outputs 0。

 if they're the same。 Okay， or in other words， just outputs， there sum modular 2。Okay， and。

And then what you're allowed to do is build up a more more complicated logical operations by just stringing a bunch of these together。

And， you know， feeding the， the output of one into the input of another， so。So to take an example。

 let's say that we wanted to compute the majority function of3 bits， X， Y and Z。

 meaningan we just want to know， you know， are， are the majority of these bits equal to one。 Okay。

 how could we do that using， well， using the gates that I that I， that I listed there。

Yousing let's say and or not goods。So I just want to know if at least two of the bits are one。Yeah。

Yeah， we could do it with X or you know， And， in fact。

 there's a way to do it using only and and or gates。 We don't even need， yet need anything else。

 yeah。嗯哼。😊，Let's see。 Let's try that。Does this work， Unfortunately， I don't think so。 So。

 for example， suppose y is 1 and x and0 are 0， right， then you're gonna get 1，1，1， even though yeah。

 So， okay， but this， this sort of almost works。 Gu anyone。 Yeah， fix it， yeah。Yeah。Yeah， there we go。

 so。So let's say we just。And x and Y。And Y and z and x and Z。Okay， and then we just or all of these。

 So， so we could do that， you know， if I just say。I just ore all of them。 Now， now。

 I didn't explicitly tell you that you're allowed to have an or the of three things， right。

 the the number of inputs to a gate， by the way， we call the fan in of the gate。 Okay， so I didn't。

 I didn't tell you that we have an or a fan in 3。 But that doesn't actually matter。 Why not。Because。

 well， because you can build one anyway。 Okay， all you have to do is or two of these adss。Like that。

 And then or the result of that with the remaining end， right， because the。

 the or function is associative， right， you can just or by， you know， you can keep taking or's。 And。

 you know， and， and this is equivalent to just the or of all the things。Okay， so。

 so thatll that this will represent the majority function because it just directly encodes it， right。

 It says， you know， it's just sort of looking for any pair of the bits that are that are both one。

 And as soon as， you know， it finds one of those。 then the you know， then the the， the。

 then the circuit is happy。 right， so。😊，Okay。So， so， you know， we can build， of course。

 much more complicated things。 you know， we could build a circuit that perform binary addition onto numbers written in binary or that multiplied them or or that or that ran windows or or or Linux。

 Okay， don't worry， I'm not going to ask you to do any of those things on on the P that's。 Okay。

 but if you take you know， in your systems courses and， in computer architecture courses。

 you will basically learn or or have learned maybe how to design adders and multipliers and things like that。

 just just just by stringing a bunch of logic gates together。 of course， you know， this， this， this。

 this is。This is what's going on， you know， in in your computer at the， at the lowest level， right。

 in some sense， you know， the what， what a transistor is， is， you know， it's precisely like。

 a solid state， you know， physical device that allows you to implement things like and and ore and not gates。

 you know， in a very reliable way。 right， because， you know， you can use you know， a very。

 very weak current to control a much more powerful current And， you know， and that， you know。

 once you have that ability， you can sort of use it to， to construct logic gates。 Okay， so。嗯。Okay。

 but now， you might still be， be worried about something， which is， you know， I just。

 I just listed a few specific gates， right， you know， the an gate， the or gate， the not gate。 I mean。

 who's to say that this is a complete list， right？ I mean， you know。

 even if you were able to use your transistors to build those gates， right， why， you know。

 as soon as I want to do something else， why， why， why shouldn't I need some some other logic gate。

 So， so this leads us to sort of an important concept that will you know。

 show up again and again in this course。Which is the concept of of universality。 Okay， so。啊。

So in this context， you know， let's say， if I give you a set of logic gates like and or in not。

 you know， we'll call the set universal。If by just stringing together gates in that set。

We can represent any Boolean function on any number of bits。 Okay。

 so this is just a little bit of notation， right， I mean。

 this means that F is a boolean function that takes n bits is input。

 So its input is an element of the set 0，1 to the n， meaning its input is a string of n bits。 Okay。

 N is output is a bit0 or1。 Okay， now it's clear that if we can， you know。

 create any boolean function with one with a one bit output。

 then we can also create any boolean function with however many output bits we want because we just。

 you know， you know， have one circuit to output the first bit。

 have another circuit to output the second bit and so forth。

 So that's so so that's the reason why we can， we can just concentrate for simplicity on on circuits that produce one B as their output。

😊，U。And so， you know， so， so it's not， you know， entirely obvious a priori that there's， you know。

 any finite set of gates that， that's going to be universal， right。Okay。You know。

 one thing that I that I， that I always dislike in。

 in math classes is when they give you a definition and they never tell you any examples of anything that doesn't that don't satisfy the definition。

 right， like you know， an elementary school。 I had to memorize what， you know， what's commutative。

 What's associative， right， but it's completely pointless。

 If you've never seen anything that's not commutative or that's not associative， Okay， so。So let me。

 so， so let's see some examples of things that are not universal。 Okay。

 just just in order to see that， you know， that that universality is not a trivial concept。 right。

 what， what， what's an example of a set of gauges that's not universal Anyone in the sense that cannot be used to represent every function。

 yeah。就是。Yeah， if we only had the identity gate， Yes， absolutely。 good example。 Okay。

 we could only compute the identity function。 Alright， what's another example， yeah。😊，Yeah。

 if we only have the not gate。 Well， you know， you're never gonna be able to compute anything that involves more than one bit B。

 right， every bit will be its， you know， will be its own island。 Okay， no， no， you know。

 no to ever talk to each other。 Allright， what's another example， yeah。Yeah， so。嗯。

And and or fails to be a universal set。 What can and and or not represent。Not， Yes， yes， and， and。

And， and what's the reason for that， why can't they represent not， yeah。嗯哼。Mmhmm。Well， okay， yeah。

 I mean， you， you can， okay，'re， you're， you， yeah， you're。

 you're absolutely sort of grasping toward the Yeah。 So there's a word for what you're。

 you're trying to get it。 The， the word we use is monotone。Okay。

 so and and or are are both monotone functions。 Montone means that if you change one of the inputs from 0 to 1。

 then that can only ever change the output from 0 to 1。 right， you know。

 or it could also leave the output unaffected， right。

 But changing an input from 0 to 1 will never change the output from 1 to 0。 Okay。

 that's what monotone means， yeah。Okay， so， so， so， so， so this this actually raises a good point。

 which is when we talk about universality So this is， you know， this is just a convention。 You know。

 this is， this is a choice that we can make， okay， but。Were we're in this class。

 We're going to say that constants are available for free。So。Which means， you know， you can always。

 even if you have a 2 bit gate， you can always get a 1 bit function by just feeding， you know。

 like a 0 or a one， you know， into one of its input wires。 Okay。

 you can always just fix one of the input wires to be 0 or one， right， and then， you know。

 restrict the function like that。 Okay， so you could always，😊，For example， if you had an end gate。

This will， you know， you could represent just just X itself。 like that。 Okay。

 by just saying the end of x with one。 Okay， so， so that's just a technicality。 But， but good point。

 Alright， so， so， so and and or are clearly both monotone functions， right， changing。

Right they both satisfy this and the， the property of being monotone， you know。

 is closed under composition。 So， you know， if I take two gates that are monotone and， you know。

 I string them together， I still get a monotone function。 Okay。

 and whereas the not function is clearly not monotone。 Okay， so so that。

 that's why this set fails to be universal。 Does anyone know another set。

 a different set of Boolean gates that's not universal。There's。

 there's basically one other interesting possibility。It's， it's one that's already been on the board。

 actually。Yeah。Yeah， X or。In fact， I can even take。X， or， and I can throw in the knot gate。 Also。

 Okay， X or and not。 this will also fail to be a universal set。 What， what。

 what am I not able to represent using X or and not gates， anyone。 yeah， and， for example， Okay， w。

 why can't I represent the and function using X or and not gates。Okay。Yeah。Yeah， that， that's true。

 But， you know， but， but I'm allowed to string together a whole bunch of Xor gates， right。

 So I still need to say， why can I never get an an gate， no matter how many XOs I put together， yeah。

Oh。呃。So I'm not， I'm not sure I understand that， but。嗯哼。Mhhu。Mmhm。Yeah， yeah， okay， okay。 So， so， so。

 so ultimately， you know， I want some sort of invariant， You know。

 I want some property that's going to be preserved。

 no matter how many X or and not gates I string together。 but， you know。

 but which is not satisfied by the end function。 Okay， and yeah。Yeah， yeah。

 The property that I want here is， is actually is linearity。 Okay， you know。

 with and and or preserve that the function is always monotone。

 X or and n preserve that the function is always linear。 What do I mean by linear here。😊，嗯。

I actually mean linear modo 2。 Okay， so linear over the field that has two elements。 Okay， so。

 so I can think of。The x or of x and y， if I interpreted it algebraically。As。

 as an arithmetic operation on bits。Then it's just x plus y mod 2。 right， That's all it is。Okay。

 if I interpret not as an arithmetic operation， what's not， anyone。1 minus x。1 minus x mod 2。

 In fact， it's also one plus x mod 2。 Okay， you know。

 if you're mod 2 plus and minus are the same thing。 Okay， but you know。

 now these are both linear functions， right， so you can compose these， you know， like you could have。

The x or of x and y。And the XO of that with Z， for example。

But that's just going to give you X plus y plus Z， M， you know， mod mod 2， right。

 you're always going to have a linear function in your input bits。

 no matter how many linear functions you compose， you're never going to get a quadratic function。

 For example， Okay， but what is and as an， as an algebraic function， mod 2。Yeah。Yeah， exactly。Yeah。

 so。Although way， you know， this， this correspondence between， you know。Bolean operations and。

 and algebra。 This is， this is why we call them Boolean operations in the first place。

 because George Bull in the 180s， you know， noticed this correspondence。 I mean， I mean。

 I I I guess someone had had to be the first to do it， right， so。

Discoveries back then were sort of easier to make， Okay， so。Alright。

 but so and does a degree2 function。 You know， you're never going to get it by， you know。

 composing all the these linear operations。 Okay， so an interesting fact which maybe I'll put on on PS at 1 is that these are sort of the you know。

 monotonicity and linearity or in some sense， the only two ways for a a collection of Boolean gates with constants available for free to fall short of being universal。

 Okay， so， so in other words， what we're saying is that is that and this is， again。

 a very sort of general phenomenon in computer science。

 universality is sort of the rule rather than the exception。

 you have to you actually have to work somewhat hard to， to avoid being universal， okay。😊，And。

So without further ado。Let's see why if you've got the and or and not gates。

 then this is a universal set。 Okay， so remember， the definition of universal is that， you know。

 we we can use these gates to express any boolean function on any number of bits。 right。

 So we need to give a construction that does that。So。Which means that in order to prove this theorem。

 you know， we'll have to start out with some arbitrary boolean function。On end bits。

But we could also just do an example， you know， as long as it's。

 as long as we make it completely clear that， you know， what we do in our example would， would。

 would generalize to any， you know， Boolean function。嗯。So。Sorry。

So how can we represent an arbitrary Boolean function？ Well， theres， there's， there's a。

There's a general way to do it， which you may have seen before， which is called a truth table。 Okay。

 truth table just means， you know， you list every possible combination。

 every possible setting of the input bits。 Then for each one， you list， you know。

 what output do you want。Alright， well。So。For example。What's the truth table of the and function。

 anyone。0，0，0，1。 Yeah， the truth table of the or function is。0，1，1，1 Tru function of the X function。

 anyone。0，1，1，0。 Yeah， okay， so now I could make up anything that I want over here。 I'm like， let's。

Let's do 0，1，0，0。0，0，1，0。You know， there， there， there is a nice boolean function。 Okay。

 and now I have to show how to represent this， you know。

 arbitrary boolean function by a circuit of and or and knot gates。

 So can anyone suggest how I might go about this。Yeah。Mmhmm。MYep， so， yeah。 so， in fact， you know。

 all I can， that that's exactly right。 You know， in fact。

 I can just look at those rows that output a one。 Okay， you know， in in， in fact， what， what I。

 what I can do is I can just look for you know， those。😊，Okay， in this case， there are。There are。

 there are two rows of this function that that lead to the output1， right， And so basically what。

 what I'm trying to say with my circuit， right， what， what my circuit is yearning to express is that。

 you know， you should output one， if the input is this or if the input is this and otherwise you should。

 you know， you should output 0。 So how can we express that。How can we give voice to that。

 to that statement， yes。Exactly， so all I've gotta do is for each of these rows that out the leads to a1。

 I just and， you know， I， I I， I implement a check that asks whether all the bits have the prop。

 you know， have， have the right setting for to be that input。 So in this case。

 it's not X and not Y and Z。 Okay， for this row down here， it's X。😊，And why。 And not Z。Hey。

 and again， I could implement these， these ans as， as ans of ans if I want them to have only fan in 2。

 Okay， and then what do I do at the end。Yep， and then I or it。There。

 I just represented this function。 Okay， and， you know， in a way where， you know。

 we could clearly generalize this to any truth table of， of any size。 right， So， so incidentally。

One thing that， you know， will， will interest us a lot， although we you know， we'll。

 we'll only have the tools to， to really start to understand it later in the course is。

Is the size of a circuit。Okay， by the size of a circuit。We just mean the number of gates in it。 Okay。

 so， so this construction that we saw here， if you've got a boolean function of n bits， what is。

 what， what's an upper bound on the size of the circuit that that this construction will produce。

Well， how， I mean， how big is the truth table， first of all。

The truth table has got two to the n rows in it， right， any of which could have a one in it。 Okay。

 for each of those rows， how much logic are we using to， to， to check for that row。Yeah， okay。

 that that's， you know， that that that， that， that's gonna change things by a small factor depending on。

 you know， whether we， Alright， So， so one， so one， one thing about this course is that， you know。

 all the habits that you've learned of like being really precise and calculating things that all goes out the window in this course。

 Okay， and we're gonna， yeah， what。Yeah。Yeah， well， so。Well， we， we wan to know the dependence on Ed。

 right， We wna， what。So， okay， so， so what can we say， So， so each。We want to， So。

 so what's going to concern us is like， is， is asymptotics。 Okay， so actually。嗯。So， so probably。

 you know， most of you have already seen O notation in 60，4，2 or or whatever。 But just。

 to refresh your memory about it。 let me， let me show you the。

 the notation that we're gonna be using a lot in this course， okay， so， so we're， you know， we'll be。

 we'll be very interested in， you know， the growth rate of function。 So in this particular example。

 we'd like to know just the， the rough growth rate of the number of gates in the circuit as a function of N。

 Okay， that's what we want to know。 And， you know， we don't。

 we don't care that much about the leading constants。 I mean。

 we can work them out if we if we really want to。 But。😊，But mostly。

 we're interested in what can be captured using this notation。 So， so F of N， let me say。

 is big O of G of N。If there exist constants， A and B， such that F of n is at most。

A times G of n plus B for all N。 Okay， this， by the way， the， this means for all。

 this means there exists。 Okay， so， so what that is saying， you know。

 if you unpack it is it just saying that F of n is， you know。

 grows asymptotically at most as fast as G does。 Okay， so G is an asymptotic upper bound on F。Okay。

 so。For example。We could say。That n squared is big O of n cubed。 Okay， You know。

 this grows faster than this does。 Okay， we could even say that。10 n squared is big O of n squared。

 Okay， because we don't care about the 10， right， that that can just be absorbed into this constant A here。

 Okay， but it is not。It is not true that N cubed is big out of n squared， okay。

We say that F of n is big omega of G of n， if。There exists。Constant a greater than 0 and B。

 such that F of n。Is greater than。A G of n minus B for all N。 Okay， so this is say。

 this is saying just the converse thing that that that G is an asymptotic lower bound on F。 Okay。

 when you go out to large enough ends， then F grows asymptically， at least as fast as G grows。 Okay。

 and so in in， in theoretical computer science， you know。

 this kind of statement is very highly priced。 we like to prove lower bounds on。

 on the complexity of things when we can。😊，So， you know， we can make the opposite statements here。

 n squared。Is not。Theta of n cubed。 by the way， some people， you know。

 if they really want to be pedantic， they'll say n squared is contained in big O of n cubed， right。

 because like， what is what the hell does it mean to set this equal to this anyway， right， you know。

 this， this is， this is actually a set of functions that contains this。 Alright， but， you know， I'm。

 I'm just sort of using it equal sign as a shorthand for is， right， Like if I say Bob is tall。

 You know， I'm not saying that the concept of tallness coincides with the concept of boness。

 you know， so， I'm I'm I'm just using it to mean is。 Okay， so。All right， and you know。

 but we could say that N cubed is。Omega of n squared。Okay。Okay， now。

We say that F of n is big theta of G of N。 If just both of these things hold F of n is big L of G of N。

And。It's also big theta of G of n。Okay， so this means that F and G grow asymptotically at the same rate。

 Okay， that means that you have act， you have really pinned down the rate at which F grows。

 if you can make a statement like that， A big theta statement。And then there's one last one that we。

 we sometimes like。We say F of n is little O of G of n。If for all positive A， there exists a B。

Such that。F of n is at most。It is less than A G N plus B for all N。 Okay。

 so this is saying that F of N grows at asymptotically less than the rate of G of N。 Okay。

 so it's saying that the G of n is an upper bound and it's， and it's a strict upper bound。Okay， so。

 so we could say that n squared is little L of n cubed。 That's true。

 But 10 n squared is not little L of n squared。So。Quions about these。 Alright， so we'll， we'll。

 we'll，ll， we'llll， you know， there's not， there， there's nothing deep about these。 Well，ll， we'll。

 we'll， we'll， we'll have a few P at problems to， you know， to， to nail these down。 You know。

 including， you know， with some， some， some， some slightly less obvious examples。 Okay。

 so so now you know， I， we can say， we are interested in。You know， the， the size of this circuit。

 you know， that's produced by this construction。 What is it big O of。Okay， so。

 so in terms of big O notation， right， how， how does the size of the circuit grow as a function of n。

Yeah。好。Yes， per row， it's L of N， exactly。 And how many rows are there。2 to the n， yep。

So we can say that this construction。Produces circuit of size2 to the n times n。 Okay。

 and you can see that， you know， between these two terms， you know， this one is the heavy hitter。

 Okay， you know， the other one just， you know， barely even matters。 Okay。

 it's it's the two to the n that's really the killer here。 Okay， because you know， if n is 100。

 this is telling you that yes， that's construction with theoretically work。 But you know。

 it will produce a circuit with more than two to the thousand gates。 Okay。

 how big is2 to the thousand。 That's well， it's more than 10 to the 300。

 the number of subatomic particles in the observable universe is about 10 to the 85， Okay。

 so this is more， you know， if if even if if if every， you know。

 you miniaturized your gates that every one had one subatomic particle， this is way。

 this is a circuit that's way， way bigger than， you know。😊，Would would fit， you know。

 in that part of the universe where the light has has reached us since the big bang。 Okay。

 that's a big circuit。 Okay， so， so， so this， you know and this is exactly the kind of issue that you know。

 we we're interested in in complexity theory， right that when you get an exponential growth。

 you know， it blows up in your face to the point where you know， something you know。

 even if something theoretically exists。 It's， you know， it's just a practical impossibility。 So。

 so so you might wonder you know， could there be an improved construction， could there be a。

 you know， a way to construct a circuit for an arbitrary buoolean function of n bits that used fewer than this number of gates。

 you know， ideally way fewer， Okay， well， we'll come back to that question。Okay。

 let me just observe first that， you know， we didn't， in， in this universality construction。

 We didn't actually need， you know， the and or a not gate。 We can。

 we can actually get rid of something and still have it be universal。What can we get rid of anyway。

Yeah。Yes， yes， either one， right， So， so let's， let's just。

Let's argue that and and not are already universal by themselves。 Okay， well， to show， you know。

 this is another point that's gonna to recur。 right， If you've already proved that a is， you know。

 thing A is universal， now you want to show that thing B is universal。 Okay， it's now， you know。

 it's enough to show that thing B can emulate everything that thing A does Okay， you know。

 we call an argument by reduction， you know， the standard joke， you know， how do you how do。

 how do you boil water， you know， fill a pot with water， you put it on the stove。

 What if what if the water is already in the pot， then what do you do Well then you dump the water out。

 thereby reduce the problem， the one that you already solved。 Okay， so okay。

 so how can we reduce the the problem of showing that and and not are universal to one that we've already solved。

 Yeah。😊，Yep， and how do we do that？Yeah。Yeah， yeah。 So we say not the and of not X and not y。

That's exactly right。Equals the or of x and y。Okay， this is called the the Morges Law。As I said。

 discoveries came easier in the 1800s。 So， so you can check that not of and of not x and not y is or of X。

 Y。 Okay， and the converse also holds not of or of not X and not y is and of x and y。 Okay。

 so which means that， you know， you only， once you have a not gate。

 and you only need one of and and or。 And then you can generate the other one。 Okay， in fact。

 we can even so so this， this shows that and and not， for example， is a universal set。 in fact。

 we can even do better than that， we can even have a single gate， which is universal。

 Anyone know an example。Yeah。The Nand gate， yeah。Okay， so， so how can we show that Nand is universal。

someone else， yeah。Yep， good。 So， how， so how do we make a knot out of a nuand， yeah。Yep， exactly。

Okay， now how do we make a， how do we make an and out of aadd，Yep， you now that we have a not。

 you know， now we might as well just put that on top of the end。And then we've got an end。 Allright。

 there we go， yeah。Yeah。Yeah， okay， so that so so， so that that， that that's a good point。

 I was assuming here that， yeah， that， that you that you're allowed to just， you know， have。

 have two wires coming out of the same bit。 So this， this， by the way， is。

Is something that we call fan out。 Okay， so， so yes， we're， you know。

 we're assuming that you are allowed to copy bits arbitrarily。 Okay。

 that's that that that's an assumption that's that that we' make you know， talking about circuits。

 interestingly， when we come to quantum computing at the end of the course and we talk about quantum circuits。

 we will find that we need to drop that assumption。 Okay， in the quantum world。

 you're not allowed to copy things arbitrarily。 Okay， but in the， you know， classical bits。 Sure。

 you know， you've heard that you've all heard from。

 from Staman right that information wants to be free， or， you know， it can it can be， you know。

 it wants to be copied all over the place。 Okay， so。😊，There you go。Okay， so now， you know。

 we know that that the Nand gate is universal。 And， in fact， you know， if we did this construction。

 you know， with N gates only， you know， the size of the circuit would change by only a constant factor。

 Because you know， every n or not gate can be represented by some constant number of Nand gates like two or three of them。

 Okay， so， so we can represent any boolean function of n bits using it most n times 2 to the n O of n times 2 to the n Nand gates。

 Okay， but now， let's now， let's come back to the question， is that optimal， Could we。

 could we improve that， You know， could there be a way that we could represent any n bit Boolean function using only。

 let's say n squared Nand gates。That would be right。 that that would be awesome if we could do that。

 right， yeah。😊，嗯。So， alright， I mean， no it'， it's what， it's。It's， yeah， it's worth think。

 thinking about， but yeah。Mmhmm。嗯哼。Yep。啊哈。😊，啊哼。😊，Yes， so so theyre very often， you know。

 tricks for simplifying circuits， building them out of a smaller number of gates， right， sometimes。

 you know， you might come up with a naive way of building a circuit。 like like like， for example。

 let's say you wanted to compute the majority of end bits， right？ You could do it this way。

 you could do it using this truth table construction。

 but that would be a wildly inefficient way to do it， right， in fact， you know。

 it is possible to create a circuit that computes the majority of among end bits using only about n times log n gates。

 Okay， I think maybe even a linear number of gates。 Okay， but you know。

 I'll check how hard it is And， you know， if it's not too hard。 I'll put it on the piece Okay， but。

But， but， but， you know， there are， there are many， many cases where， you know， you can。

 you can express something， you know， interesting， complicated using， using a circuit。

 which is actually quite small， right， or you could start out with a complicated circuit and then simplify it using carnal maps or or whatever you call them。

 Okay， but now， you know， with our sort of 60，4，5 goggles， you know， we wna。

 the question we want to ask is， is， is it possible that you could always do that， you know。

 is there some obstruction， you know， that's going to require some boolean functions to。

 to always need circuits of of exponential size。And so so， so。

 so one way that we could approach that question is that， you know。

 we could just try to come up with specific examples of functions that we think require exponential size circuits like you know。

 one good candidate would be if we took an you know。

 a boolean function that encoded an N complete problem。 Okay。

 you know I haven't told you yet what N complete problems are。 But you know， for example。

 let's say that these zeros and ones， you know， encoded whether there there was an edge or there wasn't an edge between various pairs of vertices in a graph。

 And now the boolean function will be one if that graph contains a Hamilton cycle， which is you know。

 a path a tour that visits each vertex exactly once that's that's a famous。

 you know N complete problem。 It's one for which we don't you know know any efficient algorithm to solve it。

And so you might say that maybe it should also require circuits of exponential size。 In fact。

 you know the question of， you know， finding a you specific problem like that one where you can prove that it requires exponential size circuits is very。

 very closely related to the P versus NP question Okay。

 which we're going talk about later in the course。 and we'll see exactly how know this question is related to P versus N。

 but suffice it to say for now that you it's it's also an insanely hard question。 Okay， we have。

 you know， we hope someday if civilization lasts long enough that well be able to prove that this Hamilton cycle function。

 requires circuits of exponential size but right now， you know。

 the best that we can prove for such functions is that they require circuits of size。

 at least3 n something you know， we can prove that they require circuits， you know。

 we can't even prove that such。Functions require circuits of more than linear size。 Okay。

 iss what I'm saying， right， And， and， and people just just fight on about the exact， you know， to。

 to improve the exact constant， you know， in front of the end。 Okay。

 that that that's the best that people can do today。 right， It's kind of pathetic， okay。So， you know。

 but， but we will sort of see later in the course why it's such a profoundly difficult mathematical problem to。

 you know， take a particular function that you care about and then prove that let's say there is no circuit of。

 you know， linear size or of n squared size or something that could possibly compute that function。

 right， very， very hard to prove that kind of statement， okay。Okay， but in 1949。

 Claude Shannon did something， you know， which is sort of obvious in retrospect。 But we you know。

 which， which is you know， in， an amazing sort of shift of perspective。 Okay， what he。

 what he said is that I cannot， it's true， I can't give you a single example of a boolean function that requires gigantic circuits。

 Okay， but I can prove that such functions exist。 Okay， and not only that。

 I can prove that almost every function requires gigantic circuits。 Okay。

 even though I don't have a single example of one。 Okay， so how did he do that。😊，Well。

 he used what mathematicians know as a accounting argument。Okay， so。

 so the basic idea here is that we're just going to count how many different boolean functions are there of n bits。

 And then we're going to count how many different circuits are there of a small size right， and。

 and then we're going to use the okay， we're going to use the following observation that， you know。

 it's possible that the two you know， two completely different circuits could represent the same function。

 right， this can certainly happen。 Okay， but it never happens that the same circuit represents two different functions。

 right， You know， once you've specified a circuit， you know。

 a circuit is just a way of specifying the function， right。

 So each circuit can represent one and only one boolean function。 Okay， which means。

That if there's a gigantic set of， you know， possible boolean functions， you know。

 you should think of this， this oval as gigantic。 Okay。

 and there's only a small number of circuits you know， of a small size that can。

 you know that there can possibly be then you know。

 there's there just aren't enough circuits to go around， which means that most of these functions。

 you know， even if we can't give examples， we know that sort of you know。

 the chocolate chips fail to cover the cookie。 Okay， you know。

 most of the most of the functions that are out there have to fail to be represented by any small circuit because there aren't enough of them。

 Okay， so let's， let's do the calculation。 And let's， let's see exactly what comes out of it。 Okay。

 so the first thing we have to ask is how many different boolean functions are there。

the take and bits of input。Anyone。Yeah。Yeah， exactly。 So， so some， so some， you know。

 some years when I asked this question， I get a guess of two to the n， right， you know。

 and2 to the n is big， but it's not nearly big enough for for what we're talking about here。 Okay。

 because you know， the question here is how many different truth tables are there。 you know。

 each boolean function corresponds to one truth table， and you know。

 it just a single truth table already takes two to the n bits to specify， Okay。

 because you've got two to the n different inputs and for each one， you know。

 you choose whether the output is a0 or a one， you know， you know。

 in order to specify a boolean function， right， So you've got two to the n choices to make to specify one function。

 Okay， which means that if we're interested in the total number of boolean functions。

 then this is actually two to the two to the n power。 Okay， this is doubly exponential。😊，Alright。

 so now。The next question that we need to ask。Is how many Boolean circuits are there of size at most S。

 Okay， and to， to clarify， let's say that we're talking about circuits。That are over n input bits。

 X1 up to X N。And and let's say that these are circuits of Nand gates only。 Okay， because we。

 we've already seen that Nand is universal。 Okay， so we don't have to worry about different types of gates。

 Okay， we're just， we're just asking sort of how many different ways are there to string together a circuit of。

 you know， it most S Nand gates you know， in order to create a boolean fun Boolean circuit on an input bits。

 Okay， and you know， and once again， we don't really care about the exact number。 right。

 the exact number， maybe something complicated and messy and depend on what we you know。

 identify is being equal to what。 Okay， I all I really want here is an upper bound。

 I want a reasonable upper bound on the number。 So。Okay。

 this is all available on the syllabus this information， okay。呃。Sorry， so let's， let's just。

Do this by plunking down gates one at a time。 right， How many choices are there for， you know。

 how to， how to put just say a single nad gate， you know， for， for these end bits。Well， yeah。

 it's basically n choose 2， you know， except that rules， let's say we allow， you know。

 the N gate could take the same two Bs as input。 So then it's actually n choose 2 plus plus n。 Okay。

 but between friends， let's just say it's n squared。 You know， I mean， seriously， right。You know， we。

 you know， it's， it's A， it's just a factor of two difference anyway， Okay， so。Alright， and， and now。

 you know， now how， how many choices are there for the， for the second nan gate that we put down。

 So let me draw the first one。How many choices are there for the second N gate。Yeah， one more。 Well。

 okay， let's say， let's say n plus one squared。 right， because now you know， we've got， you know。

 the the new N could take any of these two guys as input， but it could also take the output of the。

 of the first N gate as input。 right， So there's really n plus one choices here。

 for each of the the for， for for each of the two wires for both of the wires。 Okay， so， so。

 so we've got n plus one squared choices for the second N。 How about for the third N gate。😊。

N plus2 squared。Now， we've got two Nn gates， you know， in the house so we can， you know， you know。

 the output of either of those can be the input to our third Nt and gate。 Okay， and for the next one。

 we've got n plus 3 squared and so forth。Let's say all the way up to n plus S-1 squared， right， but。

You know， again， you know， I don't like messy expressions， Okay， so。Between friends。

 let's just say that this thing is it most。嗯。🤢，Let's to say that each of these guys is at most。

 is at any rate at most n plus S。 right， So this thing is really at most n plus S to the2 S， right。

There we go， okay。So now what we've got is that。There are at most n plus S to the two S different circuits of of Nand gates of size of size S。

 Okay， and and actually， we were interested in circuits of size in most S。 But the truth is。

 the ones of size less than S will just add such an infinitesimal amount to this。

 that I'm not gonna worry about it。 Okay， You know， it's gonna to be a geometric series， right。

 or more than geometric series， actually， and it's gonna to be totally dominated by the last term in the series。

 right， So let's let's just worry about that。 Okay， and now， you know。

 we know that that if s is big enough that every boolean function， you know。

 of size n can be represented by a circuit of size S。

 then this needs to be greater than or equal to what anyone。2 to the two to the N。 right。

 This needs to be big enough that there can be a circuit for every Boolean function of size N。Okay。

 so now all that's left to do is to solve this for S。Okay， so。How can we solve this， anyone。Well。

 you know， anytime you've got stuff in the exponent， you know， you want to get at it。 You know。

 the first step is to log both sides， right。So， so there we have this。 Now， how， how。

 how do we solve this thing for S anyway。Well。Once again， you know， if， if， if。

 if you fixate on finding an exact solution， there's not gonna be a closed form solution， you know。

 for S in terms of n that， you know， involving sort of any functions that you've ever seen before。

 Okay， so， so so let's just forget about getting an exact solution。 you know， we basically you know。

 this n is actually gonna be like totally unimportant because S is gonna be so much bigger than n anyhow。

 this factor of  two is also gonna be， you know， unimportant in the in the scheme of things。 Okay。

 so really， what we， you know want to know was like。

 how big does S have to be for S log S to exceed2 to the N。Anyone wanna give me an estimate。I mean。

 let's say that S was， was2 was was2 to the end。 Then what would S Y gas be。2 to the n times n。

 So even if S was all the way at the top， if S was 2 to the N， you know， we've。

 we've only sort of overshot the target by a little bit。 You know。

 we've gotten up to only up to 2 to the n times n。 So maybe we should scale back S a little bit。

 Anyone have a guess for what， what S should be to satisfy this。Okay， well turns out that the。

 the S that will satisfy this is gonna be about 2 to the n divided by n。Okay， and， you know。

 I you know， the， the， the the best way to come up with this is just。

 to play around with things until you find something that works。 Okay， or， or just， you know。

 you have， have experience with similar things。 Okay， so like， you know， but， but here。

 but here's a way of， you know， once I've told it to you， here's a way of checking it。 right。

 we can just say what's， what's2 to the n over n times log of  two to the n over n。Right， well。

 log of 2 to the n over n。Is what， anyone。It's， it's log of  two to the n minus log of n。 right。

 Let's say that all our logs are based， too， just to， you know， be friendly。 Alright。

 so that's like n minus log n。Right， okay， so this minus log n is just some little piece of crud。

 okay。Just， you know， not gonna affect anything。 Basically， we have here 2 to the n over n times n。

 It's about 2 to the n。 And thats， you know， that's what we want， okay。So， you know。So I'm。

 I'm trying to inculcate you in the ways of bounding。 Okay， yes。Okay， good， yeah。hu。M。Yeah。

 that that's right。 Okay， so， so， so actually you actually， you ask a very good question。

 So here's a thing。 like if if this were physics， right。

 then I could just do a whole long chain of this is approximately equal to that is approximately equal to that。

 you know， and just neglecting the lower order terms that we know， you know。

 don't really matter except sometimes they do， But you know， you know， okay， you know， if。

 if we were， you know， you know， if this were say a calculus course， then we would only need。

 you know， you know， we we would have want to be much more careful。

 we would want a chain of equal and just know what's exactly equal to what。 Okay。

 in theoretical computer science， we mostly want bound。 Okay。

 so so the reason why we're allowed to be， you know this fast and loose is that you know。

 our final answer that we want is only a big or or a big omega。 Okay， so so we know。😊，that， you know。

 we are， you know， you know， this， this is an exactly true statement。

 This expression is at most this expression， right， you know， I have upper bounded it。 Okay。

 I know that all I need for the number of circuits is an upper bound。 you know， and so， you know。

 I'm not allowed to are at all in the in the opposite direction， right。

 I'm not allowed to under count， you know， the number of circuits even by one。

 but I'm allowed to overcount by as much as I want， because， you know。

 all I'm going for is an upper bound here， right， and， you know， and， and， and if I make a mistake。

 if I overcount by too much， that will just mean that the that the bound that I get at the end will be maybe weaker then。

 you know， then I'd like it to be， but I won't be false。Right。Okay， so， so， so here， you know。

 I claim， so， so if you want to be precise about it。

 the claim would be that there is some constant multiple of2 to the n over n that sort of oversisfies this。

 this， you know， this inequality， right for which S times log S is more than2 to the n。

 and there is some other constant multiple of2 to the n over n for which S log S is less than 2 to the n。

Okay， so， so therefore， whatever is we say about the S that satisfies this。

 it is some constant multiple of two to the n over n。Right， that would be。

 that would be the formal statement to make here。Okay， or， or。This。This is what we want to say。Okay。

 S is big theta of 2 to the n over n。 Okay， now， well， okay， that that， that's the， or at least the。

 the， the solution to this equation is big theta of 2 to the n over n。 Okay。

 the conclusion of the argument is that。Is that the number of of gates that we need to represent an arbitrary boolean function is big omega of 2 to the n over n。

 meaning you know so from this argument， we conclude that to represent an arbitrary boolean function of n bits。

 you need at least on the order of2 to the n over n N gates。 Okay， you know。

 maybe it's more than that， right， you know the upper what was the upper bound we had。 well。

 you can see that the upper and lower bound here were off by a little bit right the upper bound that we got was2 to the n times n Okay。

 the lower bound was2 to the n divided by n。 So they're off by a factor of n squared。 know， but。

 but they're pretty close in the scheme of things， you could say， you know。

 we have shown that you can represent any boolean function with about two to the n gates。

 And in fact， you need two to the n know， about 2 to the n gates to represent an arbitrary boolean function。

 okay。Now， you might wonder about the exact answer。 So if you invest enough work。In fact。

 it can be proven was， was proven by various Russians in the 1960s that that this is。

 that this is tight。 Okay， that， in fact， you can represent so you can improve the construction。

 The construction is this is the thing that has to improve here。

 You can give a better an optimized construction that represents any Boolean function of N bits using only about2 to the N divided by N gates。

Okay， and that's， that's a， you know， considerable amount of work， to do it。 And。

 and not all that interesting either。 So we won't， you know， So， so so I'm not gonna cover it here。

 Okay， but， but counting arguments have the remarkable property that， you know。

 that often not only do they give you an answer。 They give you the tight answer。

 They give you exactly the right answer， even though you know。

 they didn't give you a single example of， of a boolean function， you know。

 we still don't have a single example of a boolean function that requires an exponential size circuit。

 we just know that they're almost everywhere。 Okay。

 so if we wanted an explicit example of a boolean function。

 like if you wanted to program your computer to just come up with， you know。

 deterministically a boolean function that requires exponential size circuits。 how could you do that。

 Anyone。 Can anyone suggest a way to do that。😊，Well， there's a really， really stupid way to do it。

 Okay， but， but amazingly， this this， this stupid way is sort of almost the best that we know today after。

 you know，60 years of research on， on these sorts of questions。😊，And the way is this。

So we can list all the possible truth tables of N bits， right。

 There are two to the two to the n of them。 Okay， and we can list them in what we call lexiaographic order。

 What does lexxiaographic order mean， It just means that we we， we。

 we start with the all zero string。 And then we， we just keep incrementing by one viewing these as integers written in binary。

Okay。So it's just some standard way of ordering all of the possible truth tables of all the possible Boolean functions。

Okay， with with， so so these are three input functions。 So they have 8 bit truth tables。

 which means that there are 256 of these functions。 I'm not gonna write all 256 of them。 Okay。

 here's the first three。Oh oh。Just for you。 I'll write one more。 Okay， Alright， so。

 so we could list them all like this。 We could then just go through this list 1 by one， you know。

 starting at the left。 and for each one， we could just by brute force。

 work out what is the size of the smallest circuit that that represents this function， right。

 we could just loop， you could just program your computer to iterate over all circuits， you know。

 starting with the smallest， starting with size 1 then size  to， until you find， you know。

 one that represents your function andll thereby find the size of the smallest circuit for each of these functions。

 Okay， and now you could program your computer to halt as soon as you get to a function that requires。

😊，Circuit of size， I don't know，2 to the n divided by n squared。Let's say now。

 we know from Shannon's counting argument that such a function must exist。Rightright。

 so since it exists， there must be a first one。 So your computer will halt and find it And which one it finds will be deterministic。

There， I've just defined for you an explicit boolean function that requires exponentially large circuits。

Okay， that was， you know， that was a little bit pathetic， right， It's like， you know， the the this。

 you know， usually answer， you know， you ask a mathematician where am I your lost， right， just。

 you know， you know， you've answered the question but without sort of saying anything very useful。

 Okay， so， you know， the big challenge here is to， you know， come up with a。

 come up with more natural examples of boolean functions that still provably require exponential size circuits。

😊，Okay， so。So， so now， you know， you might say， you know， you know。

 we've shown in any case that that Boolean circuits are， are universal， right。

 You can use them to represent any boolean function whatsoever。 So in that sense， you know。

 why isn't this just the model of computation that we want to use for the rest of the course。

 What are the drawbacks of circuits。 What's the， what are the limitations of circuits。

 What can circuits not do。Anyone， does anyone see like， what。

 what aspects of the computers that we actually use are sort of missing in， in circuits。Memory， yeah。

Yeah， that's a big one。's， know， that's actually the 1 I want to focus on here。Okay， so， so。

 so we like to distinguish between uniform and non uniform models of computation。 So。

 so circuits are an example of a non uniform model。Which means。

That sort of you need a different circuit for every input size。 You know， even if you've invested。

 you know， lots and lots of work to design like the perfect circuit for computing the majority function of 100 Bs。

 Well， that's great。 You pat yourself on the back。 And then someone hands you an input， you know。

 of 101 Bs and ask you to take its majority right your circuit is completely useless， right， know。

 you might as well just trash it and just start over from the beginning。

 designing a circuit for 1 hundred01， you know， bit inputs。 Okay， so that's that's not very useful。

 right we would， you know， we would like to be able to design you know a single program you know。

 that can handle inputs of arbitrary size。 And in particular， we would like inputs that you know。

 we would like programs that can handle you know， inputs that are much larger than themselves。 right。

 like the total code base of Google， for example， you know， was pretty large， Okay， but it's a spec。

😊，You know， it's nothing compared to the entire size of the Internet， right。

 which is the thing that it sort of takes as as its input。 Okay， so we'd like programs， you know。

 that can handle inputs that are much larger than themselves And circuits don't do that， you know。

 a circuit is， you know， sort of， you know， if， if。

 if it's a circuit that acts on all n bits of the input， then it has size at least n right。

 And so it's at least as big as the input that that it's operating one。Okay， so。

 so we w to move over to sort of non sorry， sorry， We want to move over to uniform models。

 A uniform model is one where you've got just a single program And it can handle you know。

 an input of any size。 okay， but， you know， we want to get our feet wet with this。 So。

 we're gonna start out with maybe the simplest type of of uniform computer that that there is。

 And this is what we call finite automaton。Okay， now you can think of a finite automaton as basically just a very。

 very hobbled computer that can only read its input in one direction。 Okay。

 it can only read its input from left to right and just， you know， you know， if， if， if it's。

 if it's a Hebrew or Arabic finite automaton from right to left。 Okay， either way， you know， it。

 but it can only remember a little bit about， you know， what it's seen so far。😊，Okay。So。

So the basic idea。Is。And and， and， and there's actually a more modern name for these。

 which is streaming algorithms。 Okay， so， you know。

 there's actually been like a resurgence of interest in these kinds of things recently because。

 you know， because of big data because， you know， you actually want sort of a program that can just make a single pass through。

 you know， massive number of terabytes of data， you don't have time to make multiple passes。

 And just， you know， learn something interesting even while it's doing that。 Okay， so even you know。

 the sort of most rudimentary models of computation that we're gonna to see in this course， you know。

 they still have applications today。😊，Okay， but。Anyway， the idea is that， you know， you， you get。

 this sort of stream of bits and you can read it in one direction。 Okay， you'。

 you're some device and， you know， and and， you know， your， your construction， you know。

 the construction of the device， you know， might be complicated and might， you know。

 have all kinds of components to it。 But know， we want to abstract away the details of the construction of the device。

 and what we want to say is that， you know， whatever this device is doing， you know。

 it has the property that the sort of whatever it has remembered about the the bits that it's seen so far can be encapsulated in a single object that's called the state。

 Okay， so。😊，So， so， so， so in other words， there is a finite number of different configurations that this。

 of different internal configurations that this machine can have at a given point in time。

 For example， it could have a switch， which is either on or off， right。

 that would be a two state automain。 It could have two switches。

 which are each independently either on or off， That would be a four state automain， Okay。

 but at any rate， you know， it has a finite number of possible states。

 That's the key limitation here， why is that an important limitation， anyone。😊，Well。

 you could say it first of all， it's important for a physical reason， right。

 how on earth do you build a device that has infinitely many states， Okay， you know。

 need an infinite amount of memory。 Okay， but but secondly， you know。

 if we allow an infinite number of states that would just completely trivialize what we're talking about because we could then just say。

 you're gonna read these bits from left to right。 and your state just consists of a record of all the bits that you've seen。

 Okay， so you just， you know， you're just like a hungry， hungry hippo or something right。

 You're just， you're just gobbling up these bits。 Okay， and you know。

 and then you just you see all the bits。 And， it's trivial。 Okay。

 so so we want to capture the fact that you know， this machine only has a limited ability to remember what it's seen。

 right it's gonna be reading in very， very long inputs but it only has a small memory to remember sort of you know。

 the most important， you know， facts about about those inputs， right， like it's。😊，It's， it's， it's。

 it's， it's， it's， it's， it's studying for the test。 Okay， it's， it's skichemming for， you know。

 at the end， there's gonna be a final exam。 And it wants to， you know。

 only retain the most important material from this， from from this string。 Okay， so， so let's。

 you know， no， you know， since it'll only take two minutes or so。 you know， let's。

 let's just do an example of a finite automaton。 I would like a finite automaton that just checks whether there are any1 bits in this string。

 How do I， Okay， so。😊，So the automaton， as I said， it has some finite number of possible states。

Let's call the states like A And B。 It also has， you know。

 one of the states we designate as a start state。 Okay， let me designate A as the start state here。

Okay， and， you know， it some of the states are accepting states and others are rejecting states。

 Okay， so I'm going to call B an accepting state。 You know。

 it's a state where where it accepts the string。 And I'm gonna to call a a rejecting state。 Okay。

 and now what we can do is we can define transitions among these， these states。

 So so this is a finite automaton that reads a string of zeros and ones。

 So we say that it's alphabet。The set of symbols that it can read and which is denoted by sigma consists of 0 and 1。

 Okay， and then the key thing that you do in specifying a finite automaton is that you define a function that takes So let's say that that S is the set of states。

You know， in this case， it's A and B。Right， and then what you do is you define a function that maps a state and an alphabet symbol to a new state。

 This is called the transition function of the finite automain。 Okay， so， so。

 so you define a function that that says given what state you're in now。

 And given what symbol you're reading， Here is the new state that you're going to go to and then you go and read the next symbol。

 Okay， so， you know we can， we can represent such a function using arrows。 So like if you're。

 so now I said I want a finite automain that's going to accept if and only if there's any one in my string。

 So what should， what arrows should I draw from this a state。😊，If， if I'm in state A and I read a0。

 what should I do。Stay in state A。 If I'm in state A and I read a1， what should I do。Go to state B。

 Yeah， because now I know that I can accept。 Okay， if I'm in state B and I read a 0。

 what should I do。Stay in B。 If I'm in state B and I read a1， what should I do。Stay in B。There we go。

 our first finite automain okay， so next Tuesday we will we'll see a couple more examples。

 we'll prove some theorems about what finite automa can do and what they can't do and what else they're equivalent to and PSet1 should be out this weekend okay。

Y。