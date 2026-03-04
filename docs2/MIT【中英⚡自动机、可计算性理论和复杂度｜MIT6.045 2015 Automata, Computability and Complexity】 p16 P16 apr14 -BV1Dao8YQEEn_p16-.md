# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p16 P16 apr14 -BV1Dao8YQEEn_p16-

All right， let's begin。Can everyone hear me？Okay。 so let's start with a recap of what we ended last class with。

So last time we were talking about。NP with an NP oracle， the polynomial hierarchy。

CoNP with an NPical and so on soth。Let's start with a little picture。嗯。CfP， and then we saw。

NP over here。ConP。So we've seen these before and then last time we saw。

What's called the second level of thepomial hierarchy， which is。NP with an NP oracle。And we saw。

Co NP with an NP oracle。This thing over here。 So this class you should often call。Sigma2。

 this one's often called。Phii 2， sometimes the superscript P。And there's another class here。

 which is inside both of these。Just。P with an NP orac， sometimes called。Delta 2。

And you can keep doing this， you can add another Oracle to NP and you'll get NP to the NP to the NP and here you can get CoN to the Co NP to the CO NP and so on and you can。

Keep doing this and what you'll get at the end of the day is the polynomial hierarchy。

Looks like this。And。That's just a union of all sigma cases。One way to think of it is just。

Significate。Or it's just take all the ps。Add them up， that's fine too。So。

This is the problem Archarchy and all of this sits inside of peace space。 So that's our picture of。

Complexity classes and last time thing we saw。We saw a problem here。We saw that。

The factoring problem is here。So it's both in NP and in Co N and this。

Prevent it from being NP complete in the sense that we don't。If factoring was NP complete。

 then Co N would equal NP。 and we don't think that's。That's the case。

 so it's very unlikely that factoring is uncomplete。Okay， any questions about this picture？This is。

Does a diagram make sense？Okay。And。All right， so today we're going to talk about。Peace space。

 which is。WellW whichch includes all of this。And well， let me just cut to the chase。

 so last time we talked a little bit about pre space as well， right？So I think。let's start with。

So let's start with peace based hardness。So of course you've seen peace space before。

 so now we're going to discuss some hard and complete problems for peace space。Okay， so。Okay。

 so what is peace pace hardness can so on？Tell me what peace based hardness is。

Guess what peace based hardness is an analogy to NP hardness？Like。Yep， that's exactly right。

Convert any problem in peace based to that problem， so we say。You know。Yes， x is piece based hard。

For all languages in peace space。L can be solved if you give it an article for X。

So this would be the this would be。Peace space hard under touring deductions or similarly。

 you can say。And。Reduce the sticks。Under。Under mapping reductions。

 that would the other definition of peace based hardness。And so what's peace based completeness？

None of we know what peace based hardness is。It's。当时。That's also piece space hard。That's right， yeah。

 so generally， this is always the case that completeness for any complexity class。

 once you defined hardness is always。😊，problemble is complete for that class if it's hard and also in the class。

Pace complete a piece space complete problem would be a piece based hard problem that's also in peace space just like NP completeness was an NP hard problem that was also in NP。

All right，Peace face complete problems。So when we started NP completeness， we had this。

Obvious NP complete problem which Scott calls the the problem right you're just given a Turing machine and you're given some time bound and then you asked you're given a nondeterministic tuuring machine。

 you're given a time bound and you asked， well what would this nondeterministic tuuring machine do in these spin steps does it accept or not so it's kind of obvious why that problem is NP hard because it almost literally encourage every NP problem in the problem。

So similarly， what would be？And obvious。Peace space hard problem in analogy of the problem we saw。

A couple of weeks ago。So any guesses for how you would construct a piece based hard problem？

know with that strategy that basically you just make the heart problem， something trivial。

 just make it simulates a machine。Any guesses？You just have to give it enough space。 that's right。

 so we just want to define some problem，'s let me call it It know。

So it's the space version of the dough problem。And just so there's some tuing machine。

And you just give it enough space， so let's say you give it zero to the S space。

And then the question is， does this tuing machine？Halt and accept。Using， you know， OS。

Tape squareters or whatever OS space。So。And accepts。Let me see。Using OS space。Right。

 so in analogy with the dough problem we solve or NP completeness， this problem is piece based hard。

 kind of trivially because any piece based problem you can map to this problem。

So maybe it's not that interesting， just like the。The NP complete problem that we saw was not that interesting。

What's more interesting is that there are natural peace space complete problems， you know。

 stuff that。That doesn't look like this。You，Questions that are not just about tuing machines。

 questions， problems that are not just constructed for the explicit purpose of being piece based hard。

So let me give you an example of。Rea natural。Peace space， hard problem。

And this relates to something we've seen before in the class。Probably like two months ago or so。

 so I don't know if you guys remember this stuff anymore， but。

So remember regular expressions that we saw like a long， long time ago， I don't know。Es ago。Yeah。

So you have some kind of expression that look like。You know。like。0 or。0ero one。Start。One or zero。

 zero， zero。Or1，0。St。1，0。star。Okay， how about this， Okay。

 so this is just some regular expression I just wrote wrote down off the top of my head。

So say I give you a regular expression like this。Let's use LFR to doote。

The language expressed by this regular expression。So I give you a regular expression like this and I ask you。

 is LFR just equal to all possible？Binary strings， is this just 01 star。So this is the question。

So this is a simple simple problem， I guess， right， I mean， the problem makes sense。

 I the statement of the problem clear， I'm going to give you a regular expression。

' written something like this。 and you have to tell me whether this regular expression generates everything。

 So just is it just kind of trivial。I mean， it looks complicated。

 but is it just generating the trivial language， which is just everything？So。

What I'm saying is this is a pretty reasonable problem， and this could have been a problem。

We might have。Concerned ourselves with when we were studying regular expressions。

 So it turns out that this problem is peace based complete。So good。So what does that mean？

That means A， this problem is in peace space， so you can solve this problem with polynomial space。

And B means that every problem in peace space can be reduced to this problem。

 so this is one of the hardest problems in peace space。So that may be surprising。And more generally。

 if you're given two regular expressions， you know R1 and R2 and you're asked。

 do they generate the same language， this problem is usually called regular expression equivalence。

 This problem is also piece based complete。In fact。

 the problem in my stated here is a special case of that problem。

That problem is also piece based completely。So there can be interesting problems on our pre space complete。

 I guess is what I was trying to show you with this one example。More。

 more informally or more to do with problems that you deal with in everyday situations。

If you think about NP completeness。N complete problems have this flavor of puzzles，You know。

 you want to find a three coloring or you want to see if the graph has a Hamiltonian cycle or you want to find a solution to a Sudoku puzzle。

So these things are always of the kind that you're looking for a solution。

 so you're trying to solve a Sudoku puzzle， you're trying to fill up all the squares with numbers that make sense and satisfy all the constraints。

And this is a property of NP problems in N because problems in NP are the kinds for which you can show a witness。

So there are naturally these kinds of puzzle solving problems。So in this way。

The intuition for peace based problems is that they are problems which are usually。

Like a two player game， so there's two people who are competing。And you want to know if。

Player one wins or player two wins in some kind of。Two player competitor game。

 So a really good example is chess。So I'm not going to explain the rules of chess。

 obviously that would take half an hour。But just think of chess。

 so there's two players black and white。And。You want to decide？

If starting from the usual configuration of pieces。Does White win？Or does black win？

Assuming both of them play optimally。So this problem， as I've stated。

 is not a great computational problem because you know chess is just a finite board game where there's like 64 squares on a chess board and there's only finitely many things you can do so you know this is not the kind of problem we like to study in computational complexity。

 but let's try to generalize chess to some kind of end by end board so know there theres。Right。

 n squared。Squares on the board and。Maybe you have the same pieces。

 doesn't really matter what the details of the game are。

 but maybe you've been given a configuration of all the pieces， and then you're asked。

Does white win from this configuration， assuming both white and black play optimally？

So this could be called something like generalized chess。

 some generalization of chess to end by and boards。And you know now we have a family of problems。

 we have growing input sizes， and so now we can talk about the computational complexity of this problem。

 and it turns out that this version of generalized chess is piece based complete。

And chess has this flavor right chess is exactly a two player competitive game。

 two people are playing with each other， and both of them are trying to win and answering this kind of question of who wins in a two player competitive game turns out to usually be。

In peace， in peace space complete。At least if there's some kind of reasonable upper bound the number of moves the game can take。

 so a whole bunch of two player games turn out to be piece space complete so if you're interested you can look at Wikipedia's article on。

Peace based complete problems and there's like there's probably like 30 games that are just normal games that you've probably played in your childhood that turn out to be peace based complete。

So it's pretty interesting， actually， another interesting game is this game geography。

That you may have played when you were a kid， and it's this game where you。

Say you're playing with another person you have to name a country like you start with the country and or you say Canada and then the other person has to say a country that starts with the last letter of the word Canada A。

 So the other person says're Afghanistan and then you have to say a country that starts with n and so on and this game goes on and you're not allowed to repeat countries and the person who's not able to name a country at the end of the day loses the game So this is also an example of a twoplay competitive game and you can I mean this game again。

 as I said， there's only like 200 countries or so so it's a finite game there's nothing that interesting about it but if you generalize this and the way to generalize this be you're just giving a graph let's say where the vertices are countries and there's arrows showing you which country can be said after in another country name has been said this game is often called generalized geography generalize in the same sense that we generalized chess to。

Arbitrary board sizes。And generalized geography is also one of the good examples of peace space complete problems。

And it's also in the textbook and the Sster books， if you're interested in seeing how you show a game like that isPaceSp complete。

 you can look it up。It's pretty cool， it's pretty interesting that very reasonable and interesting problems turn out to be captured by this very natural complexity class piece space。

Okay， so。Are there any questions about this so far？

Palom hiarchy about peace space or about peace space complete problems。That we're good。Okay。

RightSo when we talk about NP completeness， we had this obvious N complete problem。

 which is the analog of this problem over here。😊，Then we had we had some interesting MP P complete problems。

Like， the traveling salesman problem or。re coloring a graph and so on and so you we talked about some interesting piece space complete problems。

 but there there's also the canonical NP complete problem3S。

 which is a very nice and convenient problem to show NP complete because it's often easy to show other problems NPP hard starting from a reduction from three sad so in some sense three sad is like。

The the weapon of choice when you want to prove NP hardness reductions。

 like it's always a great place to start if you want to show a problem N NP hard。 So similarly。

 there's a canonical。Peace space， hard problem。 That's not one of the ones I've mentioned。

 which is often the。The main heat space heart problem you would start off with if you wanted to show reduction。

And this has a flavor similar to the NP complete problems we've seen。 and in fact， its similar to。

Problems complete for NP， Co NP， NP to the NP， and so on。So。

So let me give you a unified view of how you can come up with a bunch of interesting complete problems for some of these classes。

So。So let's start with NP。So we've already seen examples of MP complete problems。

And so what is the essential flavor of an NP problem you're given some kind of you're given a system of some kind of constrained system。

 and then you're asked， is there a way to satisfy this？And in three sec， and in general， in just。

The satisfiability problem， you're given some formula。 Let's say you're given a formula。fi。

And variables， let's say， some polynomial size formula n variables。 And then you're asked。

 do there exist x1？To extend such that this formula is true。

So does there exist in assignment to the bits x1 to xn so that this formula phi of x1 to Xn is true。

This is an NP complete problem。And， you know， you can。

You can always think of anti problems written out like this。This is the witness asking portion。

 like does it exist a witness that satisfies this part over here？Similarly。

 you can come up with a problem that's complete for Co&P。Which looks exactly like this but。

There's for all quantifiers。Instead of that exists quantifyfires。So。

So there's probably many ways to see this， so we redefine CoNP as those languages whose complement is an NP。

So， you know， if you take the complement of this expression over here。

 the fors are going to become there exists。 But maybe another way to see it is you know Co N complete problems are just。

Things for which there is a no witness， right， you want to say that。嗯。Sure。

 there's something that does not satisfy this， and that's something you can exhibit because you can come up with these X1 through XN。

So this is one way to think of NP and Co NP completely problems。

And this way are thinking about is nice because now you can write down complete problems for it。

NP to the NP， for example， and it turns out that N to the N has a complete problem that looks like this。

Questions。Do that exist variables x1 through xn so that for all assignments of variables， Y1 to Y N。

 some formula， which now involves x1。逆戦？All the variables is true。So this would be an example of。

A problem complete for NP to the NP。 if you want a problem that's in co NP to the N。

 this class over here， then you would swap the order of the poifiers。And in general。

 you can construct problems that are complete for the ca level of the polymid hiarchy by just having enough quantnaifiers that you have。

If you want to go to the K level， you'll have K alternating quantifiers。This there。Oh， this one。Yeah。

 if you have two exists， then that's basically the same as having one exists， right？

These classes are closed under。Plynomial time reductionds， right。You can I mean。

 if you had two exist， that's just like having two n variables here and n variables or。

There would be two in variables here as well。 So I mean， that exactly fits into here。

So there's not- you haven't gained anything if you just had two in that exist quantifiers。

Maybe the other way to think see why this is true is that。

You want this problem to at the very least be stronger than NN Co and P because if you have access to an NP oracle。

 even if P had access to an NP oracle， it would certainly be able to solve NP complete problems because while you just ask the oracle。

 but it will also be able to solve Co NPP complete problems because you just ask the oracle and you take whatever answer the oracle gives you and just flip it。

 the oracle says yes， you say no if the orle says no， you say yes。

So this class should be at least as powerful as both of these guys。

 so you can see that this problem embeds both of these problems in it。

 so if you just want to solve an NP problem with this。

 just forget about the y variables like make your formula just not depend on the y variables and similarly if you want to solve a co NP problem。

You just make your formula not depend on the x variables。

 so just use the y variables to encode this for all quantifier。

So N to the N is something that includes both of these guys。And it's。Yeah。

 it's probably a fun exercise to try to show that this is actually complete for MP the N。

 but it would kind of take。Too much time。But yeah， that's a good question。

 would why don't you just have all exist quantifiers。 So I mean。

 the importance is that the quantifiers alternate because we just have quantifiers the same type。

 then it's just the same as having one set of quantifiers。Okay， any other questions about this？

So the reason I mentioned these was that I'm going to give you a complete problem for P space that kind of looks like this。

And so this problem is called the。The true quantified Boolean formula problem。

Just often abbreviated to TQBF or just QBF。And。The thing here is that you're given a formula again。

 and this depends on a whole bunch of variables， x1 through xN， let's say。And but。

The interesting part is。You alternateinate all the quant first。

And let's say whatever the last one let exists in。Right。

So this last guy over here should either be an existence sort of for all。

 depending on whether n is even or odd。Let's say n is whatever n is larger that the last guys exists。

 So I mean what I'm saying is the quantifiers alternate。So right， what is this question。

 it's saying is there a way to set x1 so that no matter how x2 is set。

 there's a way to set x3 so that no matter how x4 is set。

 there's a way to set x5 and so on that makes this formula true。So when I say it like this。

 it kind of just looks。It just looks。Crazy， and it's not clear why this would be an interesting problem。

 but。It encouraged the essence of these two player games。

 And the reason is that you can think of the。Let's say we're asking the question。

 does the first player win and let's say。嗯。Let's say every step of the game。

 the player has only two options。So this says you know is there a move for the first player so is there a way for him to choose 0 or1 so that no matter what the second player chooses。

 there's a way for the first player to choose a move so that no matter what the second player does。

 the first player can do something so on so that and this will be the winning condition of the game like you given the sequence of moves that the two players have played this formula evaluates who has won the game so you're asking the question is there a winning strategy for player one even if player two players optimally。

Yep。It actually。So okay， that's a great question。 So rearranging quantifiers is actually changes the meaning of the question right so for example。

😊，You know。Let's see what a good example of。You you can write down some question like does it exist in X Now maybe let's just think of x and y as natural numbers。

 so does it exist in X， such that for all Y。嗯。X is strictly greater than y。嗯。Okay。

 just so think of x and y just being natural numbers。 So this question is asking。

 is there a natural number x so that for all y， X is greater than y So this question is asking basically。

 is there a natural number that's bigger than all other natural numbers And the answer to this question is no obviously there's no such natural number。

 but if you switch the order of quantnifiers， you ask。

For all Y does it exist in that x is greater than the y？

This is saying for every natural number why is there a natural number that's bigger than it。

 and that's true。 There is always a natural number that's bigger than any given natural number， know。

 you just add one or something。So。So the answer to this question is yes。

So the order of quantifiers is important。And kind of the reason the reason why the order of quantifiers is important is you know the if you think of quantifiers as choices。

 or let's say you' thinking you have the。Exists quant as a choice it's saying， you know。

 should I pick0 or should I pick one， This choice is allowed to depend on the choices outside。

 so here what happened is the choice of x depended on y So we chose an x。You know。

 relative to the y that was already chosen by the outside quantifier。

 and then that's why this worked because we were able to choose x equal to y plus1 or something。

 but it's here that doesn't work because you first need to choose an x and then you to choose a Y so yeah that's a great question。

The order of form advice is really important， and these two things are often。嗯。

We'll often have different answers like the exist for all question versus the for all exist question。

So that's maybe one way of thinking about why this problem is incredibly powerful like this is a complete problem for P space and we saw peace space includes all that stuff written over there and the reason it's so powerful is it has this set of alternating quantifiers and you can have a number of alternating quantifiers that depends on the input size and that's great like in NP you had just one quantifier NP to the NP you had two quantifiers and in general the case level of the problem in hiarchy of K quantifiers but P space is great because the number of quantifiers is not just on constant K but the number of quantifiers can also just depend on the input size so you're able to express much more powerful stuff in this class piece space。

😊，So this problem is called TQBF， as I mentioned，s like a canonical piece space complete problem。

 And if you're trying to show something peace space complete， this would be。

Good problem to start with。All right， okay， yeah any questions about this problem， QBFs？3。Oh right。

 so TQBF stands for total quantified Boolean formula。Which is。I'm not sure。

So I guess total quantified。So boolean formula because that's a Boolean formula。

 and I guess total quantified refers to the fact that all these variables that you have they're quantified。

 there's quantifiers， there's no free variables， there's no variable that's just like hanging around there that's not been captured by any of these quantifiers。

Sorry。Oh， that's a good question， what was it？True， total， true， total。 Yeah， it doesn't matter。

 Let's go over true。 That sounds better， actually。So we want to know whether this formula's true。

Some people just call this quantified building formula。

 probably to avoid this ambiguity of not remembering what the T stands for， sorry。It is true。

 so he knows the answer。Right， great， so is true a quantifyified brilliant formula。Okay。

 so let's not prove that this is piece space hard。 That's kind of time consuming。

All these hardness reductions kind of look the same once you've seen the C 11 Theorem and NP hardness reduction。

So maybe it just worth。Talking about why this problem is in peace space。

And then we can end our segment on。Peace space。Okay， does anybody you want to tell me。

 do you have any ideas for why this problem might be in peace space？Just a guess。Just how would you？

Yeah，How would you try to share those problems with peace space。

 So you want to come up with an algorithm that uses only polynomial space that uses space。Polo n。

And at the end of the day， it is able to decide whether this is true or not。就是这思。That's right？Right。

 so there's I mean， how would you do that， The problem is that say you lexographically go through。

 you need to check this kind of complex dependence right that exists the choice for x1 so that no matter what choice you choose for x2 that exists the choice for x3。

 So it's not just that you want to。know take all of these end bit strings and just check if all of them satisfy that expression over there。

 but this says something。You know， kind of complicated。 Like， for example， it could be that。呃。

It turns out that。There is a way to satisfy this and the winning strategy for the first player is always to pick0。

 and whatever that mean is if x1 is set to 0， no matter what x2 is set to。

If x3 is set to0 no matter what x4 is set to this works。

 but the strategy for the second move of the first player could depend on what the second player played on his first move。

 so maybe here you play a zero and then this guy if he plays a zero or one depending on that。

 he might want to play a different move in the third round so。

It's not exactly clear how you would just go through all possible assignments。And check。

But but that's definitely on the right track that because there's only n variables and you have in space。

 you' well at least you can write down any possible assignment and you could go through all of them for example。

 so that's already something we have。So we just need。

Something to attack this idea that there's these alternating quantifiers that we want to solve this problem。

 any other ideas or？Just a guess。So one way to think about this。Which is kind of nice。

 is that let's just reduce the problem to a slightly simpler problem。

 which is say you had one fewer quantifier。Say you were just solving this problem， you know？

For a fixed value of x1。 So let's say I fixed x1 to be something。 Let's say X1 is 0。

Then you plug in x1 equals0 into this formula， then you get a simpler formula。

That only depends on x2 to the XN。 And then you ask the question， you， is this formula satisfiable。

 is it true that for all X2 that exists in x3 and so on。And。This is some problem on an input of。

You know with n minus1 variables。And let's assume we have an algorithm that solves this problem in using space and minus1。

So what you can do is。To solve this problem， you can first put x1 equals 0 and then call this algorithm that we assume to exist for。

Solving an instance of size n -1 and say， you know， ask it， hey， is there a solution or， If there is。

 then then you're fine， then you found an X1 that satisfies this formula。 If it says no。

 then put x1 equals 1。And again， call this algorithm。

 but the important thing is the space that the first algorithm used。You can use that space again。

 it's not like the space has been used up and cannot be written on again。

 so you just clear out all those tape cells on your Tring machine tape and just reuse the same space。

 so to solve the problem in inb，You just need to solve the problem at n minus1 bit twice。

 but you don't have to use two times of space you can reuse the space， that's just S of n。

 the space used for the n bit version of the problem is like the space of n space use for the n minus1 bit problem and some constant amount of extra space。

Maybe。You know， you need to store the value of x1， for example。When you do this recursion。

And if you saw this。Recor installation， you can see that。Actually。

 you can solve the problem in linear space。So， that's。

That's one way of thinking about how you would solve this problem。

There's probably a more graphical way of thinking about how you can solve this problem。

 which is to draw this as a tree。Right。Rather， you write this as a formula。

You're trying to compute essentially this。We're trying to compute the output of this function。

 So this is an our gate。Which corresponds to x1 equals0 and x1 equals 1。

This is an end gate that corresponds to the choice for x2。And so on and。You keep doing this。

 and at the end of the day you have these leaves。Which are phi of x1 to xn。ButWhen you've reached。

 if you've already made all the choices for X to X， so this is just a bit。

And then what you're trying to do is just compute the the output of this formula。 So this is some。

You know， depth and formula and you want to know and all the leaves are bits and you want to know what what is the output of this this thing。

 So if you just were to evaluate this upwards， what would the answer be。

Now the problem is that here there's two to the n nodes， they's two to the n leaves for this graph。

 because you've gone down a depth T and to a depth n and each time the number of leaves in this level increased。

And that's bad because2 to DNA is too large for piece space to。To store。

But you don't actually have to like， write down all of this and enumerate through all these possibilities。

 You can do this with the。With a graph search algorithm。And。

Any guesses for what kind of graph searching algorithm you would use so as to traverse this graph without actually。

Sttoring exponentially large number of vertices in Europe。

In your database or whatever you're doing all of this stuff。Right， right。

 that' for a search because yeah。That first I just said。

Is the algorithm that does this kind of stuff， it goes and traverses the graph。

 and all you need to store for depth for search， say here you really need to just store the names of all the ancestors or the parents of the vertex you're at。

Your stack in depth for rate would only be of the size of the height the tree， which is n。

So that's good， you'd be able to do that first search without。嗯。

Without having to store all the leaves in a given level of the tree， if you've done breakfast search。

 breakfast search you'd have to store all the levels in a tree now all the vertices at a given level of the tree。

 this could be exponential and that's bad。So yeah， so there's a way to think about this in terms of just doing a DFS on some appropriately given implicit formula of this kind。

But maybe it's probably just simpler to think of it this way。

 We have a solution for the smaller problem。Just solve the smaller problem twice。

 so you don't have to use two times the space。 That's the good thing。 if you had a two here。

 it would go， the solution to this record solution would be exponential in then。

The great thing about space is， of course， that you can use it， and that lets you all this faster。

Okay。So that's a sketch of why QBF is in P space。 Of course this is explained in great detail in the book。

 and they've also shown how this problem is peace space complete。Yeah， interested in more details。

 that would be a great place to look at。All right， so。Okay， any questions about this part？で。

Basically brings us to the end of our segment on peace space。So before we move on， nope， okay。Oh。

 here's a。Here's a fun fact to motivate the next thing that we're talking about。So okay。

 maybe here's a good question， why do we care about peace space hardness。

 like isn't NP hardness hard enough？You might say well。

 I've proved my problem to be NPR why does it matter that now you're showing that it's piece based hard。

 if all you care about is showing that if all you care about is coming up with poly time algorithms solve problems。

 maybe it's not so clear why you would care about peace based hardness hard is hard if you're not going to be able to come up with the poly time algorithm that's just that。

But complexity theoretically， one reason to think about peace space hardness is then you can give evidence that the problem is not in NP。

 so we think of PSp as in closing all of these classes and peace space hard is somewhere up there。

And if a problem is P space hard， then you're pretty sure it's starting NP。Of course。

 we can't prove this。 we do not approve that NP is not equal to P space， but。

You know swimmingming MP is not equal to peace space。Peace based hard problems are not N。

 if you want to give some kind of evidence for a problem not being an NP or not being an NP to the NP or not being in the Pmian hiarchy。

 one way to do that would be to just show that's peace space hard and then。

Assuming things that we believe about complexity classes， it would not be in one of these classes。

There's a lot of things in complexity that we believe that we have absolutely no idea how to show。

 That's generally going to be a recurring theme for the rest of the course。Right。

 so the Pmy hierarchy is just the union of this set of classes。You have NP。NP to the NP。

NP to the NP and so on。So in other words， everything in this class is some fixed number of levels of NP to the NP to the NP and so on。

 so if you wanted to write it down。Like an alternating sequence of quantifiers。

 That'd be a fixed number of quantifiers， you know。

So that the 200th level of the polym hiarchy would have 200 quantifiers。

 The number of alternating quantifiers is not allowed to depend on the input size。

So you know here there's one， here there's two and in the 20th level， there's 200 quantifiers。

 but in quantified boolean formula， you're allowed to have n。

Alordinating quantifiers where n is now the number of variables。So。

The number of alternating quantifiers is allowed to depend on the input size。

 and this makes it much more powerful than pH， but any level of the polynomial hiarchy would just have a fixed number of alternating quantifiers。

Any other questions about this？Okay， so maybe let's。Okay。

 let me give you a fun fact about these things， right。

 So we're just talking about peace space hardness。NPpR this。4。So think of this problem。

So does it exist an assignment to X1 through XN， these are bits so that this formula is true。

So how quickly can you solve this problem on a standard tuuring machine。

 like say you're writing an algorithm to solve this problem because you really car about the answer and you just want to code it up in your favorite programming language。

 what would be the time complexity of this algorithm， roughly how much time to？

it's exponential right， and even more precisely， it's roughly like it's like two to the end and maybe there's some polynomia factor for deciding。

For the formula itself evaluating the formula， but what do you do is just try all possible assignments so there's two to the impossible possible assignments and then for every assignment you just evaluate this formula。

 maybe the formula takes all your time。I mean， what I'm getting is essentially you need to spend the end time and we don't know any better algorithms。

 like this is the best algorithm known for this problem。呃。And。

Proving anything better would actually lead to yeah would lead to breakthroughs in other areas。

 so that' would be great if someone could come up with a better algorithm two to the end。But now。

Consider the following piece based complete problem。

Another question is what is the best algorithm for this problem？You know， again， you're just。

You just want to minimize the time complexity of the algorithm。You're trying to code this up in some。

What your favorite programming language？You forgetget about peace space and all of these things。

 you just one the fastest algorithm for this problem。So it turns out that， again。

 there is an exponential time algorithm， which goes like that。 there's a 2D theN algorithm。

 but it turns out that if you don't mind。An algorithm that's randomized in the sense of so I'm going to talk more about randomized algorithm shortly。

If you don't mind an randomize algorithm， you can actually do better and you can do you can achieve time complexity that goes like 2 to 0。

753。Something of that story。So this is significantly faster than this character。

 the constant of the exponent is smaller， and now you're thinking， what is 0。753？

How did he get this number？And it turns out this is like it's like some lock to the base to of one plus square root of 33 over four or something like that。

So this is an actual exponent that appears in an algorithm。That's pretty crazy， I don't know。

You do that， right？Yeah， this is the best algorithm we know for this problem right now。

The only caveat is it's a randomized algorithm， it's a probabilistic algorithm。 it doesn't always。

It's not an algorithm in the sense that we've been talking about so far。So this is a good。Way to。

Motivate why we should think about randomized algorithms， I guess。 So yeah， without further ado。

 let's start talking about randomized algorithms。 Why should we。

Why should we use randomized algorithms？好。Okay， any questions about Peacepa before I move on to an algorithms。

嗯。Ill I'll answer that question when we。When we at the end of the randomized algorithms part， Chris。

 I'm going to introduce a whole bunch of randomized algorithms complexity classes and then I'll tell you where this fits。

That's right。The first one is NPpably。Because it's just。Well， if you reduced it。

 you need n exists quantifiers， right， whereas this version of the problem as I've written it has only n over two exist quantifiers。

 so the way you would reduce it is you would come up with an instance of this problem with this n being  two times the n over there。

 so you would get an algorithm that goes like 2 to the 0。7 feet3 times 2 n。

But that two is going to multiply with this guy and give you an xer bigger than one。

 And that it's probably better for you to just go and use that algorithm little more。So。Yes。

 it's actually really surprising because you think of this problem as being harder because it's space space complete。

 and know in some formal sense， it is harder， but if you really just care about solving the problem。

This one。You know， there's a faster algorithm the for。But it's randomized。Okay， yeah。

 any other questions about this？That would good。Okay， so let's talk about randomized algorithms。

So why should we use randomized algorithms？ What's up with the randomization， Why is randomized。

Interesting。I mean， the kinds of functions， I mean。

 the kinds of problems that we were trying to compute， you know， things like。

 is there a satisfying assignment of this formula， are just these are deterministic questions。

 right like either there is a satisfying assignment or there isn't a satisfying assignment。

 why would you。Why would you need a randomized algorithm to solve this like this would be something that。

You could ask like who would randomness help， certainly the question is not random。But。Yes。

 sometimes it does， and in fact this。And it might help algorithmically， especially。

 And this is an idea that goes back to， I don't know。1800 something。

 but someone was trying to estimate the idea of pie。Not the area of pi， sorry， the value of pi。

And the idea for doing so， you know there's many mathematical expressions for pi。

 but here's a simple way to estimate the size of the value of pi， which is。

Take a square whose side length is one and inscribe the biggest circle that you can in it。

And what you'll see is this area。So the ratio of the area of the circle to the area of the square is pi。

So one thing you can do is。Just randomly sample points from the square。 So what does that mean。

 just randomly pick points from the square。And count the total number of points that are inside the circle and the total number of points that are outside the circle。

 so if you just compute the ratio of total number of points inside the circle divided by total number of points you've picked。

 this will approximately be pi， at least if you're picking points uniformly at random。

That seems reasonable enough。And this was something that people actually tried。

 I think it's probably not the best way to compute by， but。Disord worker。But anyway。

 this doesn't seem as useful， but what's more useful is say you're trying to estimate。

The area of some complicated shape。This is some shape。And。

This shape maybe you don't really understand it very well， like the boundary is kind of confusing。

 it's a very complicated boundary， say but what you do know is you know how to test whether a given point is in the area or not。

 so one thing you can do is just sample points uniformly at random from the square。

And just compute how many points fall into this， and then the ratio of number of points that fell into this gives you an approximation for the area of this complicated object。

 and you can do the same idea in more dimensions， like you to compute the volume of something。

 you're trying to compute the volume of something RN。

You don't have a good understanding of what the object is just pick points randomably。

Like another thing you could do is say you're trying to compute the integral of some function from here to here。

So this is the area trying to compute， but integrals can often be nasty， right？

You can get crazy functions that you don't know how to integrate。

 there's no simple integrals for this， Maybe you're trying to do this。 So what do you do。

 just find some box like that。Pig points uniformly at random。

 count how many points are below the curve。And divide that by the total number points you picked at random。

 and this is going to give you a reasonable approximation。

So this is something that people actually do， like is these techniques are called Monte Carlo methods。

And I think they were invented during the。The Second World War because they needed to do a whole bunch of calculations for the nuclear bomb and cross sections of things。

 and I think it was invented by a bunch of physicists who wanted to compute some integrals that they were not able to on a computer。

 but this method was able to give them really good estimates for what the integral should be really fast。

So， yeah， that's the reason why you might care over randomized algorithms。

And this is like something that was actually done。 So that's a practical motivation for caring where to random algorithms。

Another reason to care about randomness in general is just， you think of cryptography。

 you' trying to。You're trying to hide something from an eavesdropper。

 you have some message you want to encrypt it， send it to your friend and you don't want anybody else to read the message to know what's in the message and usually there's going to be some kind of password or some secret that you're going share with your friend that only the two of you know and it's really important that this password is random like the password is always a fixed thing like your password is always like password then like this is not a secure system right the Eavesdroppper can just try out this password password。

M conceptualulates the reason。Crypttography needs randomness for the same reason that you need randomness in the game rock paper scissors。

 actually if you're playing rock paper scissors for someone and you don't want to lose。

 it's a great idea to choose your play randomly don't always just keep playing rock because then of course the other guys going win but I mean it's essential in this game that you play something random like that's the only way you're gonna to win if you're predictable and you always play。

The rock， you know you're going to lose， and that's kind of the same reason the cryptography needs random misses you want the adversary or the heavesropper who's trying to read your messages to not know what your password is or what your secret is or so on。

So we're going to talk a lot more about cryptography in an upcoming lecture。Yeah。

 that should be a lot of fun。But that's just a high level expansion of why cryptography would need randomness。

And let me give you another。More algorithmic example。 So this is a problem that。

Not known to have any。deterterministic。Plynomial time algorithm。

 just a polyno time algorithm in sense that we've been discussing so far。 And the problem is。

 you know， you're given。You're giving some number N。And。New to output。Any inbit crime？Okay。

 and let's say that the input is encoded like this， you're given 0 to the n。

As input you have polyan time。So you have polynomial time in the number of bits of the prime number。

 So you know， so I give you this much time and I say， hey， produce。

I know 1000 digit prime number for me and you're allowed。

Time polynomial in the length of the representation of the prime。Yeah。

 does anybody any ideas of how you would do this like you need to argue just any prime doesn't can be just yeah anything doesn't have to be random or anything。

 just any old endB prime。The important thing is it's an nbit number。You know。

 the first bit is a zero， so dont output。The prime two and say that it's an n bit prime because you can add 0。

0，0，0，0，0，1，0。 But you know， something that's a legitimate n bit prime number。

Any ideas for how you would do this？Cook up an hand prime。Yeah， okay， anyway。

 if you have a good idea for how to do this in deterministic polynomial time。

Then that's great because it's not knowing how to do that。

 and this would be an excellent paper and so on， probably getting into a great journal。

But there is a randomized rate to do this。And why is that？This follows from the prime number theorem。

Which I'm certainly not going to prove。But what the prime number theorem says essentially is that。嗯。

A random end bit number has probability one over end of being prime。

Roughly when we end up being prime。So。For the probability of that。And with。Number is prime。

It's roughly some con of everybody。Okay， so now that you know the prime number theorem。

 can someone give me an idea for how you would。Generate primes。Like how would you find it？

An inB prime for some man。Yep。Right， right， that's great。 Yeah。

 so you know you can test if a number is prime or not in polynomial time。

 this has been known for a while。So that's exactly what you do， just pick an nbit number at random。

Check if it's prime if it's prime you're done， if it's not prime。

 there's only a1 over n or C over n probability that it's not prime I mean that it is prime so you have to do this a whole bunch of times。

 but how many times do you need to do this like if the probability of you succeeding is like1 over n then you roughly need to do this like n times to have some decent probability of finding a prime。

So， so so this is a polynomial time algorithm because you know， you're going to only run for。

Whatever time it takes you to find one prime and check if it's prime times something like n。

 or maybe you go even longer， maybe you go for n squared time。

 and then almost certainly you found a prime number。So that's an random argument for writing a prime。

Yeah， this is an example of a problem for we don't know a deterministic algorithm。

 but we have a problem in time randomized algorithm。Okay， so that's a。

That's the reason why we might care about randomness。But okay， let' start。

 let's get into the meat of the matter， talk more about randomized algorithms。

 any questions so far about just this informal motivation for why we care about randomized algorithms。

Very good， okay。So。So I want to talk about。Yes， so I want to talk about basic probability theory。

 or I can talk more about randomized algorithms。And。So okay。

 let me first talk about randomized algorithms and then I'll let Scott talk about。

Basics of probability theory next time。talkingalking about randomized algorithms is more fun。So。Okay。

 let's do that。 let's start with。So。Okay， so how do we。Okay， so how do we do this。

 how do we come up with a model for a machine that has randomness incorporated into it？

So you know a curing machine model so far has no randomness it's just a machine that works with some specified rules。

 but what you can think of is maybe it has access to this randomness machine and the kind of thing we like to think about in computer science is just a fair coin。

 you just have a coin， you flip it and with this probability 50% you get heads with probability 50% you get tails。

Right， so that's like。It's supposed to be the simplest random thing you can ever think of。

 it's just a fair coin。If you have something more complicated that also generates randomness。

 like maybe you have some。Some method for generating random numbers between one and 100 or something from that certainly you can construct something that just know generates a single random bit certainly generating a single random bit is like possibly the easiest random thing you can think of so that's what we like to think of as our source of randomness。

And so one way you can think about a tuuring machine that has randomness is what's called a probabilistic Turing machine。

So。A probabilistic drinking machine。And a probability steering machine is allowed to flip coins during its execution。

 And what this means is that it's allowed to say， you know， with。You know for that。

In a training machine， you have these transitions， right？There's something here， something here。

 and what you're allowed to say is you know if I read a zero。Then flip a coin， if it comes up heads。

 then go to this state over here and if it comes up tails， go to this state over here and of course。

 right， whatever you're supposed to write on the tape and move left or right as a tuuring machine usually does。

But you're allowed to make these decisions on the basis of some coin flip。

 So this is just something that the straight transition allows just allows you to have。To say this。

 with 50% probability do this， with 50% probability do that。And then。

And then what you do at the end of the computation。

 you have probabilities of being in different states of your Turing machine。

And you say that maybe you say that the tooling machine is accepted's if there's a higher probability of being in the accept states or not。

 or something of the start， but I mean we'll talk more about what these acceptance conditions are more formally。

I mean， I just wanted to explain the idea of what it would mean for a tuuring machine to have access to randomness intrinsically somehow。

So this is a bit like the non deterterministic tuuring machine model that we studied where the tuuring machine is allowed to。

Non deterministically going to many different states。

 it's allowed to choose the best state or something of the sort。

And while this is a nice model theoretically for。For NP， we had this other perspective。

 which is that someone just gives you a witness。Or in other words。

 the trading machine just has a separate witness tape and then so you think of there being two kinds of inputs。

The usual input X to your problem， and then there's this witness input Y。So this is for NP。

 you guys have witness input but Y and then you said that there's some killinging machine M of Xy。

 which had certain properties there。You know， if x was a yes instance。

 then there should exist a y that satisfies that makes this accept。 And if x is a no instance。

 then you know， there should not exist a Y that has this property。

 So what we did here is we separated out the。This nondeterminism or this witness from the model of the machine because this was just a standard deterministic machine。

 so we didn't have to talk about nondeterminism while talking about the machine。

 we only needed to we just added it as a separate input。

So that's something you can do with probabilistic toing missions as well， what you can do is。

You can just， instead of saying that the tuing machine can make these coin flips。

 you can say you're just given a separate。tape。It's color to see。And。

This separate tape just has random bits on it， so the tuing machine has an input tape and it has a randomness tape。

 and this randomness tape you just get to assume that there are random bits written on it。

 You don't have to worry about how that happened。And。And then。Basically。

 whenever you want to use randomness， you just consult the tape。

Pick a bit from there and that's random。And so that's。Yeah， so that's how you would use this machine。

 so it's very similar to how。In this discussion about NP。

 we went from this witness perspective to the nondemin tuuring machine perspective。So。

 I'm going to call this。 Okay， so this is a probabilistic tuing machine。

 the one that's allowed to make randomized。Transitions。

 and this is just a tuing machine with the random tape。

And what I'm claiming is that they're equivalent， like whatever one can do。

 the other can do because they can simulate each other。Okay， does anyone have any？

Ias for why they would be similar or any questions about this， if this didn't make sense。

 like the probabilistic tuing machine model and the tuing machine with a random tape model。

So any questions about what they are or any suggestions for how you would ensure that one of them can simulate the other？

Right， so you just have a tape and there's bits written on it and the idea is that these bits are random and you don't have to worry about where they came from。

 but it's just every bit that you read from this tape has been chosen。

 is a0 or1 with equal probability。So it's just like， yeah。

 you've offloaded this problem of creating randomness to somebody else。

 somebody else just came and wrote down an random string of bridge on your tape。

 doesn't matter where they came from。Okay， yeah， any ideas for why these would be？

Why one can to the other。Right， right， right。 So。Right， so you're trying to simulate the。

Right the tape model with the probabilistic turing machine so that's right yeah and maybe just the simplest way of thinking about is this probabilistic turing machine know it's allowed to make coin flips and write things on its tape so maybe on a separate tape which has nothing written on it right now the first thing it does is it just tosses like a whole bunch of coins which means it just makes a whole bunch of random transitions and just writes down what transition it took so maybe it does this n times and now this tape which is previously empty now just has n random bits written on it and after it does is it just simulates the deterministic machine that this guy is gonna do。

So a probabilistic clearing machine， because it's able to flip coins， can generate random bits。

You can just write them down on a separate tape， and then you just follow the deterministic machine that this machine the。

The tuuring machine with randomness was going to do。

 So the tuuring machine with randomness starts off with the assumption that there's random bits written on this random tape。

 And what you've done is you've just written a bunch of random bits on the random tape。

 And now you just do whatever that guy was going to do。So that shows that this steering machine。

 the deterministic one， which gets two tapes。嗯。Can be simulated by a probabilistic toing machine。

Okay， so that's great。Okay， any suggestions for all you would do the other way down？

How would you simulate the probabilistic tuuring machine with this steering machine。

 which doesn't have any randomness built into it， but it has access to these random bits written on a tape？

Yep。Yep， yep， that's exactly right so the answer was。

Just use the random bits from the tape to decide the transition。

 So if you were going to take this arc with probability half and this arc with probability half。

 you just go here and see whether it's 0 or1， if it's a  zero， you go here， if it's a one。

 you go here。So the random take can simulate。Inherent randomness and。

Inherent randomness can simulate the possibility of having a random tape。

So what we like doing is just thinking of having the randomness separate on a tape because then we can talk about deterministic tuuring machines。

 we don't have to talk about these。These probabilistic tuing machines。

 whose state transitions might be much more complicated。 yeah。

 it's just easier to think of determinacy tu machines that have two inputs。

 a normal input and a string of random bits。Okay， so that's what we're going to talk about from Nan。

Any questions about this before。Right。No， okay。So。Okay， so let's。Let's talk about。

Let's try to come up with the model for what an randomized algorithm would be So let's say you have。

I think you have some language out。You're trying to decide this language out。

And you have some tuuring machine M。Let's say M halt in polynomial time。 so we want this。

 So we're trying to come up with some model of a polynomial time randomized algorithm so we wanted to halt in polynomial time。

 so that's certainly good。That's a requirement from our algorithm。And what else do we want。

 So we want that intuitively， what we want is that for most choices of the。The random string。

 like it's probable that the algorithm outputs you know the correct answer。

 So so let me write down know one version of what this would be， for example， So let's say x is。嗯。

X is an end string and this says is。M B string and Ms and polynomial and N。So let's say for all X。

In the language。What you have is the。That a majority of these lead this machine to accept。

 and what I mean is。The set of all these such that。And see accepts。The size of this set。

Divided by the total number of。The total number of possible z， which is 2 to the M。

This is greater than a half， let's say。So。So some more than half of all possible random strings caused the machine to accept。

When x is in the language。And let's say when x is not in the language。系啊。Let's say， M X Z。Yeah。

Let's say this always rejects。So for all Z。Okay， so what is this saying？

This is saying you run the steering machine， which has access to randomness。

And no matter what random string it was provided， if the input is not in the language。

 it's always going to say no， no， the input is not in the language。

 but if the input is in the language， then there's a pretty good chance there's a more than 50% chance that it's going to succeed。

 that it's going to say yes， the inputs in the language。

So this would be one way of defining a randomized complexity class for polyial time。

 and this class is called RPV。Which stands for randomized polynomial time。Obviously。Okay，Okay。

 any questions about this definition， like what does it mean？

Is the intuition kind of clear like what it's trying to say is that。嗯。

If the string is not in the language， it's never going to accept。 So that's great。

 And if the string is in the language， then there's a pretty good chance it's going to accept。That's。

 that's essentially the。The intuition for Work RP is。Any。Any questions about that， Er？Infusions or。

Any proposals for a different way of defining a randomized polyial time， which is not this one？

You can make it the other way around。 That's right。 So that's perfect。

 You could say that when it accepts。Effect is in the language so basically it always accepts。

 and if it's not in the language， there's a greater than the 50% chance of rejecting。

 and that class would be called coreRP。已见。You， you can verify the definition of。

You know the coer of any complexity class which is just， you know， a language is in coreP。

 if it's complement as an RP， if you use the definition you'll see that it's exactly this。

 but you swap the accepting and rejectjecting。I think so in that case here it would always accept and here it would reject with at least 50% probability。

 Okay that's a good idea， and that leads to a different complexity class。Okay。How about yeah。

 how is this question how do these classes fit relative to the classes we've already talked about？

You know， we've talked about P。And we've talked about RP。Oh， we've just talked about RP。

 now where does this fit with respect to NP， for example？And what I'm claiming is that。In fact。

 it's like this。RRP is contained an NP。So。Okay， does anyone you want to see why like why would RP be contained an NP so if you have this kind of an algorithm for a problem。

 so if you have a deterministic clearing machine that takes two inputs in the yes case。

 more than half the Z' causes it to accept and in the no case。

 no Z causes it to accept why would this class be contained in NP？Like what would the witness be？

Just。Guess something throw out here。TheThe strings or just AZ string is sufficient。

If x is in the language， the NP per like the。There needs to be a witness that convinces you that iss in the language right so I'll just give you one Z that causes this guy to accept And once you've seen this1z and you've verify that M of x come a Z except。

 you know it cannot be here because if x was not in the language。

 theres no z that causes it to accept。 So being given even one z that causes it except convinces you for sure that X is in the language。

 So this is a witness this is a certificate that completely convinces you that X is in the language being given 1 z。

😊，So this perspective of thinking about it shows that。RP is kind of like NP。

 but what NP says is that in the yes case， there should exist at least 1 z， and in no case。

 there should be no such Z， and what RP says is not only should that exist 1 z。

 but like pretty much all disease， I mean， half disease should work。

Because we're saying the fraction of these that work is about a half。 So Rp is some kind of。You know。

 relaxation of NP and NP just had this kind of existential quality that there should exist one string that does the job。

 but like you have no way of finding there one string， you know。

 unless someone comes and gives it to you， that string could be any string。

 but what our piece saying is that you know。At least half the strings should work。

It's a strengthening of the definition of NP， so it gives you a smaller class like this。

 so P is contained an RP and it's contained in an NP， which is itself contained in NP。Or any。

Does that make sense？Why our piece contained an NP？Any mean。Questions about that。No。Okay。

 and so so similarly， you can build this kind of。You think here this CorRP。You know whatever there。

CoNP。And so on。The same reason why RP was contained in NP also gives。

Core RP is contained in Co and P， you can go through the same proof。

 or you can just look at this expression which says RP is contained an NP and just put a co on both sides that's fine too。

 that's a legitimate way to prove stuff。😊，All right。Okay， so this is RP。Okay。

 but any other proposals for what a randomized algorithm would look like。

 like maybe a different definition or not？Not like having a half here。Go aject here or maybe。呃。

Maybe a number different than a half here。 I don't know。

 So we haven't talked about So why did I choose a half here， Okay， does anyone have a。

Intuitive explanation for whyA。Why half from？What if someone wanted a different definition where they say not half of all possible strings should work？

Maybe， you know。Maybe0。99。Fraction of all the strings you wear。It shouldn't just be that。

Half the random strings work， but pretty much all of them work。Or pretty much， however。

 you start or like whatever randomness you get。要。You almost certainly get the right answer。

 and this could be something else， maybe this could be 0。999。

Maybe this might be a better definition of RP。Like an even better randomized algorithm。

 like it's almost surely giving you that right answer。

Does this sound like a reasonable definition of RPRP as well？Sure。

 this could be something we can define。So anyway， so it turns out that these two definitions are equivalent。

If you choose a much stronger hardness like this， you say that。Almost surely like you 0。999。Or99。

99% of the times。The randomness works， and。It's very and this case is still the same。

 like there's no choice of Z that makes it except if it's not in the input。

 This definition is as the same as the other definition。Okay， does anyone have any。

Suggestion for explaining why this would be the case。

 Why is it good enough to just have0 versus a half？To give you 0 versus 0。99。

What you just run the algorithm？😔，Right。That's exactly right right So what are we trying to do right when we have this algorithm and we know that if you just choose Z at random with 50% probability you're going to see a good one if it's a yes input and with no input you're always going to see these that that J。

So instead of picking one Z at random， what if you pick like two Z's at random。

 or what if you pick like 100 zs at random， what happens then？So。

If any of these Z's cause it to accept， you picked 100 Z's and you check this for all of them。

 so try M of x comma Z for all of them。If any of these theses accept， then you know。

 for sure you're in this case， right， because if x was not in the language。

 there's no z that causes it to accept。 So you would always just see the rejection but。If。

Are of these00 disease that you've chosen if any of them accepts then？

Then you're good to go so what your algorithm should be。You know， sample hundreds seat randomly。

 you know， you have randomness。 So just pick these。Random strings and just check if any of them exc。

 so you take the ore of all of these random strings。

You take the or function and apply it in all of these， so maybe more formally， what you do is pick。

Big C1， C2。ZK at random。And then compute。Mm of xcom1。MFX come with C2 and so on。

And if any of these guys are one， then you want to say that the answer is。Is yes。

 right So the function that you're applying on the outputs of all of these things is the R function if all of these are0。

 you want to say0， but if any one of them is one， you want to say one。So this is a new algorithm。

This new algorithm uses more randomness than the previous algorithm。

 but it uses k times more randomness。But if we choose k to be a constant or k to be a polynomial。

This is still a poly algorithm。And now we want to analyze what happens to the success probability。

 right？And so what happens is。So again， in this case， if it was a no input。

That is there's no Z that causes it to accept if you choose K Z's。

 all of them will still cause it to not accept， so this case is going to stay exactly the same there's not going to be no matter how many what value of k you choose no matter how many Z you pick。

 it's always going to reject so that part' is clear。

Here you started off with an algorithm that I have here， so this was our original definitional RP。

You red。Ha here， that means half of all possible disease cause it to accept。Now。

 what I'm saying is if half of all possible disease cause it to accept and you pick K of them。

 there's an even better chance than one of them works。You have。You have key things。嗯。

And with 50% probability。Each of them come up one with 50% probability。So it's like yeah。

 it's like you have K coins， you know each of them come up heads with 50% probably。

 what's the probability that you to K of them and you still don't see any heads that seems extremely unlikely each of these was individually going to come up hedge with probability 50% and now you're going toss。

K of them。And now it seems like， well， it's very unlikely that all of these would come up tails。

 And how would that happen。 So theres， we know there's a strictly less than half probability of。

Finding a bad Z， like a Z that doesn't cause it to accept。

 there's a strictly less than a half problem to hear causing this to happen and so on for all of these guys。

And so so it turns out that the probability for you all of these to be bad is the product of all these propertiesbilities and so itll be。

So the probability of you not finding a good Z is one or2 to the K。

 And this is kind of an informal argument。 But next time we're going to。

Get into a lot of details about probability theory。You know。

 things like the union bound expectation values， linearity of expectation， conditional probabilities。

 things like that。 And we we'll see this more formally。 But this is kind of the I was just trying to。

Give you the inition of why。嗯。Why this constant doesn't really matter。

And that's because you know you can just run it a couple of times and get a better constant like for example。

 K could just be 10 and this is1 over 2 to the 10， which is like you know 0。000。

001 or so like1 or two to 10 is like one over 1000 so that's great you've boosted the success probability if your algorithm from point from half all the way to。

0。999 by just running the algorithm a thousand times。Yes， yes， yes， yeah， so that's right。

 so this argument。Did not actually use the fact that this was a half， right， I mean， this。

 it just goes like the product of all of these probabilities， like instead of a half。

 if it was like it was a quarter if it was three forts。

 like all that was important is that you had the number that was strictly less than one。

 when you raise the power of K it gets even more。Even gets even smaller If you start with the number less than one。

 then you raise it to the bottom of gate， It gets smaller and smaller。 Half is just like， somehow。

A convenient number to work with， but。But it works with any constant because of this property that you can always。

You amplify the success probability。 Yeah， this is often called success probability amplification or error reduction。

It's a very general idea in computer science。That often constant like this are really relevant because you can just run the algorithm 100 times and just see if that works and that'll have better probability working then than running at one time。

 This is kind of the same idea that we did for the prime number thing that you know if you just pick one number at random。

Yeah if you just picked one number at random， there was a pretty small probability if it working。

 but if you just did this enough times， then there's a pretty good chance that it would work。But。

Yeah， we'll see this more formally next time。We'll see even more complicated stuff proof next time about how you bound these kinds of things。

 like if I give you a bunch of random processes and I want to know what's the probability that all of them happens simultaneously or at least one of them happens。

You we can handle these things。系。Yeah， you'll see more formal proofs of that next time。

 and maybe the last couple of minutes， let me say， okay， so this was RP。And that was Corpi。And。

What an interesting class is also the intersection of RP and Q RRP。

 So these are algorithms for which you have this kind these are problems for which you have this kind of algorithm and the opposite kind of algorithm。

 the one that。Never accept an invalid string， but always does the other thing with 50% probability。

 These things actually correspond to something that's pretty natural in real life， which is。

In the notion of false positives and false negatives like sometimes you have。

You have some kind of test， like maybe it's a medical test or some kind of machine that is checking something and these machines have will tell you that it'll never find they often have this property that。

嗯。If there is something to be found， they'll probably find it with a reasonable probability。

 but if there's nothing to be found they won't find it at all so it's like if，You know。

 if half the people in this room have a cell phone。

 if I just randomly pick a person and ask do you have a cell phone？

If it is the case that have the people in the room have a cell phone。

 then maybe I'll find a cell phone with this randomized strategy， but if no one has a cell phone。

 I won't just find a cell phone， there's no cell phone to be found right like it's that kind of thing and often real life situations have this property there。

You know there there's a good chance of finding something if it exists， but if it doesn't exist。

 you're not going to find it because you know it doesn't exist。

 so RPp does model a fairly reasonable intuitive notion of what。At random of my algorithm would be。

 but I mean there are some arguments for why core you would also model this in the kind of opposite situation what you're looking for。

You know， something not existing。And so what would be nice is if you had an algorithm for a problem that was in RP and in CoRP。

And this class also has a name， and it's called。ZppP。

Which stands for zero error probabilistic polynomial time。And I'm going to define it like this。

 I'm going to say that ZP is defined to be RP interect co RRP， but in your。

In your problem set I think in PSet5， you're going to show that ZPP actually has a different definition。

 That's the traditional definition of ZP。 and these ZPP algorithms are traditionally called Las Vegas algorithms with the idea that。

When you go to Las Vegas， the house always wins and you always lose so the algorithm's like。

I don't know who came up with the name， but there's a different definition of ZPP which explains why the name is also Las Vegas。

 and on problem set5， you'll see that with a different definition。

 ZP is a need equal to RP interect coRP。But anyway， yeah， so that could be a different way of。

Another complexity class that you would define based on randomized algorithms。And。Maybe lastly。

 I'll just say the。There's， there's a。And we'll talk more about this next time but we'll talk a lot more about this next time。

 the most general notion of a randomized algorithm is something that's even bigger than RP and coreRP。

It includes all of them， and this guy is called BPPP。And so let me see。Okay。

 what's BPPP So BP is a bit like a mixture of RPp animals original dropping we have a lecture but we have a quiz coming up on Thursday they didn't have a lecture nobody show off to that Friday section anyway。

To the council level。These that are good， the cause accept is greater than say23。

And if x is9 the language now it's no longer always a。Again。

 we have a similar condition like this with that。It's nice and quiet？

Divided by the total number of fall。It's less than， say one。

So what's important is that these cons are separated。What this means is if it's a yes in word。

 if x is in the language， then you know a majority of the random strings say you know agree with you。

 y， x is in the language， if x is not in the language。

 then a majority of the strings will say that x is not in the language which means like a minority of strings will say that this。

Except。So I mean， another way of saying that only one third of all random string cause MFX come to accept is to say that two thirds of the random string z cause MFX come to reject J。

So which means a this notion of what's happening is。

You don't have this property anymore than in one case it was。

