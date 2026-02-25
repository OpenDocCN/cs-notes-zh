# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P18：-18-Lecture 19 - Synchronous_Reactive Models.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Okay，1 to stack。So， today， we are going to。Hello。So today we are going to talk about synchronous reactive models。

 Now， synchronous reactive models a little history， so they are coming from the French community。

Of synchron re languages。 So there are a family of languages that have been developed in France some of them are called El signal。

 Luster that are all related to this model computation and the idea was to make a computer language is deterministic so that you know what they do right so we know that the basic problem of computer science is the fact that the machine。

Itself， the holding problem of the touring machine is undecidable。

 So this is the root of all possible evil right because we don't know what the computer program does essentially we can't even say if it terminates or not。

 we have no proof right So the only way is just to run it and say if it goes So not not a good situation。

 So if you look at circuit design and this approach by French community come from the hardware design side。

 So in circuit design in the 70s everybody was designing aynchronous circuit and so the problems where about the fact that you add race conditions。

 So the actual results， the output of what you design depends on the data。So， you cannot say that。

In material what the data is， the function of these hardware computes is always the same。

Is not the case because according to race conditions and so forth， we may have。Different results。

 So this was creating， of course， all kind of nightmare。

 So what people resorted to is they tried all possible inputs。 and off you go。

 remember that in the 70s， the largest circuit that people could realize we're about 16 transistors。

 So a big deal。 know， I can do it in my sleep。 Yeah。

 it works all little way right now when you start increasing the complexity of the circuit。

 this kind of analog ain't going to work。So you have two options。

 right One option is analyzed to death。 So simulation simulation， simulation， simulation， simulation。

But again， the confidence of the result depends on how many simulation vector you try。

And so how well you visited the input space。And so there is no guarantee that if the simulation result tells you that circuit is okay。

 it is really okay。😊，If it says it's broken， it is broken， no problem， but if it says okay。

 it's okay as long as I look at my inputs。That's one。 Or you derive some formal techniques。

 whatever proof， you know， you prove the your stuff， which is not exactly scalable。

So then the alternative is that not to have the problem。So you eliminate the problem by construction。

And so the circuit guys say， how do we eliminate the problem of race conditions？

And the idea came by saying， okay， we put boundaries to the computation by inserting lectureches in the circuit。

And inserting a clock signal that makes me read what is in village。

At a time that I decide to be and that's a clock cycle right what we always say。 so computers。

 for example， when they say is one gigattz computer。

 it means that the clock cycle is one gigtz is what determines the reading of a computation now again and if you look at the computation by putting this latches。

 what happens is that，In between clock ticks， you don't care what is going on。

 The only thing you care is when the clock tick comes And so if you let enough time in the clock period for a circuit to settle。

Then the computation is unique。 So you have a deterministic。U， so you always know it。

What you compute does not depend。On the data。 Okay， so it's a generic result。 So， of course。

 the value depends on the data。 But the fact that if your circuit is correct or not not。

 does not depend on the data。Great， so that was the beginning of a beautiful friendship。

 So we got lots of results。 You know， Intel went on and designed huge micropls and all that based on this principle。

 Now， when the French people said， wait a minute， why all these guys cannot write a damn program that works。

 Soy， why can't we use the same reasoning。😊，So if indeed。

 the asynchronicity of implicit in the Turing modern。

Is what causes all the all the angst about writing correct programs。 Well， we use the concept。

 a similar concept is what we use for in the sense that we are going to。

Assume that all the components of the software program work in lock step so they go together。

 which means that at some point that's the reason why we are called reactive。

 synchronous we just say but reactive means when an input comes。

When you look at all variables in the computer program when that input comes。

And then you decide what to do。So it's like you take a snapshot of the entire system and you decide on that snapshot what to do next。

That is a synchronicity。 Reactivity comes， something happens， and you take an action。And that action。

 though， is to look at the entire space of all the variables of the system。And based on this value。

 you decide where you're going to go。 So you do computation。

 and then you settle and then you wait for another input to come in。And off you go。

 So that is the principle of synchronous reactive models。 Now， when I say to you， everything settles。

 Now， the point is that in circuit， you can say that because we are a physical system。

But in abstraction in computer languages， we know the time is not there。 right。

 So what does it mean when all settles means nothing，Essential， everything happens。Immediately。

 right， there is no time， right， So instead of saying immediately， you say time is not there。

 So whatever computer is what it is。 right， So you don't need to wait until it settles。

Is a concept if it doesn't exist。You compute media right and then you wait for the next input to come。

 Now， these friends of mine。 So we wrote several papers together with this community of French guys。

 I almost wanted to kill them because they did something very bad in what sense。

 because they say that in this model of computation。Computation takes zero time。

 and communication takes zero time。What is wrong with it？Anyone volunteers？And why he was so。Uting。

 at least me。 I don't know how many other people， yes。你你你那ね。Unrealistic always is unrealistic。

 I mean， when we work in the abstraction， you know， also computer languages arenistic。 you know。

 there is no time right。So。Any other person wants to volunteer。And they say zero times。

It implies that there is time， but we just say that time is not part of a model。

 so if we shouldn't say zero time， it should not never save it because you mess up things。😊。

And you come up with the right observation。 And yes。 So say， what the heck，0 times。 It is impossible。

 right， The point is that time is orthotgonal to be model， no time。 So they say。Computation。

Occurs in a separate。Cycle， then communication。 That's all it is。So time does not matter。

 There is no time in the modern。 So if they tell me zero time， I'm going to kill them。

 So I kill them， Okay。Now， I mean， figuratively speaking。 So we are all kind of。

 So we came up with the logical time。 Also this one is kind of upsetting me。 But logical time， okay。

 I can get that going， So at some point on， the Turkey French people say logical time。 Okay。

 we can discuss it because it's not real time。 So no notion of time。 and that's fine。

 So then everything occurs in logical time， which means logical time is only ticks， right。

 It's only discrete jumps that we like， at least I like to call reaction index not time reaction index It's an index。

 because it's a sequence of such computation。 So it's an index in the sequence。

 Okay now this is what sinks are active models are。😊，Now this presentation here。

 since there are a few tricky points that you have to keep in mind， is very much based， I mean。

 this the lecture last year was given by Staavs de Pakistan with associate of the department。

 he decided to do the analysis using circuits right and the logic circuits so we will use that because again。

 logic circuits relate very much to the way in which the French people came about。Okay。

 so we said already composing discrete system There are two major paradigm synchrons of asynchron。

Synchronous means that everything occurs in lockstep and asynchronous。

 everybody' is free to do whatever。 So whenever something becomes available， your computer。Okay。

 so the fundamental characteristic of synchronous systems is this idea of a synchronous round。

 which is a synchronous round is between one reaction index and the next is round of computation right so the rounds are。

 for example， you start the round， you have inputs。

 outputs produced and then you start the next round inputs， outputs are produced next round， inputs。

 outputs and so on oops too much okay now the point that I don't like about this figure is because you have the inputs and outputs in between。

😊，That's not exactly right， because there shouldn't be an in between。 But， you know。

 youve got to have a picture， Right， So so but remember that every time there is a reaction index input and how to occur at that。

Reaction index， nothing in between at that reaction index。 Okay， so anyway。

 this is a picture just to show that in round， something else。

But the important point is that we read the inputs。

 we give the inputs and we read the outputs at the reaction index。Istantaneously， same reaction in。

 Okay， so everything happens altogether。So let's take this synchronous block diagram。 You have ABC。

 Now， I want you to think about。 So suppose that。And around is when you compute all the blocks。

 right， because remember what I say。When we have a reaction index， everything has to compute。Right。

 everything happens。Now。Assume that we are in asynchronous mode， right。So is this？

Diagram always giving you the same answer or not， Or potentially， you may have something different。

Now， if it is an asynchronous thing， then a may have delays inside as synchronous。So the output。

 which is the input to B， may occur before。The output that fits C。

So you will see a particular computation that gives me the output of B first and the output of C later。

Assume that the input is such that， the delays are reverted。Now in get particular case。

 youll see C first and then B。It's a different computation， right。And so this is data dependent。

 it depends on the input， which circuitry is exercising inside the block。Okay。Now。

 assume that we are in this wonderful synchronous world， right？

So the only thing we do is that a produces an output。Which doesn't have time。😡，Istantaneously。

 B andC compute their。Okay。So there is no ambiguity。Given an input， that's what you read。

Be the output of B And C， and of study。So you see that by using this。How to say synchronous model。

 this particular diagram has no ambiguity whatsoever。 So it's deterministic，'s fully deterministic。

And in fact， you can compute when you implement the circuit with the synchronous assumption。

 you can do B and C in parallel， you can do B before C， you can do C before B。

 nothing changes because you read after this is done。Okay，In implementation。

Now when we're talking about you know the model， there is no notion of time so it doesn't matter B parallel doesn't have any sense doesn't make sense how you do it because it is a logical specification of what the system does okay so this is called deterministic concurrence。

Now the thread model that you have seen before， which is what for example。

 computers use to speed up computation， is that they pick up fragments of the code that can run in parallel quote unquote and then they interleave right so it is an asynchronous model。

And so that is the reason why threads are bad right it's very good because speed up the computation。

 but are bad in the sense that complicate the analysis。 so not so very good。

 So it's much better to use a model computation that gives you the exact。😊。

Meaning of a computation itself。So we said before threads incomprehensible behavior。

 so now we want to exploit this model computation， synchronous reactive。

 and it is a computer program by the way。 So we have constructs， we have all kinds of stuff。

 esterl and Lster and signal。And， for example， Esterelle is very much used in designing trains。

And the train you know synchronization， right， you know。

 when the barcom and the rails switches and all the kind of stuff。

 you don't want to mess that up because of the race condition， right， it's not boom。Can still happen。

 but because something breaks， but not because of a model computation。

 So S L is very much using V domain。 loosester and signal are very much using airplane。Aviianni。

And so much so because the looser compiler can be proven， correct。So it's correct by construction。

So of course， you can always mess up the algorithm right and there's nothing but the implementation of the algorithm in that language is always correct。

Aレoya。 that's very good。Now， where can you get into trouble is in performance and performance on one side is the speed because you have to quote unquote when you implement。

 you have to wait for the tick。When you implement。Or because remember with every reaction index。

 I have to look at all the outputs。😊，Of all we blocks。And so some of this。

 there is no need to look at them because they don't do anything， but I don't know。

 And so I have to look at all of it because the modern computations say you have to look at all of it。

 So you get the advantage of being correct， what I'mquote by construction。

 You may be hit on the performance side。 That is the reason why people still use C C plus plus another kind of craft。

 right。Seriously speaking， instead of using these wonderful languages， because you may have。

An impact on performance。 So then Aeu So we still work in trying to figure out how to combine the performance of one model with the beauty of the other model。

 And there are all kinds of things that one can try anyway， so now。

Since we are talking about synchronous systems， then it's natural to in investigate this smaller computation using。

F state machines， because finite state machines in per se are going according to reaction index。

 if they are alone。 Now， we are talking here about concurrent systems。

Which means that my system is a bunch of finite state machine。 not just single one。

And we have to see how we are going to combine them。 So when you combine paths。

There are two or three things that you need to say， one is the behavior of the part。

2 is the communication pattern。 So， for example， the output of his output goes into him and his output was into me and my input goes into him。

 But's a communication pattern is how the input and output variables are set。

 And so that's when you write a diagram with things and errors。

 thats what it means There's a communication pattern。

 And the last thing is that what communication means right because the fact that I put and error between me and him。

 what does it mean。 So these are the the different。

Things that you have to say when you study concurrent model。Now， again。

 because your book is based on the notion of actors， we will use the actor model of finite machine。

 here is kind of tricky。Because we will that in certain way of connecting subsystems。

 we really cannot reason of entire signal， you have to go step by step。

 remember with reactor model as inputs which are waveforms。

 right waveforms meaning sequences of values and the output is all sequences of values as well。

So it's not point by point， right，s the entire boom， right， the entire。 And so that's the after mode。

 So an input is a waveform， and the output is a waveform。Okay。So， in fact。

 the system then is a function that accepts input signal and yields an output sigma。Signal。

 which implies that the S goes from capital x to capital y。

 Well capital x is the space of function over the real。Okay， so remember。

 it's like I inject the entire waveform。 I want to see what is the output wave。O。Now。

 there are different ways in which you compose a finite state machine since everything happens in lockstep in the synchronous reactive model。

The most used way of combining things is called the synchronous parallel composition。

 So parallel composition。Now， your book is says side by side composition right and why do we say side by side composition in the book。

 because parallel， you always think about you know like in service。

 right when you have a resist capacitor in parallel。That's not the case here in parallel。

 means that is the combined behavior is the product of the two behavior。

 So it's nothing to do with the fact that the input and output connect in any particular way。

Is the way in which we build the overall model of a system that is called parallel composition。

 so parallel is nothing to do。With the connection。Just the mechanism， according to which。

We combine two final aid machine。 And so what is it。Well， how do we？

Combine the model in a parallel composition。 So assume that I am a finite state machine。

 and here to verify is another finite state machine。 Okay， now the parallel composition。

 remember everything happens in lockstep says input come in。😊，I take a step。

My friend here takes a step。So the system goes from the pair of initial condition for me and my friend。

To a pair of states， that is my next state and my friend next state。

So given a particular set of inputs， they go to the two machines。

You go to a state in machine 1 and a state in machine 2。

So is that as if you had a single finite state machine where the states are given by all the payers。

Of states。In the transition in the compose machine。

Exist if the corresponding transition in the two machines occur。Okay。

 let's call parallel composition。Okay， that's what it is。 So you go together。You know。

It's like side by side。 It's like you grab your friend and you move in lockstep， right。

 synchronous reactive mouth。Okay。Now， this is independent on the fact that my output can combine with this input。

Remember that in the model of computation。You know， I take a step。 E takes a step。They thought。

That my output are is inputs。Forces him to take a particular path in his trajectory。

But the composition is the same。 So we are going to when something occurs， everything computes boom。

 and then he takes this next step。 I take my next step we combine and the vet transition belongs to the transition of a combined system。

 So that's the way you should think about。😊，So reaction are simultaneous and instantaneous。

 meaning no time， okay， so they happen together right that's what it means together where togetherness means you don't wait to do the computation because you could wait to do the computation right so if I a causality relationship impressed by the arc then I should wait。

But since we are moving in lockstep。Everything happens all。 So， okay。

 so consider a cascade composition like this， right。

 So you have a finite state machine to the left and the finite state machine to the right。😊。

So an input comes， which is a。 right What will be the。Composed modern of these machines。

 So how many states are you going to get。4our。Hes a brother。

Because I have to look at all the possible composition of different states in the different two machines。

 So it's the product of the two machines。Okay， so it is going to be S1 S 3， S1 S4， S2 S 3 and S2 S4。

 So these are the four states of the composition。😊，Now。

 then I want to see when I should take an arc between these composed states。

And what the input and output should be corresponding to the movement。Now。This is the。

This you see S1 is 3， S1 S 4， S 2 S4， S 2 S 3。 So this is the。The compositionposition now。

I comm in withve。Now， if a is present， then I output put B and I stay in S1。Okay。Now。

 if a is not present， I go to S2。And then I come back to S1。Putting out nothing。Okay， now。

What does this say says that if B is present， then I'm outputting C。And that's David。

If I have no input， no presence of B， when I go to S4， and then I come back。

 always come back output putting nothing。Now， the composition as primary input A。

 we call them primary input。 So where the inputs to a combination of the system and as primary output C。

And B is an eternal variable。So， then。If a is present， I stay here。But a ups B， so b present。

 so it up with C。So machine 1 is an S1 and machine 2 is in S3。😊，So S1 is 3， if a is present。

 always up to C stays there。😊，Okay。那。If a is not there， is not present， right， what do I do。

 I go to S2。But if a is not present， it outputs nothing so B is not there。

 so B takes the transition and goes in S4 right。O， so I have to go to S2 S4 bingo under the condition。

 not a because not B is the same。Not a。And then I always come back。

 So I come back to S1 S3 un trueru。So since that we exhausted all the possible combination of input。

 right， so we said， okay， so this is a finite state machine， yes and no。

 because we have these other states that we have to take care of。Now。

 because we have walked through a machine is obvious that what we will come out for the other states is going to be a set of unreachable states because otherwise we would have seen it。

And we have taken all possible combination of the inputs right present absent。So in fact。

 if you want to do say S1 S4， so you have to assume that you are in this composition， S1 and S4。

And so S1 and S4 here in this composition， If you assume that a is present。

 then it goes to S1 and S3 takes this。And it doesn't output anything if a is not present in S1 and S4。

 then it outputs nothing， goes to S2 and S3， but S2 S3 I have to say。

 a transition that is always taken but spits out nothing。

So which means that you cannot go from S1 S3 S2 S4 to S1 S4 S2 S3。

Which then means that these states on the bottom can be thrown out。 They are unreable states。

 so you can throw them up。So in fact， in the compositional machine its true that in the worst case。

 the number of states is a product of the two states。

And if you have three machines to compose is a product of n1 cross N 2， cross n3。

 So it's an exponential growing number of states。The good thing is that often。

The actual finite aid machine is full of states that are not reachable so that the complexity is less than that。

But you have still to look at all the combination and determine if the states are relevant or non relevant。

There are plenty of literature that goes around and says how you should form the composition machine。

😊，Quickly。喂。You can compose implicitly all kind of very nice algorithm。

 because this is a basis when you look at you analyze a large system。

 the basis is to combine the components。😊，And so you want to do that efficient。 Okay。

 so this are reach throw M away。Keep on going。 Ha ha Now this one is a pest of a test of a test。 Now。

 remember， a feedback is a very good thing because with feedback， we can fix things， right。

 control theory is all based on the feedback on the fact that output feedback in the input and then you have a reference signal。

 And then you look at the difference between the reference signal and what comes out and you take action to make what you want。

 You know， this difference is and an important information。😊，Now， on the other hand。

 we also know that feedback can be tricky。W， because they come。

Mmunication is between a machine and itself。And what that signal that goes like this says is that。

Inev reaction。I have to add that the output。A2 has to be equal to an input A2。Now。

 who tells me that that should be the case。诶。So this is a tricky pad。

There are ways in which if you assume certain things on the system， when this is always well defined。

 but there are many composition， which is not well defined。

 meaning that you can never find a way of operating of a system which the output is equivalent to input。

Okay。All right， so。Interestinglyterestly enough。If the block that is fed back like this。

Is a physical system and has ordinary differential equation written in the form x dot equal to f of x。

That thing makes sense， it always exist， and you can construct the feedback signal always。Soalluya。

 but you have to have。A， the equations of the block written as x top equal to S of Z， if you had。

C of F of x dot x and U。You not去饭。It has to be written exactly like what I say。

 X dot equal to F of x and U。 Otherwise， you can claim a priority that things work by the same token。

If indeed the block in there is a finite machine of type mo， this always work。

If it is a machine that is typed merely not necessarily。

 you may or may not have a well defined composition。Now嗯。I know that you already seen yes。

Not because we are talking in the domain of finite state machines。

 So a finite state machine intrinsically， is never time triggered。And then is's a single system。

 right， so。It doesn't make much sense to be time to。 it's the same thing， right。

When you have two things， then you can say it tiny event even。 but if you have a single thing。

Is the same thing， the of mentoring， right。Because it's an active mode。Okay。

 so I put an input something happens then okay now who knows why or at least as an idea。

 why if the finite state machine is a more machine， it works and why if you have a mill machine。

 it may not work。Any wild idea。What is the difference between a more machine and mini machine。

 first of all。那 great。Yes。不然。Only of the state。 Okay， so that is the key difference。 right。

 So now if the output is a function of the state right。

 but what function in which state you are talking about the state。Previous state， right。

 because we are talking iss not after the transition， is that the transition？So。

 which is something that is。Well known， it doesn't change， so the output is well defined。😡，Okay。

Should be now， the problem with a milli machine is that the relationship between the output and the input is instantio。

😊，So there is no delay。And so anything in a feedback loop where there is no delay。

 you may or may not have a solution。 And if you have a solution， you may have more than one。Shocks。

 right， that's bad news。 Okay， so let's analyze this。Oops did too much。 So， okay。

 now interesting point is that no matter how complicated your stuff is， you can always。

Agregate things in such a way， That is a。Function F， together with the feedback loop。Yes。Same thing。

我只找你。デベデアスデティ。It to introduce delays。Remember that， for example， in physics。Yes， in in， of course。

 in continuous time。 Yes， right， D X。No， but we have a reaction index。

 And what it says is that ver index here depends on the state of the previous reaction index。No， no。

 no， no。 when I talk about x dot equal to F of x， I'm talking about continuous systems。

 So there is no finite aid machine， no nothing。 is a dynamical system。And so dynamic system。 I mean。

 we I hope that you have done some control class。 And then the old point is to have the controller。

 right， which takes the output and fits back back into the input。 And then the equation here is F。

 I mean， x dot equal to f of x is a basic thing。 And then you have y equal to you to to introduce thing。

 Now， if you have。X dot equal to f of x。 What happens is that。The way in which X changes。

The derivative is continuous， right， If is lips continuous， which means that I cannot make jumps。

Which means that my x of T is delayed， which means that the output is delayed with respect input。

But it is enough to guarantee me that I don't get into the。Okay， so in fact。

 is funny because the theanoppiccard binddel of theorem of existence and uniqueness of the solution of a differential equation is based on the assumption that F of x is continuous now in that continuity means that the derivative of the trajectory of a solution is continuous。

 which means that no jumps， no jumps， everything is fine。Now， in the discrete domain。

 this translates。Into what is the delay then there is no time in the discrete。

 So I use a more model to introduce the notion previously， previous reaction index。 So that's what。

The translation is。So a mo machine is the same as x dot equal to F of x。we first back to feedback。

Okay， so anyway， no matter how complicated your system is， you can always reduce it。

 but via a series of parallelic composition to be a system with the feedback。On top of it。Now。

 if you don't have feedback， I know， but 99 out of 100。A system of interest do have feedback。

 So you got to deal with this stuff。 right Okay so given the fact that I can always combine my system in many different ways until I get to that thing。

 I have to say， what does it mean to have a system with with that feedback right， What does it mean。

 How do I compute that signal S。That is the results of the feed right so you must have already seen where we are going to go I that okay this is the continuous system x dot and it was talking about before and so in this particular domain you see the theta dot y of T is equal to theta dot y at time 0 plus1 over Iy y integral from 0 to T of the input which is Ty tau in d tau that is where the delay comes in is the integral operation Let's move out thanks。

So this one is equivalent to this node。😊，Tau y is equal to psi of T。

 which is the primary input minus the feedback signal con， which is the input E of a controller K。

And so when I look this， I look at theta dot y here， and I look at theta dot y here。

So there is a variable that occurs on the right and on the left。

Which then means that in order to find the value of that variable， I have to solve that equation。Now。

 again， remember what I said before， if you assume that this function is the derivative function is continuous because of an integral。

 this is always a solution。 Okay， so alleluja， so this feedback is well defined。

In this particular case， not always， but in this particular case it is。

 but this is what the meaning of a feedback is that simply you feed the output signal with first respect of a reference signal and you drive a system okay。

Now， again， we say that easy when state machine is type more is complicated because it's merely for re。

 So a derivative is equivalent to taking one step delay calling， okay。So more versus mill machine。

 so more machines are such wet， the output depends on we stay。

And so the representation of a more machine， it doesn't have to have a transition label by the output。

You can label the states with the output because the output depends on your mistake。Okay。嗯嗯。

And this also tells you that when you land in the state， then they output this computer。

So which means that when you compute the transition， you have to take。Previous reactioning。

Wwhich makes life easy okay so okay that's of thing。

 so a mere more machine circuit view means that you are pulling up the output function out of the state and the state is sitting in the latch and so you read the state out of it and you compute with a resistive circuit。

The呃 after the位 O。And so which means again， that you are taking the results。

Of a previous reaction index， okay。So how to define feedback。

 separating output from state update function is necessary to define feedback easily。

 So I take Yna put it back into X and。 The fact that there is an output that reads out of a ledch is essential in this situation。

Okay， mill machines。 Well， we have to love label they。Transition with the output。

 because now the output depends on the transition， does not depend on the state。嗯。So in fact。

 you can see that in S0， if you take one transition。

 the output let's see which one S2 is always zero。 So this one is0 defined thing because it says equivalent of more machine。

 so even though the idea was to give it as merely this one is a more machine so okay forget it。

 but the idea。Which one S one。Because I， yes， correct。 Because I have， yes， I have 0 or one。 Yes。

 according to Veization， right， if I had。1，0 and0，0。 then it would be a more machine。

So I look at all the transition， except。 thank you for pointing it up。

 So this one is a mill machine because the output is not only function state。

 it's also a function is function。Of。Mini machine， the view is this one。

 You see that the input feeds directly there。Okay， so is a0 delay， quote unquote，0 transition。嗯。

Impact on the output from the input。So feedback from the meeting machine。 again。

 you take Y N and you feed back into X N。 And all of a sudden， you've got something that is。

 So it is a logic dependence。So now we said before， what is the meaning of this？Writing。

 so this one is a symbolic writing， right， It's a box with an Acara。

So the meaning of that is the same thing as we've seen in the continuous system in which we add one variable which appears on the left and appears on the right。

So why， because you say S。Suppose the signal S comes here。This output is F of S。

Now to impose the feedback， you have to say that S is equal to f of S。😊，Okay。

 so if that equation has a solution， then this is well defined。If you have no solution。

 is inconsistent。 if you have multiple solution。It's not determined。

Because it may have different behaviors， given the same situation， the same。

So the meaning is S equal to F of S。 Now， have you seen this before。In any of your classes。

 x equal to F of x。What is it called？咁问几。No。No。Is the fixed point equation x equal to f of x。Now。

 how do did they， well， boy， go。You've not seen this。Oh。

 now is for whoever now remembers this beautiful equation X equal to F of x。😊。

What is the simplest way of computing。The solution of x equal to F of x。Yeah。

 so what you do is that you start from x0。When you put into the F， right， and you grind it。

And it comes out F of x 0。Now you feed it back and say， oops。Is not equal to x 0。 Now。

 what do I do when I take f of x 0， and I put into a machine， and it comes out F of F of x 0。 right。

 And when I say， is f of f of x 0 equal。To x 0。No， so I keep on going， right？I keep on going now。

What do you think will happen。Griing， grinding， grinding， grinding， grinding。

 Do I get to some place or。Sometimes very good。 Sometimes does anyone remember what is the conditional on F to make sure the thing is a sufficient condition。

 It's not necessary。And now， mind you。There are tons of results in mathematics about this dem equation。

 X equal to F O X， is say， well， ge， what is so。You have topology that is saying， well。

 under what condition x equal to f of x as at least a solution。

 And that's called the brewer fixed point。 So if it is a mapping of the unit ball into itself is always as a fixed point。

I'm not asking vet to complicate theology。 forgetgeing something more simpler， right。

 simpler than this， yes。呃に。It has to be monotonic in a certain sense。

 because you can have monotonic increasing， not so very good， right？

Because what happens that x0 put in f of x0 bigger than x0， then you put back in F of F of x0 is big。

 so never come back。Nothing enough。Yeah， it is enough for a brewer for a brewant theory。

 but in general。For the iteration to converge is F must be a contraction mapping。

Which means you put in something small and it comes something and it comes back smaller。

Then at some point， smaller， smaller， and smaller， start buying convergs， right？

Because you keep on cutting down at some point， you get that right。

 So x equal to F of x as a solution。 Everything is a contraction。 thank God。

 in the case of this systems here， we can do instead of looking at condition under which the map is a contraction。

 we can have a constructiveive， similar to x to the what we were saying to the grinding machine。

 right， you put in in x0， you see what happens when you put down F of x 0， call it X1 grind again。

And we do exactly the same thing。 So we are going to operate。

In the same manner to figure out what is going on in this thing。

 So reorganize abstract a or abstract seeing a variables go。

 So we seek any S belonging to S N such that F of S is equal to S。Such as this called a fixed point。

 Okay， and it is the behavior of the system。 So it's what the system does， right， okay。Now。

 data types。 Now， first thing that you want to know is that， well。

 if I'm feeding back y into the system， of course， Y has to be in the space of the input。

Because if I input is apples and you put in oranges， then the F is says， I don't know what to do。

 I only know how to do。 apples。 Don't feed me oranges。 So that is inconsist in the data type。

So data types， think always the data types， oranges， apples， That's what it is， Nothing more。

 nothing less。 So apples to apples， oranges to oranges。So let's what this thing means， okay。

So there is also the concept of a firing function， and the firing function is when you take a step into the。

In。Okay， so we are going to use a sequence of firing function to see if this thing does something or not。

Okay。Well phone feedback。 A wellform feedback is when。It convertverges to one thing。

 right So x equal to y。 So at some point， this I can find the solution。 That's well form。

 I ill form if I can find a single solution， I can find multiple or no solution。😊。

So this the notion of well form or real form。O。Now。

 how to determine whether a system is well formed now cyclic circuit， as I say before。

 this one is a cyclic combination。 You see that the output is fed back into input in this particular case now。

Anyone say that this has a fixed point or not？Any wild idea。So can I X equalequ equal to0 happens。

X to 0， you have an end。 So no matter what the other input is， is always 0。 So bingo， now， okay。

 for x equal to 0， everything is fine。 Now， put in x equal to one。 Okay， So now one end。

 so it's equivalent of the input of a input， which is fed back。 now， but x is equal to one。

 this is an nor。So what is the output， one。 So feedback there。 Okay， the bingo， right found。

 So this is a wellform circuit because no matter if x is equal to 0 to1， we know what happens。Okay。

렐ya。Even though this is bad stuff because there is no alleged， no nothing， So this is a。

AFix point with direct influence。 So they are put on the input at the same reaction index because it is not a finite state machine。

Okay， now this one is cycling combination circuit versus a select。Operator， it says if C。

 when you take F of G of x， else you take G of F of x。 Now， is this wellform or not it is。But it is。

 in fact， this is a selector。 Its a standard circuit that you use。 So not always。

 if you have a feedback its bad news， you can define some interesting compact circuit to do what you want。

Is there an equivalent a secret circuit， this standard question and the answer is yes。

 but is' much bigger okay so sometimes people use these circuits with feedback instantous's feedback to cut down on the size of a circuit。

 but you are running you potentially running into problems or trade officer and I don't know anyone who is able to do except for simple circuit to exploit instantane's feedback to make this circuit smaller okay。

😊，Allright， so now on the right is a classical example in circuit that people say oh bad， right。

 Why is that Because the input is0， The output is one and one is different from0。

 So that circuit bad， no solution is ill for right bad now， but it has a。😊，有。What is that， I mean。

 did any one of you did design， logic design， circuit design。 Do you know what that is。Oscillator。

 but oscillator what， it oscillates only if you put a delay。 So in physical circuit。

 there is always a delay。 And so that think kind of boom boom boom boom and that is an oscillate。

 That's the way in which you indicate an oscillator in your circuit。 But remember。

 it has to be a delay。 And it is a physical implementation of that diagram because that diagram from a logic point of view。

 doesn't make any sense。😊，Okay。Now， go to the right。 Then this one is O， right。

 you can find a fixed point， But unfortunately， you can find two fixed point can be 0 or one。诶。

Both of them are okay。So it's non deterterministic。

 So you don't know what this thing does unless you introduce delay， venos。What about this one？

Any wild idea。So now what is the difference we first before。

 Because this one is a no gate and the input of end gate is negated。 So if it's bad news。

 right It doesn't work。诶。Okay， y because you have a possible oscillation in y。

 So its a variable that goes around。May oscillate。 It doesn't have。

 So the overall circuit doesn't make sense。But if you look at from from the input and output point of view。

 you always can find the solution， But the inside there it's something that goes on， it is not nice。

Reason being is that that variable inside is non observable。😊，Okay。So in fact。

 that's the reason why sometimes people say that you should have observability in your systems because this may cause instability and the circuit to burn up。

So a circle computes what is' supposed to， but inside there is an oscillation。

 and so you have power consumption kind of bed stuff， okay。

So now constructive circuits are things that are guaranteed not to oscillate。

 Constructive means that you can compute the fixed point using the grinding machine。

 That's all there is。 and there is my friend again， one of these guys of the French community。

 Gerard Be that uses these to establish a symmetry between the hardware and software implementation because in software you can write something like this as well。

So。嗯。So although a cycle does not affect the outputpo Z。

 this circuit may be problematic for world what we said can be unstable and all kinds of stuff。😊。

So a constructive circuit is always well formed because we have a machinery that gives us a fixed point。

 so is well formed。😊，Its like F is a contraction mapping。 We know a fixed point exists。

 but we may have a fixed point， even though F is not。A contraction， same thing here。

 We may have a circuit。 It's nonconive， and yet it may have a single solution。

So now what is the grinding machine？The grinding machine is the following。

You start with all the value of your circuit to unknown。 So I don't know if it is a01 okay。

Excepting input that I know， right。 And then I start propagating this signal around。

And see what happens if they unknown。Now， if I have unknown or 1， we know that is 1， the output is1。

If I have unknown。And0 we know that the output is0 no matter what the are known is so doing this simplification。

 either we converge， so all the are known go away or they dont if all the thing go away we say that we reach a fixed point and this circuit is constructive wise constructive because it builds the solution by this iteration process。

😊，Okay。So analyzing circuits。 So using the constructive fixed point。 So take this0 and something。

 the output is always 0 right then 0 and 0 is 0。 So this is O， right。

 my constructive approach will tell me that the fixed point exists。 bingo， fixed point rich。Okay。

 now this one， one and something。Is that a constructive circuit or。No， very good。Because。

 the feedback is always unknown。 You know， I don't know what it is because one is killing everything。

 Okay， now， second one is no， right， you are on the board today。Last one。 Yes， good。Okay， excellent。

Okay。Now， more example。So we initialize with input values and unknown on other nodes。

 and then we keep on going。And so we would see that in this particular case。

 I eliminate all the unknown。 In this particular case， they are in there。 It's not eliminated。

 which implies I don't know what is going on。 And so maybe that I don't like it， right。

 so but it has a fixed point。 It does have a fixed point。But it's not constructive。And in factor。

 there is a part of a ci， bad， bad， bad。Okay， evaluate the lower gate sentence trivia right so 1，11。

 everything works and you are happy now in the particular case where you have on that side the negation。

 then you get that， but the feedback variable is always unknown。Okay。And so that's even why he's bad。

So unknown node remaining constructed semantic rejects this surface say， go away。And you say， well。

 I have a fixed point， but they construct this cement saying， yeah。

 but you have all the problems that you don't see。O。嗯。Now， again。

 the equation f of S equal to S can be also interpreted in classic logic。

 So all is 01 through false and no unknown value。And so there are beds circuits with unique fixed point in classic logic。

 so if you go through the analysis of this string， you say logically the output of end gate is always0。

But if x is equal to0 and the inverters have delay， then this circuit will oscillate。Okay。Now。

 let's apply this principle to state machines。 So this is my final state machine that you see there。

And then I'm putting B equal to a。Now， the question is， what does that finite state machine do。

Alright， so instead S1， we no matter what we have a S of n， which is the output。

 if you like of the system， which is always absent， right， because I I mean S1 A is a。

Present gives me。No presence in the output。B present doesn't do anything because the output is not defined yet。

 so in S1， there is no B to be talk about。 So we get unique S1 equal absent instead state S2 then we always get S and present y。

 because the input is not a， I get B， and if the input is a， I get B again yes。Sa点。Not necessarily。

Yeah， well， you can assume most of it you cant start， right，' no。No issue there。 So anyway。

 so hence S alternates between absent and present。 So B。

 the output is absent when it becomes present， when it becomes absent， when it becomes present。

 and if the fixed point is a waveform with done absent present。

 absent present absent present and iss consistent right because it's not oscillating at the same reaction index。

 remember now we have a finite state machine。 and so very is。Reaction indices that take place。

 It's not static like the circuit that we have seen before。

 So this one is a well definedfin machine is actually is equivalent to a very simple machine with S1 and S2。

 and oscillate。 And then in one case， no B and then B。 And the transition is always taken。

 So it's always true always happens that way。 Okay， so this is a composite machine。

 So we had the finite state machine to begin with。 We had the feedback loop。

 And we encapsulated that feedback loop。 It tried to find the machine that has the same behavior of machine plus the feedback。

 And this is it。And the way in which you compute is exactly the same as we did before。

 you assume something， you propagate， see what happens。You assume the opposite is theda。

 and you see what happens So that the method。To compute what that finite state machine ought to be is always going through analysis of what happens to the various valuess of input。

So this one is actually a yield form example， and in fact， where it doesn't exist any possible。

Value so in state S1， of course， there SN is absent in state S 2。

 there is no fixed point it can't possibly work right。Because why， because not a， A is not present。

 then you output put B， but B is equal to a。 And so how can it be be present and not present at the same time。

 bad news， right， So this one is an inconsistent circle。Yes， I mean， finite machine。Now。

 in this particular case， in S1， both SN absent and SN present are actually okay， fixed points。

 So no matter what happens， you are always okay。Now in state S2。

 we get the unique assign sign equal to present because no matter what the value of a is。

 you always r to B， so B is present there。So since state S1 is reachable through the transition mark with a。

 this composition is ill form again。😊，Because we have a situation where we can have two solutions。

 so that is the order formatness that the solution is non unique。Now， single signal。

 you start with as an unknown， you propagate and you see what happens to a compose finite stage machine until you reach a consistent value。

 So still this idea of grinding。The computation。 So a final state machining， which this。Ittereration。

Works is called a constructive machine because I have a way of building the solution。

This one is a nonconive but is well formed， meaning that if you try to apply the algorithm of grinding you go nowhere。

 but yet if we look at in its entirety， this machine is in fact giving nothing so B is absent for allN so nothing occurs。

But I cannot use that idea of propagating because I don't know what to propagate。

So for this situation where the constructive machine。Procedure doesn't work。

Then the only way to do is to look at all possible combination of inputs and see what happens。

So it's a exhaustive search to build the compose machine。Now。

 sometimes you can get by by using still the idea of a constructiveive， but with a minor variation。

And this minor variation is about the main and must thing。Look at this machine and state S1。

 and when we can immediately determine that this machine may not produce an output。

 right because if a present doesn't do anything， the output is empty。Therefore。

 we can immediately conclude that the output is absent， even though the input is unknown。

 So no matter what the input is is always。Opset。In status 2。

 we can immediately determine that the machine must produce an output because no matter if a is present or absent。

 I always speed out B。 so we can immediately conclude that the output is present。

And so this one with analog mayma， I can then build the confidence that this machine is indeed makes sense。

Okay， now the catstic semantic for multiple signals is what the same。

 So now instead of propagating a signal a single signal， I must propagate a bunch of them。😊。

And so what happens is that when I do a construction， I have to follow several signals。

 so I have to build all you know the valuation of all the signals and so constructive procedure is that you start with all unknown and then you determine you put as many。

 you eliminate as many unknown， you can and it until eventually either you eliminate all unknown or not。

 if you eliminate all unknown the machine is constructed， you found a fixed point。😊。

If not is not constructive， may or may not have a fixed point。Multiple actors， same things。

 If you have free FN， you combine them， and then you apply with very same procedure。

And you can have an arbitrary structure， whatever you want， the machine is always the same。

So now state machine language with constructive semantics。

 will reject all the composition that in any iteration failed to eliminate all their node。

And in fact， the way in which your computer fixed point again， as I repeated before。

 is to do the propagation。 And so the propagation eliminates all the unknowns， happy。It's not。

 not happy。 And， in fact， yesterday。Will speed out I say black， right， So if a compiler。

Will tell you， this feedback composition， I cannot handle。 It doesn't mean that its not correct。

 I cannot handle it。Because S compiler is based on this construction。Some other programs， like。

 for example， Simullink is preventing you from having a particular feedback。

That will cause this problems to occur。 So you eliminate everything so。

 The compiler looks at it and saying， no， I'm not going to do this。 right， So go away。Well。

 Estherl will try to find the fixed point and we'll come back to you and say I found it or not。

 and if not， maybe it exists， but I don't know how to find it so it rejects I think so in conclusion。



![](img/b46b0cada05f598edd2d80c27617e469_1.png)

So our emphasis of synchronous composition is always undeterminate and alyzable。Now。

 we also found out that some kind， some time the analysis is very complicated。

 We have to resort to exhaustive analysis。 But in principle， it is possible。 And so we have a unique。

Answer to the question， is this well formed or not？

Now the point is that automated tools like the compilers of the synchronous reactive languages will apply the techniques that we have seen before because if you want to do it by hand is very tedious。

 of course， and it circuit is lot， you don't want to do that its out of the question。😊。

So synchron system in general， have fewer。Horrible behavior， then a single。

The horrible behavior we've seen before， are do you always do a feedback composition and the feedback in general if it is。

With machines that， you know， the property of is always well defined。

 So more machine is always well defined， no matter what。

But if you have mini machines in the in the structure， then you don't know。

 you have to do all the analysis that we say before。 Okay， and no study。

 So thank you for the attention。To the next lecture。



![](img/b46b0cada05f598edd2d80c27617e469_3.png)