# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p22 P22 Krahmer-Mendelson-Rauhut proof wrap-up, BPTree -BV11zi7BjEHu_p22-

![](img/72a17577f9a09ef476ec153b43637476_0.png)

I think you're muted。Very great， so thanks for that。So good。

 let's I just want to finish off the proof of the KMR theorem from last time because we were almost done with the proof we were less than half a whiteboard away from finishing it。

So let me do that I'm going to first remind you of where we were and then after we do that i'm going to show you。

How to use these tools like Dudley's inequality to actually come up with an even better algorithm for the heavy hitters problem。

 so maybe it's not clear why those two things would be related。

 but you'll see that in the remaining part of lecture。Yeah， so if you recall。

The KMR theorem was this， you have a set of matrices， script A and plus minus one random variables。

 the theorem actually holds for subgausians as well， but we just proved it plus minus ones。

And you're looking at this supreum of a stochastic process so a stochastic process is just a collection of random variables Okay so our random variables here are these differences as sigma L2 squared minus expectation as sigma L2 squared so each one of those is a random variable and we're looking at the soup over all of them in magnitude。

And there was this theorem that it's bounded up to a constant factor by this righthand side。

 gamma2 squared plus gamma2 times the Frbeius radius plus the Frbenius radius times the operator on radius。

 and this was related to Gordon's escape through the mesh theorem to get instancewise bounds for dimensionality reduction。

Where。TheThe target dimension is not log n over epsilon squared。

 but it's the square of the Gaussian mean with over epsilon squared right and the way that we got that from KMR。

Was for each point。That we're trying to preserve， we can define this matrix。

 so for each play X we're trying to preserve， we define this matrix aid x。

 which is written here at the right hand side。Of the whiteboard。

And then we basically will apply KMR to that family of A's， so AX for EX in the point set。Anyway。

 so let's finish off the proof of KMR。嗯。So I defined。

Let's go to where we were for camera Okay good So I defined E as being the that expectation of the supreme of the satorcastic process。

Okay。And I said you know I denoted the columns of a by A1 a2， et cetera。

 and I said that TR is an admissible sequence if you don't remember what that means。

It means t0 size1。TR has sized at most two to the two to the R。And the Ts are nested。

T0 is a subset of T1， which is a subset of T2， et cetera， which are all subset of T。

And I define this notation pi RA is the closest point to A and TR under operator norm。

And Delta R is pi R minus pi r minus1。Okay。So given all this notation， what we showed last time is E。

Which is the thing we're trying to bound。We showed that E was at most。This thing here。Okay。

 and you know， we bounded the first term already。We got to this term already。By this。

That's the operator norm radius times the Forbenus normius radius and then our what we were finishing off was bounding like this thing in the middle。

And the thing on the right and the thing in the middle are basically the same I mean。

 in terms of how they're not of course， they're not the same exactly the same but。

The the way you bound one is pretty much exactly the same way as you bound the other one。

 so we just focused on the middle there。Okay， what was this XRA？XRA is defined up here。

It's this dot product。I bet talk。So Delta RA sigma dot with pyr minus1 a sigma prime。

And then we summed over all ours from one to infinity of XO ray。Of this well。

 expectation of the soup over a of the sum of XRA。So that's the thing that we are trying to now understand。

这不是这个。Okay， and。Basically， you know， we just use the fact， so call this。

 call this big random variable。嗯，Z。Okay， the soup over a the soup over all a of the sum over R of the absolute value of XRA。

Call that entire thing Z Z is a random variable。 It's a non negative random variable because there are absolute values there。

And the expectation of a non negative random variable is the integral of its taildown that just follows from integration by parts we used that last time right that was this inequality that was this inequality right here。

The expectation of random variables to integral of its tail bound and then。

We just did a U substitution， you remember from， I guess high school calculus。

 you do a U substitution。We did that to artificially insert a gamma2 in there。ok。嗯。I mean。

 you should say with Gelani if it's artificial， why is gamma too special。

 why couldn't I have inserted anything else and the reason is。When we put a gamma two in there。

 specifically that thing that's circled a billion times in red。Okay。

 that's beta and we did the U substitution u equals t times beta or actually be well， I should say。

That whole thing in the red box， not just the thing that's circled。

 but this whole thing in the red box。Was our beta。And then we did a U substitution。

 we said u was equal to t times beta。And now the point was after we did that， we could do this like。

Infinite union bound after doing kinchin inequalities， one for every R。

 So for each fixed A and for each R， we could do kinchens inequality to get a tail bound and then we could union bound over all we could union bound over the entire net and we could union over all all the elements of T R and we could also union bound over all R。

And then we would get this circled sum， which was convergent。

So that's kind of whygan to a special it's not like you could have just put anything in there you need to put something there such that when you calculate the probability。

 the probability that。The left hand side exceeds the right hand side。

 you get something that when you integrate it converges to a constant。

And it just so happened that this choice of beta made that happen。

 it made that integral of the probability converse to a constant so that what you were left with at the end of the day was just beta outside of the integral。

So that was why this choice was special。Okay。And then what we said was， look。I'm just。

 this is just rewriting more cleanly what was on the previous whiteboard。😡，What we were saying was。

 I didn't say this explicitly last time， but this is kind of where we left off。

So what we left off was basically right here。唔仔。And。This Delta RA， just by triangle inequality。

 what is Delta R， Delta R is pi R minus pi r minus1。

So if you just add a and subtract A and then do triangle inequality。

 you'll get what I wrote above it in red， namely that deelta RA in norm is at most a minus pi RA plus a minus pi minus1a。

And the Ts could be anything。So if you just choose the CRs。To minimize the right hand side。

That is the definition of gamma2 gamma2 is the in over all admissible sequences of Ts of this quantity。

 right？So that is gamma 2。And then this is basically now where I want to pick up from and we're going to finish this proof right here on this whiteboard。

Okay。So how do you finish the proof？嗯。First， you just do some koshi schwartzing。

so Kohi Schwartz says。The expectation of a。Is that most square root of the expectation of a squared？

So I'm going to do that here， this is at most。Square root。

Of the expectation of a similar prime soup over a。Aing a prime operator arm。

 this this an L2 norm squared， this is L2 norm， this is a vector。Time together two。

I'm just going to write gamma2， which you should read that to me in Gamma2 of script Day with respect to operator normm。

And then now I can do a triangle inequality， I can subtract the expectation and add it back。

This is at most。Um， so this square root thing is the same thing as。

 I think it's just going to be easier for me to write。Square root。

 I'm just going to say is like raising into the one half。So this is at most by triangle inequality。

Expectation over S prime soup over A and script A of。

Asigop prime L2 norm squared minus the expectation of asigma prime L2 norm squared。pl。

The soup overall， a。OfThe expectation of receiving prime。Of a sig prime l norm squared。Squa root。

Times gamma two。ok。This thing。Is also known as， I mean， it's just a trace。Of a transpose a。

Does that make sense？Sigma transpose B sigma。 This is equal to this thing here is equal to。

Sigma transpose a transpose a Sigma， right， Sigma transpose B Sigma is the sum over all I J。Of BIJ。

sigma i sigma j。If you take your expectation of that。

What happens when I is not equal to J I'm looking right here when I is not equal to j。

 you get zero in the expectation when I equals j sigma i squared is1。

 so the only thing that survives in the expectation is the trace it's the diagonal terms right so this expectation that's boxed below is the trace of a transposese。

 which is just the Frbeni norm squared。So then if you take your soup over that。

That's the soup over the Forbenia storm squared， that's just equal to the Frbeius radius squared。嗯对。

And then now you use the fact that。You know， square root of a plus B。

Is that most square root of a plus square root of B。So now what we get is。This is at most。嗯。

Forbeius Nor radius sub A。pl。If you notice what is this thing。

 so it's going to be like this thing square rooted， right？

It's going to be this part square rooted what is what is that thing that I've just circled in red？😡。

Yeah， it's E。AndBut there's a square root， so it's root E。All times gamma two。So in other words。

 if you just put together this was only a bound on the XR part。

Don't forget that those the YR which basically gave the same thing。

 and then there was also this first part over here。Which gave us this。Okay。

 so if you put so E was bounded by the sum of all those things， so if you put it back all together。

 this implies that。E is that most up a constant factor。

The operator norm radius times the Frbeius norm radius。Plus。嗯。The three norm radius times gamma2。pl。

We're E times gamma2。And let me just call， let me just name this thing。

 I'm just going to name this thing。Zi。Right， so what have we really shown we've shown that。Z squared。

Minus。Some constant C times gamma2 root Z。嗯。Minus some constant times。Df gamma2， well。

 actually let me just pull the DF out。Gamma 2 plus L2 L2 operator radius。Is at most0。

That's what we've just shown。唔嘢。So this is a quadratic equation。And you know。

 when z is minus infinity， it's infinity， when z is plus infinity。

 it's infinity just because there's the。The constant factor in front of the Z square term is positive。

So you know this quadratic equation。You know， if you plot it， you know， it looks something like。

Something like this。And here it is Z。And then then the y axis is sum is the z squared minus whatever。

So I just plotted that quadratic equation， this is zero right here。And what are we saying。

 we're saying that z is at most zero。Which means that Z has to be smaller than the larger root of this quadratic equation。

Z has to be。Z is at most this point。Right， does that make sense？Right。

 is it any questions about that？Excellent， makes sense good。So that's it。

 you basically just solve the quadratic equation for Z， you look at the larger root。😡。

You don't really want to bound Z， you want to bound z squared right Z is root E。

 we're trying to bound E So you look at the larger root of the quadratic equation， you square it。😡。

And that's your bound on E。And if you do that。Let me not do it because it's not really interesting it's just like a calculation at this point if you do that you're going to get exactly what's written here the right hand side。

Okay。So that's it， that's the proof。If you look at the probability review in the lecture notes。

I call this the square root trick。You know basically you have some usually it's some moment bound。

 some moment that you're trying to bound， you do some sequence of steps to bound it in terms of its own square root。

 you solve a quadratic equation and then you declare that the moment is that most the larger root of the quadratic equation so there's a proof of Bernstein's inequality in the notes that that goes about the same exact way。

And I think there might be， I think Hanson Wright also， the proof of Hanson Wright。

 we also in class did that was also via the square root trick。So it's a it's a pretty。

 I think useful trick iss a trick that I think was invented by Mark Ruodelson back in the。Late 90s。

 but it's kind of useful all over the place。O。So that's it。

And now I want to show you another application of。This business of Supremepremo of Gausian processes or stochastic processes。

Okay。So another application。Okay， let me just write other。Other applications。

know bounding supremo stochastic processes， like Gausian processes or rotmara processes。So one is。

Showing。That。SH。Satisfies。嗯。RIP。So here S is a sampling matrix。And H is had a marred。

You can also use the DFT。So if you remember。If you remember when we when we proved。The Kramer was it。

Cear reward theorem。Right嗯。That you can take any RIP matrix and get a jail distribution out of it。

One of the things I mentioned at the time was that's another way of analyzing fast JL because it's known that SH with high probability satisfies RIP therefore if you throw the D on it。

 which is the diagonal signs you'll get a jailL distribution so how do you actually prove that S satisfies RAP。

I'm not sure that we'll have time to talk about it today if we do at the very end and I can say a little bit more。

 but basically you can write down， you can write down kind of what you want to bound and then do a little kind of a few standard tricks。

嗯。So basically turn it into bounding the supreme of a Gaussian process。

And then you can use Dudley's inequality and that's exactly what Ruddleson inversion and do to show it there were some sharpenings of the log factors after them。

But you know， the basic idea that this can be reduced to bounding the Supreme of a Gausian process was due to them in Ruddleton verse in 2008。

Two is getting a。More memory。So for example， I can just say this is due real estate version。呃。

Lower memory。Requirements。To solve。Hel two heavy hitters？And insertion only。Streams。

So you know that the count sketch。He says L of K log in。Words of memory。That it turns out there's。

There's another data structure called the BPP treee。Which uses K log K words。Remember。

 you're trying to find up for the approximate top K。

Out of a universe of size n so k is always at most n in particular， if k is a constant。

 you're trying to find the top 10 or the top 100， the BP tree uses a constant number of words of memory。

 whereas the count sketches is O of log n words of memory。嗯。And I'll just say it's an open problem。

Show that O K is possible。 well， actually It well I don't know that it's true。

 so I should phrase a little differently。Is O K possible？We don't know。

And you know L1 heavy hitters and insertally streams。

 we know that you can solve that in 2 k words of memory that was one of your PSet problems on the very first PSE I think that was the last the last problem on the PSet if I remember correctly。

But for L2 heavy hitters。We don't know。You know， we don't know whether the right answer is k log K or whether it's k I mean。

 we know that there are differences like the Bp tree is not a deterministic algorithm。

 it's randomized。Okay， and we know that I believe that you know。

 you can show that you need to be randomized for LT heavy hitters to be able to get anything which is sub linear。

 whereas for L1 heavy hitters。That problem on your PSet on PSet one， you know you could。

 if you didn't use the dictionary， if you didn't care about runtime， you didn't use hashing。

 you could get a completely deterministic algorithm。That uses O of K words of memory right so for L1。

 the story is a little bit different we know that O of K words deterministically is possible。

I think that's not possible for L2 the best we have is a randomized K log K。

 so can you get randomized k0 of K that's the question。So。Good。

 so what I want to focus on for the for the next。For the remaining part of lecture。嗯。嗯。

Something about the RIP as well。So， and I guess the reference for this is well there were a lot of。嗯。

Braverman， we are a lot of authors， braveverman。笑死。Yeah。Yeah so。So just， if you remember， you know。

 if I look for it is this braverman。I mean， it's going to be in the notes。

 the reference will be in the notes， but it's from pauses 2017。Okay， great。

 so let's let's look at it。So the B P tree。First。Reducuce to the super heavy problem。

And the second step。Show it like okay， in particular， when I say reduced to super heavy。

 I'll define you haven't told you what super heavy means， but I'll tell you so we'll show that。

If can solve。Super heavy。In space， S。Then can solve。L2 heavy hitters。In space。O of K log K times S。

So the second step will be。That we can achieve。Asking what the constant。Okay。

So what is the super heavy problem， so super heavy？Is that。

An item is not just a heavy hitter heavy hitter means that you're at least 10% of the L2 squared mass or you're at least 1% or whatever super heavy means that you're not just 10% of the mass you're like you are almost all of the mass。

 you are like 99。9% of the mass。Okay。So Superany。Super heavy。If。Xi。Is。Let's say bigger than。1000。

Times the sum of J not equal to I。Of X weird。So that's the definition of super abb。Okay。

 so if it had been in an L1 cent。Um， if it had been in an L1 sense。

 then what it means is like literally 99% of the things you see in the stream are I。

Here's an L2 sense， so it's not so。Here。Like Gi give you an example。

 let's say you have a stream with n elements。One item appears 100 root n times。

 100 times the square root of n times， all the other items appear once。

So the total length of the stream is n。UNow the mass of that item that appears 1010 times well when you oh this should have been squared。

 sorry。When you square him， you get 10000 n Xi squared is 10。

000 n whereas everyone else combined is only like less than n right so in a squared sense he really dominates he's almost everything。

Does that make sense， so that's what it means to be super heavy。

 which is not the same as being 99% of the stream， it's being 99% of the stream or 99。

9% in an L2 sense in a squared sense。Okay。So I'm going to show you parts one and two。

 how do you reduce the super heavy？And then how do you solve the super heavy problem？

Does that make sense？Yeah。So first， let's reduce。对。

So I'm going to so let's suppose what is a reduction。

 a reduction if you reduce from problem A to problem B。What it means is。

If you have a black box that can solve B。Then you can use that to solve A。

RightSo if we have a black box that solves super heavy。

We can use it to we can use that black box to solve actual heavy hiters and actually they just stay something here。

嗯。You know the success probability just needs to be a constant here。

India can solve surrounding Space S。律四。With failure probability。At most let's see one1。

Then you'll show that。And here I' going to be with failure probability。One of aly kid。

So if you can solve super heavy with failure probability， what 10%？

I hit his problem with failure probability one over polyK where the expon the polyK can be。

However big do you want to just it'll affect a constant factor in your memory。

So what's the reduction to super heavyvy？So what I'm going to do is the following。

 suppose I have a data structure that solves super heavy， I'm going to instantiate few copies of it。

So call this D1， D2。Ip to DQ。Each we right up here。Each DJ solves。Super人。

I must have the hash function， H。Which maps the universe。Into one to Q。

And it's from a universal hash family or paraized independent hash family。

So that means I can represent H and O of login bits。

Whichch is just a constant number of machine words。是。And now whenever I see eye in the stream。

I' want going to compute H of I。And that's going to send me into a random DJ and it'll be processed there。

Okay。😊，So now what can I say？So if you pick you。Pick Q to be like very big， I mean。

 this constant is not the best possible constant， but you know， pick Q to be like a million times k。

你觉得。Let I be a heavy hitter。They're only k of them， right。

 they're only K heavy hitters because heavy hitter means approximate top K。

 so let I be a heavy hitter。The probability that。I is isolated。From other。Heavy hiters by H。

I claim it's actually quite high。Right。😊，Because。What is the expected number of other heavy hitters that collide with I under H what's the you know。

 if you look？If you look in here in this bucket。How many other heavy hitters landed there， Well。

 in expectation。It's k over Q。😡，Right。So you expect K over Q， K over Q is one in a million。

So you expect less than one over a million。So what's the probability that you have at least one？

The probability that you have at least one。Is by Markov's inequality。

 well that's the probability that you're a million times bigger than your expectation。

So that's that's rare right that's going to happen to probability at most one in a million。so。Now。

 what's the probability that？Okay， again， let's look at now the L2 squared mass from the non heavyers。

So what's the problem of the sun？Over J in tail K。TLk means not thatviators not in the top K。Of。嗯。

Xj squared。诶。Inm write it like this。So I'm only going to keep track of the L2 squared mass that collided with I under the hash function。

 so xj squared。Times， I'll say indicator random variable。For the event that。H of I equals H of J。ok。

So this summation just means how much squared mass from the non heavy hitters？

Is with colliding with I in its bucket。So you expect this thing to be at most X k squared over Q。😡。

Which is like。What over a million times Xle squared over。呃。What over a million okay， so yeah。

 so what's the problem that this is bigger than let's say I don't know。嗯。1。

Times its expectation where its expectation is at most。Exhale。X toL K L2 norm squared。嗯。Over Q。

This is at less than one over 10， this is just Markov's inequality。By the way， this was also mark。

And this just by definition， is equal to one over 10 to the fifth。Times Xta k squared over k。行。

So with the probability that。The problem is that you're not isolated。

From all the other heavy hits is one over a million。

The probability that there's too much light mass in your bucket is at most one over 10。

If these two events， if neither of these two events happen， you will be super heavy。Right， because。

By definition， if you're a heavy hitter。You are bigger than whatever k times XT k squared。

And I'm saying that the remaining light mass， the noise in your bucket is over with high probability。

 only a one over 100，000 times smaller than that。Does that make sense？So。嗯。So actually。

 let me write it like this。If this had said not isolated。Then this would be。

Less than one of a million。Okay。And。If neither event happens。Then I is super heavy。

And the probability of neither happening。The probability that one of them does happen， let's say。

Is that most one over 10 plus one over 10 to the six， which is like much less than one， right？

So that means with high probability， with probability pretty close to one。

Any fixed heavy hitter will be super heavy in his bucket。And if he's super heavy in his bucket。

 you will find him with probability 99%。Because your failure probability over here。

Is at most one tap？So overall， what this means is。The like for any heavy hitter。

If you look at the bucket where he landed， he will be reported with probability at least， you know。

 70% or something like that。Okay， so that's that's a start that's but that's not exactly what we want right to solve heavy hitters doesn't just mean that each individual heavy hitter is founded probably 70% we really want to find all of them。

With with good probability， not just one， but all there could be k of them we want to find all k of them。

😡，So how do you get that done？And that's also kind of a simple trick。

What you do is you just repeat repeat this picture。

Many times and then do kind of a turn off a union down， so let me just write it down。so。对。

So we're going to repeat this， let's call it R， which is。Theta log k times。And each one of these。

 you know， this is like let's call it D11 D12 up to D1q。D21， D22， up to DT， QQ， et cetera。

This is D R1。And to D，RQ。And then each one has its own hash function， H one。Which maps n into Q。

All the way down to HR。Wch maps and into queue。行。And then I'll return。Return as our list。

Of heavy hits。L， which is defined to be。Instead of all I， such that。I is returned。By at least。

Let's say。Are over to。DIJ， D， I'm already using I。These。So that's the reduction。First of all。

 if you just remember the promise， you know， what does it mean to solve heavy hitters。

 it means with good problem， it means a， your output list has size at most O of K。😡，And B。

With high probability。You do not have any false negatives， meaning if someone is a heavy hitter。

 they will be included in the output list， you're not allowed to miss anyone。Okay。

 so this L has size O of K by construction。Right， why？

Because the number of D's in this grid is Q times R。😡，ok。

And you're only returning someone if they're returned by at least r over two of the data structures is D。

😡，While there areq times R of them， each guy you return consumes R over two of them。

So the number you can return is guaranteed to be at most2 Q。

So L is guaranteed to be at most2q in size， which is O of K。So that's good。Now。

 what about the other thing， which is you're not allowed to have false negatives？Well。

 look at a heavy hitter。What we argued on the last slide is。

If you look at where he lands in the first row。You know， with high probability， with probability 70%。

That data structure will return him。ok。😊，So now， you know， what's the expected number so again。

 also that's true of the second row as well， look in the second row。

 the data structure he hash there he hased to there， with 70% probability。

 that data structure will return him as well。😡，收。The expected number of data structures that return him。

Is going to be something like at least。Seven tenth times R because seven tenths of the rose will return him。

得几。So what's the probability that he's returned in less than five tenths of the rows？Well。

 that's a deviation from the expectation by something by like2 R over 10。

Right and the probability of that happening by the turn off bound is exponentially small in R。😡。

We chose R to be log K， theta log K， so that means the probability that you fail to return that heavy hitter is one over polyK。

😡，So by union bound over all the heavy hitters， they're only k of them。嗯。

You will not have any false negatives with high probability。Okay。Now again here。

 you have Q times R data structures that you're instantiating， Q is O of k， R is o of log K。

 so you have O of K log K data structures。😡，And you also have R hash functions。

 but each one of those is pairwise independent and each one only consumes a constant number of words of memory。

 so using O of log K words of memory for the H's and then an additional O of K log K times S memory。

For the K log K copies of this data structure。So that's where the K log k times S comes from。对。

So any questions about that before we actually then now。Show the main event。

 namely how do you actually implement this data structure in constant memory？Okay， so I guess。

People seem to be okay or at least no one is speaking up， so I'll assume that people are okay。

So that's it for the reduction。So， now。Will show。S is a constant。That can be achieved。

And this is where we're going to use our new knowledge of Dudley's inequality and bounding the supremo of stochastic processes and Raabva processes。

是。嗯。So here's the idea。And I should say in the reduction， you know。

 like there are some buckets that might not have any super heavy item in them。

But we don't care if there's no super heavy item， we allow the data structure to return whatever it wants。

 it doesn't affect the correctness argument from the previous whiteboard。

So let'll just assume that there is one because if there isn't one。

 we can do whatever we want anyway。So， there's some。Super heavy。I'll call it H。

 which is a number between1 and n。And I can write ancient binary， right？So this is H0。

And our goal here is going to be to learn the bits of H1 by one。😡，So we're going to learn H。

We'll learn。HJ，1 bit at a time。Or we'll learn H1 bit at that time。

So first I'm going to say alemma and thislemma is really the heart of the argument。

And we're going to spend some time proving alema。那来吧。喂。hy之。你呃。Via， you know， histogram。The state。

Of the。Underly。Frequency vector。At time T。Let kind of so we're going to look at。I got that y is0 y1。

Why capital T。The evolution。Of why。Over time。In an insertion only stream。

So what does it mean for a frequency vector to evolve according to an insertionally stream？

It means that if you look at two adjacent time steps like y5 and y6。

The only way they can differ is that y6 has one more in one of its entries right you saw an item in the stream。

😡，You incremented that items coordinate by one。😡，So the difference between Yt and yt minus1 for NT is some standard basis vector。

Okay。I don't know if this is clear or not， this word here says evolution be the evolution maybe a handwriting kind of site。

Now， what。Sigma 1 up to sigma n。B。F y is independent。Independent plus minus1 random variables。Then。

If you look at the expectation of the soup over all time。

Of the absolute value of the dot product of Sigma with Yt。This is at most up to a constant factor。

The L2 norm。Have the final  vector。嗯。so。I want to spend just a little bit of time。

Helping you digest what this means before we use it。But I mean， we do know， we do know the following。

 right？So this is what I said， I said。The expectation of soup of time。小米达位置。

Is it most the final norm？So that's the main claim where the signs are only fourYs independent。Now。

 if forget about the soup， what is the expectation of just like sigma dot Z？哎，那是他说这什没写。

My khi Schwartz。Right this is just。The sum of Singma I Zi。By Kohi Schwartz， this is at most。

The expectation of。That thing squared。Square root。And if you do that。

You're going to basically have like the sum of all Ij of Z I， Zj， Sigma I sigma J。Again。

 the off diagonal terms， expectation of Sigma I times expectation of sigma J is zero。

The only thing that survives。Are the diagonal terms。

 and you're going to be left with some of her eye of Z I squd。And then you have a square root。

 so this is just equal to the L2 of Z。So if you look at any individual dot product。

The expectation of that dot product is at most the norm of the vector。

But this is not just talking about the expectation of one dot product and sometimes talking about the expectation of the max of all the dot products。

😡，Imagine that they were not random signs， but they were Gausians。What I'm going to talk about。

 by the way， will hold for Gaussians too， but imagine that they were Gaussians。

So if you have one Gaussian， if you have not just one Gaussian， but a lot of Gaussians。

 capital T Gausians and you take the max of them。What do you expect what's going to happen in expectation？

You're going to have an extra factor of the square root of law capital T， just by a union bound。

You're going to want a union bound over all time steps。

That's going to make you pay square root log capital T。

And you can get the same kind you can do the same kind of reasoning for any sub Gaussian distribution。

 including Raammaers。So the thing that would have been the thing that would have been just basically obvious from a union bound would be if I had an extra square root log T here。

That would be obvious from a union band。But what the dilemma is saying is that you actually don't need to pay that square root log D factor。

So that's the significance。That's the significance of this lemma。

 the fact that you don' need to you don't need to pay anything to do a union bound。

Right you just have a constant out front， so it's as if it's as if there was just a single random of variable there。

 you paid absolutely nothing。To be able to say that all capital T of them are small simultaneously。

An example。Is what if your stream？Stream was one， two， three， four， five， et cetera。

What does that mean in terms of the Y's， that means that y0 is the zero vector。

Yhy1 would be1 comma 0。Y2 would be1 comma 1 comma0。s啊。So if you look at。So if you look at sigma。t y。

Right。Sigma。y1 is well， it's going to be sigma 1。So sigma kind of sigma dot Yt。

Is going to be equal to the sum J goes from1 to T of sigma J。So that means that， you know。

 for the first t minus one steps。You were， you know， imagine that when you start。

 you start at the origin， you're a person standing on the the on the number line initially you're standing at the origin。

Now you see Sigma one， that means you'll either walk left one step or you'll walk right one step if it's minus1 or one。

😡，Okay， now you're where you are， now you see sigma two。

 that's going to make you also walk left one step or right one step。😡，So after Sigma。

y T is basically your position at time T after doing a random walk on the line for little T steps。😡。

This is equal to the position。After T steps。Of random walk。On the integers。Starting from the origin。

谁。And kind of lovevy's maximal inequality。Saize。The expectation wall over the random choices in your walk。

诶。The max。Absolute value。Of any position reached。Is at most some constant time square root of T？

Which， by the way。Is just equal to the L of y capital T。

So I don't know some of you may have heard of levie's maximum equality or not。

 I mean it's something that is usually taught in。I don't know if it'll be taught in like the very first probability class you take。

 but if you take enough probability classes， you'll see it at some point it's kind of a standard。

Thing that people study in probability， these max inequalities。

And kind of thellmma generalizes just by out of curiosity in the chat。

 anyone who's heard of Levy's maximum inequality or maybe you didn't know the name。

But anyone who's heard of this fact that。If you do a random walk on the line。

You're kind of your maximum absolute value is bounded。

 you basically always stay in a pretty small interval between minus over t and over t。

So I'm curious anyone who's heard of that just write it in the chat， okay， so at least one person。

So this lemma is a generalization of Levy's maximal inequality in two ways。Right， what is that。

It works for an arbitrary evolution。Of of an insertion only stream， not just the stream one， two。

 three， four， five， but any insertion only stream。That's one way it generalizes levy's max inequality。

 Maybe the more surprising way it generalizes it is that。Kind of the typical proofs。

 There's this like reflection principle proof of leviees。

 The typical proofs very crucially use the fact。That。Your decisions。

 your random decisions over the time steps are independent of each other what you decide to do in time T is independent of everything you did in the past。

That's not true for our Lama。 Our Lama says that these sigmas are only fourwise independent。Right。

Um so。Already this lemma says that love's maximumimal inequality holds。

 even if your increments are only fourY independent。And I should mention。

Maybe a little advertisement for this course。Three wises。Independence doesn't suffice。Ohoops。

And that was due to naion。In 2019。And that was actually。He actually， you know。

 he took a previous version of this course。In 2018。And。This was not his final project。

 but you know he worked on it after the class was over and managed to show that the fact that we the fact that we use fourwise independence in our proof is really necessary。

 he showed that well first way he showed was that two wise independent doesn't work he constructed a two wise independent distribution for which thislemma fails。

And then after he did that， he later generalized his idea and showed that even three wise independence doesn't work three wise independence also fails。

 you really need four wise independence I mean it doesn't really matter for us the only reason you're going to see in the design of the algorithm。

The only reason I want to get away with fourY independence is because I can store a fourY independent hash function in a constant number of words of memory。

But that's also true for8 wise independence， It's also true for 42 wise independence as long as I'm using constant wise independence。

 it doesn't really matter whether it's 2，3，4 or 50 okay。

 but it just turns out that four works and four。Why is what true。

 the fact that four wise independence uses a constant number of words of memory？

So I think in the past， is that the question？Yeah。So earlier when we talked about KY independence。

 we said。You can like if you have a K if you have a bunch of KY independent bits and there are n of them。

You can generate them using K log n bits of memory， but for me。

 a machine word can hold log n bits sorry， I didn't say that explicitly when I say machine word。

I'm assuming that the machine word can store login bits。So K log n bits is O of K words。

 so if k is a constant， o of k is o of one。Does that make sense？Yeah。

 I didnt that machine word was like long end。Right， yeah， sorry I didn't I never。

I never said that explicitly。Okay， so good so now let's try to let's try to develop the algorithm using this lemma。

So as I already mentioned。We're going to try to learn。H， bit by bit。So you know， how do we learn a0？

So learning age zero。What I'm going to do is I'm going to draw。singer one sing n。

Each one is a random side。From a four wise independent family。We an instantiate just two counters。

And let's also say。Let's say we know the stream length。We know the stream length。Hello。

And we also know。The frequency。Of H。At time now。Okay， these assumptions can be removed。Of course。

 we don't necessarily know these things。But essentially two counters， not counters。Of course。

 we don't know the final frequency of H。But it's just going to be easier to explain how the algorithm works if we did know that。

 and then I'll talk about how to remove that assumption so that you don't need to assume that。

But for now， let's assume we know it。Okay， I'm going to instantiate two counters。

 let's call these counters。B0 and B1。And let's say I see I in I going so I see eye in the stream。

I looks like 0，0，1，1，1，0，1，0，1，1，1，0，1。And you know this this is bit number zero。

 this is bit number one， this is bit number two， this is bit number three。

 all'll the way up to log in。I'm trying to learn the zero bit， right？So I see eye in the stream。

And I is a one。I mean， the zero bit is a one。So what I'm going to do is I'm going to update B1。

Because because it ends into a1 I'm going to update B1 and what I'm going to do is let's say I'm going to add Sigma I here。

That's it。That's how I process and update in the stream， okay？I just when I see eye in the stream。

 I look at its last bit in binary at's zero bit and。😡，I update the corresponding counter by Sigma I。

That's it of course this is all part of a larger reduction right if I'm actually trying to solve heavy hitters。

😡，You know I remember I had these I had these log K different rows。

 each one had a you know two different data structures that solves heavy hitters so in actuality and the actual heavy hitters algorithm overall。

Um，I'm going， I'm going to hash， I log k different times。

 each hash is going to send it to a random super heavy data structure。

Each super heavyav data structure is storing its own。😡。

Sigma vector drawn from a fourY independent family。

 and then I'm going to do this picture inside of each one of those data sourcess。

So now let's just think， so let's say just for the sake of illustration。Illustration。Say that。

80 is one。That implies that B1 is equal to sig H。Times x H0 times x H plus。

The sum overall J not equal to H。Such that J is also odd。Of Sigma J Xj。And B0 is equal to。

The sum overall J even。Of S J X J。And I want to focus your attention。On these two sums。Now。

 I claim that we can say something about these sums based on ourlemma。RightThis is ourlum up here。

What can we say？嗯。We can say that， you know， I can define now， let me define two different。

Let me define two different vectors， y and y prime。喂。Is the frequency vector？Projected。

Plus act basically。X。Projected。On to。嗯。All Aj。Which are not equal to H。

And y prime is equal to x projected。To all the even Jays。And the Loma says。

So the Luma has talk about the expectation， right？The expectation of the largest dot product you'll ever see。

😡，But if the expectation is small。Then that means it's going to be small with good probability by Markov's inequality。

 right？If you say that there's random variable and expectation is at most bh。

 the probability that it's bigger than five times bh is at most a fifth， for example。😡。

Or 10 times bla is that most1。So thelemma implies。That。TheseThese two red boxes。Is that this red box。

 the first red box， let's call these one and two。So red box one is at most。嗯。

Y at the end of the stream， YL， which is at the end of the stream。And the second box is at most。

Why prime now？不的是。Kind of with high probability， like let's say， at least， you know。

 80% or something。Let's say 90%。But now recall that。What do we know about x， about H。

 H is super heavy。Which means at the end of the stream。The Lco of x at the end of the stream。

Is equal to。X， HL。Squared。Plus。YL。Eltonor squared， plus。Y prime L。Hel squared， right？

The l pseudo norm squared of x is just the subover coordinates ofxii squared。So in particular。

 it's H plus the odd things， excluding H plus the even things。😡，Right。😊。

And what do we know about superheaviness？This。Is almost everything。唔仔。Does that make sense？

That thing that I circled XH squared。Is like a thousand times bigger than the other two things。唔几。

Which means that， you know， if you just take the square root， Xh， Xh and magnitude。Is way， way。

 way bigger than the L2 norm of Y at T L。And it's also way bigger than the Ltum of Y prime at T mill。

So these two numbers here。Are tiny。Compared。To X H time。对。So going to again。This is big。In magnitude。

And this is tiny at timeel。And this is tiny。It's not just tiny， okay， so this is tiny always。

That's why thelemma， it's not just tiny at time L， it's always tiny right thelemma says that over time steps are always tiny。

😡，This is always time。And this is big in magnitude。Big meaning much bigger than tiny。As soon as。

We've seen。At least。one tenth。Of。The total occurrences。Which。嚟。XH in an L2 sense。

 XH is like super duper huge at time L compared to the other two things。So， you know。

 even if you've only seen like。XH over 10 of his occurrences。

 he's still pretty super duper heavy compared to the other two things。Okay。And remember。

 we're assuming that。We know X at time L， know X H that we know X H at time L。Okay。

 so here's what I'm going to do。I'm going to wait。So I'm monitoring these two counters， B0 and B1。

 right？I'm going to wait until one of them。Is at least。So let's call this threshold deelta。

Delta is equal to。X HL。I'm going to wait。Until at least。Okay， I'm going to wait until some counter。

1 of B 0。B1 is at least Delta over 10。Inmail two。Nationally if feel like this。

Dels over 11 does't really matter。Now。The claim is that。Once we've seen。At least。嗯。

Delta over 10 occurrences。Of X H of H。In stream。诶要 b one。Will be at least Delta over 11。

With large probability。Does that make sense and you know why is that and the other claim is that。

Be 0。Is going to be less than Delta over 11， always。So this is just dilemma。

Thellma says that B0 is always at most y prime L2 norm。But that's way less than Delta。

 it's way less than Delta over 11。So。So the lumma directly implies that with the lumma combined with Markovs inequality implies that with really good probability。

 B0 will never be big， B0 will always be small。😡，对。Furthermore， thellma says， look。

 at the time when we've seen the deelta over 10th occurrence of H。B1 will be large。Why。

 because it's a large thing。Plus， the very small thing。Okay， and yes。

 the small thing might have an opposite sign and cancel a bit might cancel a little bit of the large thing。

But the large thing is so large compared to the small thing that even if you cancel a little bit of it。

It's not enough to push it， you know， it used to be deelta over 10。

 it's so small that it's not going to push it below deelta over 11。Okay。Does that make sense？

So that's where the lemma is fitting into this argument。

 the lemma is fitting into this argument to say that these two things。That I putarrows on。

Are always small and they're never going to confuse you。

You're never going to think that the wrong thing is big or you know it's very unlikely that you think the wrong thing is big。

 it's very unlikely that you think the big thing is small。ok。😊，Does that make sense？Yeah。Okay。

 now there's a okay， so we're all we're getting there， I haven't actually proved alumma yet。

 we're getting there。How do you actually how do you actually？

How do you actually finish this off well the problem is I did all of this to learn one bit of H。😡。

Okay， I consumed 10% of the occurrences of H。In order to learn one bit of H。

How many times can I consume 10% of the occurrences of H， well at most 10 times。

 because H only occurs 100% of its time， right？So that means that if I try to do this kind of argument。

 I could only hope to learn 10 bits of H， but H doesn't have 10 bits， it has log end bits。😡。

So how can I learn all login bits？Can only hope to learn。10 bits。Have H via such an argument。

How can I learn？All log ins。So here we go， here's the intuition。Okay， this is not， of course。

 necessarily true because we're doing worst case analysis。

 but let's say that we're promised that the mass of the vector is randomly spread around。Okay。

 like someone came and just randomly permuted， they， you know。

 they randomly permuted the indices of the universe before putting it in the stream。Okay。Now。

 let's say we've learned the first five bits of H。H0 to H4 are， you know，01，1，01， whatever it is。Now。

 that means that from now on， now we're trying to learn the next bit， the sixth bit。From now on。

 whenever we see an item in the stream。😡，If that item does not end in and I should say like when youre when after you' learned the zero bit and you're trying to learn the next bit。

 what you're going to do is you're going to draw you're going to zero out the two counters be0 and B1 and you're going to kind of start from the beginning again。

😡，Not from the beginning of the stream， but just you're going to restart the counters to zero and just keep going from where you are in the stream。

😡，Okay。UmNow， what was I saying？I was saying that。If you know， if you know that H ends in 01101。

And now you're trying to learn the sixth bit whenever you see an item in the stream。😡。

If that item does not end in 01，1，01。You should not process it， you should just ignore it， why。

 because if it doesn't end in 01101， you know that it's not H。

Conition on the fact that everything you've done so far is correct， you know that thing is not H。

So by processing it and updating one of the counters。

 all you're doing is you're contributing to the noise， right these two red boxes。

 you're contributing to one of those noise boxes。😡，And like noise can only hurt you。

 noise can only trick you into thinking that something is big and it's not big。so just don't do it。

 just ignore this and move on to the next item in the stream。😡，What's the advantage of that？

The advantage of that is。The fraction of the noise that survives。

Is only a one over two to the fifth power now， because， you know。

 if mass is randomly spread around in the vector because he randomly permuted the mass。

The fraction of mass that ends in 01101 is a one over two to the five fraction of the mass。

Which means that。The noise is cut by a factor of one over two of the five。Okay。

 so in terms of the survivors， H definitely survived。And what else survived。

 a one over 32 fraction of the noise survived。So H used to be a thousand times bigger than everyone else。

 guess what， now he's 32，000 times bigger than everyone else。

Because the everyone else only includes the people who end in 01101。

And that's only a one over 32th fraction of the mass before。

Right so he became even more super heavy than it was before。

 so when you're trying to learn the K bit， he's not just a thousand times bigger than everyone that's remaining。

 he's two to the K times a thousand times bigger than everyone remaining。😡，Okay， which means。

Basically what it means， you if you kind of think about it for a little bit。

 what it means is you don't really need to consume 10% of his occurrences to learn his next bit。

You can get away with consuming something like 5% of his occurrences。Okay。

 and then the next time you're trying to learn a bit。

 instead of having to wait for 5% of his occurrences， you only have to wait for 2。

5% of his occurrences。So when you add up how many of its occurrences you consume before you learn all of his bits。

You know， it adds up to less than 100%。It's a convergent sum， it's a geometric sum。Okay。

 so you will be able to learn all of his bits before the stream ends。

So that's the basic idea now of course the mask is not randomly spread around。

 so how do you fix this the way you fix it is。You know we didn't really talk about it。

 we talked about two Is independent hash functions。

 there's also such a thing as two I's independent permutations。

 so you can pick a pseudoran permutation that's random enough that it makes this argument go through。

😡，Okay， so let me not get into that because we only have seven minutes left。But that's the idea。Yeah。

So and then now only the things that remain are a， how do you prove the dilemma？And B。

 made these I made this assumption that you know I made this assumption that you know Delta， right？

I said that you know the final value of XH at the end of the stream。

 but you don't actually know that。So how do you fix that？Problem。You don't know。

The final value of XHL。So， you know， we had this threshold where we wait until one of the counters is Delta over 11。

 but we don't know Delta。So the fix。Is to observe that。First of all， XHL。

Is roughly the same as XL L2 norm because it's super heavy。So we just need to know this。

And we don't even need to know it exactly， we just need to know it up to a factor of two。

That turns out to be good enough to make the whole argument work， okay。

 but we don't know that either。So what do we do？We run an AS sketch on the side。ok， so。

I should look write this。We just in parallel。That the final value， so let's call this alpha。

We guess that alpha is equal to。To the zero to the one。Up to like two to them， let's say 10。

 we make 11 parallel 11， some constant parallel guesses for alpha。And then in parallel。

 we run this entire algorithm that I just told you for super heavyav。

 we run it assuming that Delta is alpha。唔使。And then also in parallel。We run the AmS sketch。Okay。

 so now what's happening。So we're running all these parallel guesses。For alpha， and for each one。

 we're running the algorithm assuming that Dlta is alpha。We're also going to run an AmS sketch。

 if you don't remember the MS sketch it approximates the L2 norm。😡，Okay， now， you know。

 the sloppy thing to do would be make the As sketch， you know。

 boot it up with a failure probability that's so small that we that we can union bound and say that the As sketch never fails throughout the stream。

And then in every time step we can ask the MS sketch what's the L2 norm now， what's the L2 norm now。

 what's the L2 norm now and at some point it's going to say oh well it's the L2 norm now is like roughly six and they're like oh it's six that means that our guesses our guesses of alpha being two to the zero。

 two to the one and two to the two are off it's roughly two to the three are bigger。😡。

So let's just kill our parallel instantiations that guess two to the zero and two to the one and two to the two。

 and let's boot up another parallel instantiation that guesses that it's two to the 11。Okay。

 now that new parallel instantiation that gets through of the 11。Is it missed a prefix of the stream。

 it missed the first part of the stream， however。The first part of the stream had at most two to the two mass in it。

 which is way smaller than two to the 11。So if the right answer actually ends up being two to the 11 or larger。

The mass we missed is insignificant compared to the final number of occurrences of XH anyway。

Of H anyway， so we didn't miss much。Okay， so that's the idea we basically we're always gonna run 10 or 11 parallel guesses and then once in a while we're gonna kill the really small guesses once we know they're wrong and we're gonna boot up a parallel instantiation that has a larger guess Now what about item3 I said that we're gonna keep asking the A a sketch every time step what is it now what is it now what is it now the naive way of making this work is to make the failure probability be really small so we can union bound over all these time steps The problem with that is if your failure probability is delta。

 you pay a log one over delta in your number of words of memory I don't want log one over delta words of memory Delta is going end up being something like one over the stream length So I'm going to pay log the stream length in terms of my memory bound I don't want log stream length I want constant memory。

So then what you do is。You that lumma that I showed you。

 which is based on supremo stochastic processes。You prove a similar dilemma applied to the AS sketch。

😡，You prove that if you run the Ams sketch at every time step， you query at every time step。嗯。

The maximum error will ever give you。With high probability is big O of epsilon times the L2 of the final vector。

So you don't need to pay to union Bo overall all time steps。It's sort of。

 it's sort of like the lemma again for free， like for free。

 your maximum error is never larger than epsilon times the largest altune born。Okay。

So that's how to fix the algorithm now the only thing that's left is how to prove thelemma。Okay。

 so any questions， I think we only have two minutes left。

 so I'll be able to sketch how to prove dilemma。And I'll either finish it off on Monday or put it in the notes。

Okay， but any questions before we now talk about thelemma？

So this said that the expectation of a stigma of the soup overall time steps。Of sigma dot Y t。

Is that most？Why capital T elsewheremore。Okay， so。First of all so you know because I have so little time left I just want you to see the idea in lecture and then maybe I'll put the the details the full details in the lecture notes。

 but what's the idea let's look at the special case。Where the stream is。1，2， three。

 four5 so that means that yt is 11100 t times and let me define Vt to be yt over the square root of capital t which implies that for all time steps。

VT has normal atless one。行。And let me define now。You know， A is equal to the set of Vt。

Overall time steps。So we want to show that the expectation of a sigma of the soup over x and a of sigma dot x。

Is basically a constant， that's what we really want to show。

This is exactly what we talked about before on Monday。

 this is the supreme of a Raammara process which you know it Raammacker has satisfied the kin inequality just like Gaussian so everything I talked about last time applies Dudley still holds。

😡，Deelly still holes， generic chaining， all that still works。冇知。

So we know that the expectation over sigma of the suit over x and A。Of Sigma do X。

Is at most the sum over all r from1 to infinity of1 over2 to the r at times square root log of the covering number of a with respect to the altud norm1 over2 to the R。

So the name of the game really is just understanding how big is an epsilon net of A。

So an excellent N of A。Just notice that if you look at some V at time A minus v at time B。😡。

This is going to be some vector that looks like。It's going to have a bunch of zeros here。

 it's going to have some ones， it's going to have some zeros。

And then there's a division by root T and you're taking the L2 number of that。

How many ones do you have here？And let me just say it， it's a minus B。

So this is equal to a minus B over root T。So a claim。Is that if you take an epsilon out of a。

 with respect to the L2 norm。Does at most want of uppsilon squared？Why is that？

The proof is just take。Just take the following net。V at time zero， via at time epsilon square t。

 v at time two epsilon square t via at time you know。Vet time， you know， whatever it is。

Epsilon squared。I guess what， yeah， so at time one ofspson squared times uppsilon squared2。That's it。

 so many episodes were water something。So that's the proof。 and then now you just take that。

And you just plug it directly in there。And you get that the expected soup。

Is at most the sum of R from1 to infinity of1 over2 to the R times square root log water uppsilon squared so square root log。

Of。I guess two to the two are。2 to the R squared it is2 to the 2R。😡。

Which is at most the sum over R of root R over2 to the R， which is a constant。

So Dougie's inequality gives you exactly what you want。And okay， again， we're basically out of time。

 but let me just say the following thing。Okay。Now， how do you get this to work not just with full independence。

 but four wise independence because we only have four wise independent random signs？The point is。

 why did we have a square root log here？😡，We had a square root log。

Because sigma dot x decays like e to the minus lambda squared because of kin's inequality。

 and square root log is like the inverse function to e to the minus lambda squared。

But if we didn't if we didn't decay like e to the minus lambda squared。

 but instead we decayed like one over lambda into the eighth or something。Then instead of log。

 instead of log， you would have like。The one， you know。

 the raised to the  one/ eighth power function。You would have the covering number raised to the1/ eighth power。

😡，which is still enough to make this whole thing converge。

And if you really pay attention to what you need to make this whole thing converge。

It turns out that what you really need is。F wise independence。

 And if you have four wise independence， it'll converge。 you won't get root R over2 to the R。

 but you'll get some other thing that that shrinks fast enough that it converges。

So real it's all basically Ddley's inequality so any questions about this？

And if you want to extend this not just to a random walk on the integers。

 but arbitrary an arbitrary insertion only stream， you basically just need to prove that this claim still holds。

😡，Even under an arbitrary。Evolution of an insertionally streamed， but it does。

 you can show that and it's honestly not that much harder than this example。第1位。

So I think I'll stop recording now， if anyone has questions， please let me know。Professor。

 I have a question。I think for like the L1 version of this question problem。

 there' just just like the super majority voting algorithm right like why is the L version so much harder？



![](img/72a17577f9a09ef476ec153b43637476_2.png)

Like what fails when you just use like the majority voting algorithm？



![](img/72a17577f9a09ef476ec153b43637476_4.png)

You try to find。