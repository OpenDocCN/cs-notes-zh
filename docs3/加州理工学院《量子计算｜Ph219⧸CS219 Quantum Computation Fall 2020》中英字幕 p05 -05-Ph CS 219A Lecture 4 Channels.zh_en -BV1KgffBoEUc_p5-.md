# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p05 -05-Ph CS 219A Lecture 4 Channels.zh_en -BV1KgffBoEUc_p5-

![](img/12af5b78187b4882f05b81b706ec5dab_0.png)

All right， hello everybody， welcome back again to physics， computer Science。219。

 this is the fourth lecture of the fall term。I'm posting this lecture a little bit behind schedule。

 I hope that hasn't inconvenienced you， but the good news is that。

We're a little bit ahead of the syllabus anyway， and of course， if you ever want to。

Jump ahead if you're eager to see what comes next， at this point， we're following pretty closely。

The lecture notes that are online。 So， of course， you can read ahead if， if you're curious about。

Where we're heading。So let's get going with the fourth lecture。This is actually the third of。

Several lectures in which we are developing the theory of open quantum systems。

You'll recall that we say a system is open。If it can exchange energy and the information with its environment。

 we can think of our system and。Its environment， the rest of the universe as a closed quantum system to which our axioms for closed quantum systems apply。

And we talked about the states of an open system which are described by density operators。

 talked about properties of density operators， and last time we talked about the notion of a generalized measurement where a unitary interaction occurs between our system and its environment followed by some orthogonal measurement in the environment and that as a measurement of the system is something more general than the orthogonal measurement we had previously discussed on the system。

That's what we mean by generalized measurements and we talked about their properties and at the end we talked about the idea of a quantum channel which you could think of as a case where the environment is measured but the result of the measurement is discarded unknown to the agent who's observing the system or if you like you can just think of a unitary transformation。

 acting on system and environment after which we trace out the environment because we're only going to be making measurements on the system after that interaction occurs and the way the system changes under that procedure that's what we call a quantum channel。

And we saw last time。That a quantum channel has a nice representation in terms of an operator sum。

 So remember， we're talking about this type of procedure I'm going to often use。Yi。

In a script font to represent a channel， sometimes I'll use a script end and same thing。

And there's some input density operator。The channel， as I said。

 arises from some kind of unitary interaction acting on the input system and some environment。

 but we don't observe the environment thereafter， and we are interested in how to describe the state of the system after that interaction and in general。

 the output state，After the action of the quantum channel can be expressed in this form。The sum of。

An operator MA summed over its index day， the input density operator times the edge joint of MA。

And that will have the property of mapping density operators to density operators and preserving the trace if a normalization condition is satisfied by these linear operators。

 the MAs， namely the sum over array of MAA joint MA is equal to the identity acting on the system。

So this is more general than the unitary evolution described by our axioms4。Close systems。

 but the unitary map that we talked about before is a special case。

 it's the case in which we just have a single operator in that operator's sum where the index H hit only one value。

 and that means that the matrix M has to be unitary has to obey M and join M。Equals to the identity。

But a general quantum channel does not。Behave as a unitary map unitary maps take pure states。

 take state vectors to state vectors， pure states to pure states。General maps do nod row in can be a。

Pure state。A vector in our Hilbert space or ray in the Hilbert space。

 but it gets mapped to an output density operator， which is not pure， which is a density operator。

 which can be viewed as representing an ensemble of possible pure state inputs， outputs rather。

 as we discuss。Now this quantum channel。Has several fundamental properties that we should note。

 The important thing is that it maps density operators to density operators。

 If row in is a density operator， then so is row out。 So that means in particular。

It's a linear map I should emphasize of density operators to density operators。

 and if the input is hermissions， so is the output if the input is。

Non negative has no negative eigenvalue， that's true also of the output。

And if the input has trace one， if it's a normalized density operator。

 then that's true of the output as well。The word channel comes from the conventions of communication theory。

 we can think of the channel as describing a quantum state which we want to send from one place to another。

嗯。Through some noisy procedure， maybe we're sending photons through an optical fiber or something like that。

 and when they arrive， the quantum states that we send through the channel may have been damaged in some way。

 and that damage is described by this operation or linear map that takes the input to the output。

Not necessarily unitary。Now， a property that quantum channels evidently have is that we can compose them。

Because if you think of a quantum channel as representing what happens when a quantum state is sent from one place to another。

 and incidentally we might send it through time rather than through space。

 so we might think of it as representing the evolution of a quantum state。

Row in could be the quantum state at some initial time。And then for a while， that state is exposed。

To interactions with the environment。Which we can't control very well because we don't control the environment。

And then after some time the state has been changed and it becomes the output state。

 so that generalizes the idea that evolution of the waste of quantum states change with time if they're not measured for closed systems as described by unitary maps。

 the more general situation is that it's described by one of these quantum channels。

And if I think of one quantum channel as representing the way a quantum state changes between Monday and Tuesday and another quantum channel as describing what happens to the quantum state between Tuesday and Wednesday。

 then I can apply those to quantum channels in succession to get another quantum channel。

 which describes how the state changed between Monday and Wednesday。

So that's what I'm trying to say here in this equation。We have a quantum channel。

 the first one describing evolution from Monday to Tuesday， which I call the sub one。

 and it has some set of。Operation elements， sometimes we call these cross operators。Um。

Thatll define the channel。 And then there's a second channel describing how the state changes between Tuesday and Wednesday。

 That's denot D2。 and it has a set of cross operators appearing in this operator sum。

 which I called andm。And then the composition of the two has cross operators。

 which are just given by the product of a cross operator for the first channel times the cross operator for the second。

That's also a channel， it also takes density operators to density operators and preserves the trace because the individual ones do。

In fact， the cross operators now being MUMA for all possible values of UA。

 our normalization condition becomes。That if we sum over both a and mu。

 the adjot of M mu and A times n mu and a， that is the identity。 And well。

 we can see that by doing the sum over mu first， which gives us the identity because E2 is trace preserving。

 and then we can sum over a and we get the identity because E1 is trace preserving as well。

So now we can ask a question。Suppose。A quantum state changes， as described by some quantum channel。

 Is there some other quantum channel which can change it back to what it was in the first place。

Now in the case of the unitary map， we know the answer is yes。

Unary map U takes our input density operator to U row U add joint。

 and we can just use the inverse of U to undo what the channel did。

 The channel has an inverse when it's unitary， but what if it's not。If we have a non unitary channel。

 is it possible to find a another channel which maps the output of the first channel back to its input for any possible input？

That's the question。So let's investigate that。So if it's true。That there does exist a channel。

 which is the inverse of E1， that would mean we call that inverse E2。

 that if I let E1 act followed by E2， acting on any pure state input like this projection onto psi that I'm indicating。

Then the output of E2 e1 acting on side has to be the input。

Projection on thes So if I say the cross operators of be1 are the set of operators I may。

And the cross operators B2 are the set of operators and mu。

 then we know the composite channel has the cross operators and mu MA。And so。The operator。

Some representation of that composite channel。 I can write this way。

 summing overall cross operators and Mu MA of the。Of the composite channel。

And we want to get side back， and we wanted that to be true for any side。

So each one of these terms in the operator sum， each one of them is a positive operator。

And that means that every term in the sum better be proportional to the projection on decide side because if there's any component。

Whi is orthogonal to that projection on Deai， there aren't any other terms that are going to cancel that because all the terms are positive。

So if every term in the sum is proportional tos， it looks like my。I don't know， think I can move oh。

 look， I can move that， very cool。嗯。That means that each one of these operators acting on any state。

Has to preserve the stay， that means it's a multiple of the identity which could depend on the value of mu and A。

 and's that's what I've written here。Okay， so。What can we infer from that Well remember we have a completeness relation the sum of N a jointint M mu for the completeness relation。

 the sum of MA a jointt M in both cases the sum gives the identity for the two channels so let's leverage that let's consider for any pair of cross operators of the first channel MA and MB let's look at MB a joint MA nobody can prevent me from inserting this resolution of the identity between MB a joint and。

AA because。The cross operators of E2 obey our completeness relation。And so now we have a sum。

Of the adjoint of Nm M。occurringcurring。Here as what and then the product and muma here now let's come back to what we had over here and muma that's just lambda mua times the identity。

 take the complex or take the Hermeian conjugate of this equation and replace a by B it says that MB a jointt and mu a jointt is complex conjugate of lambda mu B times the identity so I made that substitution here。

And the important thing is that for any pair of indices， A and B。

 labeling the cross operators of the first channel。嗯。

Every term in the sum is proportional to the identity， so the sum is proportional to the identity。

 I just called the coefficient in the identity beta B。

 it could depend on which cross operators MB B and MA I'm talking about。

 but the important thing is is proportional to the identity。Now， quantum channels in general can map。

An input system to a different output system。That wouldn't be the case if we were considering the evolution and time for a particular system。

 but we might want to， when we're sending quantum information to send from an initial system to a final system where the two systems are different and in fact they might even have a different dimension。

So now I'm going to suppose that that's not the case。

 I don't have to worry about the dimensions being different。

 so the output state and the input state both live in a Hilbert space with the same dimension。

That means I can think of my cross operators as being。

Square matrices with the same number of rows and columns。

Remember in this course we're always considering finite dimensional Hilbert spaces。They're matrices。

 which are finite dimensional。And I can remember that every matrix has a polar decomposition。

 it's always possible to take any one of the MAs， for example。

 and write it as a unitary acting from the left times the square root of MA adjut MA。

That's a positive operator and MA joint MAA so I can take its positive square root。

And now I come back over here， and when I said a equals B。MA ajo MA gives me beta。

AA times the identity， So when I take that square root that just gives me a number。

 the square root of beta A， which actually is a positive number if you look over here when a is equal to B。

 this quantity is。Is a positive， real number。And then I still have this unitary。

 which I pulled out when I did the when I did the polar decomposition， Okay。

 but now you see we're saying that MA is。Proportal to a unitary operator ats some number times a unitary operator。

All right， so now let's come back to what we had here that M a joint MA is equal to a number times the identity。

But now let's substitute in what we just learned M A and M are。

 They're both proportional to unitaries， U A and U B adjus。 So I get some。A number。

Times UBA joined UA， but remember， we showed up here that MBA Jo MA is proportional to the identity。

So that means the unitary， which appears in MA and B。

 they're both unitaries up to some multiplicative constant。

 they're actually the same unitary up to some multiplicative constant。

Because I don't have to be afraid to to divide by。The square root of beta AA beta BB。

 those are both non zero if MA and M are operators which are not equal to zero appearing in our operator sum representation。

So I can just multiply。Bye。The unitary used to be on the left and the right。

 put that unitary UB over here on on the right of this equation。

 and I can see that UA is proportional to UB。Okay， so what we've found is that if we can invert。

Our channel E1 with another channel E2。Then the channel  E1 has to have a very special structure。

 All of its cross operators are not only unitary up to a multiplicative content。

 they're all the same unitary。 They're all proportional to the same unitary。

 And so when you sum everything up。In the operator summary representation。

 while all the terms are the same up to a multiplicative constant。

 it means we're talking about a unitary map。The conclusion is that if I want to invert a quantum channel with a quantum channel that is possible only if the channel I'm trying to invert is unitary。

 It's unitary。 It's easy。 We apply the inverse of the unitary。 If it's not unitary， we can't do it。

 We can't for an arbitrary input undo with the channel did。So remember the way the channel arises。

 at least the way we've described it is。That。We had a unitary map acting on the whole universe consisting of the system and the environment。

 so why can't we undo it if it's a unitary it's because we don't have access to that environment。

We only can act on the system or think about it this way， you can think about each。

Application of the channel is having its own environment。So we had some environment。

 a unitary act on the system and the environment we traced out the environment now we've got some density operator now we won't undo that。

 we can append another environment， apply some unitary and trace out that second environment。

 but the point is that unless the original map is unitary that's not going to suffice to undo what the map did。

It's because we don't have access to the environment of that first operation。

 the application of the channel E1， that we can't undo it。So this is the story of decocoherence。

 this is how decocoherence of quantum systems works。

There are interactions between the system and the environment that we cant control。

 and we can't undo them because we can't access the environment。And。

It's sad but true the information。That's encoded in the quantum system can decay。 You can get lost。呃。

Flows into the environment where we can't get it back again。Now。

 I want to talk about a concept which is a little more general than a channel。

 I'm going to call it a quantum operation。That's one of the names that people use for it and the idea now is we want to look at this scenario that we've been discussing where we have a system in an environment。

And we talked about two different extremes。And。There's something in between that we haven't talked about yet。

 so what do I mean by two different extremes well there's a system in the environment。

Or I think the way I talked about it last time， as I said， there's a bipartid system。

One is under Alice's control and one is under Bob's control， so let me use that language again。

And there's some unitary， which is applied to the joint system AB， and then we discard B。

 that's the way I described a channel。Um， and Bob might have done something to his staff for the system。

 but it doesn't matter what he did， that's not going to affect。

State of system A after the joint operation on A and B has occurred。

So that's the case of a channel where。The Uniary X jointly on A and B， and then we discard B。

And don't retain any information about me。But last time we talked about the idea of a generalized measurement where。

A and B were originally uncorrelated， just in a product state。

 some unitary was applied to AB acting jointly on A and B。

 and then Bob did an orthogonal measurement。On system B。And he reported to Alice。

 the outcome of his measurement。Okay。And Alice used that information she got from Bob to update her description of her system。

And so we talked about generalized measurements in that scenario and about what the post measurement state looks like。

How Alice describes her state after she hears from Bob the outcome of the measurement。

So that's one extreme， Alice hears everything about what Bob measured。嗯。

The other extreme is Alice doesn't hear anything from Bob。

So you can imagine Bob did his orthogonal measurement。

 I don't really care whether he really did or not， but he didn't tell Alices anything about the outcome。

And that's the case of a quantum channel。But another possibility is that Bob performs a measurement and he tells Alice only partial information about the outcome of the measurement and Alice uses that information to update her state so that's the more general possibility。

 which I'm going to call a quantum operation。So we can think about it this way。

That we have Bob does his orthogonal measurement， the different outcomes correspond to cross operators。

 which I'm going to say carry two indices， A and mu。

And A is the part of the outcome that Bob is going to report to Alice。

And mu is the part that Bob is going to keep secret from Alice， so Alice is going to know a。

 but she's not going to know mu after Bob measures and then she has to describe her state after that measurement。

So first of all， we can assign probabilities to the different outcomes that Alice hears about from Bob。

 those outcomes labeled by。A alone。Now， if。We really had complete information about the measurement outcome。

Then we could assign a probability to a value for both a and mu like we did in our previous discussion of generalized measurement。

 and that probability would just be the trace of m sub a mu row m sub a mu a join if row was the input state on on which that。

On with that which that measurement was performed so remember this is the way we described a POVM I guess the way I said it last time in at least I sometimes said it this way is you can think of the of a resolution of the identity by the operator's MA mu ajo MA mu。

Those them up to the identity， they satisfy the completeness relation that I wrote down here that ensures that the probabilities for all the outcomes labeled by A and U。

We'll sum up to one。But。If we're only interested in the probability of a。

Then we consider summing over the possible values of mu。

Because Alice is only going to learn about A she's not going to know about mu。

 so that means we for each a， some over mu to get the probability of that particular outcome A。

And how did the quantum state in that change in that case？Well。

 we can use our operator some representation， but now Alice knows the value of a。

 she doesn't know the value of mu， so we sum over mu but we keep a fixed。

 So we have a different map of the input density operator to the output density operator for each one of the possible outcomes。

 that was like in the case of our generalized measurements。

 we had a post measurement state that depended on the outcome。 but here the post measurement state。

In the way Alice describes her state after the measurement depends on A， but it doesn't depend on mu。

 which we have to sum over because Alice doesn't know mu。And as usual， when we write this。

Representation for the measurement operators corresponding to the particular outcome that Alice has。

The state doesn't have norm one anymore。Because in fact， it's or doesn't have trace one。

Because its trace really corresponds to the probability of this particular outcome occurring。

So after the measurement， if we want to have a normalized state。

 we have to take this post measurement operator。What results from？

doing the measurement acting on the input density operator row。

 and then we have to divide by the probability of that particular outcome a。

 which is just the trace so to get the post measurements saved of course we wanted to be sure to have trace one so we divide by its trace。

To get a normalized stay。And that's the way we can describe a quantum operation。

It has an operator some representation， but now if we're summing over the muse， but not the A's。

 we don't have that the sum of M join time is equal to the identity。

 it's some operator whose eigenvalues are non negative。But can be strictly less than one， okay？And。

The nice thing is that if we don't do the division by the trace to get the normalization。

 this can be described by just a linear map。It becomes nonlinear because we have to renormalize the state and the nonlinearities use can be kind of nasty to deal with。

 so sometimes if we want to consider a sequence of operations like a sequence of measurements that are occurring。

On Alice's system。We we don't do the。Reormalization of the state。

 Every time another measurement is made， we just let the trace of the state of this sub normalizedmalized state represent the probability that we see a particular sequence of measurement outcome。

 So in other words。If I have some initial state， row。And then I perform a series of operations。

The first one， we tell Alice our Bob's outcome was A1。

 the second time it was A2 and so on altogether and measurements。In general。

 each one of these maps is going to reduce the trace。And that reduction of the trace。

Corresponds to the property that the outcome of the measurement was something that occurred with probability less than one。

 and only after the sequence of measurements is done and now we would like to update our description of the state to get normalizedizations right。

 we can divide by the trace of this composition of operations to make sure we have a normalized state at the end。

So that can be convenient since we only have to deal with linear maps up until the very end。

Now linearity is kind of built into our whole description of quantum mechanics。

 and we've seen correspondingly that aside from that renormalization。

Operations are described as linear maps， channels are described as linear maps。

 and we're entitled to ask from kind of a fundamental perspective。

 what's so special about linearity in quantum mechanics？After all， in classical mechanics。

 we're very accustomed to systems having dynamics， which is non nonlinear。 but in quantum mechanics。

 the Schchrodinger equation is linear。 Quaum channels are linear。

 These more general quantum operations are also linear aside from the。Final state being subormalized。

What's the big deal about linearity？Well， the reason linearity is important is because we have a probability interpretation for quantum states and in particular we would not have a consistent way。

Of interpreting a density operator as an ensemble of pure states。

 were it not for the linearity of these maps of quantum operations and quantum channels？

So let's see what I mean by that。Let's say we have some initial mixed density operator。

And we can always imagine that that density operator is prepared by sampling from some source of randomness。

 sampling from a probability distribution， getting the outcome I or getting the sample I。

 that occurs with probability PI， and when our sampling gives I。

 then the state that we prepare is ROI。And so the density operator that describes that ensemble is just this convex combination of quantum states。

 the different states in the ensemble being weighted by the appropriate。Probabilities。

So first of all， let's look at what happens from the point of view of。

The ensemble sort of state by state and the ensemble。

In the case where the state that we prepared was RoI。

 one of the possible states we might have prepared that one occurring with probability PI。

Now we perform a measurement。And it has some particular outcome。

Outcome A corresponding to some particular operation applied on that state growi。

And the probability that we get the outcome A。When the prepared state was rows sub I。

 I'll consider it to be this conditional probability。

 the probability that the outcome is a when the input state was I。Now。

 when we start out with an ensemble and we know we have a sample from the ensemble。

 but we don't necessarily know。Which state was prepared， all we really know is the density operator。

Then when we make a measurement。We gain some information which requires that we adjust。

The probabilities we assign to the different outcomes because when I get outcome a outcome a may have occurred with high higher likelihood for the。

State row1 than for the state row two。 And so when I get outcome A now it's more likely than it was initially。

That the preparation was row one rather than row two。And so let me call my revised。

Estimate of the probability that the prepared state was actually row I， this conditional probability。

 the probability that the prepared state was I when the measurement outcome was observed to be a。

Okay， so now what's the right way for Alice to describe？

State that she has after she receives the information。That the。Measurement outcome was a。Well。

 from the ensemble point of view。When the outcome was a and the input was Ro I， then the。

Probability of getting that outcome， that's what Inot by P of a given I。

 I have to divide by that probability to get a normalized post measurement state in the case where the input was I。

And the measurement outcome was a。And then I have to take the convex combination of such post measurement states weighted by the A posterii probability that the input state really was I。

 given that the measurement outcome was observed to be a。So from that point of view。The measurement。

The measurement of post measurement state can be written the way I've written here， some over I。

 probability of I given A， the result of the operation E sub A applied to initial state row I divided by the appropriate on normalization。

Okay。Now。Let's remember base rule。It says there are two ways of writing the joint probability of the preparation was I and the measurement outcome was a。

We can either take the probability that the measurement outcome was a and multiply that by the conditional probability that the preparation was I。

 if the outcome was a or we can say that the。Joint probability is the probability that the preparation was ros subbi times the probability that we get the measurement outcome a。

 given that the initial state was actually ros subi。So what Bay's rule gives us。

Is an expression for the ratio？Of the probability of outcome I given an A。

Dived by the probability of sorry， the probability that the preparation was I。

 given that the outcome was a， divided by the probability that the measurement outcome is a。

Given that the preparation was I and it's just the ratio of the a priori probability that the prepared state was RoI。

 namely PI divided by the probability P sub a of getting measurement outcome A。

When I don't know what state was actually prepared and have to average over them all。ok。So。

If I look at this expression here for the post measurement state。

 what we actually have in our sum over I is the ratio of the probability of preparation I given outcome a divided by the probability of outcome a。

 given a preparation I， which is just the。Probability of preparation。 I divided by。嗯。

The probability of outcome A。So I can rewrite this expression using base rule。As the。Well。

 I can write。So hold on a second。 I'm sorry， Im having a。

I'm having a technical issue here for a moment。

![](img/12af5b78187b4882f05b81b706ec5dab_2.png)

So oh， what happened， I don't see my my little face anymore。Wo， what did I do around this time？下。我咪有。

Pas it again。Well， okay， I don't know why I don't see my little face up there anymore。

 and I love looking at myself so it's kind of sad but。

I guess we'll just we'll just forge ahead maybe。Even that will get repaired as we go on well I was getting a little distracted。

 so I think my explanation was。Unusually poor even by my own my own standards。

 so let me see if I can pick this up again， so as we discussed we can use book base rule。

And that allows us to simplify the expression for the post measurement state when we express it in terms of you know a convex combination。

Of the results of applying the operation for all the possible states in the ensemble。But。You know。

 if we want to describe what happens to Alice's state， you know， Alice doesn't know the。

APart sample that we chose the only thing that Alice can know about is the density operator。

 which is the convex combination of the states in our ensemble。

 so we should be able to describe the output state in a second way which is the result of the operation applied to the input density operator the sum of P Roi and then we can normalize that by dividing it of the probability of getting the particular outcome a associated with this operation and when we use this base rural identity we can see that the two ways of computing the postmeasure state are related in this way from the point of view here where we look at the states in the ensemble one by one and weight them by the right postmeasure a posteriory probabilities we get the sum of PiI times the result of。

Plying our operation corresponding to measurement outcome a to input state Ro I。

 and the other is the result of the operation applied， oh， I guess I left out the PIs。Of course。

 this should have been the sum of。Of P I Roi， the initial density operator。

But the idea was to see that this requires that the map be linear。That the operation。

Applied to the sum of P Ro I is the same as the sum of P times the operation applied。To row eye。

And so in order to have a consistent way of interpreting a convex combination of density operators as the result of sampling from an ensemble。

 operations have to be linear。Now。I had mentioned last time， I think。

That a quantum channel is a map from density operators to density operators which preserves the positivity of density operators。

 but in fact， there's a stronger requirement than that。

A quantum channel has the property of being completely positive。

So what does it mean to be completely positive？A map of operators to operators。

 I'll call it positive， if it maps non negative operators to non negative operators。

 that sounds like it ought to be enough。For describing possible maps of density operators density operators。

But it's not enough in general， because we might want to consider a map which acts on part of a larger system。

Instead of on the whole system， so in other words， if I want to consider a physical map that describes what can happen to a quantum system a。

Then I ought to be able to extend the system to consider a to be part of a larger system， A B。

 and when our quantum map。Is applied to system A， it better take density operators of AB。

Two density operators of AB， okay？That's what I mean by complete positivity。

 it's not just that the map takes non negative operators of A to non negative operators of。

A or a prime， if we're talking about a map that takes a to some other system， a prime。

 there's a stronger requirement that it takes density operators to density operators。

 even if we extend the system， and that's the property of complete positivity。And the important fact。

Is that there are operators which are positive， but are not completely positive。

So an example of that is。Transposition， the transpose operator。

 you can think about it as acting this way， well we normally think about it as a matrix which interchanges the row and column indices that is we think of transposition as acting on matrices in that way。

But I can also describe it this way， that if I can consider a basis for operators。Labeled by I and J。

 where I is a k and J is a bra and what transposition does is it interchanges I and J。

 it takes Ke I bra J to catch a bra I。And from the point of view of a matrix in the basis labeled by the index I or J。

 that's the same as saying that it takes the density operator expressed in that basis to the transpose of the density operator。

Okay。Now transposition is surely positive。That is， if Ro is a non negative operator。

 so will be its transposed， let's just check that。So let's consider some arbitrary state vector expressed in terms of some basis。

 so the orthoormal basis states are labeled by I， we can write this state as the sum of P psii basis element I。

And I'm going to use the notation size star to be the state vector that I get by taking the complex conjugate。

Of all the coefficients expressed in terms of that basis。

 so what I mean by s star actually can depend on the basis that we're talking about on how I chose those basis vectors but let's not worry about it we'll just talk about a fixed basis in the present discussion so I know what it means。

嗯。When I saysi star， I just take the complex conjuggates of all the coefficients in that fixed basis that we're considering。

So what I want to check is that if I consider any state factor。

The expectation value of row transpose is a non negative operator if that's true for row。

 if row is also non negative， or I should say the expectation value is a non negative number。

 which means row transpose is a non negative operator。

So if I write out in terms of components in our。Preferred basis。What that expectation value is。

 it's a sum over the indices I and J of Psi J star。

 the J I matrix elemental pro transpose times P psi I。Because here I've just taken the inner product。

Ofsi with road transpose acting onsi and it complex conjugation here。

Because of the complex conjugate and the inner product in their complex alilbert space。Now。

 I know that。The transpoer row。嗯。Labeled by matrix element， JI。

 that's the same thing as the IJ element of the matrix row。

So I just tooksi and put it over on the left inside J star and put it over on the right and replaced row transpose JI by row I J here。

And so this is also。An expectation value in a state vector of an operator。

 but now the operator is row， and instead of having the state sizeia have the state size star with the components complex conjugated。

But if row is non negative， of course， its expectation value in the state size star has to be nonne just as for the statesi。

 so what we conclude is that if row is non-negative then row transpose is also nonneative since the transpose takes row to row transpose。

 sorry， well that's what it does transpose takes row to row transpose。

 so we can think of the transpose as a map of operators to operators which is positive。

 meaning it takes non-neative operators to non-neative operators。Okay。

 but now I want to consider an extension of our system and see how transpose x in that case。

 So what i'll consider is extending a by appending another system B。

 which has the same dimension as a。And I'll consider a entangled state of A and B， in fact。

 a maximally entangled state。Remember， maximally entangled means that the density operator of a。

Or a B。Is proportional to the identity。It's a maxly mixed state。

And because I didn't want to be annoyed by factors of1 over the square root of d。

 I haven't normalized the state properly， I've chosen it to have a norm squared of D。That's okay。

 I'm just doing that for convenience， so I don't have to clutter up my equations with factors one over square root of D。

 which might be distracting。 and another way of writing this entangled say is just two notations for the same thing is I can write it as a sum of。

Basis state I for a tensored with basis state I for B， but as a shorthand。

 I just write that as I comma I。But now I want to consider the so called partial transpose of this state。

 I'm going to have the transpose Act only on the first system A and not on the second system B。

So I'm considering in other words， transpose on a tensored with identity on B。

 acting on this a pure state， unconventionally normalized pure state。So what does it do？Well。

 let's expand out what this projection onto Phi Tilde is。Um。It's。Kt is a sum over I of I tensor I。

 here's the one eye， here's the other eye， and then the bra。

 I can write as the sum over J broad J for a， broad J for B。

 but then if I reorganize that in terms of a tensor product of an operator on a。

 and an operator on B， it's the sum IJ。That is cat I Bro Jay acting on a。Ked I brought J acting on B。

 Now we let the transpose Act。 Okay， so what the transpo does is it takes。

Cat I broad J to catch A bra I。And so the result of applying this partial transpose。

 the transpose on A and the identity on B。Is going to be this state that's the sum of。

Kt J I bra IJ So if you think about what that does， it's a so called swap operator。

 it takes the product of the tensor product of basis elements I tensor J to the tensor product of basis elements J Tensor I。

So why do I call that swap operator because if I have a tensor product of two pure states？

One for A and one for B， let's look at what this operator does。

So let's say this swap acts on pure state psi for a tensored with pure state phi for B。

These are state vectors， I expand them out in terms of our basis。

What's multiplying basis element icon comma J is Psii pi J。Then what does the swap do？It。

Take the it doesn't change the coefficients， but I just wrote the。

A different order put the Phi on the left and thesi on the right here。

 but it does change the basis element I J to basis element J I。

And so what I have now is the tensor product of Phi for system A with psi for system B。

 so it swapped the two states， I started out with Psiine A and phi and B and what the swap did is it returned phi for a and psi for B。

Now the point about the swap operator is that it is not a positive operator。Well。

 you can see that if you apply swap twice， if you square the swap。If you compose swap with swap。

 that's the identity， it doesn't do anything the first time it swaps。Systems A and B。

 the second time it swaps them again， and that's the same thing is not swapping all at all。

 So the fact that it squares the identity means that its eigenvalues。Have to be plus one and -1。

 but it's not the identity operator。 So we don't have all the eigenvalues equal to plus1。

 It also has -1 eigenvalues， Hence it's a non negative operator。In fact。

What it means for swap to have a plus one eigenvalue is that it means the state of8 B is symmetric。

 It means that if we interchange systems A and B， that doesn't。Change the state。

 whereas if it's anti symmetric， when we interchange A and B， we pick up a minus sign。

And there are states which are anti symmetric， just to be explicit， I suppose。

 for two qubits again I'm。Not normalizing these states。

 I could have divided by one over square root of two but。

I just wanted to explain how swap accesss is a linear operator so I didn't bother with the normalization。

But01 minus10。And is basis state0 for qubit A and one for qubit B， minus1 for qubit A 0 for qubit B。

That's an antisymmetric state。 If we apply the swap operator， it maps 01 to 10 and 10 to 01。

 and that changes the overall sign。So swap is indeed not a positive map。From operators to operators。

 sorry， I didn't say that right。 swap as an operator is not a non negative operator。

The transpose is positive， it took a。Density operator， in fact， a pure state。

 an entangled state of A And B， a to an operator， which is not a density operator。

 which has negative eigenvalues。So that's an example， the transposition is an example of an operator。

 which， although it is positive， it is not completely positive。Now， in fact。ho， one moment。In fact。

 if。I want to have a way of describing。What can physically happen？

When a density operator evolves to another density operator could you say it again please or is mapped to another density operator。

 what do I want， I want something that's completely positive okay。

 because there's no reason why it shouldn't be possible to extend the system。

 so the physically realizable operations that we can perform on quantum states。

A completely positive linear maps of density operators to density operators。

And that raises the question of the operations that we defined。Which we arrived at by considering。

Taking system A， extending it to AB， performing some unitary on AB。

 then possibly performing some measurement on B and partially reporting the results。To Alice。

 are those the most general types of operations which have that property of being completely positive maps of density operators to density operators？

And in fact， the answer is yes， we haven't missed anything by constructing our quantum operations。

 operator I serious trying to tell me about density operators。 I got a next time I do this。

 I'm going to have to put my phone in another room。 No she won't be listening。

 She's telling us all about density operators。 So maybe we should just let her give this lecture。

 but。Okay。So。That means that whenever we consider a completely positive math。In fact。

 from some system A to some output system A prime， it can always be realized by extending to a larger system。

 applying a unitary and then measuring the complement of A， if we extend from A to AB。

 apply a unitary A B， measure B， perhaps report some of the information about the outcome。

 and that's the most general thing that's allowed to happen to a density operator or the most general thing that's physically。

Aloud。Now， if we don't report any information about that measurement outcome of if we don't。

 as I put it here， postselect on some particular outcome and then renormalize the state as we would in a general operation。

 that's the case of a quantum channel， which preserves the trace。

 so that's the case where our operator， some representation obeys that completeness in relation。

 some of M at joint M is equal to the identity， and the more general operations in which some information is retained about a measurement outcome。

Will not increase the trace， but it can decrease it。

 And then we renmalize the state in order to get a properly normalized post measurement density operator。

 So now I have to explain to you how we prove this statement that I'm making。That。

The most general map of density operators to density operators was just completely positive。

Has an operator some representation can be represented as a unitary on an extended system。

Followed by an orthogonal measurement on the extension。

And to do that we're going to introduce a concept which is interesting for other reasons as well。

 it's often useful in quantum information theory， it's a notion called quantum channel state duality。

Channel state duality， sometimes people use the name Choi， Yamelowski， isomorphism。

Those are two names for the same things。Johoy Yamelowski is。

Challenging to pronounce and channel state duality is quite descriptive。Of the idea。

 so I'll usually just call it channel state duality。And the point is that。

If I want to describe a quantum channel or even more generally an operation， there's a mapping。Of。

The quantum operations to states and from states to operations。

 so we can use either the language of operations or the language of states to describe the same phenomenon so let's see how that works。

So I'd like to understand。How to describe the action of some operation here， I've called it。E。

 it's going to map system A to system a prime。And I'm changing my notation here。

 I'm instead of talking about the system by which we extended B， I'm going to call it R now。

 R stands for reference， people often speak of the reference system。

You don't have to think of it as a real system， it can be something that we introduced just for convenience in order to have a handy description of what's going on。

But what I want to do is take my system A on which this operation or channel E is going to act。

Introduce another system which has the same dimension as system A。

 which I'm now calling R and now consider a input state。

Which is just this maximally entangled state of RNA。 again， I'm not bothering to normalize it。

 so I don't have to write annoying factors of one over the squared of D here。

 So it's just the sum of basis state I for reference system tensored with basis state I for our system A。

 and now we're going to let our channel or operation act on a it maps it in general to some other system a prime。

But we're not going to have any channel or operation acting on R。

 though it's just acted on by the identity， so I'm considering the identity on R tensored with our channel mapping A to a prime。

And now let's suppose that we know this channel is completely positive， okay。

 so that means that acting on any input state。This extended map is going to give me a density operator。

 okay？And so I'm going to write that output state， the result of applying identity tensored with E on this entangled state of RA。

 I'm going to write it this way， and now I'm introduce another notational simplification。

 which I hope won't cause confusion， we know that any density operator has a representation。

 in fact can be represented in multiple ways in general。As an ensemble of pure states。

And here I'm using the same unconventional normalization， first of all， that I did for the input。But。

I'm going to call the pure states that occur in our description of the output density operator。

The sigh。Tilda states and they're labeled by some index a。

 but you probably expected to see those weighted by some probability when we have an ensemble representation of a density operator。

 we have an ensemble of pure states which each one assigned its corresponding probability。

 but because I didn't want to keep writing those。Probabilities。

 I absorb them into the normalization of the state。

 so in other words apart from the unconventional normalization that I used to begin with。

The probability of the state ciilda suby occurring in this ensemble has actually been absorbed into its normalization。

So the in other words， the。The norm squared of Psi sub a you can think of aside from this unconventional overall。

嗯。Normalization as representing the probability of that particular state。

 So there's no harm in writing it this way as long as as we don't get confused。

 the probabilities assigned to the different pure states in the ensemble are are there。

 but I've just absorbed them into the normalization， so I don't have to write them out explicitly。

So all I've used here is the property of complete positivity。

We know for any input and in particular for this maximally entangled one。

 the output is a density operator。 We know that any density operator can be represented as an ensemble of pure states。

 and I've written down the most general such ensemble okay。

So now there's a nice thing that we can notice， which is here we considered the identity tensored with our channel acting on this entangled state。

 and we got this particular output。But。We can recover。From that。

The result of applying the channel to any pure state for system a。

This is a trick sometimes called the relative state method。And。

If we just think about the initial state here for now before we've let the channel I tensor E act on it。

 how would I recover from this entangled state of RA a particular pure state for system A well let's write down a particular pure state for system A in terms of our basis elements labeled by I it's just a sum of coefficients phi I times basis element I for a。

 but now we can think of the。Brara associated with basis element I for R。As a linear operator。

 which takes the Hilbert space of R A to the Hilbert space of a as we've discussed before。

 so we can take the partial inner product。Of the entangled state for system RA。

 this state Phiilda with the basis element I for R and what that's going to do is pick out in this sum。

 the basis element I for a。So since this is just a way of writing the basis element I for a。Then。

This is just alternative way of writing phi， the sum of Phi I。Basis element I for a。

And now I'd like to think of this linear combination， this sum over eye as a linear map。And。

What I'll do is I'll just notice that。If I considered the。

Brara associated with the sum of Phi eye star basis element。

 I taking the bran instead of the k would。Complex conjugate the coefficients。

 so I can just as well write this as the action of the bra associated with the state vector for our Phi star。

Acting on the entangled state for RA， and that's going to give me back Phi a。Okay。

 so this is what I mean by the relative state of the entangled state RA。

 the result of acting with this bra for the reference system。But now here's the nice thing。That。

Now we're when we consider the action of the channel on this input。

 nothing's happening to the reference system。 The identity is acting on the reference system。

 so I can just as well。Apply this relative state trick after the action of the channel as I can before。

Okay。So I know if I applied the relative state trick first。

 if I put a five star for reference system。A on the left and also on the right。That would just。啊。

Allow me to get from the input pure state written as a density operator。

 the density operator for the pure state Psa A of system A。But I could just as well。

Use the relative state method after the channel X， so I can write the result of a to the input pure state phi as in this way。

 take this output state， which is the sum over a of these pure states chosen from our ensemble with their normalizations absorbed into the state and then put a phi star for system R on the right and a phi star on the left。

 and that's going to give me the same thing as the result of the channel applied to the input state projection onto phi for system A。

And now the thing to notice is this is an operator some representation of the output。

Because I can think of the result of taking the Bra I star acting on the entangled state or the joint state of our a prime。

 the state I called Psi tilde。I can think of that。As a linear map。Acting on the vector phi。

 the only thing we have to check it's clearly has the property that if I take a superposition of phi1 and phi 2。

 that's the same thing as letting the cat phi1 star plus phi2 star act from the left on the joint state side tilde of RNA prime。

 we have to make sure that you know it's linear rather than than antilinear and that's why。You know。

 we have phi star instead of phi so that if we take a linear combination of phi1 and phi 2 in system a with coefficients a1 and A2。

 then Phi star is going to have the coefficients A1 star and a2 star but then because we have the bra here instead of the cape cat that's going to become a1 and A2 so this is just a way of writing a linear map and this is the operator sum representation。

Of the output of the channel。Where the operator MA is just defined by this relation。Okay。

Since we have an operator some representation for the channel， we know since we saw how to do it。

 that that means there is a way of constructing the channel。By introducing a。

Extra environmentron system applying a unitary to A in the environment and tracing out the environment。

But more generally， we've seen we have a nice isomorphism of states and CP maps that any CP map can be represented by the state that we get when we apply the channel tensored with the identity。

On this maximally entangled state。So that was a。Kind of a tricky argument。

 but let's just summarize what the ideas were。So we're given some channel which is completely positive。

 so by definition that means we can extend the channel to identity tensored with E。

 and that's going to take a maximally entangled state on the extended system RA to an output density operator。

 which will be on the reference system and composite with a prime。

 which is the output system from the channel。And we can represent that density operator as we can with any density operator as an ensemble of pure states。

 and then it turns out that we can associate each one of the pure states in that ensemble with a linear operator。

 the cross operator in this operator sum representation of the channel。Okay。Now。

We've discussed before that if we have a density operator， which describes a mixed state。

The ensemble representation of that density operator is not unique。Well。

 it's going to be the same thing here because of that isomorphism between states and channels。

 the cross representation of a non unitary channel。Is not unique。

It's exactly the same freedom because of the isomorphus in the case where we are talking about a unitary channel。

Then of course， there is a unique cross representation。

 there's just one operator in the operator sum， which is that unitary。

But once we have more than one term in the operator some representation。

 then there are multiple ways of representing the same channel。

 So let me remind you again of the Houston Jo Woods H J W theorem that we talked about before。

For state ensembles。And we said， well， suppose you have a density operator and it could be represented as a confix combination of some set of basis states。

Here， I've denoted them by Psi Tttle twittle A， or by gamma tilde mu。

And before I think we wrote out explicitly the probabilities assigned to the different states in the ensemble。

But here， just to simplify our equations， remember。

 I've absorbed those probabilities into the normalization of the states in the ensemble。

 These states are not necessarily mutually orthogonal。

And they have they might have this overall funny normalization that I chose for convenience。

 so I wouldn't have to write one over the square root of D here and there。

But what did the HHW theorem tell us， it told us that if there are two such representations。

 then there's some unitary matrix。Which relates the choices， the HW theorem， as I wrote it before。

 had explicit probabilities in the equation associated with the。

The elements of the pure state ensemble， but because I've absorbed those to the states。

 they're not appearing in the equation as I'm writing it here。There's some unitary matrix。

 though that relates the two ensembles。If we by means of this state channel， isomorphism。

 translate that into a statement about our freedom in choosing the cross operators。

 well it's a very similar statement， if I have a channel and I can write it。As。

An operator sum representation with a set of cross operators MA。

 but I can also write that same channel as an operator sum representation in terms of the cross operators and mu。

 then there's some unitary matrix that relates the N operators to the M operators as I've written down here。

And how many cross operators do we need to represent a general channel？

Which map system A to system A prime。Well， we're going to need just as many as the number of pure states we would need。

In an ensemble representation of a density operator on this output system here。

 which remember is the composite of the reference system R and the output a prime of our channel。

 Remember in general， our quantum channel could map a system A to a system A prime where the two systems A and a prime don't even have to have。

The same dimension， but the reference system is the same on both sides because only the identity acted on the reference system。

So we can ask， all right， well， how big a Hilbert space？

Do we have here and the answer is the composite system of a prime and R has a dimension which is equal to the dimension of R and the dimension of a prime。

 What's the dimension of R Well we chose it to be just big enough。

That we could construct this maximally entangled state， and so it has the same dimension as a。

So the dimension of our output Hilberts。What do I do now， I see I got to work。

Yes where start the thing。嗯。你啊。Whereas I write this output Hilbert space has a dimension which is equal to the dimension of R name same thing as the dimension of a times the dimension of a prime and we know that if。

 for example， we choose the orthogonal ensemble， it's always possible to write down an ensemble representation of a density operator。

In a Hilbert space， which has dimension D as an ensemble of deep your states because that's the number of eigenstates of the density operator。

So that means that it's always possible to find a gross cross representation of a channel with a number of terms in the operator sum。

 which is the dimension of a times the dimension of a prime。A， the input system for the channel。

 a prime， the output system。Now， it is possible to write down cross representations with many more cross operators。

 just as I can represent a。Density operator。For for a qubit， if I want to。

 as a convex combination of an arbitrarily large number of pure states。

 it's possible likewise to have a number of cross operators for a given channel with fixed input and output dimensions。

 which is as many as I please， but in general for a general channel。

 I don't need to have more cross operators in the dimension of the input system times the dimension of the output system。

Another question we could ask is how many parameters do we need to describe a quantum channel？

How many real parameters are there， What's the dimension of the space of quantum channels。

 if you like。Which map system A to system a prime。 Well， first of all， it's a linear map。

It takes the hermeian operators of A to hermeian operators of a prime， and it preserves the trace。

So Hermeian operators。For a system of dimension D。The number of hermeian matrices that are D by D。

 the number of real parameters that is to say that we need to characterize them is the dimension of a squared。

And same thing for the output density operators， D prime squared。

 so we have a linear map from D squared dimensional space to D prime squared dimensional space。

 that's a total number of parameters， D squared times D prime squared。However。

 we also know if we're talking about a channel that it preserves the trace and the trace of the output is fixed for any of the possible input states。

 so that's a number of constraints on the channel， which is equal to the dimension of the space of possible input states。

 namely D squared， so from the trace constraint that they're altogether D squared such constraints that reduces the number of real parameters accordingly。

So for quantum channels， which map system A to system A prime。

 the number of real parameters that characterize that space。

 its real dimension is D squared times D prime squared minus D square， it's a lot of parameters。

 even for a qubit， even if we're just talking about a channel mapping a qubit to a qubit。

The number of parameters is 12 because it's  four times 4，-4，12 parameters。

So it's a pretty complex thing to describe general decocoherence even for a single qubit。

 you can see it's a lot more complex。Then unitary maps。

 unitary maps from our two-dimensional vector space of a qubit to itself。

 since we don't care about the overall phase which doesn't affect how the density operators map。

 there are only three parameters for for an SU2 matrix。

 a unitary matrix with if we don't care about the overall phase。

 but we need 12 for a general decocoherence process， much more complex。

 and that's kind of a headache for experimentalists who would like to be able to characterize decocoherence for systems in the lab。

 they have a lot of parameters that they need to track down。All right。

 so we learn the general theory of。Quantum channels today， the important concept of。

Channel state duality that helped us to understand that any physical operation that takes quantum state to a quantum state can be nicely characterized by an operator sum representation so what i'd like to do next in the next lecture is to sort of fill out or amplify this rather abstract discussion so far by discussing some examples of quantum channels so that's what we have planned for for next time。

And。I hope I'm still recording here。Am I， yes， I am now thank goodness。So I guess that's it for now。

And I'll see you next time。Have fun until then， Stay well。

