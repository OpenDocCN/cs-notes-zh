# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p11 P11 Johnson-Lindenstrauss lower bounds -BV11zi7BjEHu_p11-

![](img/ca3266c71b2ba7d934020b155e2dbc01_0.png)

Great， hello everybody， so welcome back after the guest lecture I know I know it was a bit technical but。

I hope people enjoyed it。You know， don't worry， there there won't be any homeworks related to that lecture or any other thing that's。

Well， there are no exams of this course anyway。You're not going to be quizzer in any way the contents of that that was just for fun。

嗯。So thinking about what we did in the recent past。

We've done a lot of stuff on norm estimation and embeddings。 You know， the Johnsontroauslema。

 followed by A M S， Well， A S sketch， Johnson Letroaulema， LP Nor estimation， and then sketching for。

Arbitrary norms in the relation to embeddings today we're going to stick with embeddings and we're going to talk about lower bounds。

So， today。I'm going to show you。An optimal lower bound for the Johnson chest。Right。

So we know from JL that any。Yeah know， endpoint。Subset。Of the Euclidean space。In beds。Into。

M dimensional including in space。With distortion of the epsilon。Where。M is。Oh。

 I have 10 cents squared login。And you know， I haven't I don't think I've used some of these terms like what does distortion mean？

Basically distortion means。If you have two metric spaces。Let's say the metric space。

 X with distance function Dx。And Y with this distinction Dy。These are two metric spaces。

And then you also have a function F， which maps x to y。Then if it's so row basically。The distortion。

Grow。Congratulations said at least。It's true。 that's at least one。Is the smallest value。

Such that there exists。this version wrote of F。Is the smallest value such that there exists？You know。

 scaling constant C。Such that。For all points X Y in PeX。If you look at the distance。

Between the distance and y between F of x and F of y。Is that most。

R C times the distance in x between x and Y。It's at least C times the distance of x。Exent。

This scaling sea business。Only only matters for kind of non norm spaces and norm spaces。嗯。Yeah。

Us the question we're interested in is， does there exist？And embedding a blow distortion。系。嗯。

So for that， you know， you don't really need this C there because。

If you have something that has the C， you can just take the embedding and scale it by one over C and then you'll just have D on the left and row times d on the right。

 but you know you can do that in norm spaces you can't necessarily then arbitrary metric spaces。

 but yeah we're just dealing with norm spaces here anyway we're dealing Euclidean space。So right。

 so you could ask the question of， you know， jail gets this distortion one plus epsilon with target dimension 1 plus plus squared log n。

 is that the best possible？ is jail， is the jail Imo the best possible？嗯。Or is it true that。

 you know， so really the question is， does there exist a bad point set？Such that for that point set。

 you cant know for every epsilon， let's say and for every end。

 does there exist a bad point set with endpoints such that you cannot do better than JL。

If you want distortion one with uppsilon on those endpoints。And it turns out that the answer is yes。

 jail is the best possible。And you know， the history of what was shown。Is as follows。

So first we have。In 1984。The jail paper itself。Showed that， if Epslaon is smaller than some constant。

Like a third or something， actually， you know we'll see well I'll show you this argument。嗯。

And some fixed content。You know， say a third， it's not exactly a third。Then。There exist point sets。

That required。Target dimension would be at least some sometimes log on。

So that argument is not sensitive to Epsilon。Once Epsilon is less than a third。

 you just get a lower better of log in if Epsilon is 0。001。You still just get a lower band of log in。

 it doesn't capture the hardness that comes from the epsilon。And then no go alone。every the year。

 this is 2003。Showed that there exist point sets that require。A to be at least。

One of Refpslon squared log n over log one of Epslon。So this is optimal， except for。Except for that。

 you know， it doesn't match。You know， the jail upper bound does not have that log onrups side of the denominator。

And I should really mention that the lower bound is like the min。Of this quantity and N indeed D。

Because you're never going to prove a lower bound better than D right D is the original dimension。

You're， not're going to prove that there's a little ground better than DY because there's always an embedding into dimension D with distortion one with no distortion。

 namely the identity map， right， just take the points themselves。

You're also never going to take get a lower bound better than n minus1。And why is that？

So take your endpoints。You can translate them if you translate all the points by the same amount。

 the distances don't change。So translate them so that one of them gets moved to zero。Okay。

Now you have n minus1 points together with zero。These n minus1 points with zero span a subspace of RD。

Of dimension at most n minus1。对。So since they're in an n minus1 dimensional subspace。

 you can embed them in dimension n minus1。And preserve all the distances exactly。

basicallyically just rotate the subspace so that。You know。

 it becomes the span of you went up to you know， E minus1 or something。Okay。

 so you're never going to prove a lower bound better than the min of N and D。

So you can think whenever I write these lower bounds。

 what I mean is know M is the min of N D in this quantity。Hiss Lael。Okay。诶。

My pencil likes to change itself to eraseer by itself as a mind of its own。In 2016。

 there was a lower bound by。Casper Green Larson and myself。

That showed that M is at least one of some squared log n。For linear maps。

Right so if you look at the jail ama， what are we trying to do。

 we're trying to embed D dimensionally Elidean space into into lower dimensionally Euclidean space。

Now， you know。The jail Lama just proves the existence of such a map。

It turns out that in the proof this map is a linear map。

 x gets mapped to a times x for some matrix A。So in this paper， what we proved was that。

There are point sets such that if you insist on the embedding being a linear map。Then， you know。

 even if it's not random projection， you're allowed to do whatever fancy linear map you want。

 there simply does not exist a linear map that does better than jail。

But for our hard point set in that work。You know， potentially the I mean。

 actually there was a non nonlinear map that actually did better than jail for that point set。

 so we really crucially use the fact that the lowerbe was only against linear maps。

And then the thing I'm going to show you today is also with Kas were Larson and myself。

Is that MSV at least or the square login？Okay， so and you know。

 and this this is this is the lo running against any map。

 So even if you allow even if you allow yourself。A non nonlinear bedding。

You still can't do any better。And you know， interestingly。

 it doesn't mean you're going to see the proof today。

It doesn't use any tools that I feel like well okay。

 so it does use some language that I will have to introduce。

 but the basic idea is an idea you've already seen in our previous discussion of lower bounds right so I thought you know。

How talk how did we come up with lower bounds before。

 there were compression arguments and there were communication complexity arguments。

 the latter of which often you prove the communication lower bound itself via compression argument。

But it's going to be the same kind of thing， it's going to be a compression argument。

We're going to show you today that。You know， basically。

I don' don't know a specific point set for which you can't be jailed or what I can do。

Is I can define a very large collection of point sets， so a set of point sets。Such that。you know。

If for every point set in that collection， you can beat jail。If that is true。

Then I can use that fact。In a black box way。To define an injection。

From that collection of point sets。Into a smaller set。

Which is a contradiction right I can't have an injection from a big set to a smaller set。 therefore。

 the assumption， the assumption that every one of these point sets has a good low distortion embedding that beats JL。

Is is not true at least one of the points sets in that collection。you cannot be jail again。

 that's open， which， you know， tell me an explicit point set。

 tell me one point set where you can't be jail， I have no idea。

But I can tell you a large collection of point sets for which one of them I know you can't be jailed。

Okay， so let's start off with the original lower bound of JL。

Because it uses ideas actually that you know， that get used in the very last the optimal lower bound。

 so alone Nogo alone， when he came along， he gave an argument that was totally different from the original jail argument。

And then the 2016 paper was also different from JL and from Nogoone， completely different。

And then the 2017 optimal lower bound actually went back to the language of the original jail lower bound。

 I mean， of course you had to do some more work because you're proving a better bound。

I would say it was in the same category of proofs sort of。So。Jail  any4 lo bound。

Was what's called a volumet argument。So they look at the hard set of points， capital X for them。Is a。

0，1， oh， sorry。0 vector。Together with E1， E2， up two， let's say。Yeah， might。Yeah。

 and so it's a set of n plus one point， so pretend n was actually N plus one。

Or just drop the E this matter。Now。Yes， say， I have。A low distortion。Embedding。F。

Which maps X into RM。I can translate。So that f of zero is zero right again。

 if if you translate basically translate everyone by f of zero。

That doesn't change parawise distances。Okay， so and let's also say。Define。E， I tilda to be。F。

But yout remember EI is the standard basis vector right so EI is。The vector is0，0 to the0。

 and then a1 in the eighth position。0，0， Wait。 this is yeah。The simple。Okay。

 so what's the picture here？So。Here's a picture。嗯。Originally all the EIs。You know， have unit norm。

And their paralyzed distances are the square root of two。Okay。Now， you know。

 after you after you map by F， you know that， first of all， you know that for all I。

 if you look at the distance。Between F of EI and F of zero。

This is the same thing as the distance from EI Tilde to what is F of 000？

So that's just the normal EITda。This had better be one plus or minus epsilon， right？Because remember。

 the distance to zero is preserved while the original distance to zero was one。

So the new distance to zero had better be one plus or minus epsilon。So。So here's the picture。

Here I have a ball。Of radius。Oneable epsilon。And this is in our M。What do I know。

 I know that all the EIT does are in this ball because they all have norm at most they all have norm that's one plus or minus epsilon。

What else do I know？I know that if you take two of them。So here's some EI Tilda。Here's some EJ Tilda。

Okay。They have to be far apart。Right，Because originally their distance was route two。

So now their distance has to be at least。For all I not equal to J。

 I know that the distance from EI Tilde to EJ Tilde。Has to be at least1 minus epsilon。

Times the square root of two。Are they also outside the ball of radius1 minus subpsilon sorry can you rephrase the question no。

 I didn't quite understand what you mean by that Oh like was the norm has to be like less than one。

Plus epsilon but also also be greater than one minus epsilon。

 And so it's gonna that's like a thin show That's right yeah。

 so I'm not gonna that's true I'm not going to use that fact。

 but what you're saying is correct that they can't be toward the origin。

 They have to be kind of near the boundary because their norm is also at least or minus epsilon。

That's true。Okay， so I know that these things are far apart。

Which means if you take balls around them。Let's make with this ball red。You know。

 these red balls have radius。Less than say。1 minus epsilon root two over2。Let's call this R。

So this is radius R。This is Raius order。These balls have to be disjoint。

because if they were not disjoint， there's some point that's common in the intersection。

 let's call that point X。Then by triangle inequality right。

 I could go from EI Tilde to X and from x to Ej Tilde。

 I would have a path of length at most2 R between them。

 which means the distance between them is at most2 R， but I know that's not true。

 I know their distance is more than2 R。Or it's at least two are， so all these balls are disjoint。

So let me draw them there are a bunch of them。 How many of these balls are there there are N of them because there are any itildas right。

 So there are these N red balls。And I know that they're all this drink。

But all these balls are contained in a bigger ball。Great， this art this yellow ball here。This。

 let's say， so what do I know， I know that。EI Tilda has norm at most one plus epsilon。

And then this ball has， you know， has a radius of。1 minus epsilon root 2。 So this has， let's say。

 radius of。嗯。One plus you know， one plus epsilon plus one minus epsilon， you know， root two。

which I' it's roughly one plus root two。Which is， you know， which is less than three。Anyway。

If Epsilon is smaller than a third or something， this is less than three。So what do I have。

 I have end balls。Of a certain radius。That are disjoint。And they're all。

They're all contained in a radius  three bowl， and now I can end the argument。

 How do I end the argument。The volume。Of the。Union。Of the red balls。Yeah。Is equal to the sum。

Over the red balls。Of the volume of that red Bull。This is because the balls are disjoint。

So the balls are just joint， the volume of the union is the sum of the volumes。On the other hand。

 I also know that。The volume of the union of the red balls， well。

 the union of the red balls is contained in the yellow ball。So this is at most。

The volume of the yellow ball。Does that make sense？

And also I know that you know all these red balls are the same right they all have the same radius。

 so they all have the same volume， so this is just equal to n times the volume。Of a red ball。Yeah。

And let me say also， you know， so I said those bird balls have radius R and let's say this。

 this yellow ball is some radius R pride。So just rearranging things， what do I have， I have that。嗯。

My inequality is that。The volume。Of the yellow ball。Divided by the volume of the red ball。Is。呃。

At least N。这 X sense。Right。Are people with me， any questions？Looks good Okay。

 and now what is that ratio I mean you can you can look it up you know， what is the volume。

 what is the volume of of a ball and you know an M dimensional space， a Euclidean ball。

It doesn't really matter because the point is it's going to cancel so the point to you know。

 if you have a radius Rball。In dimension M。The volume is going to be something like R to the M。

Time something that something that depends on that you know you you can look up where the volume of a ball is。

But the point is， so the numerator is going to be like r prime to the M times bh。

The denominator is going to be r to the m times bh。So this ratio is going to be。

R divided by our prime。to the end。Which implies that。M is mega。Log base are divided by our prime。

Should it be our prime overall？Yes， that's。And you know。

 you just look at what we have here and you know， our prime and R are both constants。

R prime divided by R is some constant， so you have log based and constant of n。So it's Oomega login。

And you can see here why this argument does not is not so sensitive to。To epsilon， basically， I mean。

 what do you know， you know that。嗯。Yeah， so what can I say here？Our prime over R。

 you know so you want to minimize the base of the logarithm， right because？😡。

know log base a million of n is a smaller lower bound than log base2 of n。

 so the smaller you can get the base， the better of the logarithm。😡，On the other hand。

 you know that you're never going to be able to get r to be bigger than R prime over two。😡，Right。

 because。You have these you have at least two balls， two red balls。

That are completely disjoint bigger inside this yellow ball。Each of those house radius are therefore。

The yellow ball can't have radius therefore the R can't be。

R can't be more than half the radius of the yellow ball。

 so you're never going to get better than log base two of n。And you know。

 this argument maybe is going to get you something close to log base three over two， you know。

 so it's I don't know， log basease five event log base6 event so you're getting within some constant of that。

 but。Even improve even if you try to incorporate epsilon in your arguments。

 there's some limit as to what the base loging is going to be。😡，Yeah。So that's it。

 that's the jail order。How do we get the 1 minus epsilon root 2。For each E I till the。

Being far apart from the other EJ Tildos， how do you know how do you know that that how do you know that they're far apart？

Yeah， I by 1 minus epsilon root 2。 Well， because E I。In the original space。

 E I and EJ has distance root 2， right？EI is the vector that has a one in the eighth position and a zero everywhere else。

So if you look at EI minus Ej， it has a one somewhere and has a minus one somewhere。

 the norms root two。And my assumption was that F is a low distortion embedding。

 it preserves all the distances up to one plus or minus epsilon。Therefore。

The distance between EI Tilda and EJ Tilda， which are the embedded versions of EIEJ。

Have to have distance at least one minus epsilon root two。

So if you have two points that are at distance， at least know D。

Then the balls of radius D over two around them have to be disjoint。If not。

There'd be something in the intersection and by triangle inality， they'd be closer than D。

 which is not the case。Does that answer your question？Yeah。Okay， so that's the jail or Ed。

question the J lower bound and specifically in this case like it's too hold true for all point sets in this case we use like a well separated set so are there on like the point set in which we can sort of exceed the lower bound。

嗯。Wait is there like are you asking if whether there's a characterization of point sets where you cannot exceed the lower end Yeah。

 it seems like because in in our counter example， we used a really well separated one right is like is that like a hard like it' is like a particularly hard problem to have load distortion in like right well。

 I mean I guess as you see from the argument the you're right the only thing the only properties we used about the Es and EJs I mean we used the fact that they had some bounded norm to say that everyone fits in the yellow ball。

And we also use the fact that they're well separated in the original space so say that they're still going to be well separated in the target space so you would get the same lower bound using any such set it doesn't have to be the EIs of Egypt it doesn't have to be the simplex I guess my question is if we knew that if wenew some property of our point set that they're not well separated can we exceed the jail lower bound。

Yeah， so what you can do is。I'll say the following， so。

JL says like you can get M to be O of log squared and a represents log answer。

Log in of Rpsalon squared， there's a theor of Gordon from '88。It says the following。

So let's say that your x has size n here。And let's define T to be the set of all normalized difference vectors。

 so x minus y divided by the norm of x minus integral broad。For all x not equal to y in capital x。

And then there's something called the Gaussian mean with of tea。I mean not use the same control。

 so let's call it with for W for with W of T is defined to be the expectation over a Gaussian vector。

So G is distributed you know GIR II normals means zero variance one。Of the soup over exee of G dot X。

This is called the。Gausian mean with。And Gordon said that it's enough to choose M to be big of。

The squared width of T， let's say plus y that represents on squared。So。Yeah， this is some。嗯。

It's it's more， yeah， so this is some notion of。呃。Easiness for JL in the sense that， you know， if。

 if your point sets are nice， then somehow。嗯。You can do better than jail You can prove that W squared of t is never bigger than log n or O of log n。

 so this is never worse than the jail bound， but sometimes it's better and kind of the hard case。

 the hard case here is really when the vectors in T So forget about X second let's just look at t which is the normalized difference vectors the hard says the case when the vectors in T are all orthogonal。

Which basically， I mean， that's not exactly the same as the simplex。嗯。But， you know。

 those vectors are not all orthothgon atal， but that is the hardest set。嗯。

Notice though that the simplex， I mean， it does contain a large subset of orthogonal vectors because。

You have zero in there and then you have the EIs So if you look at EI minus zero over the norm of EI minus zero。

That itself is the simplex again， so T contains the simple plus other and choose two other things too。

So that simplex that it contains is kind of why it's hard。But you know。

 the cases that are easier are like basically where let me draw T。

So if T looks something like the following where。There are like all these different。

 there might be a lot of vectors， but they're like clustered。So imagine like this is tea。Right。

Then as these clusters become like arbitrarily small。诶。

Kind of the mean width of T starts looking more and more like square log the number of clusters。

It's not exactly。It's not exactly that because。Yeah， all okay， anyway， I mean。

 the easier case is when the T is clustered， the harder case is when T has a bunch of orthogonal vectors。

That's something that's known， I don't know if we're going to have a chance to prove Gordon's the in this class。

We'll see where we get。Does that that help answer question Yeah， yeah。

 So if like Gordon had a matching lower bound then it would be like a strictly better like more adaptive statement than like JL。

 right。Yeah， unfortunately there's no lower bound saying that the Gordondon bound is optimal。

There it's not a characterization， it's not like for every point set。😡。

The exact right answer is w squared T over rhpsson squared， that's not true。

I see there are point sets where you can do much better than Gordon and you know。

 maybe you need to do a nonlinear embedding to do better than Gordon。

The Gordon embedding is the same， it's just pick a matrix of random plus minus ones or random Gaussians。

' the same random projection thing。Okay， thanks， this is a better analysis of random projections。

Okay， so let's get to one more thing that I wanted to add maybe to history。

I there was something in 2011。And there were two papers， one was by Jay Ram and Woodruff。

There's another paper by Kane。Mecca and myself。That what that said is that the distributional jail dilemma is optimal。

So distribution remember distributional jail。Distributional jail says。For all Epsilon Delta。

Their exists a distribution， D epsilon Delta over major C。Such that。You know， all for all X。In RD。

The probability over choosing a random matrix from that distribution。That you fail to preserve it。

Is that most Dalton？So the way that we proved JL in this class was and the way that everyone proves JL。

 it's the only proof of JL that we go。Was pick a random， you know， pick first of all。

 you show that such distributions exist。Oh， and also I should say。嗯。

Your M was like one of ups on squared log one adults right。So you show that this distribution exists。

And then to get J， you know， you pick a random such matrix pi， you're embedding F of x is just pi X。

And you do some union bound and you show that， if delta is less than one over n squared or one over inches two。

 then the union bound can go through and such a map exists。So in 2011， we you， it was shown that。

That this bound am for DJ， this bound。Os。Now this bound is optimal。嗯。

But that doesn't necessarily mean that jail is optimal， right because this is saying that。

If you insist on proving jail using VJ， then you're never going to do better than when Upps Sound squared log in。

But you， in principle， maybe there's some other proof of jail that doesn't use DJL at all。

And gets a strictly better band， right。That was kind of the state of。Affairs。2011， nine years ago。

And I think， you know， I do have some time， let me show you。

 it's I mean it's a useful thing to know about， I'm not going to show you the details of the proof。

 but how do you prove that DJ is optimal？So， you know， you say something like this， you say。What。

For all X， and I'll show you the proof from。Kme Mecca and myself in 2011。

The JM Wood of proof was actually different based on communication complexity。

But you say something like this。 Let's say yeah， you say for。For all X and RD。The probability over。

 let's say that you had such a distribution for DJL， you have this distribution D Epsilon Dlta。

So that means that for all x， the probability of a random matrix pi from that distribution。That。

Pi x L2 arm squared minus1 is bigger than D Epsilon is like atmost delta。Well。

 if it if it's true for all X。Then it's certainly also true for a random X。

So let's say this implies that the probability over x。Coming from some distribution。

 let's call that distribution B。Or the probability over a pie of that same thing is less thanta。

This is true for any distribution B。And then now I can change the order of the probabilities。

 so this implies that the probability over pi probability over x。Of that thing is less than Delta。

So now what this is saying is for random pie。A random pie works。

For all but a deta fraction of the x's and by delta fraction。

 I mean under the weighting given by distribution B under the probability deelta fraction of probability mass under distribution B。

😡，Okay。So a random pi works for all but a delta fraction。

So there you know there must be some pi that does at least as well as the average。

 you know the average pi works for all but of delta fractions。

 so there must be some particular pi that works for all but of delta fraction so this implies that there exists some pi star。

Which is an MD matrix。Suchly the probability of act coming from B。That。Pi star。

XL genome squared minus1 is bigger neons else than delta。And then you just show that。

No such pi star can exist if M is too small for a certain hard distribution B。😡。

So you say the hard distribution。B is just uniform on the sphere。

And then you show that this just requires some calculations that show that no。Such pie star。

Can exist。For this be。Unless M is sufficiently large。

And sufficiently large basically means matches the DJL lower bound or the min of that indeed。

And just， you know， this is this technique of basically this right here。

This implication going from going from like。Saying that's the， you know。

There has to be exist this pi star。 I mean， this， this is called， you know， the easy part。

 the easy direction。Of something called Yao's minii Maxax principle。

I don't think you're ever going to see that term again in this course。

 I'm just saying it so that at some point in the future。

 if you ever see the term Yao's mainax principle， he'll be like。

 oh I've seen that before when I took Gelani's course you know， years ago。嗯。Right。Okay。

 so that's all I want to say on the the optimal DJ alert about。

 it basically does this sequence of steps and then it does some calculations to show that。

A short matrix cannot do well on the uniform distribution。Okay。So now the optimal jail lower bound。

And before I can show you the optimal jail or bound。

There's just a few more kind of preliminary definitions that I need to give you。First。A prior。

On some convex geometry。So definition。A convex body。Is a。Compact。Convex。Sunset。Of R D。Okay， so。

Convex， know， if you don't know what any of these terms mean。

 convex just means and if you look at the body。If you take any two points in it。

And you look at the line between those two points， the line is not allowed to leave the body。

 so in particular I think this might not be contracts because。If you look at baby。

This point and this point。That line does seem to。Leave the body a little bit。And then compact。

 it has a more general definition， I mean， I'm not assuming that people here have taken analysis or topology。

 but it does have a more general definition in terms of something called open sets， but。For us in RD。

 it's just the same thing as closed and bounded。Maybe you know what bounded means。

 bounded just means what you think it means， it's in a bounding box， it doesn't go after infinity。

Closed means that it， you know， it doesn't have any so called limit points， which are not in the set。

 So， for example。Imagine， so closed means you know contains。All limit points。So for example。

 you know， if you just look at the line。From zero to one， look at the interval， you know。

 zero comma one， so it contains zero。But it doesn't contain one so's。Sorry， know for some of you。

 I'm saying things， some of you maybe not familiar with these terms， some of you。

You've seen this a long time ago。So this half open interval is not closed。 Why one is a limit point。

 What does it mean to be a limit point？Being a limit point means so one is a limit point because if you take arbitrarily small balls。

 arbitraryarily small intervals around one。There's no way to do that。Without intersecting the set。

 So like the set is the the set is S， right， So this is S。

If you take an arbitrarily small ball or an arbitraryarily small interval around one。

 no matter how small you make it。Any interval around one is going to intersect S。

That is the definition of a limit point， so we'll say that one is a limit point of S however。

 one is not in S in right in this example， so S is not closed a closed set is a set that contains all its limit points。

But if you took the closed interval。That actually contained one。

Then then the closed interval does contain all its pivot points so this would be a close set。

So convex bodies are closed and bounded， so you know， like this is a convex body in R2。

This is a convicx body。That's a convex body。E cetera， it's what you think， Okay。

 so just think polytope。In some maybe high dimension。And a convex body。Oh。

 and I should say it's a comic conve of RD。And with non empty interior。

So if I just have a singleleton point， for example。Or if I have a aligned in three dimensions。

 I'm not going to call that a convex body， it has to have some volume。

For me to call it a convicx body。对。And a convex body is symmetric。If let's call it K。

Its symmetric if。X and K。Implies that minus x is in K。Just like coordinate wise negation。

In particular， notice thatsymmetric a symmetric convicx body has to contain the origin。

 it has to contain zero。Why， because since it has non empty interior， there's some X in that body。

And then minus X has to be in the body。And then the line from x to minus x has to fully be in the body because it's convex。

And the line from x to minus x contains0。It's halfway through the line。So。And then now。

A fact which I'm not going to prove is that。Symsymmetric convex bodies。

Are basically the same thing as norms。Okay。So。😊，For every norm that norm defines a body。

 a symmetric convex body and for every symmetric convex body that thing defines a norm these two things are equivalent So whenever you want to tell me about a norm。

I， you know， you can tell me。You can tell me it by， for example， telling what the body is。

So why is that？So if I have a symmetric convex body。Body K。I can define a norm。

I'll call it norms sub K。Where。The norm of X。Is basically the。

The largest element in the following set。It's the largest T such that Tx is in the body。

So what I mean， for example， like what is the。what is the body associated with the Euclidean space？

It's the it's a sphere。Right so in like dimension two。

The symmetric convex body associated with Euclidean norm in two dimensions is a circle。

It's a circle of radius1。Right， so example。Should it not be like？T such that x over T is in K。

 It seems like if you scaled up X， then the。The soup would get lower。 Oh， yeah， maybe you're right。

Yeah， I think you're right， actually sex over。So let's think about it。So here we have this circle。

It's not a perfect circle， I'm sorry。And then now let's say we have the point， you know。

 we have a point out here。X。Which has， you know。It has norm 1。5。I mean yeah。

So shouldn' it be like the smallest tea So like the inchema。The smallest tea。Oh， yeah。 So I。

 I divided。 I I took soup instead of infant。 I multiple instead of divided。 I think that is right。

 in particular。Like I could set T to be。 Yeah， it made。

 it made sense to say soup when it was multiplied， which was a bug now that I'm dividing。

 it should definitely be in right， because I can divide by T being like infinity and that's gonna go to the origin。

 That's definitely gonna be in K。So now that I'm dividing， it should be， it should be the。区别。就嗯。

Great， so yeah， so the point is。Okay， so I have this vector X here。

If I wanted to stay inside the circle。You know， I need to divide by 1。5 or more。Div divide by 1。

5 or more， I will get mapped into the circle。So since the smallest number I can divide by to make it work is 1。

5， I'll say the norm is 1。5。Does that make sense？对。And then， you know， on the flip side。

 if I have a norm。I can define。The convex body。K， which is defined to be basically the set of all x that have norm at most1。

So I mean， this is how from Euclidean or I get the circle， for example。Oh infinity Nora。

 I would get a square。in high dimensions， how would get a box。A box with side length two basically。

 because it goes from minus one to 1 in each dimension。Okay。Any questions about any of this？And。😊。

Now that you are experts in convex geometry， I'll do one more definition。嗯。If you have。X。

Z is a metric space。And T is a subset of x。We'll say T prime is an。Epsilon Ne。Of tea。If。

For all X and T。There exists in x prime and T prime。Such that the distance from x to x prime。

Is that most epsilon？And then there's the entropy number， so called entropy number。And。TD， epsilon。

Is the size？Of the smallest。Apsilon Ne。Of tea。Under metric D。So a picture there。

Let's put it here a picture there。 I mean， let's just say that x is the real line。

 and let's say that， you know the distance between x and y is just the absolute value x minus y。On x。

 which is R。And let's let T just be the integral from zero to one。Yeah。

 I don't I thought I fixed this bug of phone number showing up with my iPad， but I guess not。嗯。

So what is it good what's the kind of what's the best epsilon net， I mean。

 you can be basically you just place a grid on this thing where you know。

 you take the point at epsilon， you take the point at two epsilon。

 you take the point at three epsilon。All the way to the point。Kind of。One minus epsilon， I guess。And。

 you know， these red points are an Epsilon net， and they're basically the best you can do， right？So。

 you know， see question， you know， it sp it out by two epsilon because then。

Each one could go to the left right to get one that's with an epsilon。Oh， actually。Yeah。

 that's a good point。嗯。I guess the first one would have to be ups， okay， so yeah， maybe you're right。

 but I guess like I'll just be a little sloppy I'll just say this thing。In this case。

And now I'm getting my notation a all confused。And of， let's say， you know， zero1。

Where this is like just absolute value， I'll call it epsilon is， you know。

 it's some theta of one over Epsilon anyway。Yeah， maybe you can do what you said in Sa factor too。

Yeah。Very guys。And now maybe I want to do one more preliminary thing before I finally show you the proof。

Which is that。There's this kind of duality between packing and covering。I can define also。

 so I I define what n means。Let me define a packing number。The packing number。嗯。Let's call it P of。呃。

TD epsilon。Is the maximum number。Of。Pair wise， disjoint。Balls。Under the metric D。A radius epsilon。

That we can pack and tea。So for example， imagine， imagine。That T is like the circle。Of radius one。

And D is also Euclidean space。And then Epsilon is whatever it is， Epsilon is some small thing。

So what we're asking here is。Kind of what's the most number of small circles you can pack into big circle such that。

 you know， the red circle such that。They're disjoint and the centers have to be inside the black circle。

 but you know that might go out of the circle as long as the centers are inside。Does that make sense。

 this is the packing number。Okay。And now I claim that。Claim。If you look at。And。And let's call it。黐。哇。

Maybe be a little more。Im going to be a little more specific。So let's look at the ball of some norm。

Okay。And let's try to get an epsilon net of it。You know， in its own norm。Okay。

 so this is not necessarily clin orbit it's arbitrary norm。Of Radius epsilon。

I claim that this is at most the packing number。Of。The ball。Under that thing。

With radius epsilon over2。So why is that true so the proof of that is。So let's think， you know。

Let's take the。Let's take example ball。Let's pack as many radius epsilon over two bowls as we can。

Take a maximal packing。Et cetera， each one of these has radius。Expsllent number two。

So we've packed as many as we possibly can， which means， you know。

 if we take any other point that's not in a ball like this point。😡，You know。

 why did we not have put a ball around it， we didn't put a ball around it because the radius Epsilon 2 ball around it intersected some other ball。

It violated the packing condition of disness。Now take these now take all these centers that did have balls。

 so all these centers。And expand them to have radius epsilon bowls。

So take those same centers and just have latest episode。And the claim is that these bowls。

These green balls。Cover。All of the。By triangle on inequality。Yeah。Right， so。

Why pretend that there's some point？And the ball and the big ball。

 the black ball present there's some point that's not covered by any green balls。

If it's not covered by any green balls。It's distance from every single red point。

Is more than epsilon。Which means if you draw a ball around it of radius epsilon over  two。

That ball doesn't intersect any of the other radius epsilon over two balls around。

 it doesn't intersect any of those red balls。RightIf it did。If it did。

 then it would be with an epsilon of that center by triangle inequality。

But so then this point that's not covered by a green ball。

You could have drawn one more red ball around it， but that that' violates the optimality of your packing right P is the maximum number of balls you could have drawn so you can't draw any more balls。

😡，And you know， why is this a useful claim， it's a useful claim because now。How do you。You know。

 how do you bound？How do you bound this thing？How do you bound the packing number， you can bound。

Via volumetric argument。basically， this is what you saw in the original jail proof。

Basically what you said is， look。All the green balls combined。Or' sorry， all the red balls combined。

Are contained in a slightly larger ball of radius one plus epsilon over two。😡。

So you have a bunch of balls， red balls。Of radius epsilon over two， they're disjoint。

They're contained in a larger ball of radius1 plus so you have a bunch of radius epsilon over two balls that are disjoined containing a larger ball of radius 1 plus epsilon over two。

So just by comparing volumes， you can say there can't possibly be too many of these red balls。

 otherwise that would have too much volume that wouldn't fit larger in the larger yellow circle right this yellow circle is this yellow circle that's guaranteed to contain all the red balls。

😡，So this has radius。One plus Epsil or two。So you know that this thing here has to be at most。

Basically， one plus epsilon over two over epsilon over two raise the dimension。

Which is equal to kind of one plus。嗯。So is this。One those two of uppsilon， I guess。Right。

So the quarollary。Is that this covering number。This interviewpy number。

Ass always at most one plus two of reppsilon to the dimension。So we're going to use that fact， Okay。

 good now you know enough preliminaries that we can actually do the lower bound。

Questions got any of this？Okay。So just a quick question the the first inequality of the covering number to the packing number holds for any metric right not just yeah。

 that's true yep any metric Okay any any norm space。R。Well。

Does it need to be normal does it need to be a norm， I don't necessarily water quality。Yeah， I guess。

You're right， maybe that first inequality， I think。Can be can be an arbitrary metric。

 but then for the packing argument or for the volume metric argument you need it to be enormous。

 that need to be an answer。Thanks。Okay， so， so now the jail I still confusing what the entropy number is。

mean， what does it mean？😡，Yeah， so so we have the definition earlier of what an Epsilon net is。

 right？Yeah。And the interviewtropy number is just， you know， like， so these red points here。

 that's an Epsilon net， but I could I could just add a bunch of more points just unnecessarily。

 I would still have an epsilon net， right？😡，Okay， you see here I'm just adding more and more points。

And the interview number is just like think of it as an optimization problem。

 like find me the smallest epsilon net。😡，up team。Okay。The size of the smallest epsilon net。

 that's the entropy number。Right。So here， when I say that the intropy numbers at most one goes two erups line to the D。

What I'm saying is always there always exists an Epsilon net of size and most one still over up solidity。

If you're trying to cover the ball with you in its own norm。Okay。So okay， so okay。

 we have2 minutes left， so I mean， let's try and get it out to the actual the meat to the proof。

 I think we have time。So the first observation。Is that if x contains zero？Then。And also， let's say。

早声。X contains zero。And all other points。Have unit norm。Euclide in normal。Then I claim that。

Then this is all Euclidean。Then I claim that。嗯。F has distortion。You1 plus epsilon implies that。嗯。

For all X。Y in Capital X？If you look at the dot product of F of x and F of Y。

It's going to be equal to the original dot product。Well an additive error at most epsilon。So。

The proof of that。And I'm going to translate F is translated to that F of00。Right。

 so the point is okay， so x contains zero， I can assume without loss of general that F0 is zero just by translation。

If F has distortion multiple subpsilon， it implies that it preserves dot products， why is that true？

That's true because if I look at x minus yl2 norms squared， that's equal to all norms from now on。

 unless I say otherwise are Euclidean。That's equal to x squared plus y squared。

Minus twice the dot product。Meanwhile， if I look at F of x minus f of y。Hel squared that's equal to。

Im x squared。Plus of y squared。Minus tries the dot product of x and f of y。And you know that。

Because x contains0 and f has low distortion。The distance from f of x to zero is approximately the distance from x to zero。

 which is one because they all have unit norm。So F of x has norm roughly one plus epsilon。

 one between one minus epsilon and one plus epsilon， so this is one plus or minus epsilon。

This is also one plus or minus epsilon。This is one， this is one。

This is equal to one plus or minus epsilon。Times x minus y sum norm squared。Okay。

So if you just rearrange these things。嗯。Basically what you get is that this implies that。

And of F of x。Dotted with F of Y。Is going to be。At most。

 like some epsilon plus epsilon plus some you know。嗯。

Plus or minus so let's say let me do what I think this。

The difference between this and the actual dot product。

Its going to be at most in epsilon plus epsilon plus another epsilon times the norm squared between x and y。

But by triangle equalityality。X minus y has normment most。2。So x minus y squared has no atmost four。

So this is at most six epsilon。Does that make sense？

So preserving distances on unit norm vectors together with zero implies you preserve dot products up to an additive o of epsilon。

I don't want to keep drawing the six all the time， so let's just call this epsilon。Okay。

 so now what I'm going to do is I'm going to define。

What was what did other points mean in that observation。You know x x has endpoints， right。

 so like one of them is zero and then the others are just the other points。Does that sense。

X is zero with plus a bunch of other points。And those other points I'll have un Do。So the strategy。

Is going to be as follows。 I'm going to define。A collection。A of point sets。

Such that if it's true that for all oh these all point sets， by the way。Are going to be。Size N。In RD。

I already。If it's true that for all point sets in a。There exists in embedding F， mapping x to RM。

With distortion Wimpos epsilon。For。M let's say much less than 0。001。

Log n over uppson squared so much better than the jail bound by some big cu factor。

Then there exists in injection。G， mapping the collection。Into。A set of size。

Smaller than the collection。Which is a contradiction？对。

So what's the assumption I made to arrive on this contradiction？This I said， if for all x。

 there exists this F。Right。So since there's a contradiction。

 it must be the case that there is some x for which there is no such f。

So there is a lower round again， I don't know which X that is。

 I just know it's some X in the collection， but I don't know which one。Okay。

 so what is the collection going to be？嗯。Now let's。For a set。S， subset of D。Of size K。Yeah。Define。嗯。

Let's call it。Whyice sub S。To be the indicator vector of s divided by root T。

That implies that by root case already。What I mean by that is if you look at YSI。

This is going to either be one of a root K。If I is in S and0 otherwise。

And I'm going to set K to be something like。100 over Epsilon squared， I think。Yeah。

 let's say I0 everyone on screen。Now what do I know。

 I know that basically dot products and COVID information， if I look at EI dotted with YS。😡。

This is either going to be one over K or zero right， E with EI with YS is also known as YS sub I。😡。

So that's exactly as above。So whatever root Ka， I would actually。

So I think I want the00 to be in the denominator。One over 100 epsilons squared。So Ei。

ys is either going to be 10 epsilon。If I is in S or is0 otherwise。佢几。So， you know， if I had。Now if。

My F preserved doc products。Up to you plus or minus epsilon。

 that would give me something like kind of F of EI dot with F of YS。Is either going to be like。

At least nine epsilon if I is an S。Or at most epsilon， if I is not in us， so there's still a gap。

And then I'm going to find my point set， I'm going to look at point sets that look as follows。

Imagine that like X。It actually， you know slightly slightly fib， it's not going to be a point set。

 it's going to be a sequence of points， a point sequence， possibly the repetition。

So it's a two of points that looks like0 E1 up to E D， together with like Y S1， Y S2 up to like Y S。

N minus D minus1。So it's a sequence of endpoints。And A is like the collection。Of all such X。

So notice that the size of a is equal to basically。You know， the first D plus1 vectors are fixed。

 they're just zero up to they're just zero e1 up to ED How many possibilities are there for YS there are D choose k because you have to tell me which things are going to be an S。

😡，So D chooses k raiseds to the n minus d minus1。Okay。😊，Does that makes sense。So。嗯。Any injection。any。

Injection。Of a。And to say like zero one。Bit strings of length。You know， S。Must have。

As being at least。呃。The logarithm of a， which is n minus d minus1 times。

Lwing of D choose K is roughly。K times the log of D over K。Okay。hich诶。Is， you know basically。

You know， n times k。 what is， what is K it's one of Epsilon squared and n of Epsilon squared。

Times log of。Epsilon squared D。And for now， let me make the assumption。

 this assumption can be removed later， let me make the assumption that D is exactly equal to n over logan of rhpsilon。

You'll see where that comes in and I'll see why that assumption can be removed。

But then this becomes basically。Anna Rupslon squared。Log of。Epsilon square D。

 and let me also make the assumption that。Epsilon is much bigger than both one over root N and one over root D。

Why why is that a reasonable assumption again， there's always an embedding into dimension n minus1 with no distortion。

😡，There's always an embedding into dimension D， namely like the identity map with no distortion。

So how are you going to prove a1 e uppson squared lower bound if1 uppson squared is bigger than n or D。

 you can't。So lets we're going to make the assumption that basically one over rhpson squared is much less than the min of n and D。

 or in other words。Epsilon is much bigger than。The max of one of a root N and one of root D。

So then Epsilon squared D。You know， which is epsilon squared n over log order Epsilon up to a constant is the same as log n。

 So this is basically the same as。Yeah， the epsilon squared inside the log doesn't really matter much because it's so far away。

这是被谁呀。Thes are black。AndAnd here。So what are we shown。

 we've shown that if you inject into B strings of length S。

 we need us to be basically at least up to a constant anorpson squared log n。

And then what I'll show you is。Low distortion。Embedding。Exists into RM。For all X in the collection。

Implies an injection。Into bit strings。Of length。O of NM。

So I'm going to show you that if every single one of these point sets has a low distortion embedding into m dimensional space。

 that implies the existence of an injection into mid strings of length Nm。

So that implies that NM has to be at least up to a constant n over Epsilon squared log n。

Which implies that M has to be at least sort since we're long。

That's where our lower is going to come from。And how does you get the end inside the log？

How do I get the what？TheThe and inside the log that absolutely do Yeah， so I had this。

Inside the log。And then I made this assumption。And then I also made this assumption。

So basically that you know。

![](img/ca3266c71b2ba7d934020b155e2dbc01_2.png)

Let's say I'm assuming that specifically oops。Can I lose my new share。



![](img/ca3266c71b2ba7d934020b155e2dbc01_4.png)

Okay。So specifically what I mean is like， say epsilon is bigger than one over n to the 0。49。

 for example。Then epsilon squared n over logar epsilon is still polyn。It's still end of the 0。

01 or something。 So log of N of the 0。01 is still omega log n。Does that make sense？Hello。Yeah。

So maybe can you ask me offline after after because since we're running out of time， Yes I。嗯。So good。

 so this is what I need to show I need to you know。

 basically the name of the game now is showing this thing。How do I show this？

So I want to kind of represent which points that I have。

I want to represent which points that I have by some encoding of length N M。Where do I know。

 I know that I have an embedding into dimension M。So why don't I make this my encoding？

I'll just write down。I'll write down F of0。 I'll write down F of E1。 I'll write down F of E D。

 and then I'll write down F of Y S1。 I'll write down F of Y S M I T S1。You know。

 each one of these is an M dimensional vector， so each one is M numbers， they're n of them。

 so that's NM numbers， so here's an encoding of length N M。And if I have this。

 I claim that this is enough， having this is enough。To recover， well， first of all。

 I know what all the EIs are， what I don't know are the YS is， I don't know what thes are。😡。

But I claim that if I have all these Fs， I can recover the Us because of this。

I can just take all the dot products between the EIs and the YSs。😡。

Whenever a doc product is bigger than9 epsilon， I know that means I is in S。

 whenever it's less than epsilon， I know that means I is not an S。

So I can recover every single S just via the information from these dot products。请。😊。

So what's wrong with this， why does this not work， any takers， anyone see a problem with this？

So since we're running out of time， I'll just tell you。The problem is that these are yes。

 these are NM numbers， yes I can I can decompress and this is an injection because I can recover the information from this the problem is。

😡，I want to have an injection into a small set， specifically bit strings。Of length at M。

F of0 is not a bit stringing of length M， it's a real vector of length M。

 so the entries of f of0 are real numbers。😡，So， you know。

 my encoding length is not even finite because every single number here is a real number of infinite precision。

😡，So here's my first attempt at a fix。Okay， which is all round。Each entry。Of know， each other X。

To an integer， to the closest integer multiple。Of gamma。

 where gamma is going to be some a small number。Think of gamma is like much much smaller than Epsilon even。

And then now the point is if I look at。F of x dotted with F of Y。Now there's going to be some error。

 right， because this is equal to the sum overall I of Xi plus or minus gamma when I round to the nearest multiple of gamma。

I'm changing each entry by at most camera， right？😡。

So x y plus or minus gamma times Yi plus or minus gamma。Which is equal to x dot y plus some error。😡。

Because of the gammas。And I'm not going to show it， I'm out almost out of time， but you can show。

That if gamma is less than something like。I think epsilon over。Rudan。That implies that the error。

Is that most？Epsilon in magnitude。So what does that mean？That means that。You know。Now let's。

 you know， basically what I'm doing is I'm rounding， I'm rounding these things。These F's。

 I'm taking that vector and I'm rounding it each entry wise to multiples of pianoma。😡。

So now if I look at F Tilde EI and F Tilda of YS。This thing is going to be at least eight epsilon because I'm going to lose an epsilon。

And here it's at most two epsilon。But there's still a gap。

 so I can still tell which case I'm in so that I'm still golden。Okay。

And so now this actually is a finite length encoding right because I don't have real numbers anymore you know each entry of the real you these are m dimensional vectors。

 but each entry is a multiple of gamma， how many multiples of gamma are there between minus1 and one right each entry of this vector is definitely going to be between minus one and one。

😡，So， you know， there are only two over gamma possibilities for each entry。

So the number of possibilities for any vector is at most roughly two over gamma to the em power。

Right so my encoding length。Is that most n times？嗯。M times basically log of one of gamma。

The number of possibilities is2 over gamma to the M。

 so to write down which possibility I have takes log that number of bits。

 which is m times log 1 over gamma。So now you get that。N M log1 regamma。Has to be at least。You know。

 the same lower bound we had above。En of Epsilon squared log n。And if you， if you solve for M。

 you know， the ends cancel， you solve for M， basically what you're going get into at the end of the day is M is at least。

1 over epsilon squared times log n over log1 over Epsilon plus log log n。Okay， so， you know。

 it's not terrible。It's pretty close to Nogo loansan lower bound。

But Nogo alone didn't have this term， so it's very slightly worse than Nogo alone lower bound。

And now you stop， you know okay， so we have only basically 30 seconds left。

 so here's what I'm going to do， I'm going to tell you a slightly better fix。And then on Monday。

 I'll tell you the final fix to get the optimal bound and you know， given what we've done so far。

 explaining that is going to take less than five minutes， but unfortunately we're out of time。

So here's the new， so the first fix was。We're going to round each entry of the vectors to the nearest multiple of gamma。

😡，Now， what is that really doing， it's really it's really taking an L infinity net of the L2 ball right I know that all of these Fs F of x is contained in the L2 ball of radius one pluss epsilon or something let's say almost radius1。

😡，And I'm taking entries of that and rounding them to the nearest gamma net。

 to the nearest elements of a gamma net under L infinity。fin L infinity distance between two vectors。

Nowinfinity norm is just the magnitude of the largest entry right so I'm saying that you know I have X and I have and I want to round it to x prime such that for all I X I minus x prime at position I is at most gamma in magnitude so that's saying that I want to have an L infinity net。

😡，Of quality gamma。So the better fix。The better fix， actually。I's to around。To an epsilon net。In L2。

Don't round to a gamma net in L infinity， round to an epsilon net in L2。ok。

So and then I'm going to ask myself， okay， now what's the encoding length。

 basically for each one of these Fs， F of x's。😡，I need to tell you。

Whi element of my Epsilon net was the closest element？To F of EI or to F of YS。😡。

How many bits does that take？Well， how many， you know， what vector is it in the Epsilon net？Well。

 the Epsilon net has size equal to the entropy number。

 right the entropy number is the size of the smallest Epsilon net。😡。

So how many bits does it take to tell you which element of the net I have log of the entropy number？

😡，Okay， so then what you get is basically like n times log of the entropy number。

Is at least Npson squared log n。And you know， if you just solve for what the interviewtropy number is。

 you're going to get something like。M is at least one over Epsilon squared。

 log n over log one over Epsilon。So you're going to get the same thing as before。

 but without this log log in in particular， this is exactly Noga Lo lower bound。😡。

But it's a completely different argument， his argument didn't go like this at all。

And then you have to do one more kind of final clever trick to get rid of the log when interruptrups lawn and that's what I'm going to show you on Monday because I'm out of time right now but it's really not a big step from it's not a big jump from what we've done。

😡，Okay， so I'm out of time， let me end the recording and then take questions。



![](img/ca3266c71b2ba7d934020b155e2dbc01_6.png)