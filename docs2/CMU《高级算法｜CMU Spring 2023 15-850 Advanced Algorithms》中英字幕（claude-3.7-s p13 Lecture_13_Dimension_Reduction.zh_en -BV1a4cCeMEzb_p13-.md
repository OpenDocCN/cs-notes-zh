# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p13 Lecture_13_Dimension_Reduction.zh_en -BV1a4cCeMEzb_p13-

So welcome back， everybody。ACouple of little things to mention。

 some of you asked for homework homework solutions。 we'll try to put out homework solutions。

 but you know it might take a couple days。At least so homework  one， then， you know。

 we'll go on from there。 There's， there's a couple of little bug fixes in problem 1。Of homework too。

 So if you are doing the low diameter decomposition problem， there are a couple of bug fixes。

 I'll post something on piazza later today。嗯。But on that。

 hopefully people are doing well with their homework。啊。对。Good， so。Let's any questions。

 do people have。Doubts， questions。Yeah， okay。Good， so let's continue。 So we're going to talk about。

So the last time we talked about dimension reduction a little bit， at least we。

Began talking about dimension reduction。 we talked about turn of pounds and I said well dimension reduction is at least distance preserving dimension reductions。

 what is known as the Johnson Lyndon Strauus transform or the Johnson Lynden Straus Lama is actually just a turn of pound。

 so I wanted to illustrate that but I wanted to also show you how once you've proved such a result。

 you can get other interesting。Other interesting algorithmic ideas almost for free。

 somewhat surprisingly， so Ill try to tell you about one of those ideas which I find you know pretty impressive it is known as compressive sensing。

😊，And it's this idea that if you have a sparse signal。

 you can recover it using very few measurements。And so so this idea will elaborate on this whats the spa signal。

 what's measurement etc cetera and I'll talk about that this idea by the way。

 it came out of math and。And this is sort of an interplay between math and CS and WE and you'll see the you know the applications are actually quite surprising。

 maybe I'll talk about that a little bit。 this is a slight digression from where I was thinking of going but you know it doesn't really matter right。

The journey is the point。So okay。So let's very quickly remind ourselves where we were。

 we were talking about the Johnson Lynden Straus lelemma and it said， well。

 if I gave you end points in D dimensions think of D as very large。😊，Then， you know。

 think of this as like a million points。A billion points， if you wish， in a million dimensions。

So that's a lot of dimensions， a lot of points。Then there exists a map going from a million dimensions down to。

Log of a billion。Over E Silon squared。 There's some constant sitting here。

 So we have to worry about that。Such that all distances are preserved。Okay。

 and all listens are preserved up to this one plus minus epsilon factor。Now。

 one thing to mention is this is very different from singular value decompositions which preserve in some sense the energy of the system。

 if we have time we'll do a lecture on SVDs but we'll see how it goes。😊。

But this is maintaining all pairwise distances。嗯。So this is this is the this is the theorem。

 and essentially I'll outline the proof。 I won't do the algebraic details because as I've said。

 you know， doing the details of one turn of pound on the board is enough the rest of you， you know。

 you can figure out the details yourself， but I'll tell you the main steps。😊。

And the construction was surprisingly simple。 We said， look， this by the way。

 this is just an existential statement。 There exists a map。

 I haven't told you anything about how to construct it and the algorithm is going to be。

 it's going to be a randomized algorithm and it's going to be this algorithm that ticks this matrix where the matrix all matrix entries。

😊，This is a， this is a fact matrix with。B columns。K roads。

Every entry of this is an independent Gaussian。And your map is really。

Just hitting x with this matrix M and then recal it down by one over square root k。

And that's just this linear map。And the sort of main claim is going to be that for any fixed unit vector x。

啊。The probability that its length is not maintained。And you know， for technical reasons。

 I'll work with length squared。😊，YeahThe sort of big O is very forgiving out here。 so I can。

 especially if that's long is small。 So I don't need to worry about length versus length square。

So if I look at the length squared of this vector x。

 it is going to be preserved with fairly high probability。😊，So if I have this lemma。

 then I can apply it to all the pairwise differences。Suitably scanned。This map is linear。

 so if I can apply it to x minus X minus x J renormalize， it applies to X minus x J。

 and we go on from there。So from once you have this claim。

 the Johnson Lyn Straulemma follows by a union bond。

And so the whole whole the onus is now to prove this lemma。And this lemma is okay。

 So we we'll give the main idea behind proving this module or some details。Good。By the way。

 you know this what I've done out here is I just pulled out a matrix from nowhere。

 I just populated with with Gaussians and I made a claim about this。😊，And you might ask， well。

 how do you come up with this matrix， Why would you think of this matrix。

So here is one one one thing that you could think about。 So let me give the intuition first。

 which is perhaps more important than the just the details of that proof。

Consider the following thing。What I want to do。If I want to take these points， you know。

 these points are sitting around in some massive dimensional space。I want to project these down。

Onto a random K dimensional subspace。From the set of all possible K dimensional subspaces。

 I want to choose one uniformly random。 and I want to project all these points down onto this K dimensional subspace。

😊，And that's more or less what what's happening out here。Okay。So let me let me do this in two steps。

How would I choose a random K dimensional subspace， by the way。呃，广红。

Pick a vector So so here is one way to do it。 Pick a basis， pick a random basis。😊，Pick a vector。

 pick another vector orthogonal to it， pick a third vector orthogonal to the first two。😊。

And each time， you know， condition on sort。 So the first vector was uniformly at random。

 The second vector was orthogonal to the first vector。And so on so forth。

That's one way of doing this。 Now， what that requires is， you know。

 first haveve picked the first vector， then have to condition on that and pick a second vector orthoal to it。

😊，So let me do the following thing let me observe that if I pick two vectors think of d as being large right we are only interested in the case where d is large if d were already kind of small smaller than k then I don't need to worry about this then the identity map is good enough。

😊，So here's what I'll do。 I'll pick a vector。And then I'll just pick another vector uniformly random。

 So two uniformly random。vectors。And I want to claim that this will be almost your talking。why。

So let's just very quickly do a little back of the envelope calculation。嗯。对。So so here's。

 here's the idea。So， you know， the first unit vector， see， I'm picking unit vectors。 let's say。

 So I pick the first unit vector。😊，And now， what I really want to do is I want to pick。A unit vector。

From the， from the orthogonal sub space。O。Ill say it is almost orthogonal if I picked it。😊。

From so that the inner product between these things is at most， let's say some w。Okay。So。

 I want to figure out。That， if I picked。1 vector。So if I picked my first vector。

How much of the surface of this sphere。Is almost orthogonal to this first factor。

Let let's call this V。I want to figure out how much， you know， it's。

 it's this band that's around the equator。I want to figure out how much of how wide is this band so that it contains。

 let's say，99% of this of the surface of this wave。Any guesses？This is a sphere in let's say。

 R capital B。How wide should I go。So that I contain 99% of the surface。I'm sorry。我走。

Almost all the way to the top。 So you know， your two dimensional intuition says if you want 99%。

 then I want to go like that。Here's the fact。If you want 99% of the surface of the sphere。

 the distance you have to go is something like order one over square root D。From the equator。

So when D is very large， you are hardly moving up from the equator。You take the equator。

 you go up a little bit， you go down a little bit and you make a band in this little bit of like order one over root。

And that contains 99% of the surface。So this intuition that you have from two dimensions is good for two dimensions。

 It is good for three as well。😊，But as B gets very large。Most of this fear is sitting on the。

On the equator。By the way， it's kind of weird。Because this was for a single vector， right。

So let's look at another vector。I me， pick my favorite vector。Another favorite vector。

 This was my first favorite vector。 My second favorite vector is， you know。

 perhaps pointing somewhere out there。😊，So 99% of the surface。 So the state lives。On a band。

Which is near the equator defined by this newde notion of north。No matter what direction I pick。

 I can define a band around its middle。And 99% of the mass is sitting out there。By the way。

 the same thing holds for a cube for a hyperc as well。You can take the hypercue。

This is the picture we usually draw the hypercue。And I can define the notion of equator。

 right all the vectors who is having weighted n over2。😊，Let's say it's an insal hyper tube。

And I can say， well， how far do you need to go from the equator？

Until you get 99% of the mass and you know， n over 2 plus minus square root。😊，Consantine square。

Basically， I'm saying。The set of all x's。In01。To the maybe I'll stick with B。

Such that the heming weight of x。In this case， it's just having weight of X lies in D over 2 plus minus order square V D。

This contain contains 9%，99% of the mass。Okay。So really， the， the cube。

 instead of drawing it like this， we should draw the cube like this。Most of the mice is sitting。

And they贵。嗯。嗯。By the way， there is。I'm not trying to sort of confuse the hell out of you。 actually。

 maybe I am trying to confuse No， but I'm basically saying your your your intuition。

 you should recalibrate it when you're talking about high dimensions。😊，Here's another fact。

 by the way。So， so this， okay， So， so let's go。Let let me tell you one one final fact about this here。

 Let's go back to this here。In fact， I'll go to the ball。Let's say。Or the sphere， you know。

 I'm just talking about all points at distance exactly one。

 And the ball is all points at distance at most one。And now， let me ask。How far do I need to go？ So。

 so now I'm talking about the the ball。The unit ball。 And I'm saying。

 how thick a shell do I need to take。So that it contains 99% of the volume。Inside。好呃。对。

On the on the surface， right？So it turns out you need to go out only1 over D。Okay。

 this one is particularly easy to see。😊，的的嗯。That the the amount of mass sitting out here goes something like R to the D -1。

This is， this is you know， this is the surface of the sphere of radius R。😊，And so。Basically。

 what's happening is that if I want 99%， then I basically need to say， you know。

 I need to integrate this over some some very small region。Towards the end。

 in order to get 99% of one。So， so this is like。1 minus epsilon to the D -1。

Which is something like e to the minus epsilon times b -1。喂。

So easier to think about like helps potentially grow the insight bulb， such a cover it。Sure。

 either way。So the point is most of the mass of this ball is near its surface。喂。Also。

 most of the mass of the ball， you know， you can do the same argument is near the equator。

And it's near every equator。So the ball， you know， in my， in my head。

 this sort of the picture of a high dimensional。Ball looks something like this。Somehow。

 a lot of the surface。😊，Must be。Must be concentrated at the equator。Yeah。

 I don't know if this picture helps。 but these are the facts that sort of are useful to remember。

 Maybe I'll remove this picture because it you know， confuses me as well。But。Let's pull back。

 What were we doing。We were trying to find a projection。So I wanted a subspace。

 I wanted an orthogonal basis。Basis， right， an orthogonal sub orthogonal set of vectors。I said。

 let's forget about this one thing。 Let's forget about orthogonality。 Let's pick a vector。

 Let's pick another independent vector。 Let's pick a third independent vector， and so on so forth。

I want to pick unit vectors because these are basis vectors。 How do I pick a unit unit vector。

I can pick a vector from the surface of the sphere。But another thing I can do is I can pick。

A whole bunch of。I can pick a spherly symmetric。😊，You know。

 a vector from some spherly symmetric distribution and renormalize。And one。

 my favorite sppherlylysymmetric distribution is the multivariate Gaussian。

 So this is the Gaussian in the first coordinate， Gaussian in the second coordinate。

 Gaussian in the D。😊，So here is how I am picking orthogonal vectors， nearly orthogonal vectors。

 I take the first orthogonal vector like this， renormalize。😊，I picked the second vector like this。

 Renormalize and so on and so forth。But then finally， I say， look。This guy is very concentrated。

 its length is very concentrated around one。So I don't even need to renormalize。

 Let me just put the first vector like this。Instead of renmalizing by its actual length。

 Ill renormalize by its expected。Actually， if I were renormalizing by its expected length。

 I would do square root D。😊，But then， you know， because Im multiplying x by a d by K matrix。

 I would I would have had to multiply by square root D over square root k。

 So this is why this one over square root k comes。😊，Don't worry about the the renormalization。

More or less， the basis I'm picking basis。The first vector is picked from this distribution。

The second vector is also picked from this distribution， and so on so。Those are exactly the。The。

 the rows of this matrix。 That's all I'm doing。有。So if if this was confusing， ignore all that。

 basically the first vector is my surrogate for a unit vector。😊，Suitably scaled。

 whatever unit vector vector。The second row is my surrogate for the second orthogonal vector。

AndMy third role is like this， and I just。That's exactly what this matrix is。 And then。

So that's how you should think of this as this is more or less a projection onto some K dimensional subspace。

😊，对。没不算的。It got to those。没。Out here， yeah。I觉得。I think I think this is the best you can do。

 I think both of these are the best you can do。O。各种。So this。

 you should just think of as projection onto a random k dimensional subspace。😊，The rest is recal。

Not important。Okay。And now the question is， what does the projection onto a random K dimensional subspace give you the lemma is this？

😊，And the process。Let me not do it。It is sort of nice， sunny dates。嗯。哦。

Too much algebra on the board puts me to sleep as well。How would you do it just， just， just to again。

 just， just。Like rule of thumb。 How do you argue about such。So here's， here's the fact you could use。

Look， I want to figure out what。M times x looks like。M。All the entries are Gaussians。So as we said。

 the first row is the Gaussian 1， Gaussian 2， Gaussian D multiplied by x 4 and x to x d。

 So the first entry of the answer。Is equal to summation over I going from1 to D。

Independent Gaussians， let me even write this。 This is， you know， not portionional maps。

 but this is exactly a Gaussian times X。And then we said， well， the sum of Gaussians， you know。

 if you multiply a Gaussian by X it becomes 0 X squared， some of that。It behaving like 0。

Some of the size squares。我就高兴。四万？So we said， oh， the first entry is the Gaussian， The second entry。

 the Gaussian， Every entry is the Gaussian。Okay。So this， this right hand， So1 over k。

Times M X is behaving like。Gussian1， Gaussian 2 up to Gaussian K。1 over schedule。哎。

I want to understand the length squared of this thing。What's the length squared of this thing。

The length squared of one of F of。With one over again。Sation da ice。Is distributed like this。O。😊，对。

Now I need to understand how this guy behaves。This is an average of a bunch of independent random variables。

Rpe for a turn of pound， please do。This， this call it Z。So you are asking。

 what's the probability that z is bigger than one plus epsilon times its mean， which is one。

Is less than equal to if equal to probability that e to the Tz is bigger than equal to E to the t1 plus epsilon。

For B greater than0， which is at most。Expectation of E to the T Z over E to the T1 plus epsilon。

 which is equal to a product of E to the。Expectations E to the PGI is squared G is or Gaussians。😊。

Over E to the P1 plus epsilon。You know how this goes。How this will end up。This will end up with。

 you know， this is。Moom in generating function。 You don't want to calculate if you're feeling sleepy today。

 It's nice and sunny outside。 You look up Wikipedia。 Wikipedia will tell you the MGF of this thing。

You plug it1。 you optimize。 you want to do algebra。 You don't feel like doing algebra。

 a wolf from alpha will allow you to do the algebra。Minimize this object。It'll tell you the answer。

 The answer will be that。It's just。可以。So you could use the Gaussian variance one by K。

 But remember youre summing up the squares of Gaussians。These are known as sky Square distributions。

 you remember that from when you took your probability class。

 you look it up on Wikipedia it tells you the MGs right away。You know。

 it's or you look up Wikipedia and you ask for squares of Gaussians。 You just， you know。

 just just type in squares of Gaussians into that Wikipedia page。

 You'll see it says sky Squared with a link out there。😊，不这。So in any case， you know， actually。

 Ryan has a very nice lecture note on street fighting mathematics， right。😊，The election video。

It's like we should know how to do this， but you know， we should do this only when we have。😊。

Save your time。Use the tools that you have， except when you are doing homework。 then please don't。

 you know， if you use tools that you shouldn't be using， please don't。Or otherwise。

 that you cite the tools that you are using。 I'm perfectly happy。😊，But， you know， it's just this。

 you know， there's nothing to it。对。Okay， so let me tell you， you know， a couple more things。

 by the way， So so this， and now you'll do the rest of the proof and you'll come up with this answer。

I'm not going to do it。But instead， I'll use this time to tell you a couple more interesting things about it。

对。嗯，对。大です。Put the line here。But。So this was the Johnson Lynden Straus slemma。

 the original Johnson Lynden Strauslemma said choose a K dimensional subspace。😊。

Then subsequent proofs simplified it。Then subsequent proofs simplified it even further。

 they said look。I want to do this in practice， with this matrix。

 you are asking me to put down Gaussians in every place。

 Gaussians are expensive to generate number of random bits is very large。 I don't like it。

What I want to do is I want to say MI J is going to be either minus1 plus one uniformly right now。

That's all I want to do。One week。Does this work？ And the answer is， yes， it does work。But now。

 the proofs require a little more care。You have to do the concentration bounds because， you know。

 these kind of things， these arguments that we were doing O Xi times Gaussian summed up behave like another Gaussian this is not quite true。

😊，You have to deal with these random variables。So there were direct proofs of this thing。

So there's direct proofs。And again。It's。It's completely doable。 You just sit down and you do it。

One afternoon， you know， a colder afternoon， you do it， you can do it。

But then other people noticed that actually you can use。

So what what can you do you can actually both generalize this and simplify the proofs at some level。

Simplify as in you're using one machinery。 So you can simplify that way。 So you say， well。

 M I J is going to be an independent。Sub Gaussian。不在个北。

A subgaussian rhino variable is exactly what you think it is。

 Its tails should go faster than a Gaussian。😊，As in tail should go down faster than Nado。

So these should be random variables where you say the probability that x is bigger than some T is less than equal to e to the minus t squared over two sigma squared。

😊，This is the Gaussian。You want to be subgosian。这标签。Exactly。

 so so now it will really depend on what this sigma is。

That will play a role in how many roads you need to take and stuff like this。By the way。

 a subgaussian， since I have already defined the terminology， I can tell you。

 here is one way of defining another equivalent way of defining a subgaussian。

 You remember our friend the。😊，The log MGf。The log M。Of。A Gaussian。Behaves like。

 so the log MF of A Gaussian is。P squared sigma squared over 2。

 let's say it's the zero mean you know variance sigma squared Gaussian。对。

For for a random variable to be subgaussian， you want it to be。And in your lecture notes。

 I just added in some， some comments on how you can quickly from this infer things about subcasians。

So it's a powerful language。 if you are interested in probability theory。

 it's a powerful language if you are not， you know， you can ignore those sections， not not important。

😊，But basically， whenever you see a Gaussian being used， you should think， oh。

 can I use the sub Gaussian rhino ver？Oh， good thing。 by the way， A Gaussian is sub Gaussian。

Another good thing。These random variables， you know， plus -1 random variables。All finite ones。

 but in particular these guys are very nicely， you know， it is like one subgaussing。😊，One。

 one subgaussian being， know， the sigma quite behave like one。Very nice。就。

Just the extension to subgaussian immediately applies to these random variables。

 which are often known as， you know， we need a name for these things。

 These are known as Radi mark random variables。😊，01 are， but only Gaussian or whatever。

 So these are r markers。M chair。Why use two syllables and three suffices。But but anyway。

So you can use this this phenomenon。Okay， so， so what would I think， Okay， so。

 so if your proof works with Gaussians， you should ask， oh， can I do this with plus -1。Or。

 maybe it works with plus -1。 Can I do this with subgausianss。And automatically。

 you are quickly extending your results。There are some advantages to this as well， because， you know。

 you might， you might get this language of subgaussians to then work with。嗯。

What else did I want to say about So yeah， often， okay， So another thing that happens， you know。

 in in C S， we work a lot with plus -1 Bs， right， bits are a business。 It says the lingu of Franca。

But very often a lot of our theorems， when we want to prove them for bits。

 we dont know how to prove them for bits so we instead you know extend it to the Gaussians and we start proving the theorems for Gaussian rhino variables。

😊，To see whether they are true or not。 and then hope that those proofs will generalize。

So if you go this way， then hopefully your proof will， you know whatever it might give you intuition。

 It might not there two might be different beasts。Wor trying。

So the more you can get comfortable with Gaussians， the better it is。😊，They are your friend。嗯对。嗯。

Good， so let me stop philoso。 by the way， one thing I forgot to mention it's not important。 I mean。

 it's important， but。嗯。は。Doing jail。If you want to do it fast。So by the way。

 if I want to figure out F of x。It's。This matrix multiplication， right。So this is B by K。So。

 it takes。没有。KB time。To do the matrix multiplication。对。If these is very large。

 I might not want to do this thing。So the question is， can you。Instead of this being a dense matrix。

 can you make a dispare matrix。And secondly， you know， so how fast can you do this。

 can you do this evaluation of F of X， Can you do this dimension reduction。

 And some people were interested in this。 And they came up with what they call the fast jail transform。

Yes， where they use some very nice ideas， including some， some， they use。Firstly。

 they want to make this sparse。And secondly， they don't want to。Yeah。

 so let me just look up what the run time of okay， crap。 I don't have it written down， but Ill。

 I'll put up some links on this thing。 If you're interested， there are fast ways of doing this where。

The runtime as a function of， you know， as a function of B is nearly linear。As a function of k。

 it becomes something like K log K。But as a function of deeds nearly linear a vision。

So there are ways to do that。 the one that I was thinking of just uses well just it uses a Fourier transfer。

So it uses a so called ha theide transform。There might be ways of doing count sketch， but those。

 as far as I know， are weaker guarantee。They might not be as as strong as the ones up there。

But we'll come to count sketch and you'll see some， some results based on that。O。Good。

But this is kind of a digression。 I'm not spending too much time on this。

 You might see a little bit in some homework if we managed to produce a good homework problem based on。

😊，在哪啊？OK。But for the for the rest of today， I want to consider the following question。

It's it's really just sort of a question that's of interest。And it says。I have。A vector x。

 which I don't know。I want to figure out what x is。And I'm allowed to build queries to this。

But I'm allowed to do sophisticated queries to this。So， each query。Is of the following form。

 So I'll give you a vector a。Oh you give me a vector A， and I'll give you back。AX。

It's an inner product claim。So after this， you can give me a2 and I can give you a2。

You want to figure out what takes。So what's a completely dumb solution to this thing？

Take unit vectors。 A1 is the first unit vector。 A2 is the second unit vector。 You'll figure out x。

Okay。And queries， we got the answer， that's perfect。😊，But now I tell you， x is parse。X is S sps。

It just means that the support of x， the non zero elements of x are at most as the size of the support。

Another way of writing this， this is like a fancy way。 You might see this in other settings。

The L0 norm， is not really a norm。 I don't know why we call it an L0 norm。

 but it's called the L0 norm。I at most s this this is by definition equal to that， you know。

 the definition of the zero norm is the size of the support。😊，是。

So it got at most S non zero symmetry。So now the question is。What query should you ask？

Let's say exactly。I'm sorry。呃。Say that again。Ha theard matrix。random matrix。No， no， no。

 Wder mo matrix。 of course。 Okay， why a Wderor。It has linear independence。 Okay， good。呃，So。

Each of these is a row from the random 1 matrix。😊，Okay。But how many roads will I ask。2 S。

And how would I show that this works。So but the idea is very， very nice。 I really like it。

 So here is a fact， by the way， O， by the way， Okay， so so here is a fact。😊，Suppose。嗯。A is a matrix。

Such that。Okay， let me actually define something。So let me just define fine。对。Csical rank。

Of a matrix a。Is the。Maximum。Od。Such that。Any。A columns。哦诶。啊0年。Every， you know。

 no matter which all columns you pick， they're linearly independent。哎。A let A V such a matrix。

SoSo you， whatever， it has cross skill ranking。So， claim。嗯。If he。Has crosscal rank。At least two S。

 let's say maybe bigger than2 S。 We'll see whether it it bigger than or at least。Then。

Then do the following。嗯。Look at A X， okay。So a， the matrix，It has crossedal rank2 S or something。

Ask queries， which are the first row of a， the second row of a， the whatever。啊个嗯我这个。The the mtro。

As a matrix with some some some rows and columns。브로 아。喂。Now， A X， you'll get back answers B。嗯。Now。

 the question is。The correct answer is a solution to this thing。😊，And this have other solutions。

Make sense， right。We will call this matrix a。Such that I am asking the rows of this matrix a。

 the sensing matrix。😊，So I've constructed a sensing matrix whose column rank。As a sensing matrix。

 I'm using a rank who is cross rank。😊，A at least2 s。Then， A X equals B。Will have。Okay。

 so I want to say。A X equals B when。安利。Have。160。嗯。One solution。 let me call this X star。 just。

 just so X star is the。行。😊，啊。哦哦 wait。Support。Let你关度。It won't have two sparse solutions。Reite。对。

So let me， let me write this more for。靓。All x such that A X equals B。X。Zero norm of x is at most S。

你闭过咯。Let's， let's prove this thing。Suppose。X。And X prime are two solutions。What are sparse。喂。

So this means a X minus。X primeme。不是一こ不ゼ。X minus x prime is 2 s bars。But this。

Is giving me a linear dependence。With only two S entries。Not possible。嗯。Hでね。被告。

So as long as I could give。A matrix。Whose crust rank was large， bigger than2 S I'm done。

And I think the viom one matrix should be good enough for this。哎。What's the problem with this？

That is great。我依赖你们辞。backward。应给我。Good， good。 So how do I find。You know。

 I need to come up with solutions。To this beast。If I can find a solution to this beast。😊。

Thenm either I'm in great shape， a sparse solution to the space， and I'm in great shape。😊。

But I have a problem。 You know， I want efficient algorithms。Class doesn't say efficient。

 but you know， as we say at the beginning of the homework， all your algorithms should be efficient。

So I want an efficient time。So let me try to write an LP。嗯。

So here is the here is the possible solution。 There were several solutions posed before。

 and I should be very clear the solution I am going to give is not the first solution。

 despite several people claiming that it is it was the first solution。😊。

The first al was given in the year  you，17， something， something by French noblemen。It's a very nice。

 elegant solution。 And I was。😊，Yeah。Now you guys will hate me for this。

 but whenever I see these things， I try to make it into a homework problem， but you know。

 it might be a little more annoying than pill。😊，But this one at least I will be able to tell you the ingredients right here。

😊，嗯。Even that we could， but that is another day when we talk about more linear algebra than we will talk about。

😊，O。So here is， here is one possible approach。 So this is approach。 Maybe this was approach 0。

 You know， find any matrix with large cross scale rank。In fact， you know。

 one way of creating a matrix with large crust rank is pick a pick a matrix with。

Probably something like， yeah， hopefully even2 F，2 S rows。

And whatever N columns and just fill it with random entries。

 Chs are that theyll have large cross length。😊，Chances are you won't get any non dependencies。

How would that but you know。Inverting things is complicated。

 So let's do approach one approach one approach2。Let's use convex programming。

Let's try to solve the following， following mathematical program。Find me a solution。

Such that A X equals B。So x is my unknown a the sensing matrix I haven't told you what the sensing matrix is but lets imagine that I have a very nice sensing matrix like this。

😊，And let me just try to solve this。H me。Or I shouldn't say LP。There is one problem with this。

 This objective is not convex。喂。It doesn't get off the ground somehow。This is NP hard。

 You can show that it's as hard as subset sum。So let's try。 and this is， you know， by the way。

 this is a very general recipe。 You'll see this again and again。😊，I'm going do。啊。I already say。

The zero norm is not really a norm。By the way， what is the norm do you guys remember what is the definition of enormous somebody remind me quickly what a norm is。

😊，What property that satisfies H on somebody else。 let let， let's try， let let somebody， anybody。

 please remind me what the normal。And actually， myself， I'm not 100% sure what all it satisfy。

It's a a norm of x。Is non negative。知他的。CX。Its equal to c times。X for the。No negative。

X plus y is less than equal to x。Plus why。啊。Yeah。就。So， so you're saying。X is equal to0。

 if and only if x is equal to0。Hopefully， good。 Okay， So the thing is， at least for LP norms。

It's the， the situation is very nice。 And maybe Ill I'll just create a little room out here。

 The LP norms， their unit ball。 So I can define for X。 I can just say for an LP norm。😊。

Let's look at the unit。 you know， the the unit you know， sphere really。So for the two norm。

 let me draw this。And I'm making the classic mistake。

One should always draw the circle before drawing the coordinates。

 when you can always get the coordinates through the center。But this one worked out pretty well。

That's the two ball， right？嗯。The one ball looks like this。The infinity ball looks like this。Okay。包。

Value is less than。One， it starts looking kind of weird like that。是。All these guys are not really。

 you know， norms， they're not convex。L1 is the smallest convex。呃，2。So what we can ask is。

 that' is not a good reason。 I'll tell you a good reason for doing this。By training。

Let's ask for minimizing the one norm such that Ax。いこ。Seems a little arbitrary。

 See you know kind of like， why did I do this thing just because of some weird geometric similarity。

 not really in similarity， right。对。Now， this， this。

 this approach where instead of looking for minimizing the zero norm。

 I'm trying to minimize the one norm。Is。This thing is called。Basis pursuit。It在哪个。

And the beauty of this algorithm is。That。嗯。Maybe I should write now that we've written down the definitions of these guys。

I can drag down the theem。So铁了。There exist。Marices， sensing matrices， a。对。M being ordered。Yes。

Lo n over S。Trows。Such that。Basis pursuit。He gives。

I wanted to solve the zero non minimization problem。Instead。

 I solve the one non minimization problem。Amazing fact。There exist matrices。With its not2 s rows。

 it's likely more S log n over s rows。Such that。This will give you the correct answer to this。真个。

It got that was there just so that they art Cru school， Frank S。the basis is just like。你都改块。

I'm sorry。 This is just linear programming。 Yeah' programming right。

 that's not nothing to do with the size of a that like the M it just theres。好了。No。

 so the M is big enough to make sure that this this algorithm。

 which is solving the one nu minimization。Will actually give you the correct answer for 0 non miniization。

嗯。This should be surprising to you。 You should be wondering why the heck is this true。I mean。

 that's kind of like that has to be like a。there's like end choose as possible。

Like the horns that you don't like。ISo， so it would normally be a lower bound。

 There's an annoyance out here。 Each of these answers doesn't give me just zero just a one bit answer。

😊，那个。So， so it's， I can't do the argument just on based on bit complexity。I， I thought of that。

 and I almost fool myself into believing it。But you're right。 this。

 this expression is just coming from log of ens。😊，Don't question。一这的是。第四个。

These are specific matrices that I will use in my basis pursuit。Yes， so you'll see this in a moment。

In fact， water are we matrices。😊，These matrices are exactly jail type matrices。

I want to take a matrix with so many rows。😊，How many columns and columns Because you come on。

That's what I need， right。Im want to fill every entry with a Gaussian。

And Im going to say with high probability， it's going to satisfy this property。哎。You， you you， you。

 you see the general game plan， right。So we， will， willll do this。 Lets do it。Questions about this。

This is like a。This should be surprising to you if it's not surprising。

 please tell me Ill try to figure out why it's smart。😊，Yeah。O。Okay。Okay， I want to keep。This thing。嗯。

Just to remind you， this is1 over square root k。Yes。对起。不了。So far， sub。Let me see what I wanted。Oh。

 by the way， this theorem。Is due to David Donoha。啊。



![](img/2f8ee32bded993d3de4902b89ff06691_1.png)

So this is a theorem due to David Donoho。And I've forgotten the exact provenance thing。 You know。

 you know me， you know， I get confused with all these things。 Once you search enough， you， you。

 you get。More and more confused Who exactly did what。 And Emmamanuel Candace has a， I think。

 accent somewhere out there。And like that is。

![](img/2f8ee32bded993d3de4902b89ff06691_3.png)

Perhaps one of those are more famous mathematicians nowadays Terryta。啊。One of his。

reallyally works okay。Good。So。嗯。So here is， here is a definition that will be sort of useful。

 You'll see this again and again。 So I need a definition。Definition。A matrix A。A matrix。

 it's got M rolls and it's got n columns。Is。B epsilon。Has， had。

But T epsilon restricted isometry property， isometry。老ber 때。Often known as RIP。I mean。

 one of the reasons why I give you guys all this jargon is you go to Per lunch and， you know。

 this is jargon starts flowing thick and fast。 Oh， is this an RP made No， no， no。

 this is not an RP matrix， So please。😊，I might be restricted isome property， very simple idea。

If the following thing holds that。A X。啊。Norm。Is in like one plus minus epsilon。Times x。For all。Ex。Oh。

 this is neither two。Nor for all x who 0， which is parse。O。Right。This matrix。

Maintains norms of every sparse vector。Not a every vector。Every sports。O。😊，对。

So now our theem is going to be。If。So I'm going to write down maybe two les， but you know。

 maybe let me write down。靓嘛。1。Yes。He is。3 years。Expsilon。Alright b。Ford。Apsilon less than 110th。

 let's say。Then。诶。Is。Go far。Maaz pursuit。Witht。S， spas。Sigma。

If you can find a matrix which maintains the lens of every S parse vector。

Then you can plug that into that LP。And things will work。This is going to be our first lemma。

And maybe I'll write down Lama two out here。嗯。If。M is bigger than。浪。TheM is bigger than。

theta S log N over S， then。The然。J matrix。Satisfies。1 plus。Epsilon，1 plus。我呃，不下一。Satisfies。3 years。嗯。

Contentth。你看。If the number of rows is bigger than S log and choose S。

 then a random Gaussian matrix is going to satisfy 3 S1，10 all right。Yeah。One more time。Right， oh。

 so actually here you can use any plus -1 matrix。😊，So basically， any subsient matrix will be fine。So。

 in fact， I could just say。Subcon。Do things super。Let's， let's do it。



![](img/2f8ee32bded993d3de4902b89ff06691_5.png)

I want to prove Lama one chances that I run out of time。그。Yeah后。So how do I prove Lema 1？

I need to show you。Okay。So， suppose。You know， I wanted to show。Remember， there is this X star。

that AX do。Is equal to B。And。X die。Have their own arm。At most。This is our goal。This is our target。

 We are looking at the north star。 We are looking at this guy。 We want some this guy。Suppose。We get。

Back。X tlda。From that LP。So what do we know， we know that a x tilde is equal to B。

But also that the the one norm of x tilde is less than equal to。The one norm of extra。

This is why I got back exilder instead of X star。O。😊，Let the support。Of x star。Be equal to the set。

Do that the entries were S。 you were extra as non。Yes。X star is， you know。This是ね。

T tilder could be anywhere。Let's write。Xtder as X star。Plus， deelta。

So I know that a delta is equal to 0。Because a x star and A X tilde are both equal to B。Okay。

So I'm going to have a claim。I want to claim。That。Look at Delta。

And restrict Dlta to the elements of S。So Delta has some garbage all over the place。

Delta sub S just contains these entries and zero everywhere else。

 and Delta S bar is going to contain the rest。😊，So I'm going to say delta sub S。

 the one norm of this。I at least。Delta sub S bar。6万了。I want to say it must be the case。

 we'll show this。Like this delta must have most of its not within。Yes。Within S bar。

 it has little known。

![](img/2f8ee32bded993d3de4902b89ff06691_7.png)

嗯。Let's， let's take this claim。 and let's go on。Okay。So now here's what I'm going to do。

And this proof， let me keep this up。So， let's look at F bar。And this F bar。

 I'm going to break into blocks。This is going to be block1， which consists of2 S entries。

 there's2 S entries in block 2。And so on so。Okay。😊，And let's say that these deelta values。嗯。Sorry。

 Im I'm forgetting one，1 detail that。O。So what I've done is Ive， Ive。

 I've written the values of Delta so that they are。Non increasing in absolute value。

 So this is Delta。 This is absolute value of Delta。The highest entry。Sorry。

 the highest entries are to the left。This is all in Epar。So this is the first block。

 This is second block， third block， fourth block and so on。Absolute。Okay。So。And here， you know。

 this is a fresh proof in my mind。 So I'm forgetting some details now。哎。So。Good。

Let's look at any entry out here。It is smaller than。Every entry out here。Okay。

Any entry out here called that Delta I is smaller than every entry in the previous block。So。Data I。

Is smaller than。The L1 norm of this， this previous block， be1。Divided by the size of the block。

Every entry out here is smaller than every entry out here。So it's smaller than the average only。

Each entry out here is smaller than this quantity。So how big。Can。Delta B2 is2 non B。

Times square root of2 f。There are two entries out here。Each of them are smaller than this quantity。

And you're looking at the L2 norm。So you're going to get a square root to out。Okay。Which is。That呃。B。

呃，B one。你白明白。Do square。Okay。Good。Which is at most。Delta of S bar。Divided by a square root of2 S。

Be one。Is contained。In F bar。Which is at most。That oh， sorry yeah，1，1，11。

S bar is smaller than S1 known。They bus square root to s。F bar is smaller than S vi a claim。

And this guy。Delta S only has S entries。So， this。Is Delta S。

2 norm over square root2 S and square root S F1 norm and two normal differ only by the number of coordinates。

So this is smaller than Delta S， the two non divided by squared。It's a little magical。Basically。

 I'm saying each of these guys。😊，The two norm of each of these blocks。Is smaller than。The two norm。

Of this original。YouS thing out here， whatever。As O。Divide best question。So far， so good。I mean。

 it's just algebra that I've done。Here's one more thing I could do。Each of these blocks。

 I was charging to the previous block。So I could have summed over all blocks except。The first。

All except。1。Will be smaller than。The sun over all blocks。And then in this case。

 this is a sum over all blocks as well。 And this L1 norm is actually。😊，Equal to this。S8。

So the point I want to make is that this averaging analysis gives you something like。If I look over。

Delta。off。哦。But。The first block。And as bar。Okay do not。And I want need to somehow care。

🎼Is less than equal to。Delta S。で外 by。So this delta its mass in this region。

Is small compared to its mass。追下。And what else do I need。Now， I just need to finish the proof。

This is， this is。Very clear in my head。A delta is 0。But， a delta。Is a。S union block 1。

 Delta S union block1。This is too norm。我也不是。I use。え。The rest。レ到で。嗯。This quantity。Is smaller than。嗯。

This quantity， this guy。It maintains the length of each of those blocks separately。

So this guy is going to be smaller than one plus eps salilon times。Delta S。嗯。对 the less快。

And this quantity。Is going to be。At least one minus epsilon。Times。Delta S Union B1。Do know of that。

And from there。I can say this is at least one minus epsilon。Delta S， the true normal of that。

Some algebra going on I'm falling into the same trap。 What do I want to show。I want to show， look。

I want to get a contradiction。I want to say look my only source of contradiction is that I've got back X such that。

This has happened。I want to contradict this。So what do I want to say， Look。

 I want to say where is most of my mass city。I want to say most of my mask is sitting here。

The rest of this is pretty much garbage。Suppose all this mass was gone。Okay。

 suppose there was no answer okay。This was some algebra doing that。 I got carried away。

There 너무 master okay。So， all the mass is sitting in how many blocks how many coordinates S coordinates。

😊，Plus 2 x coordinates。That's3 S coordinates。O。😊，If these three as coordinates are the only delta。

Then。What is a going to do？Is going to maintain the length of deelta。막 a de 했어요。So Dlta must be here。

That's the the only thing to take away。Ignoreed by algebra。If there was no mass。

If if all the mass of Delta was in three3 S coordinates， I'd be done。The problem is。

 S might have mass on other coordinates。You say no， no， no。

 the total mass that S can have on another coordinates is very little。😊，It can't confuse us。

So this total mass， we are saying is very small compared to the mass sitting out here。So this。

 this can't give me too much of a length。 Most of the length must be coming from here。But then。

 you know， then this this portion can't， you know， this whole thing can't cancel this out。

 And that's。嗯。That's the。Proof。For。This part。What's the proof for this part？😊。

The proof for this part is essentially a churn of is a union bond。You want to say， look。

This matrix satisfies some restricted isometry property。It maintains the lens of every S p。

Of code of S parts vector。C， S person。How many three S perspectives are there and choose3 S。

And on each one of these， I'm going to apply。A union bound like this。

Now of course I can't apply to every entries 3 s parse vector you know once I have chosen some 3S coordinates。

 I have to make sure that every vector which has support within these 3 S coordinates is maintained。

😊，And。We maybe we'll do this little argument next time。But the。

 the second lemma is kind of fairly routine， if you've。

If you've seen the Johnson Lynden Straus like distributionclaim。

 the first lemma is the slightly surprising one。It's somehow saying that， look。This。

Interesting property that is that this matrix a is maintaining the length of every3 S sparse vector is enough for this LP to work。

😊，Why it enough？Exactly the impression that we said。If。

 if the difference between x star and x telder is sparse itself， we are done。 If it's not sparse。

 we prove that most of the Mar is sitting。On3 S coordinates。没。Anyways， let me stop。

And well continue on Friday。Well maybe do the last part of this proof because theres at least one cute idea that I want to tell you。

 and then we'll talk about streaming。And we can't get to count get as you were talking。OK。

What's see you guys are right。