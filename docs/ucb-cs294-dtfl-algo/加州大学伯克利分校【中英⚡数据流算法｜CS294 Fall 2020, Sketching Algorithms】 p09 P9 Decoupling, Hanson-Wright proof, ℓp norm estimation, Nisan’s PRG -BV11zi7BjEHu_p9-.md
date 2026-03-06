# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p09 P9 Decoupling, Hanson-Wright proof, ℓp norm estimation, Nisan’s PRG -BV11zi7BjEHu_p9-

![](img/a5cfecf4ae2613500e2b8655c138f240_0.png)

Okay， so today。What I wanted to do was to prove。嗯。Prove the handsomeen right inequality。Right。

 so we use that on Monday to prove the distribution of little J alema。AndOnce we're done with that。

 we're going to move into。Norm estimation for other norms， so LP norm estimation。For P not equal to2。

Specifically， we'll look at the case where zero is less than p is less than  two。

If it's less than one， it's not a norm， but it's still a well defined function of the vector and we'll show that we can do that in both space as well。

 and then then we'll wrap up by talking about。嗯。Sorran generators。For space mounted computation。

Right。We've found ourselves numerous times in a situation where if only we had a perfectly random hash function。

 our analysis would be simpler。But then you know we can't afford to store such of things。

 so we talk about how to derandomize it， maybe I'll use two wise independence or four wise independence or log n wise independence or maybe you know。

 well that's all we've seen so far is's basically using KY independence。

 but there are other tools in the pseudorandom toolbox okay。

 so KY independence is not the only one there are things like。Epsilon bias faces， for example。

 and other PR pseudo random generators so today what I want to tell you about is pseudo random generators for just generic space bounded computation right so if you have an algorithm that uses small space there's just a generic method to。

To generate pseudo randomum bits that fools the behavior of that algorithm。好嘅。

The first application of such kind of generic tools to streaming algorithmms was for LPN estimation when P is not2 since that paper we've discovered that in fact you can actually solve that problem just using KY independence so you didn't need this more generic tool。

 but it is a good general tool to keep in mind for other problems as well。

So we're going to prove Hansson rightite first that's number one I've reminded you what Hanson Write is from the Monday lecture。

 so it's it's a tail bound for quadratic forms when the random variables are plus minus1 so you have single one the singleigma capital n。

Their I plus uniform plus minus1， you have a matrix A， which is square。

Once the problem sigma transpose a certainulma deviates from its expectation by more than Lambda。

 it's something that depends on the Frbeius and operator norms。I you know。

 I defined for me and operating norms last time， I just wanted to thank Yessshwaan who pointed out to me over emailed that something I said for operating norms is quite right I said。

first of all， what is the operator norm？RightThe actual definition of the operator norm is like。

Is it find to be the soup？Overall， x of A X L2 norm。Divided by the norm x。嗯。Now。

It turns out using linear algebra， there are other。Characterizations that are equivalent， you know。

 you could also say it's the soup。Overall。X， Y of unit norm。

There are L two norms of just x transpose AY。One of the things I said in lecture was if it's diagonalizable if a is diagonalizable it's just the magnitude of iigenvalue。

 so that's not so that was the bug that a verbal bug I made that's not always true it is true if a is a real symmetric matrix right then it's diagonalizable by an orthogonal matrix then it's true that it's the magnitude of the largest eigenvalue but just diagonalizable is not enough in our examples。

 if you remember when we applied Hansonite to proving the distributional Jlemma。

Our matrix A was like of the form kind of B transpose B for some other matrix B， if you remember。

RB looks sort of like。I had like Z transpose， Z transpose。

Z transpose and then like zeros everywhere else and a1 over route， I guess。This is our B。

 and then our A was B transfer was B。When we applied Hanenright on Monday。

So this matrix is in fact a real symmetric matrix， so it is by the special theem and diagonalzizable by an orthogonal matrix so it so in fact for this case。

The operator norm is the magnitude of the largest eiging value。

 but you know that's not always going to be the operator norm if you don't have a， let's say。

 real symmetric matrix necessarily。So any now I stated at Hansen right on Monday as this tail bound for all lambda there's some tail it's a mixture of a Gaussian tail and an exponential tail right so Gaussian like this e to the minus lambda squared is how a Gaussian behaves it's how Gaussian decays E to the minus lambda is how an exponential random variable decays so it's like the tail bound gives is some of the two。

 which is basically the same as the max of the two up to a factor of two。嗯。

So you decay like a Gaussian up to a certain point。But then don't as good decay as Gaussian decay。

 you only start getting exponential decay。Okay。Now。嗯。

Tail bounds and moment bounds are equivalent I'll say a little bit I don't want to get too into the math。

 but I put already put all of this in the lecture notes in the probability review I uploaded it either last night or this morning。

Um， whenever you have a taildown that looks like this。

 like you say that some random variable decays like Gausian。Thats equivalentquivalent to saying。

The moments of the random variable grow in a certain way。 It's equivalent in both directions， right。

 So the moment in equality implies the tail bound。 The tail bound implies the moment in。

When you say that。Your tail bound decays like the max of a Gaussian and an exponential that similarly implies。

Let's say abound on all the moments， okay。So right。

 so maybe I'll just say a little bit about that without spending too much time on it。

 but remember okay so we have for you can define a norm on random variables so that's this P norm here that I'm highlighting in yellow。

Okay， so the P norm。Of Z， Z is just some real valued random variable。 The P norm is the Pth moment。

the P and then you take that PF moment and you take the one over P of power。Okay。

And you can prove that for any P that's at least one， this is a norm， this satisfies tri inequality。

 it satisfi it is a norm， a norm。Okay， that's you know。

 the fact that it's norm is something called Minkowski's inequality if you haven't seen it before。

It's a norm for P greater than one。For P at least one。Okay。

So right so i'm saying that this kind of tail bound is equivalent to bounding all the p norms of the random variable Okay。

 why is that okay， so again， let me just give you a little let's say let's say that probability let's just do it for Gaussians let's say that probability that。

嗯。Z is greater than lambda is at most this less than triman up to a constant factor is at most E to the minus some constant lambda squared over。

You know， alpha squared。Let's say that someone told you that I claim that implies a bound on the penors why。

 because this implies that right the expectation。What is the expectation of Z to the P？

That's equal to the integral。From0 to infinity of p times x to the p minus1 times the probability that z is greater than x dx。

Okay。This is the PF moment if you haven't seen this， it follows from integration by parts。

That you know， the normal way you define the peace moment is you say it's the integral。

Of x to the P times the Pf， right， some Pdf of。It's the X。

Or this PDF is the PDF of the absolute value of Z。But you can show via integration by parts that。

The two integrals are actually equal。So then now， right。

 you told me that I have a bound on the probabilitybil is bigger than lambda。So。

I'll just apply that bound to this。ok。😊，And then I get that this thing is at most some constant times e the minus c lambda squared over alpha squared。

And now what am I integrating， I'm basically I'm integrating exactly the Gaussian taildown like this is exactly the pth moment of a Gaussian。

Okay。And you know， you can look it up。The P is the Gaussian know the moments of a Gaussian are known and。

You know， it's it's exactly， this is you can prove that this is at most。Yeah， O of Ru。

Alpha repeat to the V。Just based on Gausian moments。And similarly， the other direction。

If you tell me that。The expectation of。But if you tell me that the Pth moment is bounded。

By something。And there。The probability that Z is bigger than lambmbda。Is less than， well。

 it's equal to， when you write， it's equal to。The probability that is z to the P。

Is bigger than the lambda of the P。 But by Markov， that's less than。嗯。Be over to the P。哎。

A comess inequality。嗯。And so if I tell you that B is something P to the P。I'm going to tell you。

 this is something like oh of。Alpha， let's just say let's just get rid of the big O this is going to change the exact most。

 let's say some constant times alpha root P to the P。Over lambmbda to the P。

 So if you know that's true。De， what am I going to do。

 I'm going to just basically set P I can you know I have a bound on the P of moments for all P。

 so I'm allowed to freely choose P so how am I going to choose P。😡，the base of that exponential be。

 let's say， something like one over E。So I'm going to choose P。 So let's say choose P。

To be something like。Lambda squared。Or lambda over C alpha， EEC alpha。Squared。Then this is equal to。

E to the minus P， which is E to the minus lambda squared over。You know， E squared。

 C squared alpha squared。Which looks a lot like。Right so this exponent is basically the same exponent as what you have here right either minus some constant lambda squared over alpha is basically serving as the standard deviation or alpha squared is like the variance for Gaussian。

So I don't want to so I'm not going to do all these calculations。

 you can look at the lecture notes if you want in the probability review section。

 but the punchline is。Proving a tail bound that holds like this is equivalent to proving bounds on all the moments or on all the p norms Okay。

 so the way we're going to prove Hansson right is to bound all the p norms Okay so that will be this equivalent of proving what I wanted to prove So let's do it let's prove all let's bound all the p norm。

Okay。So before we do that， I'm going to teach you a technique called decoupling。

Did we show both directions of that equivalence？Sorry， what tell。

Did we show both directions of that equivalence。I think so。

 so the directions are divided by this yellow line right here。Right so above it。

 okay I'm showing that if you have a tail bound， then you have a moment bound and below it I'm showing if you have a moment bound。

 then you have a tail down。But again， again， looking in the probability review notes。

 I have things more written in detail there。So just take it for granted that。

These two things are equivalent for now。And that's let ban the Peters。Okay。So actually。

 before I do decoupling， let me actually do one one simple thing before that。

 I'm going to reference a theorem that I think is I've already put in the probability review a while ago。

 which is called kinens inequality。Which says that if Sigma1， Sigma n。Our II plus minus1。

 and let's say x is a fixed vector。Then if you look at the p norms of sigma dot x。

So this is the same thing as right some of Sigma Ixii。This is at most。Root P times the Lorex。Okay。

And kind of why is that true， Well， let me let's just prove it in the case that let's say p is an even integer。

Then if you look at。Expectation of the sum of sigma Ixii absolute value to the P。

 then that's the same as the expectation of the sum of Sigma Ixii to the P without the absolute value because P is an even integer。

 right？Raising to the P is definitely going to be positive or not negative。

And then you can expand this thing out， right， so this is equal to。

The sum of I1 up to IP X I1 up to X IP， and then the expectation of that product， stigma I1， Sma IP。

对。And now。🤧The thing to note is。You know， some of these indices I went to IP might be repetitive。

 all those P indices are not necessarily distinct。Okay。

 so let's just write this as like a sum of all kind of monoomials。Of x to some index。

 let's call it J1 race to some power D1。X， J， R up to some power DR times the expectation of。

Sigma J1， D1 up to Sigma J R DR。Does that make sense we're like here now？The JTs are distinct。

The JTs are distinct。So I basically I grouped eyes that were the same。

So D1 plus dot dot dot DR is equal to P right， that's right， plus DR is equal to P。Okay， right。

 so now the thing to observe is what is the X first of all， by independence。

 this thing is the product over T of the expectation of sigma Jt to the Dt。

So what what is this kind of what is this product， well， there are only two cases。In one case。

 all the DTs are even。And then sigma to the D is one。

 and then the product of one a bunch of times is one， so this thing could be one。On the other hand。

 even if a single DT is odd。Then sigma to the D is going to be the same as sigma。

And the expectation of sigma is zero right this is a plus minus one random variable。

 so this is either zero or one。Either zero or one。Okay， and what if Sigma had not been Sigma。

 what if Sigma had actually been a Gaussian G？Versus， let's say it had been some of G Xi。

 where the Gs are ID Gaussians。Then you could do the same kind of expansion。

 you'd have this a similar story， it would either be zero if any Gaussian is raised to an odd power。

😡，Or if all the Gaussians are raised to an even power， it would be at least one。

 it might be more than one because like the expectation of a Gaussian squared is one。

 I'm talking about a standard normal random variable with the variance one。

So the expectation of G squared is one， the expectation of G to the fourth is three。

 I think the expectation of G to the6 is phi or maybe three times5 or something。

 but the point is it's always at least one if you raise it to an even power。

 so this is term by turn dominated by the Gaussian case so this is at most that same sum of Xj1 D1。

 blah bh， blah Xj R DR of the expectation of the Gaussian case， which is Gj1 D1。G JRDR。

RightAnd this is just the same thing as the expectation of。The sum of G Xi。Race to the P。

So we've just proven this is the inequality here， we've just proven that the Raammacker case has moments that are strictly bounded by the Gaussian case。

And you， if you haven't seen this before， now I'm going to cite a fact about Gaussians。If you add。

Independent Gausians together， you get back a Gaussian。Whose variance is the sum。

Of the variances of the Gaussians that you added。 Okay， so G I X I。Is itself a Gaussian。

 it's a normal random variable with mean zero and variance。Xi squared， sorry。Okay。

 so this is the variance， this is the mean。So you're sum a bunch of you're summing up capital and Gaussians。

Whose variances are each X I squared？ So when you do that， you get back a Gausian。

 whose variance to the size of the variances。 So this is equal to basically the expectation of。

The al norm of x times just now is some1 Gaussians to the P。And then you can just look up。You know。

You can look up what is the PF moment of a Gausian。Um， and you'll get exactly what， you know。

 you'll get something that is at most root of the pe。Okay， and weno。

 if you then remember the P norm takes this whole thing to the one over p of power。Et cetera。

 So here you're going to take this all to the one of repeat power。And then you're going to get。

Something like that's at most the al of x。Times the square it be。

Which is exactly what I wanted to show。对。I think that the PF moment of a Gaussian。

If P is an even integer or something like's， there's an exact formulas like P over2 factorial divided by two to the P or sorry。

 not P over2 factorial。P factorial divided by 2 to the P over 2 times P over  two factorial。

You know there's whatever you can look it up if you want， but the point is that this thing is。

 which I think is something like one times three times five times seven， whatever。嗯。

I think you usually prove that by some repeated integration by parts。

 but you can just take it as a given for for the lecture。Okay， so good。

 so this is Kinenss inequality， which is a linear form with Ramas right， So it's sum of Sigma Ixii。

 we're interested in quadratic forms。😊，Okay。So now let's see how we're going to do that henceson rise back quadratic forms。

So you can view it as like a generalization of kin to degree two polynomials instead of linear polynomials。

So we're going to。Use a tool called decoupling。And here the theorem。Is that if you have。

The sum I not equal to J of AI J Sigma I sigma J P norm is at most four times。

The sum I not equal to J of signal of。AI J， Sigma I， Sigma J prime。Kor okay。

 where Sigma 1 up to sigma n。And Sigma1 prime if Sigma n prime。Or2 N。IID plus minus v。

So this is I can replace I can replace kind of so I mean， what is this， right？This is like。Basically。

 sigma transpose a sigma minus the expectation of sigma transpose a sigma。

Whereas what this is is sigma transpose a sigma prime minus the expectation of sigma transpose a sigma prime。

It's that or not exactly it's minus minus the diagonal， let's say。

So you I'm allowed to replace one of the sigmas with the sigma prime and pay at most a constant factor in my P norm。

 that's what decoupling says。Yeah。Very good。So let's prove this。嗯嗯。😊，Im sorry。So proof。来。Ada。

1 up to a to n。B like Iid Bernoullia half。So it's zero with probability one half and it's one with probability1 half So right。

 this implies that。The expectation of like eight to I is a half， right？So I can write this thing。

Is equal to。F times。The times this， the expectation over Eda。S I not equal to J。呃AI j。

Is this what I want to？Yeah。え。Eta I kind of1 minus Eta J。你觉。

Right just because I mean I'm basically just in a convoluted way。

 multiplying by a quarter on the inside of the norm and then I'm multiplying by four on the outside of the norm so I haven't really done anything。

And then now what I'll do is。I'll say that this is at most。Four times。嗯。This thing。

 some I'll basically pull the expectation over Eda outside。So if you want me to be clear。

 I mean this。Sorry， I forgot to put the actual Ps that in the signalss。So here's like Sigma I。

 Sigma J。And here there's also a Sigma I， Sigma J。And you know， remember。

 I told you what the definition of the P norm is。Yeah that's yeah so no I think you got your question answered I told you what。

The P norm is it's like the expectation of b raised to the P of power all through one over P。

 so if want me to be more clear， this is like the LP norm over the randomness of like sigma。

And this is here you're taking the expectation over both Eda and Sigma。So right。

 there's like an expectation over both Eta and Sigma of whatever to the P al1 over P。

And this follows by Yenssen's inequality。Okay， so Jannsen basically says whenever you're taking。嗯。

When you're taking， let's say phi is a convex function and you're looking at phi of the expectation of a random variable。

That's at most expectation of fee of the random。So like basically whenever， so in this case。

 the convex function is like absolute value to the P。

So Ysen says I can pull the expectation from inside the norm to outside。

This is a common trick that we're going to use a lot is basically。

Pulling expectations inside the norm， outside the norm yes unless you do that。

And now what we're going to say is， look， what is an expectation and expectation is just an average。

 right？So there be there must be a fixed choice of the Eda， I mean Eda is just a 01 vector， right。

 it's a random 01 vector。😡，嗯。😊，But's but it is a zero1 vector。 so look， this is the average。

 I'm saying that when now what I want to say is that there must exist a fixed vector that achieves a value that's at most the average。

There's always someone who's at most the average， so this is at most now。嗯。Four times。それ这个事。

First some guys has been of thought。Yeah， so I guess what I would say is' it must be some fixed very good。

Not at most the average， I want to say that so this is the average。

 there must be some fixed eta's that's at least the average is what I want to say not at most the average。

 so this is at most the sum I not equal to J of AI J Sigma I prime1 minus ata J prime Sigma I sigma J where now the randomness is only over sigma where Eta prime is fixed。

It's not random ata prime is some fixed vector it's a fixed01 vector right so I'm saying that there must be some vector whose value is at least the average。

Okay， and then now I can just write， let's write this as four times。The norm of the sum。

 let's say IN S。The sum J nodded S。Of AI J， Sigma I Sigma J。Okay， LP norm。

 where here I just define S。To be， I guess the set of all I such that a to I prime is1。

Does that make sense？你下。Your a a a to I prime1 minus a to j prime is going that product is either going to be1 or0。

 It's going to be one if I is an S and J is not an S， otherwise it's zero so it doesn't appear。

 it doesn't matter。😡，Okay。And now this is equal in distribution。To four times this thing。

Does that make sense， right， because basically what I'm saying is look。HereHere's my vector sigma。

 Sigma 1， sigma 2， sigma capital n， this is a vector of ID plus minus ones。

 and I'm saying yeah there's a set S and the complement of S here。Right。😊，And what I'm saying is。

 look， if I just replace everything in the complement of S with like sigma。

J prime up to Sigma n prime， and this is now my new signine vector。

This new signine vector is also just a vector of independent signs。

 it's equal in distribution to the previous vector。😡。

So replacing those J no in S with sigma J prime doesn't change the distribution of the random variable at all。

 it's not just that the norms are equal， the distributions are identical。😡，Okay。

And now I'm going to do something funny， which I'm going to add0 in a funny way。 I'm going to say。

 look， this thing is equal to。😊，Four times。The norm of， let's say。The expectation。Over。

Sigma not in S， sigma， let's say projected to Nain or。Sigma， no an S。Expectation of Sigma prime in S。

Of the sum。And here actually， I'm going to write here all IJ， actually。

I don't need to remove the diagonal。Of some overall IJ of AIJ， Sigma I Sigma J prime。

And then I'm going to do penor。And then I'm going to do Ysen again and pull these expectations outside。

 and this is at most four times the p norm of all sum of AIJ， Sigma i Sigma J prime。

And that's exactly what I wanted to show right， This is exactly that。Okay。

 so that's decoupling questions about decoupling。So I guess it didn't need to be a P norm right it could have been any convex function of this。

Yeah， that seems to be the case。I mean， maybe the four would be something， well。

 would the four be something else？Yeah but you just it should still be before right right yeah。

 that's I think that's so yeah， it should be fine， yeah。

 I think anything think you can do it with other convex functions too。Any other questions？Okay。

 so now let's move Hanson right。So Hansson right。Okay。收。😊，We're looking at the P norm。

Of sigma transpoposed a sigma minus the expectation of Sigma transpoposedse as sigma。Now。

One nice thing about plus minus ones is that， if you look at the diagonal terms of sigma transpose a sigma。

 it's basically just equal to the sum of the diagonals of a。

 it's the trace of a right just because Sigma i squared is one with probability one。

Which cancels exactly with the expectation of Sigma transpose asigma。Okay， so this， I mean。

 this thing is the same thing as the sum of I not equal to J of AI J， sigma I sigma J。

 all I'm trying to say is that the diagonals cancel out completely。

So we can apply decoupling and decoupling says。Is that most up to a factor of four。

 that chiwittleddle means up to a constant factor。Of the P norm of sigma transpose a sigma prime。

Okay。And then now what I want to do is I want to do。Kenss inequality。Okay。

 so if I first just condition on Sigma。Let's say Eric condition。 Yeah， condition on Sigma。

And now Sigma， I can think of Sigma as a fixed vector and first take the expectation over Sigma prime。

I can apply Kinch's inequality and Kinchin says that this is at most。嗯嗯。😊，basicallys。

The P norm of a sigma prime。So's the so it's the it' its。What is it， it's like。

 which let me do this a little more carefully。So normally this would be like， you know。

 it's at most root P times the L2 x， right？So this is at most root P。

Times the L2 norm of as sigma prime， but the alt2 norm of asigma prime is a random variable。

 so I have something like this。😡，Pino Im there。Does that make sense？These are different norms， right？

 This is a vector norm。 Yeah， sorry P norm is is the random variable norm。 The LP better Yeah。

 maybe it's better to say like LP or something for the maybe that will be less confusing。

 So these these are LP is like the。I'll use LP to mean the random variable norm and the two there is like Euclidean norm。

And if you look at what the definition of LP is， then right this thing is basically this thing here is like the expectation of。

A sigma prime。诶。L2 norm to the P。All to the one over repeat。Right。But that's also the same thing as。

I'll write it as like let me do a different color。That's the same thing as doing。呃。

L two norm squared。To the P over two。To the2 over P all to the1 half。

Okay that's just like playing with numbers I haven't changed anything they're they're equivalent so all I'm saying is that this is the same thing as root P times。

A sigma prime L2 norm squared LP over 2 to the12。ok。And then a fact about penors is that。

P less than  Q implies。LP is at most LQ。This also actually follows from Jensen's inality and I have the proof in the lecture notes so you can take a look it it's not a hard proof。

 but going to let me not waste time in lecture doing it。

Do we need P to B at least two or something though， because？Yeah， you do need P2B at least two。

 so let's do let's do Ps at least two。Yeah， otherwise， the P over2 thing is not a norm。But yeah。

 so this thing is att most。Root P times。A singleig prime L2 norm squared。LP to the one half。

And then what I'll do is I'll just add and subtract the same thing。

 so I'll add the expectation of a Sigma prime L2 norm squared and also subtract the expectation so let me add the expectation of that thing。

And subtract the expectation of that thing。And the expectation。Of right， the expectation of。

Of the al norm squared， right？The expectation of a sigma prime L two norm squared。

 that's the same thing as the expectation of Sigma prime transpose a transpose a sigma prime。

 which is just the trace of a transpose a， which is just the Frbenius norm squared of a。喂。

So I can I can do a triangle inequality and pull out a Frbeius norm， so this is at most。

Root P times the forbeius norm of A。Plus。嗯。😊，Something that looks like a Sigma prime。

L2 norm squared minus the expectation of a sigma prime。Litude norm squared。LP to the one half。Okay。

And now what I can do is again， apply decoupling。And I can say that this is at most up to a constant of four。

Root P times the ferennous norm。pl。So decoupling says I can put here。诶识咩？

Transpose a transpose a sigma prime。LP to the one half。Right。And then okay。

 so it looks like like where am I going with this， it just looks like I'm doing I' back where I started sort of。

 but we're almost there。And then I'm going to do to the kin again。Okay， so this is at most by Kinch。

Root P times the Frennous norm。pl。嗯。😊，Now the L2 norm。Of。A transpose a sigma prime。Okay。Now。

Now what I'm going to do is use the fact that。This thing is right should there be like a square root P or something？

Yes， you're right。 There should be a repeat right here。Um， or actually like a p to the one fourth。

 right， because don't you have a。I guess it should actually be where did I do kinchin。

 so I just did kin here。And also I was a little there are rootees all there arerupees here and here too right there's a rootee there yeah yeah。

 yeah and then here it should be basically be P to the three quarters yeah。Because of K。Okay。

So this is Ken。Now we're like basically almost one light away。

And then now what I'm going to do is I'm just going to say， look， like if I have two， if I have。

 you know， like a times B times x else warm。It is at most the operator of a times。B X L2 norm， right。

 I mean， that's what operator norm means operator norm means like how much can you increase the L2 norm of the vector that you're operating on by。

So then this is at most。Root P times the Frennous nerve of a。Plus， P to the three quarters。

Operator norm of a to the12。Times。嗯。Okay as sigma prime。Oops。We're getting too close to the bottom。

 I guess。As sigma prime L2 norm。LP to the one half。Okay， does that make sense？

So now I claim we're done， even though you might look at this and be a little scared。

 I claim we're done， why are we done？We're done because let's just compare things。

 so we have this somewhere along the way we had this。Let me actually go one level down。We had this。

This thing that I circled in red。And we just bounded that。By this。Okay， so why is that significant？

Let me let's take this thing that I'm highlighting in yellow。

And let's just call that like let's call that E。嗯。So what have I just shown， I've just shown that。嗯。

Is that what I？Oh， actually， let's go。 No， no， no， no， good。 Yeah， good。 So let me， I， I went。

 I went a little bit too far down， actually。 So let's erase this red thing。

This is what I wanted to say， this thing right here。This。Yes。

 that's what I want so compare that red circle I bounded that red circle thing by something on the bottom。

So now let's and let's call that thing that I circled in yellow E。

 what have I just shown what's the thing in the red circle， it's actually just e squared， right？

The yellow circle is some norm of something raised to the one half。

And that red circle is the same thing without the one half。 So that thing is e squared。

 So what I've just showed is that root P times e squared。Is at most some constant。Times。

Root P times svenous norm。Plus。P to the three quarters。嗯。A to the 12 times E。In other words。

 what I've shown is that like and I can cancel some  repeats here and there and you get this is P of the one quarter now has shown that e squared minus something some constant times E。

Minus some other constant is at most zero。拿出来没有。So。Let's just plot that。

This is some quadratic right where the x axis is E。And the y axis is this quadratic for the sun。

This quadratic equation or quadratic expression。And I know that in the limit as egos to infinity。

 you know， it goes toward infinity， so I mean the picture looks something like this。😡。

That's the graph of e squared minus alpha e minus beta。And I'm telling you that。I'm in a region。

Where the quadratic is non positive。Which means that E has to be。Left of this point。

 it has to be somewhere here。Does that make sense？So I just got an upper bound on E。

Which is exactly what I wanted Okay， I mean I now now you just have to solve the quadratic equation and show that the root that you get is exactly the bound that you wanted。

 this is basically the larger root of the associated quadratic equation。😡。

So I mean that's essentially it so maybe i'll i'm not going to do that in lecture because I think it's a waste of time there's nothing interesting beyond this point it's really just solve a quadratic equation。

Now， you know that E is smaller than the larger root。

 that implies exactly the bound that you wanted for fancy rate。Okay。

So I know that was a lot of math on one board but。Any questions about this？

Or are people too scared to ask a question？Okay， is it also possible to get control like the just the。

Like the P moments for P between one and 2。Yeah， so yes， but you know。

 that's kind of trivialremal because as I said here。

Oh because you have the less than like the thing right so now I can just bound the one norm by the two norm。

 for example。And is that the right answer for this quadratic form？No。

 it is the right answer if Sigma had been Gausian。If sigmas so。

 so why can't actually that's a good question， let's even go back here。😡，It's a kinchin。

 is this the right answer for kinin？No， it cannot be the right answer。

 Why cannot be it Why can it not， Why is it definitely not the right answer， Notice that。😡。

Sigma dotX。Is that most the L1 or of x with probability like one right because again。

 the sigma I are at most one in two they're either they're either one so meanwhile on the left。

The P norm bound is going to infinity as P goes to infinity。

So it cannot possibly be correct for allP this is now a random aside it's known what the right answer is the right answer is that for all P。

😡，If you look at。Sigma dot X P norm for all por at least one。

 This is equal up to a constant factor to。The sum I goes from 1 to K or P， actually， of x star I。

Have value。Plus， root P times。The sum I goes from p plus1 to n。Of X star。Iigh squared square root。

 So know this is the same thing as basically。X had P， I'll say x stormies in a second X had P。

 L1 norm。Plus， root p times。嗯。Extail P。到 two。So x star just means you sort x by magnitude and decreasing order。

 so like x star1 is the biggest entry in magnitude in x x star2 is the second biggest entry， etter。

So， I mean， the upper the fact that this is an upper bound is。Easy， right。

 just by triangle inequality。I can say I have some of Sigma Ixii。

 let me do triangle inequality to move out the largest pe in trees。

 and then I'll use kinchin on the rest。Right and then for the part that I moved out the largest entry。

 I'll just use the trivial bound that it's at mostly L1 norm。Okay。

 the fact that it's a lower bound requires more work。

 but it's it's been known by probabilists you think the first person to prove it was someone named Montgomery Smith。

But yes。The kin is exactly correct for Gaussians for plus minus ones it can't possibly be correct because you know that you know the pen norms should not go to infinity。

 but yes， we know what the right answer is so the basic issue is that you just have bounded random variables or。

Yeah， I mean， in general， though， even for like。I mean。

 if you have something that I mean all you know about Sigma here is that all you're using in K is that it's sub Gaussian。

 right， but I mean。Sub Gausian decays at least as fast as a Gaussian。

 but there's no reason to believe that kinchin should be correct upper and lower bound for an arbitrary sub Gaussian right I mean you're just because you're you decay at least as fast as Gaussian doesn't mean you decay exactly like a Gaussian decays right signal I doesn't decay exactly like Gausian decays what's the problem that signal I is bigger than two is zero right right right so there's no reason that you should expect kinchin to be the right answer right？

Similarly with Hanton Wright， it is the right answer， it's known。

 it is the right answer for Gaussians。For plus minus ones。

 it's not the right answer for a similar reason， right？

The sum of AI J sigma Sigma J cannot possibly be bigger than the entry wise L1 norm of A， right？

Meanwhile， Hanr goes to infinity， but it's known what the right answer is and you know。

 if you want to look it up for yourself， there's a paper that has the right answer。

 it's due to Laawwa。When you say if I had answer， you'd be my tightest asymptotic tail bound。Yeah。

 I mean that not only is it an upper bound， but it's a lower bound。

Like up to a like it's it's the right answer up to a constant factor so like I want to bound b such that the P norm is at most C times b and it's at least C prime times b so basically it's theta b right so what I've been showing so far is just big O I've been showing that the p norm is big O of something。

😡，Whereas kind of right answer means theta of something。Yeah， so Laa。

Laawwa that that that that first that L T A L with a little thingy through it。

 some Polish letter sounds like a W A， so he has a paper。嗯。😊，I forgot the name of the paper。

 well actually I can tell you。I can tell you right and it's similar in that it just depends on the sorded values of a No。

 and he his is actually unfortunately a little bit more complicated。 So his paper is called， I think。

Taale and moment estimates for some types of chaos。 So yeah， probabilists。

Whenever they have polynomials and random variables， they call it chaos Okay。

 so this is like Raammacher chaos So when he's he's talking about moments of chaos and tail bounds for chaos he means polynomials and he's looking at degree two polynomials in that paper but。

No， it's not unfortunately it doesn't just depend on the L1 the intratroY L1 number of a he defines some like。

Restricted operator norm on a where you you know， you take the。

I don't know just look at his paper unfortunately it's not as it's not as simple as the other one Okay。

 so I think let's yeah， let me not get too derailed but yeah that's handsome right okay。And。This is。

I mean， this is the proof of Hanssonide I chose to show because it all fits， you know。

 once you have decoupling， it all fits on one board。嗯。

It's not the most general proof because it's known that most more generally Hanson Wrightite holds not just for plus minus ones。

 but for any distribution that's so calledled sub Gaussian。

 meaning that thema if Sigma I decays at least as fast as the Gaussian does。

You can basically get Han to right from that distribution as well in the notes I did have a reference to a paper of Ruleson inversion in。

In the probability review， which has the more powerful proof that that shows it not just for plus minus ones。

 but shows it for subgaussians， but。For this entire semester in this course。

 we're never going to use this handsomeson right for anything other than plus minus ones。

bothering with more general version。Yeah， so let's continue so that that's so now you've seen a proof of Hanson right you can plug that into the proof of distributional jail。

 which you saw on Monday， which implies jail so now you really have seen all details of a proof of jail。

Okay。Oh， another nice thing I should mention maybe before I move on to the last part of the lecture。

 if you remember I said at some point， I think it was maybe last week。

I was talking about like if you have the turn off bound。

And the turn off bound is giving you some failure probability of delta in fact。

 the random variables didn't need to be fully independent。

 they only needed to be lo whenever delta wise independent remember I said that at some point that fact is just like a corollary essentially of this yellow part of this board right because。

Right we know now tail bounds apply moment bounds， moment bounds apply tail bounds right and we saw exactly how to choose P right that was right when we highlighted in red。

 we chose P right here， right。So。RightIf you have a tail bound like turn off or Hanson Wright or whatever or Kinchin。

 okay， you know that you have a tail bound that implies that you have a moment bound。

But now that you have that moment bound， that moment bound again implies that you have a tail bound via Markov where you know exactly which moment you're using for the tail。

 you're using P， you know in the case of Gaussian decay。

 you're using P equal to lambda squared over alpha squared。😡，对。So， you know。

 if you just kind of backsolve and figure out what does that actually mean， it means， for example。

 in turnoff， as well as Hanson Wright， as well as Kinchen。

 that if you're if you're shooting for a failure probability of Delta at the end of the day。

Then P can basically just be logged whenever delta。Okay， which means that， you know。

 since so a quadratic form is a degree two polynomial in the random variables。

 when you raise it to the P of power， you have a degree 2 p random variable。

The expectation of this degree 2 p random variable is fully determined by 2 pYs independence。

 which is2 log1 over delta y independence， so you could have carried out your entire argument。

With your signs being too log whatever else wise independent。So for example。

When we talked about the Johnson Lewiss Straulema， we said。

 you we're going to let our matrix pi have IID plus minus1 entries。In fact。

 they don' need to those entries of the matrix don't need to be independent plus minus ones。😡。

They just need to be two log n y is independent why， because when we applied VJL to get JL。

 we set Dlta to be1 over n squared so that we could union bound over all the difference vectors。

Log whatever Ad adult says now basically oh of log in。So we just need O of log n wise independence。对。

So we already now know that。To get JL， it's enough that your random matrix only has log n oh of log n Ys independent entries。

Which means even though your matrix is big， it's M by D。

You can be represented succinctly because the entire matrix is specified by a bounded independent cash function。

Okay， does that make sense？Any questions about that？

I guess it's the kind of thing where maybe once you use it a few times。

 you'll get the hang of it and it'll be second nature but。

But you just keep it in mind that whenever you use one of these like exponential Gaussian taildowns。

Implicitly you know that the random variables that are involved only have to have bound in independence。

 they don't really actually need to be independent。ok。sorry。

 was someone about to say something before we move on to the next one？I guess I don't really。

Didn't see where they like log one of a data where independence comes from， but。Okay， yeah。

 so I didn't actually write any math down， but I guess what I'm saying is so you're， you know。

 you're applying a tail bound， maybe it's turn off， maybe it's handsomeen right， whatever， right？

Your tail bound looks something like this。You know that for all lambmbda your tail is bounded by some Gaussian thing or exponential thing or whatever。

 and we know that that implies that you have bounded moments。Right。

But now that you have bounded moments， you know， we know that。Not only do you have a bounded tail。

 but to get that bounded tail， you're choosing a very specific moment。To apply Markov on。ok。Right。

 so like。So I mean， if you're looking at turnoff， right， turnoff is looking at the sum of X minus mu。

You want taildowns on that。And I'm saying that that's the same thing as moment bounds。

Moment bounds means the expectation of this to the P of power。Right so you could write that down as。

The sum of like。Xi1， Xi2， whatever， whatever mu to some power。And then you have expectations here。

 right？And the point is this thing has at most P terms in it。

 so it's it's fully determined by Pys independence the the Xs don't actually need to be fully independent usually when we state turn off。

 we say that the XI should be independent。They don't actually need to be independent。

 they just need to be。PY independent where P depends on the failure probability that you're getting at the end of the day。

 so if you're getting a failure probability of Delta and you you basically unwind all of this。

P right here is getting set to be something like log whatever delta， that's what I'm saying。

So maybe I'll let you marinate on that。But yeah， that's all I was。You mean to say？So。

NoI didn't mean why isn't it norm。So how can you estimate LP norms and data streams we did Ps to that was like the AMSS sketch or Johnson Lidentrass。

 what about other LP norms？So definition。A distribution。Let's say， distribution。ZP is。P stable。If。

For， you know。Z1 up to Z N。IId from that distribution。 and also like。X in Rn is fixed。

We have that and let's also say we also have a Z， So Z Z went to Z N then。诶。

What I want to say is that。The sum of X， I， Z， I。Is equal in distribution。To the LPor of x。Times Z。

Does that make sense？So。It's saying that if you sum up。

A bunch of P stable random variables with different scale factors。

 what you get back is a P stable random variable， whose scale factor is the LP norm of the coefficients。

So Gaussians。So p equals2。Gauussians satisfy this， right？

If you sum up a bunch of independent Gaussians， you get back in Gaussian。

 whose variance is the sum of the variances in other words。

That Gausian is scaled by the standard deviation， which is just the L sc norm of these coefficients。

But it turns out theorem。Such a DP exists。If and only if。Z is less than p is less than equal to 2。

Okay。You know， you can look up these things so like for example， P equals one。

Is what's called the kshi distribution。Which has a PDF that looks like p of P of x is something like some normalizing constant times。

 I think y over1 plus x squared。That's the PDF。You know。

 you can prove that this thing satisfies peace stability。

 I think for for like maybe all except for a few special cases like equal equals two equals one and maybe equals a half there's no closed form for the。

Probably density function of a piece stable random variable。

 you can just prove that the distribution exists。There is a closed form for the Fourier transform of the Pf。

 So I mean， I'll just write that， you know， you don't have to。Know what I'm talking about。

 but if you just take the Fourier transform of the PDF。And evaluated at a point T。

 it looks something like e to the minus absolute value of T basically to the P。

And you you're allowed to have a scale factor here。That scale factor could be arbitrary。嗯。

And you know， this is。And maybe there's some scale fact normalizing constant out here too。

 something like that。嗯。Actually， do you have the normal constant Yeah， I'm not sure。

 but it looks something like this。嗯。RightAnd I mean， and the fact that this isP stable， I mean。so。😊。

I guess yeah， what you always have is a closed form for the Fourier transform。

 but what you might not have as a closed form for the actual PDF and the fact that something with this Fourier transform works is somewhat obvious because what happens when you add independent random variables。

 their PDFs canvol。😡，Which in Fourier land means their Fourier transforms multiply。

Which means that kind of， you know， if you have e to the minus t， alpha1 to the P。😡。

Times E the minus t to the P alpha 2， you know， just， you know， you know that right， E to the A。

 E to the B， I'm just using is E to the A plus B。 So in other words。

 if you have E to the minus T to the P times alpha1 times E to the minus T T to the P。

There's no minus here， I think。UDoes the minus， I guess for Gaussians， there's no minus， right？

I think maybe there's no way。嗯。either minus or not， those' say there isn't。I'll say there is。

 I don't know。But。I might have a typo there on， I might have a sign error times alpha2。

 right this is equal to e of the minus T to the P。Alpha 1 plus alpha 2。Okay。

 so like that already gives you kind of a sense of why the Fourier transform。

 this is a good Fourier transform to have because it says if you add two independent PC of random variables。

 you get backup piece table random variable， it's just that the scale factors。嗯。

The scale factor changes。Okay， good。嗯。😊，I guess what you really want to know is。Well yeah。

 that's all I wanted to say about maybe piece table random variables。

 just let use the fact that they exist and they can be efficiently sampled。

So now how do you use that for estimmanating LPnos of data stream， so streaming？Basically， turnt。

You want。A one plus epsilon approximation。Of the LP norm。

Which is defined to be the sum of Xite in the P。To the1 of P with probability at least23s。

So InAC in I think 2000。Consider the following matrix pi。Each one of these entries is like ZIJ or Z。

 let's say ZRJ is P stable。So what you do and you estimate。Estimate。The alper of x。

As the median entry。Of。You look at pi X。I absolute value。So like let's say y is pi X。

 so this is just Yi。So that was his algorithm。And properly normalized， so you normalize。ZP。

 so that this is true。 So Zp looks like this， right， It's some distribution。I mean。

 it kind of looks like a Gaussian distribution it's bell shaped。

 its just that the smaller you make P， the heavier tail it gets right so Gaussians decay like even the minus lambmbda squared。

You can show that a P stable random variable for p for p less than two。

 it doesn't decay like e to the minus lambda squared， it decays like1 over x to the P。Okay， actually。

The PDFf。Let's see the PDF is like when its to the p plus1， I think， yeah。

 so the decay is like when its to the P。And when I say normalize。

 so you're going to normalize it so that。If you look at the interval from 1 to1。

This area is equal to a half。So in other words， if you take the expectation of the absolute value of a P table random variable。

 it's one。I mean that that's just a matter of scaling right if you have a P stable random variable and you just like scale it by some other constant you still have a P stable random variable so what I'm saying is take your P table distribution and scale it so that this is true so that the amount of area in between minus1 and1 is exactly a half。

And then use that as DP， and then this is his algorithm。

He maintains pax and memory and he outputs the median as the final thing。So now the question is like。

 why does this work？So。This is a question。Is there some like something interesting happening when p is equal to two or as P' is getting closer to two。

 like it seems weird that all of a sudden you get really fast tail decay when p is equal to two and then it slows down considerably as soon as you know you have one plus epsilon。

Right， so okay， so one thing that's magic about peak equals too is you know。

 maybe you've heard of the central limit theorem， right， which says。

If you sell a bunch of independent random variables， it starts looking like a Gaussian okay， now。

 but there's a caveat， the central limit theorem only holds when the random variables you're adding have bounded variance。

Right so you could so you could say like wait how could how could a one stable distribution exist like central limit theorem says if you add a bunch of copies it should look like a Gaussian。

 so like shouldn't everything be like kind of too stable or something。

 but but you know there's that catch of bounded variables right？So except for p equals two。

 none of these distributions have bound variance， in fact。

All of these have infinite P norm like so all p stable random variables other than p equals2 have infinite P norms。

 they have infinite Q norms for any Q that's at least P。😡，So in particular。

 like the one stable distribution， the koshi doesn't even have finite expectation。

 it has infinite expectation。Okay， got it。And then kind of once you get。

 once you P store is getting bigger than two， it's like， well。

 you can't have something three stable because now central limit， you know。

 you can prove you can prove that。😡，You know， if you're P stable。

 your tail decay has to be at least as fast as one of x of the P so if you're 2。1 stable。

 you're decaying at least as fast as one over x to the 2。1， which means you have bounded variance。

But then central limit theorem applies， right， so you can't so yeah。

 that's that's why two is kind of a magic number。So so that's his algorithm and now let's analyze his algorithm。

So。😊，So you're maintaining y， which is pi times x， notice that like y is distributed like the LPer of x times a PC of random variable。

So what we're saying is like if you look at the expectation of the indicator function。

Of minus11 applied to y， let's say， Y R divided by the lp of x。This is a half right。

 so right the indicator function of an interval is just I'm saying。One。

 if x is in applied to x is1 if x is in the interval and zero otherwise。Does that make sense， I mean。

 this thing is the same thing as I'm just rewriting in a fancy way， the probability that YR over XP。

也不行。Is in the interval from minus1 to 1。The expectation of the indicator of that interval is the same as the probability that you're in that interval。

Okay， and since I scale the distribution to the median is one， then I have exactly this now。嗯。😊。

What does the distribution look like， I mean， take my word it looks like this。And you know， here's。

Here's minus1 and here's one。What if I went to？One plus epsilon。And what if I went to， you know。

 like one minus epsilon？So question for you。How much mass is in that？

How much mass is in that yellow region， like， what can you tell me about that？

don't even me an exact number， but rough estimate how much mass is in the yellow region？

Probability mass。Right。It's theta of epsilon。Right because it's basically upper bounded and lower bounded by different rectangles。

And these rectangles have some heights that， you know are some those heights are some constants that depend on the distribution。

 but there's some fixed number。And the width of this rectangle is epsilon。

 so this area is like theta epsilon。And you know， that other red area is also theta epsilon。

OkaySo now what I'm going to do is the following， I'm going to look at。The sun。R goes from one to M。

Let's say1 over M。The indicator function of  -1。Minus epsilon，1 plus epsilon。

Y R over Al XP this thing。So okay， so what is this mouthful？Actually， computing， it's computing。

What fraction？So I'm maintaining y， which is pi X， So y has R different entries， right？😡。

And different injuries， right so why。Y is like an M dimensional vector？Because pi is MRrose。

So it's like what fraction of these M entries？😡，So I'm counting like what fraction？

Of the M entries of y。Satisfy。The absolute value of YR。Is that most。你食乜嘢。

1 plus epsilon times the LPRX。That's what this thing means。Does that make sense？And let me ask you。

 what's the expectation of this？Right I'm basically saying I'm moving a little bit into that red region。

 I'm widening the interval instead of minus one to one。

 I'm going minus1 minus epsilon up to one plus epsilon。

 so I'm gaining a little bit more probability mass， namely that red probability mass。😡，So this。

 by linear expectation。Is a half。Plus， data Epsilon。Does that make sense？Similarly。

 if I look at the expectation of one over m some agos from 1 to M indicator of minus1 plus epsilon。

1 minus epsilon。Of YR over LPR。This is a half minus theta epsilon。And this is basically saying。

What fraction。Wait， the the the diagram that you have written that you've drawn is different than the one that you're。

Taking the expectation of， right？No， I think it's the same right Well， you have。

 I think I think it should be an interval to the left of minus one， right？Well， no， okay。

 so because it says1 I'm doing on both I'm doing it on both sides， right。

 So this this is minus one oops。This is -1 epsilon。 and this is like -1 plus epsilon。 So I'm gaining。

 I'm gaining like。There's being like epsilon on both sides right Yeah。

 but state epsilon plus state epsilon is state epsilon。So' so in the first equality。

 I'm gaining the two red regions in the second equality， I'm losing the two yellow regions。ok。

So let's imagine that this is not just having an expectation。

 but this is like actually happening so what am I saying i'm saying that。😡。

More than half of the entries are less than one plus epsilon timess theLP norm。😡。

And less than half of the entries are less than one minus epsilent times the LP norm。

Which must mean that the median entry。Is between one minus epsilon and1 plus epsilon times the LP norm。

 which is exactly what I want right the median is my estimator does that make sense？😡。

So if both of these things actually happened and didn't just happen in expectation。

 I'd be very happy。So now I want to argue that it's not just happening in expectation。

 but it's actually happening with good probability。😡，We're going to use our usual trick。

 which is chubby sheve's inequality。Or you know like。If it helps， you know。

 let's let me get rid of the whatever in here and move it outside。So this is basically M over two。

This is basically M over two， plus stateta epsilon M and this is M over2 minus theta epsilon M。

So what I'm interested in is something that looks like， the variance。Of the sum of the indicator。

 blah， blah， blah， of like YR of X。Okay。Now the variance of independent random variables。

 like when you have independent random variables and you sum them， the variances add。

So what is the variance， give me an upper bound on the variance of one individual indicator function。

The most trivial upper band you can give me。One point yeah one right the indicator function is always between zero and one so the variance can't possibly be more than one that's like the absolute most trivial bound you can give me so i'm just going to say that this variance is at most M。

😡，So by chubby chef's inequality。Chby shop basically says that you're usually within a standard deviation of your mean。

 and that's what it says in words。😡，So my chby chef's inequality。

 this is usually this plus or minus o of rooted。And this is also plus or minus o of rootta。

And I want to make sure that this O of Rum error from the standard deviation。

Is not canceling the epsilon M。 So basically what I want to make sure is I want to make sure that this root M factor is like much less than epsilon M。

😡，Which is the same thing I say I want M to be like at least what of Repsilon squared。That's it。

 I'm done。Does that make sense？so we've just shown that as long as you have what rhspson squared rows in this matrix。

you succeed with probability 91。That's implied by Chevysha。Okay。Now how do you derandomize this。

 this is a giant random matrix， it seems kind of hard because we're very much， you know。

 in these two locations right here。😡，We're very much using independence of the entries in the matrix because we're saying if you sum up a bunch of independent copies of P table random variable。

 you get back a piece table random variable， that's not true necessarily with some pseudo random version of the PC table random variable。

😡，And you know so。We're also using it here。To say that the variance of a sum is equal to the sum of the variances。

But that part is easy right variance of the sum equals sum of variances that only requires two wise independence。

 so what we can say is look。😡，We had， you know， each， you know。

 there's some random seed that's being used to generate each row of the matrix。

We can just make sure that those seeds are only from a parawise independent family。Okay， so。

 you know， each seed， if you look at each seed individually， that seed is generating a uniform row。

 like uniformly independently random。😡，But the seeds from row to row are actually only two wise independent。

 Okay， so we we've already made some progress。The next thing that we wanted we would want to show is to show that。

If the if the if the， you know basically we want something like this。

 we want something like this to still be true。Even if the PC random variables are not fully independent。

 but almost fully independent， they're like KY independent。And that is true， so theorem。

If the Z I are。K wise， independent。For K being at least like one over epsilon to the P。Then。

For all intervals A， for all， let's say， intervals A B。诶情况 a b。

If you look at the expectation of the indicator function of baby。

Let let's say the ZI primes are Kwise independent and you look at。The sum of ZI prime Xi。

This is equal to the expectation of the indicator AD。

Of the sum of the ZI Xi up to an additive like epsilon term， epsilon additive epsilon。

 where these are actually IID。So this is a theorem about like the you know。

 approximate peace stability， it says that if your P statement random variables are only Kwise independent and not fully independent。

😡，Then the city， I mean， notice that like。Notice that like the indicator function of。

Minus infinity A。Thats this is just called like the CDF， right。

 the cumulum density function or distribution function。So I mean， what this is really saying is。

If you have KY's independent pieceab random variables instead of fully independent pieceab random variables。

😡，The CDf。Of some of ZI prime Xi almost looks like what it should look like at every point。

 the CDF will be correct up to an additive epsilon error。😡，So this is a theorem that was proven。

By Daniel Kane， myself and David Woodruff。In 2010。So I'm not going to prove that。

 unfortunately that is actually pretty complicated。But in the last couple minutes。

 I do want to talk about this general hammer of like。

 you know In when Indych wrote his paper it was not 2010 yet， it was 2000 it was 10 years before。

 so how did he deranize his algorithm？He used something called Nissan super randomum generator。

 and the idea there is you can define what's called a branching program。

This is this is some model of computation that's supposed to represent like space battery computation。

 The idea is you have like a start state。And then you， you see the first input。

Let's say that your inputs are bits， but they could you know they don't to be bits。

 they can be from any alphabet， you know you see a zero or you see a1 that's going to change the state your of your algorithm。

 you're going to integrate a new memory state based on what you see。😡，And then from here， you know。

 you see a zero， you see a one， and you know， there can be overlap。So here he says01， here he says01。

And you know， there's basically like a layer over time。

 so let's say this is time where you're seeing inputs one by one。And you。

 you just basically have this kind of graph。Where every node has out degree to。Does that make sense？

And then this is kind of the final time step。Where this is your final memory configuration after processing the entire input。

How is P being used here， where are you so no are you asking about PE？There's oh P so yeah。

 the ZIA prime are P stable， so P is the stability parameter。Does that answer your question。Yeah。

Okay， so。You know， you can imagine that at every time step。I'm seeing， you know， either a zero or1。

 a zero or a1， a0 over one。 imagine zero or one。And what you should imagine is that kind of。

This input the zero1 input is like the specification of the hash function I'm telling I'm first I'm telling you what H of one is then I'm telling you what H of two is then I'm telling you what H of three is I'm revealing H bit by bit。

😡，Okay， and then I'm saying like based note， now after you've NAF I' revealed all of H。

That implies some kind of probability distribution over your final memory state。😡。

RightNow if those zero ones had actually been independent。😡。

There's some distribution that you would have on your final memory state。

And now I could say what if the zero ones are not actually independent。

 but they're generated by an algorithm， a pseudorandom generator like KY's independence or some other method。

😡，Is your distribution over final states still approximately the same。

 because if it's still approximately the same， that means that if you used to be correct with probability two thirds before。

 you'll still be correct with probability approximately two thirds now？😡，so that's what I want。

 I want to generate these red bits in a way that that keeps your final memory state distribution similar。

😡，Okay。So。Does that make sense？That's the name of the game。Now， if you look at here the。

Kind of the number of。Let's say nodes。Per layer。Is called the W of the branching program。

And this is basically2 to the S where like S is the memory， right？

Because if you have aspects bits of memory， you have two of the best possible memory configurations you could be in。

Okay， so。So now what so now theorem。And this is due to Noam Nisan in 1992。The if。

The branching program has， and by the way， this is called。

 I should say this is called read ones branching programs because you're never allowed to like go back in time and read a previous input。

 you have to read the inputs in this kind of streaming fashion。

So if you have a read once branching program that has， let's say， L layers。And with。嗯。With2 to the S。

Then。There is。An algorithm。Let's call it a nassan。It's called a pseudoranum generator。

And let's call this branching program， let's call this P for program。Sitor random generator。

Such that。If you look at and in his model， in his model。The out degree。Is2 the S。Every layer。

So he's imagining that you're not just reading one bit at a time。

 but you're reading S bits at a time。Okay， so since you're reading S at a time。

 there are two to the S out arrows depending on what you just read。嗯。Such that if you look at。

The distribution was apply P。So the uniform distribution。On on L。Let's call it。LS bits， right。

 there are L layers。Each goinging from layer to layer， there are S bits that you're seeing at a time。

 so just imagine you have the uniform distribution on l times S bits。😡。

Okay and then you apply P P is this branching program。

 it's an you know you can think of P as as computing something namely it's computing what its final state memory state will be so P of a string is just what's the final memory state of P when you run it on that string。

😡，So P on a uniformly random string is a probability distribution over final states。

So you look at this distribution versus P applied to Nissan。On a uniform distribution on， let's say。

 qubits。So now you generate Q random bits， you feed that into thesan， thesan will spit out LS bits。

 you feed that into P。😡，These distributions are close。Where Q。Is。O of S times log L。

So I think I'm busy out of time。But。What this is saying is that。嗯。

You have some low memory algorithm which you're going to model as a branching program okay that's that's your branching program P maybe'm I'm going to release the homework very soon maybe I'm going to do that I'm going to make you do this for index algorithm and do we randomize it using using this theorem。

Wal you so make you some practice with it， but you know you have a low memory algorithm P and I say what if I fed P uniform random bits I'll have some distribution on its final memory state and then you say。

 okay， I'm not going to feed it uniformly random bits instead。😡，Instead of taking LS random bits。

 LS is very big， think of L is huge， let's say So instead of LS random bits。

 which is a huge number of random bits， I'm only going to take Q random bits where Q is only log L。

 It's not L。 It's log L， so it's much fewer。Anason， anaon you can think of as like a function。

That takes。Here random bits and spits out。LS random bits， okay。

 those LS bits could possibly be uniformly random because you took few bits and you stretched them out into more bits there's no way those things are independently random。

But from the perspective of P it looks random， so the distributions between P ULS and P A Nassan U Q are close in L1 and if have if you're not familiar with this close in L1 basically means that there's no you know if if you're epsilon close in L1。

😡，It means that there is no way to distinguish the distributions with distinguishing probability better than Epsilon。

So that means that if your success probability used to be two thirds。

 your success probability is still two thirds up to an additive epsilon so now here epsilon is one over two to the S so your success probability used to be two thirds now it's still two thirds up to an additive error of one over two to the S okay so that's Nissan's theorem and you're going to have practice applying it in you know index algorithm on the homework so final questions I know I just I went over time by five minutes。



![](img/a5cfecf4ae2613500e2b8655c138f240_2.png)