# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p06 -06-Ph CS 219A Lecture 5 Qubit Channels.zh_en -BV1KgffBoEUc_p6-

![](img/e660e8108e14ff1c61621616065966a7_0.png)

Hey everybody， welcome back to Ph， computer Science。219 a。

This will be the fifth lecture of the fall term。As you may know。

 I've had a few technical glitches in the last couple of lectures。In fact， last time， by mistake。

 I turned off。Screen sharing， so for about half the lecture you were just looking at my face。

Without saying my slides。But since I'm dising the slides as a PDF file。

 I hope you were able to persevere。By viewing the slides。While listening to the lecture。

And I think by now， maybe I've reached the point of。Having made most of the obvious mistakes。

 So I'm anticipating， I feel lucky today that。We won't have。Technical glitches today。In fact。

 I even turned off my phone so we won't have Siri butding in to tell us what he thinks she knows about quantum channels。

So let's hope for a technically perfect lecture。Although I'm sure the lecture itself will still leave something to be desired。

 but I'm doing the best I can。 I hope you're enjoying the course。I'm having fun。

 but that's not really a fair test because I'm kind of easy to please and I love this stuff。But。

I hope you're learning something。So let's see， and now I'm going to be checking from time to time that I really am sharing the screen。

 I guess I learned my lesson on that。But。I believe I am。 so let's go。

 So this will actually be the last of our lectures introducing the theory of open quantum systems。

Remember when we say a system is open。If it's not perfectly isolated。

 if it can exchange energy and information with an unseen environment。

 we're interested in that because all real systems are open， at least to some extent。

And we've discussed how in the setting of open quantum systems are axioms that characterize the quantum theory of closed systems need reconsideration。

Quantum states of an open system are described by density operators in general。

Measurements are not necessarily orthogonal measurements they can be。POVMs， generalized measurements。

 and last time we talk about we talked about how quantum states evolve。When systems are open。

 that's described not by unitary maps as for closed systems， but。Instead。

 by what we called quantum channels。Also known as trace preserving completely positive maps。

And we discussed how a channel can be given a operator some representation。

 also called a cross representation。And we discussed why。

Physical operations that can actually be applied to quantum state should have the property of being completely positive。

And last time we use an isomorphism between completely positive maps。

And states to show that completely positive maps always do have operators some representation。

 so we can always imagine。When we're talking about a quantum operation that what's really going on。

 whatever really means is that there's an extension of the system to include an environment and that a unitary map is being applied to our system and the environment where initially the system environment are uncorrelated in a product state and then we trace out the environment。

How to get the result of the map， This point of view is sometimes honored by the name of the Church of the larger Hilbert space that we can always use our closed system point of view。

 if we imagine extending the quantum system is the gist of that ideology。

So what I want to do today is continue one more lecture with open systems by fleshing out what we learned last time about quantum channels。

 the discussion last time was quite general and abstract， that's okay， I like general arguments。

 they can be very powerful。But it's also important to fully appreciate the general theory to see how it applies to some examples。

 so what I'll mostly talk about today are some examples of quantum channels。

And to keep things simple， I'll consider quantum channels just acting on a single qubit on a two dimensional Hilbert space and the examples will。

I think be instructive， apart from deepening our understanding of the general theory。

Of quantum channels， they also have some lessons that are of physical interest。So。Let's start。

So the first example of a quantum channel that I'd like to discuss is called the depolarizing channel acting on a qubit。

This channel is special because it's sort of the most symmetrical of。Quantum channels。

It doesn't pick out any preferred direction in the Hilbert space in a sense。

And we can think about the depolarizing channel for a qubit in the following way。

 you remember our notation for poly operators which。Sometimes I've called Sigma1。

 Sigma 2 sigma 3 here I've used the alternative notation， X， Y， and Z。

And what happens when a quantum system when a qubit is subjected to thepolarizing channel？

We can think about it this way。That there's some error probability P。

 a probability P that something happens to the qubit。So with probability 1 minus P。Nothing happens。

But with probability P， one of three possible errors occurs， which changes the quantum system。

 I'm imagining that you know we'd like to preserve our qubit in a memory and so I'm speaking of an error。

As something that changes it so it becomes damaged and it's not the original state of the qubit that we stored in our quantum memory。

And those three possible errors are all described by poly operatorsators and the three poly operatorsators denoted here X。

 Y， and Z。Are all equally likely， so each occurs with a probability P over three。

 so the total probability of a polyre is P。And the three types of errors we can think about this way。

The polyopator x flips basis state zero to the basis state1 and one back to0 well that's just like a bit flip that occurs on a classical bit so I can think of the x as a bit flip error。

The Z。I can think of as changing the relative phase of the basis state 0 and one， or if you like。

 I can imagine an alternative basis， which we talked about before the。

Basis H plus the uniform superposition of0 and1 and minus the orthogonal state。

 the superposition0 minus1。And because it changes the relative phase， the relative s of0 and1。

What a Z error does is it flips a plus to a minus and a minus to a plus。

And y up to a phase factor is just the product of a Z in a x。

 so you can think of that as the error that simultaneously applies both a bit flip and a phase error。

So we can describe this channel like we can any channel in terms of some set of cross operators。

And for this channel， I can choose the cross operators to be the four that I'm showing here called M0。

 M1， M2 and M3， so M0 is the cross operator that corresponds to the possibility that nothing happens to the qubit。

 so that's proportional to the identity， it doesn't change the state。

 and it has a coefficient which is the square root of the probability with which that operation occurs。

 namely the square root of1 minus p。And then for our three other cross operators。

 which do correspond to errors that affect the qubit。

They are respectively proportional to poly operatorator X， Y， and z， and all have a coefficient。

 which is the square root of the probability of that error。

 which in this case is the square root of P over 3。

So now if we think about our operator sum representation， remember how it works？

The channel acting on an input density operator。Is going to be the sum of four terms， which is。

In this case， all of our operators are frommeian so I don't have to worry about the difference between M and M adjoint。

So I have M0 rh M0 and M0 is proportional to I， so that just gives me one minus P times rh。

 the input density operator。And then I have M1 row， M1， M2， row M2 and M3， row M3。

 so each one of those will be proportional to P over3， the probability of the corresponding error。

And then I get the sum of x rh x， that means x error occurs on the state， y rh y， y R and z rh z。Now。

 these poly operators all have the property that they squared one so we can check easily our normalization condition for the cross operators。

 This is the condition that the。A result of applying the channel to input density operator row。

 if row has unit trace， if it's properly normalized。

 so will be the result of applying the channel to row。And well， if we just take the sum over a of。

MAA Jo time in this case。MA is self joint， so MA adjot is the same as MA that's supposed to be equal to the identity that's the condition that the trace has preserved。

So from M0 squared I get1 minus pi and for the other three terms。

 I get p over three times I because there are three terms that adds up all together to p times I and the sum of all MA a join mas is then just the identity as it should be。

 or we can see the same thing coming back here， if we just take the trace of the right hand side of this equation。

It's the trace of a sum which is the sum of the traces。

So here I get a1 minus p times the trace of rh， which is1 minus p and when I take the trace of x or rh x。

 of course the trace is cyclic so I can move one of the x is over to the other side x squared is equal to the identity so each one of these terms gives p over three times the trace of rh there are three such terms and so I wind up with one minus p plus p。

Times the trace of row， which is one。Now， remember。

 we talked about this idea of channel state duality。

And let's see that in action for thepolarizing channel。The way it worked was， we imagined。

Preparing a maximally entangled state。Of the qubit on which our channel is going to act and a reference system and then we consider the channel acting only on the qubit not on the reference system so let's see how that works here。

 i'm going to choose as the initial state， the entangled state of our system and the reference system。

This state5 plus。It's a superposition of0，0，0 for system and zero for reference plus 11。

 and I normalized it。And I'm also going to consider four other states which are all entangled。

 they're all maximally entangled， meaning that in all of these states。

 if I trace out the reference system， the density operator for the system is just maximally mixed。

 it's one half times the identity， and they're all mutually orthogonal。

 so we can think of these entangled states as a basis for the fourdimensional Hilbert space consisting of our system and reference system。

 and the other states in this basis are zero，0 minus11。01 plus 10 and 01 minus10。

 It's easy to see They're all mutually orthogonal。And you can check that so now to find the state that under the isomorphism between states and channels corresponds to our channel。

 what we are to do is to take this maximally entangled state5 plus I'm here looking here at the corresponding density operator。

 the projection on to5 plus。And I let the channel Act on the first qubit and the Ident Act on the second。

Okay。So with probability 1 minus P， our channel doesn't do anything， so I still have。

The pure state 5 plus。But then with probability P over3。

 each of three possible things can happen an Xer， a y or z。

So what happens if I apply x to one of the qubits and not to the other。

 well then 01 plus 10 is going to become 10 plus 01。

 that's another one of our basis states what I call psi plus， so when I have x。

Acting on the left and on the right。This。Kt。Phi plus bra phi plus becomes cat psi plus bra psi plus。

And if I consider Z acting on one of the two qubits， the first qubits say。In 5 plus。

 that's going to change the relative phase of the zero and the1。

That's going to map phi plus to what I call phi minus， it becomes00 minus11。

 and so we also have a term here in which the projection onto phi plus has been mapped to the projection onto phi minus and then the third possibility is the y error also occurring with probability P over3。

 and because that both flips a bit and changes the phase。

 it maps phi plus to the state here that I call si minus up to a phase and that phase isn't going to matter when we can correspond when we look at the corresponding density operator。

So under the y error， projection onto5 plus gets mapped to projection onto Psi minus。

Now notice there's something special about the case p equals three quarters。

 that's the case in which the error occurs with a total probability of three quarters。

 so in other words an X error， a y error and a Z all occur with probability one quarter and the case where nothing at all happens。

 also occurs with probability one quarter。So in that case。

 when we let our channel act on the first qubit and the identity on the second。

The maximally entangled input state， this projection on5 plus。

Becomes this equally weighted mixture of our four basis states， I get one quarter。

The pure state phi plus the pure pure state psi plus， the pure state Psi minus。

 the pure state phi minus。And remember， these are the orthoormal basis states or a choice of the orthonormal basis states for the two qubit system。

And so this is just the maximum mixed state for that four dimensional space。

 it's one quarter times the identity acting on the pair of qubits。

Now if you remember how our relative state method works。

 we can apply it here to see how the channel itself acts on a desired input state now remember I did a funny thing when I defined this relative state representation I didn't actually consider the input state to be5 plus but rather an unconventionally normalized state。

 just the 00 plus 11 without the1 over squared of two。

And so in this case where the error occurs with a total probability of three quarters that unconventionally normalized state actually gets mapped not to one quarter。

 the two qubit identity but rather one half times the two qubit identity and I did that because then we have a nice characterization。

 a nice formula for how the channel X on just a single qubit。

 if I want to know for an input pure state psi， what the channel does。

 what the relative state method tells us to do is to take this state。

 the output from the channel except for this funny normalization when the input is phi plus sub systemt and reference system and that in this case is just one half times the identity and then I take its expectation value in a state psi star。

Wwhich is just psi except with its coefficients and our particular01 basis complex conjugated。

 but because it's just the identity in psi star as a normalist state that's just one half the identity for the output qubit from the channel so what that's telling us is that in the case where the total error probability for the depolarizing channel is three quarters。

 any state you put in in particular this pure state psi is going to be mapped to the maximally mixed state to one half the identity and of course the same will be true for any mixed state because a mixed state is just mixture of pure states and the channel is linear。

So the depolarizing channel in that case with P equals three quarters is a special type of channel in effect。

 it throws the state away and it replaces it by a maximally mixed state by an essentially random state in our Hilbert space in that case we say it's completely depolarizing if you think about the Bpher picture。

Which we've talked about last time or maybe I guess it was the time before。

The the pure state lives on the B sphere itself。On the boundary of the block ball。

 the max mixed state lives right at the origin of that ball and what this channel does when peak equals three quarters is it takes any state in particular any pure state to the center of the ball and in other words it completely destroys the polarization of the qubit。

 and that's why I'm calling it completely depolarizing。Okay。

 but now that was just for the case where P is equal to three quarters。

 what about general values of P？Well， let me do the following thing。 We already saw how the。

Channel tensored identity acts on the maximally entangled state of our system and a reference system。

But now I'm going to add to the term we had before， which had。

Projection on to psi plus on psi minus and on phi minus I'm going to add to that projection on to phi plus and I want to do that because I know that's just the。

The identity operator。Acting on that two qubit system。

And but then I made a little mistake when I put projection onto5 plus here。

 so I have to subtract it away here， so where before we had one minus p times the pure state5 plus now that's going to be one minus4 p over three because I added p over three times projection onto5 plus over here and let's get my little face out of the way there we go。

So but now this is just the identity， the maximally mixed state is one quarter times the identity for the two qubit system。

 so let me factor out that one quarter。And so now the coefficient to the maximum mixed state here is4d P over 3。

So in the case where P is no larger than three quarters。

 we can think about our depolarizing channel in the following way。It's just as before I said， well。

 we either do nothing or reapply X or weapply y or reapply z each equal probably。

 but there's an equivalent way of describing what the channel does as we now see with probability 1 minus 4p over 3 nothing happens。

 and then with probability 4p over 3， we throw the state away and replace it by a maxly mixed state。

That's just another way of saying what's going on。Now what about the B sphere picture。

 you remember the B sphere， I just made a reference to it a minute ago。

 this is supposed to be a picture of the B sphere， it's a unit sphere。U。

You remember associated with the density operator？Of a qubit is a polarization vector。

We can write the density operator with no loss of generality for a qubit as one half the identity plus here I've written it as vector P dot vector sigma。

 that means p1 times x plus p2 times y plus p3。Times Z。All X， Y and Z are all traceless， by the way。

 so we can see that the trace is properly normalized here。 the trace of identity is2。

 so the trace of rh P here。Is one？And from the point of view that I just described where either we do nothing。

 so row of P is unchanged or with probability for p。Over three， we replace the state by the。

Maxally mixed state。So in the case where I replace it by the maximum state。

 I just get a number of times I the important thing is that when the。Arror occurred。Sorry。

 the case of no error when we didn't throw the state away。

 that occurs with probability 1 minus 4 p over3， so the effect of that is to rescale the polarization by the factor 1 minus 4 p over 3。

And you can think about it that way， even when P is larger than three quarters。

 although in that case you'll notice the polarization kind of gets turned inside out。

 when P is equal to three quarters， it syncs right to the origin of the block ball and when P is greater than three quarters it actually gets extended further to the other side。

 but anyway， if you want to think about how the depolarizing channel X on a qubit。

 it's helpful to visualize it in terms of the block sphere and what happens is that all the pure states which live on the unit sphere in three dimensions。

Get shrunk down to a smaller sphere， the polarization gets isotropically rescaled。

 the whole sphere deflates to it's still a sphere， but now a smaller sphere。嗯。Now you could ask。

 well， suppose I wanted to undo the effect of the depolarizing channel。

I would just have to blow the block sphere up again to reverse the deflation that occurred。

 But remember， we said that except in the case of a unitary map。

Completely positive maps can't be inverted by physical， completely positive maps。

 and you can see how that works here， if I want to undo the effect of the depolarizing channel。

 I want to inflate the sphere to a larger sphere so we can go back up to unit radius。

But if I rescale the polarization。By a factor larger than one。

 that can't be a physical map because it takes physical density operators。

 which had the length of the polarization vector。Less than one or equal to one。

 two unphysical states which have a polarization vector larger than one。

And those are not positive operators， okay？So we can't undo the depolarizing channel and it's kind of。

呃。Nice to have a geometrical way of thinking about that in this case， we know in general。

 there isn't a physical operation。That can undo the effect of decocoherence， undo maps。

 which are not unitary。All right， now I want to talk about another example。Of a。Cubbit channel。

And in this case， let's think about kind of a physical picture of what might be going on。

I want a very simplified model kind of stripped down to the essential features of the following physical situation。

There's。A little piece of dust。 It's floating around in intergalactic space。But it's quantum dust。

So it doesn't necessarily have a well defined position。

 it might be in a coherent superposition of different possible spatial positions。

And let's suppose there are two possible places it could be。

 and I'll label those two states by zero and one because I'm not very imaginative when it comes to labeling basis states of qubits and I call them zero and one in most cases。

 but in this case we're envisioning that zero and one correspond to two possible positions。

For the dust grain， which could be in some superposition of those two positions。

But the dust grain isn't perfectly isolated because there are some photons drifting around。

They're the 2。7 degree photons maybe that are left over from the big bang。

 those are everywhere even between galaxies。And every once in a while。

 a photon might encounter our grain of dust。And be scattered by it。

But the way the photon gets scattered。Depends on the position of the dust grain。

So the picture I would like to suggest is the initial state of this photon。

 which is incident on the dust grain， I'm going to call zero and then it scatters and it scatters into either one of two distinguishable states if the dust grain is in the position that I'm calling the state zero。

 then the photon gets scattered to a state one and if the photon encounters the dust grain in。

The state one， if it's in the position corresponding to what I'm calling state one of the qubit。

 then the photon scatters to some other state two。And I'm going to take zero，1。

 and two to all be distinguishable or orthogonal possible states of the photon。

But this process is a unitary process okay the everything's described quantum mechanically and what happens is that because of this scattering。

 the photon becomes correlated with the dust grain。

 the state of the photon will either be one or two corresponding to whether the dust grain is either in state zero or1 so the unitary process in which the photon interacts with the dust grain is going to create an entangled state。

Potentially of the dust grain and the photon。So we can describe that by a map。

 I'm calling it here an isometric map， that just means that it preserves inner products and I'm making kind of a distinction which is a bit pedantic。

 we've talked a lot about unitary maps but in this case I'm not going to worry about well I'm not going to keep trackgnoosis I could have。

Of the initial state of the photon and I'll just worry about if I have the initial state of the dust grain to be either zero or1 after the encounter of the photon。

 what is the joint state of the dust grain in the photon and because that's mapping one qubit to two qubits。

 it's not really unitary， but it's isometric meaning it preserves inner product。

 so it's something that physically makes sense。So in the case where the dust grain is。

In the state zero， after encountering the photon， the state of the photon。

 I'm using E to suggest environment A is our system， the dust grain。

 it sends some'm superposition of zero for dust grain， zero for photon。

because there hasn't been any scattering in the state of the photon didn't change in that case。

And zero for dust grain and one for photon and the coefficients I'm going to call the square root of 1 minus p and the square root of p。

 of course there's squares， I have to sum up to one because the state is so normalized。Well。

 if on the other hand， the state of the dust grain were one。

 then I'm going to suppose that again with the same amplitude as before the square root of 1 minus P。

 there is no scattering， the photon doesn't encounter the dust grain。

But in the case where there is scattering， now the photon is going to be scattered from the state zero to the state two。

And so in the case when the dust grain was in the state one， after the interaction with the photon。

 I have this state， the square root of1 minus p state one for dust grain zero for photon。

 that's the case where。No interaction occurred， there was no scattering。

Plus the square root of P1 for dust grain2 for photon。

 that's the case in which the photon got scattered into the state too into a state distinguishable from the initial state and also distinguishable from the state that it winds up in if the dust grain had been in state zero instead。

So now I can describe this in terms of cross operators。

 remember you can always imagine that we perform a measurement on the environment in this case I'm going to measure the photon or imagine measuring the photon。

In the zero， one， two basis and associated with the three outcomes。

The photon is in the state zero or1 or two。 there are three cross operators which act on the state of the dust grain。

In the case where the photon is in the state zero， that's the case in in which nothing happened to our qubit。

 so the cross operator is just the identity and it has inherited this square root of 1 minus p。

In the case where we measure the photon and find it in the state one。

 well that means we must be looking at this component of the state。

 so that couldn't have occurred if the dust grain had originally been in the state one。

 so what I actually have is a projection on the state zero of the dust grain and this square root of p becomes the normalization of my cross operator。

And the case where I measure the photon and the outcome is the state two that means that that's coming from here。

 so that means that the dust grain must have been in the state1。

 it gets projected onto the state one and again with this amplitude square root to P now nobody had to really measure the photon or detect the photon with some kind of detector we can just do the trace over the unobserved environment in this case the photon on any basis we want and it was convenient to do that tracing out using the012 basis and that's how I arrived at these three cross operators remember you always have the freedom to change the basis of that measurement and that corresponds to some unitary remixing of the cross operators。

Now， in fact。You can see。That the cross operators are not in this case。

 linearly independent because if I add together M1 and M2。

I guess something proportional to the identity。So this was a convenient choice for cross operators because I corresponded very directly to the way I was thinking about this fiscal process。

But it's not a minimal representation of the channel。

 we're using one more cross operator than we needed to because they're not really linearly independent or to say of another way。

 I can express all of the three cross operators M0 and1 and M2 as linear combinations of two operators。

 namely the identity。And the poly operatorator Z。Because， well， this is the identity。

 M0 is the identity， but also the identity plus z is the matrix 2000。

It has two only in the upper left zeros elsewhere， and identity minus E is the matrix which has a one on the lower right and the other elements equal to zero。

So I actually I wrote one here but it should be identity that's a little confusing maybe i'll fix that。

 but at any rate let's rewrite our channel。Um。By rewriting our cross operators in terms of identity and Z。

 So again， with probability 1 minus P， nothing happened。But then with。Probability P。

 I have a one quarter here because remember when I took one plus E that was actually twice this matrix so I divided by two and then I up wound up squaring that because I have an M1 on the right and the left。

 so I have P over four here。And then identity plus E row identity plus Z， that's the M1 term。

 and then for the M2 term now I'm writing my cross operator as a square root of P。

 which got squared here times one half identity minus E so multiplying this P over4。

 I have identity minus E。Row identity minus E。And now we can simplify this a little bit。

Because the terms here which have a Z on one side and the identity on the other。

 they're going to cancel because they occur with a plus sign and they occur with a minus sign here and so since those terms cancel all I wind up with are the identity row identity terms and there are two of those so the P over4 became a P over two and the zero z terms and because these two minus signs cancel those add together and they give me P over two0 z。

So if I combine together this row with this row， there's another way of describing the channel。

 which is a completely valid way of describing mathematically what it does。

 which is with probability P over two。An error occurs， namely a Z is applied to the state。

 and with probability 1 minus P over 2， nothing happens。So you see there's a difference。

 an interesting difference here。For this channel， which I'm calling the defphaing channel。

 which is that there's a special basis that it picks out， namely the  zero1 basis。

 that wasn't true for the depolarizing channel， it didn't really have any preferred basis and correspondingly we could see that it deflated the B spheree isotropphically。

 but here there's a preference for the polyopator Z or for its eigenbasis consisting of the state zero and1。

For the dust grain。Now let's go back to the original three cross operator representation because that's kind of convenient for seeing how a density operator of qubit is affected by this channel so I suppose there's some input density operator completely general。

 so I've just written it this way it's actually as you know a hermeian trace1 non negative operator and this notation doesn't show that explicitly but that's okay it just as entries row 00 and row 11 on the diagonal row 01 and row 10 off the diagonal and so if you look at what the what these operators do。

 when we square this guy in other words when we consider M0 row m0。

 that's just going to multiply the whole density operator by1 minus p both the diagonal and the off。

Diaagonal parts。But then the guy M1 then adds an entry which is P row zero zero because this is projecting out the zero component。

And M2 is projecting out the one component so that's going to give me a P row 11。

 so on the diagonal I wind up restoring the original entries when the channel X row00 and row 11 are not affected。

But the off diagonal terms are effective， they become smaller that's a kind of loss of coherence I'll try to make it a little clearer what that makes what that means in the next slide or two but anyway again this is reflecting the special basis that our defacing channel picks out we're representing the density operator in the zero1 basis and in that basis the off diagonal terms are suppressed by the channel the on diagonal terms are not affected and of course。

The trace is preserved。No。We might think about what's going on this way。That there are many photons。

And many photons are incident。On。Our dust grain。And for each one。

It's highly probable that there's no scattering at all。

So the term in which nothing happens dominates in each scattering event。

 but there are many scattering events， so over time the density operator is affected by the interaction with the photon。

So let me think about that this way， there's number P。

 which we saw we could think of as the probability that scattering occurred when the photon encounters the dust grain。

嗯。But let's because there are many。Photons encountering one after another of the dust grain。

 let's think about that as a probability per unit time。

Or suppose there's a very small time interval over which we're monitoring the dust grain。

 which I've called Delta t。And that the probability of a scattering event of the photon being scattered into a state which is orthogonal to its initial state。

嗯。Is proportional to the time for small times， so it's just going to be some number times gamma t P is a dimensionless number。

 so gamma has the dimensions of one over time。I'm calling gamma that probability of a scattering event of an error per unit time。

 and I'm imagining that deelta t is small enough that that probability is a small number。

But now suppose I consider many such tiny time integrals。Interval。

 so the total time that elapses is n times delta t where n is a large integer。

 Then this channel is actually applied many times in succession Every time a photon comes by。

 it comes by each time interval delta t， let's say so in time n delta T。

 the channel has been applied n times and each time it's applied the off diagonal terms in the density operator get hit again by another factor of one minus p。

 So after n application to the channel， the off diagonal terms have been suppressed by one minus p to the n power。

And now P remember is this gamma delta t， the small probability of scattering and each scattering event。

 and now I'll write that in terms of the total time。

 it's gamma times the total time that's elapsed divided by n the number of small time intervals and that got raised to the n power。

And then if I consider letting。And get large。Then this just approaches an exponential E to the minus gamma T。

 So in other words。As a function of time， the off diagonal terms in the density operator decay exponentially with time。

Or here's another way of saying what I just said when we apply this。Channel and times and succession。

In the limit I just considered。The on diagonal terms are not affected。

 but the off diagonal terms decay by a multiplicative factor， which is e to the minus gamut T。

So if gamma t gets to be a large number， in other words。

 at the time gets large compared to one over gamma， then the off diagonal terms become negligible。

And if we started out with some coherent superposition of our qubit。

 if we imagine the dust grain was in a。Superposition of two possible positions with。Coefics， A and B。

Then after a sufficiently long time compared to the so called coherence time， one over gamma。

 that density operator has decayed。To a mixture， it has some probability absolute value of a squared of being in the state zero。

 some probability absolute value of B squared of being in the state one and there any possibility of。

Interference between the0 and the one has been completely destroyed by this process in which the photons scatter off the dust grain。

 So again， we see that there's a preferred basis。For this process that the dust grain deheres in the 01 basis as a result of the coupling to the photon that we describe。

 So that's what I mean by the basis dependence， you know， I say， oh， well。

 this coherent superposition。Is going to decay to a mixture。But you know。

 how do I know that it's going to be a mixture of zero and one， why isn't it a mixture of。

0 plus one and0 minus one okay well it's because of the way the photon is assumed to interact with the dust grain and in particular we've sort of built in some locality assumption that the state of the photon after the scattering is going to be different if the dust grain is in the position on the right than it would be。

The position on the left， because of the locality of the nature of the interactions between the photon and the dust grain。

 you know， you could have asked a similar question about that poor cat of Schrodinger's。

 which is in a linear combination。Of。Alive and dead。And then it decocohers。

 we like to say very quickly， it's either definitely alive or definitely dead。

 it behaves like a mixture of alive and dead instead of a coherent superposition that's because of a similar process。

 it's because the cat interacts with its environment just like this dust grained interacted with the photon and for a similar reason there's a preferred basis it doesn't decocoherre in the basis alive plus dead and alive minus dead it decohers in the basis alive and dead。

 because of the nature of the interactions of the environment with the system in this case the photon。

Being scattered off the dust grain。Now we can also visualize this process。嗯。From。

The Bpher point of view。 So now let's go back to the other way of describing the channel。

 which is that with probability P over2。嗯。The poly operatorator Z is applied to the qubit and with probability 1 minus P over 2。

 nothing happens。 So since that Z commutes with Z， it commutes with itself， of course。

 it doesn't affect the third component。 the Z component of the polarization of the qubit。

 that just stays the same。But X anti commutes with Z and y anticommutes with C。 So in other words。

 zxz is equal to minus x z Yz is equal to minus y。 so if I ask what happens to the other components of the polarization。

The X and Y components， again， with probability 1 minus P over 2， nothing happens。

 but with probability P over 2， that component flips。X goes to Z x Z。

 and so you put together those two contributions and for either the x or y polarization or the one or two component of the polarization vector it gets。

Depressed by the multiplicative factor1 minus p。So visually what's happening is that along the Z direction。

 the polarization is unaffected， but in the X and y directions。

 it's deflating and so it becomes a pro a prolate ellipoid kind of a football shape over time and as the time gets longer and longer。

 if I think of you know the channel that I just described in which the defphaasing event occurs over and over again。

It will shrink to a narrower and narrower ellipoid eventually asymptically。

Occuping the Z axis where the one in two components of the polarization have been completely eliminated。

 but the Z component is unaffected。Now you might wonder well what kind of channel would cause the B sphere to evolve not to this prolate ellipsoid。

 but instead an oblate ellipoid of a pancake shape and the answer is that doesn't happen because that's not really a physical。

Completely positive channel。If you think about it， well。In some appropriate basis。

 what that would mean is that P2 is shrinking， but P1 and P3 are not。

But that map is really the transpo map， Okay， that we talked about before， because remember that。

The poly operatorator Z and the poly matrixtrix X are both symmetric matrices。

 while y is an anti symmetric matrix， so under the transpose。X and Z are unaffected。

 but y goes to minus y so that map that gives rise to a pancake instead of a football。

Is one in which a transposition occurs with some non zero probability and that's not completely positive。

 So that's the no pancake theorem。 You don't see the block sphere shrink to a pancake。

Looccalized at the equator， although it can shrink。To a football localized on an axis。Now。

This type of defphaing is seen in many different physical systems。

And one can in the laboratory measure this to phing rate gamma， the observed the exponential decay。

Of the polarization。嗯。That example might be prepare。A state of an electron spin。

 maybe it's a superposition of spin up and spin down or an atom in a optical trap。

 which is a superposition of the ground state in the excited state。

Where the two states that are being superposed have different values of the energy。

 in the case the electron spin， that might be because it has a magnetic moment and it's in a magnetic field so spin up and spin down。

Have different values of the energy。So in the basis in which it's diagonal， the Hamiltonian has。

2 distinct eigenvalues by fixing the zero of energy。 I can make one of those eigenvalues0。

 So the Hamiltonian， I don't usually write H bars， but I guess here I decided I would。

But usually I've said H party equal to one， which I did without comment。

Because it's really not important to us for the most part， in this course。

 what the value of H bar is。So let's say the state zero of our qubit has zero energy。

 but the state one is an excited state with some positive energy omega。

 then if I don't worry about defphaing if there's no decoherence。

 I'm just solving the Schchrodinger equation。Then the excited state in a time t picks up the phase e to the minus I omega t the ground state is unaffected by the time evolution。

 and so if I prepare an initial state which is a uniform superposition of 0 and1 it will then oscillate。

And it will process。If you like around an axis， it willll move around in a circle in the space span by 0 and1。

But if we include the defphaing as well。Then there will be exponential decay of the off diagonal terms in this basis assuming as is often the case。

That defphaasing is occurring in the energy eigen state basis。 So let's say it's an electron。

Which is the superposition of spin up and spin down。

 the environment might be able to detect the difference between an electron with spin pointing up。

Along the magnetic field axis and the electron the spin pointing down because there are other spins in the environment。

 maybe other electrons or nuclear spins。Which interact with the electron spins because all the spins have magnetic moments and so decoherence will occur in the energy eigenstate basis。

 and so the evolved density operator will have the behavior I've shown here。

 there will be an oscillating off diagonal factor， but it will be suppressed by this exponential decay term when t gets large compared to one over gamma。

 So if I prepare an initial state。And then I let it evolve for a while。

 and then I measure in a basis， which is。I。The0 plus1 and0 minus one basis so I started out at time zero here with0 plus one up to normalization I let some time pass and then I measure to see whether it's0 plus one or0 minus1 that it go back to where it was originally or did we wind up finding the orthogonal state then the probability of getting the outcome plus that's just the matrix element in the state plus of row of t and remember I'm talking about plus being one over square root of two0 plus1 So what this does is it just gives me one half from squaring that one over the square root of two。

Times the sum of the four entries in this two by two density operator。And of course。

 that means I get one plus1 plus e to the minus gamma t e to the i omega t。

 e to the minus gamma t e to the minus i omega T， adding together the e to the i omega t and e to the minus i omega t gives me twice the cosine。

So we wind up with up to the normalization factor1 plus the exponential of k times the cosine of omega t。

So as time passes， the probability of getting the outcome plus will oscillate in time。

 but it will also be modulated by an exponential。Deay factor。

And so I could measure that the way I would do it is I'd repeat the experiment many times of preparing the initial state1 of 20 plus one。

 waiting for some time t and then measuring。And I would do that for many different choices of the time and for each time I would perform the experiment many times so I could estimate an expectation value by averaging the results and in that way I could get a plot like this one。

Where I can see the probability of getting the outcome plus。As a function of time， it oscillates。

But it also is governed by。An exponential decay envelope so from that data I can measure both omega。

 which determines the period。Of the oscillation and also the defacing rate gamma from the exponential decay。

Now I want to talk about another example of a qubit channel。

 I'm going to call this one amplitude damping。Another name for is spontaneous decay。

Let's imagine we're talking about an atom in this case， if that atom was in an excited state。

 it has some amplitude for emitting a photon and decaying to a lower energy state。

 so let's just consider an atom which has just two levels， keep things simple。

 so it's a qubit we'll call zero of the ground state， one， the excited state。

 the higher energy state， so the process by which the qubbit can change is one in which we start out in the excited state。

 a photon is emitted and a transition is made to the ground state。

So in the language we've been using， our atom is interacting with an environment。

 the environment is the electromagnetic field。😊，And to begin with。

 it's just in the vacuum that means there are no photons around at all。

But after some time there might be a transition from the excited state to the ground state from one to zero and when that happens。

 the state of the electromagnetic field changes， now there's a photon there in principle I could detect that photon if I had a good high efficiency photo detector。

So again， I should think of this as a unitary process。

 a unitary interaction between our two level atom， a qubit， and its environment。

 the electromagnetic field and。To simplify things to what's essential。

 I'll consider the electromagnetic field to also be a qubit。 It has just two states。 the vacuum。

 there's no photon and the one photon state in which a photon has。Has been oted。

 those two states are perfectly distinguishable， they're orthogonal states of the electromagnetic field。

 likewise， the ground and excited state of the atom are the basis states for qubit ortho the normalmal states。

So I can think of the process this way， if the atom is in the state zero。

 the ground state and nothing's ever going to happen。

 so it stays in the ground state and the photon never appears photon。

 the electromagnetic field stays in the vacuum， the no photon state。

But if we start out with no photon in the electromagnetic field and the atom in the excited state。

 then there is some amplitude for nothing to happen。

 so the atom is still in the excited state and there's still no photon。

 but it's possible for the excited state to decay to the ground state in which case the atom makes the transition from the state1 to the state zero and the state of the environment changes a photon appear。

 so the electromagnetic field is now in a state orthogonal to the initial state zero。So as usual。

 I can get cross operators by imagining measuring the environment in some basis and asking what the conditional state is of the atom。

For the different possible measurement outcomes， so in this case there two possibilities。

 if I were to measure the environment， either there's no photon or there's one photon。

When there's no photon， that means that if we were in the state  zero at the atom。

 then nothing happened。 But if we were in the state  one， it got suppressed by the factor。U。我是。

What happened here。It got suppressed by the factor。Squa root of 1 minus p。

 that's the square root of 1 minus P here。And if I get the outcome one when I measure the environment。

 if I see a photon is there， then I know what must have happened was that the atom was initially in the excited state and it wound up in the ground state。

 and that's this cross operator， which just describes a transition from the state one to the state zero。

And it involves the amplitude square root of P， which came from here。

So let's look at what this channel does， here's its operator sum representation。

 these were the two cross operators。In the case where。The cross operator is M0。

 the M M0 adjoint term。Is going to suppress the 11 component of the density operator by the square of this square root of 1 minus p。

 So there's a 1 minus P here。But the off diagonal terms get hit by just one of these square root of 1 minus p factors。

 so they both get suppressed by the square root of 1 minus p and the zero zero component isn't affected。

 and then there's an additional contribution from the case where the photon is emitted。

That's the cross operator M1 and what that does is it projects out the atom being in the state one to begin with because otherwise it couldn't have decayed but then the state one goes to the state zero。

 so the final state of in the case where we detect the photon。Has oh， look。

 this should have been row 0 zero。No， that's not right。

 I'm sorry no it's row 11 what had originally been the population or the probability of being in the one state。

 which is row 11， that becomes this additional probability after the photon is detected。

Of being in the ground state， which is proportional to row 11 and also to P the probability of the decay。

So here I've just added those two terms together again。

 augmenting the row0 zero up here in the upper left。

Entry the density operator with the additional term P Pro 11。

And so what we can see is that this spontaneous decay process。

What I'm calling amplitude damping for some reason。

Has an effect on both the on diagonal and the off diagonal entries。And。

There's a relationship between what happens off the diagonal and on the diagonal， in particular。

 the probability of being in the excited state gets suppressed by 1 minus p and the off diagonal terms get suppressed by the of factor square root of 1 minus p。

So now let's， as we did before， when we talk about defphaasing。Consider。Watching the atom。

Or considering how its state changes over an extended period of time。

So let's again imagine there are many consecutive time intervals。

Each of which is described by this channel， which I've just rewritten here。

 it's what we just saw a minute ago。And so the probability of the spontaneous decay occurring。

If the state is in the excited state。It has some rate a gamma per unit time and the probability in a time interval delta t is gamma times delta t。

And now， if we wait altogether， same story that I told you a minute ago about defacing for n such time intervals。

 So the total time is n times Delta T， then the。1 minus P。

Suppressing the 11 component of the density operator becomes 1 minus P to the n。But P。

 remember is this gamma delta t， I can also write that as gamma t over n if t is equal to n delta t。

 they're altogether n intervals each of with delta t in time that gets raised to the n of power。

 and then if I consider the limit in which n gets large。

 if you like in which I consider that tiny time interval delta t to be arbitrarily small。

It's an exponential E to the minus gamut T。And that same remark I just made。

In reference to the 11 component of the density operator applies just as well to the off diagonal ones。

 except now we get a square root of one minus p raised to the n power。

 that's just the square root of the suppression factor that we have for the 11 component。

So when you put it all together。If we start out with an initial density operator with entries row 0。

0， row 01， row 10 and row 11， after times t， the  one1 component has been suppressed by the exponential factor。

 e to the minus gamma T。The off diagonal component， 01 and10。

 both suppressed by e to the minus gamma t over2。And well。

 then you can see what happens to the0 zero component just by knowing that the trace has to be preserved。

 so the trace of this matrix has got to be row 00 plus row 11 because that's what it was to begin with。

 and it tells me that this entry， it better be row00 plus1 minus e to the minus gamma t times row 11。

So that is what happens to our atom。As。We wait a long time for it to spontaneously decay。

So there are a couple of things that are interesting to point out。So first of all。

 there's a relationship as we previously noted， between what happens to the 11 component。

 describing the probability of being in the excited state。And the off diagonal components。

And the standard language used in experimental physics is that the characteristic decay time for the excited population is called the T1 time。

 so we call this exponential factor to the minus t over capital t1 capital T1 thats spontaneous decay lifetime is just one over gamma。

But there's also defphaasing， like in our defphaasing channel。

 we discussed earlier suppressing the off diagonal terms。

 and that's just the square root of what we had in the。1，1 component。

And the standard terminology for the characteristic decay time for the off diagonal components of the density operator is T2。

 so I can write this as e to the minus t over capital T2 capital T2 is just twice t1 so in the case of spontaneous decay。

The defphaasing rate is simply related to the lifetime。

 the spontaneous decay lifetime of the excited state。See， did I have another thing here， Yeah， okay。

 coming into that。Um， and sometimes then， of course， when we talked about defphaasing。

 like when I imagined I had that electron spin in a superposition of zero and one。

 there wasn't any spontaneous decay， but there was defphaasing。

That was occurring because somehow the environment is catching on to whether the spin was up or down so in many cases。

 that a phasing time is a much shorter time than the spontaneous decay lifetime it's easier for the environment to find out。

Whether the state is zero and or one than it is to flip it from。1，2，0， but that's not the case here。

 not in the case of pure spontaneous decay， and in fact。

 in that case we say that the T2 is t1 limited and in fact。

 it's a time which is twice as long as a spontaneous decay lifetime T2 is equal to2 T1。

So now all this was assuming that nobody's detecting the photon。

 we traced out the state of the photon， but it's possible to affect photons。

 You can actually do an experiment if you're a skilled。吓。Experimentalists。

In which you surround the atom。With photon detectors。 so that when a photon is emitted， you know。

 it's been emitted。 You can actually detect it。So of course， if you detect a photon。

 you know what happened， it means the atom was in its excited state， made a transition。

 it's now in its ground state， and that's why we were able to get a photon。

But what if no photon is detected， you wait and you wait and you wait， no photon has been detected。

 you start to get suspicious。Well， in order for no photon to be detected after this long time。

 it must be that the。Adam is actually in its ground state all along， okay。

 so if we let's see if we can turn that intuition into equations。

And what we expect to find now is that。Even though no photon is emitted。

 the way we describe the quantum state。The quantum state vector or the density operator。

Is going to be changing with time， even though so to speak。

 nothing happened because as time goes by and we don't see a photon。

The way we describe the quantum state has to change。

So let's imagine we start out with some initial state。Of the。Aam。

 it's a superposition of the ground state0 in the excited state  one。The photon field。

 the electromagnetic field is in its vacuum， there are no photons around。

And then this is the way we argued the state would evolve in a short time in which the probability of a spontaneous decay of well。

 actually， whether it's small or large， we would describe it the same way。

 though I would like to consider the case in which it's small。Um。

 that is that there's the case where the at was excited and it didn't decay。

And that has an amplitude square root of 1 minus p times the original amplitude of being in the excited state of the atom。

And there's also an amplitude square root to P for the transition from， oh。

 I think I lost a beic here， didn't I？Yeah， I should have a beta here。H。

Because I'm saying that the beta 10 made a transition。To。Beta 01 because of the spontaneous decay。

 which made the atom go from the state one to the state zero while the environment went from no photon。

To one photon。And。But now， like we did before， we can imagine that many such time intervals pass。

And now there are a lot of different possibilities。

 and therefore there will be a lot of different crafts operators。

Because in each of these little time intervals， I either detect a photon or a don't。

 I've got a photon detector。 So when that photon appears， I know it every time。

The unitary interaction occurs between the atom and the electroag field for some small amount of time。

 I imagine I'm measuring。Projecting on to no photon or one photon。

 I'm looking to see if the photon is there or not。 We weren't doing that before。

 We were supposing that the environment is unobserved。 Now。

 I'm going to imagine we're really making the measurement。

 and I get some conditional state condition on whether I see a photon or don't see a photon。

And there are altogether together n possible time intervals。In each one of those。

 I could have either seen a photon or not， of course， once you see a photon， there's just one atom。

 you're not going to see another one。Then now the atom's in its' ground state and it's going to stay there。

But you could have seen a photon in the first time window or the second or the third and so on up to the last。

 the1 time window， or you might have never seen a photon at all。

 You might have after the many time intervals。 and you never saw a photon。

So the cross operator corresponding to that case in which you never see a photon。Is。Well。

 let's look here。 That means that you always got the state 0 when you measured the electromagnetic field each time you did so。

 the amplitude for the state one of the atom got suppressed by another factor of the square root of one minus B。

 and that happened altogether n times if you never saw a photon。

But what if you finally saw a photon in the case step？Then it was getting suppressed by 1 minus p。

 this 11 component。Was getting orm sorry about the state one for the atom was suppressed by the factor。

A square root of1 minus P altogether， K minus1 times because you saw no photon。

 the first K minus1 times。 but then you finally did。 So when you did。

 you picked up this additional amplitude of the square root of P。And in addition。

 the state made a transition from the excited state to the ground state。

 from the state one of the atom to the state zero of the atom。

So the cross operator for detecting the photon in the k step is this one。

 it describes a transition of the atom from the state1 to the state zero， but with this amplitude。

 a factor for not seeing the photon the first K minus1 times and a factor for finally seeing it。

Hit the case time。And so again， if we consider。Case of many consecutive time intervals。

 and we say there's some probability per unit time of spontaneous decay。

Then what happens when the no photon ks？That cross operator is applied to the initial state。

If after a total time t， we never saw a photon， well that's just this m0。

 but now as we've already discussed a few times， I can think of the square root of 1 minus p over n。

As going to e to the minus gamma t over  two， where gamma is the probability per unit time that the excited state of the atom decays to the ground state。

So when we don't see a photon， the amplitude for having the excited state of the。

Of the atom is getting smaller and smaller and smaller as time goes by。So really。

 if I wait a long time， so gamma T is a large number and E to the minus gamma T over 2 is incredibly small。

 I'm， in effect doing an orthogonal measurement， although it's a destructive one。

I don't wind up with the original undamd state， if it was。And I can say， in fact。

 I always wind up with the state zero at asymptotically large times。But there are two possibilities。

 either a photon was detected， and that can only be true if the atom was in the state one or no photon was ever detected。

 And that can only be true when gaut T is large compared to one。If the atom was in the state zero。

 so in effect， I'm。With probability absolute value of alpha squared getting the outcome。

No photon and with probability。I absolutely value beta squared getting the outcome of photon was emitted。

 and it's the same thing as an orthogonal projection on the basis states of the atom。

 the ground state and the excited state。All right， so there's one more thing I want to discuss。

Which is。Now I'm going beyond Cbit channels， I'm going back to general discussion。

What's the way in general， which we should describe how？Density operators evolve with time。

I've given you some examples。In the case of defphaing and spontaneous decay of how to think about that。

 but whats what's the general framework？Now we know in the case of a closed quantum system。

 the evolution of quantum state is unitary， it's determined。By。The Schchrodinger equation。

 or if I consider an infinitesimal time interval。When the time advances from T to T plus dt。

Then the state at time T gets multiplied by this operator。

 which up to terms which are of ordered Dt squared。

 which I'm neglecting is a unitary operator it's just the identity minus IHDT no H bar here I got rid of H bar like I usually do。

And so what's the corresponding equation for an open system。

 How do density operators change with time。 Well， in general， it's kind of a complicated story。

 but we can write down。General form for the equation that describes。

The evolution of a density operator with time in the case where the time evolution is Markovviian。

I'll explain what I mean by that in a second， well。

 I guess I'm explaining what I mean by it right now what Marovbian means。Is that。

The density operator in this case， at time T plus Tt is determined by the density operator at time T。

 you don't need any additional information to know how the density operator is going to evolve in the next microsecond。

 it's enough to know what the density operator is at time zero to know what it's going to be at time zero plus。

One microsecond when we say non microovviian evolution。

 what we mean by that is that what's going to happen between time zero and time zero plus one microsecond depends on more information than the density operator at time zero。

 I also have to know what the density operator was at time minus one microsecond or minus two microseconds and so on。

It's not enough to know the instantaneous state to know how it's going to evolve in the next instant and that type of non-markovvian evolution actually is quite common in open quantum systems which you probably shouldn't be surprised by because after all how do we think about open quantum systems there's a system and there's an environment we don't see the environment。

 there's a unitary interaction occurring on the system in the environment so even think of some information as leaking to the environment from the system。

 but that information might come back again。All right， are the unitary might and you know。

 acting jointly on the system and the environment。Myight。

Potentially undo the initial unitary or partially undo it。In that case。

 it wouldn't be enough to know the state of the system right now to know what's going to happen at right now plus one microsecond。

 because information which used to be in the system。

 has gone to the environment and might come back again。But when I say the evolution is Markovian。

 I'm taking it for granted that when the information goes away， it never comes back again。

 you can think of the environment as an entity that forgets information so quickly that once information goes to the environment I'm never going to see it again so somehow it gets all mixed up in the many degrees of freedom of the environment and it's very unlikely to ever return to the system and that means Markovvian time evolution is going to be a very good approximation so what it means is。

That in each instant time， I can imagine that there's no correlation between the system and the environment。

 They're not entangled at all。 and then I can describe what happens from time T to time T plus T T。

As a completely positive map because that's what we've always been talking about。

 the completely positive maps occur if the system and the environment are initially uncorrelated。

 a unitary occurs which entangles them， then we trace out the environment。

But if we didn't trace out the environment， in other words， if at time zero。

 we still have an entangled state of the system and the environment。

 then we wouldn't necessarily be able to describe the map as a completely positive map。

Because I would need more information about exactly the nature of the entanglement between the system and the environment。

And so the whole idea of Markovviian evolution， which is a good approximation in some cases， like。

 for example， and for the case of atoms interacting with the electromagnetic field。

The environment does' forget very quickly as far as the atom is concerned， in most cases。

 that a photon has already been emitted。And that means we can think of the environment as being refreshed in each instant of time。

And use our notion of a completely positive map to describe the evolution from time T to time t plus Dt。

And that's what this equation is saying， it's saying the evolution is Markovbian。

That to get the density operator at time T plus Dt。

You consider some completely positive map acting on the density operator at time T。

And being a completely positive man， it has some。Operator sum representation like shown here。

And since the time has increased by just the amount Dt， the density operator。

 which is the output from this map， will be the additional， sorry。

 the initial density operator plus some initial additional increment， which is going to be order Dt。

Now， as usual， we can think about this channel by imagining。😊，And。

Recalling the discussion that we just had of the atom undergoing spontaneous decay that somebody measures the environment。

 that's just a convenience and it's not really that somebody is necessarily measuring the environment that just provides us with the basis in which we can。

Generate an operator some representation。Or imagine there's some initial state of the environment。

And there's some amplitude for that state of the environment to be unchanged。

And then there's an amplitude for various transitions that could occur of the environment。

 let's say it's initially in the state zero， it could go to the state one or two or three and so on。

 and for each one of those mutually orthogonal perfectly distinguishable states of the environment there will be some cross operator。

So I have one cross operator， which is corresponding to the case where nothing is happening。

That I'm calling m sub zero and it's the identity plus something which is a order Dt because of course。

 when Dt goes to zero nothing happens， a row of t plus dt in that case is equal to row of t。

But then there's some correction of order DT， and I with no loss of generality。

 Ive written this coefficient as a sum of a Hermeian operator and an anti Hermeian operator。

 H and K are both hermeian。But when I multiply by minus I， that makes this term anti hermeian。

 and this one is hermeian and I can take any operator and divide it into its hermeian and anti hermeian part。

 and that's all that I've done there。But then for each one of the jumps of the environment to another state。

 there's going to be some corresponding operator， I'll call it a jump operator acting on the system like when the atom underwent。

Spontaneous decay。But I'm going to scale these in a funny way。

 I'm going to put a square root of Dt in all the nontrivial jumps where the index a is not equal to 0。

 And that's to make sure that all the jumps occur with some probability that scales。

With the time increment linearly in DT so I can think of the jumps as occurring with some probability per unit time。

 just as we discussed in the case of qubit to phasing。And cubit spontaneous decay。

So here it is again， what the master equation。Looks like。

And here's our expression for the jump operators Now there's one more thing that we should note。

 which is。We want this to be trace preserving， we're considering the case in which we don't。

Observe the environment。We have Marovviian evolution to interaction with an unobserved environment。

So our operator some representation has to obey the usual。

Normalization requirements so that the trace of row of t plus dt will be equal to the trace of row of T。

 we don't want the trace to change with time。So that means the identity is equal to this sum of MA ajoint MA。

When I take。M0， adjoint M0。I am。Get a term which is i plus Dt times 2 k plus something order higher order in Dt。

 which I'm not going to keep track of Dt is infinitesimal order Dt squared is negligible。

I want to find the。Terms which are a linear order in DT。

And those I want to set equal to zero so that thy normalization condition will be satisfied。Now。

 when you take M0 a joint M0。The adjoint is going to change the sine of minus IH to Ih it's not going to affect k because k is hermeian and H is hermian and so there's a cancellation between the IH and the minus IH so the hs go away that just corresponds to the fact that to order DT if there were no k。

I minus IH DT would be unitary， and so if it's unitary， M0 a joint M0 is equal to the identity。

But there isn't any sine flip for k because it's hermeian。

 so what I get to order Dt from M0 adjot M0 is i plus Dt times 2 k。

But then I also have the contributions from all the jump operators。

 all the MAA joints MA when a is not equal to zero。

And each one of those is going to be linear order in DT。

I arrange that by putting the square root of Dt here。And then I will have LA ajoint LA。

Times Dt is what MA ajoint MA is equal to where LA is this jump operator。

And so since this normalization condition has to be satisfied up to order Dt。

Because I don't want the trace to be changing with time。

 I can express k in terms of the jump operators and that's what I did here。

 this expression in parentheses has to be0， that means k is equal to minus1 half times the sum of LA a joint LA summed overall the jump operators。

So now I can write down the evolution law， the Marovian evolution。

As a first order differential equation in time， that is I can take the difference between row of t plus dt and row of t and divide by Dt that's the first time derivative。

 I've denoted it row dot here and the equation says the row dot is equal to some linear operator acting on row。

 which is sometimes called thelin beladian。And what's in there well。We have。诶。Contribution from。M0。

Which is going to。Produce a commutator。Of the Hamiltonian with the density operator row。

Because when we have M0 in front of row and M0 adjoint after row。

I get a minus IH row from M0 times a row in order DT。But I also get a row。

IH times Dt from the row M0 adjoint term and all the other terms are higher order in Dt。

 so that just gives me a commutator of the Hamiltonian with the density operator with the coefficient minus I and that's just the Schrodinger equation for a density operator that would be all I would have in the case of time evolution governed by the Hamiltonian H unitary time evolution。

And the rest of the terms describe the possible decoherence mechanisms the jumps that could occur。

And I have， as you can see， absorbed the probability of a jump into the normalization of these jump operators。

So the probability of the jump corresponding to L1， for example。

 would be the trace of row times LA a joint LA， that would be the probability of a jump of type A。

For each j per。You the L1 jump， the L2 jump and so on。

 so this describes with the appropriately scaled probability， what happens when a jump occurs。

And these other terms， well， we can see why they are there， they are the terms coming from the K。

In M0， in the M0。嗯。Row M0 adjoint where I've used our expression for K in terms of the jump operators。

嗯。And so in other words， I have。A。K times a row and I have a row times k here。

And then I've substituted for K， this expression in terms of the jump operators。

 and that is the general form of the master equation， which describes the Markovian evolution。

Of a density operator。 sometimes it's called the Lndblad master equation。As you can see。

 it has the property of preserving the trace by design， in fact。What should happen。

Is that if the trace isn't changing with time， then the。Time derivative of the trace should be zero。

 which is the same thing as the trace to the time derivative。

So the trace of the left hand side of this equation is zero。

 the trace of the right hand side better be zero。And indeed。

 that's the case here I have H rh minus rh H and because of the cyclicity of the trace。

The trace of rh H is equal to the trace of。H4O and so those two terms cancel in the trace。

And then if I take the trace of each one of these terms for each value of a， again。

 because the trace is cyclic， I can take LA adjoint over to the lefthand side here。

 I can take this LA adjoint LA over to the lefthand side and so I have and when I take the trace。

 it's the trace of LA adjoint LA row， then minus LA adjoint LA row from adding up these two terms and using thecyclity of the trace。

 we've also seen by construction and that's how we arrived at this master equation。That。

The time evolution from time T to T plus dt。Is a completely positive map。

 we enforce that by writing it in the form。Of a。Operator some representation and as we discussed in detail last time。

 that's really the most general type of completely positive map。

 completely positive maps always have operator some representations。

 and that's really all we assumed to construct。This general form。Now。

 as we also know and discussed last time。A channel and if it's not a unitary channel。

 any channel that describes decoherence。Can be expressed in terms of cross operators in lots of different ways。

In view of our isomorphism between states and channels。

 that's just the channel version of the statement。That a mixed density operator can be expressed as an ensemble of pure states in lots of different ways。

 we talked about that last time。So the same time evolution can be exchanged the jump operators。

 I can write， I can trade in these jump operators for others。

 which are related to the original jump operators by some unitary matrix just like when we consider two different ensemble representations of the same density operator according to the HJW theorem。

 there's some unitary matrix that describes how the original ensemble is related to。The new ensemble。

And I can do that for the jump operators in particular。

 so taking the same density operator and expressing it in terms of a different set of jump operators。

 sometimes let's call a different way of unraveling the master equation and sometimes it can be handy to make use of that freedom to make master equations easier to solve。

As。It's generally the case when we consider the different choices of cross operators to describe the same channel。

 you can think of that as arising from measuring the environment in different ways so the different unravelings correspond to monitoring the environment in different ways measuring the environment in different bases and therefore describing the jumps in terms of different jump operators so there's a lot more one could say about the master equation there's a little more in the notes about it than i'm going to do in class we also have。

Some discussion in the notes about the non Markovviian case。

 just so you don't think that Markovian evolution is the only thing that can happen in the lab。

 that's not really the case at all。So that's it that's the end of our four lectures on open systems I think we've covered the essential things about open systems that you should know for this course and also for your general education and edification which means we're ready to move on to a new topic I've actually got a little ahead of myself This is the end of the fifth lecture and we've gotten to the end of the material that I anticipated would be covered in the first six lectures probably that's happening because i'm presenting the material using slides more quickly than I would if I were writing things on the Blackboard I guess that was inevitable I've tried not to go too fast and sometimes。

Maybe it seems like I'm being a little long winded as a result。

But I probably have gone a little faster than。The ideal pace。

 but you know you have the advantage of being able to slow me down or speed me up or listen to me again thanks to their lectures being recorded so hopefully things are working out。

And so that's going to be it for now。Next time we're going to start talking about quantum entanglement in more depth than in particular。

What is it about quantum correlations， about quantum entanglement。

 which is really fundamentally different from correlations that we have in classical systems that will lead us into the notion of bellinequalities and ways of testing quantum correlations to see that they can't be prescribed classically。

 though that's a fun topic。And' we'll get into that next time， but in the meantime。

 I hope youre you're enjoying life and staying healthy。And I'll be seeing you next time。



![](img/e660e8108e14ff1c61621616065966a7_2.png)

ok。搜爱。Be well and carry on。 Bye bye。