# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p18 -18-Ph CS 219A Lecture 16 Quantum Search.zh_en -BV1KgffBoEUc_p18-

![](img/b56708f980a820e1e6d75b2ca0f24bc7_0.png)

All right， welcome back again to Phs Comp Science 219A。I'm glad you're here。

 especially because we have a fun topic。To discuss today。

 we're going to talk about how a quantum computer can speed up exhaustive search for the solution to a problem。

So we've discussed the last couple of lectures。The black box setting。

Where we can talk about query complexity。And we saw that。We can speed up。Period finding， for example。

 exponentially by allowing quantum queries relative to when we have only classical queries。

And that algorithm is useful in practice because we can use it to。

Compute efficiently the period of any function that。We can compute efficiently。

 if we can compute the function， then we can determine its period。

 even if the period is exponentially long， and that was the key to the factoring algorithm。

 And there are other exponential speed ups known exponential speed ups are really cool because。😊。

In the future， at least， it means that with quantum computers。

 we can expect to be able to solve problems which are hopelessly out of reach。

For the digital classical computers of the future。And I'm going to talk in the next lecture about another important exponential speedup exponential。

 as far as we know， which is using quantum computers to study quantum problems likely to be an important application in the future。

 but today I'm going to talk about a speedup which is not exponential。It's， in fact。

 a quadratic speed up， meaning that the quantum time it takes to solve a problem goes like the square root。

Of the classical time， less spectacular than an exponential speed up for sure， but still interesting。

 And the one I'm going to talk about today， the speed up of exhaustive surge。Is。

In principle of quite broad applicability to many problems。

 it remains to be seen whether that quadratic speedup will be sufficient to make a practical difference at some time in the foreseeable future。

 probably eventually it will。And it's an interesting thing to discuss。

 particularly because the argument is actually very simple and intuitive once you see what it is for understanding how this speed up in exhausthausive search can be achieved quantumly。

So what we might think about are a way to justify what we're going to study。Is。

We can imagine trying to solve an NP hard combinatorial problem like we're trying to find a satisfying instance for a formula or something like that。

And there's no special structure to the problem that's obvious that we can exploit to solve the problem。

Quickly， one way we could always solve that is just by doing an exhaustive search for the solution。

 if the problem in NP we have a verifier every time there's a trial solution we can check to see whether that input is really accepted by the verifier or not。

 and we could run through all the possible solutions but of course that would be an exponential time algorithm because they're an exponential number of candidate solutions that we'd have to try。

哦。In some cases， we really don't know a much better method than exhaustively searching for a solution。

And to kind of formalize that so we can study it。More deeply。

We'll consider it in the black box setting where there's a function which you can think of as sort of a model of a verifier。

 and there's just one possible and string that it will accept。Out of two to the end possible strings。

 this function evaluates to one for one and only one string。Let's call that string W Actually。

 I had a hard time deciding whether I was going to call it W or omega and when I was making the slides I called it W for a while and then I switched over to Oomega。

I didn't fix that， but I'm going to call it W for now and then later on I may decide I prefer to call it omega the W looks a lot like the omega anyway。

 hence the confusion， but what I mean here by F sub w of x。

As a function which rejects every input except for the string W。

 it gives zero for any x not equal to W for W， it gives1。

And that W is the solution to a problem that we'd like to find。We could find it by exhaustive search。

 but if they're altogether capital n， let's say two to the little n， possible strings of length。

 little n。Binary strings of length that n then we'll have to query an exponential number of times or if capital n is the total number of candidate solutions。

 i'd have to try at least half of them to have。A probability of finding this solution successfully greater than one half。

 So I would need。Big omega n queries in order to solve the problem。

 but quantumly it turns out that just the square root of n queries are enough。

 that's the quadratic speed up。The way we achieve this miracle is called grover's algorithm。

 And it's really pretty cool that we can search through n possible solutions in square root of N time。

 with this square root of n queries。 We do it by using quantum superposition by querying in superposition。

 That's how we're able to surpass。😊，What we would be able to achieve classically。嗯。So first of all。

 we do with what we've done in the past， we'll take our box。Which computes the function。

 we can imagine it has an input and output register， there's some unitary that computes the function。

And in order to be unitary， it preserves the input register。So it takes X， Y to x。

Tensored with Y x or F sub w of x， in other words， if F evaluates to1。

 it flips the value y and otherwise it doesn't do anything。Now， as we know， we can put the。

State minus0 minus-1。Divided by square root of two。In that answer register。

 and the effect of that will be that what a query to this box does。

Is it flips the phase of the state in a way that depends on the input X， namely。

 it flips the phase if Fw of x is equal to1 and it doesn't do anything if Fw of x is equal to zero。

So we can forget about the answer register now because it's always going to be in the state minus and just pay attention to the input register so what a query does。

Is of the capital N ortho theormal basis states for our Hilbert space。

 it doesn't do anything to capital n minus one of them。

And for the one mark string that string that we're trying to find。Namely x equals W。

 it changes the phase， it flips it to minus1。So I can write this unitary this way as the identity minus twice the projection onto W。

For anything orthogonal to W， it just acts like the identity。

 but for W it becomes identity minus well one minus2 minus1 actually on the state W so if there's any。

State that I query this box with。It can be written as a superposition of the orthoormal basis state W and some state orthogonal to W。

 nothing happens to the part that's orthogonal to W the part。嗯。Proportal to W changes phase。

So you can think about that geometrically in the following way。

 if we imagine there's some direction in Hilbert space。

 which is picked out by the orthoormal basis state W。

And then there's a hyperplane perpendicular to it， which contains all the vectors。

 which are perpendicular to W and the components。Um。That are perpendicular to W or unaffected。

The component along W changes sign， so it's like a reflection of a vector I tried to draw it here in that hyperplane。

 that's what a query does， so it takes this state when we apply the query unitary use of W。

 it takes it to the other side of the hyperplane reflects it by changing the sign of the coefficient of basis state W。

Okay， so now I'm going to explain what the algorithm is and we'll see how it works。

The first thing we do is we prepare a state which is a uniform superposition of all possible basis states one of those basis states is the one that we're looking for a priorityi we have no idea which one so it makes sense to start out with the state which is a uniform superposition of them all treats them all symmetrically because we have no reason to favor one over another now this is an easy state to make we've made it before we can make it with the quantum Fourier transform acting on the state zero or if we're talking about nqubits we can create it with a tensor product of and headammars as you know。

Now， whatever the marked string is， the corresponding basis state。

 I'll sometimes call that the marked state。Has a inner product。With this state， which I'm calling S。

 which I think I chose S because it stands for symmetric， treating all the basis states the same。

The inner product is just going to be one over square root n。

amp the amplitude in this superposition for all strings is one over square root of n。

 including the mark string。Now， for reasons you'll see。

 I want to think of that as the sign of an angle。And n is a really big number。

The angle is very small， I can use the linear approximation to the sine function。

 so the angle is very close to one over the square root of n it's one over square root of n plus corrections which are higher order in one over n。

And now what our algorithm is going to consist of is many repeated applications of the same unitary。

 which I'm going to call you Grover， the Grover iteration iteration because I'm going to do it many times and it consists of a product of two unitaries。

 one of which is use of W that's the query to the box。And the other， I'm going to call use of S。

 and that's this unitary。It is two times projection onto s minus identity。ok。

So what that does is for the orthonormal， well， for the state S。Some vector in the Hilberts space。

 namely this one。It just leaves the state alone。But for everything orthogonal to S。

 it flips its phase， so if you want to think about it geometrically。

 it reflects a vector in the axis defined by S it doesn't change the component along S and it flips all the other components。

Now， this isn't so important for query complexity， but if I really wanted to use this method to do exhaustive search in practice。

 it would be important that this unitary is one that we can perform efficiently。

 that is indeed the case。嗯。Well。I guess you can think about it this way。There's some。

 I guess I should have written this out but。There's a unitary which acting on the。

The zero state creates s， okay， like it could be that tensor product of headamards or quantum Fourier transform。

So you can think of this。As the result of。Conjugating。

Two projection onto zero minus identity by that unitary that maps the state zero to the state S。

Conjugating meaning you。Times the operator two projection onto to0 minus one times u add joint。ok。

And。So。All I have to convince you of since you already agree that theres an efficient unitary that prepares S acting on zero is that the operator two projection onto zero minus I is something we can do efficiently so what is that guy it's a controlled phase operation so if I think of it acting on n qubits。

And let's say I don't care about the overall minus sign。

 so you can think of it as something that flips the phase of the basis state zero and leaves everything else alone。

So that's like a controlled phase operation， it changes the phase triggered by the state being all zeros。

And that is related just by changing basis， which you could do with a Haemard to a not which is controlled by all n qubits where the not on one of the qubits is triggered by all the other qubits being in the state zero。

 so that's like I guess I called it lambda n minus1 x back when we were talking about toly gates。

 it's a controlled controlled controlled controlled blah blah， blah not。

And while there's some discussion in the notes I don't think I went into the details in class about how you can construct that out of Toughly gates。

 we know how to construct Toughly gates out of whatever our universal gates set is and the number of toly gates you need is linear in n little N so that would be logarithmic and capital N capital n being the dimension of the Hilbert space so I consider that to be efficient。

And。Well， the whole point of that digression was just。

 although it doesn't matter for query complexity， we should know that this use of S is something that's not so hard to do。

With a quantum circuit， it doesn't require that many gates。Okay。

 so what happens when we first do UW and then do US， that's the this Grover unitary。

 the Grover iteration。And so well， we start out with the state S。

 so' come down and look at my picture here。We start out with the state S and then what UW does remember is it reflects in that hyperplane orthogonal to W Now these unitaries are going if we start out with the state S。

As we'll see， they're going to preserve the two dimensional space spanned by S and the mark state W so in order to understand what the unitary does to see where the state goes。

 it's enough just to consider is action on that two dimensional space because the vector is never going to leave that two dimensional space the span of s and W。

So it starts out。Being S。S。Makes a。Has a small overlap with W of there's some vector in the hyperplane orthogonal to W。

With which it makes a。嗯。In which it's almost aligned， okay？嗯。So in other words。

 the angle theta is the angle between S and the vector which is orthogonal to w。

Which is the same thing as saying the overlap of S with W is the sign of theta or the overlap with。

Of S and。When I'm calling W perp， which is orthogonal to W is cosine theta。

 so that's where we start out。And then。We do this reflection。In。W。 Perp。

And that's going to move us down here to a state which still makes an angle theta with the W perp axis。

 but now its on it's on the other quadrant， it flipped over to the other side of W Perp。

That was what the query did。The operation UW。Now we do US ourselves。

 the query you have to go to the box， the US， we don't need the box， we just do it ourselves。

And what that does is it reflects in the vector S。So let's look over here now after we've done UW。

 we have a vector which makes an angle2 theta with s because originally it made an angle theta with W perp。

 but it got reflected in W perp， so now it's，Rotated by theta in the other direction away from W perp。

 the total angle between this state and s is2 theta， then it gets reflected in the x S。

 so that means it winds up over here， rotated by2 theta counterclockwise relative to s。Okay。

 so that's I've indicated here the result of applying the grover iteration first UW and US。

On this initial state。S。Allright。So we rotated it further up towards W。

We increased its overlap with W， we decreased its overlap with W perp。

If we were to measure now in the computational basis。

 we will have increased the probability of finding the result W。

 and we will have decreased the probability of finding any other basis state。

Because W per pi is the overlap。嗯。Well。It's it's essentially the。The component of S。

 which is orthogonal to W， and that's just the uniform superposition of all the strings except for W。

Okay， so we suppressed the W perp part and we enhance the W part by doing this iteration once。

So that's good。We're closer to having W than we were to start with。

 and we want to find that W when we finally measure at the end。So we do it again。

So if we have any factor。Which is rotated counterclockwise now I'm looking at the lower right here。

Which is rotated counterclockwise relative D by an angle phi。 We do the grover iteration。

 So first of all， it gets reflected in the axis W perp。

 It's making the angle theta plus phi with W perp。 It winds up rotated by theta plus phi from W perp in the clockwise direction from W perp here。

And that's what the query does。And now we do U sub S。

 the unitary we applyly ourselves that reflects this vector in the axis S it's now making an angle2 theta plus phi with S。

 so it's going to wind up being rotated。U。Two theta plus phi counterclockwise away from S when we apply US。

 so that's what I indicated here。The initial state psi made an angle phi rotated counterclockwise with respect to s。

 we do another grover iteration and that vector has been rotated counterclockwise further by another angle 2 theta。

So every time the iteration consisting of the query to the black box and the unitary we do ourselves has the effect of rotating us counterclockwise in the plane。

spanned by S and W perp， and that means we're getting more and more overlap with the mark string。ok。

And so what we want to do is keep continuing the gr iteration。

Until we have the maximumimal overlap of the vector with the marked state。

 then we can measure in the computational basis and we'll find the string W with probability close to1。

Okay， so we keep rotating， rotating and rotating until the vector lines up with W。

 and that's one we measure。So how many times shall we do the grover iteration before we measure？Well。

We started out with a state which was rotated counterclockwise by theta relative to W perp and where we want to wind up is with a vector rotated by pi over2 in this plane。

Counterclockwise from W per because that's W， we want W， so when we measure we'll find that string。

So every time we do an iteration， we increase the rotation angle by2 theta。

So we want the total number of iterations that we do， which I've called capital t times 2 plus1。

 which is the initial angle， all that times theta should be as close to pi over two as we can get。

Okay， and theta is small。So each time we're rotating just a little bit and when we stop。

Willll choose theta I will choose t in such a way that the angle between the。

Resulting vector after all those iterations， and w is something of order one over square root of n because we can since we rotate2 theta every time。

I will always be able to make that angle known larger than theta。

If it's because success orientations are only two theta apart， once we get up to nearly vertical。

 one or the other， orientation is going to have an overlap between our vector and W。

 which is no larger than theta。So with a small error， which is negligible if capital N is very large。

We can when we measure find the marked string。With probability very close to one。

The number of iterations that we need is。To satisfy this condition。So T is going to be really big。

 the one doesn't matter much， so I can say the T should be chosen to be about pi over4 divided by theta。

And here it is pi over4 divided by pi over4 theta， theta is very close to1 over square root of n。

 so this is pi over 4 times the square root of n。The number of times that we query the box to find the string。

Is essentially the square root of n， except for this numerical factor。UW whichch is whatever it is。

 0。78， something like that。Okay， so that's really pretty remarkable。Classically。

 we're looking for a needle in a haystack， one out of capital N possible states。

 and we just have to check them one after another until we find the right one。Quantumly。

 though we were able to do an exhaustive search over all of the fossil strings。

 even though there are capital n of them， we could do the exhaustive search in square root of n evaluations of the function。

And the reason it works。Is because probabilities are the squares of amplitudes in quantum mechanics。

If I were doing classical queries。And I did one query after another after I've done little T queries。

The probability that I found the needle in the haystag is increasing linearly with T。Right。

But quantumly， I can get it to increase quadraically。

Because the amplitude is rotating by a constant angle every time。

And the so after done I've rotated t times。The square of the amplitude is going to scale like t square。

Okay， so the probability of finding when I do little T iterations。

 the string that I'm looking for is actually increasing like t squared instead of t。

All because probabilities are squares of amplitudes。

Then so far I've discussed the case in which there's just one special solution， one marked string。

 of course it's possible there's more than one if i'm trying to solve a。A problem in NP。

 there may be more than one solution。 There may be more than one string that the verifier will accept。

And。So。Let's suppose there's more than one。 some number are。

 I don't know why I said greater than two。 I must have meant greater than one greater than or equal to。

So suppose there are two or more solutions。Well， of course。

 if it's a small number of solutions compared to capital N， it's still a needle in a haystack。

 there are a few needles in the haystack。But it's going to be hard to find。嗯。

There altogether are marked strings out of N， and in order to have some constant success probability for finding the mark string classically。

 I'll have to query a number of times that scales like an over R because the probability every time I make a query。

If I make our random query of finding a marked state will be Auburn。Capital N。But quantumly。

 we can speed things up， so the number of queries we need goes like the square root of an over R。

It's essentially the same argument as before， except that now。

The in that coherent superposition that we start with the state as the coherent superposition of。

All of the。Possible candidate solutions。Now。R of them are marked， so there's a marked state。

 which is normalized， which is one over the square root of R。

 the coherent superposition of all of those R marked strings， all the WI。

And so the overlap of this marked state and we'll be happy if we can get to this state because then when we measure。

We'll just be randomly sampling from the solution set。

If we had the marked state and we measured it in the computational basis。We get one of the WIs。

 one of the solutions。Sampled uniformly all those marked strings occurring with equal probability。

 So if I can reach that marked state I'll be very happy when I measure I'll find a solution。

Now the overlap of the marked state with our initial state。

Is larger than before instead of going like one over the square root of n。

 it goes like the square root of R over n。So I can think of that as the sign of an angle。

And theta is assuming R is small compared to capital n theta is essentially the square root of R over n。

 and the rest of the story is just the same， I'm going to do the queries and I'm going to do the use of S which reflects in the axis S。

The thing that's different is that the overlap of the Mar state with us。

Is given by a different angle than before。And so now the again。

 the number of queries that I'll need to reach the marked state with probability very close to one is still going to be pi over4 theta。

 but now theta is a larger angle， square root of R over n instead of one over square root of n。

 so the number of queries that I need goes like the square root of n over our times that same numerical factor of pi over4。

So the point of this story is that even when the case when there are multiple solutions。

 then you have a。You need a smaller number of queries to find。The one of the marked strings。

 one of the solutions。With some specified success probability in the classical case。

 the number you need goes like N over R， the number of queries that you need quantumly again goes like the square root of the number of classical queries。

It's n over R classically， and it's the square root of n over R quantumly。Now。

It sometimes said that Grover's algorithm is like a souffle， if you leave it in the oven too long。

 it starts to sink again。So you have to know when to measure。

 you have to measure at the right time the probability of finding the mark string。

As a function of T goes up because。You know， you're rotating closer and closer to W。

 but if you just keep on rotating， then you start rotating away from W。Okay。And。

So if you were unlucky。And you went too far and you queried for twice the number of queries that would give you the optimal chance of finding the marked state。

 you'd you'd be back to having essentially zero probability of finding it。

So that would be bad and we donate priority no。How many solutions there are？Well。

 let's hope there's at least one， but you know there could be some large number R capital n is huge。

 we'd be happy to find any one of them， but depending on how large R is。

 the state as we make additional queries is going to rotate at different rates and we don't know what that rate is。

So what do we do well in choosing， we know the if there is a solution at all， our is at least one。

And in that case， we know the number of queries that we need is pi over four square root of M。

And the number of queries that we should choose if R is larger is going to be less than that。

 but what I can do is just sample uniformly from the possible numbers of queries ranging one， two。

 three up to well， I'd be kind of silly to just do a few。

 but essentially sample uniformly from all possible numbers of queries up to capital T。

 which would be the optimal number of queries in the case where there's just one solution。

And so then I'd be sampling from this sinusoid essentially。

 and because the average of the square of a sine function is one half。

What that means is that averaged over the choice of the sample number of queries。

 our probability of success is going to be one half。ok。

And so each time we have a pretty good chance of finding a marked state。

 if we find it we can check that it's right because we just evaluate the function one time to be sure。

And。So。That's what we do and if we don't find it the first time we try again and after a few trials chances are we're going to find a solution。

 we're going to fail after M trials only with the probability。

 which is at least as small as one half to the M。Now。

 so far I've been talking about the case where we just do completely blind exhaustive search。

 we really have no idea where to look for a solution。That's not always the case for NP hard problems。

 sometimes we can make a guess or we have information that indicates that some trial solutions have a better chance of panning out than others and in that case too we can achieve the quadratic speed up。

Just as an example。I suppose that of those capital N possible strings。

 therere actually a smaller numbered capital M， which have a higher a priority probability of being solutions。

 and so I could try sampling just from those capital M instead of all capital N。And。Then。

In the classical case。The number of queries that I would need would scale linearly with them。

 but quantumly I can still do it with square root of m queries， here's what I have to do。

The initial state that I want is going to be， let's say。

 if I don't have any reason to think any of these candidate solutions are more likely to succeed than others。

 the uniforms superposition of all the candidates。So let's say there is some efficiently computable unitary。

If I really want to do this in practice， I'd care whether it's sufficiently computable。

Which can prepare this state so I could use that and by preparing it。

 I mean acting on the basis vector0， u gives this superposition。

And so I can use that to prepare my initial state， I can also use it for the iteration。

 this is sort of what I was trying to say before in the case of the grover iteration where all capital N strings are considered a priority equally likely。

 the unitary that appeared here was the unitary that mapped zero to the uniform superposition of all capital N。

Basis states， and then this conditional phase， which is triggered by the all zero state。

 conjugated by that unitary gives the the unitary that we do ourselves as part of the grover iteration。

And in this case， if this unitary is something I can do efficiently， I use the same idea。

 I take this conditional phase gate。Triggered by the zero string， I would conjugate it by you。

 and then I can do the analysis the same way we did it before。Considering the。

The angle between you know this state and the mark state and then the way the angle is changed when we do the grover iteration using this unitary ourselves as well as the query。

 the analysis goes through just the same way。And so the number of queries I need classically here is capital n。

 but quantumly I can make it order square root event。

And there you can generalize that a little bit more by as essentially。

 if you do some kind of search which is informed。By the structure of the problem。

If you can do it classically， then you can speed it up quantumly quadraically by using Grover's idea。

Okay， so this is pretty cool。 we've seen that quantumly we can achieve a quadratic speed up of exhaustive search。

Compared to when we have only classical queries and so it's natural to ask。

 is that the best we can do is。Having the number of queries go from the classical number。H。

Essentially n to the what can be achieved quantumly square root of n is at the optimal speed of。

And the answer is， yes， it is the optimal speed up in other words。

The answer to the question the way I asked it here is that we can't do better， no， too bad。

So let's consider the case， of course we could talk about the case when there are many solutions and it' would be a similar story。

 so let's go back to the hardest case。Where there's just a single marked string and we're trying to find it out of capitalM possibilities。

So our phase oracle。Is as we and this is I think， is where I went from w to omega。

 these are actually megas now， okay。Is going to flip the phase。Of the marked state omega。

 it's not going to do anything to everything orthogonal to omega。And。In the Grover algorithm。

 we used that use of bass。In between queries and now the question we want to ask is what if I do some other unitary。

 in fact I could pick a different unitary。Every time between queries。

 so I start out with some initial state， whatever it is。

We had a particular initial state that we liked but it could have been something else and then we do any unitary in the world we want to on that state and then we query and then we do another unitary which is ours to choose and then we query et cea。

 et cea， et cetera until finally we do a unitary and。Then a query， a final unitary， and then a query。

I could have put another query at the end， but that would only affect the basis that I have to measure and in the end so I didn't bother with that last query。

 but anyway this is the general situation where I have capital T queries and general unitaries between the queries and some general initial state that we started with。

ok。😊，Now， the state that we wind up with。If we run that procedure。

Is going to depend on the marked state because all of the queries depend on that state mega。

And so there are really n possible states that we can generate through our procedure。

Once we fix the unitaries that we apply。The capital and possible states correspond to the end possible。

Mark states the end possible ways in which the。Oracle could act when we do a query。Now。

 the unitaries that we do。Don't make。It easier to tell the different mark states apart。

 So what we would like is for these n vectors once we're done。

 the n possible vectors we could get for the capital N possible choices。For。What the queries do？

Is we want them to be as distinguishable as possible so that we can measure and find out as much information as we can about which omega really was。

Okay。So what we want is for the vectors as we apply more and more queries to s out from one another to separate。

 so they're easier and easier to distinguish from one another。But that splaying of the vectors。

 which makes them easier to distinguish， that's not something that happens when we do our unitaries。

 when we do our unitaries， U1， U2， et cetera。 that just rotates all of those n vectors together and doesn't change their relative orientation at all。

 It's only the queries that can do that。And in the end， if when we're done。

 we really want to be able to identify the marked string with a very small probability of error。

We want them to be almost perfectly distinguishable at that point。

 so we want these capital and possible vectors to be very close to mutually orthogonal。

And then when we measure in the right basis。The computational basis。We played our cards right。

 we'll be able to unambiguously identify which omega it was because those capital in vectors can be perfectly distinguished from one another by the measurement。

So what I want to do is I want to keep track of how those vectors play apart as we do one query after another after another。

And what I want to see is。That we're going to need lots and lots of queries to make all capital n possibilities distinguishable from one another。

And that's how we'll obtain a lower bound on the number of queries that are needed to find the marked state with low failure probability。

So to keep track of that spplaying， it'll be convenient。

To instead of looking at how vectors for different values of W separate from one another。

I'll look at how the vectors for given W。Deaviiate from some fixed reference vector。Well。

 it fixed at least in the sense that it doesn't depend on W。

Although it will depend on the number of queries。And that'll be a convenient way to analyze how far apart all of the UW of Ts are getting from one another as we increase the number of queries。

 okay， that's our strategy。The reference state that we're going to use is going to be a state like this。

 except we leave out all the oracle calls。Some we or you if in one way people sometimes say it is we replace the oracle by an empty oracle that doesn't do anything。

 it just applies the identity， we could just as well say we don't do the queries。

So we'll do our unitaries， U1， U2， U3， et cetera， but with no queries in between。

And that will define for each value of little T， a reference state， which I'm going to call phi of T。

And what I want to keep track of is how far apart is psi sub w of T。

The what the state has become when we're querying with a box that marks the。The state mega or T you。

 whatever it is， I'm calling it。And so after little T queries。

Ssi omega is going to Diateiate from the reference state phi of t by some amount。

Which is E sub W of T。So phi is a normalized vector， psi sub omega。Is a normalized vector。

 E of omega is not， it's just the difference between the two when I had to call it something。Okay。

So just just repeating some of the things I just said。

si omega of t is the result of doing here now I have little t because I want to see as t increases how this deviation is going to be affected。

So this is after I've done。Little T queries with unitaries of my choice， U1， U2， et cetera。

 in between the queries。And I'm going to write this vector as my reference vector5 of T。

 which is obtained by the same sequence of unitaries that I chose。

 but without any of the queries to the box。I'm going to write it as 5 T plus the deviation。Okay。

 and now I want to look at how that deviation is affected when I do one more query。Well。H。

I do one more query after doing one more unitary of my choice。

The T plus one unitary use of t plus one， and then I do the query unitary。

So after I've done one more query， I have the state P psi omega t plus1 that's obtained by acting on psi of T with u t plus 1 and U omega。

嗯。si of t is equal to phi of t plus deviation of T。

 so I have u omega u T plus1 acting on phi the reference vector。Plus。

 U omega Ut plus1 acting on the deviation。And that's what。Size of W is after one more query。

 but I want to compare size of W with the new reference date because I've added。嗯。One to the time。

 the reference state is。Depends on the number of unitaries that I've applied or when I apply u T plus1。

 the reference state becomes phi of t plus1。So I want to keep track of the difference between the reference state and the vector that we got from the queries after one more time stuff。

So for that purpose， it'll be convenient to write。The query unitary as the identity plus its deviation from the identity。

 it I plus use of w minus1。So。When I do that， I have this term which is U omega Ut plus1 acting on 5hi of T。

But from the identity piece here， that's going to just give me U of t plus one acting on5 of T。

 that's5 of t plus1。 Okay， so that's good。 So now I've I've got I've written size sub omega t plus1 as the reference saved t plus1 plus some other stuff that other stuff is the new deviation。

The contributions to the new deviation are， first of all。

 the rest of the unitary use of omega minus1 acting on the。

Deviation that I get from applying Ut plus1 to5hi of T， so that's this guy。

But then I also have to consider U omega Ut plus1 acting on the deviation from the previous step。

So now the new deviation is going to be the sum of this term and this term。

 so what I'm calling E sub omega t plus1， the deviation from the reference vector after t plus one queries。

Is going to be given by u omega minus identity acting on the reference data at t plus 1 plus U omega u T plus1 acting on the deviation at the previous step。

Okay， so now I just， I'm just going to use the triangle inequality to get a bound on how much that deviation grew。

In that last query。I'm going to say that the deviation after t plus one steps by the triangle inequality is less than a and I'm using the operator norm to keep track of its size。

 the soup norm。Is less than or equal to the deviation at step T。Well that's just the the soup norm。

 well sorry， not soup norm because these are states， I just mean the norm of the state， you know。

 okay。You know what the norm of the state is， not an operator。

Now use of omega of times u t plus one that's just a unitary， a product of two unitaries。

 so that doesn't change the norm of this vector。So。In my triangle inequ。

 this just becomes the norm of the vector e of omega of t。And then I also add this term。

 which is the norm of the vector resulting from U omega minus identity acting on 5 t plus1。Okay。

Now at this point， let's remember what。What the queries do？What unitary Uomega is？It's this guy。

 it's identity minus two projection on omega。It changes the phase of mega。

 doesn't do anything to the states orthogonal to mega。And here I have omega minus identity。

 so that's just except for this minus sign。Twice the projection onto mega。

So what I have here for my bound on the difference between the deviation after t plus1 steps and the deviation of T steps。

Is two times。The absolute value of this inner product of omega with phi T plus1。

That's because I just plugged in what U omega is。Into this expression。

 the second term in the triangle inequality。All right， so that deviation is going to grow with time。

As I do one query after another。I have a bound on how much it grows in each step for each query and then to get a bound on how large it has grown。

After capital T queries， I just have to sum up these increments over capital T steps。

Now it's going to be the overlap of the mark state with the reference state at time little T。

 absolute value。times a factor of two summed over all values of little T。The first query。

 the second query， the third query， and so on。So that's my bound on the deviation after capital T queries in the case where the mark state is mega。

Now I'd like to write this in a different way。Using the khi shortwartz inequality here I have the sum of some。

Absolute values of complex numbers。What Koshi Schwartz says is that the sum over little t of the absolute value of c sub t can be written as less than or equal to the square root of capital t。

 the number of terms， times the norm of the vector whose components are absolute value of Ct。

 in other words， the sum over little t of c sub t squared square root of that quantity。

You may be familiar with Koshi Schwartz as saying that the absolute value of an inner product。

Is less than or equal to the product of the norms of the two vectors in the inner product this is just a special case of that you can think of the two vectors in that version of the Koshi Schwartz inequality as being the vector with capital T components where the components are the absolute value of C subTs and the other vector is the vector with capital T components where every component is one。

So the expression on the left here is just the inner product of those two vectors。

The norm of the vector， all of whose components are one when there are capital t components。

 that's just the square root of capital t， it's the square root of the sum of1 plus1 plus1 plus1。

 etca， t times。And then the norm of the vector whose components are capital absolute value of C subT that's just this expression。

 the sum of those components squared square root of the whole thing， but that's just goshi shortwars。

So what it tells me is。The norm squared of this deviation， and just to remind you what it is。

 that means the norm squared of the difference between the reference state after capital t states and the state that we get when we include the queryries size of omega capital t。

We we had that。It could be bounded by the sum。And now I'm going I've squared it here。

 so though what I can do is square the right hand side of the koshi shortwartz inequality here。

 I had this factor of two that gets squared to become four。

 I had this square root of t that gets squared to become t。

And then what's left is the sum of the squares of these overlaps。

 the sum of this absolute value squared of the inner product of omega with phi of t。Okay。

 summed over little T from one to capital T。So now we have an upper bound on the deviation faculty steps。

The deviation of the。Case where we include the queries。

From the case in which we don't include the queries。Now。

 that applies for all possible choices of the Mar state。

 Omega could be any one of capital N possible basis vector， which is marked。

And so that's here I just rewrote what we had on the previous slide。

So now what I'm going to do is I'm going to sum those deviations over all the possible marked states。

So I'm going to sum the。Possible marked strings from 0 to capital n minus1 for each one of which I know that this deviation squared can be bounded as shown here。

AndBut now I'm going to reverse the order because why not they're finite sums。

Between the sum over little t and the sum over omega。

 and then I thing about that is that the sum over omega of absolute value squared of inner product of omega with 5 of t。

 that's just equal to1。Okay， because it's just the sum of all the components of phi of T along an ortho normalmal basis。

Squared。And it's a normalized vector。 P of T is a normalized vector。

 So that sum is just going to give me one。 And so then I've just got one。

Smed from little t equals1 to capital T， that's just one occurring capital T times so that sum is just capital T。

Times 4 T。 So this is 4 T squared。 We have 4 T squared as an upper bound on the sum of the deviation squared summed over all the possible mark states。

Okay， now suppose it's true that with success probability extremely close to one。

That we can identify the mark state perfectly。 That means that the different vectors corresponding to different mark states have to be mutually orthogonal。

Not only in that case would I be able to essentially perfectly distinguish them。Now。That means that。

In the case where the success probability is essentially one。

The psi omega of capital T's should all be elements of the north and normal basis。

Now for any orthonormal basis and any fixed vector。I can consider the sum over the basis elements。

 the difference between basis element and。A fixed vector。Norm squared。And。When I evaluate that。

 well the norm squared， that's just the inner product of this guy with itself。

 and so we get the inner product of I with I and a phi with phi that gives me two。

 but then we have minus inner product of I with phi minus inner product of phi with I。

 that's just going to be minus2， the real part of the inner product。

So here I have two appearing capital N times。And so that just gives me2 n and then I can get a bound on that by asking what's the largest that these real parts can be well they can't be larger than the modulus of the inner product that would be the case in which the inner product actually is real and positive。

And so I can write this as2 n minus this sum。Time two of I equals one。

2 capital n minus one of absolute value of inner product of Phi with I。

 but that's just the kind of sum that we bounded using kshi shortwartz on the previous slide。

It's bounded by the square root of the number of terms by the square root of n if phi is a normalized vector。

And。And so what we have is that this is greater than or equal to 2 n minus2 square root of n。

So n is really， really big， so the square root of n is really small compared to。The N。

 I can write this as2 n times 1 minus some little correction， I wrote little O and。

 which just means that as that capital N gets large， this becomes as small as you please。

So what this is telling us。Is that we know that4 t squared。Is greater than or equal to this sum？

We know that if thesi omega of capital Ts are perfectly distinguishable。

 then this sum is greater than or equal to2 capital n times some small correction。

 which I'm not going to worry about。 So that tells us something about the number of queries。

 The number of queries that we needed to make these states distinguishable had to be。

 let's just divide by four and take the square root had to be at least the square root of n over2。

About 0。707 times the square root of n。What we found using Grover's algorithm is that we can find the marked state by choosing those unitaries to be the right unitaries to do the grover iteration。

Capital T times。Then with Grover's algorithm， the number of queries used is pi over four times the square root of n just a little bit bigger。

 0。785 times the square root of n。And。That's pretty close so we have an upper bound on the number of queries because we know we can get probability essentially one for finding the mark state using Grover with 0。

785 square root of n queries。But what we seen。I that we needed to have nearly that many we needed to have at least 0。

7007 square root event now actually if you tighten this argument up and you put in a little more detail。

 you can close the gap between the 785 and the 707 and it's really the case that we need by over four times square root event queries to get an arbitrarily small failure probability。

When we measure to identify the marked string。Now， this is all in the case in which I demanded that we have。

A success probability， which is。Essentially one， of course， we might be willing to settle for some。嗯。

Success probability less than one， what if for any choice of the mark string。

 we say it'll be okay if we identify it with a success probability of at least one minus epsilon。

So we're allowed to fail with probability epsilon， but no worse than epsilon for any choice of thes of the mark string。

 but then we can change the story a little bit。That when we make our measurements at the end in the appropriate basis。

It's okay for the states to deviate away from the orthoormal basis， which is labeled by。

The different marked states， so it would be all right if you know。

 after we've rotated the basis to line up the vectors as best we can。With。

The computational basis elements corresponding to Mar states。

That in the case where omega is the actual marked string。When we're done with all our queries。

 we have omega times some coefficient a sub omega and something orthogonal to omega with coefficient B sub omega。

 as such said when we measure the orthogonal case occurs with probability no larger than epsilon。

 which means that the amplitude for the orthogonal piece shouldn't be larger than the square root of epsilon。

ok。And so when we take the overlap。Of。si omega of t with phi， the reference state。

We got a contribution which is a omega， but I'm just going to bound that by one。

Times the overlap of phi with omega， the inner product of Phi with omega。

 but then there's this correction。Which can't be larger than the square root of epsilon coming from the inner product of Phi with the orthogonal part。

Of Psi omega。Okay。And now we just run through the argument again。

We know that for t squared is greater than or equal to this quantity。

 that's true no matter how many queries we have。And but then I use this result。To bomb this。

That I'm going to， well， it's I can just write this out like I did before is 2 n minus of 2。

Times well， it's actually a bound minus the absolute values of the inner products of the s omegas with Phis。

And so I get the 2 n from this term and the minus2 square root of n。

 which we got from this part of this inner product。

 but then there's an additional piece coming from the error。

Coming from the component which is perpendicular to omega。

 which can be as large as square root of epsilon in each term and there are all n terms well actually two square root of epsilon in each term。

 and so I get this minus2 n square root of epsilon。Well， as before。

 the squared root of n is negligible compared to capital N when N is really big。

But the epsilon also comes multiplied by capital n。

 so what we conclude for the number of queries if the probability of success is at least one minus epsilon。

For each possible choice in the Marx state is square root of n number two， what we had before。

 negligible correction when n is very big， but now one minus square root of epsilon。

 and because this is a bound on t squared， I have the square root of one minus the square root of epsilon。

So for some order， one epsilon is not much different than before the coefficient of square root of n changes a little。

But the number of queries that we need will still scale like the square root of the dimension of the Hilbert space if we're looking for one mark state。

So the conclusion is that even when we allow for some probability of failure。

As long as the probability of failure is bounded for any choice of the mark string。

The number of queries that we'll need to identify the mark string is still going to go like the square root of in。

We can't do better than that。So what's the broader lesson from that well you might take it as。

Suggestive evidence。That NP is not contained in MQP sorry in BQP that we can't solve NP complete problems with quantum computers。

Why do I say that？At least we can't， by just using the power of quantum superposition to speed up exhaustive search。

 do better than a quadratic speedup， we can't get an exponential speed up。Um。

 by doing exhaustive search on a quantum computer to try to solve a problem in NP。

That's just not enough if we're going to do better then somehow we have to take advantage of the structure of the problem so we can do something better than just testing all the possible solutions for testing from some very large pool of possible solutions。

啊。We would have to take some NP complete problem， make use of its structure。

 to speed up the solution quantumly in some more dramatic way。

But nobody really knows of any such structure for NP complete problems that would allow us to speed them up dramatically。

 classically or quantumly， if there is such structure， well。

 we just haven't gotten a glimpse of it so far。We don't know how to improve on exhaustive search for some hard instances of。

And be complete problems and if we can't do better than that then quantumly we're not going to do better than a quadratic speed up。

Because when it comes to speeding up exhaustive search， the quadratic speed up is the best we can do。

Okay， so that's the story of。Exhausive search on quantum computers。And polynomial speedups。

 quadratic speedups are nice。Maybe they'll be important someday。

 I guess one way of saying it would might be this， you know。

 let's say there's some some maximum instant size， maximum input size rather。That we can handle。

With a classical computer and solving some search problem。Then with a quantum computer。

 assuming the quantum and classical computers have about the same clock speed。

We'd be able to handle inputs which are。Twice as big。Right because。嗯。You know。The square root。

Of two to the n。Is。It's 2 to the n minus1。嗯。So。Yeah， I guess that's right。So that's okay。 You know。

 if we had to stop at。And1 thousand。嗯。Bit inputs for。For a classical computer， maybe we go up to 2。

000 bit inputs for a quantum computer。And。That's better， but it's not sensationally better。And。

 you know。The truth is that for the foreseeable future。

 there's going to be overhead with quantum computing because of the need to do error correction。

If we're going to run circuits which are of reasonable size for solving really hard problems。

We're going to have to use quantum error correcting codes and that means extra qubits to have sufficient redundancy now formally the theorem that one can prove about quantum error correction。

Is that once the error rate is below a certain threshold of accuracy。

 the overhead cost is just is just poly log。And。So in principle， if you have a quadratic speed up。

 but you have to pay a polylo price。To have sufficient redundancy to run your algorithm reliably on a quantum computer。

 you're still going to win。But that might only kick in asymptically for very。

 very large inputs and so I'm not terribly optimistic about say sometime in the 21st century。Well。

 that's who knows， that's too far off， I shouldn't say that。But at least。

 let's say in my lifetime and I， as you know was still a very young man。

I don't expect to see a lot of practical impact of the quadratic speedup for exhaustive search。嗯。

Sad to say， but it certainly is a cool idea and it's there's a lot of beautiful theory about other types of polynomial speedups。

 which unfortunately we're not going to take the time。

To discuss what I would like to discuss is using quantum computers for quantum problems because based on our current understanding。

That's where we have the best hope that quantum computers will have a big impact on the world。

 and so that's what we'll start discussing in the next lecture。



![](img/b56708f980a820e1e6d75b2ca0f24bc7_2.png)

But so。I guess that's it for now。And hope to see you next time in the meanwhile。

Take good care of yourself， be well， I'll see you soon。

