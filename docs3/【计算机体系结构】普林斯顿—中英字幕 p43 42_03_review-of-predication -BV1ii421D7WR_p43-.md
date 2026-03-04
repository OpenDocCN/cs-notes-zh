# 【计算机体系结构】普林斯顿—中英字幕 p43 42_03_review-of-predication -BV1ii421D7WR_p43-

![](img/a81557dd633b09829fc2133e99c8bcc6_0.png)

Okay， so we left off talking a little bit about how to encode instructions in V IW or how V IWs encode instructions。

And。I you may recall in a V IW instruction encoding。You have a very long instruction word。

 So it could be， I don't know， many， many bytes。 So if you go look at something like the multiflow processors。

 the multiflow trace processors， they had very long instruction words。 They could， I think。

 execute something like in their largest machine configuration，20 some instructions。

And they had to encode this。 But one of the challenges was that you didn't necessarily want to have all that encoding space used all the time。

So if you are executing a simple instruction or something which doesn't actually need all the coding space。

You end up with a whole lot of no ops。 or if you have a very long dependency string in your execution trace。

 if you will。 So you have an instruction which is dependent on the next instruction。

 which is dependent on the next instruction， which is dependent on the next instruction。

 and you cannot fill any of the extra slots。 You're gonna end up having a lot of no ops in your program。

So how do we go about solving this。A couple different solutions here。

Cidra 5 went off and added a particular instruction。

 which is a single operation instruction and used a much smaller amount of memory。

 So this would effectively reduce your instruction cache pressure。There was compressed。



![](img/a81557dd633b09829fc2133e99c8bcc6_2.png)

Formats in memory， so you can hold your instruction sequences in memory。

 And then when you go and pull it into your instruction cache。

 it would expand to the fully expanded version。 And this is kind of like a compression algorithm。

 You're basically compressing your VIW instructions sequences because otherwise these things are very。

 very large and have lots and lots of zeros or no ops in them because the probability that you're going to fill sort of 20 instructions per cycle is low。

 but you want that capability there in case you actually do want to execute 20 instructions per cycle。

Another solution here is what's actually used in the Intel ittanium or IA 64 processor line。

 and also the， the T I， DS SPs， the C 6000 series。 they， they have the ability to。Effectively， mark。

Where a bundle starts and stops。 So it's something sort of between a variable length instruction and a fixed format。

V I W instruction。 So we'll talk more later in today's class about how IA 64 Intel's ittanium handles this。

 But roughly what happens is they have a fixed instruction format。

 And you can fit sort of three instructions per bundle or what they call bundle。

 And then if you want to go over that。 you can keep going over that。

 and they have special bits in their instruction， which says， oh。

 this is gonna express the more parallelism later。 So you need to look at the next bundle and try to fetch that bundle。

 And that's all can be executed parallel。 So it's still a parallel execution semantics。

 But the formats are not necessarily fixed。 And these is sort of outside the bound of classical V I W。

 Now it's going into a little bit more modified V I Ws or more contemporary V I Ws。So today。

 we're gonna， as I said， talk about how to go about getting all the performance that out of order super sailrs can get。

But in the context of a V I W。 So we're going to slowly build up all the different techniques that out of our supercals have and all the ways that they can get instruction level perism。

And then。Apply that inside of VIW or how we make small changes to classical VIWs to get a lot of the performance back。

Okay， so let's talk about the first trick here。One of the questions that comes up are the problems that comes up here is。

If you have branches。And they mispredt。This can limit your instruction level perism in a V IW。Okay。

 so why is this。Worse。Than in a out of or super scer。Well。

 an out of our superscale can dynamically schedule around branch mis predictdicts。

 So if you branch mis predictdict， you can basically schedule other code or speculatively schedule code。

 depending on your prediction。But on something like a VI W processor。

 that's a lot harder to do because you don't have a dynamic scheduling engine behind there。

 The compiler had to go do all that scheduling statically at compile time。

So how do we go about fixing this。One solution is just to eliminate all the hard。To predict branches。

 So you take out the branches。That might be hard to predict。 So your branch vi is trying really hard。

 You could still have a branch victor in your V I W processor。

 But some of these things you don't know。 It's like a data dependent branch。

 How do you know which way it's going to go。And you， this is a problem even for supercals。

 but at least in a supercalar， you can try to sort of backfill instructions or try to try to do something or move around。

 if you will， loads or long las the instructions around branches。 in a super out of our supercal。

 you can potentially move a load beyond a branch。But in a Vli W processor。

 that's not easy to do because compiler has to make that decision whether that branches is gonna predict。

 taken or not taken。 and that may， that may change over the lifetime of the program。

And it may also change， as the。Depending on the sort of input sets to the program。

 So it may not be somebody it compiler time， even knowable。Okay， so our first。

Technique here that we're going to use is called predication。So let's define what predication is。

Well。First of all， predication。Is a technique that allows you to basically change。The result。

Of a register。Based on some other register。 And it's going to less transform。

Hard to predict branches。Into。Data flow or data dependencies。So， we're going to。

Add something to our instruction set。 And it's going to take。

What looks like a small branch or a short distance branch。

 And we're going to basically execute both sides of those branches。

Or the take and the nonta code path。And then at the end。

 decide which one was the right one with a something like a select operator from C。

 So this is like the question mark colon operator， which no one ever uses in C。

 This is sort of the equivalent of that。 But we're going to do it in one instruction or maybe two instructions。

So let's's， let's take a look at how this helps with small branch regions or branches。

 which are hard to predict。So we're going to introduce two instructions。

And I also want to point out that predication， sometimes。Shows up in supersourers。

 processors or sequential instruction sets also。 So a good example of this is two instructions very similar to this are actually an X A A 6。

 They're called C move or conditional move。And we're going to introduce conditional move。

As the most basic form of predication。So let's look at the semantics of these two instructions we add for conditional move。

First instruction here。Move zero。So what does moveve 0 do。Well， move 0 test whether。

One of these input opera here R T。Is equal to 0。And if it's equal to0。

It's going to move R S into the result register， the destination register here。 So it's gonna move。

R S and R T R S and R D， if R T is equal to 0。And。If。R T is not equal to 0。

 It's just going to leave R D alone。Okay， well， on first appearances。

 that seems like a very simple instruction。It's basically just doing a， a copy operation。 It's。

 it's a gated copy。 It looks a lot simpler than something like add or subtract。

 We don't have to do any math。 At least there's no compare。 I mean the compare is easy。

 It' just the equals。 It's not less than equals。 So it's a pretty simple instruction。

And we're also going to introduce。Move not0。 So it's kind of the complementary one of this。

 And we're going to want this because when we go to execute code， we're going want to。

Let's say have a if then else。 and we're gonna have what to execute the， the。

 the then and the else at。The same time， or。Roughly at the same time or indiscriminately。

 not dependent on the branch。 And at the end。We're going to decide which one was the correct one。

 And we need sort of two instructions here to choose。 Well was， was the positive one。

 the right one or the one where the， the conditional value is true or false。

 the right one or the one where it was true or vice versa。So move not zero。

R not0 is going to do the same thing here。 It's gonna see， except the sense of the。

 of the condition code is gonna be different。 It's gonna a sense if R T is not equal to 0。

And if Rt is not equal to zero。Then R S is going to go into R D else。

 We're just gonna leave R D alone with the original value of R D。Okay， so let's。

 let's walk through a quick code example here and see， see how this helps。

So here we have a code example， here' have some C code。

We have non predicated MIPS like assembly code。And then we have a MIps like assembly code here with these fancy two predication instructions。

 And there are all three of these are doing the same thing。

So let's let's look at this piece of code here and the C code。's probably the easiest to understand。

It's going to start off。 and it's gonna say if a is less than B。 So there's a condition。

 and then there's a then and an else。So what does this actually implement。Well。

 this is a minimization function or a min function。X gets the minimum of a。Or B， if A is less than B。

 it gets A。 If A is greater than B， it gets B。So it's going be assigned to x。

 the smallest value of A and B。And。These sort of， if then else's。You can see here it's pretty short。

 We don't have a whole lot of code in either the， the then case or the else case。

And that's going to be important in a second。 You'll see why。

Mainly it involvess around if you have lots and lots of code or one of the sides of the branches is。

 is is long， It may not make sense to actually predicate this because there's some cost of predication。

Okay， so here， here's some assembly code does a similar sort of thing。 set less than。

 This is a comparison operation in MIps。 So we're going to set less than。

 And these are gonna be R 2 and R3 are gonna have our two A and B values here。If it's less than。

 we're gonna put into R 1。 If not， this gets set to 1 or 0。

 And then we have a branch0 here effectively。Otherwise， this is a branch。Okay。

 so branch equal with 0。 It's a little odd。 We probably just put branch 0 there instead。

 but I was going check to see whether this value is 0 or  one。 And if it's。

The one direction is going to jump to L1。If it's the other direction。

 it's going to fall through and then jump over this move。

 And these two moves here are the two assignment operators， the x equaling A or x equaling B。Okay，'s。

 that's not so bad。Let's analyze how long this takes， how many cycles this will take to execute。

 on a sequential machine。Okay， does this set less then。It's one。This is branch。So that's2。

Let's say the branch is not taken or falls through。3。four。And then the jump over。

 So it's going to be 1，2，3。Instructions in the one。 is that right，1，2，3。

4 instructions in the one case。And the other case， it's going to take the branch to jump to here。

 So it's going to be one，2 jump over all the stuff， three instructions。Okay。That's。

 that's not so bad。 So the one case is 4 and the other case is 3。They're different。Now。

 something else that makes this interesting is， let's say this branch。Is mis predicteddicted。

 It's a data dependent branch， A And B。 So what what's a good thing to predict here。

 Can our branch predictor do a good job on this。I don't know。

 It dependss on what you know about A And B。 If the compiler knows nothing。

Or the hardware knows nothing。You're not going to do a particularly great job。

 So let's say it's a data dependent branch。 and it's 50% to one direction and 50% the other direction。

Is this going to slow down our execution？😡，Well， sure。

 let's going to slow down on execution because all of a sudden。When we take a branch。

One of the directions， whichever we we predict， the mis predictdict path is going to add some mis predictdict penalty。

So instead of the one path being 3 and the other path being 4， let's say the branch is predicted。Oh。

 I don't know， let's say the branch is predicted。Not taken。 so it predicts the fall through case。

So all of a sudden， the fall through case is going to be 1，2，3，4 instructions。

And let's say we have a two cycle branch mis predictd penalty。 So let's look at the other case。

So other case is going to be1，2。And then two cycles of mis predictdt。

 So that gets us up to4 or to branch over。5， so it's going to be five cycles。So all of a sudden。

 we have our branch mis predictdict penalty coming into the equation here of and， and you know。

 two second branch mis predictdts are relatively benign。 If you， if that starts to grow longer。

 then you really start to have problems with this。Okay， so let's take this code sequence。

And look about how to predicate it。So if we're going to go predicate this。

 we're actually going to execute both sides。Regardless of the value of the。诶。

If clauses are the conditional clause here。So if we look what we do。

 we actually have restructured the code here a little bit。And。This is our compare。 This is our if。

Still up here， we have a set less than。And then。We say if。R1 is0， move r2 to r4。Else。

 just leave it alone。And then here， if。R1 is not0， move R3 to R 4。

And what's important to note here is this nondestructive operation。

Especially here in this last instruction is really important because if the move 0。

Was executed and that copied a new value into R 4。And then this move， not 0。

 where to somehow change our  for。You lose that result from this previous one。

 So this really depends on these operations be nondestructive。If their condition is not true。Okay。

 so let's analyze this from a number of instructions perspective。First question is。Does this matter？

What happens to the branch or what happens to the condition？

Is it gonna have different numbers of instructions or different numbers of cycles dependent on the。

 the direction of the the condition。Well， no， there's no branch。Nothing's going to change。

So in all cases， this is going to take three cycles。So all of a sudden。

 we transform something which can take， as I said。If let's save a branch mustp penalty。

 four cycles or five cycles。So on average， let's say the branch is taking 50% of the time in either direction。

 we'll split the difference there and we'll call it four and a half cycles on average。

 and we turned it into something which takes three。Well， that's a great win。嗯。

So where else is this useful？Does you always need to have if then else clauses to make this work out？

So no， this also works good for small code hammocks。

 So I say small code hammock is just a if which jumps around a small piece of code。

And if you can't predict that， if very well。Then it makes sense just to go execute effectively what's inside that code hammock or that small piece of code always if。

 if if， for instance， you have two instructions inside of a code hammock and your mis predictdict penalty is like 10 cycles。

 and you don't know whether the branch is being taken 50% of time either way。 All of a sudden。

 your average mis predictdt penalty is gonna be something like 5 cycles。

 You could have just executed the code in the middle。 It would have been faster。

 You could have executed the two instructions。And then just done a conditional move at the end and that would have been and basically always better。

🤧。Okay， so we bring up some questions here。What if the if then else has lots of instructions？嗯。

So let's say we have if then else here， but there's 10 instructions here and 10 instructions there。

Should we？Predicate this。😡，Let's say the branch Misspher penalty I said five。For no， it's 10 cycles。

 and it's 50% either way。But there's 1000 instructions in the。If the then clause and the else clause。

Well， no， that would never make sense to do。Because。You're basically doubling your code。

 And there's a lot of code there。You'd be better served by just doing the branch。

Because you'd be taking something that was could be 1000 instructions and turning it into always 2000 instructions or doubling the number of instructions executing。

 executing versus just adding， let's say 10。Cyclees of branch mis predict penaltyity or on average 5 cycles of branch missed predictity to your 000 that you have to execute。

 So all of a sudden， you're， you're adding a little overhead。

 So where this predication really helps is sort for small pieces of code。

Where you don't necessarily know the branch。Outcome or can't predict the branch outcome very well。O。

 what if the， the code is unbalanced。So you have an if， then an an else。

But the then clause and the else clause are very different in size。 So one is three instructions。

 other is 1000 instructions。Does this make sense？Wello。

It goes back to the same argument we had before。With the。Very large， if then else clauses。

If the code is really unbalanced， you have a lot in the then cause and a little bit in the else clause or something like that。

And let's say the branch is taken 50% of the time。 It might make sense just to use the。

 an actual branch there and deal from the mis predictdict penalty costs versus trying to。

Somehow predicate because effect what's going to happen is let's say you have three instructions and 1000 instructions on the two different sides。

 you're gonna be adding， You're gonna be executing。 if you predicate。10003 instructions。

 every single execution time， plus maybe some sort of。Conditional moves at the end。

 some overhead involved。Versus if you have 50，50。And you have to add a little bit of a branch overhead penalty。

 Your 5050 is gonna5050 chance is going say， well， I'm taking 1000 plus 3。

And I'm going to add those two things together and take the average of them。 Basically。 So， you know。

 it's going to be， what's the average of that， It's going to be like 501 or some of that or 502 cycles。

 And that's going to be better than always executing 1000。Cyclees。

Let's see anything else we wanted to say here。Yeah。

 one last thing I wanted to say here before we move off this slide。Mo。0 and move， not0。

 or sometimes called C move， conditional move instructions。Our what are called partial predication。

And we're now going to move on to full predication， where we can actually put。

Conditions on every single instruction in our register， every single instruction in our IA。

But this is a little bit easier to do than full predication。

 This is sort of the first step that people typically implement， and it's called partial predication。

And just to hammer this home one more time， predication is really turning what was control flow into a data flow operation or a data operation。

Okay， so let's take a look at。Full predication。Full predication。

 we're actually going to change the instruction set。Such that all the instructions can be。

 or almost all the instructions are executed conditionally based on some predi predicate。

If the predictd is false。The instruction is not going do anything。 It's just not gonna to have any。

 any side effect。So let's look at a code sequence here。So in this code sequence， we have an if， then。

And else， and then some code。呃。After after we're done。So here we have if。A little bit different。

 This is not actually in MIPS code。 this is something just sort of pseudocode here。But。

 it's gonna to say。Is there if here， if A is equal to B。Then branch。To be 2。Else， fall through。

Here we're going to execute our else clause。And what we're done， we're going to branch over。

The then clause。So not， not anything interesting here for basic blocks。

 I don't know if we've introduced this term yet in this class， but I want to。

Introduce the term basic block。Basic B is a piece of code which has strictly one exit point。

And one entry point。So you could enter it from other places。

 you can jump to it from other pieces of code， but once you enter the piece of code。

 you can execute code all the way to the end。 and then there's one place you can leave。

 so you jump to someplace else or branch and you can fall out to two different places but the exit point is only one place。

 so we're going make the differentiation here is the piece of code can have， for instance。

 two branches let's not called a basic block。That's called a bigger type of block。

 but this is a compiler term。It's just good to know。Okay， so let's apply full predication here。

So these are relatively short code hammocks， two instructions here。

 two instructions there and two instructions in the L， two instructions and then clause。

 This is like a really great place to think about predicating。Okay， so let。

 let's take a look at the predication here。 And and before before we do that。

 I wanted to just say that one of the big reasons that we're trying to predicate。

On a V I W in particular is in a V I W， we have lots of extra。

 or we could potentially have extra parallel execution slots。

 So in our instruction sequence or instruction encoding， we have extra places to put code。

So it may not actually hurt us to predicate because a lot of times when we go to predicate。

 we're basically going to execute both sides of the if then and else。

 And it's bad if we have to execute both sides of the if then and else and they're big sequentially。

 But if you try to sort of slide them up next to each other。

 if you have extra no op slots or extra slots in your VIW。

 you can actually decrease the critical path through your program。So let's look at this。

 And we're actually gonna do this in this example。 So in this example here。

We took this piece of code and added full predication。So when we say full predication， we added。

Some extra things to these instructions。 they look a little strange at first。So here we have In 3。

 In4， In 5， In 6， and these are the same ones that we back over here。But， instead。We added。

Some extra words in front of them here are these， these parentheses with Ps in front of them。

 What that is is these are predicate registers。 So we're going add。

A second register file into a processor。Where we can store。Effectively，1 bit values。

 sort of true or false values。That are going to determine whether this instruction executes or doesn't execute。

Excuse me。What this means is if P1 is1。Execute this。If P1 is0。Nify this instruction3 here。

And we have， we have a double pipe here。 What am I trying to show of this。 Well。

 I'm trying to show this is parallel。 This and this are executing at the same time。

 because we have a very long instructional processor we can execute multiple things at the same time。

And what we've done here isve actually slid this up next to the， the then up next to the L。

 and we're going to execute them at the same time。Depenent on。These predicates。

So this is the L block。 and this is the Ven block。 We're going to execute concurrently。Okay。这 of。

Stuff before the if， stuff after the， if then else is all done。 That's sort of from that。

 that four basic block example。What's this instruction。

 This instruction has very interesting semantics。 And this is something that you。

Probably have to add if you're going to try to have full predication。HOkay， so it's a compare。

 So this is our comparison。 If a is equal to B， and then it writes into two outputs。

That looks broken。 That looks wrong。 somehow。 How can we have one instruction right to two things。

 what is the semantics of it， What is it right to hear and here。Well。

 what this is actually doing is this is writing the positive outcome of this compare to the one and the inverse or the。

 the negation of that to the other。And this is useful because then we can go use these predicates down here。

 We can use the， the positive  one。 let's say the negative one。 and that can。呃。

Drive whether we execute the or of else clause or the then clause。

So lots of instruction sets that have full predication have either something like this。

 This is one option。 You can actually have sort of two outputs。 and you load two predicate registers。

 The other option is when you go to actually encode the instructions。You have sort of a not bit。

 So it denotes the predicate register。But when we denote the predicate register。

 we also denote whether we take the。Predcate register being true as or the pre register being false as what drives whether the instruction executes in our full predication scheme。

So in effect， this is computing P and P bar at the same time and running them two different registers。

 and then we can use those separately。Down here。And。Interesting result here in Isca 95， Scott Melkey。

Showed that you can， on average， let's say， remove 50% of your branches by using full predication。

Now， full predication is not easy to build。 Very few instruction sets have actually had full predication。

 Ittium was probably the closest to a real pro that was built that has almost full predication。

 It doesn't have quite full predication。嗯。The H P Plato instruction set， I think。

 actually had full predication。 I think this is what Scott Malkey was working with or a derivative of that。

 So you can actually have。So actually sense that people have thought about that have had full prediiccation。

 but not all things are easy。 So first thing， you need to add an extra register file for the predicates。

 you need to bypass those predicates， You need to compute them。 There's some overheads involved。

 And we're gonna talk a little bit more about them。



![](img/a81557dd633b09829fc2133e99c8bcc6_4.png)

![](img/a81557dd633b09829fc2133e99c8bcc6_5.png)