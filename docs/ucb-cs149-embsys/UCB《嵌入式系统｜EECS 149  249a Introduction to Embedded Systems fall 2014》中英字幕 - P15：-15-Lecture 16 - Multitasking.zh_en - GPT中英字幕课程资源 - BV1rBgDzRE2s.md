# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P15：-15-Lecture 16 - Multitasking.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

咁。

![](img/0e6565636ef2e9049bbeab928c52cd5c_1.png)

The big picture。Is that state machines give us a way of formalizing。Decision logic。

Discrete decision logic， sequential decision making， okay？

And you can use it to formalize fairly complex behaviors。And。In some ways。

 when you use state machines manually。They don't look very tractable， right in some sense。

The examples that we look at are all oversimplified。

they don't really respect the realities of a situation。

 which tends to lead to complexities that become overwhelming when you're using a bubble and arcs kind of diagram。

嗯。We add some notation to the state machines that enables us to handle a little more complexity manually for example。

 extended state machines which give us。The ability to manipulate variable values as part of the state machine。

And。Concurrent composition of state machines where we can take two relatively simple state machines and compose them either synchronously or asynchronously。

The composition itself defines a state machine that can be quite a lot more complex than the two individual components right so that know as a general engineering principle。

 this is a good thing to do right you break down a complicated system into simple components。

And you're not eliminating the complexity in the complicated system。

 you're just making it a little easier to understand， right？

But the real value in state machines is that if you have a good formal state machine model。

 then it's subject to mechanized analysis。Okay， and that's where the real value comes in where。

I shouldn't say the real value， it's also valuable you know。

 for our limited brains to try to understand a system right， I mean。

 just attempting to construct a state machine description of some system can give you a lot of insight。

Into that system。 so it is valuable for the human cognition part。

But it's even more valuable because you can throw automated tools at these state machines and they can reveal behaviors that you didn't expect and you can use them for example to check for safety conditions so I'm going to try to illustrate that today and again I'm going to have to oversimplify the state machines in order to do it manually。

 but hopefully it'll give you a sense of how you can use them with an automated analysis。Okay。

So just as a reminder， we talked about synchronous composition and here's a very。

 very simple example。Two state machines with no inputs。So again。

 I want to remind you that one of the key principles in our state machine formalism is that the state machine itself doesn't decide when it reacts。

Okay， the state machine says nothing about when it reacts。

 the environment chooses when the state machine reacts。Okay。

 when you have a composition of state machines。The environment chooses when the composition reacts。

ok。You then get to choose what it means for the composition to react。

But the environment's going to choose when the composition reacts。

 So the environment chooses to react this composition of A And B。Okay。

 and the question is what do you do？If you choose to do synchronous composition。

Then the two machines react simultaneously and instant。ok。And in doing so。

 they're actually behaving like another state machine， a single state machine。

 which is described over here。there's simultaneous and instantaneous reactions。

We'll take you from the initial state， S1 S3。Which is this initial state。To the next state， S2 S4。

In one step， instantly。and you'll produce the output B。And then in the next reaction。

 when you're in state S2 S4， you will。Instantaneously go back to the initial state， okay？So。

When you're doing composition of state machines， the first thing to do is to try to understand the state space of the composition。

And。A brute force way to get a state space for the composition is just form the product space。

So each of these state machines has some number of states。

 in this case these are not extended state machines。

 so the number of states matches the number of bubbles。 but if it's an extended state machine。

 it doesn't。Right， but in any case， each state machine has some number of states。

If you have two state machines， this one has some number of states。

 this one has some number of states。Then the total possible state space for the composition machine is the product of those two state spaces Okay。

 so in this case， two states here and two states here gives us four states there。This， by the way。

 just forming the product space tells you why this is actually a powerful methodology because you can describe complex systems with lots of possible states using state machines that don't have very many states。

And that's where the engineering value comes in in being able to modularize systems， right？But。Okay。

 so in this case。The product space has four states， but two of those states are not reachable。

There's no path to them from the initial state。Okay， so are they in the state space？Well。Sort of。

But not really。And in fact， we're going to look later at the notion of equivalence of state machines。

 okay？In。What I do have described here is a four state state machine。

 it just happens that two of the states are not reachable。

But this state machine is equivalent in a very strong sense to a two state state machine。

That doesn't include these states。Okay， that notion of equivalence we can formalize as well。

 and we will， in fact， formalize it， and it's very useful to formalize that notion of equivalence because you can determine if you simplify a system。

 have you changed its behavior？Okay。That's an important question to ask。O。All right。

 so that's synchronous composition if we take the same two state machines。

And we compose them using asynchronous composition。

Then we have some choices because the word the phrase asynchronous composition by itself isn't enough to tell us what it means for the two machines to react。

If I choose an interleaving semantics for my asynchronous composition。

 then a reaction of the composition consists of first。

 non deterministically choosing one of the two machines。And letting that machine react。ok。

And then in the next reaction， I non deterministically choose one of the two machines and let it react。

that's what an interleaaving semantics for asynchronous composition means。

And the resulting composition is itself a state machine， which again， has four states。

But in this case， they're all reachable。 and the resulting composition is a non deterministic machine。

There's more than one possible reaction in each state。All right， now。Okay。

 so let's see if we can apply this composition mechanism to a real problem in embedded software。Okay。

 so you remember we looked at this。Pieace of code when we're talking about interrupt service routines。

And how to control timing in a program and the idea is that you know I want to write a program that's going to do something for two seconds and then do something else。

 okay so this might be some initialization phase， your program is supposed to make pleasant sounds for two seconds so that everyone thinks that they're happy and then it goes on and does whatever annoying things it does after that right？

Whatever it is， okay， you're going to do something for two seconds and then go on。

 So the question is， is this code correct？Now one way to pose the correctness question is。

 do you in fact get to？The point in the code after this two second loop。Okay。

 can you assure that you will get there， that would be one simple correctness criteria right I'm not even going to worry about whether it takes two seconds。

 just will I get there。Okay。That's if I can show that there's a way that I won't get there。

Then I clearly have identified a bug in the program regardless of the timing。Okay。All right。

 so can we use state machines to analyze this problem that would be the key question。Of course。

 this is a C program。And。According to the von Neuman model of computation。嗯。

A C program executes as a state machine， right under the Vanon Neuman model。

Your computer starts with an initial state， which is the contents of the memory。

And then your instruction set architecture has a set of operations that transform the memory。

Memory here includes the registers and everything， all the state。

 all the possible state of your machine， all of the memory in the machine。Each instruction。

Change is state。 Now， the number of states is。Enormous。I mean， if you have two gigabytes of memory。

Two gigabytes is。16 gigabits。ok。So the state of the main memory in this machine has。呃。Two to the。

A lot， there's a lot of states。Okay。So you're not going to want to represent the state of this machine using a bubble and arc diagram。

It's not going to work。嗯。So we're going to have to abstract somehow what this program does Okay。

 so one way to abstract programs in a useful way is let's just look at flow control。Okay。

 how does the execution proceed through a sequence of instructions in the program？

So we can identify sort of key points in the program like this。So for example。

I identify a position D just before a branch。And a position e just after the branch。Okay。Similarly。

 the wild statement is also a branch， so I've got a position A just before I enter the while loop。

 position B， when I'm starting the body of the wild loop and a position C。

 which is what I'm ultimately interested in is will I get to see。ok。

That's going to be the question that I'm going to ask。Okay。

 so if I say these are all the interesting points in the program。Then。

Can I answer this question definitively using state machines？就。

I want to emphasize the word formal again here， okay because the informal way to do this is you kind of scratch your head。

 you look at this program， you think through all the possible threads of execution that you can come up with。

And you kind of form an understanding of how the program works， and you come to a conclusion。

And the problem is that。With。Non trivial systems。 This is a pretty trivial system。

 so you can probably。Go through all the possibilities。

 although there's a pretty good chance even with this， you're going to miss some。Okay。

But with a more complicated system， I guarantee you will miss some。

you're assured of missing some and so the formality of the mechanism。

Means that we can actually do an exhaustive search。

You can actually show that study all the possible executions kind of all at once。

 and that's the power of the method。Okay， so let's try to apply state machines to this model。

 So here are two state machines for the two parts。 There's a main program。

 and there's an interrupt service routine and。In good engineering practice。

 I want to modularize this program， I'm going to describe each of these two components using a state machine。

And I could do it like this， there's many choices， by the way， I mean， you know。

 there's kind of an art to constructing these models。

Although you can also mechanize the construction of these models。

But the result of a mechanized analysis of this program will be a much bigger state machine and it's not going to be one we're going to want to look at manually because it'll overwhelm you right it's one that you're going to want to look at automatically。

But when you're constructing these things manually， you choose some abstractions， okay。

 so here's one possible choice。So the main program。Let's just say， okay。

 nothing interesting happens until we get to A， so we'll just call that the initial state。ok。And。

It's an extended state machine where we have a timer count variable that we initialized to value 2000 as we enter the initial state。

Okay。Then do we go to B， well， we go to B if the timer account is non zero。And after we're in B。

 what do we do， well， we always return to A。Okay that's the only thing B can do because this is a w loop。

 so after B， Id just go back to A。When I'm in a， if timer count is0， I will go to C。Okay。

 so that's a nice state machine abstraction of a pretty simple snippet of code。Okay。

 let's look at the interrupt service routine， the interrupt yes question，A good question。

 so the question is， when does the move between B and A happen？

Remember that in our state machine formulaism， your state machine doesn't get to choose。ok。

So this is a key question that we're going to have to resolve is when is this thing going to react and how are we going to coordinate the reactions of these two state machines。

 are we going to do synchronous composition， asynchronous composition or something else， right？Okay。

 for just one state machine， in fact， the C program doesn't say either。Okay。

The C program says nothing about when you go from the end of this wild loop to do the test again。

Okay。There's nothing in this model that says。ItIt's a perfectly valid execution of this C program。

To enter this block of code and then put my machine in suspended animation and go out to lunch。

And come back and then start the clock up again and go back to well， again， you know。

 all the C program says is these are the sequences of operations to be performed。

 it doesn't say anything about when they should be performed。Yes。

So our formalism has the same property as the C code。

 which is that the formalism says nothing about when that transition is taken。

 it just says that if you're in state B，And the machine reacts， then it will go to A。ok。Yes。

 question。No。So the question was， if we're in B and timer count reaches zero， will it go to C？

And the answer is no， certainly not in the formalism because there's no transition there。

 but also not in the C code。Okay， so the model is a good model of the Cco because B is the state of the program execution。

 in fact， before I even enter this block of code。ok。

So once I've made the decision to enter the block of code， I'm at B。At that point。

 if timer count goes to zero。Nothing happens I will execute this body of code until I go back to doing this test again。

Does that make sense？Yeah。C doesn't work that way， there are programming languages that work that way。

 so in particular， if I wrote this program in SL， okay？I could say， while watching this time account。

 execute this。And if the timer count goes to zero during the execution of this。

 I could abort the execution of this and go to the next step。

But that's way that's not the semantics of C。 C is going to test this timer count only at the beginning of this while loop。

 and it ignores its value during the execution of this body of code。Right。

At the end of the execution of this body of code， it goes back to the beginning and performs the test。

Again。 which is exactly what our model says。At the end of the execution of that body of code。

 we go back to the beginning and perform the test again。Yeah， so one of the problems is that。

You what exactly do I mean when I put these arrows here saying this is where we are in the code。

It can be a little bit tricky， but what A means is I'm about to do the test。Okay。

 to determine whether to take the branch。To execute the body of code or to skip to the next。

Execution， right that's what A means。Okay。And then B is I've already made the decision。

And I'm now going to execute this body of code。Yes。有。Right， yes， that could happen yeah。

 so if you were to pause the execution of this body of code indefinitely。

 your timer interrupt could still kick in。This model doesnt this lower state machine by itself doesn't say anything about what happens。

Okay， because so far it doesn't include the interrupt service routine。But in fact。

 the C program also doesn't really say what happens。Okay。

 it's a perfectly valid execution of the C program to pause this indefinitely and let the interrupt service routines continue to execute。

That is a valid execution， yes。Yeah。嗯。So whoops。こたね。Any。No。So in our formalism。

 the transitions only describe what we do in a reaction when we're in this state。ok。There's actually。

 the notation does not directly provide any way to say， if I'm in this state。

Then I not in the current reaction， but in some future reaction， I'd like to go to C。All。

The only way we have to say that is to go to an intermediate state。In life。Oh， we choose。Well， yes。

 that's right， so the transition from B to A has no guard on it， and in our notation。

 that's just a shorthand for the guard is a boolean that evaluates true always。

So this transition will trigger if you're in state B and the machine reacts。

 we will move from B to A。There's no question， there's nothing to test。Okay。

these are good questions because， I mean， you there's a lot of arbitrariness in this notation。

But there's a lot of arbitrariness in any formal notation。And so you in order to use a notation。

 you have to get used to it。And you can't argue that it's wrong unless it's inconsistent with itself。

 right？All formal notations that are consistent are equally correct。Formal means devoid of meaning。

The most useful formal notations are not only correct， but also useful。Right。

And hopefully this one is both correct and useful。You know。

 it is there are arbitrary decisions and you sort of have to get used to it in order to use it。Okay。

Okay， so we've got， I think hopefully everyone's on the same page and understands this first state machine pretty completely yeah。

Right。呃。Yeah， actually， that's a good question so if A had a self loop would this still be a faithful notation。

 in fact， because of the semantics of C， I could put a nondeterministic self loop on all these states and it would still be an accurate description of the C program。

Oh， I see what you're saying。Yeah， this is another shorthand in our notation， right， which is。

If we're in state A and well， actually we have all the conditions covered。in this case。So。嗯。

But you could have a state machine that's incomplete in the sense that you could be in a state and there's no enabled transition out of it。

And we implicitly assume there's a self loop。That is taken if no other transition is enabled。Oh。呃。Oh。

 I see and get rid of B altogether。嗯。Yeah。嗯。It。Yeah， so Martin raises a very good question， I mean。

 would this state machine be equivalent if we just eliminated B and had instead of this transition from A to B。

 it just went right back to A and if you look at this state machine by itself。Then yes。

 it'll be equivalent， but I'm not sure it's going to be equivalent when we compose it with the other state machine。

Right。Yeah， so I'm glad you raise that question because I'm going to put that on the second midterm。

嗯。Because。At that point， you will have the equivalence refinement。

Ability to compare state machines and determine under what circumstances they are exactly equivalent。

And this would make it potentially very nice example。For testing that。That mechanism。

 I'm not sure what the answer is， by the way。It will depend on how we compose it yeah。你我。아야。

able it that'll stop it from。So then when you enable it， will that reset？The new like little second。

Because I'm thinking。给我们。Okay， so thats you raise a good question and it's a slightly complicated question because really it deals with what really does it mean to disable interrupts here？

嗯。And then reenable interrupts， okay？And I'll tell you what it means from the perspective of this C program model。

 and it's actually quite simple from the perspective of the C program model。

 but how it manifests in a physical system is not so simple。

From the perspective of the C program model， it simply means that this procedure will never be reentered。

So you don't have to write it to be reentrant。In other words。If I'm executing this procedure。

Then I cannot begin a new execution of this same procedure。Until I'm done executing this procedure。

ok。That's the only thing it means from the perspective of the C model。 Now。

 that plays into how that plays out in terms of timing。

Is actually not expressed in this C program at all。

And how it plays out in terms of timing is going to depend on the hardware that you connect up to this thing。

 what does the timer do， how does it handle toggling of the interrupt request line you know what if the interrupt request line transitions。

During the time that I'm executing as interrupt service routine， will it respond to the interrupt？

After it's done when it enables interrupts or not。That's up to the hardware。Okay。

And it's actually not expressed in this C program。This is， by the way。

 one of the real challenges with embedded systems is that actually we work with models that are very incomplete。

 they actually don't tell us a lot of things we need to know about how the system is going to behave。

I consider this a flaw in our current technology， and it's valid to look at this critically and say。

 gosh， you know， actually， it would be nice to know that and it should be expressed in the model。

But it's not。Okay。All right， okay， so first question。Okay， wait。

 let's make sure we understand the top state machine。Okay， so first of all。

The interrupt service routine is a little bit stranger than Maine because in the main program it was I could clearly define an initial state being at position A。

But the interrupt service routine， I can't really do that because。When this thing starts up。

 it may not even the interrupt service routine， I may not be anywhere， I'm not at D， I'm not at D。ok。

Because the interrupt hasn't been triggered。So I needed to add an extra state， an idle state。

 which just says， I'm not in the interrupt service routine at all。ok。

And now I need to define an external input， assert， which is a pure input。Okay， that will。

Take me to D。So whenever that external input is provided。

 this interrupt service routine will go to D。And then when it's indeed， it will test the timer count。

 and if the timer count is non0， it'll go to E。 otherwise。

 it will transition back to idle and issue an output return。Okay。If it goes to E。

Then it will unconditionally in the next reaction。Derement the timer count and issue the output return and return to the idle state。

ok。So everybody understand that。Stay machine describing the ISR。Okay。So how should I compose these？

Should these be composed as using synchronous composition？I see a couple of shaking heads， why not。

 Martin？Right， they're not synchronous， so it would be really weird， right。

 and it would actually be an incorrect。Model of the behavior， right because it would say， well。

 all right， so suppose my initial state would be idle comma A。And then when the composition reacts。

IBoth machines have to react simultaneously and instant。So if I get an assert。At the input。

 I will transition to D and depending on the value of time or count to either B or C。

But that's not what the C program does。Right。Okay。So is asynchronous composition the right thing to do？

And if so， which variant？Should I use an interleaving semantics or。Well。

 probably based on the same argument， the same reason I wouldn't use synchronous composition says。

 if I'm going to do asynchronous composition， probably it better be interle。

 I don't want these two machines to react simultaneously。ok。So then the question becomes simpler。

 will asynchronous。Interleaving semantics be the right way to compose these two state machines， yes。

Say it again。Right。Yeah， good point， what's your name？Sean， yeah， so Sean nailed it， he said， I mean。

 if I choose non an interleaving semantics， interaving asynchronous semantics。

Then I could have asserted the interrupt service routine in B and D， and then in the next reaction。

 choose to continue executing my main program even though I'm still in the interrupt service routine。

And that's not the way interrupts work。The main program isn't going to resume executing until the interrupt service routine returns。

Okay， and in fact。If I just brute force and construct the state machine that describes the non deterterministic。

 the interleaving asynchronous composition of these two state machines， there it is。O。

And this state machine has state transitions that won't occur in practice。So for example。

 it shows that I could go from AD。To。To BD。That's a transition that's allowed in this composition。

 but the C program won't do that。Okay。So we're kind of stuck。

 weve got two nice simple state machines。And all the composition mechanisms that we've come up with so far fail。

I don't know how to compose these。Okay。嗯。So。Let's choose a new composition。Semantics。

 which is hierarchical state machines。ok。Now。In order to do this。

 I'm going to have to come up with some description of how the interrupt controller works。Okay。

 so there's going to have to be some logic that governs how these two state machines interact with one another。

 I have to capture the fact。That。That if the interrupt service routine starts executing。

 it'll execute to completion。ok。And I could capture quite a bit more detail about the interrupt service routine。

 so I could start to answer questions by sorry， what's your name？That Josh raised， right？

Which is well you know what does it really mean to disable interrupts right so I could for example。

 have hardware that if an assert occurs while I'm in actively。

Processing an interrupt service routine。 Then I keep track of the fact that that assert has occurred。

And then in to later handle it when that service routine returns。

 I could capture that behavior in a state machine。But the hardware。

 this is a description of the hardware， this is not a description of the C program。

 this is not a description even of an instruction set architecture。

It's a description of a particular realization of the microprocessor。And the timers， okay？So yeah。

 so I could do that， but I'm going to use a simpler interrupt service routine because with that four state interrupt handler。

I end up with too many states on the PowerPoint diagram and again。

 you're going to be better off doing mechanized analysis than human analysis。

 so I'll simplify still further。Before I do that， let me explain hierarchical state machines。ok。

So again， there's a lot of arbitrariness in this notation。

 and this style of hierarchical state machines was originally introduced by David Harrell in 1987 in a formalism that he called state charts。

And。That formalism， it turned out， his original state charts paper， it turned out。

 was not really a formalism。There were a lot of ambiguities， and in fact。

 people went off and misinterpreted his paper and came up with many different implementations of state charts。

 all of which had different semantics。Okay。At one point。

 I read a paper that cataloged some 28 different variants。

Of hierarchical state machine semantics that were actually used by people in various contexts。

 and they were all different。So if you want to do anything， you have to pick one。

So I'm going to give you one， okay？And it is formal in the sense that it completely defines the behavior。

It's not subject to human interpretation if I give you a state machine。

 its behavior and set of possible behaviors is fully defined， okay？All right。

 so what does it mean to have hierarchy， well first of all。

 we associate with a state potentially a refinement。ok。So in this case。

 I have a two state state machine with two states， A and B。And B has a refinement。

 which is itself a two state state machine。And the way to interpret this is that。If I'm in state B。

 I'm actually in either C or D。ok。But it can be either one。Not both， one or the other。

So this is called in Harrell's notation， he called this an or state， called B in or state because。

It's not really a state， it's a placeholder for being in one of several other states。Okay。All right。

 so that says， well， all right， so immediately， how big is the state space here。

 how many states does this state machine have？3。Actually。It's either three or four。

Depending on another subtlety in the semantics。Okay。

So let me give you a hint on this and then we'll come back to this， right？

When I transition from B to A。I might remember where I was in CD。And when I come back to B。

 I might pick up where I left off。So if I left B well in D。Then if the next time I return to be。

 if I am still in the。Then actually this state machine has four states。On the other hand。

 if every time I enter B， I go to C。Then this state machine only has three states。Okay。

 so David Harrell introduced that notion as well， and he talked about transitions being either history transitions or not history transitions。

And history transitions actually give you a way of describing enormously complicated behaviors very compactly。

Okay， but the number of states can get quite large。Okay。Now。

 we have to define what it means for this hierarchical machine to react。So a reaction。

 by definition of a hierarchical state machine， consists of first， the refinement reacts。

And then the top level machine reacts。But these are even though they're sequenced。

 they're occurring in the same reaction， so you view these as being simultaneous。

Simultaneous and instantaneous。But you still have to do one after the other。

Its almost like a contradiction， but from the external view， what this means。Is， for example。

 suppose that I'm in state B and the machine reacts and both guard G1 and G4 are both enabled。Okay。

 then what's going to happen？Well， the refinement reacts first。

 I go from C to D and I produce output A4。And then。Higher level state machine reacts。

And goes from B to A and produces output A1。The important thing here is that A1 and A4 are simultaneously produced by this state machine。

Okay， they are both present on the output in this one reaction。Right。嗯。Okay。

 so this is a possible sequence of reactions。This is a trace which is a way to keep track of possible reactions。

 so we start in state A， if G2 is enabled， we're going to produce output A2 and transition to state C。

If G4 is enabled in the next reaction， we'll produce A4 and transition to D。

If G1 is enabled in the next reaction， then we will produce A1 and produce A。 wait a minute。

Did I let the refinement react？In this transition。I actually did， right， I'm in state D。

 the refinement reacted， but there's no transition out of D that's enabled。

 so its reaction was to stutter。It just stayed in the same place。

And then the higher level state machine reacted。Okay。嗯。Then for me， I might go back to D。😡，Oh。😮，D。

 I went to D。 So is that a history transition or a non history transition。It's a history transition。

 right， I went to D。So I remembered where I was。So now once I'm in D， if both G3 and G1 are enabled。

Okay。Then my reaction will be to simultaneously produce a1 and A 3 and transition to a。ok。

Where will I come into next entry into B？Into C， right because I took the transition from D to C。

Right， yes。Because think about this transition， right when I went from D to A。Okay。

 I'm now in state A。If my next transition brings me back to B。Where should I go？

I need to remember where to go， right I have to either go to C orD。If it's a history transition。

 I'm going to go to- well， either way， actually， it's going to go to C， but in both of these cases。

 anytime I go from A to B， if I have a history transition， I have to remember where I left off。

So there's more information just knowing that you're an A。Is not enough。

RightIf the only thing you know is that you're in state A。

 you're missing a piece of state information， so I'll make this more explicit by actually the way to answer this question。

 by the way， always， whenever you've got a composition of state machines and you want to know definitively。

 what does it mean？Translated into a single flat finite state machine。

That single flat finite state machine is the definition of the meaning of that composition。Okay。

 and so that's what we're going to do in just a minute， yes。那个。该给。Yeah， so that's a good question。

I'm assuming here that A1 and A3 are both distinct pure output ports。

So there's no possibility for a conflict here。But suppose you had a single output port with an int data type。

And the transition in the refinement。Seets the int to zero and the transition in the in the。

A higher level state machine sets it to one。ok。Then what is the output？It's a single reaction。

 so the output cannot be both zero and1。And it can't be a sequence， zero to one。

It's a single reaction， it can only have one value in the data type。Okay， so again。

 you need a semantics。And there are several choices。1 one choice is。It's undefined。

 your state machine is erroneous， rejected。ok。So that would be one possible answer。

Another possible answer， which is actually the default in Sl for integer data types。

 is the output is the sum of all the values that are produced。That strikes me as a little bit weird。

That's a choice， right？For any data type that can be added， it says， all right。

 if two transitions assert of same value in the same reaction， add them。Okay。啊。

A third possible choice is there actually is a well defined order。就。How these assignments are done。

 because the refinement always reacts before the containing machine。So as a consequence。

 these assignments to the output do occur in order， you could say， well。

 the output is going to be the first value or it's going to be the last value。Those are all choices。

 make one of those choices， and you've got a formalism， fail to make one of those choices。

 and you don't have a formalism。Okay。I think the choice that's made in the textbook is。呃。

That it's an error。Okay， but I'm not， I honestly don't remember。Yes， sorry。

 there was a question in the back。Right。Right。Yeah。Reactions are all instantaneous。

And the environment chooses when they occur。Okay， so add a reaction of a state machine。

There are input values and there are output values。That's it。No， no， no。No， no， no。

 the transition of the refinement doesn't occur in a distinct reaction from the transition of the containing machine。

It occurs in the same react。It it happens first， but within one refinement， so think of it as， okay。

 what it's expressing is the decision logic of trying to decide what the values of the outputs should be in this reaction。

And it's an imperative logic。Okay，In order to decide what the outputs are going to do。

 I first consult this guy， see what it asserts about the output。

Outputs and then I consult that guy to see what it asserts about the outputs。

And after I've consulted those two in that order， I know what the outputs are。

 And that's what the outputs are in that reaction。ok。Yes， skill。Setting variables。

 so that's a really tricky one right and you have to be careful and this is where a lot of state machine formalisms don't get it right。

Okay， in our formalism， the set actions are distinct from the output actions， okay。

 and the set actions are all performed。After the reaction has been concluded。ok。So for example。

 if I do a set action here。And I have a guard that depends on that variable up there。

The guard will be evaluated with the old value of the variable， not the new。ok。

That turns out to be an important。Requirement， but for very。

 very subtle reasons that we're a little bit beyond the scope of this course。

We'll hint at them when we look at feedback compositions of state machines， okay。

 because it's a way of ensuring deterministic behavior of feedback compositions。

But excellent question。Are there any more questions， yes， Mquench。Yeah。Inacted。只有。Okay。

 let's answer that question by flattening the state machine， so I'm going to do that。

So here is a flattened version of this state machine。ok。And this should also sh。Josh。

 Sean was back there。Yes， thank you。嗯。So this will hopefully answer Josh's question， Okay。

 so I initially started AC。Hopefully that's clear to see， right？And then I could transition to BC。

Okay。And from B C， I could transition to B D， or I could transition back to AC。Okay。嗯。If I'm in BD。

 however。Because this is a history transition， it would be incorrect to transition to AC。

Because if I go to AC C at that point， then next time I enter B。

 I'm going to enter at C rather than D。Okay， so I have to if I go to a。

 I have to remember where I was in the refinement。So AC says。

 I'm in A and if I enter my refinement again in the future， I should enter at C。And this state says。

 I'm in a， and if I've entered my refinement sometime in the future， I should go to D。

So that issue of remembering where you need to pick up where you left off。

Has to be captured in the state machine because it is state information， yes。说完。

Excellent observation。So if I have a whole bunch more states here。

Then the total number of states in my system will be the product of that number of states and the number of states in the refinement。

Suppose I have four states in the refinement and four here。Then this thing has exploded to 16 states。

 right， if it's  eight and 8， it's exploded to 256 states。As a consequence。

 you can really express very complicated behaviors very compactly。All right。Yes。

Because the representation here， the way to interpret this is I'm in state A。

 and next time I enter B， I should enter at C。Okay。

 remember that state is everything about the past that I need in order to move forward into the future。

ok。That's what it means to have state。Okay， so let's look at a refinement。

 suppose that we don't have a history transition。But a reset transition。

Then I no longer have to remember where I left off。Okay。

 so the flattened state machine just has to have a single state representing A。

 I don't need to remember where I left off。So if I'm in A。If I ever in the future reenter B。

 I'm going to reenter at C。O。So reset transitions are a little more compact。Okay， also。

A notational convenience。We allow her。Preemptive transitions， and again。

 David Harrell introduced these as well。So a preemptive transition is one where if the guard is enabled。

 we don't allow the refinement to react。Okay， we。Preclude that possibility if the guard is enabled。

All right。So it would be a good exercise to。呃。You know。

 make sure that you understand the flattened version of this state machine and how the preemptive transition is captured in this flattened version。

Okay， but let's apply it， so here's my simplified interrupt controller。I'm just going to say。

 all right， if my interrupt is inactive。Then I'm going to have a preemptive transition。 Okay。

 so when this machine reacts， if a is true， I will not allow the refinement to react。Okay。

 I will instead transition to the active state。And。When the active state。

When that refinement produces an output return。I will transition back to the inactive state。

 using a history transition。so now this is starting to look like an interrupt， right？And in fact。

 I can stick in my interrupt code and see that， yeah， actually， this is kind of how it behaves。

 right？And。If I make these state machine refinements， I can say， all right。

I'm executing Maine and I'm wherever I am。If aRT occurs， main is not allowed to react。

 I'm just going to stay where I am。And I'm going to transition into my interrupt service routine。

 which now no longer needs an idle state， it has an initial state D。Okay。

 notice that's a reset transition。When I entered the interrupt service routine。

 I always enter at the initial state。Okay， I execute until I produce the output return。

At which point I will transition back to enactive with a history transition。

And resume where I left off here。ok。So。We now have a formal model， I can ask a formal question。

Is C always reached？It it。No， it says nothing about speed。

 it just says that if I look at an infinite history of reactions。

There will be an infinite number of times at which an infinite number of reactions at which active is asserted。

Okay， in other words。嗯。Actually， I'm not even sure I need that constraint to answer this question because if I get only a finite number of assertions。

I don't think it changes the answer。What this was trying to get at was that I didn't want to examine the special case of where。

An interrupt request never occurred。Or an interrupt request occurred only once。Oh， actually。

 that is important because。If an interrupt request never occurs。

 the timer count variable is never going to change， and consequently， in fact。

 I will never reach C because time count will never hit zero。Right， so I do need that constraint。

Okay， so what it's saying is， you know。The timer hardware didn't fail。

It's going to keep requesting interrupts。Okay， that's what that assumption asserts Okay。

 so now we have a formal model， we can ask a formal question and there is one answer。

Either C is always reached or C is not always reached。There's no two answers here。

 it's not subject to human interpretation anymore。So what's the answer？If on every reaction。

 assert is true。Then， in fact， C will never be reached。

I want to emphasize this because this wouldn't have occurred to you if you're writing embedded software。

 and you set a timer to trigger every  two milliseconds。You kind of think， okay， you know。

 it's not going to be asserting interrupts all the time。Right？嗯。But， actually。You know。

 given the way the system is defined。The interrupt request is an input。

 you don't have control over inputs。What if your hardware has a stuck at fault and in fact your interrupt request line is stuck at true？

That's actually。You knowWithin what the system we've defined， that is。

A valid situation for the environment， because。It provides an input assert。

 it just happens to provide it all the time。Okay。But this could also occur in practice in the C program。

 right， suppose that。嗯。Suppose that this body of code always takes longer than the time between interrupts。

Then effectively， assert will always be， well， no， that's not quite true。

Suppose that this body of code。Always takes longer than the time between interrupts so the interrupt service routine actually takes a long time to complete its action long enough that the timer hardware triggers again。

Okay， then it could occur yeah。呃。Yeah， but to enable them again。

 so if the timer has pulled that interrupt request line high。

 it could just hold it high until it gets a reaction。Okay。So。

So even with interrupts being disabled and these things not nesting。

 but I'm glad you raised the question of nesting because。If you nest。Oh， before I do that。

 I'll show you what happens if you allow nested interrupts。Here。

 this hierarchical state machine can be flattened。Okay， and now the flat state machine。

 I can do exhaustive search。I can look at all the possible behaviors and I can find a trace that never gets to see。

And that trace is called a counter example。It's a demonstration that my assertion that this program would eventually reach C is not true。

Okay， the way the program is defined。And that's the kind of analysis that you can do。Yes。

If you nest interrupts。If you allow nestT interrupts。

 then you have a harder analysis problem because the state machine now becomes infinite。Okay。

 and if you think about the way it works in C， in fact， within the logic of C， it is infinite。

 right because every time an interrupt occurs， a bunch of stuff gets pushed on the stack。

 you go into the interrupt service routine if nested interrupt are allowed。

 while you're in that interrupt service routine， if an interrupt occurs。

 you push a bunch more stuff on the stack。Your stack keeps growing without bound。

That's infinite state。O。So that analysis problem becomes much more difficult。Yes。Yes。No。

 because this is a reset transition。And this is a history transition。

If they were both history transitions， then the state space would get much bigger。Yes。Well。

 this is a normal model， it all depends on what you mean by normal。呃。

I'm sure you could come up with even a synchronous。

Composition of state machines that would correctly capture this behavior。

But my guess is it would be a much harder to understand modeled than this one。Yes。

I know there's all kinds of assumptions， but I want to emphasize that the formalism sort of circumvents those assumptions about how the hardware works。

Because this formalism is an abstraction and all it says is。

When the environment chooses to have this machine react。Either assert is true or it's not。

That's all the formalism says。And it's up to you when you design the hardware to try to make the hardware behave like that。

ok。Right。It's。That's correct if you're in the active state and you react an assert is true。

That assert there's no transitions in your refinement or in your main machine。

That are triggered by assert， therefore assert will be ignored。No。

 you don't always reach the state Sea。Yes， but you have to reach state C in the inactive state。Right？

So and this is a preemptive transition。Okay， so if you transition from active to inactive。

And then in the next reaction， assertt is true， this machine will not be allowed to react。

Because it's a preemptive transition。Okay， so as a consequence I will never get to see now by the way。

 there's other scenarios also that can keep you from getting to see。

 but the way these formal methods work is you just you know。

 you make you want to prove a property about a program。And if you've found a counter example。

 you've shown that that property is not true。It's not the only counter example necessarily。

 but if the property matters to you， it's enough to have one counter example to say， oh。

 I got to fix this。Yeah， Josh， did you have a question？It means it's preemptive。

 so that means that when this machine reacts。If a is true， the refinement is not allowed to react。

And instead， this transition gets taken immediately。That's what abraemptive transition means。Yes。

You could， Yeah， yeah in fact。Pretty much all of the notation that we've introduced。

You can eliminate。And do everything with flat state machines。 You don't need default transitions。

 You just， you just need states guards and transitions。 And that's enough。 The problem is。

Interesting state machines get really big。So， but if you're you know， if you're a computer program。

 you don't care right up to a point and so actually you know the way that a formal analysis tool would work on a state machine like this would be to first construct。

The flat completely described state machine in a simpler notation， and then apply algorithms to that。

Okay。All right， let me close this discussion and then I really want time to talk about the projects。

 but just I wanted to give you a little snippet of the notation that Harrell introduced in '87。

So this is one of a Hrell style state machine。And。It has。At the top level。

 two states on and stand by。Okay。In the on state。There are two substate machines， which。

Harrell declared to be synchronous composition of two state machines。

Except he didn't get it quite right， but it was close。But you。

 fixed up its synchronous composition of two state machines。Okay。So he called that an and state。

So this on state is an and state because when you're in on， you're in normal and mute。Okay。嗯。Right。

 and yeah， and then well the rest of it is， I think hopefully pretty clear。Okay。

 I think I've said all this。Oh。Yeah， we're going to talk a little bit more about the algorithmic techniques that we use about this when we start getting into the analysis。

I'd like to turn to talking about projects。

![](img/0e6565636ef2e9049bbeab928c52cd5c_3.png)

And。

![](img/0e6565636ef2e9049bbeab928c52cd5c_5.png)

So。Project overview。You should form teams of three to four people in the past it's always worked to have you self organized。

Okay，But if that fails， appeal to us， you could talk to your GSI first。

 I would recommend using piazza also， okay。嗯。The effectiveness of your project will depend on an effective technical plan with realistic timelines you've only got till the end of the semester。

Okay。If you decide you need to order a bunch of parts from China。They may not get here in time。Okay。

 and if they come in January。It's too late。So。You need to be realistic， okay。

 we're going to strongly encourage using hardware that we've already got on hand。

 we've got a whole bunch of stuff and I'll tell you a little bit about what that is。

But we don't want to rule out projects that actually need。Some stuff that is purchased separately。

 and we have a modest budget that we can use to spend on these projects。ok。So nominally， you know。

 each team can spend up to $200 or so without us worrying about it， okay？

More than that is not impossible but。You know， you should talk to us and there better be a good reason。

Okay。嗯。All right。So。嗯。It's very important in these projects to have an effective use of models。

 You've got to use the concepts of the course。 If you just hack together a cool demo。

You're not going to get a very good grade。Okay， in fact。

 it is neither necessary nor sufficient to have a cool demo to get a good grade。

 you could have an extremely boring demo。With just a beautiful analysis of what's going on。

And that'll be an ACE project。ok。嗯。You need to have a good software architecture and don't just pack something together。

 it's not enough that it works。Okay， it should be modular。

 it should be using the principles of model based design and platform based design。

You should choose your hardware well。嗯。First criterion is， do we have it on hand？Okay。

Second criterion is， will it do you the job？I guess those are。

Maybe it should be the other way around， because if it won't do the job。

 then doesn't matter whether we have it on hand or not。Okay， all right。

 I think I've said all that now in terms of particular hardware。

 so one of the things that we'd like to encourage projects to do is work with a technology that's fairly recent。

 but you know， is really kind of progressed rather rapidly， which is。

Individualally addressable LED displays。And I'd like to give you a sense of why that might be an interesting thing to do。

 So first of all， there's a huge wealth of possible projects that you could do with this。

I'm envisioning things like。you know， interactive holiday decorations， right。

 a Christmas tree that lights up when you come close to it or that reacts nicely when you wave your hands you know。

 you know， but there's other， in fact， if you go to the project website。

 there's a pointer to a really nice YouTube video of a cube of LEDs that reacts。

 you can wave your hand at it and a wave of light propagates through this cube。Okay。

 but we want you to be kind of inventive， right， but it should be interactive。

 so you need some sensors。But there's something really interesting about these LED strips。

 and by the way， I wasn't joking when I talked about ordering stuff from China。

We ordered 100 meters of these LED strips from China。And they're stuck in customs。

And they have been for a while and the vendor you know promised one week delivery but it's been several weeks and so it's a little bit of a problem right ordering lag times are very unpredictable and they can be a huge risk factor in your project。

 you have to take them into account in your planning okay。But anyway， we expect。

 hopefully within the next week or so， to have 100 meters of these things now。

It's a big 100 meter roll， and it turns out you can take your pair of scissors and cut it anywhere。

Okay， and there's three wires。ok。One of those wires。

 you don't want to hook up to your microprocessor。Because it's the one that provides the power to all the Ls。

If you try to power all these LEDs with your GPI open on your microprocessor。

 you will fry it immediately。Okay， and that will lead up a good chunk of your budget and some of your time。

Right。So you provide power to them， and then you provide a single digital line and a ground。Okay。

 I can cut this thing anywhere。And I've got a single digital line。

 How do you suppose I tell the third LED to be red and the fourth LED to be blue。Any ideas？Soorrry。

Yeah， so one possibility would be that each of these LEDs has an address。Okay， and you can somehow。

 you know， using a serial line， pump that address into this one bit。

One wire and that LED that has that address will react and you can set the color。

But actually that's not probably a very good solution because you can cut this thing anywhere。

So how do you know which is the first LED， which is the second LED。

 How does the first LED know it's the first LED？Right。Yeah， other ideas。

The signal strength might decrease as you go down the line。 Yeah。

 but that would be an analog technology， which is going to be a lot more iffy than a digital technology。

 yes。A bunchun of shift registers。Yeah。But actually it doesn't quite work that way。

Give you just a little quote from the website from Ada fruitruit， which sells a bunch of these。

 says the protocol that's used is very timing specific and can only be controlled with microcontrollers with highly repeatable 100 nanosecond timing precision。

We have example code using the Arduino Uno or mega microcontroller at 8 megahertz and 16 mehertz。

 but it will not work with Raspberry Pi， basic stamp。

 Netduino or any interpreted virtual machine microprocessor or any processor slower than 8 megaherz。

You cannot drive these things from a Linux box。Even this one。You can't get the timing precision。Okay。

In fact， the whole way that these LEDs work is。If you pause for long enough on this digital line。

Then your next signal， the first LED will react to it。 and then once it has reacted to it。

 any subsequent signals that come within a certain amount of time will be passed on to the second LED。

And it will react to that and so forth， so you've got to very precisely control the timing in order to write to these LEDs。

There's a few variants of these strips。 You can get them in grids or in rings。So， but we want you to。

 you know， we want you to consider projects that connect them up with sensors。

 it's not going to be enough to just make a display， right。

 it's got to be some kind of closed loop behavior。We've got a partnership with the inventionion La which has a bunch of sensors you can use。

 okay and even you know there may be we may， because of the size of this group。

 we may really stress the invention lab resources， generally the way these things work is you borrow them and you can return them unless you destroy them in which case we pay for them。

 but that counts towards your $200 budget。Okay。嗯。But you know。

 we may have to order some if your projects require more of some particular sensor than what we've got in the invention line。

 so take that into account， there might be an ordering lag。

But the kinds of sensors are things like flex sensors， right so you could make a wearable strip。

 a necklace。That you know， reacts to。Bending in your arms or whatever。Okay。

 those are possibilities we have moisture sensors， so you could make a version that you know changes color if you start to sweat when you're working on the treadmill。

嗯。I don't know。There's there's a whole variety of different sensors。

 but if you go to the project website you can find these we also have in the invention lab there's some actuators and we also have a bunch of actuators in the Cory 205 lab。

In particular， these are kind of low level servos， so motors you can drive， okay using PWM output。

These are particularly interesting， these are bioid devices。

 so that little machine there is driven with a serial port connection and you can use it to build up you know various。

Axes of control from a motor。Processors。嗯。There's a variety of possibilities here， Okay。

 and we're open to projects using。Processor boards that we don't have or that are not on the list。

 but we strongly discourage it。Lead time is a problem。 You have to order it2。

 there's not going to be anyone around you with debugging expertise with these who has figured out how to get the software to work。

 You're going to be on your own on that。 right So were this semester。

 we're going to be steering people fairly strongly towards using。This particular board。

 okay it's an embed processor made by free scale， it's got a three axis accelerometer on it and a variety of other sensors。

 I forget exactly what it's not a very fast processor。Compared to the Beale board。

 this is a 1 gigahertz arm cortex A3， which is this is pretty much the same processor that's probably in your cell phone。

ok。This is not。All right。And this thing comes with an image of Linux。That you boot up。

If you write a program under this image of Linux， it will fail to drive those LED lights。

Okay you're going to have to use the bootloader and write raw code if you use that and that's probably not a good choice okay this guy on the other hand。

 you're going to be writing low level code， but this is a 32 bit microprocessor as opposed to an 8 bit microprocessor。

 so it's a little bit more beefy and faster than the 8 megahertz or 16 megahertz Arduino processorcessors。

Okay， I'm almost out of time， but I have a couple of other high level points that I really want to make。

Google is your friend。ok。If you don't use Google and you're doing stuff with this kind of technology。

You're crazy， I mean， you're not going to get anything done， all right？

But you must attribute your sources， okay？It is cheating to download open source code and not tell where you got it。

Okay， so building off the work of others is okay， in fact。You have to。

There's no way to do something interesting without building off the work of others。

 but failing to credit the others is not okay。 you should bend over backwards to credit your sources。

 which could be your colleagues in the class， by the way。Okay。嗯。

A professional always knows his or her sources， and by the way， if you go for a job interview。

Instead of saying， you know？Oh， I used an Arduino knowing something about what an Arduino is。

Is important。 So here's a couple of examples。 So all right。

 we're using the Arduino library for the Neixel。 That's these individually addressable LEDs provided by Ada fruitruit。

 which is written by Phil Burs。By the way， that's not always easy information to find。ok。But。

Everything you use was created by a human， who is that human？For those humans， right？

And it's distributed with an LGPL license， pay attention to the licenses， right。

 you should know what the license is of any software you use。嗯。In the case of Arduino。

 you could get really carried away。 So we used an Arduino Mega made by an Italian company smart projects。

 The mega is part of the Arduino family of open source software and hardware that started in 2005 as a project for students at the Interction Design Institute。

In Irea， Italy。Aduino is named after a bar in Evire。

 which in turn is named after an 11th century Italian king。Trust me。

 if you say that in a job interview， they will be impressed。 you know what you're working with。Right。

All right。You have to turn in a project charter， okay？

And we've put on the website a sample project charter to give you an idea of what we're expecting。

All right， so I encourage you to look at it， so this is a somewhat tongue in cheek。Project。

That we've entitled proper Res。And the goal of the project is to create a figure like a stuffed animal or something that you will place in a professor's office。

 maybe a little golden bear， that will bow to the professor when the professor walks into the office。

Okay。That's the goal of the project， the project approach， this is really important， okay。

 you want to model the arrival and presence of the professor as a state machine governed by a combination of sensor inputs。

foocusing on the timing of entry and the control of the robotic actuator。

 the goal will be to accurately detect arrival through the doorway and to time the reaction of the robot for maximum effect Okay。

 so arrival through the doorway is not the same as just there's something in front of me。

How do you model that？How do you detect the difference between a arrival at the doorway and a professor opening the door for a visitor who's coming in。

Okay。These are questions that you can start to answer by trying to construct a model of this system。

Okay， you should have some idea of what resources you're going to use are going to use the embedD processor from freescale。

As the processor core driving servos， you can leave some ambiguity。

 you're not sure whether the bioidids will be more convenient or the servos that are in the invention lab。

You can leave some flexibility there because you want to be able to explore。And so forth， okay。

 so take a look at the project one。

![](img/0e6565636ef2e9049bbeab928c52cd5c_7.png)

A final word， teamwork， teamwork is really important here。And teamwork。

Sometimes fails to work as well as one would like。Sorry， we're all a human。It's really important。

 though， to respect your team members。It's one of the reasons we've asked graduate students to obey the undergrad drop date。

 which means that if you haven't dropped the class， we expect you not to drop the class。Okay。

 if you do drop the class， it should only be with the concurrence of all of your team members who are also dropping the class。

Okay， otherwise， it's just not acceptable。Okay， the other thing is we're also asking you to do a peer evaluation of your partners on the first sequence of labs。

 because that's sort of a trial run on working as teams。And in my experience。

 these peer evaluations have almost always been perfectly consistent。

 They allow you to self-evaluate how much did I contribute to the project and to evaluate your team members。

 And I've rarely found a discrepancy。 The people who slacked off said they slacked off。

