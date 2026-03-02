# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p04 -04-Ph CS 219A Lecture 3B Measurement.zh_en -BV1KgffBoEUc_p4-

![](img/550a184be77cbf1aba62577a7b20e7f0_0.png)

Sorry， I had a technical glitch there， which terminated the video file。

And so I'm starting a new file。 so lecture3 is going to be split into。Two MP4s。

 which I'm going to call lecture 3 A and lecture 3 B。This is the beginning of lecture 3B。

 I'll pick it up where we left off before。So。We were talking about。

Measurement in the scenario where we have an apparatus in a system。

 There's a unitary interaction between apparatus in system， followed by an orthogonal measurement on。

The apparatus。And so the form of the unitary interaction。

That I'm going to want to consider between the system and the apparatus。Is shown here。Am。

I've expanded it in terms of the orthogonal projectors acting on the system。

Those are the measurement outcomes on the system that I want to consider。

And for each measurement outcome on the system， an orthogonal projector。On the apparatus。

 there's what I'll call a shift operator。Now this is summed over B so for each basis state for the apparatus what this operator does is it shifts the basis state by the amount A。

 which labels this projector so you should think of this as being addition modo D。

 if there are D possible measurement outcomes， the apparatus system has dimension D。

 we get labeled the basis states by01，2， etc cea up to D minus1。And by addition modo D， I mean。

 if we shift by one， for example。than， one。To two， two goes to three， et cetera，0， goes to1。

 D minus1 goes to zero， so you can think of the D outcomes as being arranged。Like points on a circle。

 which are cyclically identified。This shift shouldn't really be thought of as a shift on a circle。

And it's kind of obvious that this is unitary， meaning it preserves inner products。

 but let's check it explicitly。By evaluating the product of you and you ad jointint。

 So here I've just written you again， expanded as before。 And here is its ad joint。

 I don't have to do anything to the projector， because it's。Her mission， the adjut。

 doesn't do anything。But in the shift operator， which that part is intermission， so the。

Bras and cats change places。Here， and now I want to evaluate the product。

So we have an inner product of basis state B for the apparatus。With a basis state D。

 So that will require B to be equal to D。 And acting on the system。

 we have a product of two projectors， E sub A and E sub C。 that will require that a equal to C。

 So the sum is going to collapse to just a sum over A and B。Where for the product of EEC。

 I can write EA。And then for the cat B plus A， bra D plus C。

 that becomes the projection on to basis state B plus a。But for each value of a。

 when I sum over all the values of B， I'm summing over projectors onto all the basis state。

 So that's just the identity operator acting on the apparatus。

 And then I have the sum over a of the Es。 And because of the completeness in the measurement operators。

 That's just the identity on the system。 So we see U U add joint is equal to the identity operator。

 this is a unitary operator。 And the way we're going to use it。

If we're going to initialize our apparatus for some particular basis state， let's say the zero state。

And then after the interaction， we're going to perform an orthogonal measurement in that basis on the apparatus。

😊，So if we have some input statesi of the system， which is what we're going to want to measure after this unitary interaction。

We have this entangled state of the system and the apparatus for each basis state a。Of the apparatus。

 the input state is x known by EA because when EA acts， the apparatus gets shifted from zero to a。

And now we。Envision Bob。Or some measuring the apparatus。In the。This orthogonal basis， so that means。

Each one of Bob's measurement outcomes， assuming is Bob doing the measurement。

 each one of our measurements on the apparatus is projecting onto one of these basis states for the apparatus。

 but it's not doing anything to the system。And so when we let that operator act on this state for some particular outcome a。

 it's just going to project it down to EA acting on the system tensored with a for the apparatus and the probability of that outcome will just be the norm squared of that state。

 and that's just the norm squared of。System projector E A acting on the input system state。

 So you see what we've wound up doing is realizing an orthogonal measurement。

 obeying the same axioms we discussed for closed systems。Acting on the system。

 but we realize that measurement。By leveraging our ability to measure the apparatus without assuming a priorityi。

 we could measure the system， though we did assume that we could do some controlled interaction between the system and the apparatus to create this correlated state。

But now we can ask the question。What if we measured the apparatus in a different orthogonal basis？

You see the form that I've written here。Is actually the schmidt form。

Of an entangled state for the system in the apparatus。

Because the basis states A are a north normal basis。But furthermore。

 the EA size are mutually orthogonal。Okay， because these are orthogonal projectors and then I've performed a measurement of the apparatus in that schmidt basis and that's how in effect projected out the result of applying EA to the system。

But there's no law that says that's the basis in which I have to do the measurement。

 I could measure the apparatus after the unitary interaction in any orthogonal basis I want。

So as an example， let's suppose we just have two qubits， a system qubit and an apparatus qubit。

We might just have something concrete to think about。

 imagine that we're measuring the spin of an electron。

We do a stern Gerlock type experiment and it gets deflected either up or down in homogeneous magnetic field。

 so it moves to one of two positions and we're going to measure that position。

Of the electron to determine the outcome of measurement of its spin。

But suppose we do something sneaky， we don't measure in the position。

It got deflected up or deflected down corresponding to state 0 and one of the apparatus。 But instead。

 we measure in a different basis。 See， the state that we get is this entangled state。

If the input state of the system is alpha0 plus beta 1。

 the entangled state of system and apparatus is alpha 00 plus beta 11。

 and then when we measure the apparatus and the01 basis we're。

projecting out either zero for the system or one for the system with probabilities which are given by absolute value of alpha square or absolute value of beta squared respectively。

But by some magic， maybe by using a beam splitter or something， we measure in a different basis。

Not the base is0 and one of the apparatus， but the base is 0 plus1。

 a state I'm calling plus or0 minus1， a state I'm calling minus。

Maybe I put the traveling electron in an interferometer or something like that so that I can measure in that basis。

However， I do it to find the post measurement state。

 I should take this entangled state of system and apparatus。

And ask what the result is of applying the corresponding。

Bra to the state to get a post measurement state for the system and now that state up to normalization is just going to be in the case of the plus1 outcome for this measurement of the apparatus as alpha0 plus beta 1 for the system。

 the same as the input state， or if I got the outcome minus0 minus1。

 then apart from possible normalization。The post measurement state is going to be alpha0 minus beta 1。

And those two states are not necessarily orthogonal， In fact， they're orthogonal only if。

Alpha beta is equal to。Equal to zero。And then find the probabilities for those outcomes。

 I just take the result of applying the broad to the state and take its absolute value squared because those are our rules for assigning probabilities to orthogonal measurements。

And because we have。Since we knew to normalize the state plus or minus the one over squared of two。

 which gets squared， that means we're going to have one half。The norm of alpha0 plus beta 1。

The norm squared for the probability in the case of the plus outcome。

And the norm squared of alpha0 minus beta 1， the probability for the minus outcome times1 half。

And those two probabilities are the same for alpha 0 plus beta 1 and alpha 0 minus beta 1 the norm squared is absolute value of alpha squared plus absolute value beta squared。

 namely1， so the two outcomes both have probability1 half。

And the two post measurement states are not mutually orthogonal。And so in this case。

 if we were to repeat the measurement again immediately after， we wouldn't get the same outcome。

If we get the plus one outcome， the state becomes well the same as it was initially alpha0 plus beta 1。

If you get the minus outcome， it becomes alpha 0 minus beta1。

 then we measure again the two outcomes are still going to have probability one half。

 whatever they were the first time。 and so this is really a different type of measurement than we've discussed before。

 It doesn't have the probability the property that if you immediately repeat the measurement。

 you're going to get the same outcome with probability one。

So now I'd just like to look at this a little more generally。

 now I'm going to speak of generalized measurements。

So now there are two systems and now I'm going to go back to calling them Alice and Bob instead of system and apparatus。

 well sometimes I'll say system and apparatus， but now I want to imagine。

That there's a world that consists of Alice's system in Bob system。 Alice can only observe system A。

 and Bob can do whatever he wants to system B。 and so there's going to be some initial state of Alicelysis system。

 which is not。Correrelatedated it all with Bob system。

 and then in some unitary interaction is going to occur， which will entangle A and B。

 And then Bob is going to do an orthogonal measurement on system B。

And report to Alice the outcome that he obtained。And what we'd like to know is what probabilities should we assign to those outcomes and what is Alice's post measurement state for each possible outcome？

So now A and B are just any finite dimensional systems。We start out， let's say。

 with a pure state for system A。And we set system B to a standard basis state， I'll call it zero。

 and then there's some unitary interaction between the two that maps the joint state of A and B to a new state。

 which I'm going to call side prime whoops。To a new stateside prime。

And I can take that resulting state and I can expand it in any basis I want for Bob system。

 but let's use the basis in which Bob is going to do his orthogonal measurement。

 I can use any basis I want and that's a convenient one to use。

So for each of the possible basic states that we might have for Bob。

There will be some corresponding linear operator acting on Alices input with which it's correlated。

 and then we have to sum over all possible basis states for Bob。To represent this stateside prime。

 the joint state of A And B after the unitary interaction。But this is a unitary operator。

 and that means that it has to preserve inner products。

 so let's check what that implies about these operators and mu acting on analysis system。

I should have for any input state psi paralysis system。

The output states I probably be had better be normalized because the input state was。

 so let's evaluate its norm squared。 I take the inner product of the state with itself。

So I'm summing over two indices now， one for the states prime may B。

 another summation for the corresponding bra Psi prime。And now I have to evaluate this in a product。

 but I know that Bob's basic dates labeled by muer ortho the normalmal。

So we'll get a non zero contribution only when mu is equal to nu that collapses this to a single sum。

And so what I have is the sum over mu that index which labels Bob's base estates and therefore is measurement outcomes。

The expectation value in the state Psi Alice's input state of M a joint M summed over all the outcomes。

And we know that this has to be equal to one for any possible input state for Alice and the only way that's possible。

Is if the sum of M a joint mu is equal to the identity as an operator equation。Okay。

 so just from the fact that U is unitary， it must be the case that the sum over mu of M adjoint M is equal to the identity acting on Alicelysis system。

So now we imagine Bob does his orthogonal measurement。So his measurement operators， his projectors。

 will all have the form of identity analysis system because he doesn't touch that。

 but he projects his own system onto the basis state mu。

And then to find the probability of a particular outcome。

 we take the result according to our measurement axiom for closed systems。

Of applying EMu to the state right before the measurement。

 which is the state side prime after the unitary interaction has occurred。

 and we take its norm square。And when we get a particular outcome。

 remember we're just going to get the state MU。Acting on Alice's initial state Psi。

 so its norm squared is just the norm squared of M applied to Psi。

And what's the post measurement state well it's just the result of applying em to the input state s prime remember that projects Bob's system onto a particular basis state in mu and it applies MU to Alice's input and then we have to normalize it to make sure we get a normalized state。

And now we could imagine that we immediately perform the same measurement again by the same method。

 So what will be the probability if we got the outcome mu the first time of getting the outcome new in the second measurement。

 the conditional probability of new in the second measurement given the outcome U in the first measurement。

 so I take the post measurement state from the first measurement， and then I apply。

M new the measurement operator corresponding to the second measurement outcome to that post measurement state。

 and I take its absolute value squared and so that is this expression in the numerator I have a new M absolute value square and new M applied to psi absolute value squared divided by the。

Norm squared to M applied to Alice's initial state。

 so the only way that will be guaranteed for any input from Alice that we get the same outcome the second time is if when we apply M new after applying M that give zero when mu is not equal to new and when mu is equal to new up to a possible phase factor。

 it just gives me M back so that's essentially an orthogonal measurement and for anything other than an orthogonal measurement on Alice's system。

 that is if Bob performs his measurement in some general basis we won't have the repeatability property that we found in the case of orthogonal measurements。

For closed systems。So let's。Take sort of a broader look at what a measurement is。

 We want a measurement to have the property。That there are different outcomes。

 we can assign probabilities to all the outcomes and those probabilities had all better all been non negative real numbers and they better sum to one。

So in general， we should describe a measurement this way。

 not necessarily assuming it's an orthogonal measurement， as we considered before。

 though I'm still going to use the notation EA that we use before for the measurement outcomes。

 but now these are not necessarily going to be orthogonal projectors。

 but they better be her mission and they better be non negative because we want their expectation values if they're to correspond to probabilities of outcomes to be non negative real numbers。

And in the case that we just discussed， these measurement operators that determine the probability are just。

MA Jot MA where the MAs are the operators that occurred in the expansion of the state。

 the joint state of A' system and boOs， but we want the probability。

As shown here to be the expectation value of E in the input state。嗯。

In the case where EA is MA adjot MA then it is， of course for missionian。

 it is also obviously non negative because if I take its expectation value in any state that's just the norm squared of MA acting on a state and that's certainly greater than or equal to zero。

And we also want the sum of the A's to be give the identity。

 and that means that the probabilities are going to sum to one。And of course。

 that's true in the scenario we just discussed。Because the sum over a of MAA joint MA equals identity followed from the unitity of the interaction between the system and the apparatus。

Now that was for the case where Alice's initial state was a pure state， if it's a mixed state。

 we know we can always think of that as some ensemble of pure states and then the probability of the particular outcome A will just be given by the trace。

Of the density operator before the measurement times EA again， those are probabilities。

 they're non negative real numbers， and they sum to one。

Now this type of generalized measurement is sometimes called a positive operator valued measure。

That's kind of a fancy word i'll mostly just call it a generalized measurement。

 but generalized measurement if you like can。Non negative operators。

 a way of choosing non negative formationian operators with sum to one。

 and they can be used to define probabilities。For any input state， any input density operator。

And in fact， any such POVM， any such generalized measurement can be realized in the way that I described as a unitary interaction between system and apparatus。

Or if you like between Alicelysis system and bobs followed by an orthogonal measurement on Bob's side。

Well， the reason is that we can always take a square root。

Of the operators defining the POVM and take those to be the operators m subA in the construction I just described defining the unitary between alysis system and bombs when we take the square root there there's an ambiguity。

Because if I want MA to have the property that MAA joint MA is equal to EA。

 that doesn't uniquely define MA， it defines it up to a unitary operator acting on the left。嗯。

That is。If I consider the square root of MAA joint MA and by that I mean the square root with non negative eigenvalues of the non negative operator MAI joint MA I could。

Apply unitary acting from the left and then if I take MA adjot taA。

 that unitarial just drop out because UA adjoint UA。Is equal to the identity。

So given the POVM defined by the set of operators EA that have the property of being Hermeian。

 non negative and complete。The most general way in which I can。

Construct a scenario in which that measurement is achieved by first a unitary interaction between system and apparatus followed by orthogonal measurement on the apparatus。

would give a post measurement state given by MA acting on the input state divided by normalization。

But in that post measurement state， we have the freedom for each measurement outcome for each value of a to act with a unitary that's conditioned on that outcome and of course that makes sense because if you do a measurement。

 you always have the freedom to take the post measurement state and apply a unitary to it。

Because other than。Other than measurements， unitaries are the most general things we can do to an isolated system。

 okay？Now in the case where the input state is mixed。The post measurement state。

If we have a particular measurement outcome A will just be given by MA acting on the input density operator on the right and MA a joint。

Our acting from the left and MA had joined acting from the right。

 and you can see that again just by expanding row in terms of pure states。And of course。

 then we have to normalize it， so it'll have trace one。

Now let's consider the following thing so far we've been imagining。

That Alice and Bob have a shared system， Alice can only measure or observe system A。

 Bob can do orthogonal measurements on system B， the two interact according to some unitary interaction。

 and then Bob measures。But in order for Alice to know the outcome of the measurement。

 Bob has to tell her。That the particular outcome was A。

 and then Alice knows how to update her state to the post measurement state that I've described。

But what if Bob doesn't tell Alice the outcome of the measurement or if that record of the outcome gets permanently lost？

Well， then Alice has to just consider the convex combination of all the possible output density operators for all the possible measurement outcomes。

And weight them by the appropriate probabilities， the probabilities for those outcomes。

So in the case where Alice doesn't learn the outcome of Bob's measurement。

The state evolves in the following way。The initial state row for analysislysis system becomes the new state row prime。

 I can think of that as the result of a certain linear map acting on the input that map is defined as summing over all the possible measurement outcomes。

 the probability of that outcome times the density operator after the measurement when that outcome occurs。

And so what is that， Well， we sum over。The outcomes， the probability of the particular outcome a。

 that's just the trace of MA row MA a joint， the post measurement state is MA row MA a joint and then we have to divide by the normalization well luckily the trace in the numerator which came from waiting with the probability。

Cances out the trace in the denominator which came from normalizing the post measurement state。

 so we really do have a linear map it's linear in row it's just a sum a of MA row ma a joint where again we know that the sum array array of MA A joint ma is equal to the identity。

Because the interaction between Alysis system and bombs was unitrior because all the measurement outcomes have to have probabilities that sum up to one。

So this type of linear map of density operators to density operators。

Of this form is what we call a quantum channel， or sometimes we call it a super operator。

 super operator， meaning it takes operators， density operators to operators， other density operators。

 We also call it a trace preserving， completely positive map。A map of density operators to operators。

 which preserves the trace。This normalization condition on the MAs ensures that row prime and row both have the same trace。

And why do we call it completely positive， well it does take a density operator to a density operator。

 it takes positive to positive positive operators to positive operators completely positive though I'm not going to explain what we mean by completely positive until until the next lecture。

Now， why do we call it a quantum channel that is in deference to the traditions of communication theory where we might think of two parties？

Communicating， let's say they're Charlie and David Charlie prepares some signal state。

 it's just a classical bid stringing， he sends it to David but over a channel which is noisy so the noise in the channel can be described by a probability distribution that's conditional on the input state in other words。

David will receive the output why if。Charlie sent the input X with some conditional probability。

 the probability of Y given x。And this is sort of the quantum version of that we can think of a quantum state prepared by Charlie。

Which is sent to David， but it doesn't arrive intact。 Instead， it has interacted in some。

Uncontrollable way with the environment， and we have to trace out the environment。

 which neither Charlie nor David observe to describe what arrives。In in David's laboratory。

Output from the channel， so just as we speak of channels in the classical case。

 we also speak of channels in the quantum case。We can also think of the channel as describing time evolution we。

Put a quantum state in a quantum memory， but it's not a perfect memory。

 so that state that system interacts with the environment。

 we have to trace out the environment to describe the system since we don't observe the environment and that's described by a quantum channel So you can see in that setting。

Or in the communication setting。We can think of the quantum channel as describing noise in a quantum system。

 What happens when the quantum system interacts with the environment as quantum systems inevitably to。

 and we can't control the environment that's described by a quantum channel。

 Now the way I envisioned it or the way I described it to you。

 we can imagine that the going back to the Alice Bob language that Alice's system interacts with Bob's and becomes entangled with it and then Bob does a measurement。

 but he doesn't tell Alice the outcome of the measurement So that's just really a way of describing doing the partial trace over Bob system。

 I can do the partial trace in any basis I want， so I can imagine that Bob does the measurement and then throws away the outcome that's just a way of describing taking the partial trace in a particular。

Basis。So what we found is called the operator sum representation of a quantum channel。

 why is it called operator sum because we have a sum which we interpreted as a sum over measurement outcomes by a and for each one of the terms in the sum and operator MAX on the state and the density operator language then we have MA acting on the a catt MA a jointt acting on the bra in the density operator it's also called a cross representation of a quantum channel and the MAs are sometimes said to be the K operators and I emphasize again the reason we're interested in quantum channels。

 the reason it's important for us to understand them and know about them is they describe noise and quantum systems and noise is the formidable enemy of quantum computing if a quantum system is subject to noise if we can't control it perfectly then we will be challenged to do。

Reliable quantum computation to fight off the destructive effects of noise。

 we need to use the idea of quantum error correction and i'm not going to explain quantum error correction in this fall term。

 it will be the topic of the winter term when Professor Kaya is teaching。

 but in the fall term we will at least，Set the foundations pave the way for that later discussion by delving a little bit into the theory of quantum channels。

 and that's what I want to do in the next lecture to talk about properties of quantum channels and to deepen our understanding of how they work。

So that's what we'll be doing next time， this is it for today， so thank you for listening， have fun。

 and study hard。We'll see you next time。

![](img/550a184be77cbf1aba62577a7b20e7f0_2.png)

Thank you。