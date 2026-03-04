# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p15 P15 apr09 -BV1Dao8YQEEn_p15-

车冠击。Okay，Let's get started with just the administrative stuff。

So I do have finally PSet three and I also have the midterms。

 so I'll give you a few minutes to pick those up after class right and so a reminder PSet four is due next Thursday。

Pace at five we' try to get out by this weekend and this coming Tuesday。

 I'm going to be traveling Robin is going to give a guest lecture about probability。

 probabilistic complexity classes， which we might get started on today if we have time for it。

All right， so last time we did an example of an NP completeness reduction。

 we showed that three coloring is NP complete， but then you we also you know and we finished you know explaining why3SAT is also NP complete。

 okay， but then you know we saw examples of not everything is NP complete。

 that you might have thought would be， so。We saw that two side is in P， for example。

And then we had a discussion about how to cope with NP complete problems in practice by either just brute forcing it by changing the question by using approximation algorithms。

 by using backtrack search algorithms， by using houristic algorithms。

 you these are all things that people do， so you know so knowing that your problem is NP complete。

 you know， is not the end of the story， it's the beginning of the story， you could say so。

And then we said a little bit about are there physical systems that just somehow automatically solve NP complete problems。

 which is a claim that sometimes gets made that protein folding does this for example。

 and I express skepticism that really the hard cases of the NP complete problems get handled this way。

 what seems to be going on is that the systems just do something like local optimization they do something like a heuristic algorithm。

 that often works well in practice， but we could easily construct cases that would cause it to fail and finding a proof of the Rimont hypothesis or breaking the RSA cryptoy would very likely be examples of hard cases。

You guys are here on time，ll give you a special treat。

 which is there was an old idea from the 60s or '70s that you could just solve and be complete problems efficiently using soap bubbles and what was the idea here well it was that you would take two glass plates and you would put pegs between them in some configuration any configuration you wanted like that。

And then。You would dip the resulting sort of contraption into a tub of soapy water。

That's a tub of soapy water and then you would take it out okay you know and so soap bubbles would form you connecting these pegs together you in some way you know but bubbles usually like to minimize their surface area right that's what bubbles do right this is why bubbles you know that are floating in the air are sphericals as you may have noticed you know but if know if they have these pegs you in between them。

 then usually they're going to try to connect up in a way that you minimizes the total amount of bubble you know the total length of wine segment that you need to connect all these pegs to each other you know and this is an experiment that you can try at home by the way it's cool to watch okay but now there's a puzzle because you know if I give you a set of points。

In the Euclidean plain， you know， I ask what is the minimum total length of line segment that connects these points where sorry this is。

's okay， sorry there's a catch which is know the bubbles the wine segments are allowed to meet at intermediate points even where there's no peg there。

 okay this can happen too these are called Steiner points right so you so there wouldn't have to be a peg here。

 there could still maybe it would look a little different than that。it would， you know。You know。

 look more like that， okay but so finding the minimum total length of line segment that connects you know all these pegs to each other。

 if the line segments can meet at intermediate points， that is known to be an NP hard problem。

 okay that is called the minimum Steer tree problem，If they're not allowed to。

To meet at intermediate points， then you have the minimum spanning tree problem。

 minimum spanning tree， there's a polynomial time algorithm okay but minimum Steer tree where you you're just asking for the minimum length of line segment connecting these all these points and the line segments could otherwise be arbitrary you that's an NP hard problem okay and yet you you dip this tub of you pegs into you dip this contraption into a tub of soapy water nature seems to solve it okay so so so there's a puzzle you know does this tub of soapy water do what you the best supercomputers can't so so there was a discussion about that on the internet you some a decade ago maybe and a lot of people where we skeptical we're saying well look you it probably can just get stuck at local optima like you know。

know all sorts of other physical systems can right， you know， you know。

 I mean we already discussed examples of that in the last lecture right that like。

Like let's say you know I put a rock and some little crevice on a mountainside where it could， yes。

 it could reach a lower state of potential energy by rolling up first and then rolling down。

 but it's not often observed to do that right。So you know so why not just you know assume that you know you know this thing gets stuck at local optimal also okay and then someone said well this is just a computer science party line I bet you know none of you have actually tried the experiment so anyway that sort of led to the one4A of my career into experimental physics and you know I built the thing I tried it out and you know as I said it's really cool you I recommend trying it you know with three or four or five pegs you usually do find them minimum Ste or tree which is you know which is very cool。

 you start adding more pegs like six seven or so forth and then you can get you know suboptimal solutions okay and you know you could even get like。

sortrt of intermediate cycles， you can get cycle， you know， you can get circles of bubble like that。

 okay， and if you have that， then that's a proof that it's not optimal。

 you can prove that cycles can always be shrunk in a way that would decrease the total length of line segment。

 and yet this can happen。So。So indeed it seems like yeah， every other case。

 nature can be very effective at trying to minimize the potential energy that it's storing somewhere this is what it likes to do in a lot of situations but you can get into local optimum of potential energy。

 okay and this is the bane of almost every houristic approach that's ever been proposed for trying to solve it be complete problems。

So all right， so that's a little bit of you know what we know about the relationship between NP completeness and physics。

 you at the end of the course you know you know we'll talk a little bit about quantum computing and how you know there were early hopes that quantum computing could I guess literally get over this problem get over the problem of getting stuck in local optima because of quantum tunneling effects。

 for example， okay now we think that you know there are cases of NP complete problems where even a quantum computer you is probably going to have a lot of trouble so。

But so you know so've I've you know like the toy with the idea that maybe you know the hardness of NP complete problems is just a fundamental fact about the physical world you know maybe we should even just use it as a constraint and know looking for physical theories like you know someone would say。

 well you know that theory violates the conservation of energy or you know it violates no faster than like communication or you know say well that theory violates you know no super searching of NP complete problems but you know' that's a speculation。

 you know you know ultimately we're asking an empirical question right you know if you could build them you know I mean I do you know hear from people from you know every month or so who think that they can solve NP complete problems and then you know that's actually a lot easier than people who think that they've proved that P is not equal to NP because if someone thinks that they've proved that they're equal or that they can build a device。

Some physical contraption that could solve and be complete problems and you just say great。

 here's a 3，000 digit number， send me the factors and then we'llll be happy to talk more and then you sort of don't hear back from them after that。

😊，So。Okay， but not all of the hard NP problems that we may be interested in are believed to be NP complete okay so to explain that we need sort of one further wrinkle on the story of P and NP。

Yeah。And this wrinkle is called a co NP， the consort or companion of NP。

 either the evil twin of NP or something。What's CONP？

It's just the sorry it's the class that contains the complement of every language that's in NP so L complement you know is the set of strings that are not in L。

 okay so for every language in NP， the complement of L is in CONP。So this isnt you know。

 this is not the same thing as the set of languages that are not an NP， right。

 that would be a very different thing okay， this is the set of complements of languages in NP。😊，Okay。

So you know， another way to define it is that KNP， there's the class of all the languages for which there is a short witness whenever the answer is no。

Okay that can be efficiently verified so you know you know so far we really haven't said much right you know all we've done is we've noticed that the definition of NP you know has a fundamental asymmetry between yes and no right like with NP we say that yes answers have to have short witnesses but you know but no answers don't need to have them right okay so with CoNP we just reverse the story and we say it's no answers that need to have witnesses so what would be you know and then we can just like we define NP hard NP complete problems we can define CoNP hard CoNP complete problems what does anyone think would be an example of a CoNP complete problem。

Like。The complement of what？Yeah， yeah， I've just， you know。

 the definition just gives you like an unlimited recipe for producing examples of KNP complete problems okay。

 how about not SAT right， you know， which is I give you a Boolean formula you know or let's say let's I give you a threeSAT formula and I ask you。

 is this formula not satisifiable？😊，Okay， is it unsatisfiable？😊。

So there's certainly a short witness if the answer to my question is no。

 which is the satisfying assignment， you know if the answer to my question is yes。

 then it's not obvious， right？😊，Okay， or we could say， you know is this graph not three colorable？

You， you know， is there not， you a subset you know， of these integers that sums to this given value。

 okay and so forth？Okay， so so the CO NPP， it's pretty clear that it's going to behave a lot like NP in most respects in particular。

😊，If p equals NPp， then what would also have to be true， anyone？Yeah。

 yeah right so p P is certainly equal to coP which is just a way of saying you know p is closed under compliment right with P theres just you know you could always just flip the roles of accepting you know you can always just swap the except and reject states there's no asymmetry built into P the way that there is for NP okay so p equals co P you know which means that if p equals NPp then you know both of them would also equal coP which would equal conp so p equals NP then the whole thing comes crashing down p equals NPp p equals conp you can you can then you find yes witnesses and polynomial time you can find no witnesses and polynomial time。

😊，Okay but what's interesting here is that the converse is not so obvious at all。

Suppose that we just had NPp equal to co NPp， right then would that imply that p equals NPp。Well。

 to this day， no one knows any such implication，So so as far as anyone knows。

 it could be that even if p were not equal to NP， that still NP could equal co NPp。Okay。

 so what would that mean？What would it mean if NP equaled CoNp？Yes。Yeah， yeah。

 right that is what it would mean right it would mean you know finding a yes witness would also mean you could find a no witness or to say it more concretely。

 it would mean that there would always be short proofs of unsatisfiability of a boolean formula and this proof might still be very hard to find because after all P is not equal to NP in the hypothetical world we're talking about but once you found it then you could just check this proof and you would say yes。

 okay I agree this threeSAT was unsatisfiable。You know you would say yeah okay once you see the witness and you would say okay yes I agree this Sudoku puzzle or this jigsaw puzzle was unsolvable okay so you know so that that would not be quite as you know astonishing as P equals NPp maybe right because it's not saying that you could find this proof okay but it would still be kind of astonishing right you know because you know it's saying someone can hand you just a witness that you know you just check it and you say all right。

 now I agree that there were no solutions to this you know exponentially hard search problem right why should that always be possible you know why shouldn't you have to do a brute force search you know by yourself to sort of convince yourself that there are no solutions right you know you know how do you know that the person is an well you know someone could always say well trust me I looked really really hard for a solution and I didn't find one right but why should you believe that？

Okay，啊。Those of you who came late， I'm sorry， you missed the soap bubbles。

 but you can get it on video。Okay。Okay， so just to draw a little picture。

So this is what we knew before， we have P and MP。The NP hard problems。

And then the intersection of NP with NPp hard is NP complete。 now we're saying。

NP also has its evil twin， CoNP。And。The intersection of CoNP with NP hard。We'll call CoNP complete。

So for every NP complete problem， there's a corresponding coNP complete problem and vice versa。

 but now you know the point of this is that know now it allows us to ask a new question。

 which is the you know is，Which is the question， is NP equal to CoNk？

Or there always short proofs of unsatisfiability？If there were。Then we could get a picture like this。

 then the picture could simplify to this one where P would still be unequal to NP。

 but NP would equal co NPP， and then the NPP complete and the CoNP complete problems would then be the same yeah。

Oh okay， good question well so under touring okay that's an excellent question okay so actually under mapping reductions they could be different okay。

 but under touring reductions， I claim that anything that's NP hard is also co NPP hard and vice versa。

 can anyone see a reason why。😊，Let's suppose that you had an Oracle thatd NP know that solved NP complete problems for you。

 could you also use that Oracle to solve coNP complete problems？Well， just flip the answer。Again。

 it's like the psychic who's always wrong， very very useful psychic just you know flip whatever。

 whatever they tell you okay so you know under touring reductions you know we sort of restore the symmetry between accepting and rejecting right you know if you're allowed to make it touring reduction to your oracle then you know it doesn't matter whether you the oracle is interchanged yes and no just you know so so then you know NP hard and CoNP hard are going to be the same thing right you know NP complete will still be different from CoNP complete because to be NP complete you have to be in NP and to be CoNP complete you have to be in CoNP。

😊，All right， under mapping if you insist on mapping reductions then。

Then actually NP hard and CO NPP hard could be different in general。So。嗯。Okay。

So this expanded picture lets us make a。Sort of a bolder conjecture than just P is not equal to Np。

 which is we can now。Stick our necks out even further and conjecture that NP is not equal to coNp so in other words really this picture。

 you know this richer picture is the right one now if this is true， then certainly this implies what？

Well， it certainly implies p not equal to NPp by what I wrote over here， if p equal to NPp。

 then certainly NPp would equal conp but this is a stronger conjecture than merely p not equal to NPp。

So you know but it's a conjecture that almost all of us would stick our necks out further and make as well。

OkayAnd as we'll see， one can stick one's neck out much， much further just than that。😊，All right。

 so now there's one other aspect of this picture that I'd like to focus on。

So actually you know this picture is analogous in a lot of ways to one that you already saw in the setting of computability。

 okay because know in computability there were the decidable languages and then there were the recognizable languages right do you remember this from your PSet right？

😊，And then there were the co-recognizable languages， okay。

 the languages whose compliments are recognizable okay。

 but then one thing you proved on your PSAT is that if at any rate if a language and its compliment are both recognizable。

 then that implies that the language is decidable because then you can just enumerate you know through like all possible yes witnesses。

 all possible no witnesses eventually you're going to find one or the other and as soon as you found one then you've decided the language right so actually we should。

I should get rid of this little wedge part here and I should just。Draw a picture like that。So。

So that was what happened in computability okay but you know that the argument that we showed that you know the argument that we use for that and required enumerating all the possible yes witnesses。

 all the possible no witnesses so that was like inherently an exponentially inefficient procedure right so it's not clear that anything similar should work you know in the setting of complexity theory okay。

 so so here you know let's suppose。😊，Here the question would be this。

Let's suppose that you have a language which is both in N and in Co NP。 Okay。

 so it's in the intersection of the two。 It's in N intersect Co N。 So it's in。This region here， okay。

 and the question is， does that imply that the language has to be in P？Well， once again。

 you most of us would tend to suspect that the answer is no okay why not。

 well not just because I drew the picture this way。

 for the reason that we actually have concrete examples of problems that are in NP intersect coNP。

 but people have had a very， very， very hard time putting in P。

So let me give you an example such why language。Okay。

 so let me just define div to be the language consist of all pairs n of integers， n in K。

 such that n has a divisor that's at most k。Okay，So first of all， I claim that you solving。

 you know being able to decide this language is just equivalent to being able to factor。

 can anyone see why？😊，All right， yeah。Excuse me。You can ask。Well， yeah。

 buts not the answer is always going to be yes。Yeah right， so yeah。

 so supposing you had an oracle for div， then you in order if you wanted to factor you could do a binary search for K in order to find the smallest factor that it has right the smallest prime factor。

 all right great， you know then you've just knocked off a prime factor so then just divide end by that whatever that smallest prime factor was and then just repeat for the smaller number that you get。

😊，That's an example of a touring reduction， by the way，😊，Okay， and conversely。

 if you knew the prime factorization of n， then surely you could decide div because it's just， know。

 know then all you need to know is what's the smallest prime factor of n。I claim that div is an NP。

 well， what's the witness anyone？Yeah， the divisor， the smallest divisor， right？😊，Okay， but now。

I claim that div is also in CoNP， Why is div in CoNP？

Why are there short witnesses for no answers to this question also？Yeah。

 because every integer has one in only one prime factorization okay because you could prove that okay so I can just give the prime factorization of n okay and there's one further fact that we need which is the primity testing can be done efficiently okay which you know we said at the very beginning of the course okay so you can so in other words you can convince yourself on your own that yes you know these prime factors really are the prime factors of n there are no smaller ones okay and then once you know the prime factorization then you also have a proof you know if n does not have any divisor which is k are smaller okay so then that puts div in coNp as well okay so basically you know we're using a structural property of the factoring problem you know that makes it different than any。

😊，known NP P complete problem okay which is that you know for factoring there is one there's always one and only one solution right every integer has one and only one prime factorization okay you know we don't know you know you know it's certainly not the case that every graph has one and only one。

 three coloring or you know anything similar to that okay。Not only that， but if I give you a graph。

 you have no idea how to predict in advance how many three colorings it's going to have。Okay。

So all right， so what this means is that you factoring， you know。

 when you suitably phrase it as a decision problem， you know。

 you give a decision problem or a language that's equivalent to factoring like this one。

 then that language。😊，Will be in NPP and it will be in CoNP。

 but you know you know if RSA is secure you know you if we believe the factoring is hard then it's not going to be in P okay so that would be a candidate for something that's in both NP and CoNP but that's not all the way down in P and more broadly you know we could make yet another conjecture。

 you know we love conjectures in this field okay。Wwhichch would say that p is different from NPp intersectq NPp so this is another strengthening of the P not equal to NP conjecture you know and this is what you're going to want you know in order to you know or you know this is like the least of what you're going to want in order to have cryptography for example。

 you're going to actually want more than that as we'll see， okay but。嗯。But all right。

 so you know once again， if p equals NPp， then this conjecture is also toast， you know， obviously。

 okay if NPP equals coNp， then this conjecture just becomes equivalent to P not equal to NPp。

 but if NP is not equal to coNp right then we're really making a stronger conjecture here，😊。

But one that most of us would again believe。Okay， so so now what I want to do is use this concept of CONP to explain something important about factoring that we alluded to earlier in the course。

 which is I said you know factoring is almost certainly not an NP complete problem okay but how do we know that。

 what makes us so confident。U。All right， so here's a theorem。Okay。

What we can say is that if there's any language in NP intersect CoNP， but which is also NP complete。

 you know even under touring reductions， then this would imply that NP equal coNP okay so basically you know these guys in the wedge in the intermediate zone you know the stuff like factoring okay what we're saying is that they cannot possibly be NP complete unless you know NP equals coNP and you and this picture is true okay so you know factoring cannot be NP complete without causing this enormous structural collapse know of the whole structure okay。

Can anyone give me an intuition for this？Why， why？Well， you know， I mean。

 I mean we're sort of saying， you know， look， you know， you got someone down here， you know。

 but it's also up here， you know， like yeah， that could cause something bad to happen right。

 but let's be a little bit more formal about it， right？So。So。All right。

 so what we need to okay so we're going to start with some language L prime in NP。

 and what we want to show is that under this hypothesis that L prime is also in CONP。

If we can show that， then we'll have shown that NP is contained in CoNP but then by symmetrymetry that also means that CoNP is contained in NP which would mean that NP equals coNP so that's our goal。

 we need to show that this language L prime in NP is also in CoNP so how do we do so we need to give short proofs for no witnesses of L prime。

😊，Okay。Let's see。嗯。So first of all， we know that L by assumption is NP complete under touring reductions。

 so what does that mean by definition of NP completeness？That means that L prime is in P to the L。

 means， if you have an oracle for L， you can decide anything in NP。So L prime。Okay。Okay。

 now suppose that。Yeah。P with an L Oracle。Pigure with an oracle fral。So okay。

 so nows suppose that x is not an L prime， you know， we need a witness right well。So okay。

 so we have a decision procedure for L prime right that you know。

 it runs in polynomial time and it makes oracle queries to L L you know， is a language by assumption。

 is a language in NP intersect coNP。And now we need to give a short proof that x is not an L prime。

 can anyone finish it for me at this point？Well， you know this polynomial time algorithm that decides L prime you know using queries to L。

 you now you now I want to provide a proof of what this procedure outputs。

 you know whatever it outputs， I want to provide you give a proof of it okay but now I can do this because I just have to provide witnesses for every query that P makes to its L oracle。

 like if it asks a question and the answer to its oracle and the answer is yes。

 I need to give a proof that the answer is yes， if it asks a question and the answer is no。

 I need to give a proof that the answer is no， okay， but I can do both of those。

 because L is in NP intersect coNP。Right and that's what it means for something to be an NP inter andp that you can give a proof no matter what the answer is okay so I just simulate P step by step and then every time it makes a query you know maybe since it's deterministic you know I can anticipate what every one of the queries is and for each one I can just tell you what the answer is going to be and I can give you a proof that that is going to be the answer right and there's only a polynomial number of queries so I only have to provide a polynomial number of yes witnesses and no witnesses therefore you know a proof of total of total size that's polynomial and then that proof will just show whatever the P to the L machine does。

 you know it will prove if it accepts， it will prove that it accepts if it rejects。

 it will prove that it rejects right so you know in particular we can thereby prove that some given input x is not an L prime。

Right which then means that。E Prime is in CoNP。Okay， which means that。You know。

 NP is contained in CoNP。So by symmetrymetry， NP equals co。All right， so that's。

That's the proof of this， that is why we believe that factoring is not NP be complete。U。Yeah。

X is just some input， so let' it is some input that's not an L prime and for which we would like to prove that it's not an L prime。

And if we can do that for anyX， that's not an L prime， then we've shown that L prime is in co andP。

Yeah。Well， so I described it， the witness is， you know。

 provide the witnesses for the answers to every query that your reduction makes to the L Oracle。Yeah。

Well， it's proof that if factoring is NP complete， then NP equals co NP。 so you know， in other words。

 if you accept know that NP is different than KNP， then factoring cannot be NP complete。So。Okay。

 so factoring gives a very concrete example of something that you know you know it is certainly an NP you know and that many of us believe is you know you know maybe be hard classically。

 but it almost certainly is not NP complete okay so it's a good candidate for being in this intermediate you know in the twilight zone between P and NP complete there's actually。

😊，But if you just want to know that there exists stuff in the twilight zone。

 then you don't even have to take it on belief。Okay。

 so there's an important result called Lad Nurse Theorem from 1975， which says。

That FP is not equal to NP。Then there must exist。Languages in。NP。

That are neither NP nor are they NP complete。Okay，So you know so like okay， if p equals NPp。

 then you know， then of course everything just comes crashing down right。

 then everything that's you know at NP is both NP P and also NP complete under touring reductions right by the way。

 why is everything in P NPp complete if P equals NP？On other touring reductions anyway？Okay， if P。

 I claim that if p equals NPp， then everything in P is NPp complete。In fact。

 everything in NP is NP complete。Yeah。Yep。Yeahep。Exactly yeah。

 in fact it's even better than that right you can just you know have the reduction itself do all the work and you know certain not even call its oracle at all right you know like you know it's like you already have the magic power you don't need the oracle for anything now because now we're assuming that p equals NPp right so then you just you know you can just you know the you know and you know NP hard means the NP is in P to the L right but if P equals NP then the P machine you can just say to the L oracle just bug off you know I don't need you you know I'm already NP。

😊，So。So okay， so certainly， you know， we can't hope that there would be anything intermediate if p equald NP okay。

 but this is saying that that's the only obstruction， okay as long as P is not equal to NP。

 then not only are there going to be P problems， not only are there going to be NP complete problems。

 but there's going to be ones that are in between。😊。

Now unfortunately you know the proof of Ladner's theorem does not give you。

 you know I'm not going to go through the whole proof in this class。

 but because not because frankly it's not that enlightening it doesn't give you any natural example of a problem that's in this intermediate realm like we think factoring is。

 for example， it just tells you that such problems exist。

 so it's sort of like I discussed that there's this Friedberg Muchchniick or cleaningy and post theorem in computability that there are languages that are a recognizable and not deable but not equivalent to the halting problem that are intermediate okay but they're really really weird languages okay so a similar thing here。

 what you do in order to construct these languages is basically。

language that on almost all input lengths is just the empty language， its just nothing at all。

 but then on a few input lengths， space very， very widely apart from each other。

 this language is three set。So it's just little little islands of threeatAT you know。

 interspersed with you know long long oceans of nothing okay and the point is that the little tiny you know islands of3atAT prevent the language from being in P you know just under the hypothesis that P is different from NP right they're enough know because we know that three sat is hard so even threeS at a few widely spaced input lengths is going to be enough to put the language outside of P right and then but then the fact that they're so widely spaced apart you know is going to kill off any possible NPp completeness reduction。

 you know that would reduce ordinary3at to this language right it's going to say that if we could reduce3atAT to this language then we could also just reduce3at to the empty language and then P would equal NPp contrary to assumption。

😊，All right， and then the technical part is to do all of that while still making sure that your language is in NP。

😊，So that's what Ladner showed how to do， but you it's not a very natural example。

 but it proves the point that P and NP complete cannot be all that there is to NPP if P is different from NP。

😊，哎。呃。So。I should say something about relativization of the P versus NPp question okay so you know and this actually speaks to the problem of you know why is P versus NP such a hard problem to solve okay so when we saw a computability theory we saw that like you can have you know the decidable languages you can have the halt touring degree and then you can take this you know and you can prove that those two are different from each other you in other words that the halting problem is undecidable then you can take that entire picture and you can just bump it up with an orgle you could say suppose that suppose I just throw out you halt oracles for free everyone can have a halt oracle okay and then and then what we're asking is is halt equal to super halt right in other words you know if if you have a halt oracle then can you？

Ive the halting problem for four touring machines with halt oracs okay and the answer to that is again no right it's you know and just by you know a perfect like repeat of the proof that you had before right the fact that there are these halt oracs you know lying around for everyone you know it doesn't change the situation at all as it turns out and just repeat the argument okay and so for that reason we got you know we can actually get an infinite hierarchy of harder sometimes harder and harder and harder problems super halt。

 superduper halt you know and you know as you know from the midterm there's no hardest one。😊，So okay。

 so so now you know we can also imagine feeding oracles to P and NPp so P to the A would just mean you know P with an oracle for the language A right。

 it can solve language A for free， okay， NPp to the A。😊。

would would be you know is just your verifier for your NP problem also has access to an A oracle。

 it can decide for free whether any given string is in a or not an A okay and you could then ask。

You knowFor every Oracle A， you then get a new counterpart of the P versus NP problem which is is P equal to NPp relative to a and now in computability you whether or not there was this A around just didn't matter at all you touring gave a proof of the unsolvability of the halting problem which was so general。

 that it doesn't even care if there is this a if there isn't this a or if there is what it is okay but now9 again in 1975 Baker Gill and Soa A。

We're thinking about you why is P versus NP so hard in particular why people were trying the techniques like from computability theory like to like self-reference arguments。

 diagonalization arguments， none of them were working to separate P from NP and so they wanted to understand why aren't they working and so what they noticed is that actually you know P versus NP does not have the same quality of insensitivity to oracles that the unsolvability of the halting problem had so here's what they showed。

They said yes， you， there exists oracles relative to which you can just prove that p is not equal to NPp。

 right， that sounds pretty good， you know they can prove it you know。for a suitable or a A， right？

But there are other oracles， B。For which you can prove that relative to that oracle P is equal to Np。

Okay， which means that， you know whatever is the answer to the P versus NP question， you know。

 it depends on the fact that in the real world we don't have these oracles， okay。

 so you need a proof technique that's somehow oracle sensitive。

 which basically kills everything that just comes from pure logic or computability theory。

so how do you construct these oracles？I don't know which one did I talk about this earlier in the class？

They didn't okay。So how can we construct an oracle that makes P not equal to NP？I'll give you a hint。

 you know， the oracle just needs to encode some really， really hard sarch problem。So for example。

 I could say that you know。You know， here's something that， you know this is actually a later result。

 okay， but it turns out to work， you know， if I just pick a language at random。

 you know I just put every input either in the language or not in the language。

 with independent probability half and just form a language just completely at random。

 then with probability1， P will be unequal to NP relative to that language。Okay。

 you know that so and why is that well， because now I can ask a question like you know， does。

 you know， within the first two to the n bits of the oracle string。

 is there like a string of n contiguous ones or isn't there okay。

 and that question will be answerable in NP to the oracle， why？😊。

Yeah because it's because your NP so just show where that string is all right so you know well basically we have this giant think of this giant string of two to the n zeros and ones okay and just somewhere in there you know deep in there is a row of n can you know a consecutive ones okay but if your NP then your verifier can you know your witness can just tell you where is that string and then you go and check it。

😊，You go and check that indeed there were n contiguous ones there okay whereas if you' P you know your only polynomial time you have access to the same string。

 then you can just prove that you know after a polynomial number of times you can only have looked at a polynomial number of places in the string and with overwhelming probability you will not have found you know if there's a string of n consecutive ones there and because you know you have to query this oracle here we really can say that like yes provably there's nothing better that you can do than brute force search because like we could just insert a string of n consecutive ones somewhere and you would have no hope of finding it yeah。

You're saying that there's two to the end。can that make end two to the end？Well okay。

 but the issue is this， you know I get to define any oracle that I want and then I just have to give an example of a language that relative to that oracle is in NPP but not in P okay so effectively I get to use the oracle to create an input of size2 to the n。

Right， the actual， you know。So I'll then you I'll let the final language， let's say L sub a。

 depending on a， which will consist of the set of all ends encoded in unary， such that there exists。

It's not that there exist n consecutive ones within the first two to the n bits of a and then you know my claim is that this for any A。

 this L to the A will be an NP to the A。All， because I can just you know the witness will just be where the ones occur if they do occur you know if zero to the n is in else okay。

But then the second claim， which I haven't proved rigorously。

 but which one can prove is that with overwhelming probability over a， so with probability1， in fact。

 over a， else A will not be in P of the A。Okay。And then this is the same。

 you like the fact that something happens 100% of the time doesn't mean that it always happens。

 you all know that， right？You know you， like for example。

 if I picked a random real number between zero and1， you know。

 the probability that it's1 over pi is zero one over pi is still you know。

 it's a real number it's there。So。Okay so in the same sense， relative to 100% of oracles a。

 you know p to the A is not equal to np to the A that doesn't mean that that's true for the empty oracle。

 which is presumably the oracle that describes our world yeah。Yeah， okay yeah， yes。

 you can ask that sort of question I mean in some sense right I mean I mean I mean so a difficulty here is that you know P and NPp are both countably infinite sets right they're countably infinite class of languages right and so in saying that you know like you need some way of you need some scheme for enumeration in order to even make sense of the question right because you know it's similar to the question like what fraction of numbers or even well you say you know a half and indeed under the usual ordering of numbers it is a half okay but it's very easy to give an ordering of numbers that's going to hit you know all of the numbers but know where like up to any finite point。

 two- thirdds of them will have been even。Or 99% of them will have been even。Right。

 you know you can easily do that okay so actually the answer depends on your ordering of numbers right in the same way if you wanted to know what fraction of NP is NPP。

 the answer to that would depend on how are you ordering the languages。

 how are you ordering the touring machines that define languages。嗯。All right。So all right。

 so now for the other side， what is an example of an oracle that would make P equal to NPp？Yeah。

Okay so that's an excellent suggestion know maybe if we just added it through NP then just P to the NP and NP to the NP would both just be NP okay in fact that turns out in fact we don't think that works okay for reasons that I'm going to go into we think that NP to the NP is actually more powerful than NP lets you do things that are not themselves in NP and we're going to see examples of that okay what does work is if you go high enough above NP whats what's like a next thing above NP。

Ha。Yeah， a might work here， the usual example people use is piece based。

So I claim that p to the p space equals NPp to the P space。But in other words， you know。

 if L is p space， which is a shorthand for saying that if L is p space complete。

 then p to the L equals np to the L。Sorry。Okay， so why is that？Well。Sorry。

 certainly P of the peaceace space is contained in NPP to the peace space。

So so the non obvious part is the other direction， why is NP to the peace space contained in P to the peace space。

 well， basically because they're both peace space。😊，Okay，😊。

You know there are different ways to see that one is to just say certainly NP to the peace space is contained in nondeterministic peace space but I already told you or the course there's this thing called savages theorem that says that NP space equals peace space okay and even easier way to say it you know that doesn't rely on savages theorem is to just say you know imagine you know you've got this nondeterministic polynomial time touring machine it can make queries to a piece space oracle and now we want to take that entire setup and simulate it in peace space right so how can we do that well I just you know use peace space to simulate you know use a polynomial amount of space to simulate the NP machine and then every time it queries its peace space oracle and I use you know another polynomial amount of space to simulate the oracle and figure out what answer over return but overall I'm just using only a polynomial amount of space right so I guess you know。

I get P space okay and the same thing if I had P querying a P space machine okay so relative to a P space a oracle。

 we can say that you know it it just collapses P and NP okay so we conclude that the answer to the P versus NPp question is sensitive to to which of any oracles are around okay and that's a surprisingly strong constraint on proof techniques okay know like it kills off 90% of all the ideas that people have ever had for how to solve the P versus NPp question you know because most of them just you know you know if they worked at all then they would still work with an oracle around。

You know， there are， you know， for the last 25 years or so we have had techniques and complexity theory that are sensitive to oracles。

 okay， so people were very， very excited about those techniques， you know。

 one of the main things that I've done in complexity theory is you know in 2008 Avi Wierson and I came up with a generalization of the Baker Gilil Salave argument。

 they basically said that even these new techniques that people came up with。

 are still not going to be strong enough to resolve the P versus NP question。Okay。know。

 it was called this other barrier， it was called the algebrageization barrier。

 okay it sort of generalizes you know we generalize the concept of what an oracle is in order to sort of account for these new techniques that were're able to you know be sensitive to the presence of ordinary oracles。

Okay。嗯。So， so we saw in particular that a piece space oracle know is enough to sandwich P and NP now。

You know， it may have confused you when I said that an NPical you know is we think is not going to be enough by itself。

 okay， and this is an important point that I now want to elaborate on。Okay。

 so now what I want to do is just consider just taking P and NP and just feeding them to each other as oracles in a big feeding frenzy and see what comes out of it。

So。first thing that we could consider is P to the NP P with an oracle for solving some NP complete problem okay and that's know that's obviously a pretty powerful class right it can solve SAAT。

 you so you certainly this class contains NP。But then negative it also contains cownpi。

RightBecause down here， when you're P， you can just flip the answer to whatever the oracle tells you if you want。

 okay， in fact， it can P to the NPP can even do still more powerful things that we don't believe to be in either P or sorry that we don't believe to be in either NPP or in CONP themselves。

 what's a good example of that。All right， here's an example。

 remember you know we talked about the traveling salesman problem。Right， fine you know。

You know let's say that that you know I give you the distance between each pair of cities as an integer okay and I ask you what is the shortest path you know that visits each city all right well that's a you know。

 okay well of course there might be more than one so I should phrase this as a decision problem and before Mo about and say does there exist a path that visits each city whose total length is at most K okay and that is an NP complete problem right okay。

 but now let's suppose that I ask a little bit of a different question okay I ask。

Does the shortest path have a prime length？Okay you know， it's kind of a stupid question， okay。

 but you know， I just ask you know， some， you know。

 I ask you like find the length of the shortest path and then I just ask you some unrelated question about that shortest length。

Then I claim that that problem is going to be in P to the NP， why anyone。

How do I solve that and P to the NP？Does the shortest path have prime length？

assuming that all the paths are integers， code and binary。How could I solve that problem？Well， yeah。

Well， okay， what you can do is you can always ask your NP workical。

 is there a path of length at most k for some given K， okay。

 that's the kind of question that it will answer for you。you can feed it， the instance。

 you can feed it a k， and it will tell you， is there a path of length k or less？Okay。

 so you could pick some prime number and it will tell you yes， there's a path of that length or less。

 but you know that's not answering your question yet。 so what else can you do？Yeah。

 you could enumerate through all possible ks， okay but the problem is now is that there's exponentially many possible ks。

 let's say if the length are integer is encoded in binary there are exponentially many possible lengths。

 so can you think of a more efficient way to do it？But what？Binary search yeah。

 just do a binary search right because this is an ordered list right it's you know you know if there's a path of length you know in most k then certainly also there's a path of length and most K plus one so just say you know is there a path of length at most you know whatever is some number in the middle of your range if there is then you ask is there a path of length that most this okay if there isn't then is there a path of length and most this and so forth so you zero in on whatever is the optimal length you could figure out what is the optimal length by using。

A polynomial number of queries to your NPical okay and these are repeat you know you have to make repeated queries just one query by itself is not going to do it right it just gives you a single bit as an answer okay you're going to have to make you know you know a number of queries so let's say that that capital N you know is。

