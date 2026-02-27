# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p04 20230831-Aug 31_ DFA product construction.zh_en -BV1Mh7RzaEL2_p4-

![](img/8b8c17a35bc2d65e80471b5ce3ca83ad_0.png)

。まなて。Thatest。ありません。Okay。

![](img/8b8c17a35bc2d65e80471b5ce3ca83ad_2.png)

What。他刚才。关。Yeah。对。

![](img/8b8c17a35bc2d65e80471b5ce3ca83ad_4.png)

从来不见。喂。Yeah。I think。I think that us been。如他们。你谂搞。对还有那个他看。Hi， everybody。呃。Thanks for coming again。嗯。

So we got about。215 submissions for homework one， which means that average group size is about two two and a half。

 something like that， which is great， we are trying to set up the grading schedule so that。

You will get your graded homeworks back。Within a week。So optimistically， that means by next Tuesday。

Things will slip a little bit occasionally， but different number of problems are being graded by different teams。

 so grades will be released as soon as people are done， but graders have already started working。

 so I'm reasonably optimistic。Um。I do want to remind you with the extension thing。

 there's no such thing as an extension just for the GPS。You have three no fault extension tokens。

 you can either spend a token in a given week or not。

Right you just define your one zero one decision at least the way we have things set up right now so a couple of you。

Tried to ask for extensions just for one thing and not the other。

 that's not how this is going to work。嗯。😊，But just and keep in mind also that you can still do 90% of the GPS and get credit for doing it before the deadline。

 it's not like the homework with the homework， you don't submit anything in。With the GPS。

 if you make partial progress， and you get 90% of the way through。That。

Probably not worth spending that。The last percent。嗯。呃。

Any other logistical or administrative questions？Okay。So。Let me。Remind you what we've been what the。

Object that we've been talking about since last lecture。

Is something called a deterministic finite state machine or deterministic。Finite state automaton。嗯。

One way that you can think of this object。😡，Is it's a。Directed graph。Where？

One of the nodes has an arrow coming to it from outer space。😡，That's the start state。

 some of the nodes， in this case only one are represented by doubled circles。

 those are the accepting states， all of the nodes of the graph are just states。

And for every symbol in your alphabet and every state。

 there is an arrow leaving that state labeled with that symbol。😡，So here from state S。

 I have an arrow labeled zero that goes to state S and I have an arrow labeled one that goes to state A。

😡，From state A， I have an error labeled zero that goes to S and error labeled one that goes to B。

 from B， I have an error labeled zero that goes to B and an error labeled one that goes to B。

 but rather than drawing two arrows with different labels， I just draw one arrow with both labels。😡。

啊。And the idea behind the way this machine works。😡，Is it the beginning of time？😡。

You put your finger on the start state， which I've labeled to your S。😡。

And somebody feeds you a sequence of bits and every time you hear a bit。

 you follow the corresponding arrow。😡，To the next state， which might be the same state。

 it might be a different state， but just whatever the next state is。😡。

When the person feeding you the bit says， done， you look under your finger。

And if you're on an accepting state you say yes， I like that string of bits you just announced。

 and if you look under your finger and you don't see an accepting state， you say， no。

 I don't like that string of bits that you just announced。Okay。That's the way the game works。嗯。

So this is a DFA that recognizes or accepts。All strings that have two ones in a row。

Anywhere in the string， so this is equivalent。To。This。Excepts the language described。

By this regular expression。嗯。And what we're going to start leading up to today。😡。

Besides doing a bit more manipulation and construction tools for like how to build DFAs and how to show DFs are equivalent and what sorts of what things you can do with them。

We're going to start moving in the direction of showing that these two representations actually describe the same languages。

😡，A language is recognized by a DFA， it's an automatic language， it's recognized by an automaton。

 if and only if that same language can be described by a regular expression。😡。

So this is what is sometimes known。As cleaning theorem。Automatic languages。

Are the same thing as regular languages。Which is why no one ever talks about automatic languages。Yes。

Viate。是的。And the typo。My fingers slipped。Thank you。😊，The 8 key is a little bouncy on my hand。Yes。

I will do that， I'm not going to do that now because it requires several stages that we haven't don't have the tools for yet。

So the question was， can I like walk through the process of deriving the regular expression from the DFA。

 I will do that， but a it's a multist process and we have to introduce a few intermediate tools before we get there。

😡，Okay。So。To remind you， I think it's useful to have like the formal definition here， a DFA。

 we would normally refer to a machine M。Thiss consisting of。A quadruple of four objects。😡。

The set Q is the set of states or configuration starting with a queue there's a there's a post on computer science stack exchange that somebody asked why do we call this thing。

😡，Q。I don't know why that just happened。that。Q is an abbreviation for quantum as a mnemonic for the fact that the states are quantized。

 they're finite， they're discreted， this is not historically accurate。

 but if it helps you remember that Q corresponds to these discrete states， then go for it。😡。

S is an element of Q。This is the start state。It's always just one state。A is a subset of Q。

These are the accepting states。Delta is a function。

That takes a state and a symbol in the alphabet and returns a state。This is the transition function。

And I want to， you know， because a couple of people asked me after class last time what this。

What this notation means， it's the same as if I'm defining。A function。That has the。嗯。

Following type signature。And I think this is this is。Roughly Python syntax with type hint。

So I have a type called state and I have a type called symbol。

the formal way that mathematicians would describe this。

 Q cross Sigma is the Cartesian product of those two sets。

 this just fancy notation for the set of all pairs with the first thing in the pair is a state and the second thing in the pair is a symbol。

To computer scientists， the way you should read this is this is a function that takes two arguments。

😡，One from the set Q and one from the state sigma。😡，And it returns a single value from the set queue。

嗯。On。Now， once we've not。These you know， the basic definitions。

 the transition function is what's encoded by those labeled arrows up there。So Delta of S comma 1。😡。

In this case is a because the arrow leaving S labeled1 has an A on it。😡。

So if I say you know delta of p comma a equals  Q， that's the same。In the graphical notation as this。

系。嗯。Okay， so I want to describe exactly what language this abstract， you know。

I haven't defined a particular dfaA with this with this notation yet。

 this is just the names that we give to the four pieces， but I can still describe。😡。

The language that this DFA accepts in terms of this so called extended transition function。😡。

That now。Instead of taking a state and a single symbol， it takes a state in a string。😡。

And this means。What you intuitively think it means。

 which is instead of just following one arrow for that one symbol， I follow a sequence of arrows。

Which are determined by that sequence of symbols。so formally。

Delta star of S common W is defined recursively sorry called the random state is little Q。

If W is empty string。Otherwise， it's Delta star of Delta。A， sorry。Q comma A， comma X。

If W is equal to AX。So again， this is fancy mathematical notation for first follow the arrow labeled A and then follow the sequence of arrows determined by the suffix X。

😡，So given the string， you look at the first character to get the first transition and you let the induction fairry worry about the rest of the transitions。

Right。U。You say that M accepts。The string W。It's an only if。Starting at S in reading W。

 I get to an accepting state。😡，Okay， so if I start with my finger on state S。

And I hear the bits at stateW and I follow the corresponding arrows when the bits are done。

 when the word has been spoken。😡，I look under my finger， if my finger is on a state in that set A。

 then I say that the machine accepts， otherwise I say that the machine rejects。😡，And then finally。

 the language of the machine。Is the set of all things？That。M excs。So again。

 I can write this out more formally the set of all strings W。

 such that the extended transition function of S on W belongs to the set of accepting states。嗯。Okay。

 so this is a lot of symbols。😡，Some of which require。😡。

Practice to learn how to type either using BX or if you have a Mac keyboard and and you remember where all the option keys do。

Um， I don't know how to do this on， I don't know how to type a lowercase Delta on Windows or Linux。嗯。

啊啊。But it's important whenever you run into mathematical notation like this。😡。

Just to learn how to pronounce it。Because the pronunciation actually will tell you the meaning。

 the reason mathematicians write in symbols like this is because the words would just take up too much space。

Okay， so nothing particularly fancy about this， this is the set of strings W。

 I know it's strings W because we always use W to represent a random strain。Is bar mean such that？

Delta star is this extended transition function。😡，Starting at S， reading string W。

This returns a state because I said so up here， and that state is an element of the set of accepting states。

But。In other words， this is the set of all bit strings。Where if I interpret them as directions。

They lead me from the start state to some state that has a double circle。All right。嗯。Now。

For this particular example。I say Delta star of S。0， zero，1， zero，1，1，0。This will be。

0010110 so the ends up in B， which is an accepting state， so I will accept that。Okay。

This is where we left off。At the end of the lecture yesterday or sorry， Tuesday。

The definitions will become more comfortable as we play with them。

 but for now there did people have questions about any of the components or any of the symbols or any of the formalities that I put up on the screen？

😡，Okay， so let's start playing with with variations， so I know for example。

 if I design this language， this DfaA here， this accepts all strings。😡，That have two ones in a row。系。

嗯。So I'll just write this again。Stngs。Containing。1， one。Now。哦。Suppose I wanted to build now。A。

DFA that accepts the language strings not containing。One， one。Yeah。How would I get there。

 what would I do？Now you designed this DFA from scratch， but I claim there's a much easier way。Yeah。

 over here。Exactly right， so you can reverse which states are accepting and which states are rejecting。

So I'll take my original DFA。😡，And I'll make a copy of it。And then I'll modify it by saying， oh。

 you know， that state shouldn't be accepting anymore。

 instead this state should be accepting and this state should be accepting。

So what I've done is I've taken the acceptance condition。😡。

The Dta Star leads me to an accepting state。And I've changed it to in the original DFA。😡。

Delta Delta star leads me to a non accepting state。😡。

And then if I swap which states are accepting and rejecting that brings me back to what I want so by negating the accepting。

For what I want， that's equivalent to negating the accepting condition by complementing the set of accepting states in the DFA。

😡，Okayy。Yeah。Can it be done with regular expressions without starring from scratch？

That's an excellent question， so can we do negation with regular expressions without starting over from scratch？

No， because you can convert it regular expression to a DFA to get the DFA。

 convert it back to a regular expression。😡，Whether that's easier than starting over from scratch is an open question。

So there are automatic ways to negate regular expressions。

 they suffer from the problem that the negation of a regular expression might be exponentially longer than the expression you started with。

😡，And that's unavoidable， there are examples where you have to expand exponentially to do negation。

 which is why in some real world so called regx languages， negation is actually an explicit operator。

😡，But the formality that we are doing doesn't require it partly because it just makes things more complicated。

Thank。So let me try another one strings。Not。Containing。Two zeros in a row。How would I？

How do I do that？Yeah， so I take the same DFA that I just just wrote down。😡，And again。

 I will duplicate it。And this time I instead of changing the accepting states。

 I'll change the transition function。😡，So where before I transitioned on a one。

 now I want to transition on a zero and vice versa。So I will erase these。And instead， I will write。

 you know， that's a one， that's a zero， that's a one， that's a zero， that's a one comma zero。

I didn't really need to do the last， but you know。I as well be careful。So。

What these simple transformations show you is that DF is allowed you。😡，2。嗯。

Take a DFA for one language and modify it to get a DFA for a very similar language under the right conditions。

😡，For this kind of substitution I want to swap zeros and ones。

 you could do that just as easy with regular expressions I take the the regular expression for strings not containing one1 and I just swap all zeros and ones in that regular expression I'll also get the regular expression for strings not containing zero zero。

 but there are operations that are。😡，Difficult for regular expressions。To support where for dfaAs。

 these are relatively straightforward， so I want to show you。Another example here。So this is a DFA。

For strings。Containing。bo。Zero， zero and one， one。This is called a。Product construction。Okay， so。嗯。

Let me describe the intuition before I poke at the example in detail we already have a dfaA that will recognize all strings that contain two ones in a row we can easily modify to get another dfaA that。

😡，We recognize the strings that have two zeros in a row。Now。

 if I want to recognize strings that have both of these things。

 one thing I could imagine doing is running these two simpler machines in parallel。😡。

So when I here is zero， I feed that zero to both of my subroutines simultaneously。😡，When I hear one。

 I feed that one to both of my subrtines simultaneously。At the end， when I hear， oh。

 I'm done with my bits， I say， are you happy and are you happy。

 and if both of my component programs are happy， then I'm happy the string satisfied both the condition that made machine one except and it satisfied the condition that made machine two accept。

😡，Now。This is。Taking。you know， a box and then putting in two smaller boxes in it。

Each of those smaller boxes is a mechanical device。😡，A thing made of gears。

And you should imagine that inputting a one means pushing the one button and inputting a zero means pushing the zero button。

😡，And what I'm literally doing here。I I'm saying okay， there's the zero button on my outer machine。

 it's going to push the zero buttons on the two component machines。And here's my one button。

 it's going to push the one button on my two component machines。

And then this has a light bulb bonnet。And this has a light bulb onnne it。

And these are going to feed into to a light bulb on the bigger machine that I'm constructing。Okay。

 now I've built a mechanical device that recognizes both。😡。

But what are the states of this larger device？😡，诶。😊，Well the states consist of two parts。

 there's the state of the little machine on the left and there's the state of the little machine on the right。

 so the state of the bigger machine is a pair。😡，One part is a state of machine one and one part is a state of machine two。

And so this is what I've drawn here on the screen， the vertical DFA over here on the left。

 that's the DFA that recognizes strings containing two zeros in a row。😡。

The horizontal DA along the top， that's a DFA that recognizes strings with two ones in a row。

The product of these two DFAs。😡，Has three times three is nine states。

Every state in the product machine corresponds to a choice of the state for Ma one and the state for Mach two。

😡，系啊。So。If my product machine is， say。Here in state S comma A， that means inside the state。

 machine one is in state S and machine two is in state A。😡，Similarly。

 how does the larger machine transition among those states， well， when I hear a one。

 I pass that one to both of my component machines， so the first half of my state pair changes according to the transition function of machine one。

😡，And the second half of my state pair。Transitions according to the transition function。

Of machine two okay， so if I'm in state SA and I read a zero they say what happens over on the left in machine one well I'm in state S and I here a zero。

 I go to state A。😡，What happens in machine  two well I'm in state A and I hear zero I go state S。

 so in the big machine， if I an S comma A， the first S turns into an A， the second A turns into an s。

 so I end up down here。系い。And so all I've done to draw out this machine is mechanically follow these rules。

For each state in my product machine and for each symbol zero or1。

 I have exactly one outgoing arrow from that state with that label。😡。

And the destination is determined by what machine one would do in that component state with that symbol。

😡，And what happens with machine two in its component state with that label？Right。So。I should really。

呃。Write this down a little bit more formally， so let's suppose that we are given two machines M1。

Wwhich is a quadruple containing the set Q1， starting state S1 accepting states A1 and a transition function delta 1。

And we're given another machine M2， which consists of Q2 S2。A2 and Delta2。Right。

We want to define the product。Machine。Whathich I'll just define as M。Q as a deelta。As follows。

The states are the Cartesian product of the states in the two component machines。

So this is the set of all pairs， PQ， where P comes from the state set of machine one and Q comes from the state set of machine two。

Again， you'll notice as I'm writing the symbols， I'm saying them out loud。😡。

Dittra actually was fond of saying lots of things Dyictra was very opinionated it's a long tradition in computer science of people being very opinionated。

But Dyketra actually said， it helps writing proofs to gently sing the notation。

So actually pronounce this out loud。Q1 cross Q2 is the set of all pairs Pq such that P comes from Q1 and Q comes from Q2。

系。😊，The start state of my machine is a state， so it is a pair。😡。

The left half is a state for machine one and the right half is a state for Ma two。

 what are those two states？What are the two components of the starts？S1 and S2。

I'm starting machinech one。And I'm starting machine two。Cool。What is the set of accepting states？

Well， again。It's a subset of the set of all pairs。So again。

 every element is in my accepting state is going to be a pair PQ。

Where P is one of the states of machine one and Q is one of the states of machine two。

 but in particular。I'm going to define it as。P is in the set of accepting states。

Of machine one and Q is in the set of accepting states in machine two and this word here。

Is important。Reasons I'll come back to。系。So I will accept。😡，If and only if both of my components。😡。

Except。嗯。Finally， we need to define the last bit， so the transition function。

So the input to the transition function is a state and a state in this case is a pair。

 so that's my complete invocation of the transition function for this product machine。😡。

The way that you should read this is I'm defining a function that takes。Either two parameters。

 one of which is a pair of states， one for machinech one， one for machine two。

 and the second parameters is a symbol， or it's equivalent to thinking this is a function that takes three parameters。

 a state for machine one， a state for machine two， and a symbol。😡，Well。

 this is going to consist of a pair of states。😡，And the way I determine the new state in Ma one is I run the transition function of machine one on the state from Ma one and that symbol。

😡，Similarly， the new state for machine two， I get by running the transition function state from machine two。

😡，On the old state for machine two and the given symbol。😡。

So this is the recipe that I followed slavishly， mechanically to build that DFA at the top of the screen。

😡，When you do this。What you end up with is a machine that accepts。😡，The intersection。😡。

Of the languages accepted by the two factor machines。

It accepts strings if and only if they belong to both。😡。

They make both of the component machines except so you get。诶。Theraman。Here。

The language of this machine is the language of machine one。😡，Intersect the language of machine two。

I'm going to prove part of this theorem。😡，In a second。

 but I want to make sure that the intuition is there before I move on。Again。

 this is a lot of symbols。But I think the picture kind of shows what we want to do。

 I have nine states that's three， but all pairs of states on the left and all pairs of states above。

 I have a single start state that corresponds to the start state from one and the start take for the other。

 I have a single accept state。Which corresponds to the single accept state from one and the single accept state from the other。

 and I have this rule for how I draw the arrows。Yes。It。four instead of and yeah， okay。

 so we're jumping ahead a little bit， if I replace this word and with or。

 that has the effect of replacing this intersection with the union。So suppose I'm happy。

 if either of my two component machines are happy， then I'm accepting a string if and only if it belongs to this language or it belongs to that language。

 that's the union。😡，If I replace this and with an exclusive or。

Then I'm accepting the symmetric difference of the two languages。

 exactly one of my two machines is happy that I'm happy。

So any Boolean operator that you put here in the definition of the accepting states is reflected in the language you accept。

 what Boolean operator you put here to combine those two component languages。😡，Okay。😊，嗯。

This is actually a subtlety that unfortunately a lot of textbooks miss， most a lot of textbooks。

 a lot of references only talk about product machines for intersections。

But you can do product machines for anything。Any boyan combination you want。

 the way that you would actually describe that DFA in the homework。Is。

I'm going to do a product construction， here's machine one， here's machine two。

 M is the product of those two things。😡，Here are the accepting states。😡。

All the rest is standard boiler platelate under the。

 this is just implied by the definition of the phrase's product construction。😡。

But you do have to specify the accepting states， otherwise I don't know what bulloley and combination of things you're implementing。

Okay。Does everybody kind of intuitively see why this works？Now this is。

Really starting to dig at something。😡，That is at one level very simple in another level。

 a little bit mind bending。Is that the notion of the state？

Of a machine or the state of an algorithm or the state of a program。😡。

Being made up of the states of the components that it's built out of。😡，This is going to come back。

Later on， when we start talking about dynamic programming algorithms。

 this is going to come back later on when we start talking about solving problems by modeling the inputs as graphs。

😡，this notion of state and states having various components。

 which I can kind of think about independently， but in the end。

 I need to deal with all possible combinations in some kind of product construction like this。😡，Okay。

 so。Well， there's the there's the ore machine and the exclusive ore machine and the ifn machine。

 but before I get to that let me actually show you the keylemma for this。Serem。

And the key lema talks about the extended transition function。😡，And nothing I'm going to say here。Is。

Profound。But I'm partly going through this exercise。

To kind of get you used to the idea of playing with these symbols。

Because there will be times when despite the fact that this is all， you know。

 math speak with Greek letters and braces and whatnot。

 this really is going to be the simplest way of describing your DFA。

 you're not going to be able to draw a picture that actually conveys any reasonable amount of information。

😡，In particular， on the homework。There's at least one problem where the minimum possible number of states that you can get away with is greater than 374。

So the only way to describe that is by using the formal notation。So here's the klema。

The keylema basically says that the extended transition function of my machine。

Behaves exactly the way I expect it to， which is it's the same as running the extended transition function on machine one。

And running the extended transition function on machine two。And this holds for all。

States for machine one， states for Ma two and strings W。嗯m。

If I remove the stars from the limitma statement， this is actually just the definition of the transition function in the product machine。

😡，Transition in each component independently and write down the results。Okay。

 and this says I'm just going to extend this to transitioning on strings instead of transitioning on。

On。Single characters。Oh look， I've got a universal quantifier。

 the first thing I need to write down is let he and cu be arbitrary states。😡。

And let the W be an arbitrary string。And then at the bottom of the page。

 I write down the statement of the theorem。Okay， now what is it I'm trying to prove， oh。

 it's a weird thing about a recursively defined function， Delta star。😡，How do I do the proof？

ductionAnd the reason I know it's induction is because I've done induction before。😡。

And I told you in every lecture， if I've done induction before， I'm going to do induction again。😡。

I'm proving something about a recursively defined object。😡，I'm going to use induction， okay。

 so this means I need to write down an induction the hypothesis， okay。

 something needs to get smaller when I recurse。😡，Among the objects that we're discussing here。

What can get smaller？Can I make P smaller？No。It's an element of set the set doesn't have an order。

I didn't number the states 1，2，3，45， it's just to set， there's no ordering to it。

 so I can't do induction on state P。And similarly， I can't do induction on state Q。

The only reasonable thing that I might be able to do induction on。😡，Is the string W？😡，Okay。

 so my induction hypothesis is going to say。Assume for all。Strings。X。Shorter。Then。W。That Delta star。

OPQ。X equals。Delta star of E X and Delta star of Q QX。嗯。

I'm a little uncomfortable with this because when I transition。

 I'm going to be changing those states， so I'm going to go ahead and fill in。For all states。

P prime in Q1 and Q prime。In Q2 and now。When I make my recursive call， the states might change。

 so I need to accommodate arbitrary states。😡，In my induction hypothesis。

 and remember my induction hypothesis says recursive calls will work。😡，嗯。So in this case。

 I'm only really doing induction on the string W。😡，But when I make my recursive call。

 you'll see that the underlying states are different from the ones that I given at the beginning P&Q。

😡，So I need to make sure that the induction hypothesis captures that idea。Okay。There are。wo。Pces。

Anyone want to guess what the two cases are？Remember， I'm doing induction on the string W。

One is w is empty and the other is W is not empty。😡，So case one， W is empty， case two is not empty。

Which means that Q is equal to AX。So symbol A。😔，And string X。哎呦。

So now I need to write down this proof once for each case。So I'll start by writing down。

The thing that I want to prove something about。And with the thing that I want to show it's equal to。

And now I'll start chasing definitions。Well， I'm in the case where W is empty so I can replace W with empty。

😡，So this is Delta star of P comma Q empty string because W is the empty string。

Now I'm going to apply the definition of Delta Spf。

Remember Delta star is what I get starting at a given state。

 if I follow the instructions specified by the second argument， the word。

 what state do I end up in so if I started state and I followed the instructions given by the empty strain。

😡，Where do I end up？In exactly the same state where it started。So this is by definition。😊，Ea Q。

By definition of deelta star。And now we're actually done。

Because p is equal to deelta1 star Bw by definition of delta star1 and  Q is equal to deelta star  Q。

 oh I should I should do one more I should put one more line in there just to be horribly pedantic。

 so it's no。😡，Let's。Epsilon Epsilon， this is again by definition of the Delta star。

 and this is because W was empty。Thanks。So definition， definition， definition， definition。

That's the way all non inductive cases seem to go occasionally there might be a line in there that you'd say math。

Or Lemma5 from the notes or something， but usually it's just definitions。Okay。

 so let's do this again。For case two。There's the thing I want to show equal to something else。

Here is the something else。Okay， so I'm assuming the w is equal to AX。

 so I can substitute AX in for W here。嗯。At this point， I can invoke。The definition of Delta star。

 when the argument string is non empty， I say， oh， okay。

 so I'm going to do a normal one step transition on the first symbol A。

 and then I'm going to recursively do the extended transition function on on the result of that and with X so just write that down that's recursively。

From the state that I get to by。嗯。Transitioning on A。And transitional an x。

 this is the definition of deelta star。Now。If you're uncomfortable treating that pair PQ as a single state in the definition of Delta star。

 give it a new name， let's call that pair PQ instead of writing down open print PQ close print。

 I'll just write down in a single letter bar。😡，And then substitute and then substitute again。Right。

Okay。So now I'm going to take this thing here in the middle deelta。

 this is the transition function for my product machine， I'm going to expand that definition。

 so this is deelta star of a pair。😡，Give an X。And the pair is going to be delta1 of P comma a deelta2 of。

Sorry， Q comma A。This is by the definition of the transition function。嗯。Now， at this point。

I'm looking at running the extended transition function of Delta star on some pair of states。

And the shorter string xed。So I'm now looking at an instance of the problem that I started with。

 given this pair of states in this string， where do I end up？Okay。

 now I've got another pair of states， they're not the same states that I started with。

 but that's okay， and I've got a shorter string X， so at this point I can invoke。Recursion ferry。

And write this as。Delta star1。Of。Delta1 of P comma a comma x。Delta star2 of Delta2 Q comma A comma x。

And this is by definition。Delta1 star of P comma Ax。Delta 2 star of Q comma AX。

This is by definition of。Well， really Delta1 star and Delta2 star。Um。

And this is because w was equal to ax。Yeah。This is a lot of symbols。If you just， you know。

 if you wake up now， oh good morning， welcome to 374。This will be on the final exam， no。

This will not be on the final exam if if you just wake up now and go， oh my God。

 somebody vomited all over the screen。After eating some Greek food。嗯。

But I do want to reassure you that nothing weird is going on here。

 it's just that I'm doing things that computers normally do。😡，With a pencil。

So I'm just doing mechanical symbol manipulation， following the definitions of the objects that I'm playing with。

 what makes this overwhelming is the belief that I should be able to glance at it and understand what's going on。

So this is something again， that will come up over and over again in this class。😡。

You have to learn to trust the process。😡，The way that you gain confidence in a proof。

 an argument like this is you investigate each individual step one by one。

 do I believe the first step， well I wrote down this justification。

 W equals AX so if I mechanically replace W with AX yes， that's what I get good。

 I believe the first step。😡，And now do I believe the second step？Well。

 it may be a little uncomfortable treating that pair PQ as a single state。But aside from that。

 I'm just writing down expanding the definition of Delta star in the recursive part of the definition。

And so at every step。I need to check， do I believe this， do I believe this， do I believe this？😡。

And even there， what's often the right way to approach this is。

Don't try to approach each step intuitively， but rather just do the mechanics。

Don't try to skip ahead， don't try to see the trick。😡，Don't try to see what it means。

But literally be a computer。And just replace this set of symbols with this new set of symbols。And。

That way， you know that this step is correct because you executed the algorithm to generate the next step。

😡，This is deeply， deeply unsatisfying at the beginning。But it comes up。

 you know this is something that a sort of technique that served me well over many years。

 so when I got to started my PhD program， I had never seen probability before。

I'd somehow managed to get through undergrad and master's degree without ever engaging with probability in any meaningful way。

And unfortunately， when you're at Berkeley， every theory class eventually turns into a randomized algorithms class。

So you have to know probability。And probability is notoriously counterintuitive。

 so eventually I found that the only way I could do the homework in my theory classes when it came to probability was just translate it mechanically into okay。

 thiss a sum of a bunch of probabilities and I'll just write down the formulas for those probabilities and grind through the algebra and do it repeatedly until I got the same answer three times in a row。

😡，Sort of trust that that's probably the right answer。I had no intuition at all。

 but by following the rules mechanically and double checking by doing them again and again。

 eventually I gained some intuition out of it。😡，嗯。So u。I'm sorry it can be tedious。

 but I just really recommend doing for the same reason that when you're writing code。

Like you you check， you know。It's not just I should be able to look at the code and know that it's right。

 no， nobody can do that。😡，With reasonable length of code， what you do instead is you reason。

 is this line of code doing what I want to do， is this loop doing what I want to do。

 is this function doing what I want to do， and then you trust that and move on。😡，系。

There's a question over here。好。好。Okay， so this is a great question how do I follow a proof mechanically and know that I'm not going off on a wild goose chase you don't you try all the wild goose chases。

 this is why you don't write proofs for the first time on the sheet of paper that you're going to hand in。

This is why you do proofs on a whiteboard that you can backtrack in erase。

This is why you do proofs on， you know， type it or write it on a tablet so you can go， okay。

 the first three steps I believe the rest of it， obviously I went on the wrong turn。

 let's try this instead and you can copy paste。You will make wrong decisions， that's okay。

 that's part of the learning process。😡，And then over time。You'll gain an intuition that says。

 I think I should go this way instead of that way。There's no way to learn to do the thing。

Other than by doing the thing。There's no way to learn not to make mistakes。

 except by making mistakes。😡，Okay。So this lemma。Says。

Transitions behave the way that we expect them to behave I told you that the way we transition on single characters is to give those single characters to my component machines。

😡，And through this complicated wall of symbols， I inferred that the way that the product machine transitions on a string of symbols。

😡，Is essentially， I independently feed that string of symbols to each of my component machines。

And this is how one argues by chasing through like definitions of acceptance and so on。

 this theorem about the the。Product machine that I built here。Okay。啱。Questions。Yes。I'm sorry。

 you'll have to speak up the acoustics in this room terrible。好。あさ？So sorry2。Again， Typo。

 the two key Im keyboard is a bit sticky。嗯。Yes。Thank you。Yeah。Okay， this is an excellent question。

 so let me show you these other examples and then I'll talk about redundancy in a second。All right。

 so this is the product machine that you get。If you say or instead of and， so this is union。

 this is the product machine you'd get if you say exclusive or， this is a symmetric difference。嗯。

This is the product machine that you get if。You say， you know， if it has a zero0。

 then it also has a 11。So this is one form of set difference。It's complement and set difference。

So in each of these， the only thing I've changed is which states are accepting。😡。

And the way that I changed it is replacing the word and with the word or replacing the word and with the word exclusive or replacing the word and with the word implies。

U。So get these different boolean combinations。Now you， as some of you have already noticed。

There are redundancies in these machines。😡，So for example， if I look at。This state here in yellow。

In all of these machines。How do I get into that state？Here。So that's known as an inaccessible state。

 there is no path from Dar state in the upper left corner all the way to get to that middle state AA in the center。

😡，So this state does not play any role whatsoever in the acceptance or rejection of strings and so I can delete it。

😡，No。When we're doing product constructions， especially。😡。

I just want you to say it the product construction， we know it's going to have redund。

 but we're not going to ask you to optimize the number of fits。😡，Hey， just。

Product construction is actually a simpler description than oh it's a product description。

 but now let me minimize the DFA for you if you're going to do that then probably the right thing to do is just to say here's the final DFA。

Right。So I want to show you another example of this redundancy in this ore machine over here on the left。

嗯。If I look at this state。Here S be in pink。If if you look at this carefully。

 I'll notice if I ever reached this state。😡，No matter what symbols I get for the rest of time。

 I will always be in an accepting state。😡，Means this is not terribly surprising because the original factor DFA does this string contain two ones in a row。

 once I reach the third state I'm always going to be in the third state。

 I've seen two ones in a row I don't really care what the rest of the bits are。

 that's what's going on here that state SB says I've seen two ones in a row and I'm still in the start state for the other machine。

😡，Okay， but no matter what I see from now on， I know I'm going to accept。😡。

And that's also true for this state down here and this state here and this state and this state。

If my ore machine ever ends up in any of those five states。😡。

Then I know I will eventually accept when the input finally ends。😡。

So there really is no reason to distinguish among those five states。

I really don't need to keep track anymore of what state I'm in in my two component machines。

 the only thing I need to remember is when the input ends accept。😡，So those five states。

Are all equivalent。And so I could make the DFA smaller。Why having only。Four states。Right。

 so it takes a little bit of。Sorry， that should be a one。

A little bit of time to actually write this down。So this is a DFA that accepts all strings that either contain two zeros in a row or contain two ones in a row。

 or in other words， this machine accepts all strings that ever have two symbols that equal symbols in a row。

😡，So my start state over here， I haven't seen either of these in a row， every time I see a one。

 I go to this state at the top， every time I see a zero， I go to the state at the bottom。

 but if I see the same symbol I saw at last，😡，Transition。

 I go to the accepting state and I stay there forever。系。And there's a systematic way。I said。

 you know， I've mentioned this already， there's a systematic way of taking。

Any DFA and compressing it down to a DFA that has the minimum possible number of states。😡，Okay。

 so I want to talk a little bit about this， but let me first， you know。

 do the conclusion of this sort of product construction stuff。

Which is sort of a general theorem about automatic languages。So if L1 and L2 are automatic。Then。

L1 Union L2 and L1 intersect L2 and L1 exclusive or L2 and L1 without L2 and L1 complement。

 which is really just sigma star minus L1。Are all。Automatic。And in light of Kney's theorem。

This is also true now for regular languages。嗯。Now。Regular languages。

Satisfy one of these properties by definition。If L1 and L2 are regular。

 then L1 Union L2 is regular by the definition of regular。😡。

It was one of the components of that definition， what a regular language means。

 the regular expression is you write down the regular expression for L1 plus you write down the regular expression for L2。

But the vocabulary of regular expressions doesn't include intersections and differences insymmetric differences and so forth。

 it could， it wouldn't make those languages any more expressive。

 it would just be more compact notation， but it would also be more difficult notation to reason about。

😡，But because weve expressed these things as DFAs instead of regular expressions。

We get these automatically out of this product construction。On the other hand。

 regular expressions tell you things like the concatenation of two regular languages is regular。😡。

By definition of the word regular。It's not so easy to concatenate to DFs。😡。

The clany star of a regular language is regular， it's not so easy to put a star around a DFA。

We'll see how to do that once we get to something called NFAs， but like I said。

 it's going to take a few stages to get there。Right。All right so。嗯。

The last thing I want to talk about today。For five minutes。Is。

A little bit more about this idea of states being redundant， states being distinguishable。

 so this is actually a DFA for recognizing strings that contain two ones in a row。Okay。

 this is something I got by writing out a program to recognize those springs and interpreting the states of that program as states of the DFA。

Then I removed all the inaccessible stuff。Right so。

There's a formal sense in which I can say that like two states are。Indistinguishable。

But I'm going to write that as in the opposite way。P and Q are distinguishable。😡，What this means is。

嗯。For some。String。Tell you。Delta star of P comma W is accepting。And。

Delta star of QW is not accepting or vice versa。So just give you a concrete example here。

 let's get state zero。And state three。All so I'll start here at state zero and I'll start at state three and I'll just sort of map out what happens when I start feeding zeros and ones。

To these things。Well， if I'm in state zero and I read zero， I'm going to end up in state one。

 if I read a1， I'm going to end up in state two from state three， if I read a zero。

 I'm going to end up still in state three and if I read a one。

 I'm going to end up in state four okay none of these are accepting state so I haven't distinguished anything yet。

But let's push this a little bit further from state one， if I read a zero。

 I'm going to end up in state three， if I read a one。

I'm going to end up in state four from state two， if I read a zero， I'm going to end up in state5。

 and if I read a one， I'm going to end up in state nine， which is an accepting state。嗯。嗯。

If I read a zero here， I go to three， here I go to four， here， I go to five， here I go to nine。

And this is an accepting state。And at this point， I can confidently conclude that zero and three are actually indistinguishable。

If I go two steps away from zero and I follow the same two steps away from three。

 I get to the same states。Okay， so。Zero and three are in the same equivalence class。

 they're indistinguishable but from by this definition。

 so I can just think of them as the same state。😡，Any arrow that I have pointing to zero。

 I can redirect to three or vice versa， in this case I don't have any arrows going into zero。

 but I could change the start state to three and remove state zero and would have no effect on how the DFA behaves。

😡，嗯。All right， on the other hand。Let's suppose I start with， I don't know， state one and state four。

Okay， so again， I'll start with state one and state four， and I'll sort of quickly realize。That。

If I get。The symbol one in state one， I end up in state four， which is not an accepting state。

 but if I start in state four and I read one， I end up in state nine， which is an accepting state。

 so one and four。😡，Are distinguished by the string one。

The string one leads from state one to a non accepting state。

 but it leads from state four to an accepting state， so state one and state four are not。😡。

Distinguishable， or they are distinguishable， they're different。😡，I cannot merge those two states。😡。

So if you sort of walk through this logic。😡，There's a complete description of the algorithm in the lecture notes。

You can partition the states of any DFA into equivalence classes。

All the states within one equivalence class are indistinguishable。😡。

The same inputs lead to the same exception。😡，Bringing in any of the states and what you would end up with is all of these yellow states are indistinguishable so I should collapse them down to a single state。

 all those blue states are indistinguishable， so I should collapse them down to a single blue state。

 all these pink states are indistinguishable so I should collapse them down to a single pink state and this now looks like the familiar machine that we've been playing with from the beginning that recognizes two strings of two ones in a row。

Okay。Next time。We'll talk about how to leverage this idea to show that certain languages。

 please sit down， we have two minutes left in class， please sit down。

 we have two minutes left in class， please sit down， we have two minutes left in class， thank you。

To show that certain languages are not regular， people have asked me this question in the past because not all languages are regular。

😡，We'll finally show on Tuesday。Examples of how you prove that certain languages are not regular but basically showing you'd need an infinite number of states now we're done thank you。

😡，I'll see you next week Oh remember Monday is Labor day， no Homer party。

here so if you choose from David we different starting points and finally reach out their vi no point。

They are the same， so we can merge them， right。

![](img/8b8c17a35bc2d65e80471b5ce3ca83ad_6.png)

然后。