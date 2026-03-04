# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p12 P12 mar19 -BV1Dao8YQEEn_p12-

Okay。嗯。Okay。So。So let's get started so sorry so just a few reminders PSE three as due tomorrow。

 I do have PSE two that you can pick up at the end of class right and the midterm is Thursday after spring break and we will you know put out after PSE3 at least we'll put out a practice midterm and we'll schedule at least one review session all right that the TAs will run so last time we。

Introduce some complexity classes onto the scene， PP space X Xspace that's kind of a tongue twist or also E you so we observed that the time hierarchy theorem。

 let's you prove things like P is strictly contained in X space hierarchy theorem。

 let's he prove things like P space is strictly contained in Xspace you know okay we also talked about the extended church touring thesis which is like the sort of justification people have for y is P a reasonable thing to study you know that for a long time it seem to correspond very closely to know what can be efficiently computed by any physical device whatsoever you know using reasonable resources today that thesis is very severely challenged by quantum computing。

 you know at least if quantum computers ever become practical。

We'll talk about that at the end of the course。But I should say that quantum computing is pretty much the only thing that we know of that really challenges this thesis you based on the laws of physics that we know。

 we talked about some sort of strange phenomena that can happen in the world of complexity。

 okay the gap theorem where there can be arbitrarily large gaps between like one running time and the next running time you know after it。

 so that like if you you are willing to consider weird enough growth rates。

 then you can find ones for which there isn't a time hierarchy theorem。Speed up theorems。

 there exist problems that have no single fastest algorithm but only an infinite sequence of asymptotically faster and faster ones okay and then we started talking about padding which is like a technique by which you can translate conclusion like like in equality that you assume is true between some complexity classes to inequ for higher up complexity classes okay it only works for translating well we're down equality into higher up ones and not the other way around okay it's a very simple trick but you can get some some very surprising mileage out of it so I want to show you one example of that and you know since since you guys are here on time you get the special treat that I'll show you something that's almost identical to one of the problems on PSN3 okay。

So here's what we're going to do。 We are going to use padding to。😊。

To prove that P is different from linear space okay and this is a very you know and this is a very strange theorem right it's not it's not often that we can actually prove inequalities between complexity classes right you know this you know like we're going to talk today about the P versus NP problem right these are some of the deepest unsolved math problems that humans have ever asked Okay but this is one of the ones that we know this is one of the ones that we can actually prove okay but now here's the really mindbending part of this Okay I'm not going to be able to prove to you that。

😊，You know that P is not in linear space like I won't be able to give you any example of a problem that's solvable in polynomial time but not solvable with linear space I also won't be able to prove to you that linear space is not in polynomial time I won't be able to give any example of a problem that solvable in linear space but not in polynomial time now we think that there should be examples of both you know in both directions you know like if you know our current beliefs are true then these two classes should just be incomparable to each other right there should be you know languages in either one that are not in the other because you know should be you know in linear space you can take up to two to the end time you know but on the other hand you so you could probably do things outside of P but on the other hand you only have linear space and there may be problems in P that require you know say quadratic time but also quadratic space or something like that okay all I'm going to be able to prove to you。

Is that at least one or the other of these classes must not be contained in the other one okay I won't be able to prove which one I'll all be able to prove is that at any rate these two classes cannot be equal okay。

So just what it says。So how am I going to achieve that bizarre feat， Well。

 I already told you using padding。So here's the proof， all right， we're going to。

We're going to suppose by way of， you know， we're going to suppose that P were equal to linear space and then we're going to use that to derive a contradiction okay and what I claim is that if P were equal to linear space。

Then p would also be equal to quadratic space。Okay， why is that well。

 there are two directions to show here， first of all。

 I claim that P would be contained in quadratic space。😊，Why is that anyone？Yeah。Actually。

 I don't even need the space hierarchy theorem right now。

 all I want is that you know under this assumption P is in quadratic space。😊。

All I need is that linear space is contained in quadratic space right now right I don't even need that it's strictly contained okay if P is solluvable in linear space。

 if everything in P can be done in linear space， then certainly everything can be done in quadratic space the space hierarchy theorem is coming by the way it's going be so sorry so certainly this is true now。

😊，In the other direction， I want to show that quadratic space would be contained in P under this assumption。

 how could I do that anyone？Well。So here's what I'm going to do。I'm going to take a language L。

That solvable and quadratic space， Okay， and I need to show that this language is also in P。

So how do I do that Well， you know， I already showed you on Tuesday the basic trick of padding right so I can define a new language L prime。

 let's say。Which will consist of all。Ordered pears。Say zero。

 let's say x and then length of x squared trailing zeros。Such that x is in L， okay？

So this is a quadraically padded version of L。All。And then L prime will be contained in what， anyone？

L was solvable in quadratic space， so how much space do I need to decide whether a given input of this type is in L prime？

Linear， exactly why。Yeah， exactly because I've paddted out the input so that it's quadraically larger than x right。

 so now I just need time which is quadratic in the length of x in other words linear in the length of this padded input。

 which means that L prime is contained in linear space。😊，Right。

 but now if L prime is contained in linear space， then what else is it contained in？What。Well。

 here I can use my starting hypothesis right I was assuming that linear space is equal to p。

 so if it's contained in linearar space， then in particular L prime is also contained in P okay so I have a polynomial time algorithm to decide whether one of these things is an L prime okay but then what can I say about L itself anyone。

😊，So let's say that I wanted to decide whether x was in L and do it in polynomial time。

 how could I do that？Well， I could just take x， I could pat it out with a bunch of zeros。

 a quadratic number of them， and then I could run the polynomial time algorithm that I have to decide whether such a thing is in L prime。

 and that will tell me whether x was in L， and it'll do it in time which is polynomial and the length of x squared。

 but know that's just polynomial and the length of x。so that's polynomial， okay which means。

That L itself is contained in P Okay， so in conclusion， you know。

 everything in quadratic space is also contained in P。😊，Okay， so。So what do we get out of this。

 so we get that from assuming that p was equal to linear space。

 we also found that p is equal to quadratic space， Anyone see a problem with this？

Space hierarchy theorem， yes， now we use that and we say， well， if p is equal to both of them。

 then in particular。😊，Linear space。Would equal quadratic space。But。

That violates the space hierarchy theorem， okay， so contradiction。

 which means that P cannot have been equal to linear space。Okay。I always loved that argument。

All right。Okay， so now we're going to bring the， yeah。Yep that's right。

 yeah that's an excellent question we could generalize this argument to show that p is not equal to space of n to the100 or whatever right you know how would we do that right which over P was equal to space of n to the 100 and p would also have to be equal to space of n to the 200 or something else right now we certainly don't get from this argument that p is not equal to P space。

😊，Okay， that's， you know we get that P is not equal to any specific polynomial amount of space。

Okay because you know you can try it for yourself， try assuming that p equals p space and then getting a contradiction but say I mean if you can do it you should certainly tell me about it okay but I don't think that you can right because I think that what you know what this argument is sort of fundamentally relying on is sort of the different you could say closure properties of these two classes right P is like you know it involves all the polynomials at once okay and like so that if you have any one polynomial then it sort of wants to swallow up all the other ones okay in space you know space of n only wants to be linear space and if I try to make these two things equal then you know then the swallowing up quality of P wants to make linear space equal to quadratic space and then you know but then the space hierarchy theorem doesn't like that okay you know there would be no such problem if I set p equal to P space。

😊，Because they both have the polynomial swallowing up property。um。Okay。U。So。

Sorry so so now you know I want to bring nondeterminism onto the scene and so you know there are two ways that we can go about this you know the first is using the concept of a nondeterministic touring machine so I think that this was talked about in some of your recitations already but if not。

 then you know all the nondeterministic touring machine is you know with just like the NDfaAs that you saw earlier in the course just like nondeterministic finite automata except for touring machines。

😊，So a nondeterministtic toic machine。Is a touring machine， you know， I mean， just like with NDFAs。

 you know it's able to follow the Yogi Ber philosophy right when you see a fork in the road， take it。

It's able to you know when it when there are two different paths， you know。

 two different things that you could do like transitioning to state5 versus transitioning to state seven。

 writing is zero on the tape versus writing one on the tape。

 moving left versus moving right on the tape， you're allowed to follow both paths。

 you're allowed to do both of them okay so and then or you know let's say you know choose one of them nondeterministically as we say。

 okay。😊，So if we drew the state diagram for such a machine right you remember what the state diagrams for touring machines looked like where you know we would say something like you if you're in this state and if you see a zero on your tape。

 then right replace it with a one and you know move one square to the left on the tape and transition to this state okay or you know if you see a zero on your tape。

 we could say you know leave it a zero and move one square to the right and transition to this state okay so now and nondeterministic touring machine is just a touring machine where we're allowed to have multiple arrows labeled you know triggered by the same alphabet symbol coming out of the same state just like you know an NDFA was that but for finite automata okay？

And。You know， and， and。You know and then we can have certain states that are accepting states just like before okay here we're actually we're going to do something that you know we haven't done before now for touring machines which is to introduce an asymmetry between accepting and rejecting okay we're going to say that accepting is special okay so the machine。

So basically， a nondeterministtic touring machine accepts if there is any valid path that you can take that leads you into an accepting state。

Okay so you know you start out with an input written on your tape。

 you know it could be maybe I start on the lefthand side。

 it could be some zeros some ones and so forth and then we do the normal touring machine thing which is we read and write symbols。

 we move back and forth on the tape， we transition among the internal states of this machine okay but you as we're doing it。

 you know we may encounter situations where we have multiple arrows that we can take from a given state and if so we can take any of them that we want okay so you know and that could affect not only what state the machine is in。

 but it could affect what is written on the tape you know it could affect where the tape head is pointing okay where which square it's on and then you we say that the machine accept。

If and only if there is any path that we could take that would lead to an accepted state。Okay。

 so now you know， we， yeah。り出し。Yeah， yeah， yeah， so yeah， lead us to and accepting。

 you can call it a configuration， you can call it a state， whatever。

 but you know where the arrow points to a place where that we've labeled by accept。😊，嗯。😊，Okay。

 so now we can define non deterministic F of N time。😊，嗯。嗯。嗯嗯。嗯。Okay。All right， so now end time。

 nondeterministic time， F of N， basically just the class of all the languages that are decidable by a nondeterministic touring machine that runs in L of F of N time。

😊，Okay so it means you know for which there's some nondeterministic touring machine M that satisfies two properties。

 okay first of all， you know for every input x， it accept if it only if x is in L right that's pretty obvious meaning you know there is at least one。

 you know it has at least one accepting path if only if X is in L right for any input x in the language you know there's some path that leads to accepting and for any x that's not in the language。

 none of its paths lead to accept it okay that's what it means for you know nondeterministic machine okay。

 but second of all the machine has to run in F of n time。

 which simply means you know there has to be some constant。

 let's say C such that all of its paths halt after C times f of n steps you when you run the thing on an input of size N。

😊，Okay， so what can we say about this class？Well。嗯。Okay。All right， once again， you know。

 there's the principle that you know， if you're a Superman， you can always simulate Clark Ken， okay。

 you can always， you know， if you have a nondeterministic superpower。

 you could always ignore it if you wanted to， and so clearly end time of F of N is going to contain ordinary time of F ofN。

The one will be a subclass of the other now interestingly you know in the category of like others know strange things that we just happen to know。

 we happen to know that this containment is strict okay there is a theorem that says that like for each F end time of F of n strictly contains time of F of n now that sounds suspiciously close to P equal to NPp but don't get too excited about it because what it really means is that so what was shown is that in nondeterministic time of F of n。

 you could simulate time of like slightly slightly slightly more than F of n you know I think it's like F of n times log。

 log log F of n or something like that。😊，I don't know you remember what it is， Rob， I don't remember。

Wg star， maybe， yeah。So you can simulate slightly， slightly more than F of n time and then you know if you combine that with a powerful enough version of the time hierarchy theorem。

 then that's enough to give you that nondeterministic time can do exactly F of n can do just a little bit slightly more than time of F of n can do okay if you had。

 you， but then if you had let's say time of F of n， times log F of n。

 then no one knows how to show that that wouldn't just contain n time of F of n。😊，Okay， so okay。

 fine， so you know， at any rate， you know， time is contained in end time。😊，Okay。Now， I can。

I could bring another very important character onto the scene NP you know nondeterministic polynomial time。

 you know and you know like I apologize for all the names that we have you know N Xspace and so forth you know I wish that you know we were physicists and we called them things like you know quark and black hole and Big bang those are good names we're stuck with these okay but you but they really are you important concept you know and you in the acronyms do make them kind of mysterious sounding right so like they've know been used on the Simpsons and future you know the P versus NP problem has appeared on all of those as well as a bunch of lesser TV shows you know so all I'd find NP nondeterministic polynomial time so you can probably guess the definition by analogy that what we've already seen you know simple way to define it。

iss that it's just the union over all k of n time of n to the K okay。

 so it's the set of all the languages that are decable by some nondeterministic polynomial time touring machine。

Okay。So。All right， so you know that seems like kind of a weird thing to care about as much as we do right because know I mean know you could go through your whole life without meeting a nondeterministic touring machine unless you take a course like this one but let me give you an alternative definition of NP。

 which I think makes it practical， it' real worldor importance。

 you easier to see and will prove that that definition is actually equivalent to this one。😊，Okay。

So basically， I claim that NP is also the class of all the languages。

For which the yes answers are efficiently verifiable。 And what do I mean by that。

 I have to explain it。嗯。嗯。You know what I want to call this thing big。Because it's a verifier。呃。Okay。

 so you know， so this is the way of saying NP is the class of all the polynomial time verifiable languages。

 so what do I mean by that it's the class of all the languages L for which there is a polynomial time touring machine V。

 which we call the verifier， as well as some polynomial P which you know will give us the size of our witnesses as we call it。

 such that for every input size n and for for every input x of size n。😊。

You know now we have two different conditions right so there's an asymmetry here between you know x's that are in the language and x's that are not okay for every x that's in the language there has to exist a string an input a special input W called the witness okay you which is a P of n bits long。

 so polynomally larger than the input X， such that when you feed a V。

 both x and the witness than it accept。Whereas if x is not in the language。

 then there must be no witness W that causes Vxw to accept。😊，It has to reject for all of them。

So does anyone want to sort of translate this for me， well what is this saying？

WellLike what role is W playing here？Yeah。Inだ。Yeah， exactly it's like a certificate。

 it's like a proof that x is an L okay and the machine has to be able to check the proof in polynomial time okay and these two conditions that I've written here。

 this one and this one， you know if we think back to our discussion of logic you know of formal of proof systems and girdtel's theorem。

 these are exactly completeness and soundness。😊，Okay，Compness does that you know。

 there has to be for every true statement there has to be a proof right for every x and L。

 there has to be a W that you know causes us to say yes， you know， x is an L okay。

 soundness says that for every。X not an L， you know， there has to not be a proof。

 so for no false statement can there be a proof， okay these are the completeness and soundness conditions。

And you know， since we're just talking about finite statements here， right。

 there's no you like the statement that x is in L， we're not talking about like statements involving infinite numbers of things。

 theres you know there's no girdtel's theorem obstacle here so we can have both completeness and soundness in the same system that that's fine here。

😊，Okay。Yeah。Here一下。All right， so let's prove that these two definitions of NP are equivalent to each other so first of all。

😊，Suppose that we had a verifier for our language， then how would we。

How would we design a polynomial time nondeministic touring machine for the same language？

Given that we have a verifier。Well， yeah， so when I say that you're given a verifier， you。

 I mean that the verifier writes in some polynomial amount of time right and you can assume that you know it。

 so yes。😊，Yeah， you basically just use your non deterministic superpower to guess the witness W。

Right。Okay， so。😊，know so it's quite easy to set up a nondeminististic touring machine where you say。

 you know， you first like。Have to you set up let's say a string of length you know a blank string of length p of n for writing a guess onto it。

 okay you can do that because as we said， you know you know you know what n is you know what p is okay and then you just go through this string nondeterministically filling in guess is right so you say you can from here you until you hit the next hash symbol you can move right you know and you know you can write a1 and move right or you can write a0 and move right know and go back to the same state you can do either okay that's just a way of filling this entire you region here with a guess for what w is okay and then you go and you check whether your guess was correct or not right and you know by the completeness and soundless conditions if x was in L then there has to have been some guess you know that would work that would cause the。

That would cause the NDTM to accept。 if x was not an L。

 then there must be no guess that would cause the machine to accept。Okay。

 so how about the other direction？Supposing that we have a nondeterministic touring machine that runs in polynomial time and recognizes our language L。

 how would we design a verifier for L， you know， what would be the proof that we convince the verifier that X was in L？

Yeah。Exactly， that's exactly right， yeah， this is not yeah， so this theorem is really not bad， right？

😊，呃。Okay in this case the witness that would convince you that x is an L would simply be a you know I'll use these symbols for a description of。

 okay it would be a coded description of the path that causes your NDTM to reach an accept state in a polynomial amount of time right if such a path exists。

 you know， it's polynomally long you could describe it within a polynomial number of bits right and so then you describe it and then you know given that path you know given the specific path right it's quite easy to check whether or not that path really does lead to accepting or not okay and。

😊，If if there was such a path， then then you'll be able to describe it to the verifier。

 the verifier will accept if there's no such path， then anything you described to the verifier is not you either that's bounded by the requisite polynomial is not going to lead to accepting。

 so the verifier is going to reject it。Okay。So。So now let's see where this NP fits in among the classes that we've already seen。

All right， so what's something that NP contains， anyone？Yeah， sure， no。

 that's a problem it contains what's another complexity class that's contained in input yeah。P， yes。

 once again， you know， since time F of n is an n time F of n。

 it follows immediately that P is at least a subset of NP okay。😊。

You know I had you know I may have mentioned before that I get you know a solution to the P versus NP problem you know in my inbox you know every you know at least every week okay you know you know someone actually called me up you know on the phone to say you know I have a solution to P versus NP you know you want to hear about it and you know and he said。

 well you know I can show you that P is not even contained an NP so okay。

This is one of the things that we do know okay certainly P is at least a subset of NP whether you know the P versus NP problem is going to be asking whether it's a strict subset okay but now what about the other direction is can anyone suggest something that NP is contained in？

😊，Yes， okay， oh yeah， I'm sorry I have actually I should have told you this， you know。

 just like you can have nondeterministic P， you could have nondeterministic versions of the other things we've talked about as well。

 that's fine you can have next。😊，So we call it Nx， and what's that， that's just the union over all k。

Of end time。Of2 to the N to the K。Right。And one thing， you prove on the PSAT， I think。

 is that Fp equals NPp， then x also equals Nx。😊，Okay。😊，You can have knee。You know。

 the knights who say ney， right？This one is。That's this， okay。I should mention， by the way。

 that you know， just like you have n time of F of n。You can also have nondeministic space of F of N。

Okay。which is just this like class of languages that are deable by a nondeterministect touring machine where each path uses it most O of F event space。

😊，So this totally similar concept now and then you know you can define。😊，And peace space。To be。

You know the union of n space of n to the K overall okay there's a reason why you don't hear as much about NP space as you do about NP okay you know there's a very very beautiful and interesting theorem due to savage we're not going to prove it in this course okay it's a little bit too far field for this course but it is the proof is in the Ss or book if any of you are interested to see it you know and it's also like the proof is done in 6840 okay and so you're not responsible for the proof you know maybe just for knowing that this statement is true。

But。What the theorem of savage？From。1971。Says that。N space of F event。

 non deterministic space of F of n。Is actually contained in deterministic space f of n squared。

 which means in particular that NP piece space is equal to what anyone。😊，hu。Peace space， yep。

Itch means。NP space equals P space okay so the space analog of the P versus NP problem you know is resolved the opposite way as we think the time one is okay you know anything you can do in nondeterministic P space you could actually do in deterministic piece space you know at most the quadraically greater amount of space you know so this is just one example you know we see some more later that space kind of works very differently than time does as a resource。

Okay。😊，So all right， so these are more classes that you can talk about， but now you I claim。

That at the least， NP is contained in peace space。Can anyone see why？

Well actually one proof of it follows from what I just said right。

 you know certainly NP should be contained in NP space right you know you can always you know in polynomial time。

 you can only have used polynomial space okay， but then I just told you that NPP space equals P space。

 okay， but there's a much more elementary way of seeing like NP is contained in P space。😊。

So you know， suppose I've got a language in NP， it has a verifier like this one。

 how do I decide that language in polynomial space， you know。

 and keep in mind that you're allowed to use exponential time。Yes。Yeah。

 you basically just brute for search it， right？You know do do a brute force search through every possible W which is you know P of n bits long right there's two to the PN of them okay so you know your search will take two to the P of N time okay but you know this is the key point you can keep reusing the same memory over and over when you do this right you can you know you only need to use polynomial memory right because you're just you know for you know each W that you're trying is like a separate thing right you can just erase the previous you know computation and just you know for each W just you know reuse the same space and you know try it out and then halt and accept if you find a W that causes Vxw to accept okay so。

Certainly， NP is contained in peace space。You know， and we saw。

We saw on Tuesday that peace space is contained in X okay so this gives us you know another one of like these funny situations right where we know from the time hierarchy theorem that P is different from X which means that at least one of these three containments has to be strict。

 we think that all three of them are but you know all we can prove is that at least one of them has to be。

😊，Okay。You know， and you could keep going， you know， X is contained in annax。

 annax is contained in X space。You know and so forth right and you know。

 we know that NP is strictly contained in NX Okay， that's another thing we know there's a nondeministic version of the time hierarchy theorem Okay so we know that。

That NX is strictly larger than NP， which means that either NP is different from P space or p space is different from x per x is different from NX。

 but all we can prove is that at least one of the three has to be true and so forth。Okay。

 but you know， since this was a little bit abstract。

 let's talk about some examples of languages in NP。And make it interesting。

 let's take examples that are not also known to be NP。

 because we know that all of those are going to be an NP。Okay so。So of course。

 you know you know I mean you know we want to say that NP contains all of the you know problems for which solutions are verifiable okay and you know and examples of such problems abound like how about factoring for example you know we saw that in the very first lecture you know you know it could be very very hard to find the factors of a number but if you do find them then you know you could efficiently verify them okay you do have to be a little bit careful just because technically NP is defined as a class of languages not of search problems okay but you know but all this means is that like you it's kind of like with jeopardy you just have to phrase your answer in the form of a question you know and you sometimes you forget to do it it's just annoying right so like with NP you have you have to phrase your search problem in the form of a language。

Yeah。嗯。Yeah， I mean， I mean we can also just talk directly about the search problems if we want to。

 but as long as we're talking about the class NP we translate things to languages so here's an example of how we could do that for factoring okay we could talk about。

The language L consisting of all positive integers and written out in binary， such that。😊，Okay。

 so we could do something like this。You know， again， harking back to the first lecture。

 we could consider the language L， you know of all binary encodings of positive integers N that have a divisor that ends in seven。

😊，Okay okay。😊，This language， I claim， will be an NP， what's a proof that it's an NP anyone？Yes。

 the certificate is the divisor thank you， you know in most cases not all of them but most that we'll see proving something in is in NPs just really really easy okay you say well you know the witnesses you know here's the witness and it's obvious that you could check it okay so like you know if we ask you you know on an exam or on a Pet or something right you know just like realize that you know that you do have to prove something is in NP but then you know once you realize that there's probably just like one sentence of proof that suffice this okay。

😊，All right， you know so now this this problem is not obviously equivalent to factoring right。

 maybe it's easier right， maybe you know you know you could do this right。

 you know you would know that there's a divisor ending in seven that's great to know right。

 but maybe that wouldn't tell you what the actual factorization was okay but you could also do something like。

😊，L of。An and I such that。So you could let L consist of all ordered pairs。

 n and I such that you if you factored n into prime factors and of course it has a unique prime factorization and then you wrote that prime factorization in a canonical way meaning let's say you sorted the prime factors from you know smallest the largest you know you wrote the prime factorization you know in some completely you know canonical way so you know for each prime factorization there was only one way of writing it that way okay and then you know you just have a string of bits and then I can just ask is the ih bit equal to1 right and so then you know I can let my language consist of all pairs n comma I such that the ih bit of the canonically written prime factorization of n equals one okay this was a language that I claim is equivalent to the actual problem of factor know if I could factor that's。

I could decide that language conversely， if I can decide that language。

 then I can also factor because I just go through all the different values of I。

 of which there's only polynomialally many， until I have extracted the whole the entire string representing the factorization。

All right。So all of that entitles us to say that factoring is an NP problem。Okay。

 another good example is graph isomorphism。😊，So I can let GI。Be the language of。Let's say。

All binary encodings of pairs of graphs， let's say， undirected graphs， G and H。

 such that G and H are isomorphic。Okay， that's another famous problem， why is GI an NP anyone？

What's the witness？yeah the isomorphism right isommorphism is just like is basically just a permutation of vertices right its how do you permute the vertices of G in order to make G equal to H right so there's n factorial possible permutations of an n vertex graph you could list one you know using only n log n bits okay which is certainly polynomial in the size of the graphs which is n squared right so so G is another。

😊，NP problem。Okay。Okay， so you know， how about circuit set。

 okay this language is going to consist of all。Binary encodings of boolean circuits。

 so you know a circuit of let's say and or in knot gates， you remember circuits， right？

For which there on let's say that the circuit has n inputs and all the circuits for which there existed in input X。

Such that c of x accept。Okay， so all the circuits that have some input that cause them to accept。

Okay， why is this language in NP， What's the witness， anyone。X， the witness is x。

 so circuit set is also an NP。Okay。We can。You know we can have if we like circuits。

 we can have more fun with that here's another one of the earliest you know examples that were' studied of an NP problem is what's called the minimum circuit size problem the MCSP okay you know we talked at the beginning of this course about the problem you know I give you the truth table of a boolean function right then you know what is the smallest circuit that represents that function right does this function have you know every boolean function has some circuit that represents it maybe an exponential size one we saw the proof of that okay but does this function have a small circuit that represents it well that's a much much harder question and in fact that's exactly what the MCSP asks okay so now again we have to be careful to phrase things as a decision problem so we could say this language consists of the set of all encodings of。

😊，Ban of the truth tables of Boolean functions F Okay so so now you know the input you know is really of length2 to the n here the input is going to consist of the entire truth table of this function F okay so you can say you know there's。

Like the input is length big n where big n is 2 to the little n where n is the number of inputs to f okay。

 or alternatively， if you want to think of n as the size of the input to this problem。

 then F is a boolean function that only takes log of n bits of input Okay。

 those are two equivalent ways of thinking about it All right， but in any case。

 the input is a truth table of a Boolean function F together with an input K， such that。

F has a circuit。F has a Boolean circuit， let's say of and or in not gates。Of size at most K。嗯。

So why is this language in NP， what's the witness anyone？

The circuit exactly and you know you might think that this circuit would require exponential time just to verify that it's correct Well。

 you know as it requires two to the little end time to verify okay。

 but again that amount of time is linear in the size of the input。😊，Okay which again。

 is the input size is already two to the end， so we're totally cool okay。😊，Okay， more NP problems。嗯。

All right， so let me show， you know， I'll go through some of my favorite examples。

 some classic examples。Okay， so if we have a graph G， then we say that G is three colorable。

 if there's a way to color each of its vertices， you know， red， blue or green。

 in such a way that no two adjacent vertices are colored the same。Okay， so for example。

 is this graph three colorable？Well， let's try， it doesn't matter what I color the first two you know countries right。

 this country can be red， this ones should be white anyone。Blue， all right， then how about this one？

Green， how about this one？Blue， how about this one。Red， about this one。Blu， yep， good。

 so you know now if I were to create a new country。Like here。

 then I would get a non three colorable graph。Right。

Does anyone know whether the map of the continental United States is three colorable？No， it's not。

 it's not， is it for colorlerable？Yes， why is it forcolable？

Because every map that you can draw on the plane or on the globe for that matter is fourcolorable。

 that's a very famous theorem which was only proved in 1976 with the help of a lot of computer enumeration of cases I should mention that if the earth were shaped like a donut。

 so if the earth were a tourists， then it would be possible to divide it up into countries in such a way that you would need seven colors。

you can check that， but seven colors would always suffice in that case。

And you if the Earth were a donut with some number of with different various numbers of holes in it。

 there's a formula for how the number of colors you would need to color。

 a map on the earth would increase with the number of holes in the donut。

But if you have you know a donut with zero holes or in other words， a sphere。

 then any map that you draw on it can be colored with four colors only right that's the four colored theorem okay。

😊，Okay but here we're asking for you know three coloring okay and you know I haven't said anything about you know that G has to be planer right that G has to you know be dable on a flat surface right you know you could imagine you know that you're trying to color a map where you know country you know where countries are able to like jut up you know into the sky and to meet up with other countries that are far away well actually you know that's not that bizarre or you know you could have countries that are just not contiguous territories as in fact you know there are countries that are like that right that they have outlying islands or whatever you know so the countries does not have to be you know the map of the countries and which ones are adjacent to which other ones does not need to be a planer graph okay but you know even if G we a planer graph you know it would still be nontrivial to ask the question is G3 color。

Okay， because some pointer graphs are three colorable and others aren't but in any case。

 I claim that this language is also in NP。 Why is this one an NP？But what's the witness？

The three coloring yes， just say give the three coloring and then it's quite once it's given。

 it's quite easy to check that yeah， know you just have to check that no two adjacent countries get the same color okay what else？

😊，Okay，😊，We've got the set of all the encodings of graphs G， such that G has a Hamilton cycle， right？

What's a Hamilton cycle， it's a tour that visits each vertex exactly once and then returns to the starting point。

 okay， you a cycle to visit each vertex once， okay， this graph has a Hamilton cycle namely like that。

😊，Okay， you know， you can easily design graphs that don't have Hamilton's cycles， okay。

 but once again， this is NNP right what's the。😊，What's the witness， it's the Hamilton cycle， okay？

Okay so you know so you know all these you know have like a similar kind of flavor right that I give you like a system of constraints I ask you。

 you know they all have the character of some puzzle that you're trying to solve right where once you have the solution。

 it's very very easy to check it but if you didn't know the solution then you know maybe it would take you a very long time to find one and in fact。

 you know you know with the sole exception of factoring。

 all of these problems have the property that a priorityi。

 you you don't even know if there's a solution if there isn't one or if there isn't one and you know you don't even know a priorityi how many different solutions there might be。

😊，Okay， so subset sum。😊，It means， you know， I give you a collection of integers， say A1 up to AN。

 as well as a target integer K， and then I ask。And it's the set of all of these for which there exists。

A subset。Of the integers from one to n， such that。The sum of those integers is equal to k。Okay。So。

 it's basically just asking， is there a subset of my integers that add up to K？嗯。Okay， box packing。

 like I can give you all right， instead of specifying this as a language。

 maybe I'll just describe it in English， all right。😊，I will give you the。Dimenssions， you know。

 length width and height of a collection of boxes。And then I will also give you the dimensions of the trunk of your car。

 and I will ask， can these boxes fit or can they not fit？

OkayThis is a problem that some of you may have encountered in life， okay， certainly have。

 you know you try packing things they don't fit so then you take them out。

 you rearrange them a different way， you try again。

 right this is an NP problem right what's the witness。

 it's you know a specification of how you should pack。Okay。Okay。You know。

 and then you know these are sort of like games but you could take things that are literally games like Sudoku。

 okay I give you， you know you have to generalize it to end by N right but I give you an end by N Sudoku puzzle。

 I ask is it solvable okay， you know what's a witness if it is， it's the solution？Okay， there's。

 I could do this with a jigsaw puzzle。Right， so you know。

 a jigsaw puzzle that has a picture on it is in some sense from a complexity or an asymptotic point of view is quite easy right because all you've got to do in some sense is I just like compare if the picture is sufficiently detailed and just compare every pair of pieces you and then you'll see if the pictures match。

 okay， but yeah。😊，平究めゃ。how about， yeah yeah， okay， that's an excellent question。

 the whole thing problem。😊，There's an example you've seen， okay。

 or actually another example that I talked about on Tuesday。

 which player has the win from a given chess position？😊。

Right that is a problem that certainly no one knows to be an NP okay know we generalize ch to an end by end board okay with you know I would say two end pieces on each side okay you know so why is that not obviously an NP well because to say that let's say that white has the win from a given configuration means that you know there is a way for white to move such that for every way that black moves。

 there's a way that white can move such that no matter how black moves。

 there's another way that white can move and so forth and you know even just to specify the entire tree of you know of winning plays from that point could require an exponential sized tree right so we don't know how to give a short witness for that？

Yeah。It does， it does， yeah， but with you know some choice of I forget what choice of pieces。

 but you know like with almost any standard choice of pieces。

 people have you been able to come up with encoding showing that well they've been able to show that this problem is either piece based complete or act complete。

 I'll define those concepts later， okay which is very， very strong evidence。

 although not a proof that these problems are not an NP。

Basically means that the only way that they could be at NP would be if NP equald P space or NP equald x。

Yeah。The whole thing problem。Computer vs。Yep， yes given this I give you a description of a touring machine。

 does this is there an exponentially large input that causes that touring machine to hold in exponential time that problem is complete for NX。

😊，There are probably。There are okay， so you got to be precise about your question， okay。

 there are problems in mathematical logic， all right， I can give you an example。😊，All right。

 so semblance to real life， you know， I'll let you be the judge， I guess。😊，Okay。

 there's something called Presssburger arithmetic。And what this is is basically， you know。

 I give you a sentence about positive integers that can involve universal and existential quantifiers and it can involve variables and it can involve the plus sign okay it cannot involve the time sign okay but you know I could ask is it the case that？

😊，For every integer x there exists in integer y such that you know y plus1 equals x okay and that's a true sentence right but you know but I could construct any sentence that I wanted of that sort of form okay now it has been proven that there is an algorithm to decide the truth or falsehood of sentences in Presburg or arithmetic so any sentence you know involving integers and for all and there exists and equals and plus okay there's an algorithm for that。

 but the algorithm takes an amount of time that's like a tower of exponentials I believe actually maybe it's maybe it's only exponential space or it's only doubly exponential space or something like that okay I forget exactly what the complexity is but this is a problem which is known not to be an NP。

You know， the set of all sentences of this form that are true。by the way， if I allowed the time sign。

 then this problem would just become undecidable， for reasons related to girdless andcompleness theorem。

Okay，With only plus signs， I get a decable problem， but one which is provably not an NP。Okay。

 so so by no means is NP the ceiling of computational difficulty， you know， in fact。

 the hierarchy theorems tell us that we can construct arbitrarily difficult problems you know。

 but which are still decidable right we can go up as high as we want okay NP is just you know。

 the class of all the efficiently verifiable problems。😊，So。嗯。U。All right。

 so let me give you you know like maybe the most wild example so far of a language in NP which。

You know， sort of starts to show you， you know， just how any the consequences would be if P equald Np okay this I'll call the theorem language okay and this just。

consists of all encodings of mathematical statements， S。

 say written in the language of first order logic or something， such that let's say， okay。

 I have to say together with a positive integer n， written out in unary notation， such that S，😊。

Has a proof。In let's say， Zf set theory。Which is it most？En bits along。Okay，So again。

 this again is a language in NP right because you know if something is in the language right it's saying that there is a proof of S。

 okay the length of the proof is at most N which is a polynomial in the length of the input in fact linear in the length of the input okay and you know there are we actually have programs you know not only that you could write in principle but that have been written that can check the validity of aclaim know formal proof in the F theory。

 if you want to learn about how to do that you can take Adam Chapaa's courses where you know they're all about that about how you do formal verification。

😊，So this language is an NP， okay？😊，So。Okay， so of course the literally million dollar question in this business is you know whether P is equal to NP and you know I should say that you know it's really you know partly just for historical reasons that we take this as our flagship question。

 I think someone is actually taking a photo of you know， writing it， okay， I can pose with this。

 for sure， but。😊，Okay， so you know it's sort of for historical reasons that we take this as the flagship right。

 I mean P versus P space is like an equally enormous question you could say you know NP versus P space right you know almost any of these questions you could ask you know we don't know the answers to any of them but you know but you know if you have to pick one of them as sort of the flagship this this is a good choice and so you know this is just asking if you can efficiently verify the solution to a problem you know when it's given to you then can you also efficiently find the solution okay and so so this problem was first you know sort of formally posed in 1971 in you know the very famous paper by Steve Cook where he also introduced the concept of NP completeness。

 I haven't defined NP completeness yet know but we're going to maybe maybe。😊，Or break， okay？😊。

But informally， you know， this question was first asked as far as we know in a letter in 1956。

 did anyone know who wrote it？It was actually written by Gerirdel。The incompleteness guy。2。

To John Vanon Neummann， okay and Gerdel know by this point was kind of a recluse you know in the Institute for Adv Stud in Princeton。

 which any of you have ever visited it is like is basically like an asylum in the middle of the woods I spent a year there as a postdoc so I know something okay but so you his great incompleteness theorem that was decades in the past。

 but you know he wrote a letter to John von Neumman with von Neummann at the time was dying of cancer in the hospital fortunate and he wrote a letter saying you know my dear Vanon Neuummann know I hope you're getting better。

 which unfortunately he wasn't but since you are let me take the liberty of asking you a mathematical question。

 and then he says， you know consider this language basically consider the set of all of the statements of Zf set theory that have a approved。

of it most end symbols okay and then he says， look。

 you know you know it is obvious that you know in spite of the unsolvability of the enshidings problem right which we saw earlier in this course you know which he was you know played a role in proving right in spite of the fact that you know there is no algorithm to tell you whether a given statement of set theory has a proof or doesn't have a proof。

 you know with no bound on the length， you know， obviously there is an algorithm to tell you whether a statement and set theory has a proof of it most end symbols。

 okay what is the algorithm。Just enumerate all the possible proofs one by one。

 there's only a finite number of them okay but he said， you know， in this case。

 the obvious question that one wants to ask is what is the running time of the optimal such algorithm okay the notion of running time you know people were most people were not even thinking about it talking about it right because you know。

 this is the obvious question that one would ask okay you know that does the optimal machine you know。

 need an amount of time that grows exponentially within or you know， you know。

 he says you know I cannot you know rule out that you know that you know I see no way to rule out that there would be a machine that would use an amount of time that would grow like n squared or even only like n okay you know you know。

 he says， you know and then he points out， you know the only the only lower bound that you know that he could see was that you need you know you need at least n time but。

So you know then he says you know if there actually were a machine that had you know this sort of running time。

 you know this would have consequences of the greatest magnitude okay for it would mean that the mental effort of the mathematician could be completely replaced by machine and then he says in a footnote apart from the postulation of axioms okay so what he's saying is that you know if P were equal to NPp right then all that would be left for human mathematicians to do would be to just sort of specify what system of axioms you wanted like Zfat theory right and then you know you could just ask your computer you know is there so is you know let's say you want to know about the Rimon hypothesispo you just ask is there a proof of you know a billion symbols and if there is a proof your computer would say yes there is and you know it's true you know if not okay so you know maybe it has a proof but one that's you know with an n so enormous that you wouldn't。

you know that you still wouldn't know the answer but in that case like he probably couldn't even write down the proof anyway right so like if there's a proof that's short enough that it could be like checked by a human being then your computer would be able to find it in a reasonable amount of time this is really what we're talking about okay so you know oftentimes people talk about well P equals NP is important because you know if it were true then we would be able to break a lot of cryptography you know almost all cryptography that's used today and we'd be able to speed up the solution of all kinds of industrial optimization problems and you know planning problems and you know know that's all true but you know in sometimes we' like we're asking about something that's almost metaphysical right you know can we like automate mathematical creativity okay now I should hasten to emphasize that even if P is not equal to NP you know as most of us think okay that。

That doesn't rule out that you could have a machine that simulated everything that the human brain does right for example。

 right it's like the joke of where someone is you is outrunning a bear and their friend says you don you know that you can't outrun a bear and they say。

 well， I don't have to outrun the bear， I only have to outrun you you know an AI would not have to be optimal。

 it's solving NP complete problems in order for it to be better than us an AI that couldn't solve NP complete problems but could merely do things faster than we did。

 you might still be powerful enough to take over the world and enslave us so I don't want any of you to worry that if P is not equal to NP that that couldn't happen but but if P equal to NP then you that would say that just automatically you'd have this way to very。

 very quickly produce an answer like whenever and efficiently checkably。

An exists Okay so that's what we're talking about here so all right to have an excellent spring break everyone so see I have PSAT two。

 which you can come and pick up here and remember PSet3 is due tomorrow at five all right。有。いや。Yeah。

Okay。First。I know what happened。It's better this time。Weird。These things happened。Just like randomly。

所人等于食上。ま。It's happy。くださいで。Yeah know how they honor the grades on stellar， so I would go again。

I missed that they stopped。I kind of stop teaching。T back。あると。啊。よは。哪个是M呀？看我说外套。哦，小起了那个。

Do you have some tape？Do have some tape for the mic？Yeah， it's he never uses that for。

That's the ones that moves the ones。It's pretty funny。And this one sparingly。Thanks。あ你的没什么。嗯。😊，NoNo。

 no， I was just checking。お曜びです。Oh yeah， perfect。It's just。Doing that。Figure it's safer。

Somehow didn't seem to need that last class but。bettertter safe than sorry， yeah。

 these things can be a little。So doest thing I you make a little triangle。Oh。Oh。

 I see that provides some rigidity。Yeah， just so it'll。 So this should stay in place more easily。

 just from。W， pro。Yeah， I just wiping out some chuck。I mean。Yeah， that seems a lot better。

 good thanks。