# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p19 P19 apr28 -BV1Dao8YQEEn_p19-

系。Com in come。It's the。I want to close the door so we don't have the construction that bothering us。

あ。Okay。Okay， hopefully that should be a little better。All right， so。Let's see。

 so PSet6 is out and that's the last one and it's due in two weeks a Friday of next week。And。PF4。

 you know， I am sort of bearing down on the graders。

 trying to get them to turn it in and know as soon as they。Get it in and we will get it back to you。

 hopefully by Thursday。So。嗯。And then also PS at five。

 okay so last time we talked a little bit about derandomization about why it's why do we believe today that actually any for any probabilistic algorithm。

 there's that produces some definite a guess or no answer。

 let's say there is a deterministic algorithm that has only you know that simulates it with only polynomialally worse performance and you the reason that people think that's true is that it seems possible to construct really。

 really good pseudorandom generators that could say expand a seed of size log n to a key。

 sorry to a pseudoran or random looking string of size N okay。

But the topic of pseudorandomness is one that sort of properly belongs to cryptography and so that that was sort of our next unit of the course so what we did last week is we talked about what's called information theoreticalore cryptography and that's basically all the cryptography where you don't put any upper bounds whatsoever on the computational power of your adversary the eavesdroppers is allowed to spend as much you computing power as they want to try to decrypt the message and you can indeed do something you know in information theore cryptography namely you can do the onetime pad we saw the one-time pad and the argument for why you when it's used correctly it really is information theoretically。

okay but then you know we also saw that you know if you use a onetime pad even twice。

 then it can become insecure， you know that fact has had historical consequences and furthermore。

 in some sense there's no you know there's not going to be any easy way to fix that because we saw Shannon's key size theorem。

 okay which says that if you want a crypto system like the onetime pad where you know it really has this information theore security then it is going to require huge key sizes。

Is there anything we can do， anything else we can do to decrease the noise， okay I don't know。So。

So it will yeah， it will require a key， which is as。

As long as the message itself or the sum of the lengths of all the messages that Alice and Bob ever want to exchange。

Okay， so you know which means that you know if we want to do better than that。

 if we want you know cryptography using short keys， then we have to stick our necks out。

 we have to enter you know the dark world of complexity based cryptography where you know at the very least you assume that P is not equal to NPp you know or you assume that there are some you know reasonable limit on what Eve is able to compute okay and and in fact we'll need to make stronger assumptions than that on what you know Eve is able to compute for example。

 it may be extremely convenient to assume that Eve is not able to quickly factor you enormous numbers you know let's say that factoring is not in P or things of that nature okay so。

So the first thing that we can do in the world of complexitybased cryptography。

 you know we can give a formal complexity definition of what we mean by pseudorandom numbers okay by numbers that look random but really aren't okay and that you know that will have two uses。

 I mean mean I mean first of all that lets us make more precise you know what I meant before。

 you know in saying that you know we think that there're a really good pseudorandom generators and that they should imply that P equals BP and so forth。

 second of all， you know once we have the formal notion。

 say of a cryptographic pseudoranom generator， then that sort of very。

 very easily lets us replace the onetime pad by a scheme that only requires small keys。

 but in some sense that we can argue you know is sort of almost，Good， okay。

So let's define a cryptographic pseudo random generator， Kerg， okay。

It's you know in this field it's often just simply called a PRG okay but the C is to distinguish it from the things that we saw last week like the linear congruential random number generator okay which might be fine for certain practical applications。

 but you really， really do not want to use them for cryptography and on PSS6。

 I believe you show how to break the linear congruential random number generator okay you show how to distinguish its output from random if you were trying to do that okay so intuitively a cryptographic pseudoran generator is going to be like a pseudoran generator that no polynomial time algorithm can distinguish from true randomness okay you know we can't have。

Sudranom numbers that nothing can distinguish from random okay， because， you know， you know。

 you could say， you know， you know， in the worst case， you could always you know。

 imagine an adversary who just loops through every possible seed you know。

 and sees whether any of them could have led to the pseudoran numbers that you saw right so so you know。

 so there's always， if your adversary has， let's say exponential time right， then you know。

 they can always distinguish pseudorandom numbers from random ones， you know。

 if the pseudoran ones were computed in polynomial time。

 but what you can hope for is that if the adversary is limited to polynomial time。

 then you generate numbers that really look random to them Okay and so。

 so that's this was kind of the key insight that people had in the early 1980s。

This definition is due to Andy Yale from 1982， I think you know he won the touring Award partly for this。

 okay and you know， so the key insight was that you know if something is look so random that no polynomial time algorithm can distinguish it from random。

 then that is random looking enough for us to be able to use it in cryptography okay and that furthermore。

 you know there are plausible ways that we can actually achieve that。So。To basically what it is。

Is its a function。The stretches， let's say an n bit string which is truly random to an n plus one bit string。

 which is going to be random looking okay and you know that's a very。

 very small amount of stretch but as we'll see it's totally enough once we have that we can get you know whatever amount of stretch we want you know and when I say a function。

 like really in some sense what I mean is an infinite family of functions like one for each value of n but you know I'll sometimes just suppress the dependence on n。

 I'll just talk about f okay。All right， and it has to satisfy two properties。😊。

The first one is that it has to be efficiently computable。Okay。

 and this is know a practical requirement right we have to be able to you know compute the pseudorandom numbers efficiently。

 okay it's reasonable and the second requirement， as I said。

 is that no adversary should be able to distinguish the output from true randomness if they run in polynomial time。

 so how do we formalize that。😊，We say that for every polynomial time algorithm A。

 which we call the adversary。The probability。That a accepts。If given。Say a。An n plus one bit。

 truly random string n minus。The probability。That A accepts。If given F of x。Where're x。

Is an end is a randomly chosen N bit seed。This has to be what we call negligibly small okay。

 so I ran out of room on the board， but I'll say this has to be less than neg， okay。

 where what is neg？If I say that something is negligibly small， I just mean that it's。

It is less than1 over p of n for any polynomial p that's what I mean okay so again。

 the difference between a's acceptance probability if you feed it a truly random n plus1 bit string versus if you feed it a random output of the pseudorandom generator has to be smaller in absolute value than one over any polynomial in n。

Okay。So。So basically you know what this is saying is that you know any polynomial time adversary A who does a really crappy job at distinguishing the output of the pseudoranom generator from true randomness okay why do we have to say that the difference you know between these probabilities is less than one over any polynomial。

 what if it were one over a polynomial， like if it were one over n squared， let's say， what could we？

What would be the problem then？Yeah。Exactly we could then amplify right when we talked about randomized algorithms。

 you know we talked about how like if you have any difference which is non- negligible by which we mean you one over a polynomial。

 like you know if the difference is one over n squared or something。

 then you just have to repeat you know like in that case like end to the fourth times and then just count the number of accepting runs and that will know because of the turnoff bound that will give you an excellent idea of whether you were in this case or in this case。

 and it'll do it in polynomial time， okay but if you could do that then you've distinguished the output of your pseudoran generator from true randomness you in polynomial time。

 which is exactly what we're trying to avoid。Yeah。Yeah， yes。Well。

 because the probability also depends on n， you know。

 F depends on n and the difference in these probabilities also depends on n。Oh。Yes。

Well well the idea is okay， so I'm sorry。Asymptotically okay so nag has to go to zero faster than one over any polynomial okay you know of course for fixed small values of n。

 you know the1 over polynomial might be smaller right I mean。

 I mean you could always you know as soon as you like like if you looked at the value of neg you know when n equals1 right you could always just pick a constant which is smaller than that and you could say a you know it's not smaller you know than that okay but you know what we care about is the asymptotic behavior。

😊，Yeah。Yeah。あ。That's right。 That's right。 That's exactly right。 Yep， yeah。

 what that means is what asymptotically means is for large a。Okay。Yeah。呃。Okay， well， if we say。

 you know， in fact， in this case they're the same thing。

 okay because if you say that you you have to be big O of1 over P ofn for any polynomial P then that's the same you know you're saying that you're at most one over any polynomial is actually the same as saying that you're less than one over any polynomial because there will always be some other polynomial that's larger than the one that you just named so that you have to be smaller than right。

😊，Okay， it's like it's like saying， you know， exactly the same with saying， you know。

 being less than any positive integer， you know， or being less than let's say any positive real number is exactly the same thing as being less than or equal to any positive real number。

They both mean that you have to be zero or less。Okay。Good。Okay， so。So， so the。

So there are a few questions about this definition right one is， you as I said。

 the amount of stretch is really small， how could we deal with that anyone。

 what if we had such a CPRG but we wanted to stretch n bits to two end bits。

 let's say or to n squared bits or some larger number， how could we do that？Yeah。

Just do it over and over again。 That's exactly right。 Yes， so， so what you can do， know。

 if you want to stretch。A seed of size N into more random bits is。Let's say that here's your seed。

 it's a string of n bits Okay， so you apply your pseudoranom generator to this seed you know。

 and that gives you a new string of n plus1 bits。I go like that， okay， and then。And you know。

 and then you could just， let's say take the first end bits of that output。

 feed it back into the CPRG， right， take the output。UYou know。That gives you some more random bits。

 right and take the first n plus one bits， sorry， take the first end bits of that。And so forth。

 okay and I'll notice that as we're doing this， you know we keep throwing off these sort of extra bits which can then be taken as the outputs of our pseudoran generator right know these n plus first bits okay because you know because these are not getting fed back in you know these should sort of intuitively be you know pretty just uncorrelated with everything okay now now there is a theorem that has to be proved here right you know so the theorem says that if your original function F was a pseudoran generator that you know mapping n bits to n plus1 bits then this construction also gives you a pseudoran generator in other words you know if I picked exit random and then I applied this iterative process and then I looked at you know the n plus first bits of of each thing that I generated then。

Then then that too will be indistinguishable from random by any polynomial time algorithm okay and we are not going to do the proof of that in this class because it's kind of messy and complicated if you take the graduate crypto class though you'll prove things like that but just to give you an idea like like everything else in theoretical computer science you at the end of the day it amounts to a reduction it amounts to a so and this is a very。

 very common thing in cryptography that you start with you could always just make up a cryptoyt or make up some scheme and say all right I think that my system is hard to break I think my systems intractable to break but problem is you stick your neck out too many times you're going to get burned sometimes。

You're going to be wrong that your thing can't be broken okay so what people try to do is is they try to sort of isolate you know the assumptions in as few places as possible okay so kind of like you know with what we did with NP completeness right when we said that you know you know okay there's one assumption you have to make you know P is not equal to NPp right and if you make if you grant that one assumption then we know that there's some you know hard problem in NP right but then that means that threeSaAT is hard because threeSa is NP complete okay but if threeSa is hard and that means that three coloring is also hard and if three coloring is hard then all this other stuff is hard okay and you know and then you get by this web of reductions you get that tens of thousands of problems are also。

Hard， so so NB completeness was sort of the intellectual model for you know complexity based cryptography right what people said is that you know let's just start with you know as few assumptions as we can like you know that know let's say that there exists a pseudorandom generator that's you know that's secure you know in fact we'll even go back further than that and we ask well what we can base that on okay but then supposing we grant that then you know we can get let's say a pseudoranum generator with a longer stretch you know that's a simple example and and how can we prove that the one implies the other well what you have to do is say suppose that we had an adversary that could break this stretched out pseudorandom generator okay know suppose that we had an adversary that could distinguish you know these bits from random then we could also use that adversary to distinguish。

The output of our original CPRG from random with some non-negligible bias thereby contradicting the assumption that we had started out with a secure pseudoran generator so that's the type of argument that you make and basically you the way I mean。

 the details are complicated， but the intuition is more or less what you would expect which is that like if every step of this process is doing something that's indistinguishable from random then the whole thing ought to be indistinguishable from random and conversely if this is distinguishable from random。

 there must be some particular step in this process that did something that was distinguishable from random and then whichever step that was。

 we can then use that to get a breaker for the original pseudoran generator。Laterter。Okay。

 that's the basic idea here。 so all right，So， so so so you know， and in fact， you know this this。

 this type of construction works to say， you know， if we had。

A pseudoran generator that mapped n bits to n plus 1 bits。Then we could use it。

To construct a pseudoran generator which would also be secure and which would map n bits to p of n bits where p is any polynomial okay so we could get any polynomial amount of stretch that we wanted okay now now for what we talked about last week know know proving that p equals B know you actually need something stronger than that you need a generator that would give you an exponential stretch that we take log of n or with log of n bits and stretch them mouth to n bits but you also have other things that are working in your favor there like you know you're allowed to use time which is polynomial and n in other words which is exponential in log of n and so it's sort of in net wind so that's a little bit you know for proving p equals。

That's a little bit of a different setting than the one that is relevant for cryptography。All right。

 but now you know let's let's suppose that you know we have this cryptographic kind of pseudorandom generator。

 the kind that maps n bits to you some polynomial and N number of random looking bits。

 you random eque bits okay let's now consider the question。

 how could that be useful for cryptography？Okay， so can anyone suggest we could use how we could combine that sort of pseudoran generator with the one time pad that we saw last week？

How couldSo suppose that we wanted something like the one time pad except that it shouldn't require such large key sizes。

 because that was the main inconvenient feature。福先生長。M哼。Yeah， yeah。

 that's basically right' you know the point is that you know the whole point of CPRG is that it lets us take a small number of truly random bits and you know and make them last longer okay stretch them out so you know be environmentally friendly with our randomness or something okay so so that's exactly what you can do and you can view you know most sort of modern private key cryptography as doing essentially this namely you know being the onetime pad except that we use a pseudo random generator in order to stretch out our randomness and make it last longer okay so to be。

😊，A little bit more precise about it。You， remember Alice and Bob， who wanted to exchange a message。

And we have some some plain text， what did I call the。嗯。Okay， let's call the plain text X。And now。

 let's say that x is some nbed string。Okay， Alice wants to send X to Bob， you know。

 Alice and Bob have a shared key。But the key is not long enough to cover the plain text。 Okay。

 it's like， you know， you know， imagine like some， some， some really skimpy article of clothing。

 It just doesn't cover， you know， okay， so。Let's say that k is only square root of n bits or something。

😊，Bob also had nose K。Okay， okay， now because k is not big enough， you know。

 we can't just use the one time pad， but what we can do is we can use a pseudorandom generator， okay。

 so let's say that。F of K is a string know which is quadraically longer than K。

 so F of K is n bits it and supposed to be indistinguishable from random by any polynomial time adversary。

 okay then what do you think Alice will send over to Bob anyone？Yeah， the XO， exactly。Okay。

 so the cipher text。This is the cipher text， I'll call it C sub K of x， okay。

 and then how will Bob decrypt the cipher text？Well， he'll just， you know， since he also knows K。

 he can also compute F of K， right？And then he can exclusive order with this x plus f of K plus f of K equals x。

😊，So that gives him the plain text back。Okay， and now。It is， you know Eve is in the middle here。

 okay now we need to make some kind of argument about Eve， yeah。Oh yeah， yeah， okay。

 I should have said that。 Yeah， so the pseudo randomum function itself。

 F that we should assume is public knowledge here。 Okay， so even Eve knows F。Okay。

 because that's just part of the specification of the crypto system。 right， So everyone knows F。

 even even Eve knows it。Certainly Alice and Bob know it。

 okay so everyone can compute F in you know and you know F F is polynomial time commutable so everyone can compute it okay。

 but you know， but now we need to make some argument to the effect that if Eve does not know K。

 then she's out of luck then you know she's not going to be able to sort of learn anything interesting about X。

 okay， how could we argue that anyone？AndAnd remember that essentially everything in cryptography goes via reduction。

We just。We need to。You know， we're allowed to start with the assumption that our pseudo random generator F is secure。

 and now you know we need to make a security argument for this enhanced one time pad for this cryptographic system based on that assumption。

Yeah。If there were。Y， yep。Yep， yeahup， yeah。That way。Distinguished。To the end。That's， yeah。

 that is essentially the argument that we want to make here right so okay so you do have to sort of say a little bit about about what it even means to break the crypto system okay because know the problem is that you know breaking the system its not even like a welldefined computational problem right in the sense like it's not even you know as we've specified it so far like it's not even an NP problem right Eve can't even be sure when she's successfully broken the crypto system versus when she hasn't okay but。

But you know， if we as soon as we change that， like as soon as we said。Like like， look， you know。

 I'm going to tell you something about x。 You know。

 I'm going to tell you that x is either the all zero string or the all one string， Okay， and。

 you know， and now。Eve's task is just to try to decide which one of those it is right okay and then you know if this were truly a onetime pad。

 then we would know that Eve would have no hope at that task right just purely information theoretically she can succeed at that task you know with exactly 50% probability and no more okay but let's suppose so let's suppose that Eve were succeeding at that task with non-negligibly greater than 50% probability right you know she were figuring out you know which of two possibilities x was you know with probability a half plus you know one over n squared or something like that。

In other words， you know， suppose that something like this were the case。 Okay then。Yeah。

 we could only conclude that you know by the very fact of doing that。

 Eve would be distinguishing the output of F from a truly random string， right or to be。

To be more formal about it。If I wanted， you know。아。Let's say that I just I had some strings。Z。

 you know， I had some end bit strings and I wanted to know whether they were truly random or whether they were the output of the pseudoran generator。

 whether they were outputs of F。 Okay， suppose that were my task。

 then the point is that I could use Eve to help me accomplish that task Okay， I could。

I could feed Eve。You know， these sort of strings with 50% probability and these sort of strings with 50% probability and I could ask her to determine。

 you know which class they were in， you know， did I exclusive or Z with the all zero string or did I exclusive or with the all one string okay and if Eve were're solving that problem non-negligibly better than chance then I would know that Z was the output of a pseudo random generator rather than being truly random and but then that would contradict the assumption that we started with you know an F that was a secure。

 you know， CPRG satisfying this definition yeah。Yes， yes， we are。Yeah， okay， good。Yeah。

 so kind of the I should have made this explicit， thank you。Yeah。

 so kind of the central assumption that we'll make for the entire rest of the unit on cryptography is that Eve is polynomialally bounded。

 okay， Eve can only spend polynomial time trying to break the system。You know now。

That's not all we'll have to assume， like we'll also have to assume that p is not equal to NPp。

 for example， so we'll also have to assume something about the limits of what can be done you know what Eve can do in her polynomial amount of time but certainly you we're gonna to have to assume that Eve is limited the polynomial time and why will we have to assume that。

 well， because otherwise， we're just faced with Shannon's key size argument from last week if Eve has has exponential time then she's just going to be able to break any of this stuff Okay by you know。

 for example， just as looping over every possible key K you know and seeing whether you know she could just if Eve had an exponential time。

Then she could just ask the question， you know， does there exist any key K。

 such that Z equals F of K， right， You know， when that's an NP question， She can， you know。

 she can solve it if she has exponential time。Okay。All right。So this was all。

 you know a little bit abstract， so I should give you at least one concrete example of a CPRG or something that know that is believed to be a CPRG anyway。

So。Okay。So I told you that the。The linear conruential generator is not good enough for cryptographic purposes。

 but there's sort of a variant of it。Whi might be good enough and that's the Blum b S generator。

 this is from the early 1980s also and the way this one works is。

You pick a composite number n which is a product of two enormous prime numbers okay which you know let's say you've generated and then you pick you know and this is just considered like you know maybe maybe this is public information you know so some trustworthy source like the NSA has just published the n and P and Q that you can use by the way you this sort of thing has been a serious problem in the past okay you know or some you know but you know or you go and generate these yourselves one under the other okay and then and then the seed that you start with is going to be some X which let's say is relatively prime to n okay。

And now。Basically what you do in this generator is that you just keep doing repeated squaring。

 so you map x to x squared and then you map mod n， I should say。

 so everything is going to happen mod n here。All the numbers are modo N。Okay， if you map x mod。

 you know and that prevents them from growing too enormous， okay。

 you map x mod to x squared mode and that to x squared squared or x to the fourth mod。And that， too。

X squared， squared， squared or x to the eighth mod n。

And so forth okay and then you just output the least significant bit of each of these okay stop with the you know just like the you know the one's place I guess the least significant bit of each one of these and that gives you your pseudorandom string starting from X okay so you know like like like you know100 other pseudoran generators that you could make up you know you could just mess around with things and make something up you know and it sounds kind of plausible you know can you tell that from random I can't you know you know looks kind of random you know can you can easily you know come up with like you know1 thousand such things right that's sort of you know as common as dirt but but b b and tube where we're able to prove something that made this one a little bit more interesting okay the thing that were able to prove was once again。

So what they showed was that if you have an adversary who can get any advantage in distinguishing the least significant bits of these guys from total randomness meaning they can guess they could figure out which it is with a half plus non negligible success probability。

 say or let's say。😊，Or an equivalent way to put it is that they could。

 if I gave them 100 of these bits， they could guess the next one。

 they could guess the next bit with some non negligible probability of success with some you half plus non- negligible probability of success。

 then you could actually use that adversary to factor n。Okay。

 so they show that this gives you a secure pseudo randomom generator。

 you know whose next bit is totally unpredictable to any polynomial time adversary。

 even know given all of the preceding bits， you know。

 unless that adversary is also able to factor in。 so if you believe that factoring is hard。

 then what this showed basically is that。If you think that factoring is a hard problem。

Then there exists。Cryptographically strong pseudoranum number generators。Okay。

 so they proved that conditional statement。Okay， and you' again。

 we're not going to do the proof of it in this class， it's in a crypto class。系。So。

So let's discuss a more general question， which is you know what is the minimal assumption that you need in order to have a cryptographic pseudo random generator。

 which is you know which once you have it is sort of a major workhorse for cryptography so what Blum blum in tube showed is that you know if you assume that factoring is hard then that's good enough okay but now you know the stuff all the stuff that we talked about in the complexity part of this course becomes relevant right because。

If you recall， which you know， I'm sure you do， factoring， we don't think is an NP complete problem。

Right。Factoring， we think is just one particular problem in this intermediate realm you know between P and NPp hard so so which means you know factoring could be in P and that you know that you know it could be for all we know that factoring is in P just because of know one particular clever algorithm that has yet to be discovered you know。

 and that would not cause p equals NPp as far as we know or any other kind of disastrous theoretical consequences it would only have disastrous practical consequences okay so。

So you might say， you know， wouldn't it be great if？We could have。A pseudoranom generator。

 which was secure only under the assumption that p is not equal to NPp right。

That would be awesome that would be the gold standard of CPRGs。😊，Allright， so this so this is。

 this is a question that that one can ask， you know。

 that people did ask at the very beginning of of modern cryptography。 But okay。

 so so the first thing that we should do is we should say。

 why at the very least do we need to assume that P is not equal to NP P if we want to have cryptographic PR Gs。

Yes。呃。Oh well， well yeah， but there could be other CPRGs that are not based on factoring， right yeah。

嗯哼。😊，Yeah。嗯哼。😊，Yeah。Exactly that's exactly right everyone here that it's because the see a seed is a witness that would be like a one sentence proof you know that we're gonna to have to assume p is not equal to NPp suppose that P were equal to NP in such a world I claim that we could certainly not have cryptographic PRGs okay because you know if p equal to NP。

 then we could always just take the problem， you know does there exist a seed that leads to this string that I've observed and that's an NP question but then because p equals NP we could then solve that in polynomial time so then you know in that world we could always in polynomial time just know whether there is a seed that would weed the CPRG to output the string that we're seeing okay but you know that you know if you know you know if there is a string that you if there is a seed that wes the string。

😊，That's really， really damn good evidence that your string was output by the CPRG because yes。

 while it's possible that a random string would just so happen to satisfy that property。

 the probability of that is astronomically small。😊，I mean， we could calculate it right。

If the CPRG is stretching， let's say you know1000 bits to a million bits right then there are two to the million you know output strings but there's only two to the thousand that are possible outputs of the CPRG so if you know I give you like a random looking million bit string and you find that there is a seed that could have led to that well then know the probability that that would have occurred just by chance。

Is then like two to the thousand divided by two to the million， right， that's a small number okay。

That's you know， so that's effectively a proof that this string was an output of the CPRG。

 certainly that gives you an efficient you know algorithm that distinguishes with non negligible probability okay。

 so we conclude that in a world where P equals NP， there can be no CPRGs。😊，All right， okay。

 so but now the other part of this stands， you， could we have CPRGs that were secure under the sole assumption that P is not equal to NP？

And。Well， the short answer is like many other things in this course， this is an open problem。

No one knows how to do this， people have thought about it for 40 years or so。😊。

What we what we do know is that you know， you know like we you know very。

 very new techniques you know would be required for this。

 you know none of the existing NP complete you know none of the currently known NP complete problems seem to you know have the right properties to base a CPRG on them and they're sort of well we'll we'll get into you know maybe a little bit later what the issues are。

 but but you know one issue is that sort of sort of the most obvious issue you could say is that。

If you want to secure CPRG， you know it's not enough that your problem just has some hard cases it's not enough that there exists hard instances of your problem you know you really need that are random instance is hard okay if you look at the definition of a CPRG right it's based on probability you really a random you output of the an output of the CPRG with a random seed has to be indistinguishable from a random string and so it's not enough like that there is some outputs of the CPRG for which it's hard to work backwards and figure out the seed or whatever that has to be true for essentially any possible value of the seed and that's a stronger property than just saying that there are hard cases of your problem so certainly at the least beyond peanut equal。

We would want that there are some N problems that are sort of hard in the average case。

 but then we even want more beyond that。Okay。嗯。So it actually is possible to articulate exactly how much more you need to assume in order to get a CPRJ and therefore。

 let's say， private key cryptography， with small keys。And so we now know the answer to that question。

 Well， you know， since the late 1990s， I guess， you know it' like the。Culmination of， of， of。

Of of a lot of work。 and and the answer is that if you want a pseudoran generator， you know。

 a CPRG and therefore like secure， you know， you know。

 cryp cryptography with small keys of the kind that we were talking about。

 then it is necessary and sufficient that there exists what we call one way function or Allf。

 Okay so what's a one- way function。So one way function is a function F that maps an n bit string to some string of P of n bits。

 you know， where P is some polynomial okay， and once again。You know。

 there's an implicit dependence on end here。 Okay， So really。

 we mean like a family of such functions。Such that。Two properties hold。First。

 F is computable in time polynomial and N。Okay， you know just like for PRGs。

 the second requirement is that you know while F is easy to compute it has to be hard to invert in some sense okay so what does hard to invert mean well you know if F were injective you know x led to a different f of x。

 then all we would have to say is that given f of x。

 it is computationally intractable to find x or there is no polynomial time algorithm that finds x with any non-negligible probability right so that that doesn't quite work if you know in the situation where you could have multiple x's mapping to the same f of x then is it okay but what we can say that it should be hard to find any pre-image of F of x you with any non-negligible probability。

😊，Okay， so the way that the definition is。Usually written is that we say for every polynomial time algorithm。

 A， which we call the adversary， the probability。Over。A random andbit string X。That F of a of F of x。

Equals F of x。Is negligible。Okay， so this requires you know a little bit of thought maybe what are we saying here right basically you know that I mean basically it's saying exactly what I just said in words。

 which is that you know the probability that a finds succeeds in finding any preimage of F of x has to be negligibly small the way we say that is that you know I pick an x。

 I compute F of x， I feed F of x to the adversary and now the adversary tries to find any x。

 you know F of which maps to the same thing you as the F of x that I gave it。😊，Okay。

That's what it's saying， right？Okay， so so that's the definition of a oneway function。

 something that is easy to compute but intractable to invert okay， by the way。

 well one thing I should say is that like in all these crypto definitions right like like we you know conventionally we say that the probability of success has to be negligible has to be you know less than one over any polynomial okay。

 in fact， what you really want in practice is that the probability of success of the adsary should be one over exponential。

😊，You want them to have an exponentially small probability of inverting the function。

 so in other words， that if they want to invert the function with a good probability。

 that should take them exponential time。That's what we really want。

 but that it should take the more than polynomial time as just sort of like the bare minimum that we would require in this business。

Okay， so now let's try to organize these you know all these concepts that we've defined， okay。

 first of all， so suppose that we wanted a one way function then what other assumption would have to be true for that to be possible。

 well， would we need P equal to NP？Suppose that P equald N P。

 could you then invert any one way function。Well， what would a witness be for inverting a one way function？

Yeah， x， for example， right， you could if p equal to NPp， then given f of x。

 you could always just say you know what is a string you know that maps the F of x， right。

 what is a y such that f of y equals F of x？That's an NPp question， right？

And so then you know that would be solvable in polyial time if p equal would NP， if p equal NP。

 then certainly you could efficiently find pre imagesages for anyF and so one way functions would not exist so we can say。

You know， if there exists cryptographic pseudoranom generators， then we need P not equal to NP。

 and likewise， if there exists one way functions， then we need P not equal to NP Okay。

 so then that just leaves the relationship between these two concepts。U。All right， well。

 there's one direction of this， at least that's quite easy okay。

I claim that if there exist pseudorandom generators， then there also exist one way functions。

Can anyone explain to me why that implication holds？If let's say that F is a pseudorandom generator。

 then what would then be an example of a one way function？Yeah。Sting。 in fact。

 we wouldn't even have to do that。 in fact， it's even simple。Yeah。

 so so let's say that F is a pseudoranom generator， oh okay， so maybe I should have clarified， yeah。

 okay， that could work， you know， when I say P of n。

 I mean I mean you know like the output has to be at most polynomly large。Right。

The output could also， you know， of the CPRG could have end bits。

 It could even have fewer than end bits。 You know， that's， that's totally fine。 Okay。

 so I claim that actually。If I have a function F that is a pseudoranom generator。

 then that same F itself is also a one way function just you know。

 so I just get a one way function totally for free， Okay， why is that。

 Okay why is a pseudoran generator also a one way function。You know， all of these things。

 you have to mentally translate it into the contrapoitive direction， okay， you know。

 just take what I say and say， well， suppose that warrant't the one way function then what would follow。

Yeah。嗯。Findd。Yep， and a such that。Yep。Yeah， exactly right if I had any non negligible probability of guessing the seed。

 right， if given the output of my CPRG， if I had any non-negligible probability of working backwards and finding the seed。

 then that would give me a non- negligible probability of distinguishing my string from a truly random string because I would just you know。

 look you know see you know if I can find the seed if I can， then I know for sure that my function。

 you know I know essentially for certain that that my string was not truly random。

 you know if I can't find a seed， then I could just guess but that will give me some non- negligible advantage in you know figuring out whether my string was generated by the pseudorandom generator or not。

 okay which means that actually F would not have been a CPRG。 so if F is a CPRG。

 then it must be intractable to find the seed with any non negligible probability。

 which means that F is then also a one way function。Everyone people see that。Okay， good。Okay。

So the much more interesting direction was starting from any one may function。

 can you construct a pseudorandom generator？Okay， and this was。

An open problem for at least 20 years okay and you know what people managed to do was like more and more special cases of this okay。

 so for example， so Yao， you know， another of the things that he won the touring award for。

 you know in the early 1980s is that he showed that if you have a，A one way permutation。

 So if you have a one way function， which is also， you know， one to one。 It's also a permutation。

 then you can use that to construct any you， you can use any such。

 such such F to construct a pseudo random generator， okay。So。You know， and then people you know。

 relax the assumptions on the， you know， that were needed on the one way function more and more until finally。

In 1997， so Hatad and Palyazto， Levin and Ruby， nicknamed Hill， proved the Hill theorem。

 okay which says that。Well， indeed， this is true。 given any one way function。

 it is possible to construct a pseudoran generator。 Okay， out of it。 Okay， now， just， to show。

I guess to give some sense of the subtlety of the question， let's first ask。

 is it true that if F is a one way function， then F is also a pseudo random generator。

Does anyone have a counter example to that Okay let's you know assume that okay let me put it this way。

 assume that a one way function exists， then can anyone construct for me a one way function that is not a pseudorandom generator？

Yeah。呃。Oh， yeah， okay， good。 So， so， so like F， yeah， right that's actually a very good point。 if。

 if， if we had like a pseudo random permutation， right， then that doesn't increase the。

 the length at all。 So that's， that's just not a pseudo random generator， right， Okay。

 suppose it suppose it even does increase the length。 Okay， then still。

 how could we make something that's， that just not a pseudo random generator。😊，You know。

 I'll give you a hint and you can do whatever you like to mess up its pseudo randomness while preserving that it's a one way function。

 yeah。Perfect， perfect， exactly。 Okay， suppose that F is a one way function。

 then F F of x padded with a whole bunch of zeros is an example of a one way function that is not a pseudoran generator okay。

 because this output is very， very easy to distinguish from random because you just look to see if there's a whole bunch of zeros at the end。

😊，Okay， so this shows that you know this is like a kind of a silly example。

 but it proves the point that you know that pseudo randomomness is a stronger property than just being one way。

 right it's like you know being one way on steroids or something okay it's you know not only do you have to be hard to invert。

 but there have to be sort of no regularities whatsoever that you can detect in the output。😊，Okay。

 so。U。Okay， so， so so so they said， you know they managed to do this， right。

 it's a very non-obous construction。 you have to， you know， starting from the oneway function。

 you have to engineer a whole bunch of intermediate objects that you know get closer and closer to pseudo random and then you combine them in some complicated way that gives you something where you can then prove that you now have a generator where if you could distinguish the output from random with any non- negligible advantage then you could use that in order to invert the original oneway function that you started with with a non- negligible probability Okay's that's what they did and the parameters were like really bad where like you know if you started with like a。

A。Let's see like like in， I think if you started with within with with with， with a key or or sorry。

 if you， if you， if you started like out with with within， with an adversary， you know。

 that could that could。That could break the pseudoran generator in end time。

 then would only get you would get an adversary that could break the one-way function and I think was like end to the 20th time or something huge like that。

 okay， it since been improved to make it tighter， but this was an example where you had blowups which were polynomial but which were quite enormous。

 at least originally。Okay， so so now you know the whole question of， you know。

 can you base private key cryptography， you know on like p equal to NPp， you know。

 is reduced to the simpler question of you know can you base one way functions on P equal to NPp right are there so we know that like factoring。

 you know so in some sense the hill theorem was like a very。

 very big generalization of the bbl sub generator because you know factoring is in some sense。

 like the original example of a one-way function you know easy very easy to multiply numbers。

 very very hard to go in the opposite direction and factor know that's not I guess it doesn't strictly satisfy the definition because you know we start have to start out with some random prime numbers rather than just you know a random string of bits but you can you can massage it a little bit to get it。

To get a one way function， which is based on factoring。Okay， so。

So so Blum bum Sch said that you know this specific oneway function factoring gives you a pseudorandom generator。

 Hill said that in fact any one way function gives you a pseudo randomdom generator and then so sort of a modern question is you know does P not equal to NP give you a one- way function okay and that you know this again we don't know the answer to I mean if we did we also would have known the answer to this other question right but。

😊，So on PSet6， I think you'll prove something that basically says。

 you know the existence of oneway functions is equivalent to there being NP complete problems that are hard to solve like on average。

 even if you know， like when you generate the random instance of the NP complete problem。

 you at the same time can also generate a solution for that instance。

Okay so I called that in the PE a puzzle generator so the existence of one-way functions is equivalent to the existence of puzzles that are hard to solve with high probability and yet the person generating the puzzle actually knew a solution to it when they generated it。

Unfortunately， as far as anyone knows， that may be a stronger property。

 even just in there being NP complete problems that are hard to solve on average。😊，Okay， right。

 you could imagine a world where there are NP complete problems that are hard to solve and they're even hard to solve on average。

 but you know， when you generate them， you yourself can't know what the solution is。Okay。So。

All right。OkaySo all of that was you know this is more or less what I wanted to say about private key cryptography。

 which simply means you cryptography where Alice and Bob can agree in advance on a key so if you want private key cryptography which is perfectly secure information theoretically secure than the one-time pad does that but but then you need a key that's as long as the message if you want a key which is shorter than the message it is necessary and sufficient to assume that you have oneway functions available a oneway function is like well you certainly need that P is not equal to NP if you want those to exist but in fact their existence is a stronger assumption than that you know unfortunately you as soon as people started using。

Networks they started using early forms of the internet in the 1970s。

 you know it became apparent that private key cryptography was just not going to scale very well you know it's okay for spy agencies maybe that can you sending these keys but if you imagine and people already were imagining this in the early 70s if you imagine that you had some hypothetically let's say some big network of people and they were buying and selling things you and sending their credit card numbers over this imagine the network right then。

You know if you're you know ordering a book know or something from Amazon it's not going to work if you know you have to first agree on a key like what does that mean know you're going to meet like at 4 am and some dark alley with some you know employee from Amazon and you're going to say all right all right fine if anyone you know find just just between the two of us you know password it is going to be rosebud know we're you know that' that's going be the seed that we're going to use for you to seed our pseudo randomum generator to use a onetime pad for okay that'ss just not going to scale very well right you know there's just not enough you know Amazon employees。

 not enough dark alleys so so somehow you know you know what we're going to need is a form of cryptography that know that can be done entirely over the internet you know including the key generation process。

you know， and that like you know amazingly in thousands of years of cryptography。

 like people had like not even asked the question you know of whether such a thing could be possible。

 okay but you know as soon as they did start asking the question， you know。

 it turns out that you know， under the right you know it's again it's just a matter of making the right computational hardness assumption。

 okay， you know， and if the right problems are intractable then then yes。

 sure that's possible okay and。😊，Okay， so this leads to public key cryptography。

 which is maybe like the you know the most， you know like of all the things that you know theoretical computer science sort of contributed to the world。

 this is maybe the one that's had the most obvious impact of any of them， okay。

And the intuition for how could public key cryptography be possible is often explained by by saying。

 look， suppose that Alice and Bob were just trying to exchange some physical items in some padlock boxes and。

You know， Alice can put a padwalk on her box and send it to Bob， okay， but the problem with that。

Is that if she does that， then you know， Bob is not gonna know how to open it。 Okay。

 so what could Alice do。 Well， she could just， you know， tape a key to the side of the box。 Okay。

 that's not a very good solution， right， you know， imagine that it's the Stazzi or something that's。

 you know， that's delivering the mail。 Okay， if they， you know。

 if there's some easy way to open the box without leaving traces of what they did then they're going to do it。

 Okay， so they would just take the key and open it， Okay， so， so what else could you do， Well。

 you know， you could have。You you could have。You could have you could have Bob send you know send a padlock over okay so in fact there are you know are two you know there are a couple different ways of doing it and they'll correspond to the you know the different public key cryptoyss that we're going to see on Thursday okay。

 so one solution would be that just。Bob first sends his pad his padlock over okay and then you know。

 Alice uses Bob's padlock to lock the box， sends it over， and then Bob knows how to open that right。

 you know， and then you know everything has just has been sent。

 you know we didn't need any secret you know， meeting between them in advance okay。

 you know another way to do it would be that。Alice first sends a box that's locked with her padlock then Bob he doesn't know how to open that box so what does he do he just puts an extra padlock on it he locks it even more he locks it with his padlock too okay so now Bob sends back this box that now has two padlocks on it okay and then Alice would given that would take off her padlock which at least she knows how to do send that back to Bob and then Bob takes off his padlock okay this one it's kind of like you know this puzzle with like the wolf and the goat and the cabbage we have to cross the river and you know that one you know you need to send the box back and forth and at no time have have the Stasy slash postal service be able to read it okay so this first system you know if we now replace the padlock by some by some encryption by some。

mathematical version of a padlock， then this first system is going to correspond to the RA crypto system okay which was。

 you know this is Revesh Shamir and Adelman， they were here at MIT in the late 70s when they invented it okay and the second one will correspond to the Diffy Heman crypto system which。

Actually predates RA by a couple of years Okay， as it turns out。

 both of these systems were actually known earlier than that。

 They were known in the So this was like from。😊，啊。78， this is from '76。

 this was did anyone know where RSA was first described to the world， how was it first published？

It was in Martin Gardner's mathematicalthe Game column in Scientific American it's like you know this is like a really cool math puzzle or something that's RSA was first announced yeah so okay but before this in the early 70s it turns out that both of these cryptoystems were known to the GCHQ which is like the British version of the NSA the problem with working for the NSA or the GCHQ was even if you're the first to discover something know you can't publish it but that was declassified in the 90s that they had known this all right so on Thursday we'll explain how Diiffy Heman and RSA work and then how you can use them to do some interesting task actually to achieve some interesting social goals that you might not have thought。

😊，つボ？Oh。好他多。