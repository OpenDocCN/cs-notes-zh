# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p21 P21 Suprema of gaussian processes, Dudley’s inequality, generic chaining, -BV11zi7BjEHu_p21-

![](img/63eeb882320375b4665314a546e0be3d_0.png)

Do you mean to be muted？Oh I did not mean to great， so just to。

Just to go back so today we're going to talk about something known as Gordon's escape through the mesh theorem and applications of it two dimensionality reduction like JL So there there are three places where we've seenuclidean dimensionality reduction so far in the course。

One is the jail Emmama， so you're given。设置CPS。We're given X。Which is a subset of let's say R D。

 that's finite。And you want。That for all。X， Y， little x and little Y in capital x。

The norm of pi x minus y。Or I should be ready like this。

The distance after you apply pi between x and y。The square distance is roughly like white used to be。

In other words， if you define。其余。Which is the set of all vectors x minus y normalized by the norm。

What you want is that。The maximum。诶 let's say z and t。嗯。I the L number squared-1 set by such slide。

有 yes。That's what you want in jailL。And here pi is M by N or M by D， and you can get M to be。At most。

 it's a constant one over Epsilon squared times log of。嗯 if you。王源。Okay so which is you know。

Basically， one ofrupps squared along the size of T。that's jail。Now。

 if you look at subspace embeddings。You all had a PSet do recently PSet two。Where， you know。

 basically what you want is so E。Is a it's a D dimensional。嗯。Some space。W are in。

So you can think that T now is basically E intersected with the unit ball。Every is。It one。

And then what can you get away with on the P set you should get with D over Epsilon squared？

You did that by applying a。By basically applying JL to a net of the subspace of the unit volume in the subspace？

And then there's also another part of that PSet problem for RIP matrices。Wherere now。嗯。

T is basically the set of all。Kase sparse vectors。Interected with the unit all。

A rate being a ball there。 And then there you got that M was at most， something like。K times log of。

You， E and every， even they just。Right， so these last two examples。嗯。They don't I mean。

 they do follow from JL after you apply a net argument。

 but they're not just immediate applications of JL， right because。These tees are not finite。

 so log T would be infinite， which wouldn't make sense。 You have to say more。

So what I'm going to show you today is a general theorem that applies all three of these kind of。呃。

Automatically。And more， Okay， so the general theorem。This is due to Gordon。乃前 eighty eight。Is。死啦。Hi。

P is an M by N matrix。And。The entry is。Our IID normal。Mean zero variance one over M。

 so basically just take standard Gausians and divide the matrix by root M。

Then for all T subset of the sphere。So now T is everything in T has unit dorm。嗯。This will be true。

An expectation over pie。 the soup over X and T。呃 pi X。Squared minus1 will be at most epsilon。

As long as。The number of rows of pie is at least some constant times the Gaussian mean width of tea。

Squared over echelon squared。Okay，So that's the theorem。If you haven't seen this before。

 you might actually let me know just to。Just to be less confusing， I'll call use a different letter。

 I'll call this W。嗯。Where。WT is the so called。gaian。你不。M。So what does that mean exactly？

The definition of it is。You take a vector G of ID standard normal random variables means zero variance one。

And you look at the maximum overall X T of G dot X。And the expectation of that maximum。

The expectation of that maximum is。The definition of the Gaussian mean with。Okay。

So I'll show you quickly why。This is stronger than than all the previous three things。

 This implies JL automatically， it implies subspace embeddings with Drupson square rows。

 It implies RP matrices with the right number of rows。嗯。And then。Once I show you that。

 and maybe I'll show you another example of kind of controlling the Gaus I mean with。

Then we're going to move on to like how do you prove Gordon's theorem and actually。

Gordon had a proof that was specifically for Gaussians it didn't work for other distributions now what we know is that this theorem holds even if the entries of pi are sub Gaussian meaning they decay at least as fast as the Gaussian so for example plus minus ones would work bottommas would work。

And today what I'm going to do is I'm going to show you how to prove Warren's theorem for Radamaers。

That's going to be implied by something called the majorurizing Mesure theorem。

 which is a bit more complicated that I'm not going to be able to prove today。

 but then given that majorurizing measures theorem I'll show you how I'll show an argument from 2014 by Kramer。

Mentelson and Rahu John。Any hear from that。Okay， so before we move forward。

 are there any questions about the statement of anything I've said so far？Yes， sorry what is S？

Where did I write， oh， I just mean the unit sphere。So S N -1 is the。

The set of all vectors in dimension N that have Euclidean norm exactly one。O。Mi see。

So if you look back at。I mean， here I could have， you know， I could have actually。All these things。

 that could have。So just doing that。你行没说。Right， so。

Because as long as Pi preserves everything out the sphere。

 it preserves everything off the sphere as well because it's linear。Very good。

 so now I want to show you like， okay， so we have a bound in terms of this weird quantity WT。

Like how do you， how do you even understand what WT is like if I give you a T。

 how do you know what WT is so that you could actually apply this theorem？And in particular。

 how do you do it to imply these three bounds that are boxed on this whiteboard over here？Okay。

 so let me show you So next。actually， what's the distribution on G in that expectation？

G distributed like a normal random it's a vector。It's meana zero。

And the covariance matrix is identity。So in other words。Like G is an n dimensional vector。

Where each GI is independent and means zero variance one Gaussian。Yeah。So next。

 how do you ban I have a question Yeah so should the entries be like normal what variance one over n because wouldnt that lead to like isotropic like grows I think。

no有系诶。So this， sorry， just to be clear。This G right here。Is not for pi for pi。Oh。Yeah。

 I didn't where I am。All right， it looks like M， sorry， that's an M。And like， Mary。Oh。

 it shouldn't be n so that the rows are like isotropic like。Well。

 there were M rows right so I mean just think about it like this pretend pi only had one row pretend pi is a vector。

And now you look at the x so like let's call the row the single row of pi is G， a Gaussian vector。

And look at G do x and look at the expectation of G dot x squared。Right。Like。

The expectation of G dot x squared。This is basically pi Xl to norm squared if it's just one row。

This is equal to the expectation of the sum of G Xi， would a row vector correspond to M being one？

Yes， exactly oh I'm just I'm just trying to even see that you're not exnc divide by N。

 you should divide by M。诶I see。Yeah because just taking the dot product of a single row and squaring it gives you the correct expectation。

 so if you have MRs and you're adding them up you need to divide by M to get that expectation right。

Does that make sense yeah yeah， okay， thank you so let's so next up。

 how do you bound the Scotian mean with anyway？嗯。So。So how to Bo。

gotSo it turns out that there's an optimal answer that's known as generic chaining I'll say what it is。

 but i'm going to build I'm going to work our way up there。So the easiest way is the union bound。O。

So remember now， G dotX is the sum of Gxii。And the Gs are independent。

 So you're sewing up a bunch of Gaussians。 Each Gaussian has variance， X I squared。

So what's the variance of the sum， it's the sum of the variances， which is the sum of X squared。

 which is one because all the X's are on the sphere。So each one of these G dot xs is a Gaussian。

And you have T Gausians or T， let's say T is the size of T， sorry for overloading variable names。

So if you have tea Gaussians and you take a union down。

 the problem is's probably not bigger than log tea。So kind of trivially。

 the Gaushem with is always at most root log tea， so let me write that down。

So W of T is equal to the expectation over G of the soup。Or X and T of G dot X。

Which is equal to the integral。 well， let's say that's at most。

Is that most putting the absolute value there？Which is equal to the integral from 0 to infinity of the probability。

At the soup。Of G dot x。Probably over G super x and T。Is bigger than Lambda D Lambda。

 actually let me know call Lambda U DU。Okay。And then I'll just break up the integral into two parts。

 This is the integral from zero to lambda of that probability。Plus。

 the interval from lambda to infinity of that probability。Did do you do you。

And I'll choose Lambda to optimize this calculation， but probabilities are always at most one。

So this is atmost lambmbda。And for this part， I'll just use the union bound。So this is u most。

The integral from zero to infinity。Of the sum。Overall。Aentee。Of the probability that G dot x。

Is bigger than U D U。So that this is the union down。And did a union band over X。

This I can just use Gaussian decay G dot， this is what we said， G dot x is a Gaussian。

And so Yaoan with variance one。Once the probability that a Gausian is bigger than you。

 it's like even the minus u squared。😡，So this is at most。

 this is just a property of the tailbound of Gaussians。

2 e to the minus u squared over two or something。嗯。

So this is at most now the integral from zero infinity of the size of T because I sum over Rox in T。

And2 e to the minus u squared over two do。Should be anywhere from lambda tofinity。Yes。😊，嗯。O。

And this is going to be some like。T times E。 so 2 T times E is a minus theta of like lambda squared。

行。So now overall putting everything together。We have that。 It's at most， lambmbda plus。

T times e to the minus theta lambda squared。So now what I'll do is I'll optimize。By choosing。

Lambda to be some subto constant， basically square log the size of T。And then if you do that。

 you'll get here this is that most square root log the size of T。Okay。So this is just always true。

The y should mean with is always at most root log the size of see。I mean。

 an assuming T is a subset of the sphere。So you plug that into this bag。What do you get？

Root log T square， which is log T of Ru line squared。That's exactly jail。喂。So。Already。

 just kind of trivially bounding WT via the Union bound gives you JL。

 what mean once you have Gordon's theorem。嗯。And you know。

 I should say like you know this this root log T can actually happen if， for example。

 you know when is this tight， it's basically tight。When。

The GI is actually when the different Gausians are actually independent。Okay。

 when are they independent， they're independent if the x's are orthogonal。😡，So for example。

 if your set of vectors is the standard basis of vectors。Okay。

 then the mean width will be theta log T。When is root log T not tight？

It's not tight when the vectors are not orthogonal and more specifically。

If you really want to make it small， like the extreme case。Is that all the vectors are the same？😡。

If all the excs are the same then。Of course， a union bound is wasteful because if one random variable is small。

 they're all small because they're the same。So kind of the thing to the thing to keep in mind is okay。

 so they're not exactly the same， but like， let's say all the vectors and T are really。

 really close to each other。They're like， you know， they're clustered in a very， very small region。

Then again， the y'o should mean with small。ok。So what's one way to bound the Gasian with by something small when it is small。

 let's say when the points are really well clustered。Well， technique number two。

Is what I'll call using an Epsilon net。你觉得。So we know what Epsilon nets are。Why are they useful here。

Say tea prime。Is an epsilon be？啊知。Under L2。And like。

I' theI'll use the notation that like x prime is the closest thing in the net。

 so for all X and T there is an X prime and T prime。

Such that the distance between x and x prime is at most epsilon。Now what。

So WT is equal to the expectation over G the soup。Of G dot X。

But I can write x as x prime plus x minus x prime。So this is equal to expectation over G soup over X and T。

Of G dot x prime plus x minus x prime。Wch is at most the expectation over G the suit？

X and T of Ges prime。Plus， the expectation over G soup X and T。F G got x minus x prime。Okay。

 now what is this。This by the last slide is at most the squared log of the size of T prime。

And the point is。Even if T is big。If it has a very small net because the points are very closely clustered together。

 then I only have to pay root log the size of the net， not root log the number of points。

And then here， what do I do？This is certainly by Cohi Schwartz at most， the normal x minus x prime。

 which is epsilon times the norm of G。But the expectation of the norm of a Gaussian vector is root n。

 so this is at most， so let's say expectation of G， so this is at most epsilon root n。

So altogether there ut most root log。If you remember this notation， if not， I'll remind you。

 so T L to Epsilon plus epsilon。Right， so。Remember Capital N is called the covering number or the entropy number。

 what this means is what's the smallest size of an epsilon net of T under L2？嗯。And what's Epsilon。

 Well Epsilon can be anything， we can choose Epsilon to optimize this。

So this is at most kind of the in overall epsilon。We can choose Epsilon to minimize this expression。

So for example， we could choose epsilon to be zero。If we choose epsilon to be zero。

 we're saying that our net has to be T itself。And then you're just reducing to the previous whiteboard。

You're just going to log the size of tea。But you're allowed to choose any epsilon in between as well。

Okay。So that that's and sometimes this gives you something better。You can take it one step further。

And you could do Duley so called Dudleys inequality。对。What is this？喂。I'll call it。

I want a good letter。Q Q S。Be a one over to the S net。诶 tea。Under L2。Okay。

 without loss of generality。T is finite。Why is that without loss of generality？

Because what I can do is。I can write。嗯。So if I just go back。Go back one slide to the Epsil network。

So I know that， you know， I'm only considering Ts， which are subsets of the sphere。

And the sphere itself has a bounded size net right we know that the sphere itself has an epsilon net of size at most water or epsilon to the dimension。

So what I could always do is。I could just apply argument to。😡，Okay。

 I can apply an argument to to a very， very tiny epsilon。

 like as small an epsilon as I want so that this thing basically goes to zero。

And then what I could do is I can apply， I can now apply whatever argument I was thinking to apply。

To this。Right kindind of what you can think of what you think of the Epsilon net argument as saying is。

Without loss of generality， I can always assume that I'm trying to bound the mean with and with finite set。

Here I bounded the mean width of the finite set T prime by using the Union bound。😡。

But nothing forced me to use the union down。I just basically reduced to another mean with problem right this this is。

This is the mean with of T prime。So whatever tools。

 whatever more sophisticated tools I have foring me with。

 I could use those tools to bound me with a T prime。

So that what that's what I mean when I say without loss of generality， you know。

 pretend that T actually is T crime we already approximated by a super super fine net。

And then now we're just focused on a finite thing。And now I say let。X。X， S， be the closest。

Points in Qs。七器。😊，Now observe， I can write。嗯。I can write X。As being x0 plus the sum。

As those from one to infinity。Of。X， S minus X S minus1。Does that make sense， why。

 because let's just think about this。So let's imagine expanding that sum just one summit at a time。

So initially the right hand side is just x0。Once we add in the first sum man。

 it's x0 plus x1 minus x0， so it becomes x1。Then we add in the next sum。We add x2 minus x1。

 the x1 cancels now we have x2 so every time we add another sunand。

We basically we're getting kind of the next level of refinements for x in the next net。

So it's going to be x3 there's going the x4， there's the x5。

 and basically that's because t is finite。At some point。At some point， QS is just T。Right。

Once one over two to the S。Once1 over two of the s is smaller than the smallest。Intro point。

 intratro set distance。We're basically just forced we're forced to set QS toBT。So at some point。Like。

There is an S star such that once S is at least S star。X S has to equal x。In other words。

 even though I wrote this as an infinite sum， it's really a finite sum because beyond a certain point。

 all these differences are actually zero。So each act like us gets its own access。细声我睇。

So each point x goods its own x 0， x1 up to。Yeah， well， yeah， x 0， x1， x2， et cetera。

 is like a sequence of points that。More closely more closely。

 they converge to x and they more and more closely approximate x。

Because xS comes from a1 over2 to the S net， so the distance from x to XS is at most1 over2 to the S。

There might be different X's that share the same excessS， right？The original X is very huge。

 excess is some smaller set。只是怎么。O。ButYeah， it should like let access be the closest point in QS to X。

Instead of two tea。Let X be the closest point of Q has2 x， Yeah， I should have said that your point。

Yeah， okay， so this implies that。G dot x is equal to like G dot x0。Plus， the sum。Of。G dot X S minus。

Right。So this implies that the expectation basically。Just remember what does the new with mean？WT。

 which is equal to the expectation over G of the suit of G X。Is equal to。

I'll just do the soup separately， it's that most。The expectationation over G of the soup。Of G do x 0。

Plus， the sum s goes from1 to infinity of the expectation over G of the suit。X t。

Of G dot X S minus x S minus1。ok， so。Whatever our， I mean， whatever our point is， I mean。

 whatever our set T is。Like it's contained in this sphere。So for Q0。

 Q0 has to be a one over two of the zero net， so it's a one net。So I mean。

 we could just set Q zero to be the  point zero， the  point。 zero is always within one of everything。

So theres no， that means there's really no soup here because there's only a single x0。Which is zero。

 So I mean， this basically I'm just saying that this whole thing。诶 little thing。This is0。你觉。Now。

 if you look at this。What can I tell you about that？X S minus x S minus-1 by triangle inequality。

Is is equal to， well， first of all， it's equal to。X S minus x plus x minus x S minus1。

I just added in some traffic X and then by triangle inequality。AndBut you know， tri。

Is at most the distance from x to XS？Plus， the distance from x to x S-1。Which is at most。You know。

 three times。What over2 to S minus1。In fact， let me just write it as。Six times y over2 to the S。

 so it's big O of y over2 to the S。嗯。So right we talked about this。

 like if you have a set of unit norm vectors and you look at the mean width。

 you get at most square root log， the number of vectors。But now the vectors are not unit norm。

 they're of norm at most six over2 to the s， so let's say they're normalre instead of norm at most one。

 they're all norm at most alpha。😡，So you could just apply the previous reasoning， you know。

 you could， for example， just normalize all the vectors by alpha。😡。

Now they do have att most unit norm。Okay， and then you get root log the number of vectors and then put the alpha back。

So all I'm trying to say is that this thing now。Is that most？

Kind of the max norm of anything in there， which is1 over2 the S。

 6 over to the S high square root log。How many vectors are there of the form？Xs minus excess minus1。

Well， the number of such vectors is at most。The size of Qs times the size of Qs minus1。

QS is a finer net than Qs minus1， so QS is bigger。So， this。Is at most the size of QS squared？

But like log of the square and log without the square are the same thing up to a factor of two。

 so I can pretend the square is not there。So， this is。This is u most。

Basically log one half the size of QS over2 to the S。Which is， you know。

Log to the one half of the covering number of T L 2。What or two v S divided by two v。So， all in all。

What we've seen here is that it implies that。The mean width of T is at most the sum S goeses from one to infinity of1 over two to the S times squared log。

The covering number of T with respect to L2 with radius1 2 yes。This， by the way。

 is called Doley's inequality。Oftentimes are people write Dunley's inequality like integrity。

It's a very like well known theorem， you can find it in textbooks。

Oftentimes when people write it in textbooks， they just approximate the this sum by an integral。

 you know， like the usual trick of。I mean。我 should你 say。

So you can think that you're plotting something where。you know， you啊。W a blog。Remember。

 I don't know whether it's increasing your be。But， there's the usual trick when if you have a set of curves like this。

And you're， you know， you're looking at this area， you can just。You can just like。

Bound that by like the area under this curve。So you can do the same kind of reasoning here and say that actually this thing up to a constant is at most。

The integral。Of square log covering number T L2 U。自 you。A row， A row from 050。

So U is basically like the one over two to the yes。Writing it as an integral or as a sum。

 I mean it doesn't really matter， okay。I'm just letting you know that if you Google Dos inequality。

Youll most likely see it in the integral form， but it's。It's the same as writing a song。Okay， so。

This deadley's inequality is already good enough that you usually get like pretty decent results using it。

There's one more level of sophistication called generic chaining you can come up with examples。

You can come with examples where Dley's inequality actually gives you the wrong answer。

But there's a theorem that says that。Whatever answer you get from Dudley's inequality will only it can only be off from the truth by at most a log dimension factor。

So here we're in dimension n， let's say， soll it'll most overestimate the mean with by a login factor。

And an example where that happens is if you set T to be the L1 ball。Okay。So。Imagine that。

Imagine you looked at actually the expectation over G of the soup。Over x in the L1 ball。

Of radius1 G I X。So even forgetting randomness。What is this？

What is the soup over exiting the L1 ball of GDtX？The norm of G， which norm？呃。Without thou one。

It's's thefinity norm yeah yeah， so the Efinity and L1 are dual norms if if you're trying to maximize this。

But you should do you should think that like。Since some of the X's have to be one， or I mean。

 some of the absolute values of the X's have to be one。

You can think that like what this is doing is it's averaging the entries of G。

It's doing a weighted average of the entries of G where the weights are the X sizes。😡。

And you're allowed to choose the weights to maximize the weighted average right So if you're trying to maximize the weighted average and you can choose the weights。

 what should you do， you should put all the weight on the largest coordinate of G。😡。

So whatever the largest entry of G is， you make that X either be plus1 or minus1 whatever it needs to be to basically it should agree with the sign so that you get something positive when you take the product。

So then this soup will be the Linfinity norm G。Okay， so G remember is an n dimensional Gaussian。

 each entry is like an independent Gaussian so you have n Gaussians。

 you're taking the L infinity norm so that's the maximum of n Gaussian so what what do you expect what should the expectation be。

What's the expectation of the maximum of N Gaussians of N independent Gaussians？

We did it already root login yeah square root login right so we already know what the right answer should be the right answer should be root log in。

And if you do， dudley's inequality on this。And you try to integrate squ along of the covering number。

It's， I mean， it's not trivial to it's not completely trivial to figure out what the right covering number is but it's doable and I promise you that if you do it。

 you're going to get lo to the 1。5 end。So you're going to be off by exactly a login factor。

And you know， and the reason is because Dubley's inequality itself is suboptimal。Okay。

So more there is one more level of sophistication。That always gives you the right answer。

 no matter what T is。嗯。And I have a question what have we packed with L1 balls instead？

Is it because of the1 like we're using L2 balls in Duley's？Oh， like。

 why are you getting the wrong answer？ Yeah， like we。Yeah，'， I mean， I don't have a good well。

Here's the interesting thing， I mean what I can tell you right now is like I'll show you what the next level of sophistication is。

The next level of sophistication still is like。It's still only ever talking about L2。

But somehow it's just a little more it's a little fancier。All right， thanks。

 so let me just write down what that next level of specificphistication is。

And this is due to forique。And then it's， and then in its current form I'm going to discuss， it was。

嗯。Described by teleground。Okay， so here。Let's rewrite Dudley。What诶。Okay， so's okay。

 let me give a definition。粤西。The sequence TR R goes from  zero to infinity is in。Amissile sequence。

If。For all R T R is a subset of T。 I actually I just write like this。嗯。

T 0 is a subset of T1 is a subset of T2 is subset of subset of T。And also to。

T0 has size1 and Tr has size at most two to the two of the R for allR。

It's really all sequences of sets that look like this。I claim that。The mean width of T。

No write like this。I think that definitely implies or it's equivalent to。

Saying that the mean width of T is at most。The in over all admissible sequences。

Of the sum R goes from one to infinity of2 to the R over two times。呃。

The soup over X and T of the distance in L2。XtTR。So I don't want to write down。Yeah。

 I'm realizing that we just started here。I don't want to write exactly why down。

 but let me kind of talk you through this。So。嗯。😊，For any given R。The thing that matters is this。

 right？The soup of the distance from any exitterR。So。

So if you're trying to choose a TR to optimize this， what should you do？

What you should do is the following， notice that you're given a budget。

TR you can make TR whatever you want as long as you don't make it too big。

 its size should not exceed2 to the2 to the R。😡，So if you're trying to minimize the soup of Re and T of the distance to TR。

 basically what you're trying to do is given this budget of how big the set can be。

 make it the best epsilon net it can be under that size constraint。

 like make epsilon as small as possible。😡，So then you should think of that soup of the distance as being epsilon。

 it's the epsilon such that TR is an epsilon net。😡，So that thing is epsilon。

And what is2 to the R over two，2 to the over two is just square root log and the size of Tr。😡，Right。

 so this looks a lot like the sum over a sequence of nets。

The epsilon of that net times square root long the size of the net that looks a whole lot like Dunundley。

喂。😊，And in fact， the reason that it really is deadly in disguise is if you think about it like。Okay。

 so let's say Duley says I'm going to take a one net then a half net and a quarter net then an eighth net。

 et ceter。I'm going to make Epsilon B whatever  two to the S。Okay。

 so initially in this in this thing that I wrote down。

 initially our budget for the size of TR is one because t0 size one。

And we can start to slowly grow TR。So for a while。The quality of the net。

 the epsilon that it achieves。Is between one and a half。

RightSo for some sequence of for some like for some prefix of the Rs。

Epsilon is basically between one and a2。So let's say that so it's most， it's roughly one。Meanwhile。

 what's happening to two to the R over two it's a geometric series right we have two to the one over two plus2 to the we have basically two to the one half is root two so we have root two to the one plus root two to the two plus root two cubed etc cetera。

 that's a geometric series with base root two so a geometric series here is dominated by its last term。

So for a while， we have epsilon being one。Times this geometric series dominated by its last term。ok。

All right， let's let's start like this， we basically something like like and most like a half times the geometric series。

So it's dominateed by this last term， so what we have is kind of root log the size of a one half net times a half。

And then the quality of our net for a while is between a half and a quarter。

And then we have another geometric series that starts from there。Right。

 and then it's dominated by its last term， I mean until finally it hits a quarter it goes under a quarter and then we can that sub we can bound that part of the sum by a quarter time squ log the size of a quarter net。

So we can basically break up the sum， this infinite sum， we can break it up into blocks。

Based on when the soup。Decreases by powers of two。And then each block itself is a geometric sum dominated by its last term。

 which corresponds to。One term in the Dudley sum。Okay， so what I claim is that this summation here。

Up to some constant factor gives you the same exact thing as the Dudley sum。

As long as you choose the TR optimally to be the best nets they can be。Does that make sense？

I I'm hearing cricket so。At least type it。 I can see the chat。 So if it makes sense。

 at least say it in the chat。 And while you do that Im way to try to find my。My iPad pen。

 because I seem to have。Put it somewhere and I have no idea where I put my pen pencil。

 which was just in my hand。This is so weird。看这面。Okay。

 so no one said anything so I'm assuming that yeah oh， I was going to say， yeah。

 I think it must to make sense， Okay， okay good。😊，So the magic， I have a question。

 Oh why do we need the TRs to be bounded by 2 to the2 to the R rather than just 2 to the R or is 2 to the R not enough？

嗯。Maybe it's just convention there's no。Oh okay， well， okay。

 it's going to matter for the next thing I say。ok。Yeah。

 so the next thing I'm going to say is that there's a theorem。By forique。Re kind of recast by telero。

That says actually WT is at most。The info over admissible Ts。Of the sink。

Over x and T of the sum R goes from 1 to infinity of2 to the R over 2 times the distance in L T from x to T R。

We took the soup， it's the same exact thing， but we took the soup outside the sun instead of inside。

Taking the soup outside of the sun。Can potentially make something smaller， right？

It makes the whole thing smaller。But the magic of Feregan Teleground is that。

Even if you pull the soup outside this is still a correct upper bound the proof is not the proof that this is a correct upper bound is not the same as the proof on the last whiteboard you you need to do a more custom proof。

 but it' it's doable and I'm not going to do it today。

Maybe I'll put it in the notes or maybe I'll link to something for further reading， if you'd like。

Okay， and then the theorem。Another theorem， which is called the majorurizing Measure theorem。

And this is the magic is that for all t， the mean width of T is at least that inch。

So not only is this an upper bound， but it's also a lower bound up to a constant factor。And also。

 let me just give a definition。This thing here is just defined to be I mean or I I'll use notation。

 This is called gamma2， the gamma2 of。T with respect to the alor。So the theorem。Is that for all T。

 the mean width of T is equal to up to a constant factor gamma 2 of T respect T。没。

And you know you can it's maybe I'll leave it as an exercise or you can read about it if you if you then tried to optimize this thing for the Eln ball you would get the right answer I mean you have to get the right answer because that's what the theorem says。

But in fact， you can do it in your convenience。Okay， so now let me show you， you know。

 so we saw already that the union bound alone was already enough to get the right answer for JL to apply JL let me show you now that Duugley's inequality is already enough to get the right answer for subspace embeddings and it's also enough to get the right answer for RIP。

So。Dudley implies。Os。And also Dudley plus the Gordon。

 so you do Gordon and then you apply Dudley to Gordon。O S C is an R P。

So let's do OSCs obliivous Subs embeddings。嗯。So E is a D dimensional subspace。

And T is equal to E intersect Sn minus1。So what is WT？Its equal to。The expectation。Of。Well， okay。

To be fair， to be fair， you don't really even need to do。You don't really even need to do do here。

 actually。All right， so let's write it down this expectation over G of the soup over X and T。

I G dot X。行。So remember now Gaussians。The Gaussian distribution is rotationally invariant。So。

If you're taking， so you might as well rotate the whole picture。

And just pretend that the subspace is actually the span the of E1 up to ED。喂。

Like without loss of generality。E is just equal to the span。E went up to ED。

To be more formal about it。I could write this as。So let's say g dot x。不。I could write this as。

As follows right so like let so I guess what I'm saying so Q transpose Q is equal to the identity。

Right。This is a rotation matrix。So what I'm saying is like。Let you。Let Q be。

Let Q be a rotation matrix that rotates the subspace to be the subspace。

 which is the span of U up to ED。谁。Then。QG。Basically， QG is equal in distribution。To just G。

 because if you take a gausian and you rotate it。You just get back in。So without lots of generality。

 I can just rotate the， I can just rotate whatever I want so I can rotate to that。

The vectors are just in this span of UNMs ED。And then now this is basically equal to the expectation over G of the soup over x in the。

D dimensionional L2 wall of unit norm of G dot X。But again， L2 isn't own dual norm。

 so this is just the expectation of G2。Which is at most the expectation of G2 squared square root。

 which is root D。So。B we're done。 so the Gaussian mean width of a Ddi dimensionsal subspace。

Interssected with the unit sphere， is that most for D？So the Gas mean with squared is D。

 so you have D over uppsilon squared， which is exactly what you got on the P at。So or via Dudley。

 let's say。Let's prove the same thing via Dudley。WT is at most。

The integral from zero to infinity of square log。Of the covering number of T L2 UDU。So first of all。

 I really only have to integrate to one because。系。Once U is bigger than one。

I can just make the net be a single point because everything in the unit ball is within within within1 of a 。

0。And then log of one is zero。Everything I'm integrating beyond one。

Beyond U equals one is just zero anyway， so it was just only I'm only going to integrate。一次要 be one。

And then now we saw this before。The D dimensionsional ball has an L2 has covering epsilon covering number of L2 of something like one over epsilons of the dimension。

So this is at most。In aroll from zero to one of root log。Something like。

Some constant over epsilon to the dimension。Oh， Eil is you。Do you。We're just equal to root D times。

The integral growth is  zero to one of root log。Some calls that over you， do you。

And you can prove that this thing converges。 So this is some constant。这候日定。Does that make sense？对不对。

And you know it's very it's obviously very similar for。RIP so for RIP， again。

 if you know I've used it， if you say I want to， if I want to ban the covering number。I mean。

 the observation for RIP is that。I'm trying to preserve and choose K different subspaces。

One for each choice of which K coordinates define this varsity pattern。

So the covering number is going to be something like and choose K。Times。See over you to the K。

So for RIP， I's write it for RIP。We'll get that。 WT is at most。

The integral from01 skirt log of and choose k times c over u to the k。自 you。And again。

 just because log of Amy。Is equal to log a plus log E。

What you're going to end up getting is something like this is going to be it， you know。At most。嗯。

Root log ands Kenny。Plus， roquet。And then this is basically the dominant term。

So is going to be at most。root of K times log of E of K or something。对是。So enough of all that。

Let's now prove Gordon's theoryorem。But before I prove Gordon's theorem， does anyone have questions？

O。So we'll prove something that's due to KMR so Kramer。mendelson。And Raroot。2014。They say let。

Scrriip A the。The same matrices。Also， Sigma 1 up to Sigma and our IID plus minus1。Then。

If you have the expectation over Sigma。OfThe soup over all matrices A in script A。嗯。

A sigma L syn norm squared minus the expectation of a Sigma El syn norm squared。Does that most？

Bear with me for a second。嗯。Gamma 2 squared of script A with respect to the operator norm。Plus。

 gamma2。Absscript A respect to the operator norm。Times the Frbenius radius of script A。Plus。

 the Promeius radius of script A。Times the operating raius。Okay， so。First， okay。

 so first I'm going to show you that it's going to be easy。

 I'm going to show you that this theorem implies Gordon's theorem at least if at least if the matrix pi has plus minus1 entries as opposed to Gaussian entries。

O。And then once we see that， then I'll prove Kmar。So just remember what gamma two means gamma2 means。

This right so what I'm saying now is we're not taking gamma2 of a set of vectors with respect to L2 instead we're taking gamma2 of a set of matrices with respect to the operator norm。

 so this this is going to be the operator norm。And the CRs are actually going to be like。

Subsets of script A， so the CRs for us are actually only subset of matrices。嗯。So now the claim。

Good observation。Is that and actually KMR proved this not just for plus minus ones。

 they proved it for any sub Gaussian distribution， so in particular the KMR theorem holds for Gaussians too。

But I'm going to prove it today just for plus minus ones because it makes things slightly easier。

The observation is that KMR implies what I'll call the Raamma reward， KMR plus majorurizing measures。

Because what we're actually going to show is that。As long as the number of rows of pi is at least gamma2 squared over epsilon squared。

 you'll preserve the vectors。But then majorurizing measure says that gamma2 and mean width are the same thing up to a constant。

So that means that you can set the number of rows to be the Gaussian mean width squared。

So this camera that I wrote up here implies the Raammaer version。According。

Where the matrix has rent Raam operaras entries as opposed to the optionss。So why is this the case？

It's something that we've seen before。我觉得。Which is I can define。For a vector。X。嗯。In our end。

I can define。And actually， let me not write the dimension here， it's not really relevant。

I can define AX。As being， you know， this matrix one over。嗯。Let's say， for vector X R also pi。

Hi R M by N。Hi IJ is equal to like Sigma IJ over。I going define a matrix a sub x。

 which is one over root M times。X transpose， x transpose。X transpose where everything else is zero。

 so the dimensionality here is the number of columns and N。And the number of rows is M。

Now if I look at。Notice that if I look at the operator norm。Of AX。嗯。Oh yeah。

 so actually what I wanted to say is just this。Pi X L2 norm squared。Is the same thing as。A X sigma。

Els squared， where're actually now Sigma is a really big vector。It's like M dimensional。

You basically cancatenate the rows of pi， so here you have sigma 11 up to sigma1 n and you have sigma 21 up to sigma 2 n。

All the way down to Sigma M1 up to Sigma Mn。So I claim that this is true。Right。

 and we're trying to understand。The soup of pi Xl 2 norm squared minus Xl 2 norm squared。

 which is one。So this is saying that it's equivalent to understand。Is equivalent to understand。

This thing。We're now。Scrip A is basically the set of all a sub x's， such that x' is and T。

Does that make sense？And KMR gives us something on the right hand side that depends on probeious norms and operator norms。

 well let's try to understand that。对。Gamma2 only depends on distances under the norm under consideration。

 so what is the distance。What is the operator norm distance between aX and AY Well if you look at the operator of AX minus the operator norm of AY。

 the first observation is that AX minus AY is just a sub x minus y。😡。

So this is equal to the operator of a sub x minus y， and that's equal to the L2 norm of x minus y。

Went over over Ro end。Because there's a division by Rudo。

Does this look familiar I think we did we reasoned about these a sub X's before when we were talking about when we were approving jail and sparse jail using the Han right inequality I know it's been maybe a month or six weeks now。

 but is this looking familiar to people。Some yeah， probably so I mean。

 this implies that gamma two of script A with respect to the operator order is equal to gamma2 of。

T with respect to the L2 norm。Overrooted。And what's the largest？So， Gf。

DM of script A is like the max is the soup over all A and script A of the Fr being storm of A。

But this is just equal to the soup over all Xs and tea。Of。Of the。For being it's norm of Ax， right？

And this is one， you can just do a calculation that's one and similarly DL2 to L2。A script day。

 you can also approve is just one。So KMR implies。That。You know。

 the expectation over pie of the soup over X and tea。

Of pi Xl 2 norm squared minus1 is equal to the expectation over sigma of the soup over a and script A。

Of a sigma L2 norm squared minus the expectation of a sigma L2 norm squared。Which is at most？嗯。

But we know gamma2 squared of script day operator norm。Plus whatever。

 but if you convert that to what it means in terms of T， it's gamma2 squared。Of。

T respect respect to L2。Over M。Plus， gamma 2 of T with respect to L2 over Ruta。Plus。嗯。

All right I have to say this， this should be one over。I think this should be。Yes should。

And this should be one of a route， I'm sorry。Plus 10 for them。So。This is ut most epsilon。As long as。

Is at least。Gamma 2 squared of T L2。Plus one of Repsilon squared。

But we know that Ghana two squared and width square are the same up to a constant。

 That's the majorurizing measures theorem。 So this is the same thing as。

The width squared of T plus1 the rhson squared。So really， really the only thing that's not obvious。

And all of this is like， why is this true？Right。Like how do you actually prove the KMR theorem that you can bound that thing？

They can bound that thing by the camera too。In terms of Gma2， with respect to operator arm and。

But using that entire right hand side is upper boundunded by epsilon or just the first term。

You want the entire right hand side we've added by this one。Yeah so。

So if you set M to be gamma2 squared over epsilon squared。

Then the first term is going to be Epsilon squared。

The second term is going to be epsilon right yeah and the last term is also going to be because you have a plus one there the last term is also going to be less than epsilon。

So the whole thing is going to be going up long。一。Does that sound reasonable， yeah， yeah。

Any questions before we try to prove Kmart？I'm not 100% confident that。

We'll be able to finish the proof of KMR in 15 minutes， but I think' we'll at least be able to like。

Almost prove it and get and get all the main ideas across and then whatever's left。

 I'll just put in notes。Okay， so are people psyched？Yeah， yeah， so let's prove it。Moation。嗯。

A has columns。A1， a2。To a。AWhatever the dimension is。That's one thing。

And then the other thing I want to say is like。If TR is admissible。Sequence。Then。Pi are。

A is defined to be the closest。Wait。The closest point to a。In TR under operator norm。

And Delta R of a is defined to be pi RA minus pi r minus。好人。So that's a presentation。

So now the first thing I'm going to define the error。To be the thing we're trying to bound。

The error is the expectation of sigma， the soup over all A and script A。

Of a sigma L2 norm squared minus the expectation of a sigma L2 norm squared。So I can write this as。

The expectation over sigma of the soup over A and day。

Of like remember now like remember that a sigma is equal to the sum of Sigma I AI， right？

This is what I wrote on the top right here。All I just saw your chat， Alex。

 I'm glad that you're excited。Okay， so this is equal to basically the dot product of the sum of Sigma I AI。

That by itself。M is the expectation。嗯。So notice that like basically if you know。

 when you have the diagonal terms in the dot product。

 you're going to have Sigma I squared so okay can let me just write it like this。

 this is equal to the expectation over sigma of the soup。Of。嗯。

Some overall all IJ of Sigma i Sigmaj dot product of AI。 AJ kind of minus1。Expectation in there。

And I claim that the diagonal terms just cancel exactly with the expectation。

 the diagonal terms are the expectation， the off diagonal terms that expectation zero。

The diagonal term Ci squared is one。系， so they stay。

So this is equal to expectation over sigma of the soup。OfThe sum over I not equal to J of Sigma I。

 Sigma J， AIA J。And I don't， so this is already in the notes in the probability review section。

 I'm not going to spend time proving it， especially since I don't have a lot of time。

 but there is a magic trick called decoupling that says this is at most four times the expectation over sigma and sigma prime of the soup over a of the sum I not equal to over the sum of I all Ij including the diagonal。

Of Sigma I Sigma J prime。AIha。So sigma， so now we have like two n random signs， Sigma1 to Sigma n。

 Sigma 1 prime up to Sigma n prime。These are two n plus minus ones。

 they're all independent of each other。😡，Okay， and then I can this is equal to four times the expectation over sigma Sigma prime。

Of the soup over a of。As sigma。 asigma private。你看。So let's just remember now where we are。

We've shown that E is at most。Up to a constant which the constant is four。

The expectation over S and Sig prime of the soup over a and script A of。A sigma out with a sig。Okay。

 now a little bit of a magic trick， I claim that。For any fixed a。

 a sigma dot a sigma prime is equal to。So remember now write I can write a。As like。

Pi 0 a plus the sum R goes from one to infinity of Delta R。

This is that same telescoping something I did before when I was proving Dudley's inequality。

And you can prove that this thing is equal to pi0 a。Sigma dotted with pi 0 a。什么。Plus。

 the sum R goes from  one to infinity。Okay。呃。Delta R。Singma pi R minus1 a。Summa prime。Plus。

 the sum are goes from y to infinity。嗯。Delta R or actually allleerate pi RA。嗯。Data with Delta R。Okay。

 so looks like a mouthful， but let's just think about what's happening。So first you start off。

 let's try to again expand out these sums like one term at a time。

 So first you have pie first you have like。Pi 0 a dot pi 0 a。

Then when you add in the next terms from r equals1。Remember now Delta R means pi R minus pi R minus1。

😡，So you basically get。Two terms from the first sum and two terms from the next sum。

 if you expand out Delta R is the difference of two things， so you get four more terms。

Yet pir do pir minus1。Plus or minus minus pi r minus1 dot pi r minus1。 So right， so this。

 this is going to give you something like。Let me take a little shorthand。

 this is going to look something like P R。Dot pi R minus1。Minus。Pi R -1 die with pi R -1。

But like this， this is going to cancel the previous sumand right remember we had pi zero not pi zero。

So p now only r is1， pR minus1 p minus1 is pi0 do pi0。

 so it's going to cancel up with the previous thing。😡，And then when you expand out this thing。

 you're going to get pir dot pi R。Minus pi R dot pi r minus1。

So then minus this minus here is going to cancel with this thing。

So the only thing that remains that survives is this。So first you add pi0 do pi0。

 then when you expand things out for r equals1， everything cancels except for pi 1 do pi 1 then when you expand out then when you add in the next sum。

😡，You get pi 2。 pi2， et cetera， and then eventually because script A is finite。

 again without loss of generality， scriptA is finite。Because crype is finite。

 eventually all the delta R's are zero。Which means that you're going to end up with like this is just a massive telescoping sum that's a fancy way of writing asigma asigma prime。

嗯。Okay， and now let me make some definitions I'm going to call this。This， I'm going to call。X，RA。

And this， I'm going to call。YRA。So this implies that E is at most。

Pi 0 a apply to Sigma pi0 a Sigma prime。Plus， the sum are goes from1 to infinity of XRA。呃。

Does there should be a soup， sorry。So yeah， there's really suits to make reasonable this。Sorry。

 sorry， sorry。 let's put the soups back。Is that most the expectation of the soup over a？

a sigma pi  zero。p zero a cinemama pi zero a。Super prime plus。

The expectation of our sigma signal prime of the soup over a。Of the sum over R。Of XRA。Plus。

 the expectation of the soup of the silver R of YRA。And Y and X are quite similar to each other。

 so like the same way that you analyze this。Is gonna to work to also analyze this。

So we' only have to focus on one of them， the other one is it the same， so let's do that。

 but first let's look at this thing。So again， remember that the definition of amissible sequence。

 t0 has size1。So really， there's only one matrix pi 0 a。

 let's just call it every single a has the same pi0 a， let's just call it a0。

So this is just equal to the expectation。Over6 months a prime。Of。嗯。Actually。Let me put， yeah。

 so I wanted to write。A zeros。A0 sigma。That a 0，0，5。And then I want to write that this is at most。

 So this is equal to。Expectation of like sigma transpose， A transpose a sigma prime。I here the see。嗯。

Which actually is interesting because that's， well， that's zero but。

Maybe we could have gotten rid of it。嗯。If you had， I don't know if I lost an absolute value anywhere。

 if I did oh yeah yeah yeah， I did lose an absolute value。

 remember now there was an absolute value around all of us。So I should have kept my absolute value。

 so really there's an absolute value here too。So this is u most。

Is at most the expectation of that thing square， square root？

Which turns out to be the forbinous norm of a0 transpose A0。

Which is at most the operator norm of a0 times the fbeius norm of a0。

So this is at most D L2 to L2 of A， the largest operator of anything in A times the largest for me sort of anything。

Okay， so we got it the first term。Okay， so how do we bound the next term？

So now we have to focus on this thing。诶。So expectation of Sigma do Sigma prime。Of。The soup。

Over am per day。Of the sum R goes from 1 to infinity of XRA。And just a reminder。

 just a reminder of what XRA is， XRA is equal to。Delta R applied to Sigma dot with pi R minus1。

He applied to。Apply to Singapore。So this thing is equal to。The expectation。Over seeingma prime。

OfNow again， right the expectation of a non negative random variable。

Like the expectation of Z is equal to the integral of the probability that z is bigger than Udu。

Right， this follows by integration， this follows by integration by partss。

 So this equal to the integral from zero to infinity of the probability over sigma。

That the soup over a in script A of the sum R goes from1 to infinity of XRA。

Is bigger than you do you。And now I can do a change of variables and I'm going to do sort of a magic change of variables that。

It's， I mean， I'm doing it just because it makes the proof work out。

But I admit that it is a little bit of magic。So this is equal to。The expectation over Sigma prime。

Of the following thing。The soup over a and script A of。A single prime。有人。

Times the soup over A and script A。Of the sub。The sum R goes from 1 to infinity of 2 to the R over two times the norm of deelta RNA。

 the operator norm。Times the integral of from zero to infinity of the probability over sigma。

That the soup over A and script A of the sum of a goes from one to infinity of XRA。Is bigger than。

Tea time the soup。Over A and script P。Of the sum r goes from one to infinity of two to the r over two。

Delta RA。Times the soup over a。Of a sigma prime。Okay， that looks like a mouth D T。So I mean。

 all I did。Like if you just call this thing beta。All I did was a use substitution， I just said that。

I just did the substitution u is equal to t times beta。

Which implies that D U is equal to Dt times beta。O。

And now okay we're almost out of time so I think but we're almost done with this proof even though it looks like a mouthful so here here's kind of the idea now we're going to end up using kin's inequality and a giant union bill so we're going to say look so this。

This integral。I can write as like the integral from zero to three of that probability plus the integral from three to infinity of that probability。

This is at most three。OkayFor this thing， I'm going to use the union bound。嗯。

So what's the probability that there exists？An R。And that there exists in A and script A。Such that。X。

RA。Is bigger than。嗯。T2 to the R over two times。Delta are a。Transpose times piy minus1a。Okay， so okay。

 this again looks like a mouthful。But let again， let's remember what XRA is。

 I wrote it up here at the top。I can write that as。

Sigma dotted with Delta R transpose pi R minus1 a sigma prime。Does that make sense？Am I write。

 like am I write？B sigma do B prime， Sigma prime。That's the same thing as Sigma transpose。

 B transpose， B prime， Sigma prime。Which is the same thing as sigma do with B transpose B prime sigma prime。

 so I can move this matrix to the other side。ABy transposing it。

and then I can do kinchens inequality， kinch's inequality says。If you take a s vector。

And you dotted with some other fixed vector。What's the probability that you're bigger than？

Lambda times its Lt2 arm， it's at most e to the minus lambda squared。So that's what I'm doing here。

 I'm saying， look。That thing on the right hand side。Has norm equal to this。

So what's the probability that I'm more than t times 2 of theR over  two times that norm？

It's at most。It's at most something like。诶。Eat， it's almost something like oops。E to the minus。

T squared2 to the R over2。Times and times。And I should really say。

 I'm going to union bound over all R because I said， was it probably that there exists are？

Was it problem that there exists in R where this is true， Was it problem that there exists in A。

 So if you fix an R and you fix an A， this is your tail bound。 This is just k。

But if you want a union bound over all R， you're going to sum this thing over all R。

And then if you're going to union bound over all a， well。

 how many possibilities are there for deelta R of a and pi R of a？😡，At most。Something like。The size。

 the size of。TR times the size of TR minus1， which is something like 2 to the2 to the r plus1。

So if you look at what's in that sum， I know again， this is a lot of math here but。

You have two to the2 to the R times e to the minus t squared 2 of the R。唔仔。

Now E to the minus t squared2 to the imagine the base was not E but the base was 2。

 I can do a change of base and lose a constant to the exponent。

 so I have two to the two to the R times2 to the minus t squared2 to the R。😡。

If T is a big enough constant， like if t is at least three。

Then 2 to the minus eight times 2 to the R is way smaller than2 to the2 to the R because there's an eight there in the exponent。

😡，So this summit converges。Okay， so that's the point， the point now is。This part here。

 this integral here， I can write as being at most。The sum overall are from reverse the order of the sum in the integral are from one to infinity。

Of the integral。From three to infinity。Of。E to the minus t squared2 to the r over 2 times 2 to the2 to the r plus1 Dt。

And this whole thing， I promise you convergeence。It converge is the sun constant， it's bounded。

So this whole mess of a thing here。嗯。This all this stuff over here。Is basically a constant。

The only thing that survives is this part， beta survives。The rest is a constant。

So what we have then is that。This implies that。The expectation of the soup of the sum of XRA。

Is that most up to a constant？The expectation。This is the expectation over S prime。

Actually over now we're single prime。Of the soup。Over a and for a。Of a single prime。Times。

The other thing， which。Again， I think we're way over time， the other thing is basically gamma2。

Is bounded by gamma2 up to a constant gamma2 of script A with respect to the operator。Okay。USo this。

 this magic of doing a change of variables in the integral basically gives you a gamma too like this。

This thing here is bounded by yamma。And I don't have time， I'm out of time。

 I'll include the details of that in the notes， but it's a simple triangle in equality to say that this thing is batter by gamma two。

And then if you just keep going， you know， you can wrap this up and get the bound that I showed you。

So I'm afraid I'm more than five minutes over time。

 so I'm going to stop here and if you want to see the details of these calculations， at least I hope。

I hope I at least gave you a flavor of the calculations and showed you。

 I showed you once you have it， how it implies Gordon's theorem。嗯。

But I'll put the details in the notes and I think that's it for lecture and are there any questions？



![](img/63eeb882320375b4665314a546e0be3d_2.png)