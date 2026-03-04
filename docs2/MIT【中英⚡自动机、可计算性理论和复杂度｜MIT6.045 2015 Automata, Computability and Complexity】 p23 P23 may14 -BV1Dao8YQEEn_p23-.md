# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p23 P23 may14 -BV1Dao8YQEEn_p23-

Okay so welcome to the last lecture， it's a bittersweet day I guess so a few things I do have PS at 5 back for you finally you can pick it up after class piece at six I was hoping to have it back for you by the recitation tomorrow but it looks like the graders can't do that so but they can do it by Monday so if it's important to you to see your PS at 6 before the final then come to my office on Monday and you can pick it up and I will bear on the graders to you know see that that happens then okay so the final is Tuesday again 130 it's here you can bring a one page cheat sheet both sides there will be recitation。

😊，Tomorrow， you know， in case you missed the review session last night or if you want just more final overview。

你谂。Come to that and just a reminder to do the subject evaluation right。

So last time you know we talked about sets of quantum gates acting on qubits and how you you can easily design sets of quantum gates that are universal in the sense that by applying enough of them。

 you can approximate any unitary transformation on any number of qubits to any desired precision and then once you have this notion of universal gate sets you can then consider what can you do using them using say a polynomial number of gates from a universal set so if have if you're allowed to build up a polynomial sized quantum circuit acting on a polynomial number of qubits where let's say you need you have a classical touring machine that figures out which gate to apply when or the description of the circuit and then you make a measurement at the end and you want to get the right answer with probability at least。

Two thirds we'll say you know this gives you a definition of the complexity class that we call BQP or bounded error quantum polynomial time okay。

 and this we consider like the quantum version of P or of BPP okay。

 sort of like the class of all the decision problems that you can that are efficiently solvable solvable and polynomial time using a quantum computer。

😊，Okay but then you know the question is you know great you can define it but what is it you know what does BQP actually contain。

 how big is it does it you know go beyond classical computing in any interesting way okay so we just started to discuss that question briefly I apologize we ran out of time on Tuesday but we talked about the Deutsch Josa algorithm this was the first quantum algorithm discovered you could say and what it does is it computes the parody of or the Xor of two bits with just one access to the bits there by achieving a 50% speed up over what would be possible classically or you'd have to query both of them okay so how does it achieve that seemingly impossible feat well by using quantum superposition so so here I've drawn the quantum circuit for the Deuts Jos algorithm okay so F here。

😊，Is you know you assume that you have like a unitary transformation that does this okay that queries the function F in a black box manner that maps x and a to x and a exclusive or with f of x okay there writing f of x reversibly into an answer register and by using that unitary transformation only one time you want to know f of zero exclusive word with f of1 okay so how do you do that well there's really just two ideas you know the first idea is that you can you can get the value of f of x written into the amplitude so you can get so it's often in quantum computing it's extremely convenient to have to have your amplitude say multiplied by minus1 if and only if f of x equals1 you know and otherwise have your amplitude be unchanged okay so that's。

And then that's what we want here the question is how can you get that using this kind of black box okay and the answer is very simple you just you initialize the answer register a to the minus state you preload the answer register with zero minus1 over square root of two okay and then you observe that you know if a one gets exclusive word into0 minus1 then it maps that state to one minus0 right which you in some sense is the same state right it's just you know it's the previous state multiplied by minus1 right so all that you've done is you've thrown a minus1 into the amplitude。

 you've multiplied the amplitude by minus1 okay so you whereas if of course if you exclusive or0 into this state and that does nothing you at all so all in all you know if you apply this unitary to this state。

😊，Then you know you get you know the same state x minus back。

 but now your amplitude has been multiplied by minus1 to the f of x okay。

 so now all you do is you consider just doing that but doing this transformation here which we now know how to do but on a superposition over both inputs0 and1 okay so we take equal superposition of0 and1 in other words the plus state okay and then we apply this transformation。

 you know what happens， well you know we get this right each amplitude has been multiplied by minus1 okay if and only if you know the corresponding f value was1。

Okay otherwise nothing happened to it okay now notice that if we had just had a single classical state and we multiplied the amplitude by you know minus1 to the f of whatever that would have no effect whatsoever right because as we said you know you know multiplying the amplitude of the universe by minus one you know it like moving the universe10 feet to the left right has no effect on anything okay but you know if you have two objects and you move one of them 10 feet to the left then that does have an effect now the objects may be further apart than they were before okay and the same way if you have two things in superposition and one of their amplitudes get multiplied by minus1 but not the other one then that does have an effect okay and in particular it sort of it reveals the exclusive or of the two values F of0 and f of1 as you can see in this table here okay so I。

😊，You know I drew the whole you know table of possibilities f of0 and f of1 if they're both zero。

 then nothing happens to the state， it remains the plus state if therere both one then everything gets multiplied by minus1 but if everything does then we just get minus the plus state so you know and then this is you know for all intents and purposes this is still just the plus state okay so again nothing is happened okay but if one of you know the f values is one and the other one is0。

 then what happens then one of these amplitudes gets multiplied by minus1 but not the other one okay so like for example if only f of1 is one。

 then we get0 minus1 which is the minus state okay if only f of1 is one then we get minus0 plus1 which is minus the minus state and either way you know the plus and the minus state or per。

😊，Pfly distinguishable from each other right because a had a mard gate multi a maps the plus state to0 and the minus state to1 okay so we can now had a mard and measure and then that will tell us what was the x or of f0 and f of1 so you know this should be underwhelming you know it's only a factor of two speed up and you know you could say that you know even that factor of two speed up is sort of swamped in practice but you know the constant factor overhead in doing this experiment in the first place you know in setting up all the physical apparatus to do this right all that you've decreased is the number of axises to F but you could say you know if it's just a factor of two who really cares about that okay。

😊，So today what I'm going to do is I'm going to show you a more impressive example of a quantum algorithm。

 I mean you already did a somewhat more impressive example on your last PSE which was the Bernstein vsanni algorithm。

 which can actually learn an endbit string using only one query， okay。

 and it' sort of like a very cool generalization of Deuts Choso。😊，But。

And that's something that's clearly impossible classically。😊，Okay， but。But today。

 you know I'm going to show you the first quantum algorithm that sort of really clearly got an exponential speed up over what the best classical algorithm could do for the same problem and this is still going to be for somewhat artificial black box problem okay and this is called Simon's problem and you it' solved using Simon's algorithm。

 but but but historically this is what led sort of very。

 very directly you less than a year later to Peter Scharer's famous quantum factoring algorithm。

 okay and I'll sketch a little bit you know how that goes and then I'll say a little bit about BQP itself what we know about how it fits in with the other complexity classes that you've already seen in this course and then hopefully we'll have time for some general Q&A okay。

😊，Okay， so what is the problem that's solved by Simon's algorithm？

So this is again going to be a problem involving a black box function F。

 you know so there's some function that you know you can only access as a black box。

 okay in this case， F is going to be a function that maps nbit strings to other n bit strings and it has a very special property okay。

You know， you promised something about F， okay， namely that。There exists a secret string， s， okay。

 which is not the old zero string， okay， but a secret n bitch string such that。U。For all x and y。

 f of x equals f of y， if and only F。呃。Why。Is the bitwise exclusive or of x with S okay like you could say you know y is the encoding of x with the Ks and the one time pad okay so just so here that this sign just means the bit by bit exclusive or okay and so what we're saying is that this function F has a hidden symmetry in it okay so like its values you know the outputs of f are all distinct you know unless you have two inputs that differ know exactly on some secret substr and if they differ exactly on that secret substring then the two outputs are the same。

Okay，😊，Let's do an example， let's say that someone give me a three bit secret string。010。

 good choice， all right， so then which pairs of inputs have to map to the same output？Well， zero，0。

0 and 010 F to， 001 and 011 and zero。Let's see about 100 and 110 and 101 and 111 Okay。

 so for these these pairs you know map to the same output okay now。Your challenge。

 should you choose to accept it， is to find S， okay you want to learn S。

By querying F as few times as possible。Okay， so。Let's first consider the classical situation， okay。

 how many queries would a classical algorithm need in general to find S， you know。

 I mean we could first consider just a deterministic classical algorithm right。

 what's a number of queries that would suffice in any case。😊，哈。Yeah， okay。

 let's consider the general case， the case of an arbitrary ad。Two to the end right okay。

 you can always just query everything right in any of these black box problems。

 you could always solve it by just querying the entire you know。

 you just just you know reading that reading the black box from cover to cover right you know that would always determine the answer okay so two to the end certainly suffices can anyone think of an approach that might do better？

😊，Let's say that you're allowed to use randomness。So you're allowed to use a classical randomized algorithm。

Let's say that you just picked a whole bunch of values at random， you know。

 a whole bunch of x values completely at random， and for each one you looked at F of x， you know。

 then when like at what point could you stop？At what point would you know the answer？最中で。Yeah。

 as soon as you find any collision pair to any x and y， such that f of x equald f of y。

 that point you could stop because at that point you could just exclusive or that x and y。

 and that would tell US。😊，Right。You know， at that point， you know。

 that point you're immediately done okay， so the question boil really boils down to， you know。

 if I picked a bunch of x at random， how long would it typically be before I found the collision pair？

😊，Anyone know？Yeah， so right， so it has to do with the。😊，The famous birthday paradox。

Which is not actually a paradox。But this is the phenomenon that， for example。

 there's a decent chance that there's two people in this room who have the same birthday， you know。

 if you know everyone who took the class， you know actually showed up for it instead of you know watching the video then it would be near you know a certainty that there would be two people in this room who would have the same birthday okay。

 you know I'm not going to go through and do it， but you know you may have。😊，You know。

 you know maybe you saw that in high school or something， okay， and you know。

 and what's going on is simply that there's 365 days in the year， you know。

 birthdays are distributed， you know。Sort of random， you know， not entirely randomly， you know。

 they're more concentrated， you know， nine months after Christmas， things like that， okay。

 but you know mostly uniform and so then what matters is the number of pairs of people okay so。

You know， if you have square root of N people， let's say when there are end days in the year。

 you know， then there are about you know，1 different pairs of people who could have the same birthday and you know each event is you know close enough to independent that you know with high probability one of them will succeed okay so by the similar sort of logic。

呃。One can prove that if you have a classical randomized algorithm， then with high probability。

 it will solve Simon's algorithm after only about two to the n over two queries。😊，So it will。

You know， you'll just pick a whole bunch of random x values。Like that。

 and then you'll just look for collisions， okay you'll look for an I and J such that f of Xi equals f of xj。

😊，When t is about the square root of  two to the n with high probability， you'll find that。

 and once you find it， then you know that s is the exclusive or of x sub i with x sub j okay。😊。

So now but now one can also prove that you know， if the only assuming the only way you can access F is via this black box that computes its values。

2 to the n over 2 is optimal， okay， it is the any classical randomized algorithm needs at least about two to the n over2 queries to solve Simon's problem。

😊，And。呃。So I think I won't prove that here， but the proof is actually not hard using a technique that you've learned。

 which is the union bound， yes。No， no， no， no， the whole point of the birthday paradox is that it gives you a square root improvement over what。

 yeahhu。Yep。So actually two to the end， the whole thing divided by two。

 this is about what you would get deterministically， I think。

 you know if you had a classical deterministic algorithm。😊，Get about that。

 but with a randomized algorithm you can actually get this real quadratic improvement okay because of the birthday paradox。

 okay。Because you know， after you've qua T numbers， you know。

 you have teachers two different pairs know to compare to， to look for collisions in okay so。😊。

So one can prove you know using the union bound actually that you after you'vequeried T things like the you know。

 let's say that S was chosen uniformly a random， right。

 then the probability that you that any two of these you know would have an x or that's what you want would be only about one and two to the n。

 one and two to the n minus1 guess okay。😊，So then， you know， if you've got t chooses2 pairs。

 the probability that any of them shows the collision you want is that most t chooses 2 over2 to the n minus1。

 and not just not going to be appreciably large until t is like 2 to the n over2。Okay。

 so you know you can formalize that reasoning。Okay， okay。

 but now I am going to show you a quantum algorithm that finds S using only n queries to F， okay。

 thereby achieving an exponential speed up over the best classical algorithm。😊，Okay，And you know。

 if you're wondering why anyone cares about Simon's problem， know。

 this was the reason why Simon cared about it because it's something a quantum computer can do better。

 okay？😊，You know， there wasn't。You， and people， you know， people sort of didn't didn't。

Consider it a very big deal at the time because it had no other application other than just the fact that a quantum computer was good at it。

 okay but know if you did take it seriously， then you would have been Peter Sho and you know so okay。

So。😊，Okay， so how can we get a quantum algorithm that will solve this problem more efficiently Okay。

 well most of the many， many of the quantum algorithms that we know of actually have a very common structure。

 which is that you。The first step， the first thing you do is create an equal superposition over all two to the n possible inputs to F。

Okay that's this， okay， and as we said， that's easy to do by just how to maring all of your qubits。😊。

So。Maybe I will。Just so we can keep track of what's going on on this board。

 I will draw what's happening in quantum circuit notation。

So we take n qubits and in the zero state and we had them marred them and we give get an equal superposition over all of our inputs okay。

 the next thing we can do is we can query F in superposition okay。

 so if I have a bunch of qubits down here which were initially in the zero state。And I now apply。

My black box。For F。Okay， then that will just。White f of x in superposition into you know into that second register Okay。

 so now I have a superposition you know for every possible input X。

 I've got x f of x right and you know and this yeah。😊，I've got the total number of wires is 2N。Okay。

 there's n here and there's n here。Because F is a function from end bits to end bits。Okay， good。😊。

You know， so the number of wires is only linear right the size of the superposition is exponential but you know but the actual physical device that we're building you know has to be only you know linear polynomial sized okay the number of wires must not grow exponentially so all right。

 so now I've got this this state， you know and and this sounds kind of impressive right you know well I've got all the answers in parallel at once in you know different universes okay but you know again。

 you know you know you know we have the usual difficulty right at some point you've got to measure the thing okay and if I just measured the state not having done anything else。

 I would just get a random Xf of X pair which I could have you know just as well gotten classically you know with the same number of queries。

 namely one。😊，Okay so all right， so I've got to do something a little smarter。

 so the first thing I'm going to do and this is actually just for pedagogical purposes。

 this plays no actual role in the algorithm， but first thing I'm going to do is I'm going to measure the F of X register。

😊，So I'll put little measuring devices there Okay， now let's suppose I measure the F of x register。

 I see some value right， you know， but now I'm not measuring the X register。Okay。

 I'm not measuring this register now can anyone tell me what kind of state is going to be left over in the X register after I measure this register and I see some value。

Excellent， yes， that's exactly where I'm going to see a superposition over two different exactly two possible inputs。

😊，X， call them x and Y。Okay， an equal superposition of them， and what y know about x and Y？😊，Yeah。

Exorly。Exactly they that they are related by the secret string okay well you know I will know that F of x will equal f of y right because what will be left in this first register will be simply an equal superposition over all the possible x's that could have produced the f of x that I observed right this is the rule for you know partial measurement and quantum mechanics right it's just like with conditional probabilities right you know I see this what's left here is a superposition of you know all the things that could have produced this outcome which in this case there were two different x values that could have produced it you know。

😊，A name we know there's some。X and y that satisfy this relation Okay by the way， you know one。

 you know， one of the many sort of things to get used to with quantum algorithms is that you know you know the only reason why I'm querying you know F。

 why I'm producing this output is because of what effect that you know that's going to produce on the input。

😊，Okay I don't actually care about the value of F of x。

 I never use it in the algorithm right you know after I measure these bits here I can throw them in the garbage okay the only thing I care about is the effect that computing F of x had on the superposition over input states。

😊，And that's again， a very common feature of quantum algorithms。😊。

So so now I've got a superposition of you know x and y and now you can say you know it looks like now now I'm really。

 really close to done because now all I've got to do is measure that state twice okay I just measured it twice then with a good probability you know I would see x and then another time I would see Y and as soon as I see both x and y then I just exclusive orm and then I know S okay awesome right you know I've got like the whole answer to my problem。

 the whole S I'm looking for is like right in my hands right it's just the x or of the two things that I have a superposition of okay so anyone see a problem with that。

😊，You can't measure twice yeah unfortunately you know quantum mechanics does not allow you to measure twice you can measure once。

 but then you know you're just going to see X or y randomly okay and the other one will have vanished right and then it's you know and then you've learned nothing about S right you know all the information you wanted was in the relationship between the two things okay and you might think well then why don't I just repeat the whole experiment a second time you know so one time I'll get X then I'll repeat the entire experiment and then the next time I'll get y does anyone see the problem with doing that。

😊，Yeah exactly next time you'll probably get a completely different pair right there's exponentially many different possible values of F of x。

 you're probably never going to see the same one twice right and you know so you repeat youll just see a completely unrelated XY pair you know so so that's no good either okay so you know this shouldn't be a surprise because nothing we've said so far has exploited interference right and you know you know the only way to get a quantum advantage at the end of the day is by using interference of amplitudes okay so we're going to have to measure this state in a more clever way that will you know use interference and that will tell us at least something about S okay so can anyone suggest a different way to measure this state what is something we could do to it before measuring it。

😊，I'll give you a hint， it's something that you've seen。Ha a mard， yes， you know， so you know。

 you know， a good rule of thumb in quantum computing， you know， if you're stuck， try hat a maring。

 okay？😊，So。Okay， so a very important identity that you saw on the PSAT is that if I take an n bit classical string。

 x， let's say， and I had a mard each of its qubits， you know。

 then I'm going to get this superposition state okay I'm going to get a superposition over all two to the n possible strings。

 but each one will have an amplitude which is minus one to the inner product of my original string with z。

😊，Okay， so。You know so all of this is this is just a fancy way of saying that the hatammard maps each0 bit to plus and maps each one bit to minus okay I'm just saying that in a different notation you know if I took each x sub i that's equal to one you know and I had a mard it then I get a minus state which means that you know whenever that X is1。

 then my amplitude gets multiplied by or sorry wheneverzi is1。

 then my amplitude gets multiplied by minus1 if if x sub i is0。

 then in the isq bit I get a plus state which means that it doesn't matter if the if bit of z is1 or0 that has no effect on this okay so all right so so this is what I'm。

😊，So we're going to use this identity Okay， so now and let's。Keep track in our quantum circuit。

 so we're now had a maring all of these n input qubits a second time。Okay。

 so what happens when I had to mark all of the qubits of x plus y over square root of2？Well。You know。

 huh？Well remember everything in quantum mechanics is linear。

 so I can just do this to x and y separately， okay。Okay， so I get this state。Which is。

I'll just rearrange it a little bit。I'll just collect disease。So I get a superposition over all Zs。

 and for each one， I get minus1 to the x dot z plus minus1 to the y dot z。Okay。

 so these are now my amplitudes， okay， they look like this okay now now let's say that I now measure this state okay。

 I'll just measure each of these qubits in the01 basis。So I'll put。What measuring devices there Okay。

 now what are the possible Z's that I can see when I measured this state？

What are these that I can't see？But I'll never say。Well。

 the probability of measuring some Z is just the square of its amplitude， right？

So the things I can never observe are the ones that have an amplitude of zero。X and Y。

If they're different， they cancel out。Exactly， we now have to think about interference， okay。

 if x dot z。😊，Equals by that Z。Then that is a Z that I could see。That sounded like a poet。😊。

If if these two are equal you know or let's say mod2 all that matters is the parodity here because I'm raising minus1 to the power okay if x dot z and y dot z are equal mod2 okay then you know these are either both positive or they're both negative okay so they reinforce each other if you like and that leads to a z that it is possible to c okay if x dot z is not equal to y dot z。

 then one of these is positive the other is negative and they cancel each other out okay so then that z would have an amplitude of0 so I could never see it okay so the you know bottom line is that I am going to observe a random z such that x dot z equals y dot z mod2。

😊，Because all of the ones that are possible， you can easily see that they all have equal probabilities。

😊，Okay， so now can anyone rewrite this equation x dotz equals y。tz mod2 and a more。

What if I exhort y。z to both sides， would I get？Yeah， yeah， so I can。

I can rewrite it like this and you know this。ThisThis inner product， you can check。

 is really just multiplication。You know， it has a distributivity property。

 which you know you could check that all this is really saying is that x exclusive or with y dot z equals0 by2。

Okay， I you invite you to check that if you okay， what is X exclusive or with Y？😊，S。H。

So the bottom line of this is you know I don't necessarily see。

 you know when I measure you know these qubits， I'm not going to see S itself right away that would be you know that would be awesome but that's you know a little too much to hope poor but I'm still going to get something that's pretty good which is I am going to see sort of a random linear equation that is satisfied by change。

 now grant me that that's something right I am going to learn something about S okay I'm going to learn that you know I'm going to see sub z such that s do z equals0 mod2 okay which would tell me basically like you know here is a subset of bits you know whose exclusive or you know in S is zero。

😊，That's the way of putting it okay。😊，What if I wanted to know more about S than just this one linear equation that it satisfies。

 what could I then do？Yeah， you can do it again。 I could do it again。 Excelt， right， I've seen。

 I've now， you know， by running this algorithm， measuring， I've gotten out one linear。

 one random linear equation that is satisfied by S， Alright， so。😊，What's the next thing to do。

 get a second random linear equation that's satisfied by S right I'll call the first one z1， okay。

 I run the entire algorithm a second time and I'm going to observe sub Z2 such that s dot z2 equals0 mod2 and so forth。

😊，Let's say I repeat M times。Okay。And now the point is you when you've got linear equations in n unknowns and they're all random。

 they're all kind of independent of each other or less than you only need about a linear number of them before you get a system that you can solve and solving a system of linear equations is something you can do efficiently on a classical computer。

 you using Gaussian elimination for example， so so when you've collected know about n of these linear equations then with high probability you'll get a system that has well you'll get a system that has exactly two solutions。

 namely S equals zero， but you know that that's not the solution because we assumed it wasn't n S equals the correct value so all at all we have to repeat Simon's algorithm about n times in order to do this。

😊，Time we write it， we make one query to F。 So on the whole， we make。I will adding queries to F。Okay。

 and actually only polynomial and n computation besides those queries， okay。

 and this is an exponential improvement over know what we had for classical randomized algorithms。😊。

Okay。Now because you know， I know that this problem looked a little bit artificial let me briefly sketch for you how you know modifying this algorithm led to an efficient quantum algorithm for factoring okay I won't be able to give you the full details in this lecture if you're interested in them you know。

 you should take you know 2111 which is the undergrad quantum computing， well。

 not it's technically a grad course， but I think it's mostly undergrads who take it so。😊，Or6845。

 which is my graduate course on quantum complexity。All right。

 so let's say you want to read someone's email right so you've got。😊，You've got a composite number N。

 you know， it's a product of two primes P and Q， and one thing that you saw when we discussed RSA is you saw that if you can just learn the order of the multiplicative group。

 mod N。This。Wicch。Happens to equal p minus1 times q minus1 okay so the number of you know elements and the group of all the stuff from one up to n that is relatively prime to n right then that you know then from this you can easily get the prime factors of n that was on your PAT right so all right so our goal is just to learn the order of this multiplicative group right。

😊，Okay， so now what we do is we。😊，U。We pick some random number x， say in the multiplicative group。

And then。Let's consider the function， F of R equals x to the R mod n。😊，Okay。

's the modular exponentation function， okay， first of all。

 can this function be computed in time polynomial in N？😊，Any other。Yeah， actually you。

 it can be computed in time polylogarithmic in this end， okay。

 but if I you know the true input size I should think of as you know little n， which is log of big N。

 and this can be computed and even in time which is polynomial and little n， how do we do it？😊。

Repeated squaring， yes， okay， so I have a fast algorithm to compute this and that's important because that tells me that this F is now not just a completely abstract black box is you know this is a function that I can actually compute right。

😊，I could design a polynomial sized circuit， even inside of my quantum computer that would map R to F of R。

All right。😊，So now。You know，Now this F is a periodic function， right， it repeats with some period。

 and what can we say about the period of the function？Anyone。what can one say about the period of F？

デ番。Yes， excellent。The period of F， whatever it is。Has to divide the order of the group。

 which is p minus1 timesq minus1。Okay， because。You sort of， you know if I you know， if I raised。

 you know， we know by Eer's identity that if I raise x to the p minus1q minus1 power。

 then I just I get one right， you know I go， so we know that you know you know the whole thing cycles around you know with a cycle length that is。

 you know the multiplicative group， it may also have a smaller cycle length than that， okay。

 but at any rate you know whatever is the cycle length of F。

 it divides the order of the multiplicative group。Okay。So so now， you know。

 I want you to grant me that if I could learn the period of F that that would tell me something pretty interesting about the order of the multipl of group。

 you know and therefore about the prime factors okay you know， just like with Simon's algorithm。

 you know it's possible that knowing the period of f wouldn't immediately tell me what I wanted to know。

 because after all it's just some divisor of p minus1 timesq minus1。

 you know it's not the thing itself， but you know if I just picked a bunch of random x's and for each one。

 I found the period call them P1， p2 and so forth。Okay。

 and then I took the least common multiple of all of those guys。

 which is something I can do in polynomial time know， using Elid's algorithm， say。Then。

Using a little bit of number theory， one can show that with high probability。

 I'm going to get the order of the full multiplicative group， right。

You know there's a chance that any one of these individually will be smaller。

 but I take enough of them you know， you sort of shake it up， you know。

 take the least common multiple of them all and with high probability that's the whole thing all right。

 so I'm not going to prove that but that's。That's something it holds。Okay， so then the question。

And becomes， how can I figure out the period of F？Okay， and now this is just。

 we can think about it as an abstract problem。 You can imagine if you like that F is just a black box function and you're trying to。

 you know， and it has this secret and， you know， symmetry to it Okay， namely that there is a。😊，那。

There is some secret s， let's say， such that f of x equals f of x plus s for all x okay and you are trying to determine that s by querying F as few times as possible does it sound familiar to anyone right so you know so it's true that like we're over a different group here we're over you know a group mod you know like that looks like Zn rather than Z2 to the N okay but you know this is structurally very。

 very similar assignments problem？😊，Okay， and the algorithm that Sho came up with to solve it was indeed。

呃。W I call this？Create a superposition over a huge number of integers which are now all encoded in binary。

 call them R。😊，And for each one， compute compute F of R， so compute F of R。

 which is x to the R mod N in superposition over all the R's， okay？😊，Okay， I should say you know。

 even just classically you could you could try looking for the period of F by just querying lots of random values looking for a birthday collision right but that's going to take in general is going to take exponential time right because the problem is that the period of F will in general be an exponentially large number and so you're going to have to until you happen to see2 x and y you know a pair x y such that f of x equals F of y you know you'll in general have to query an exponential number of values just like with Simon's algorithm you know that's the problem if you try to do this classically but。

😊，If I can create a superposition over all the possible values。

 know over like a huge number of different integer values， where let's say。

For technical reasons M should be about n squared here okay but I make this big superposition。

 I query F once again I don't really care about the actual values of F all I care about is what the computation of F did to this part of the state what it did to this superposition here okay so I measure this I throw it away。

 I look at what's left over here， can anyone describe to me what kind of superposition is left over in the first register after I throw away the second register。

😊，Yeah， well， you have a bunch of R such that they're different。Is a multiple。Yes， exactly。😊。

What I have。You know， I've got a superposition over all the possible Rs that could have produced the F of R value that I observed。

Okay， so so let's say you know， there's some smallest value that could do it and then there's that value plus s。

 you know， plus whatever is the period of F right by definition that's going to lead to the same value okay。

 there is that。R value plus 2 S， there's that R value plus 3 s and so forth。You know。

 with some normalization that I'll omit okay， so you know， now once again， you know。

 we now have the question， what do we do with this state。

 it seems like it could tell us something useful about S， but how do we get that thing out？😊，Okay。

 so you。😊，You know， you could measure this in the you know in the standard basis， but if you do。

 you know I'm just going to see like a random multiple of s shifted by a random amount which in other words nothing okay nothing you know of any use to me okay so I need so once again I need to do something else to this state if I want to learn something useful about S okay。

 and the thing I have to do is you know is more subtle in this case than simply how a maring every qubit okay you know can you can try it buts it's not going to work okay。

😊，What you do is something called the quantum Fourier transform。Okay， so， you know。

 because if you think about it， the basic problem that we have here is that。

We have a periodic sequence right we have a sequence you know you know where each pair of elements know differs by s okay and you know our goal is by measuring this thing once to just you know or let's say by linearly transforming this state in some way so let let me write this as a vector of amplitudes okay if I wrote this as a giant vector of amplitudes what I would say is like000 and then something some nonzero value at the r if entry and then0000 and then another non-zero value at the r plus ss entry and then another nonzero value at the r plus 2 Ss entry and so forth okay and now my problem is how can I linearly transform this vector or what unitary matrix can I hit it with such you know that will produce a vector that tells me something about s okay that's the problem okay。

😊，Fortunately， such a unitary transformation has been known since Joseph Fourier in the 1700s and you've probably learned about it in some of your other courses for completely different reasons。

 okay， it is called the Fourier transform okay， and the entire point of the Fourier transform is that it's a linear transformation that maps you know say a periodic function to you know a spike that is concentrated on the period of that function。

 okay。😊，That's exactly what we want here， right？とよ。So the different rows of the Fourer Bay Trix。

Like the first one， you know， I'm here I'm going to ignore the normalization there's one over square root of something。

 whatever， but the first row was like all ones， the next row is。

Like1 omega omega squared and omega cubed and so forth where omega is some complex root of unity here that you know the fact that quantum mechanics involves complex numbers is actually very convenient for us you know and then we've got omega squared omega omega to the4 omega to the6。

 then we've got omega cubed omega to the6 omega to the9 and so forth。

 the Ij entry is like omega to the Ij where you know omega is sub root complex root of unity okay and so basically the h row of this matrix is tried to pick out whether this function you has a certain period。

 namely you know。😊，So we're trying to pick out like you know。

 if I rotate around you know in the complex plane at this certain speed。

 then will it be the case that you know that every time I hit a non-zero entry I am back at the same place right there's only certain special speeds where you know namely you know the speeds that sort of resonate with S where you know every time I hit another。

 you know R plus KS you know， I'm back at the same sort of region of the complex plane and we're therefore all these different contributions will interfere constructively and reinforce each other right。

If I is out of phase with S， then every time I hit you know r plus S R plus 2S。

 R plus 3S and so forth， you know I'm just at a different direction and then I get a whole bunch of contributions that mostly cancel each other out okay so that is the magic of the Four you transform and just like in Simon's algorithm what one proves is that you know it doesn't necessarily tell you the period of S right away。

 but it tells you some useful information you know from which you after repeating actually a constant number of times you can reconstruct the period of S。

 you know in classical polynomial time。Okay so that's basically how Sho's factoring algorithm works Okay。

 and there's a very， very similar algorithm for computing discrete logarithms you know in polynomial time on a quantum computer。

😊，You know it should be clear even just from this little sketch that I gave you that you know this algorithm is really。

 really exploiting special properties of the factoring problem。

 okay this is not like a you know it's not a matter of trying all the possible divisors and superposition or anything as you know as silly as that okays you know you're using the fact that factoring can be reduced to period finding。

 period finding has this sort of global symmetry that can be revealed by just a suitable change of basis。

 namely changing from the standard basis to the four year basis。😊，All right。

So let me just take a few minutes to just。You know， give you a brief tour of what is known about BQP。

Okay， so I defined this class， you know， on Tuesday。

 it's a class of all the decision problems that can be solved by some uniform family of quantum circuits with a bounded probability of error。

 okay， so you know I defined it with at most you know。

 be the class of all the things that you can decide with。😊。

With it most a one third error probability， okay， what if we don't like one third error probability。

 what can you do about that anyone？Amplify yeah， exactly like in the classical case。

 you would just repeat your algorithm， repeat the quantum algorithm a whole bunch of times and take the majority vote right or you know in the case of let's say Sho's algorithm。

 you know if rotting the algorithm once doesn't tell you you know maybe it will only tell you the factors。

 you know 40% of the time or something that's totally fine totally fine because then you just repeat it you know 20 times let's say and almost certainly know one of the runs will tell you the factors and yeah and factoring has a nice property that once you've got the factors you know you've got them you can check them classically。

😊，Okay。You know， factoring is an NP problem， you might say。All right， so。😊，All right。

 but so now you know， so BQP is a pretty robust class， you know。

 and now the question is how does it fit in with the complexity classes that you've seen earlier in this course because first of all。

 what are some things that BQ yeah？Yeah， sure， how do you phrase it as a decision Oh。

 that's an excellent question， right So okay， so you know， we'd like to be able to say that。

Factoring is in BQP， right is like。Morally， intuitively true， okay。

 but technically factoring you know is a search problem， output， you know。

 output the factors is not a decision problem， Can anyone think of how to phrase factoring as a decision problem？

I think we actually did this at one point in the course。不要。Yeah， you could ask like that for example。

 you know does N have a divisor within this range and then if you could solve that then by binary searching you could find the factors right you know。

 so that problem is a polynomial time equivalent to factoring or you could say you know write the factors and some canonical order so you have some canonical way of writing down the factorization and then what is the I is the Ih bit in that way of writing it01。

That would be another way。Good。Okay， so yeah， so this is one thing we know about BQP that it contains factoring when that's suitably phrased as a decision problem okay what is there a whole complexity class that BQP contains？

😊，I mean， other than BQP。Yeah， yeah， so okay， so let's first say， why does BQP contain P anyone？

Why is this containment told？Well actually you know the way that I define BQP on Tuesday。

 this one is trivial， you know， I defined it in such a way that your classical you know controller that's outputting the quantum circuit could just output a quantum circuit that hardwires the answer to your P problem in it because it gets to see the input okay。

 so that's just totally trivial all right。What about why does BQP contain BPP？😡。

How would we simulate a classical probabilistic algorithm using a quantum one， anyone？Yeah。

Make measurements。Yeah， exactly， you know that's one way to you know just take a bunch of zero qubits。

 how to to measure them that gives you as many random numbers as you want okay。

 now technically when we define BQP， we didn't define the model in such a way you know that we allowed for intermediate measurements right。

 we only had this one measurement at the end okay but that's a technical issue that you can solve without too much difficulty Okay so it turns out that you know if I wanted to simulate the act of measuring a qubit。

 you know without doing an actual measurement。😊，I could always just do a controlled knot from that qubit into some ancillilla qubit that was initialized to zero in which I'll then never touch again。

 okay， you know， then it will be if I do a controlled knot。

 it is exactly as if this qubit has measured this one。😊，Okay。

Or another way to say it is that the modern view of what measurement is is that it's just a controlled knot gate from the qubit to you。

是。So you know and you're measuring apparatus and all the atoms in the room and so forth okay so I can do this to generate you know now I now have what's effectively a random bit in this qubit and you know and if I generate a whole collection of these that I can use these as inputs to let's say a circuit of puffly gates which I know can simulate any you know classical computation that I want and so then I can simulate a BPP algorithm right and you know just measure its output at the end all right。

 so I have this now。😊，In the other direction， what is an upper bound on BQP。

 what is something that BQP is contained in， can anyone give me a classical upper bound on BQP？Yes。

 peace based turns out to work， but that takes a little bit of thought。

 does anyone have one that takes less thought？X， yeah。Yeah， good。😊。

So we can certainly say that BQP is contained in classical exponential time， well why is this anyone？

😊，How can we see this？Yeah， well we can simulate。There are an exponential number of variables that we need to evolve we can do that with excellent excellent so you know our you know the state of our quantum computer is this exponentially long vector of amplitudes okay but you know if you have exponential time what's that to you right just store the entire vector in your memory and every time a unitary you know every time a gate is applied just replace that entire vector by a new one that's a big you know exponential size matrix vector multiplied but you know whatever you know you've got the time all right and you've got them and you've got the space Okay so you know and then at the end just you know calculate the probability of accepting by taking the sum of the squares of all the amplitudes of the accepting basis states and see whether it's more than twotds or less than onetd that gives you a classical simulation of your quantum computer which is merely exponentially slower。

😊，Okay， so okay， but already from this， we can， you know we learn an interesting conclusion。

 which is that， you know， there is no hope of， for example。

 using a quantum computer to solve the whole thing problem， right？😊。

Quantum mechanics is not going to take anything uncomputable and make it computable right it's not going to change the original church touring thesis okay it can only make things exponentially faster okay you know。

 of course that's already very， very interesting okay。😊，Okay， but now as someone。Suggested， you know。

 in fact， there are tighter upper bounds like B we know that BQP is contained in peace space。 Yeah。

 a quick question。 Yeah， sure if we're going to simulate。Using exponential time。To have。

Some sort of really good sit or at in general。Oh that's a good question okay so I claim that we don't need any pseudoranom generator to do this right because to simulate a BQP computation just means solve the decision problem you know is x and L or is x not an L right which means decide whether this quantum circuit except with probability greater than two thirdd or probability less than one thirdd and that just means you can if you've got exponential time you can just explicitly calculate the probability right so you don't have to do any random sampling you just calculate the probability and you see what it is。

😊，You know， if you wanted to simulate like a quantum process in terms of like producing a random number。

 you know， like producing random stuff as output， well then yeah。

 you could imagine that even if you had the halting problem as an oracle right。

 maybe you wouldn't have the random number source and for that reason you couldn't truly simulate quantum mechanics right you know that that would be an interesting issue right。

 but if you just want to solve any decision problem that's in BQP。

 then you know you can do that in X with no randomness needed。Question all right。😊，So in fact。

 it's known that BQP is contained in peace space， the proof of this relies on what's called the Feynman view of quantum mechanics or the Feynman sum over histories。

😊，Which is just a very fancy way of saying。You know， if you want to know。

The probability that your quantum computer accepts， you can write that。As the sum over。

 let's say all of the accepting basis state z of the final amplitude of z， absolute squared。

 right and that in turn。😊，Each of these amplitudes。Can it be written。

As a sum over a whole bunch of contributions from different paths。Right， so you know。

 just like that picture I drew with the tree for you know， to understand how to marting a qubit。

 right， you can calculate an amplitude by just looking at all the different ways that you could have gotten to that basis state you know and looking at the amplitude of each paths and then summing up the amplitudes of all those paths。

 that just a different way of writing a matrix vector multiplication，So you know。

 and but then you know， once I've written my acceptance probability as this kind of sum。

 then I can calculate that kind of sum in P space， okay， I can just， you know because yeah。

 it'll take me exponential time sure because I've got exponentially many different things to sum over。

 but I can reuse the same memory for you know， calculating each term in the sum， okay， in fact。

 you know， if you remember the complexity class PP from your Pet， so in fact。

 you know one can tighten this kind of argument to show that in fact BQP is contained in PP。😊，Okay。

Okay， so the final thing to talk about is yeah。はいでです。

Why does calculating alpha Z takes only polynomial。Oh。

 because I can write it as a psalm of exponentially many contributions。

 each of which I can compute in classical polynomial time。Okay。

 because each one is like just like the amplitude of this particular path。

 which is just the product of a bunch of， you know， matrix entries。Yeah， okay， good。So。

 so so you know the last thing that you know may have occurred to you is great you know how does BQP relate to NP okay。

 and you know the short answer is we don't know， okay。

 you know the longer answer is well you know there are really two very interesting questions here。😊。

First， we could ask， is NP contained in BQP or equivalently。

 can quantum computers solve NP complete problems in polynomial time？😊。

That's you know a great question， no one knows how to do it okay you know。

 you know if there is a way to do it， it looks like it will have to be totally。

 totally different from Sho's algorithm or anything else that we know okay。😊，So yeah。

 one thing that we do know is that if you just consider the black box searching problem， which means。

 let's say that I had a black box function F。That mapped n inputs to n possible inputs to zero and1。

 sorry。I mean this， and let's say I just wanted to solve the search problem。

 find an x such that F of x equals1。Okay， I wanted to do that by querying F as few times as possible。

 classically， how many queries do I need to solve this problem in general？

This is not a trick question。Yeah， about n， right， you know， maybe if I use randomness。

 maybe about n over two， okay， but really about n。Okay， quantumly。

 there is an algorithm called Grover's algorithm， which is maybe the second most famous quantum algorithm after shores that solves this problem in only about square root of n time okay only about square root of n queries to F and you know square root of n times log n computation gates。

 okay， you turns out you can repeatedly just。Increase the amplitude on the x such that f of x equals1 so it starts out with an amplitude of like one over square root of n okay you can then boost that to an amplitude that's like two over square root of n okay and then with each query you can boost it up a little more to three over square root of n4 over square root of n and so forth so that after t queries you've got a probability of observing the thing you want that's actually like t squared over n okay so you know after square root of n queries you've got probability close to one of finding your solution okay so what this says is that you can take any search problem whatsoever and a quantum computer will give you a square root speed up over classical brute4 searching okay so that's not an exponential speed up you know like Sho's algorithm gives you but it is much much broader than than shore's algorithm okay this again is called grover's algorithm。

😊，Okay so this can be applied to NP complete problems for example and you know you can put it on top of like the best classical backtracking algorithm that you know and you know usually it can be layered on top of such things and know and that can give you some speed up right but this is not going to turn an exponential into a polynomial and the other thing that we know about sures sorry about Groover's algorithm is that in the black box setting it is optimal okay so if you just if you could only access F as a black box then one can prove that even a quantum computer requires at least about square root of nqueries to solve this problem。

Okay， and if you want to see the proof of that， then take my graduate class。😊，All right， so you know。

 so and so in general， you know， so this says if there is a quantum algorithm to solve NP complete problems in polynomial time。

 it's going to have to take advantage of their structure in some way you know much as a classical algorithm would have to right now can we prove that that's impossible well of course we can't prove it's impossible right because we can't even prove that NPp is not contained in P or in BP right so how on earth could we prove that it's not in BqP okay but you know many of us would。

😊，ItWith conjecture that it's not。Okay， and yeah now the other question you could ask here is。

Is BQP contained an NPPG which which is like asking you know if a quantum computer produces an answer。

 is there at least a short classical proof that that was the answer notice that factoring did have that property right factoring is not only in BQP it's also in NPP okay but in general you this might not be true in general there might be problems that a quantum computer can solve but we the only way you know to verify that the answer was correct would be using another quantum computer you know in practice right we' even just checking the answer could take exponential time In fact。

 there might be problems that are in BQP but that are not even in the polynomial hierarchy you know we don't have extremely compelling examples of that some of my work has tried to give you know examples of this if you brought in what you mean by a computational problem then you can。

like problems with many valid outputs or problems where the output is a sample from a distribution。

 then you can get good examples of things that are in BQP。

 but that are not even in NP or indeed in pHH。matters。So just to leave you with a picture。

They'll be saying something。So we've got P and NP。Just a little bit。Jack。We've got。

The NP hard problems。And the intersection， the NP complete problems。

Okay then there we've got some special problems like factoring that are you know as far as we know in it you know or neither NP complete nor in P but they are in NP okay these are tend to be the things that we base cryptography on but you know the very same structure that makes them so useful for cryptography also gives us a quantum algorithm to solve them okay you know now I should say that there are theoretical public key cryptoyss you know that are out there based on things like the shortest vector problem that are not known to be solvable even using a quantum computer okay so if quantum computers ever become practical reality we could switch to these other crypptysts you know so there are and certainly if you just wanted private key crypto like if you just wanted one- way functions for example。

 then certainly we think you should be able to get a one-way function where the best。

Could do even with a quantum computer would be something like grover's algorithm right so there should be one way functions that are secure against you know attack even by quantum computers and maybe even trap or one way functions okay but at any rate not factoring and not this relog you know the ones that we use for you in practice for cryptography today by an unfortunate coincidence turn out to you know all be ones that a quantum computer can break all right and then BQP might protrude beyond NP it might have stuff that's all the way out here you know I drew it with this wavy border because quantum is spooky and weird but like the last lecture and any rate something like。

Being our students or something。BQP is certainly contained in peace space。

 and peace space is contained in X。And way， way， way， beyond all of this。

SittingSitting high and mighty above all of them is the halting problem so I'm sorry we didn't have time for questions。

 I'll be happy to hang around for anyone who has questions later and you know have office hours so thanks to all of you for a great semester and a good luck on the final。

やぱか。Thanks and I've got peace at five here。あ、いや。Back to slides really well。当是。Hey， Scott。The end。

Har than town。That's a very good question well you know you could you know maybe we can generate random numbers。

 you know， although even that is debate。And Im telling maybe we can do BP， but then again。

 we think the BPA will fit。So， you know， I mean， it's a very interesting question right。

 let me know if you read Roger Penro。You think。いさは。Sposedly。はは。😊，I think most people know。

would say well the brain ought to be simtable by his or。Take the， you know， connected。

Just you are not about us in terms。Probably you know in practice。你这。Sで。You know。

 that would give a sort of a attention。Argument that the brain is doing nothing outside could now it's。

 you know， if you wanted to challenge。And you know， you need something like。

That would be new to the biologist。Yeah interesting。Discussion about。People would say， you know。

How on are these？Here。