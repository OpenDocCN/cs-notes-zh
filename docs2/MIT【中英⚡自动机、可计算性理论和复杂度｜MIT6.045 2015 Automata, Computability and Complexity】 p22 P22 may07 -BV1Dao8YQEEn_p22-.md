# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p22 P22 may07 -BV1Dao8YQEEn_p22-

。Okay，All right， few things so yeah piece at six the last one is due tomorrow but for the quantum problems。

 you know you can turn them in by Monday， it's fine because the online course evaluations are available now so it's very helpful if you can go online give your feedback about the course。

 you know what we did what we did rolling know I'll give another reminder about it。

 we will schedule a review session for the final exam at some point next week and we'll also put out practice materials just like we did for the midterm。

Okay。No， so last time Robin finished telling you about cryptography。

 so he told you about the amazing concept of zero knowledge proof that lets you prove to someone that that something is true without revealing anything about why it's true。

 so you I hope that I haven't been doing that in this course too much but there are lecturers who are known to provide zero knowledge proofs but。

But you know， but it's extremely useful for cryptography。

 one of the things it's useful for is you know letting the different participants in a protocol prove to each other that they are carrying out the protocol correctly okay and yet without revealing the secret information that you would think that they would have to reveal in order to prove that okay and so you know that has an immediate application。

 for example， to this dating protocol that you saw， you know。

 has applications to many other cryptographic protocols， just。😊。

I just spoke recently to Ed Felton at Princeton， so he's actually working on they have implementations now of software where that the IRS could use to sort of prove to you that they carried out a fair procedure and deciding to audit you so if you've been audited by the IRS they to you might worry that they were just targeting you for political reasons or something。

 but but now there's a cryptographic protocol where they can prove that that they did the correct they were using the same algorithm they were using for everyone else but they don't have to reveal the algorithm that they're using for auditing and this way of course they don't want to because if they did then people would game it。

 so not clear whether this is actually going to be used。ca with cryptography。

 the problem is always even if you can prove that it works。

 or assuming a oneway function or whatever the person on the street may not understand or belief that but but apparently it does work that's just what example of an application of zero knowledge proofs。

 which were just like a purely complexity theoretical concept back when they were invented back in the 1980s so now our last unit in the course is where we're talking about something that right now is mostly a theoretical concept。

 well theoretical and a little bit experimental， namely quantum computation，Maybe in our lifetimes。

 it will become a practically important concept。Okay， so and even even if it doesn't。

 it's still really cool to learn about because you know it is like the simplest， you know most fun。

 most appealing way to learn sort of the basics of quantum mechanics itself in my opinion。

 you know quantum mechanics is maybe you know the single most important thing which is known about physics and you know it stood since the 1920s so it's not going anywhere for quite a while and you know we probably have to learn to live with it no matter how counterintuitive it is。

 okay so。So Robin， who， by the way， works in quantum computing， as I do。

 sort started telling you the basics on Tuesday， the basics of how a single quantum bit or qubit works。

Okay so a quantum bit， we write as a superposition of zero and1 states。It's really a vector， okay。

 it's a vector of these complex numbers， which are called amplitudes。Okay， and。You know。

 and they satisfy this normalization condition okay。

 and this is sometimes you know the most basic object in quantum mechanics， okay。

 just a superposition over two possibilities。😊，And。嗯。

Okay and you know we could spend you know the entire course debating what this really is。

 you know and maybe not reach a resolution， but what I can tell you for sure is how it behaves okay what it does okay so so first of all you know if let's say alpha and beta let's say for simplicity that they're real numbers which you know suffices for most of the purposes that you know we care about in this class then the possible superpositions of0 and1 of course just form a circle。

 the unit circle okay alpha squared plus beta squared equals1 okay alpha is1 and beta is0 then you have the zero state okay if alpha is0 and beta is one then you have the one state okay these are two orthogonal states you know they're at right angles okay in general two states。

 two quantum states are perfectly。Distinguishable from one another。

 if and only if they're orthogonal vectors，Another important state is what we call the plus state。

 which is an equal superposition of0 and1。And。All right， let me write it like this。

And the minus state， which is also a superposition of 0 and 1。

 but now this one is 0 minus1 over square root of 2 okay。Okay， and the basic rules。Okay。

 so so the two basic things you can do to a quantum state are you can measure it or you can evolve it by unitary transformation。

 Okay measurement sort of forces the qubit to decide you know which classical outcome it wants to be okay and that's a very you know as you may have heard a quantum mechanics measurement is a destructive and irreversible process okay it causes you know the famous collapse of the wave function。

 or you know at least at least in the conventional way of talking about it， you know。

 if you want to go deeper， can we can do that but but in the。You know。

 a conventional presentation of quantum mechanics， you know。

 you measure a qubit that's alpha0 plus beta 1 and you ask it sort of is are you0 or are you1。

 going it's going to tell you that it's zero with probability。

 absolute value of alpha squared and one with probability absolute value of beta squared。

 okay of course these add up to1。😊，And then。Whichever outcome you see。

 that's then the state changes to match that， okay， so if you see zero， it's now just zero。

 you ask it again because I already told you I'm zero， okay。😊，The other thing you can do is。

You can take the vector of amplitudes and you can multiply it by a matrix okay that you can do a linear transformation of the vector that takes it to another vector of norm1 okay so you can apply any matrix that always maps you know unit vectors like this to other unit vectors okay and such a matrix is called a unitary matrix。

There's a characterization that I think Robin mentioned that's very useful。

 which says the matrix is unitary。呃。If and only if it's in verse。Equals its conjugate transpose。

 okay， which you know， a simpler way to say that is that。

A matrix is unitary if and only if if you look at the row vectors like they form an orthogonal basis。

 they form a set of orthogonal unit vectors， and equivalent to that is to say that if you look at the column vectors。

 then they form an orthogonal unit basis of unit vectors。So for example。

So you could think of unitary matrices as just being basically rotations and reflections。

 that's really what they are。So for example， for any angle theta。

 this is going to be a unitary matrix basically you know here， if I put the minus sign up here。

 then this is really just a rotation by theta okay。

You can you can check that this is unitary okay and in some sense， you know it has to be unitary。

 of course it's mapping unit vectors to unit vectors because all it's doing is it's you know rotating okay the plane a little bit all right and so。

😊，Okay， so some of the important examples of unitary matrices。You know。

 these are ones that even make sense classically， just do nothing or apply a knot to your bit。

This is one that doesn't make sense classically， it says if your qubit is one。

 then multiply its amplitude by minus1， otherwise do nothing。呃。And then there's this hatom mard。

 which is very， very useful because basically what it does is that it。

It switches between the 01 basis and the plus minus basis。Yeah， and it's its own inverse。Right。Okay。

 so yeah。this。Plus， is this state and minus is this state。 Okay。So， it's。These two states Yeah。

 they're at a 45 degree angle to the zero and one states okay and these are two you know different superpositions of0 and 1 okay and you know and so now one conclusion that we can draw from this is that the plus and minus states are perfectly distinguishable from each other okay why because you know if I gave you a state。

 let's say you know you didn't know if it was plus or minus what you could do is just first apply a had a mark to it right and then just measure to see whether it's0 or1 you know and that would tell you okay and in general if this is the reason why orthogonal states can be perfectly distinguished by measurement because you could you know you could always just first rotate them so that you know one of them is zero and the other one is one okay and then you could measure to see what you got so you in general unitary transformations have the property that they preserve the angle between any pair of quantum states so they're never going to change。

😊，They're never going to pull states， pull two states apart or push them together。

 They're just going to be， you know， as I said， rotations and reflections。So。In fact。

 you know the picture of the universe that quantum mechanics gives is basically that the state of the entire universe is basically just this unit vector just rotating around in you know a complex vector space。

That's the fundamental thing that quantum mechanic says，😊，呃。So。All right。

 so there's a very important general point here， which is that you know you know I can consider this entire circle right in addition to you a state like zero。

 I could also have minus zero okay I'm not sure if Robin got to this yesterday okay but。

In in quantum mechanics0 equals minus zero okay there is no you know experimental or you any other you know important difference between these two states they're just different notations for the same thing okay and how can we see that well it's because you whatever measurement you were to make you know this minus sign would just be completely unobservable because you know if I ask if you're0 or you're1。

 well the amplitude for the zero state here is minus1 but minus1 squared is one and in general whenever you convert amplitudes to probabilities which is always what happens when you make a measurement then you you have to take the absolute value you take the absolute value and just you if if all your amplitudes were multiplied by minus1 that would just be totally you would make no difference。

😊，It's a symmetry of the theory， okay， so a good analogy would be like how would you know if last night the entire universe was moved 10 feet to the left？

You it doesn't mean anything to say that it was right， because it could have been。

 there was no experiment we could ever do that would tell us that。So。U。

So the same thing with you know with what we call global phases， okay， so this。

 you know the opposite poles here actually just represent the same state okay， but so global。

 we say global phase is unobservable。😊，Okay， but， but we also say relative phase is observable。 Okay。

 we just saw that。The superposition0 plus  one is very， very different from the superposition，0 -1。

 Those can be distinguished from each other perfectly by making a measurement。😊，系。Good。嗯。Okay。

 so you know another unitary transformation you could have is just like a 45 degree rotation。

 you know with no reflections like this， this just rotates your state， 45 degrees counterclockwise。

So it maps the zero state to the plus state。And the plus state to the one state and then the one state to the minus state。

 you know again you know this state is equal to this one right so this is just the minus state okay。

 and it maps the minus state to the zero state and so on you just keep going around in a circle you know as you apply this this R over and over again okay。

You know and there is something strange about that okay which is that you know you you could think of R as sort of like flipping a coin right it's a way to produce randomness in a sense in the sense that if you applied R to the zero state and then you measured you would get a random outcome zero half the time one half the time okay and you know in quantum mechanics says that that is really just irreducibly random there's you know it's not just a matter of you know you know not knowing enough details about the state okay you know and we could go into the reasons why people believe that if you know if you want to talk about it okay but。

But okay it also you know you could start with the one state and apply R that would map you to the minus state you then measure the minus state in the0 or1 basis and again you get0 half the time1 half the time so you know you would say it stands the reason then that if you started with a superposition of0 and1 and you applied r to that then you should again get something random because you know the0 leads to something random and the one also leads to something random so surely a superposition of the two you should should also lead to something random but no that's not the case if you started with with the plus state with you this equal superposition of0 and1 and then you applied R and then you measured then you would always get1 if you started with you know the minus state and then you applied R and then you measured then you would always get zero okay。

So。And， you know， there's。There's a very useful picture to represent what's going on。

Which is you know you start from zero， let's say you apply R and you get an equal superposition of 0 and1 right you know。

 and then you know you can you can you know now let's say you apply R again to the superposition of 0 and1 okay。

😊，Well， you know， all that's really going on in some sense is， you know。

 everything here is just matrix vector multiplication， right？Let me， let me do it like this Okay so。

You know what， here。So here is applying R to an equal superposition of0 and1 okay。

 so we so you know we could think of it as we apply you know R to this component and we also apply it to this component okay。

 we apply it to this component the01 we again get an equal superposition of0 and1 okay。

 we apply it to the one component and we get。Minus0 plus1 okay now if you want to find the final。

 you know， and of course， this equals01。Right so now you know if you want to find the final amplitude for some configuration。

 you need to add up the amplitudes for all the ways that you could have gotten there and if some of them are positive and others are negative then they can cancel each other out okay which would make the total amplitude zero which would mean that that outcome is just never observed okay that's called interference of amplitudes and in some sense that's the central phenomenon of quantum mechanics that's the central thing that a quantum computer which would try to exploit to get an advantage as we're going to see。

So in this case， you have an amplitude here， which is a half time sorry one over root two times one over root two。

 which is a half amplitude here， which is one over root two times minus1 over root two。

 which is minus a half， you add them up， you get zero okay， whereas for the one state。Here。

 we've got an amplitude of a half。 and here we also have an amplitude of a half。

 So the total amplitude on the one state is one， just like we see here。 Okay。

 this tree is just a different way to you know， represent the matrix vector multiplication。

 That's all it is。Okay， so。But。Okay， you know the famous illustration of quantum interference is this double slit experiment。

 I don't know if Robin showed it to， but so this is the know the famous the famous experiment I guess to sort of you know is used to demonstrate that our world is quantum mechanical and that it has to be described in terms of these amplitudes know and not just in terms of classical probabilities by the way lots and lots of people say oh well quantum mechanics is is mysterious because it involves probabilities that's bull okay if all there was to it。

 know was that know there was some you know God was throwing some dice here and there that wouldn't be such a big deal。

 could deal with that， whatever we use pro all the time but but these are dice that behave in a totally different way that any dice know that people have ever seen。

Beforefo and and then that's really the issue Okay so so so you know what happens in the double slit experiment is you know you shoot photons。

 let's say one at a time into a screen that has two slits in it and you look at where they end up on a second screen okay and。

😊，And and what you find is that， you know， there are certain places。

 you see this interference pattern， Okay， so there are certain places where a photon。

 you know where the photon can appear and then there are certain places in between where it just never appears okay。

 or you know， it iss very， very unlikely to appear okay。But then you close one of the slits。

 and then these places where the photon could never appear before， then it does appear there。Okay。

 you know， so so then， you know， then actually you just get two blobs like you know， one or sorry。

 you just get one， you know， kind of blob you know around here right and and in general，You know。

 you would think that。You would think that whatever else is true right it must be like an axiom of probability that the probability that the photon would land and say at some region on this screen。

 you know call it P would be the sum of the probability that it could get there by going through slit1 plus the probability that it would get there by going through S2 okay this is what's violated in quantum mechanics that's what is not found to be true so in the sense that you know you can find certain places where you know if only the first slit is open then the photon can get there if only the second slit is open then the photon can get there。

 but if both slits are open， then the photon cannot get there okay and。You know so you know。

 after you know， seeing this and thousands of similar phenomena， you know。

 the explanation that physicists you know finally had to invent you know， that was to say， well。

 you know。You should not think of it as there being a probability for the photon to go through slit1 and a probability for it to go through slit 2。

 instead there is an amplitude for it to go through slit 1 and there is an amplitude for it to go through slitt 2。

And then there is a。There's a total amplitude for it to you know arrive at a certain place。

 which is the sum of these two amplitudes okay， and that really does add up the way you would expect okay the issue is that when you make a measurement。

 then you force the amplitudes to become probabilities okay。

So then you're talking about the absolute square of this amplitude。And。

The heart of the problem in quantum mechanics is that this is not equal to that in general，You know。

 this has cross terms Okay， so you know， in particular， you know。

 if alpha 0 was positive and alpha 1 was negative， then this can be zero， even though this is nonze。

Okay， so you know， and this is why closing， you know。

 one of the ss can increase the probability that you find a particle at a certain place， okay。

 because you know if both of these are negative， they cancel out。

 but if you force one of them down to zero， then you get something positive。Okay， so。Okay。

 now know the even weirder part for many people right is that。

You know if you now just say this is nonsense， let's just monitor the photon and let's see which slit it goes through okay so you just set up a measuring device I don't know these are measuring devices that just you know register which slit the photon went through okay then you no longer see the pattern of interference okay then you really just see there's some probability for it to go through the first one。

 some probability to go through the second one you know and the probability that it will land at a certain place is is probability that it got there through the first slit plus the probability that it got there through the second slit okay and then it's everything is just looks totally normal like nothing weird was ever going on okay you stop looking and then you get the interference pattern again。

Okay， so。So you know I hastened you know， so a lot of people you know like sort of conclude from that well you know it must be you know like a conscious you know observer who's looking at it that changes the experiment。

 I hasten to add that in order to destroy the pattern of interference it doesn't have to be a human who's looking at it okay it could be any kind of measuring device or you know in fact。

 any anything whatsoever that just takes the information about which slit the photon went through and that leaks it out into the external environment。

 okay that causes that information， that qubit of information if you like to be recorded anywhere else including in the air molecules in the room。

 okay if the information leaks out in any way， then you no longer see the interference and you know that is the basic reason why it's so hard to build a quantum computer by the way。

 if if you were wondering right？ca you know， quantum states sort you know they only sort of do this interference thing if you let them keep maintain their privacy。

 okay， if the information and them leaks out into the external environment in any way。

 then you no longer see these patterns of quantum interference。

 then it just looks like classical probability。Okay。Okay， so you know， which means that， you know。

 you have to keep， you know， if you want to do a quantum mechanical experiment。

 you have to keep it very， very， very well isolated from the external environment。

 you know that's why people didn't notice these effects until the you know， 1910s or 1920s， you know。

 that's why you know， and sometimes that's why we don't notice them on the scale of everyday life。

 you know， like we rarely see cats are， you know， that act like they're in superpositions of alive in dead states。

 you know， you you know， if you。But you know， but if you you know make measurements on electrons。

 then they do act like they're in super you know， exactly like they're in superposition of their ground state in their first excited state。

 because you and an electron can sort of much more easily， you know。

 avoid leaking its information out into anything in the external world than a cat can。

Because a cat has you know an enormous number of particles， you know， 10 to the 23， 10 to the 24。

 you know whatever， and you the chance that at least one of those particles would have interacted with the environment is enormous and all it takes is one of them to know collapse it for being in a superposition of alive and dead to being one or the other。

So。诶。Right。Okay， so that's interference。Yeah and you know if you're making a measurement。

 so you know if you know which slit you know the photon is going through then you just sort of reduce to the classical case right where you know if it was going through this slit then you know it could have appeared at this location。

 if it was going at this slit， then it could have appeared there so you know if you know it's going through one or the other then again it can appear there okay it's only if you don't know if nothing in the external environment has recorded which slit that it can go through。

 then you see a pattern of interference that causes the photon to never appear at that location。Okay。

So。So that's most of what I wanted to say about one qubit。

 and so now we could move on if you like two qubits， okay。Which is。

Where we see more of the interesting phenomena， okay， so in general， the state of two qubits。

 we have to write by giving a superposition of over all four possibilities that you know for a2 bit string okay so there's 00。

01，10 and 11， each of those possibilities gets its own amplitude。😊，As usual know。

 these amplitudes have to satisfy a normalization condition like that。U。And now， you know。

 once again， you know， there are two things that you could do， you could measure this system。

 you could ask which string are you and you won't surprise you， you excuse me。

You'll see the amplitude sorry you'll see the outcome 00 with probability。

 absolute value of alpha squared， 01 with probability， absolute value of beta squared and so forth。

 and it'll collapse to whichever one you saw okay。😊，So， you know it's。Similar to what was before。

 except now we've got a vector of four complex numbers instead of just two of them。

We can also take that vector and multiply it by now a 4 by four unitary matrix to get a new vector。嗯。

So， you know， how can we create four by four unitary matrices Okay， so now it。

It'll be very useful to sort of introduce something called the Tensor product okay。

 Tensor product is just sort of a very fancy way of saying that you have two things and you put them next to each other okay but you know you can have tensor products of states。

 you could also have tensor products of unitary transformations okay so。

So we write it with this symbol。So the first thing is you know when I write this state like00 right。

 this means two qubits that are both in the zero state right。

 but you know I could also have written this， you know， a zero qubit and a zero qubit。

 I could have put I could have put each one in its own little cat。

 okay you know that just means the same thing， okay。Or I could also have said。That this is zero。

 tense or zero。 Okay， so again， it's just a fancy way of saying you know。

 I put them next to each other， okay。You know， now， you know， a more interesting case。

So I could take the zero state， tenor the plus state， let's say， right， and what is that？

That just zero， and then it's 0 plus1 over square root of two。Right。You know， and now you know。

 you can sort of just manipulate these like algebraic expressions just as long as you remember that you know it's not commutative right。

 so you you know， so this is the first qubit， this is the second qubit。

 okay but this is equal to00 plus 01 over square root of  two。Right。

 this is just a superposition over two strings in both of them， the first qubit is zero。

 but the second qubit is a superposition of zero and1 okay that's all we're saying。😊，Okay。

How about a tensor of the plus state with the plus state。

 what is that as a superposition over two bit strings， anyone？What？😮，Brite it out。Well。

This is0 plus1 over Ro two。This is0 plus one over Ro2。

So what's the amplitude for the zero zero state here？A half， yep。

 just one over Ro  two and one over Ro two， and how about for the zero1 state？Also half。

 okay and so forth， this is just an equal superposition over all four strings。Okay。

How about minus1s or minus anyone， what's that as a superposition over two bit strings？Same thing。

Yeah， we have。Yeah， exactly， yeah now for the cross parts we've got minus， so we've got 00 minus 0，1。

 minus 1，0 plus 1，1。😊，Over two。Okay， so those are。Tenssor products of， you know， this is a way。

 this is one way to construct a two qubit state by just tensoring together two1 qubit states。 Okay。

 and this is just saying， you know， you've got two。Onequbit states that are next to each other。

 in some sense。Okay。Now just as you can tensor states。

 you can also tensor to unitary transformations okay so this what we're saying intuitively here is do nothing to the first qubit and do a had of mark to the second qubit okay that's what this is saying okay but now you know this represents a four by four unitary matrix okay that acts on you know the set of all two qubit states and what do you think this would look like if represented as a four by four matrix。

Well， you know， again， you know， it needs to encode kind of hadamard the second qubit and do nothing to the first qubit okay。

 and so the way that you do this。There's like that。Okay。That sort of you。U。So， you know， so here the。

You know， this is what each column represents and this matrix and this is what each row represents。

 okay， so what this is saying is if the first qubit is0。

 then had a mar the second qubit if the first qubit is one。

 then also had a mar the second qubit okay that's exactly what we wanted right？😊，Okay， in general。

You if you have two， say， onequbit unitary， you said you want to tensor them。Yeah。

 it's kind of annoying to write this out。We sort of take A， we multiply it by this whole thing。

We take B and we multiply it by the whole thing。And say。Fine， I right。Okay。

 so for that that's how we tensor unitary matrices， okay。

 and you can check that the you know the tensor product of two unitary matrices is always going to be again。

 a unitary matrix okay， again， it just represents doing the one thing to the one qubit and the other thing to the other qubit。

OkayAnd so so in general， like in quantum computing we'll often talk about。

 you know you've got 10 qubits or you know even 1000 qubits or a million qubits and now you want to do something to some subset of the qubits like you know Haamor the eighth qubit or something like that okay and what that always really means is apply the tensor product of the Haamor gay you know the Haamor matrix on the eighth qubit with the identity matrix on all of the other qubits okay so so really you know like。

😊，You know， if you had 100 qubits， then you know the total space of unitary matrices on them right。

 you know， these are two to the1 hundred by two to the1 hundred sized matrices， Okay。

 but really all we mean is， you know， tensor products of。You know， had know of you know。

 some transformation on those qubits that we're talking about， like the eighth one， the ninth one。

 whatever， with the identity on all of the other qubits，嗯。Okay， so now you know， we've seen how。

You know， there are many。You know， two qubit states that we can construct by tensor product。

Just to do one more example。Who can factor this state for me？

Who can tell me what this one is the tensor product of？Yeah。Yeah， exactly。Okay。Good， so yeah。

 so we can。Also， a factor states， all right， let's do another example。Who can factor this one for me？

What？😮，Thank you。Thank you。Good point All right， thanks， yes， normalization is annoying。A mechanic。

 but yeah， you're absolutely right。 Yep， good， all right， so yeah， so this one。😊，All right。

 this one is not factorizable。 that。 And we can prove that， All right。Okay。

 let's suppose by contradiction that this state could be factorized into a0 plus B1， tensor。

 C0 plus D1， I'll switch back to the Roman alphabet。Okay。Then。What could we say about ABC and D。

 can anyone tell me something about them？What would AC have to equal？Good。

 and how about how about BD？What would B D have to equal？Same thing。Okay， how about AD？

What does AD equal？Zero yeah， because there's no 01 term over here， so AD is zero。 What does B equal？

Okay。Anyone see the problem yet？Well， what's ABCD？Yep， if I multiply these guys， ABC D is zero。

 what about if I multiply these guys？AHa， right。If I multiply these guys， ABCD is a half， okay。

 that's a contradiction right， which implies that this state cannot have been factorizable， okay？😊。

A state of multiple qubits that cannot be factorized into separate states on the individual qubits。

We call it entangled state。Okay。And。Okay we'll also call a state separable if it can be factor。Okay。

Okay，So so there exist entangled states right there are states of two qubits that cannot be thought of as just a state of the first here's the state of the first qubit。

 here's the state of the second qubit okay you know we're going to see soon what are the implications of that you know because there has very big implications okay but first let's actually discuss how would you ever create an entangled state you know。

 let's say that you started with states that are unenttangled you started with separable states okay you can that you know if you started with like you know like a separateparable state you know like two separate qubits and then you just did two separate things to the first qubit into the second qubit then the qubits are never going to become entangled okay you know。

 two things are going to become entangled， there has to be some kind of interaction okay but you know。

There is interaction in nature， you know， things， you know。

 particles don't just you know stay separate， they collide with each other。

 you know they have forces you know by which they interact with each other， okay。

 and so you can have a you can also have two qubit unitary transformations that are not the tensor product of one qubit unitary transformations。

Okay， the most famous example in quantum computing of a2 qubit unitary transformation is what's called the controlled n or CO。

😊，Okay。And。You know， there are several ways to think of it。It is a unitary transformation。

 the map 00 to itself，01 to itself， 10 to 11。And。1， one。To 10。Okay。So， you know。

 which means in particular that you know so so it just swaps the 10 and the 11 states， right。

 which means in particular this this is its own inverse， you know。

 you apply the controlled not twice， you get back to the identity okay something is。

 you know if a matrix is its own inverse， then it's a unitary matrix。So CO is unitary。

 what does it look like as a four by four matrix， anyone？

What4 by four matrix will correspond to the CNO gate？Well， you know。

 I've basically just specified it here， right？So let's say I had a vector of。Four amplitudes。

 you know， and I wanted to see not it。Well， you know I know that this unit。

 if I had the unit vector 10，00， that has to go to itself。Right， if I have the unit vector 0100。

 which corresponds to this string， then that has to go to itself。Okay， if I have unit vector 0010。

 which corresponds to the string 10， then that has to go to 0001。Which corresponds to the string 11。

 and if I have。The unit vector 0，0，0，0，1， then that has to go to 00，10。Right。

 which means that my matrix is what。Okay， that is the controlled not matrix。Right here。Okay。

 so this is a4 by four matrix， you know。You can think of it as you're just if the first qubit is zero。

 then you do nothing， if the first qubit is one， then you apply a knot to the second qubit， okay。

 so this is why it's called a controlled knot。Okay， so， you know， so this is something that involves。

 you know， both qubits sort of interacting in some way right。

 you do something to the second qubit conditioned on the state of the first qubit Okay。

 and so CO is not as you can check cannot be written as a tensor product of two1 qubit operations Okay。

 now how can we you know， let's say that。Let's say that I started with two qubits both in the zero state。

 how could I use gates or unitary transformations that we've already seen in order to produce an entangled state？

Can anyone think of how。Well， you know， I could try doing a controlled knot。

 but a controlled not will just map this state to what。To itself， all right。

 so it's not reducing any entanglement yet。Okay， but is there anything else that we could do that could help us make an entangled state？

What could we do first？Yeah。Yeah， exactly。 we could first had to， you know the first qubit， okay。

 what's that going to give us， that'll give us。0 plus one over root 2 on the first qubit。

0 on the second qubit。 Okay， what's that。That can also be written as00 plus 10。Over square root of2。

 Okay， now what can I do？See not， CO lets say from the first qubit to the second qubit。

 what will that give us？Well， you know it acts， you know， you know。

 everything in quantum mechanics is linear， right， so it acts separately on each component。

00 gets mapped to what？Z0 and 10 gets mapped to what？One，1， okay， good。

 so that gives us our entangled state。Okay，So that's how one can generate entanglement using the gates that we've seen。

Okay， so now。Okay， so what's the meaning of entanglement？Okay。

 so to say this sort of I have to tell you one more rule of quantum mechanics okay。

 but it's one that's sort of very， very you know straightforward given the previous rules okay so now you know let's say that I have a two qubit state like this where I told you you can measure both qubits told you you can do unitary transformations to it。

 okay but there's another thing you can do is you can measure just one of the qubits without measuring the other qubit。

Okay， so let's say for example， that you know because you an important point is when two qubits are entangled。

 that doesn't put any limitation on how close together they have to be， okay。

 one of these qubits could be on Earth， the other one could be on the moon， that's fine， okay。

 there's no distance limit on entanglement。Okay， so。So you know， now you know， you could imagine。

 you know maybe we have just one of these qubits in our laboratory on Earth and we would like to measure it you know because we don't have access to the partner qubit that's on the moon okay。

 but we can measure the one on Earth， now now supposing that we measure you know。

 the first qubit here in the 01 basis， what do you think is the probability that we'll see zero。Well。

 we've got to add up the squared amplitudes for all of the outcomes， you know。

 for all the possibilities that have a0 in the first qubit， okay， so you measure the first qubit。

 you're going to see0 with probability alpha squared plus beta squared。

And you're going to see one with probability gamma squared plus delta squared。Okay。

 and and then the one， you know， and the first qubit will collapse to whichever outcome you saw okay now but now there's one more thing we have to say。

 which is suppose that I measure the first qubit and I see a zero。

 then what happens to the second qubit， okay what is now the state of the second qubit。对 있어요。嗯。Well。

 if I measure zero in the first qubit， then sort of you know these outcomes have become impossible。

 right， these are now just totally inconsistent with what I've seen。

 so these have vanished if you like。Okay so you know all that's left is what's over here。

 so the new state of the second qubit should be just alpha0 plus beta 1 right except anyone see a problem with this。

 yeah， that's not normalized， what do we have to do to normalize it？😊，Well， yeah。Yeah， exactly。

We just do the。So we just sort of normalize this thing by force。 Okay， and that that's the rule。

 That is this is the new state of the second qubit。 If you see 0 in the first qubit。

 What's the new state of the second qubit if you see one in the first qubit。Okay， well。

 it's just gamma0 plus Dlta 1。Over square root of gamma squared plus Dlta squared。Okay。Go。Okay。

 so now you know， if you just apply that rule，'s say to a tensor product of two qubits， right。

 what you'll find is that measuring one of the qubits， you know， you know。

 you can measure one of the qubits， you can learn the outcome。

 that has no effect whatsoever on the other qubit， you know， maybe not surprising， right？Okay。

Let's consider by contrast an entangled state， so suppose that I measure the first qubit here and I see zero。

 then what do I know about the second qubit？it's also zero okay if I measure the first qubit and I see one。

 then I know that the second qubit is also one okay so you know and again it doesn't matter how far apart the qubits might be okay so now you know you know I'm sure many of you have heard that enormously bothered Einstein and then in the 30s and you know Einstein Pulsky and Ron wrote a famous paper about this okay 1935 you know basically saying that this can't possibly be right because this seems to suggest that you that the two qubits have instantaneous communication with each other no matter how far apart they might be in space you measuring one qubit somehow instantaneously affects the other qubit and this would。

Seem to violate relativity okay but then you know let's actually just think about this。

 you know carefully and you know just try to see how just how bad the problem is， okay？😊。

So the first question is， you know， could we use the， you know。

 could we use this phenomenon of entanglement to create like an instantaneous you know。

 telephone between， you know the Earth and Mars you know or you know， you know you know。

 could we use it to achieve faster than light communication， okay， well you know， to。You know。

 if we wanted to do that。Right，3。So Alice and Bob are not only for cryptography。

 they also like quantum computation a lot and play huge roles in this field as well，😊。

So we could imagine that Alice has one qubit and Bob has the other qubit and we draw that wy line to represent that the qubits are entangled okay now and now you know Alice wants to send a message to Bob okay so now you know can she do that by you know let's say measuring her qubit right does anyone see a problem yeah？

Choose which one is you can take。Exactly yeah in some sense that's the fundamental problem here right Alice can measure her qubit you know and if she measures。

 she'll see zero half the time one half the time， whichever one she sees she'll know that Bob you know will get the same thing whenever he measures okay but she didn't get to pick which one she saw right you know so so she's not actually communicating any information to Bob this way okay and you know it would you know it would be kind of like you know you you know if if any of you still you know read newspapers or know what newspapers are right you know you pick one up you know you see the headline and then you know that you know if your friend is also reading the newspaper you know that they're going to see the same headline okay but we don't normally describe that as you know spooky communication at a distance you know that's just correlation of random variables right just totally ordinary thing okay。

And in effect， that is what Einstein Pulsky and Rosen said in 1935。

 they said that there has to be some way of explaining this you know phenomenon of entangled particles you know in terms of you know just classical correlation right like there has to be some kind of explanation that would involved with when these two qubits got created and when they first got entangled with each other。

 they just exchanged some you little notes and they said listen if anyone asks。

 you know let's both be zero know you know and then you measure and you find that there're both zero and then it's no big surprise right so basically you know Einstein thought there had to be some story like that going on behind the scenes okay but now you know there's a you know it took you know amazingly it took sort of 30 years to notice it。

 but there's a technical problem with what。With what Einstein wanted， Okay， and you know。

 the basic problem is that you。You know， Alice and Bob， after these qubits are separated。

 they don't have to only measure them in the 01 basis right they could also measure these qubits in other bases like you know by which I mean you know。

 Alice could apply some unitary transformation to her qubit before she measured it right Bob could apply a unitary transformation to his qubit before he measures it okay。

 so。So by the way， if I ever say。If I ever talk about like measuring a qubit in the plus minus basis。

 right， all that means。Is that you first do a had of mar transformation and then you measure in the zero1 basis。

哎呦。So you can always think about rotating a qubit first and then measuring in the01 basis， right。

You know， an equivalent way to talk about that is just measuring the qubit in another basis right instead of asking the qubit。

 whether it's zero or1， in fact you're asking it to decide whether it's plus or minus right that's you know。

 that's another question you could ask in general for any two orthogonal states any two states at right angles to each other。

 you could ask the qubit are you this one or are you that one。But just suitably rotating it okay。

 so so Alice and Bob can measure their qubits in all these different bases okay and it's not obvious whether you know there's any story we can tell involving only classical correlation that will get the probabilities of the measurement outcomes right for all of those possible measurements okay and then。

😊，Some of you may have heard of the famous theorem of John Bell right in 1964。And in effect。

 what Bell showed is that there is no possible local you explanation of the kind that Einstein wanted that's going to account for all of the possible measurement results okay in other words。

 you know he gave an example of an experiment you know of a set of measurements that you could do involving two entangled qubits where there is no story involving classical correlation that you could tell that would get all of the probabilities right okay you're going to prove that on piece at six okay so you know so the last problem one piece at six basically just asking you to disprove Einstein okay you know it walks you through it okay it's not you know it's actually not very hard okay。

So so you know what this shows is that entanglement you cannot be understood as just classical correlation。

 you know of random variables right， it's something else， it's a quantum form of correlation。

 it can you know， it can lead to sort of it can allow Alice and Bob to win certain games。

 for example， with a higher probability than they could possibly win them if they only shared。

 you know， classical you know， random bits and didn't share entanglement okay， but despite that。😊。

There's also something very important called the no communication theorem okay which says exactly what you would think okay that you know there is no way at all to use entanglement to you know to let Alice send a signal to Bob faster than light okay so you know the technical statement is that if Alice and Bob share any entangled state you know of any number of qubits then there is no combination of you know unitary transformations and measurements that Alice can do to her qubits okay that will affect the probability of any outcome of any measurement that that Bob can perform on his qubits right so in that sense quantum mechanics is local okay in that sense it sort of is compatible with special relativity and with you know no communication faster than light。

😊，Okay。😊，But you if you asked for more than that then you may not get it okay so basically you quantum mechanics is like this weird intermediate possibility that no one would have even thought of as logically possible before it came along and exhibited it right where quantum mechanics does not let so putting together the no communication theorem with the bell inequ equality。

 the basic picture that you get is that quantum mechanics does not let you send signals faster than light it better not because you know otherwise it would totally violate relativity right in relativity if you can communicate faster than light and in someone's frame of reference you're communicating backwards in time that's the problem so it upholds the no faster than light communication however。

 if you were。😊，Trying to simulate quantum mechanics， like using like a bunch of classical particles。

 then your simulation would require faster than light communication。

That's what Bell's theorem tells you。Okay。So。嗯。Okay， good。So that's entanglement。

 there's one further thing I've got to tell you about two qubits。Okay。U。

So you know I told you that you know you only get one chance to measure a quantum state it's like you know you use it wisely right you know you can you know I'm sure you've heard like you can measure the position of a particle you can measure measure the momentum of a particle but you can't measure both right and you know the qubit version of that is like you could measure your qubit in the01 basis you know get some outcome you know you could measure your qubit in the plus minus basis get some outcome okay but you can't do both right you make the measurement and then your measurement has now collapse the qubit you know and force it down okay so you get you get you know one chance to to measure your qubit okay but you know you might say all right but you there should be an easy way around that right all I've got to do is make a bunch of copies of my qubit okay I just need to you know just take it you know it's just information right you just make a bunch of cop。

And then you know I could measure some qubits in the01 basis。

 I could measure other qubits in the plus minus basis， you know。

 in fact I could you know by measuring all these copies。

 I could just learn alpha and beta themselves to any precision that I wanted to okay that would be a really useful ability to have right？

Okay。Unfortunately， this is not possible， this is not compatible with the rules of quantum mechanics and the statement that it's not。

It's called the no cloning theorem， you again， very creative names here。

And we can prove the no clo theorem。It's a very very， very simple but illuminating proof。So。

So let's just assume for simplicity that what we want is a unitary transformation。

 so we want like a two qubit you know or a  four by four unitary transformation。

 U that will have the effect。You know， where I have one qubit that's you know。

 that I want to copy and now I need a second qubit which is just in the zero state， you know。

 which is just saying like it is ready to receive a copy of the second qubit right。

 this is just what we sometimes call an anciilla qubit okay or you know it just it's its just there to you know to accept a copy okay。

 and we would like the outcome of this。To be alpha 0 plus beta。 Oh you know what。That's stupid。

 I don't need the over squarequa of too。Okay。Okay I would like the outcome to be that and I would like that to be true for any alpha in beta okay you know of course if you knew alpha in beta then you could just use your knowledge to make as many copies as of alpha zero plus beta1 as you wanted Okay but the point here is that you don't know alpha and beta okay you're just given this one state Al0 plus beta 1 and you need a copying machine that works for any possibility so the outcome has to be this does anyone see the problem yet。

All right， let me。Let me。All right， well let's write this out as superposition over two qubbit states。

 so what's the amplitude of00 anyone？Alpha squared。What's the amplitude of 01？Alpha beta， yeah。

What's the amplitude of 10？Alpha beta。And the amplitude of 11。Beta squared。That's right， okay。

 so the outcome is that okay， so now I'm asking you for a unitary。

 which is a linear transformation right， which takes this input state。

 this is alpha0 plus beta 1 tens or0， right？😊，And maps it。To that。Okay， anyone see the problem yet？

This is not linear okay， this is， you know， there is no linear transformation you know。

 of alpha and beta that could possibly give you alpha squared or beta squared or alpha beta， okay。

 and that's the entire proof。😊，Cloing would require a nonline operation on the amplitudes okay you know but quantum mechanics only lets you do linear transformations of the amplitudes okay so so so you know this has very profound implications there's no cloning theorem okay you know you may have heard the saying you know information wants to be free right you know you know like a staman likes to talk about how you know you know bits can just be copied you know for free。

 anyone who wants okay quantum bits do not have that property quantum bits you know have a certain privacy to them okay and you know you could actually use that theres a proposal for quantum cryptography right where you would be sending you know you would be encrypting a message by sending qubits over a channel and the whole thing that makes it work is that you know if an eavesdroroppper is monitoring the qubits to try to measure them you know and。

But they are then you can detect the fact that the Eavesdroroppper was measuring them okay because the Eavesdroppper cannot make copies of the qubits you know for personal use while you know letting the original qubits go through if the Eavesdropper wants to learn something by measuring then they have to modify the qubits and then Alice and Bob can detect the fact that they were modified you can also use this for quantum money so actually Stephen Wesner。

 who was the son of the MIT president in the 70s had this remarkable proposal for when he was a grad student for quantum money。

