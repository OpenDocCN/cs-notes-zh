# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p13 P13 mar31 -BV1Dao8YQEEn_p13-

Okay， so welcome back， I hope you had a great break。

So probably don't need to remind you the midterm is on Thursday。

 so I think you guys are actually going to have a leg up because you're the ones who arrive on time I would。

You the problem is you know I can't give any extra time because you another class you know starts right at 11 so you it's a good idea to get here at 930 on Thursday okay so you are allowed to bring a onep cheat sheet to the midterm know you can write on both sides。

 and I actually think that you know making up a cheat sheet is itself you know a very good way to review the material so if if you've done a good job you know making it up。

 you there's a good chance that you won't even have to refer to it anyway。

 but but you're allowed to bring it and the TAs will be having a review session tonight at 730 32155 you will' also be。

Be having our usual office hours like you know I sort of moved my office hours to Thursday。

 but you know， I'll have office hours today， you know， in light of the exam anyone once sort of。

I really tried to get the graders to have PSE3 graded by today。

 but some of them were not able to pick it up before leaving for spring break。

 so unfortunately we don't have that back yet， but we'll have that back by Thursday。

Any questions about that though？Okay， hi。😊，All right， so last time we sort of ended on a high note。

 I guess we define what is the P versus NP problem。To remind you， here's P， here's NP。😊，You know。

 it's the question of you know， can every problem you know for which you can efficiently verify a solution also have a solution efficiently found。

 okay， and you know I think it's one of the biggest questions ever asked。

You and today you we're going to see the theory of NP completeness。

 which is sort of a further wrinkle on the P versus NP story。

You I should first say a little bit about the importance of the question and about what we believe about it。

 and things like that know I mean we talked before break about you like the motivation that Gardle had for example and then thinking about this question which was can you have just like a general purpose procedure to to automate the finding of mathematical proofs this would be very useful for doing PSES or for the midterm for example right can you but you and touring you says well no there's no general purpose decision procedure for the inshtidings problem but then we say all right。

 fine but we only care about proofs of，reasonablea lengths。

 you proofs of in most end symbols and then we say， well that well in that case。

 of course there's an algorithmic procedure to find you such a proof if it exists。

 namely just enumerate all of the possibilities you there's only a finite number of them there's only two to the n of them or whatever so just try every possible string most of them will be meaningless jumbles of characters but if one of them is a proof then the very definition of the proof is that you'll be able to recognize it when it does show up okay but then you know we sort of quickly realize know that's not a very good solution at all because that takes you even if for a reasonable n like a million or so that two to the million power is astronomical there's just too many possibilities to to even really conceive of trying them all。

So the question is is there a general purpose efficient way to solve this kind of problem okay but you I think you know if therere actually where you know so what we saw last time is NP is the class of all the problems that have polynomial time verification algorithms right that's the definition okay we actually saw two different definitions of NP before the break one is that it's the class of languages that can be that are accepted by some nondeterministic polynomial time touring machine that was the first definition the second definition was that。

It's the class of all the languages for which there is a polynomial time verifier that such that whenever a string is in the language。

 there is a polynomial size proof of that fact， which you know when presented to the verifier will cause the verifier to accept okay。

 but if you on the other hand， if your input is not in the language。

 then there is no purported proof that will cause the verifier to accept okay so it's both complete and sound。

嗯。So you know and then we saw a last time that these two definitions of NP are equivalent okay so basically you know we're just talking about you know any problem for which you know you can program your computer to recognize an answer efficiently。

 you if an answer is given okay so that certainly includes like almost all of modern cryptography okay you know you know almost every cryptoy right has the property that know if you've broken it then you know that you've broken it。

 you that you can program your computer to you know to recognize that yes this is the correct private key。

 you know， you know you it does correspond to this public key I multiply the numbers or whatever it checks out you know there is cryptography that would not be affected even if P equals NP like the onetime pad okay but you know。

😊，That kind of cryptography inherently requires very very large keys。

 we're going to say we're going to do a whole unit about cryptography where we're going to explain this in more detail but basically all of the cryptography that we use on the internet certainly would be broken if P equals NP and if the algorithm you have to add the caveat if it were actually efficient if it were and cubed or something rather than end to the million。

😊，You know now let's be careful about what I said， right。

 I'm not saying that if P is not equal to NPP， then all the cryptography that we use is a。

Okay that's you know that's a different question right as we're going to see later on you know if you want secure cryptography。

 you know you've got to stick your neck out and you've got to make you know even stronger assumptions than P is not equal to NPp you know as far as we know today okay I mean you know you need stronger mathematical assumptions than P is not equal to NPp you know you also need you know sort of nonmathematic assumptions like that you know there's no bugs in your code you know there's no you know side channel attacks or you know that the eavesdroppers not able to just you chop down your door with an a or something and you know just know steal your data that way right so I mean I mean cryptography you know you're always making know assumptions about what the attacker can and can't do okay but certainly you know a necessary assumptions for any of the types of cryptography that we use today is that P is not equal to NPp。

😊，嗯。Okay but I think that the okay and then you last time we discussed a whole bunch of examples of different NP problems right so there are many。

 many， you know you know I mean the entire field of operations research basically right is about situations where you have a whole bunch of constraints when you're laying out a chip or when you're planning the MIT class schedules or something you know you have a whole bunch of constraints。

 maybe you won't be able to satisfy all of them， you know some people will inevitably have class conflicts and have to drop or you something or whatever。

 but you know you want to satisfy as many of the constraints as you can and and if I just ask you is there a solution that satisfies that would say that violates it most k of the constraints then I'm asking an NP questions？

So so that gives like a huge number of examples of problems know of this sort but let's talk about some less obvious examples maybe so here's some you know I think you know there would also be sort of significant implications for AI and for machine learning why because you could consider the problem like let's say。

😊，You look at all the you know historical stock market data right and you know you feed that as input to a program okay now to say you know predict the you know the prices of stocks you a year from now that's not like a computational problem because we haven't mathematically defined it you know that's just a problem of predicting you know something that's actually going to happen in the real world right I haven't mathematically you know told you how to how to get the answer to it okay but what we could do is we could say something like you know I want you to find a very you know very compact model。

 the most compact model that you can that successfully explains all of the past stock market data okay and then I'm asking a mathematical question I'm asking you know you know among all of the statistical models within a certain class。

 let's say you know which one does the best at explaining all of the past stock market data。

Okay and you know and then that's something where you know you can imagine okay once a model is given。

 then you your computer can very easily just check how well it does。

 but there might be an astronomical number of different parameter settings in your machine learning model and and it's not obvious how to set them if it's a neural network for example。

 you have this astronomical number of different ways of setting the weights the whole problem in machine learning I guess it's new name is deep learning but and all of this stuff the whole thing that Google deals with today with machine translation and things like that is how do you set the weights in your neural net or your deep net or whatever know and there's a huge number of ways to do it and there are algorithms that can often do a pretty good job but imagine if you。

You could just find the optimal way of setting the weights。

 you know as long as you could recognize how you know like a really good setting of the weights when it was found。

 imagine if that fact alone meant that you could program your computer to efficiently find you the optimal setting of the weights。

 okay I think that would have that would have very。

 very significant implications for machine learning and for AI you know。😊，You know。

 people have even made the point that well you know like it could be that you know like maybe P would equal NPp。

 but there would be you know we would only know an end to the fifth algorithm you know or one that was not only just you know on the borderline of being efficient okay but if that turned out to happen you know then there's one very clever thing that we could do you know we could use our just marginally efficient algorithm and we could ask it itself to find us a more efficient algorithm okay we could say。

 you know can you find an algorithm for NPp complete problems that takes only n cube time and can you find a short proof that it works you know and that would be a type of question that we could now answer an end to the fifth time you know if such an algorithm exists then our algorithm can help us find it okay so you know you could you could get you know a sort of recursive self-improv right so this would have some very very loopy consequences you could say okay and so。

So you know the conjecture of most computer scientists is that P is not equal to NP why is you know well。

 you know， so you know people there's a guy named Bill Gasarch has actually done a Paul。

 you know as Pauled people's opinions about you know P not equal to NP or and I think like 90% said that P is not equal to NP you know and the ones who said P equals NP you know we're basically saying it to be contrary。

 you they were trying to make the point that that no one really knows for sure but so we're going to see。

Examp， okay， I mean， I mean， you know， the simplest thing you could say is that it just。

 it sort of sounds too good to be true。 right， you know， you could say that like if you know。

You know， it sounds like building a perpetual motion machine or like you know you know sending messages faster than light or something okay and you know and it sounds like you know if there were such an amazing algorithm then you know then then there's sort of a mystery as to why it would have alluded discovery for so long you know you know you know now now you might say but all right。

 but there's you know an equal mystery on the other side right if p is not equal to NP and why is the proof you know allludeed discovery for so long but that we actually know something about right it it's very。

 very， very hard to prove negative statements you know to rule out any possible algorithm to do something I mean you know you saw the example of the unsolvability of the halting problem right and that was a spectacular example where you know where we actually could just rule out an algorithm and just a completely clean you know abstract way using this sort of。

referential argument but that you know in most cases。

 you know you ask more detailed questions like you know is there an n squared algorithm for this can you prove that there is no n squared algorithm you know for multiplying matrices or whatever that you know any algorithm must take at least end the 2。

2 time right are know these are unbelievably difficult questions you know because you have to understand the space of every possible algorithm that that there could be for this problem so so in general it's much harder to prove lower bounds than than to discover algorithms。

😊，So， you know， but then in addition， you know， what we're going to see later on is that there are。

 you know， lots and lots and lots of examples where you know。

 what we'll see like an algorithm where like if you could just improve the parameters of this algorithm slightly or just。

 you know， make it work like in a slightly different case than the one that it works for。

 then it would follow the P equals NP。And in fact， the whole theory of NPp completeness is going to give furnish like thousands of examples of exactly this kind right where something just works out a certain way and if it worked out just a little bit differently then p equals then P would equal NPp and so one way that you could interpret this phenomenon is like wow。

 maybe maybe p does equal NPp then because there's all these thousands of ways where you you just have to do one thing and then it would follow right。

 but the other way of looking at it is well wait a minute。

 you know if there's all these thousands of things that if they were just slightly different then p would equal NPp but none of them ever are slightly different in that way then there must be some explanation for that and the simplest explanation that would spring to mind would be that P is not equal to NPp so those are just some of the argument you I don't want to know。

😊，I don't want to impose a dogma on anyone， you know you're free to believe P equals NPP if you want。

😊，But you I don't try to infringe on matters of conscience。But all right，You know。

 the other thing that you could ask is， you know， if， if P， P is not equal to NP P， then you know。

 then then why， why is it so hard to prove， You know， you know， can， can we expect to prove。

 you know， in the， in the foreseeable future， Okay， you know。

 there are even people who speculate that。Maybe this question is independent of the axioms of set theory right I mean you know we saw before you know Gerdel taught us right that you could have a well-defined mathematical question。

 but you know that has no provable answer within you know any framework of axioms that you choose to adopt for it okay or rather for every system of axioms。

 there will be questions that those axioms cannot answer one way or the other so。

You know now it's one thing to sort of know that that can happen for like statements that assert their own unpability。

 which is Gerdle's example you know or you know then it's like like come on you know or you know or the consistency are asking a formal system to prove its own consistency you know these are you could say that these are in some sense meta mathematicaltheal questions like yes。

 you can express them as purely arithmetical questions。

 this is what Gerdle showed okay but they're not the type of questions that we tend to arise and like ordinary math research you know。

 if you aren't looking for unprovvable statements you probably wouldn't find them okay so you know。

 but then you know we also saw earlier a little earlier in the course that know there were examples of questions that people actually wanted to know the answers to like the continuum hypothesis you know is there any infinity which is greater than the infinity。

Of integers， but less than the infinity of real numbers Okay that was something that Canther worked on。

 many people worked on。 People wanted to know the answer to that。 you know。

 it's like one of the most basic questions you could ask about infinity and the answer turns out to be that the you know our normal axioms of set theory cannot answer that question one way or the other okay either answer is equally consistent Okay but but then you know if you wanted to make excuses。

 you could say， well look that was kind of a weird question about trans sets right that wasn't you know a question about just sort of ordinary things like like integers or touring machines where you know where we're even you know right I mean I mean。

like you could say like if you wanted to， you could say in retrospect。

 you know this question of the continuum hypothesis。

 you know maybe even wasn't you know a perfectly well-defined question maybe it doesn't even have a definite answer theres no reason why it has to have one right because you know what does it mean for these like trans sets to exist or not exist you know you know it's sort of a plaonic thing right you could say you know they could either exist or not exist know relative to a particular set of axioms you know in one set of axioms you know it can prove that they exist and another set of axioms can prove that they don't exist but you know but the sort of the question you might argue has no meaning apart from the particular system of axioms but then you know there are questions like P versus NP which are really not like that right because you know P not equal to NP just says there is no algorithm you know。

that solves an arbitrary NP problem in polynomial time or rather you know there exist problems in NPp you know there exists language is L in NPp for which there is no touring machine M such you know M decides L and M's running time is bounded by the length of its input raised to some power that's a very concrete question like know that machine M you know it either exists or it doesn't exist just like you could say like a counterexamp to the Goldb conjecture know either exists or doesn't exist right it's not queer even what it would mean to say that well you know the answer could be one thing and one axiom system and another thing another no there's an answer right but the fact that there's an answer doesn't mean that the answer is provable in your favorite set of axioms right what Garll tells us is the truth and provability or too different。

Okay， so yes， it is conceivable that。You know that the answer to this problem could be you know。

 could be independent of set theory you know that we could never know it okay you。

 and actually you know then you know if that were the case there would be a further question which would be could we at least prove that it was unprorovable could we at least prove it's independent or would that question also be independent and you know and so on forever okay but you know I think that most of us would regard that as a pretty defeatist attitude right because you know you could sort of say that about any mathematical question that we don't already know the answer to right well。

 you know maybe it's independent of set theory you know you know you can't rule it out necessarily but you know you could have said that about you know forma's last theorem you know you know there were 350 years before that problem was posed and know when Andrew Wildes solved it 20 years ago okay but。

Yeah， and in that entire time， you know， you could have said。

 well maybe we'll never know the answer okay but no you know。

 it just required the creation of whole massive fields of mathematics that didn't exist and you know for Ma's time that's all it required。

 you know know and you know like a centuries of mathematical effort okay and you know if you forced me to bet。

 you know my bet my own bet would be that P is not equal to NPp and that there is a proof and it will require you know the creation of massive areas of mathematics that don't exist today okay so you know。

 I mean you know it's not that we know nothing about the sort of question rights in the last 30 or 40 years。

 you know， there's been a huge effort to understand questions like this one you know and we've been able to prove sort of much。

 much weaker statements than P not equal to NPp right。

You know people have been able to prove them okay that you know maybe we'll talk about examples later in the course okay but you know basically like if you restrict the type of the algorithm you know you force it to only use monotone gates only use end and or gates for example or only be like have a circuit of a restricted depth then you know we can say a lot about the limitations of particular types of algorithms okay but even just doing that just ruling out like very very hobbled types of algorithms for you know solving NP you know NP problems or weaker problems you know even that has required like you know huge creative new ideas and so it sort of gives you a sense for the scope of this problem right you know that if even these like little baby versions of versus NP have been you know you know these like big breakthroughs that you know one awards and all this。

Right then you know， the full question， right， it's going to be something。Okay。

So that's sort of what I just wanted to say for context， I'm sure we'll have more to say later。Okay。

 but now you know I want to tell you about NP completeness。

 which is sort of a crucial you know further aspect of the story of P and NP so in order to you know define what NP complete problems are。

 you know we need concept of polynomial time reducibility okay so you know we saw。

When we did the unit on computability theory。😊，We saw that there Robin showed you that these two notions of what it can mean for one language to be reducible to another one right A is touring reducible to B if if you had an oracle for B then you could use it to decide a that a is computable with an oracle for B and A is many one reducible to B if there is some computer program that maps yes instances of a to yes instances of B and no instances of a to no instances of B so that's a stronger notion of reducibility so so you saw both of these and and these can differ from each other by the way。

 what's an example where know of a and B that are touring reducible but not many one reducible。

By the way， anyone remember？This could be。This could be good stuff to know for a yeah。吓。Well。

 halt is， I think Ht is both touring Reducible and many one reducible to SuperH， yeah。Yeah。

 halt and not halt。Exactly， yeah， there's a good example， right？😊。

Certainly you know the one is touring reducible to the other right if I have an oracle you know that tells you the answer to the halting problem but it just inverts the answer or tells to you right that's still a pretty damn useful oracle because you know you can just invert the answer back right it's like you know you know this standard joke people make about you know someone whose predictions you know like a psychic whose predictions of the future are always wrong right that's a really。

 really useful psychic right they're always wrong then you know you get a lot of information from that okay。

😊，So so this is touringreducible， okay， but it's just not many one redducible because if there were a way to map yes instances of halt。

 yes instances of not halt， you and in no instances to no instances then not halt would have to be recursively inummerable。

 but if both a language and its complement are recursively inummerable。

 then the language is decidable， which would mean that halt would be decidable。

 which would be a contradiction。😊，Okay， so now all we're going to do is we're going to just take these notions that you already know and scale them down to the setting of polynomial time okay we're going to force everything to be efficient。

So we can say that a is polynomial time touring reducible to B， which you know。

 it's a little bit unwieldy to write this thing， but okay if。U。

If B is solvable in polynomial time with an oracle for a okay so the notation we use for that is if B is contained in p to the a okay so we write oracles using the superscript notation right you've already seen right。

 we don't mean you can raise a complexity class to a power。

 but you can give it you can feed a complexity class in oracle。

 okay so you can say the set of all the languages that are solvable by a touring machine with an oracle for a that runs in polynomial time。

 okay that's what P to the A means。😊，And so if。I'm sorry。Did I just screw this up？Yes， I did。

I switch A and B， okay A is touring reducible to B if given an oracle for B。

 you can use it to decide A， okay， good。😊，Sorry about that right。😊。

And you can use it to do so in polynomial time。Then we can also say。That a is polynomial time。

 many one redable to B。If there exists a polynomial time algorithm， M。Such that for every input X。X。

 sorry， is in a。If and only if。F of x is in B， sorry， I should say m of x。

If and only if M of x is in B， okay， so what this says is that there has to be a polynomial time algorithm that takes any yes instance of a and maps it to a yes instance of B。

 and it takes any no instance of A and maps it to a no instance of B。😊，So that's like again。

 it's a more restricted type of reduction because we say M has to run in polynomial time。😊。

But let's you know explore the meaning of these notions okay， you。

 basically you know they're both different ways of saying that basically you know if you knew how to solve B in polynomial time。

 then you could also solve a in polynomial time know there are different ways of formalizing that so。

😊，Okay， so we should verify that it's true that if a is polytime touring reducible to B， and sorry。

And B is in P， then A is also in P。 Okay why is that anyone？

I'm not saying anything earthshaking here okay saying you know if you have a polynomial time algorithm that solves a given you know a subroutine for B and you also have a polynomial time algorithm for the subroutine well then composing you know just like we said a few lectures ago composing two polynomials gives you another polynomial right this is a useful property of polynomials that they are closed under composition here we're using that fact and likewise。

😊，I claim that if A is polytime touring reducible to B and B is polytime touring reducible to C。

 then what follows from that anyone？😊，Yeah。Yes， why？Exactly。

 you just chained together to the two reductions exactly okay and again， you know。

 which is composing polynomials all right， you know。

 and we have you know the usual properties is like you know every A is polytime touring reducible to itself you know so this really is an order relation and we also have that if a。

😊，Is poly time many1 reducible to B than a。Is also。Powly time， touring reducible to。Okay。

 why is that？Well， if a is many1， yeah， if a is many1 reducible to B， then just you know run this M。

 you know compute M of x and then feed M of x to your B oracle， and I ask is it in the language。

 so it's a very， very， very simple use of the oracle right？😊。

Okay but you know the other direction doesn't have to hold， you know。

 once again halt and not halt gives us an example， right you know。

 halt will be polynomial time touring reducible to not halt。

 but it won't be many one reducible you know， in any amount of time to not halt。Okay， all right，😊。

We can define the main actors of the drama， I guess， which is。We have a language L。

Soy Al was NP hard。You know， and there' there's actually。

There there are different types of NP hard for， you know different kinds of reductions。 all right。

 but let's just say for now， NP hard under touring reductions。

 L is NP hard under touring reductions if。呃。There's a couple ways I could define this。

 one of them is if NP。iss contained in P to the L okay so what this is saying is suppose that if you had an L oracle。

 then all of NP would become solvable in polynomial time okay， then we say that L is NP hard。

 meaning it's at least as hard as solving everything in NP。😊，Okay。

 it's a single problem that captures the entire difficulty of NP this is what we mean okay。

 an alternative definition is。😊，呃。L prime is polynomial time touring reducible to L。

For all L prime and NP。That's really just another way of saying the same thing。Okay。

 now I should tell you that in practice， you know almost every time we ever prove that a problem is NP hard。

 you know， we actually prove it under a stronger new notion than this， namely。

 we prove that it's NP hard under many one reductions， okay， so what's that。😊，诶。Okay。

 just means that every language at NP has to be many un redducible to your language。Okay， so。Okay。

 so now。We can say that。A language is NP complete， what does that mean？If。L is both NP hard。And。NNP。

Okay。So NP complete just means the intersection of NP hard with being in NP。So。Let me draw a picture。

Oh， actually， I already have part of the picture right here。Okay， so we've got P contained in NP。

And then。The NP hard problems are sort of the problems that are above all of N。 You know。

 they're the problems to which any N problem is efficiently reducible。

 Okay and the NP complete problems。Are just those NP hard those NP hard problems that are themselves in NP So these are like the maximally hard problems in NP okayre you know it's a single N problem that captures the difficulty of every NP problem Okay so now you know you might say like this this is sort of a strange definition because you know a priority it's not obvious it's not immediate from the definition that there should be any N complete problems okay or any NP hard problems for that matter right like why should you know you can define whatever you want right but why should these things that we've defined even exist Okay so。

The first thing that I want to convince you of is that just you from the definition of NP we can prove that there must exist at least one NP complete problem it won't be a very interesting one but you will start somewhere okay but then once you have an NP complete problem then the big discovery that people made in the early 1970s was that its just sort of like a little seed and it grows and grows and grows and using that that sort of first problem that's NP complete you can then prove that another problem is NP complete by reduction from the first problem and then that second problem you can use that to prove that more problems are NP complete and more and more and it turns out that among all of these different NP problems that people worried about you these combinatorial optimization problems and so forth that people wanted to solve and puzzle problem。

And logic problems， almost all of them turn out to be NPp complete。Okay， not quite all of them。

 and we'll be very interested in the exceptions and we'll discuss them but you know。

But most of them do actually turn out to have this property of NP completeness okay so you know。

 just to jump the gun a little， you know， among the ones I wrote down here， this one， this one。

 this one， this one， I could have listed， you know， 200 more。

 but we don't think this one or this one。Okay so so again。

 NP complete does not just mean that you're an NP problem。

 which is hard right factoring is an NP problem， which as far as we know is hard for a classical computer anyway okay but we don't think it's NP complete and we're going to get into the reasons later okay N complete means something more specific than that it means that not only are you in N but every N problem can be efficiently reduced to you okay you capture the difficulty of everything in N Okay so that you know at first glance sounds like a very。

 very special property to have right the fact that all these zillions of hard problems turn out to have that property is a remarkable discovery about those problems okay and're going to see you we're going to see a few examples of you where we'll prove for ourselves that that property is true know now。

Ask of proving problems NP complete， you know， it was like developed in the 70s and you and after that to an extremely high art form right and you know people got incredibly good at it。

 you know， to the point where like they they basically got got bored of it okay and said， you know。

 you know， all right， you know， yet another NP complete problem you know。

 whoop do you do right But but。😊，So we're not going to sort of go through hundreds of examples of proving problems and be complete。

 but we are going to go through just a couple examples so that you get the idea of how it goes。Tway。

 how about this one？Okay， but we need to start somewhere。

 so let me just first establish the existence of a single NP complete problem。

So so I'm going to you know， have one that's really， really obviously， you know， you know， I mean。

 I mean， it really， really won't surprise anyone once they see it， that this one will be NB complete。

 So in the notes I call this the D problem okay。So what is theh， it's a languageguage that。

If you take someone else's course like 6840， you should be aware that the terminology like duh and SuperH is not entirely standard。

呃。All right， so it's just going to be the language that consists of all triples of a touring machine and two numbers n in T。

 which are written out in unary notation。😊，Such that。There exists a W。 There exists an n bit string。

 W。Such that when you feed a W to the machine M， then it accepts。In it most tea time steps。Okay。

 so that's my computational problem。 I give you a touring machine and I give you N and T， and I ask。

 is there an n bit string that causes M to accept at most T steps？😊，Okay。I can define it。

 That's a problem， right。Can anyone explain to us why is this problem in NP。

 why is the dull language at least contained in NP， that's the first thing we better check。Yeah。Yeah。

 just give W as the witness don't you know if one of these triples is in the language。

 then W will be a witness that proves it and we will be able to check the witness in polynomial time in fact in linear time basically。

 you know and see this and this is where it's important that we have encoded T in urinary notation okay if we had encoded T in binary notation then what would have been the problem。

😊，Then， you know， yeah。Yeah。Yeah， exactly。 you know， if Id specify T and binary that I could have。

 you know， basically said， you know， in order to verify W。

 you have to run M for an exponential amount of time because I could have specified an exponentially long running time using only a polynomially long number Okay so but you know。

 by by forcing you to code n and T and un andary， it's just a way of ruling that out。

 Okay then now I say that actually and no N and T really have to be polynomially bounded Okay you know。

 or you know， and。😊，So all right， so there is a polynomial time verifier for this language， in fact。

 a linear time verifier。 Okay， so now in order to show that a problem is NP complete。

 we have to show two things about it。 Well， what are the two things。😊。

We've already shown one of them。Yeah， yeah so you got to you know so to show that a problem is NP complete right you know the two things to chat right first is that your problem is in NP almost always that's the really really easy part it was like duh the witness you know here it is right so you know there are some cases where its you know where we're even showing the problem is N NP is hard okay but usually not usually you know if it if we were asked on you know on an exam or something know by the way NP completeness is not going to be on the midterm only the things before that but but you know but if it were you know on a final let's say for example you know you can just say all right you know clearly the language is in NP because you know here's the witness right so now we're going to show that the problem is NP hard right and that's the real that's usually the real difficulty okay。

😊，Okay so how do we show that does NP hard so we're given now an arbitrary language in NP okay。

 and what do we know about this language well you know nothing except for what follows from the definition of NP right so we know that there exists a polynomial time verifier V such that。

For all X。If x is in L， then there exists a witness w such that v of x comma W accepts。

Whereas if x is not an L。Then for all w， v of x comma W reject。Okay， so now from these facts alone。

 can anyone tell me how to reduce L to Dh？I've sort of done most of the work just by writing down this definition here。

Well。Basically you you this problem is almost just NP complete just because it just encodes the definition of NP right you know the only further thing that I have to do is I have to take this input X which does not occur over here and I have to hardwire it as part of V so I hardwire the input x into the description of my verifier V but then once I do that and I have to mess around a little bit with so well let's say that I had an oracle for D right what I need to know what n and T would I specify in in feeding a triple to that oracle。

 well the n that I would feed to it would just be the length of W that would come from the definition of my verifier right so actually in terms of my original problem the length of W would actually be some polynomial。

😊，N some p of n okay but that's fine， that's just you know a polynomial blowup like like if w were of length n squared well then you know when I feed my query to the oracle for Dh then I'm going to have to have n squared zeros to encode in order to encode the n that's relevant for that oracle call but know I can spend n squared time and write write down n squared zeros that you know that's fine that's just a polynomial blowup and likewise what should T be how will I know what t is。

😊，Well yeah。Yeah， t will be whatever is my polynomial upper bound on the running time of V which again there has to be such a bound by the definition of NPp right so let's say that that upper bound is Q of n Q is just some other polynomial so then I'll writeq of n zeros in the t part of the tape and then I have M you know M is really just V but with x hardwired into it so I take that x and I take0 to the p of n and I take0 to the  Q of n。

I take this triple and I ask whether it's in D， and that then tells me whether x is in L。Okay。

That's it。So we've established that there's an NP complete problem。😊，What did you do？呃。Okay。

 but you know now we're。In a position to address the real question， which is。

 is there an interesting NP complete problem？Okay， and well， the answer to that question is also yes。

 okay， but that， you know， you have to think maybe just just a little bit harder for okay and so。

So the ones that we're going to start out with you know are you know is the famous satisfiability problem okay sat and you know we're going to look at two different variants of SA Okay。

 the first one is circuit set， I already define this in the last lecture， but this is just，U。

The set of all encodings of bullolean circuits， so circuits of and or in knot gates。😊。

For which there exists。Let's say an end bit input x that causes the circuit to output1。Okay。

 so the set of all the circuits you know， for which you can cause a one to come out at the end by some you know。

 setting of zeros and ones to the input bits， okay， that's the circuit set problem okay。

 and then you know there's an even more famous variant of set。Which is called threeat。

 and this one is。😊，usual way of putting it is that you have a collection of clauses so so you have n Boolean variables x1 up to xn each of these can be set to either true or false okay and then we have a whole bunch of constraints you know involving these variables that all have to be satisfied at once and each constraints can involve that most three of the variables okay so the constraints you know and the usual way of writing them is just as an or or as a disjunction we say so you could say that either x1 can be true or x2 can be false or x4 can be false okay that would be an example of a constraint right and by the way it might sound like I'm being very generous by allowing you know by putting or instead of n here right I say you know this could have you know you can。

😊，the clause this way or this way or this way but know the fact that I'm being so generous。

 that's the entire source of the difficulty because if I had said you know you know this variable has to be set this way and this one has to be set this way and that one that way and so forth well then it's very very easy to see whether all of my requirements can be satisfied at once because you just check whether know did I ever tell you that the same variable had to be both true and false。

😊， but when I say when I mix in them or，😊，You know， you can satisfy any one of these， you know。

 any one of these is fine， but then also you have to set either x1 to be false or you have to set you know x2 to be true or you have to set x3 to be true okay and I'll make you know a whole bunch more requirements like this okay and then you know then it can get very tricky okay so。

this is what a threesat instance looks like， it's just a whole collection of these clauses。

 each clause is the or of it most three you literals as we call them。

 which means just like the variables or the negations of variables。

 and and know so it's threeatAT because each clause has to have size at most three and then we put all of these together and we get a formula which we call phi。

 and then the formula is satisifiable if and only if there is some way of setting these variables that causes the entire thing to evaluate the true。

😊，Okay。And then three set the。3 set is just the language that consists of all encodings of satisfiable three set formulas。

 Okay， so all the， you know， like binary encodings of formulas like this that have a satisfying assignment。

😊，Like you， this one certainly does， what's a satisfying assignment for this formula， for example。😊。

It should have six， I think。Well。Yeah， right， right。

 as long as x1 and x2 are both true then we're happy no matter what else happens， there's an example。

😊，So in fact， you can check that basically each of these clauses can kill off at at most one of the eight settings of the three variables。

 which means that if I wanted to give you to show you an example of an unsatisfiable threeat instance。

 then I would have needed eight of those， okay。Okay， so now。Can tell you the。

 the Cook 11vin theorem is， you know， one of the most famous theorems in， in complexity。 Okay。

 although， you know， its proof is， as you'll see， is very， very straightforward。Okay。

And it's basically just a statement that3SAT is NP complete okay so just it's the first interesting example of an NP complete problem okay and there's nothing really sort of inherently magical about3at right it just happens to be sort of the first interesting example that people found okay and you know and once you have that one example then you can you know you can use it to prove many。

 many other things or NP complete okay and and why is that I should。😊。

I should actually state it explicitly， okay so here's the principle that gets used over and over and completeness okay。

If if you have some language L， which you already know is NP complete okay and then you show that L is。

Let's say polynomial time touring reducible to L prime。For some L prime in NP。Then。

E Prime is also NP complete。why is that anyone？Why is this principle true？Yeah。Yeah， well in fact。

 you know because L prime is harder than L and L by definition of NP hard was at least as hard as everything in NP and now we're saying L prime at least as hard as L。

 so well then you know L prime is also at least as hard as everything in NP。

 therefore L prime is also NP hard， which means that if it too is an NP then it's NP complete。

Okay so it's， you know， it's like one of those social networks where you know。

 you have to be invited by someone who's already in the network right like basically in order to be NPp complete like you have to be invited by someone else who's already NP complete okay so you know。

 so I mean， I mean， you know， the first problem you know。

 just got in by the definition of NP you know， the just got in for free okay but from that point forward。

 you know the easiest way to prove that a problem is NP complete is just to take some other similar looking problem which is already known to be NP complete and reduce it to your problem。

😊，Okay， you have， you know， thereby showing that your problem is at least as hard as that problem that was already shown to be at least as hard as everything in NP okay。

 make sure that you've got the direction of the reduction rate okay if you showed that know if you reduced your problem to the known problem then all that would show is that your problem is in NP。

But that's， you know， that's the uninteresting part right， the interesting part。

 the part you have to show is you have to show that the already known problem is reducible to your problem。

 and therefore that your problem is at least as hard as the previous one was so。😊。

So the way that the Cook Le1 theorem is proved or the way that I'll prove it， I should say。Is that？

We'll show that D is you know， which we already know is NP complete。

 is polynomial time many1 reducible to circuit set。

 and then we'll show that circuitat is polynomial time， many1 reducible to3 sat。😊。

so this will be our chain of reductions。You like。I'll leave that up there。Okay。

So how do you think we could reduce Dh to circuit set so what we need is you know we have a touring machine。

 M， let's say。So now you know let's remember what a touring machine is， right it's this thing。

RightIt's going back and forth on its tape， it's you know reading and writing ones and zeros， okay。

 you know， except it is a polyial polynomialally bounded touring machine that's going to be important okay。

 so you know it's not you really using an infinite tape anymore right。😊，We cut things off。

 but you know it uses only a polynomial amount of time。

 so let's say it uses Q of n amount of time and it uses。You know okay。

 so certainly if it uses only Q of n time that's not using more than Q of n bits of memory you know and then there's a particular question about M that we want the answer to。

 which is know we want to know， is there a witness W that causes M to accept？😊，Right。

 that's what we want to know。 So， so we can encode that by saying， you know， is there。

Is there some particular setting of N bits on the input tape， W1 up to WN。

 so that if I initialize the tape like that， I let's say you know I initialize all the remaining bits to zero so those are just scratch space。

 okay then M will accept。Right， in a polynomial amount of time and at most Q of n time steps。 Okay。

 that's the question about M that I want to know the answer to。 right Okay。

 and now what I need says this is what I'm given。 Now what I need on the other side is I need to construct a circuit。

 Okay and the circuit。You know， will be just a circuit of andor and knotgates。

You know of the sort that we've seen before in the course。You know， something like this， Okay。

 and then it has some one gate at the top that represents the output， you know。

 and it it too takes W。W1 up to WN as input okay and then our question is you know is there a setting of these bits that know that makes the circuit accept okay and furthermore。

 given the description you of the touring machine I have to construct the circuit in polynomial time okay the reduction itself has to be efficient so I need to construct the circuit in time which is let's say polynomial know let's say in Q of n right which was encoded in unary in my instance of the do problem。

I can call， maybe I should be consistent with notation， I should call this T， so Q of n。

 which was a polynommi I'll just call it T。All so basically。

 all this is saying is I need a Boolean circuit that's going to simulate a touring machine。Okay。

So so you know now the first thing， you know when you look at that， you might say， well， look。

 didn't we say the very beginning of this course that。

 you know the touring machines in some sense are more powerful than circuits because you know a touring machine you you just have to design one machine and then it could handle inputs of an arbitrary size whereas a circuit。

 each circuit that you design is only handling inputs of one size you like inputs of size 100 or something okay okay and that's true that is a real difference between circuits and touring machine。

 you know touring machines are uniform， you know， circuits or non-uniform okay but in this case。

 you know we have we have imposed a bound on the you know on our touring machine we know that our touring machine is taking an input of size n that it's running for t times steps that's using at most t squares of memory。

 okay so once we have those bounds then。😊，The intuition is that， you know， well， you know。

 then then circuits really should just be equivalent to touring machines， right。

 We should just be able to simulate one with the other。 Okay， and basically。

 the proof of this theorem is really just formalizing this intuition， okay so。😊，You know， I mean。

 in some sense， you know you could say that we all know that something like the Cook Levinth theorem has to be true okay why why do we know it well because your computer is built out of and and or in not gates and your computer is able to simulate the actions of touring machines okay so you know like we know it must be possible somehow right I mean you know people have figured it out right it's almost you know it's sort of it's not you know that interesting as a math problem even it's really like a computer architecture problem okay but。

😊，But to just you know state in a little bit more detail， you know what you have to do。

 okay you have to build a circuit that you know sort of simulates the actions of your touring machine and you know the easiest way to do that is just to define you know a whole bunch of boolean variables。

 just be very， very wasteful you know and defining variables as long as you're only polynomally wasteful that's important okay you can define a lot of new variables。

 you know basically just encode everything that's happening with your touring machine at every step in time you know as long as we only have a polynomial number of them okay and then what we need to do is we need to show how we can actually set all of those variables by using Boolean logic aids and that will just be sort of fairly routine。

So。So let me define a variable called XIT。Okay， and this is basically just asking， you know。

 like is the I square of my touring machine tape， does it have a one in it at the Teth time step。

 you know when I'm simulating my machine？Okay， that's a natural question。

 thing I might want to know about the execution of this machine。

 What else might I want to know about it， anyone。Besides what's written on the tape。

What else is relevant to know about a touring machine if you're trying to simulate it。Yeah。

 where you are， excellent， excellent， so let's say。Let's see。

I'm going to just encode this using a Boolean variable， again， it's fine to be wasteful here。Okay。

 I'll just have a variable that just you know is true if the tape head is at location J at step T and it's false otherwise。

 and what else there's one more thing that I need to know yeah。Exactly。

 I need to know the machine's internal state， so let's just do that with another Boolean variable。

 like y of S comma T。😊，Oh， let's just say。Okay。So I've got these variables。And。ch race。Okay。So。

One way to think about what's going on。Is， you know， just imagine。

The complete history of the touring machines execution you know being laid out in a table okay we call this a tableau by the way it is like a complete spacetime history of a touring machine okay so we start out。

 let's say time is going up let's say so we start out at the bottom with you know W1 up to WN and then000 and then you know the tape head can move left and right on the tape like this。

 you know one square at a time and it can be reading and writing zeros and1 so like if this were you know000 now this can be 010 and now this can be 110 and then this could be 100 right it can change you know whichever it can change whether there's a1 or0 whatever square it's visiting okay but now。

You know， the you know， what is going on at time step T plus one， you know。

 intuitively is a pretty simple function of whatever was going on at step T right so we ought to be able to express you know。

 the values of these variables at time T plus one， you know as pretty simple functions of whatever their values were at time T right Okay。

 and indeed we can do that right so let me just give you an example of how we do that so。😊，All right。

 so let's say that I want to set。X。Of I and t plus 1。 so I want to know， you know。

 should the I tape square have a1 in it at time at time t plus1 Okay。

 then what like can anyone get me started on this like what am I going to need to know about what was going on at time T？

Well。I mean， I mean， basically what I want to say is that Xi of t plus1 should be you know whatever X of t was。

 unless it happened that the tape head was at location I at time T in which case I should look at what state the tape head was in and what was already written at the tape then and that will tell me whether there should be a1 or0 there。

 but otherwise it's just unchanged from the last step。Okay， so how could I express that？😊，I can say。

So not you know so so I could I could express this as an aura of a bunch of ans。

 so like like under what circumstances could you know。

 the I tape square have a one in at a time T plus one Well。

 if the tape head was not there at time T and also。This square was already one at time T。

 then this is a case in which Xi of T plus 1 should be1 right you agree， Okay。

 but now what's another case where it should be one？Well。If。Let's see， we could say if。

If it was there。You know， if the tapehead was there at time T。

 then we just need a whole bunch of logic expression saying if the tapehead was there and you know。

 the symbol should have been changed to a one so like you know if if tapehead was there you know and a one was written on the tape and the machine was in some state。

 you know， at that time would you know that should have caused it to write a one。

 so I'm going to have to have for each state that could write a one there。

 I'm going to have to have a cause of this form， okay。😊，ZIT and。You know。

 like some of them might say， you know there should only be a one there you know if there was a zero there at the previous step right like so if not Xit and y S2 T right if S2 is a state that only writes a one there if there was previously a zero there right then I'm going to need a clause like that okay so I write down such a clause for every possible combination of situations that could lead to a1 being there at time t plus1 all right and then。

I'll have a similar formula for Ys of t plus1 and Zj of t plus1。You know。

 in terms of all the previous stuff that was going on at time T。 All right。

 I feel like I don't want to subject you to these formulas。

 So if if you're okay with my not showing them and I'm okay with my not showing them。

 then I'll just tell you that you know they're in the Ser book。So you know。

 so the principle you know is， you know， you know， basically you know just you know clearly each of these。

 you know， for each layer， for each time step， I can express what should be happening everywhere。

 you know， you know by using a small polynomial size network of and and or not gates you know applied to the outputs of the previous layer。

 the previous time step， okay， and then what will be the final output of by circuit anyone。😊。

When does my circuit accept？When should my circuit accept？Yeah。Exactly， yeah， yeah。

 the final thing should just encode you know， does my touring machine after T time steps does it end up in an accept state right so which would mean well。

 you know we could say for simplicity that there's only one accept state right and then。😊。

And and then the final output of the circuit that I'm interested in should just be like why of the accept state comma。

 the total number of time steps okay which now I'm calling capital T right so that's my final outcome so I build up this you know this big circuit you know it's kind of big but it's only polynomally big and then you know just by construction my circuit will have an accepting input if and only if my original touring machine had an accepting input okay the other thing to say is well what are the inputs to my circuit。

 I should actually be be clear about that also。What are the inputs to anyone？

The inputs to my circuit are W1 up to WN right and you know and these squares that are initially0 these are just variables that I could just set to0 and use that to simplify the circuit if I like right like if I ever have an and of something with zero I can just simplify that to a zero if I've got an or of something with zero you know I can just simplify it to whatever is that other thing so you know I can just make some simplifications because I know that these squares are initially zero okay but these ones the ones that represent the witness w1 up to Wn。

 these are the true you know inputs to my circuit。So， okay， so that so the conclusion here is that。

You know， D has been reduced in polynomial time to circuit set， yes。

 instances mapped to yes instances， no instances mapped to no instances， and therefore。

 you know since circuitat is clearly in NP you know。

 and we've shown that it's NP hard therefore circuitat is NP complete Okay。

 now the one final step is to reduce circuitat to3at Okay， but here's the magic。

 I claim that we've already done essentially all of the work for this Okay that we can get out that the3at is also NP complete Okay。

 why all right， well we know that circuitat is NP complete。😊，Okay， but what is a circuit， right？

A Boolean circuit。You know， it's a network of an gates and or gates and not gates without loss of generality。

 each and gate you know an or gate has two inputs and one output right okay。

 so now let's say that I just define some new variables like y for the output of this an gate。

 you know， y1 y2 for the output of this or gate and so forth you know。

 okay then all I'm going to need to do is just create causes that express that let's say y1 should be the n of x1 with x2。

😊，Right？You know， and y2 should be the or of y1 with。Whatever this was， x4。

And so forth okay these are each constraints that relate one output variable to two input variables okay so these are each constraints involving three variables right I can encode that by saying you know every outcome where y1 is not the end of x1 with x2 is disallowed okay how many such outcomes are there。

 there are four outcomes where y1 is different from n of x1 x2 right so now I just need one clause to disallow each of them。

😊，And then the final output of my circuit， call it Z， I need a clause that just says Z is true。

Right okay， and then if I have a not gate， like， let's say you know， y is the no of x， right。

 I need causes that say。呃。