# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p09 -09-(Lecture 9_ A Taste of Compressive Sensing).zh_en -BV1yqVzzqEQ5_p9-

Today's lecture is going to be a continuation of this theme of exact recovery。 So I'm just curious。

 how many of you have heard of the buzzword compressed or compressive sensing。Some of you， okay。

 it's somehow like it's actually very C S S， but sort of comes from different fields。

 And not Ill some computer scientists don't actually hear about it。 So I'm glad after this lecture。

 all of you will know about it。 So， you know， just reminds you what the theme was。

 we sort of in the middle of studying problems that are generally NP hard。😊。

But we're asking about additional conditions on the input under which a heuristic which normally would not solve it optimally because it's a polynomial time heuristic and that'd be hard problem but under these extra conditions actually this heuristic does recover an optimal solution So two lectures ago we were talking about stable kdian instances and we looked at the single link plus plus algorithm which basically optimizes only over a subset of the possible solution so it can do it in polynomial time but we showed that a kdian instances are stable then actually the optimal solutions guaranteed to be in that restricted part of the space and it's actually going to recover the optimal solution then on Wednesday we studied cut problems。

 ST cut was our warmup and then in multiway cuts and we looked at a linear programming relaxation which again generally is not going to be optimal。

 but if it's a stable instance then linear programming does give you the optimal solution So those were cases right so this lecture is going to be another one in that same theme and this is about solving linear systems。

So consider the problem。You're given A， you're given B。 You want to solve for X。

 A or just real values。 that can be anything。 So it's just your typical linear system。

 But imagine A isn't square。But rather imagine there are fewer rows than columns。Okay。

 so there's your A。Here's your X。And there's your B， your right hand side。So how many solutions。

 feasibleas solutions Does a linear system like this have。

There's actually sort of two answers to that question， could you one of two things。

Either what or what。It could be none， where it could just be。

 you have a couple contradictory constraints。 What if you do have one solution。

 It is going to be unique。No， there's actually going to be an infinite number of feasible solutions。

 right， So because it's an underdetermined system， right。So if M equals n and it's full rank。

 if it's invertible， then there's a unique solution， namely a inverse B。But in general。

 if you have fewer rows， fewer constraints than degrees of freedom in X。

 you have an infinite number of solutions。 whenever you have one。

 One sort of heuristic way to think about this is it's almost like as computer scientists。

 you can almost think of it like each row of this system gives you one bit of information about x。

 Okay， not really a bit because these are real numbers。 But it gives you like。

 it pins down sort of one of the degrees of freedom。

 right So if x is in R n and there are n degrees of freedom。 So to know it uniquely。

 you need to pin down all n degrees of freedom。 So you need n constraints。

 So if you pin down only M of them， still the subspace of rank n minus M of feasible solutions。

So it's an undedetermined linear system， shortly， I'll tell you why one might want to care about these things。

But let me just sort of say what's going to be the nature of the computational problem。Basically。

 amongst this infinite number of feasible solutions。

 we're going to be interested in singling out the one which is somehow the most。

 the best or the most meaningful。And in compressive sensing。

 the definition of meaningfulness is sparsity， okay？So we call a vector x。Case bars。If。

All of its entries are zeros。Except for most k of them， so most k。Non zeros。

So I'm going to use the notation SUPP of X this denotes the support。By definition。

 that's the set of coordinates on which x is nonze。 So the number of non zeros is at most K。And。

 you know， for concrete values， maybe think of K， you know， if x has length n。

 maybe think of K as like root n， maybe even log n。 Okay。

 so those would be it's not we want to think of as constant， Think of it as bigger than constant。

 but much smaller than n。Okay。All right。The perspective of this lecture or really this topic。

Is that sparse the solutions are more meaningful。对。

And there are many applications where this seems like a quite justified assumption。

 I mean a couple caveats。 So you know in applications there's usually kind of two twists on sparsity that you need to make it really practical。

 The first one is is like okay so you know maybe the vectors and like zero in n minus k coordinates。

 but it's really small and n minus K coordinates。 So sort of most of its mass is concentrated on just k coordinates。

 So that's the first kind of relaxation you want to do。

 The second thing is a lot of real applications， your sparse not in sort of the standard basis。

 but in some other basis， like the four year and wavelelet base are popular ones。

 And so but the point is everything I'm going to tell you about today in this lecture。

 both the results and the way the results are obtained also extend really quite elegantly to those extensions having approximate notions of sparsity or sparsity and bases other than the standard one。

 So for the lecture let's just keep it simple。 I'm only going to talk about exact sparsity and we're gonna to be thinking about sparsity meaning the standard basis。

 So there's literally just in the x that we're looking for there's can non zeros and the rest of zeros。

All right。So then the computational problem we're thinking about。Again。

 has this exact recovery flavor where there's some ground truth ors some planted solution out there。

 and we want to know， when can we get it back。So recover。Some ground truth。K spae solution。 Okay。

 so we're given A， we're given B。 Let's think of it as we know K。

 And we're going to assume that there's some K sparse solution。 And the question is。

 can we get it back。是。So that's going to be the kind of problem that we're thinking about。Allright。

 so why， why think about this。So let me tell you about sort of the compressive sensing narrative。

So here。It's sort of a shift in how we're usually thinking about it。 right， Normally。

 we think of sort of， you know， the input is like， you know， coming down from the skies。

 And we just have to deal with it。 we're just given this A And B。

And so we've talked about some things like what are some conditions on A and B where hopefully。

 you know， if nature is providing this input， know maybe you know it has extra structure and we can do some exact recovery。

 The compressive sensing narrative actually， you're usually responsible for actually designing the A and B。

 So if you studied error correcting code， that's sort of in the spirit of error correcting codes where if you're gonna to have a linear code。

 know， maybe that defines it encoding and you want to somehow choose a matrix A to make your life easy later。

 Like it's easy to decode， for example。So it's sort of similar here。

 And so the way one normally thinks of it in compressive sensing is you think of， you know。

 there is some vector X。 So forget about A and And B for a second， there just is an X。 Okay。

 some ground truth， a signal they would call it。 And that could be you know。

 like something like some image you're trying to reconstruct or something like that。And the point。

 and then you make measurements， you somehow try to access this ground truth X。

 And the way one thinks about it is one thinks about a row of this linear system as a quote unquote。

 linear measurement of X。 So think about it this way。Each row of this matrix。

 right So this is an n vector。 And this entry over here is just the dot product of this row with x。

 Okay， so each entry of B is just some encoded version of x。

 is X dot product in a product with some other vector。 So in that sense。

 each of these can be thought of as a linear measurement of X。 So the more values of B you get。

 the more linear measurements you take， it seems like the more information you're getting at about this unknown X that you'd like to recover。

😊，And so then what people think about is， okay， how can we actually design measurements。

 how can we actually design these linear systems so that from A and B。

 we can actually recover what x is。Now， we already talked about how sort of the obvious approach would be。

 well， why not just take n linearly independent measurements。

 So why not just find an n by N matrix A， which is invertible。

And then if you're also given the right hand side， you just multiply both sides by a -1。

 and you recover x。 So that would be n rows， N measurements。

So the whole deal in compressive sensing says， well。

 what if we assume more about the structure of the unknown signal X， and in exchange。

 perhaps we can get away with fewer measurements。 That is fewer rows，So by contrast。

 if you think just about。K sparse vectors。Now， intuitively， there's not as many degrees of freedom。

 There's not as much unknown about what X could be。

 So the hope would be that many fewer measurements suffice。 Okay， So that's sort of the idea。

So what are some applications was like？One buzzer word you can look up。

Which was sort of popular early in the field。Was the single pixel camera。

So I'm not going to say much about this， I'll just sort of tell you the idea。But， you know。

 it's widely thought and sort of empirically validated that images that people take in the real world are。

 in some sense， sparse。 not sparse and sort of the obvious basis。

 but they'll be some other well studied basis like a waveth basis under which real images are sparse or approximately sparse。

 I mean， indeed， if you think about sort of signals which don't have any sparse representation。

 people usually think of those as like random noise。

 so real images have sparse representations in some sense。

 And so somehow like the sort obvious way to sort of take advantage of that that you might first think about it like。

 okay， you get your camera， you pack in as many pixels as you can。

 So you just get as much information as possible when you take the actual photo。 know。

 and then later， you run some compression algorithm on it and it squeezes it down。

 and probably you can squeeze it down to something much smart than what the camera took without really losing anything as far as being able to reconstruct it later。

 So the idea here is， well， you wouldn't it actually kind of be a lot smarter。

 if at the end of the day， we're just gonna have this compressed representation。

 Why don't we just have the camera just like。Actually take that compressed representation right away。

 I mean， the image it wants to take is already low dimensional。 It was already sparse。

 So why not just take a small amount of information now for later reconstruction。So in that context。

 you want to think about X as sort of the sparse representation of the image being taken。

 And then you can think of these linear measurements as just things like random dot products of the know light intensity at each of the pixels in the camera。

 so you you're literally just， I remember， this is one number This is a whole bunch of numbers like the light intensity。

 all the different pixels。 And you can think of if you choose this to be a random row。

 then this is going to be a random inner product between your image and and some dot product。😊。

And so then what this would say is actually， rather than just storing in the naive way。

 the light intensity of every pixel， you just store all these random linear combinations。

 and you can get the image back later。Another application is in MRI。 so magnetic resonance imaging。

 And so there so this is where you're trying to take a scan。

 like of someone's brain or some other part of their body。

 And so there the number of measurements like literally corresponds to the length of time of this scan。

 And when you get an MRI， you've got to stay really still depending on what you're taking a scan of。

 you might even have to not breathe。 So it's pretty clear that less measurements。

 meaning less of a scan time can be a pretty big win。

 that's why people care about this kind of stuff。Okay。So that leads to the questions。

How small can a linear system be so that at least in principle。

 so at least in principle you have enough information to recover a case sparse vector。

 but then also of course， if we don't just want to know that there's some unique sparse reconstruction。

 we also want a fast algorithm that finds it Okay we want to answer both of those questions。

All right。So。For this to be doable。Again， let's sort of think about the lines in the sand。

 So we need some assumptions about what the matrix A is。好 right。

So the first thing we've we've already sort of touched on， which is that you know a。

 we want it to be non-trivially small， So we want it to have fewer than n rows。

 but there's going to be some limit on how few rows we can get at。

 so like imagine a had just one row。 imagine like K was 10 so these various sparse vectors that X might be。

 We have no idea which one。 We just know it's some 10 sparse vector。

 And imagine it's like an a with one row。So we take one linear measurement。 we get back like 7。 like。

 this is clearly not enough information to like reconstruct which of the case par vectors the real world is。

 okay。So， you know， so the first naive thought might be， okay， well， we said we kind of needed。

 you know， one row to pin down each degree of freedom that X might have。 Okay。

 and the first thought might be， oh， as a K sparse vector， that's kind of like K degrees of freedom。

It's actually a little more complicated than that， right because like thinking even just about like 0。

1 vectors that are k sparse。 So remember， x has length n。 Okay， So the number of 0。

1 K sparse vectors， that's the number of ways to choose the K coordinate to the support out of ns。

 like n choose K。 So that's something like n to the K such K sparse vectors。

So just thinking sort of heuristically， if we think of each row of the matrix。

 maybe it's giving us like one bit of information。 again， that doesn't really make sense。

 but just heurically， maybe we get a bit of information from each row of the matrix。

 then to kind of pin down uniquely which of these n choose K possible sparse vectors it is。

 we're going to need log of n choose K rows， which is basically like K log n。Jeremy。

 but if X were 01， couldn't you pick like。Primes or something on one。

 So like consider the single row that like。I suspect that if x is01。

 you can do something with a single row Okay I guess I mean。

 the point is like think about the supports。 suppose it's an unknown support And it turns out so if you think about it for a second。

 you realize that actually if you knew the support of x then you could recover it because you just force the other coordinates to be 0 and then you'd have a normal linear system and you you'd resolve for the unique solution x So it kind of boils down to knowing what the support is。

 there's n choose K choices for the support you can find it you don't have any if x is01 and you don't have any bound on the size of the entries A。

With a single row， Okay， but， I'm just trying to motate there's going to be this K log again I'm trying to motiv where it comes from。

 Okay， the point is there's N choose K choices of a sport。

 And sort of the best case seems like you get a bit of information for each row， okay。So， E G。

Maybe we're gonna to hope for something like。And better be at least K log n。 Actually。

 It can be slightly smaller than this， but I'm just going to stick with this for lecture。

So MS be sufficiently big， but we want to be way less than n。 Okay， so like K log n。

 we'd be pretty happy with if we're thinking of K as being root n or log n or something like that。

 This would be way less than n。And again， I hope you have the intuition thatre like， K。

 we don't think is enough。 There should be some dependence on end because of this freedom of which of the N coordinates are actually in the。

 in the sport。Okay， but so that's actually， that's also not enough。 Even if you take M to be。

 you know， something like this， theres still going to be some A's， certain matrices。

 A for which this is not going to work。Even if it's a full rank， full row rank。

 like think of it A as like super sparse。Okay， so maybe all I do is I pick， you know。

 M different columns， and I stick a single one in each。Okay。

So now if you hit this very sparse matrix with this very sparse vector x。

 B is going to be like mostly zeros， pretty much no matter which sparse vector you started from。

So again， you end up not getting information about the sparse vector X。 So at the very least。

 A better not be super sparse。So it's awesome we're also not not thinking we're going to prove that this is solvable for all A。

So those are some lines in the sand。And so the questions we're going to ask is how。

 how big does M have to be and what extra conditions on A do we need before， first of all， again。

 at least in principle， there's a unique Kparrse vector X that solves this problem。

 And then secondly， we have an algorithm that will find it for us。So any questions about that？

But the definition of the problem or。Why it's interesting。What wass the intuition。That's just， again。

 this was so the vague intuition was。This is just sort of log。Of N shoes， K。

So these are the number of different supports of size K you could have in an end vector。

And so somehow， like， this is some kind of， like， if you think of it in terms of entropy or information。

The sort of amount of uncertainty in what x could be seems to be sort of lower bounded by this quantity。

And if you sort of believe that each row of A is only to give you a constant amount of information。

 then you would need this many rows。Again， that's heistic。 I mean， there is a real proof of it。

 There is a real proof of lower bounds， but it's。I'm intentionally giving you a cartoonish version of the intuition。

Other questions。Okay。So let me actually tell you the algorithm before I tell you about the conditions on A。

 Okay， so we're going to be able to do this without actually many more assumptions than these obvious ones。

With these intuitive ones。And the algorithm is going to be in the same spirit as last lecture in that we're going to look at a linear relaxation of the problem。

And we're going to show that actually the exact solution under some extra conditions of that linear program is exactly the case perspective that we want。

Okay so again it's just we're solving a program and that's just gonna to be returned to us on a silver platter。

 which is great。 And in fact， this whole field basically was born because know the problems。

 the problems it started from the applications and people tried this heuristic and then they observed they got exact solutions back when they weren't expecting it at all and then they asked okay what's the theory that would explain that And that's really the origin story for compressive sensing。

😊，Okay。So。So the algorithm， we're to solve linear program。And， you know， clearly， one of the。

Some of the constraints are going to be this， right So we're given A， we're given B。

 We're looking for a， we have some parameter K。 We're looking for a Kpar solution。 So in particular。

 it better be a solution。And。So trying to directly say。

 minimize the number of non zeros of a feasible solution， That's an N hard problem， it turns out。

Okay，It has a discrete flavor， So it's not shocking。 If you just say amongst all solutions to this。

 find the one with the minimum number of non zeros。 We can't do that。

That's sometimes called L0 minimization。 We're going to do heuristic。

 which is called L1 minimization。 And again， the motivation is this is something we can formulate as a linear program。

 And as we've discussed， linear programs can be solved efficiently。

 both theoretically and efficiently。So here's the exact encoding。

So this is going to correspond to the L1 norm of the vector X。 So remember。

 the L1 norm is the sum of the absolute values of the coordinates。

 and we already saw on Wednesday how to encode absolute values as linear inequalality。

 So we're going to do that again here。So YI is at least Xi， and Yi is also at least。Minus X。

So for i equal 1 of the K。嗯。So this is just a direct formulation of saying amongst all feasible solutions to this linear system。

 Comp the one that has the smallest L1 norm， the smallest sum of absolute values of coordinates。

 because that's exactly what this problem says。 This is not the problem we care about or that we should set out to solve。

 And there is no reason why one should expect this to work。You really， I think， would first expect。

 if you solve this， which you'd get back is a solution to this linear system。

 which probably has a nonzero value in every coordinate。

 And it's just like super small in most of the coordinates， right。

 Like if you have an epsilon and a coordinate， youre only penalized epsilon in this objective function。

 But for the objective function， we care about number of nonzes， you're penalized one。

 penalized for the whole coordinate， the same as if it's epsilon over its00。

So at least that's what I would have expected this heuristic to do。Yeah。

 so we're just trying to minimize the first K coordinates of x。No。

 so the real problem is minimize the number of non zero coordinates。对。But sure， what is this problem。

 I I that the question in this formulation， by writing eyes today or we just trying to minimize Oh。

 this should be and， I'm sorry。My mistake。That was the typo， thanks。Yeah。I got it right here。

Some for Michael and then。Okay。So there's really no reason to expect this to work。O。

 and I don't think anyone， you know， I don't think people。

 I doubt people would have thought to prove this theorem unless they actually just had the empirical evidence。

 know， slapping them in the face。O。Shu。So here's the main result of this lecture。Which is。

 if we take M。To be K log n。What seemed sort of like a back of the inbo calculation to be roughly about the best we could hope for。

And we let A be random。So random here can mean a few different things。 Okay。

 so one thing would just be populate each entry with a plus or -1，5050， everything I I D。

 Another thing would be you just populate each one with a random Gaussian。So a normal distribution 0。

1。 Obviously， this gives you a dense matrix。 We know you need a dense matrix。 Okay。

 but it turns out lots of sort of Id ways of populating the matrix A work。

the end result is not super sensitive to the definition of a random matrix。Then。

With high probability。Over the choice of A， right， if they're random Gaussians。

 you might get super unlucky and maybe all the entries are 0。They probably not， right。

 So with high probability or with the choice of A。It's the case that for all。Case parse vectors x。

So no matter what the ground truth is。With a X hat equal to B。 So again。

 we're sort of thinking in our minds like X hat existed already。 And then we're choosing A。

 and that induces B according to A， X hat B。So for all casepar X hat。

 that's a solution to the system A B。X hat is the unique solution。To this LP。All right。

 so the plan of how we're going to go about this。It's sort of similar in spirit to how we analyze the single link++ algorithm。

So you might recall a week ago， what we did is we said， okay， well， we have this algorithm clearly。

 it's not always going to work。 Let's first identify some sufficient conditions on an instance under which this algorithm will be correct。

 And then let's argue that in that context， it was a stability property。

 Let's argue why the stability property implies that these sufficient conditions are met。So for this。

 the work we're going to do in lecture is we're going to identify sufficient conditions on a on the matrix。

 the constraint matrix so that we get what we want so that we actually the LP solves to the exact solution。

Then it's going to be the case。 And we're not going to prove this part that a random matrix A does satisfy these sufficient conditions。

All right， so。For which A's is this going to work？Alright， so let's do。

 I need to do some preliminaries。 Okay， it's kind of geometric preliminaries。About different norms。K。

So。It's clear we care about the L1 norm， because that's what this linear program is about。

 It's not going to be totally obvious right now why we care about the L2 norm。

 but we're going to need to compare them。So just to make sure we're on the same page。As we discussed。

 L1 norm。Some of absolute values， L2 norm is the square root of the sum of the squares。Right。

So that's something all of you should have seen？As far as know。

 one thing that's helpful to maybe keep in mind。Based in the next couple of things I'm gonna say is the sort of geometry of these norms。

 You often visualize the geometry of norm in terms of the unit ball。 Okay， so you ask， fix a norm。

 What is the set of points that have a unit norm， What does that look like。So over the L2 norm。

 that's familiar to all of you， that's just the circle。So let me ask you。

 so the unit ball for L1 to the points with L1 norm。

That's either contained inside this bottom drawing， or alternatively， maybe it's entirely outside。

So which of those two possibilities is it？Inside， that's right。

What would you call the shape of the L1 ball？I would call it a diamond， yeah， kite is that reason。

 it's good to yeah。Yeah， diamond was the first thing I was thinking。So this is the L1 ball。

And this is the L2 ball。Okay。So， for example， this would be the point， you know。

 this would be the 01 half，1 half， which has L1 norm 1， for example。 Okay， So in general。

 L1 is the convex whole of the basis vectors and their negatives。Good。So。

Let's recall the relationship between the two norms for any vector。So if we're in RN。And。

I want to ask how much bigger or how much smaller。Could the L1 norm be relative to the L2 norm？Well。

 so something we see immediately here is that the L1 norm is always at least as big。Right。今のな。

The one norm is always at least as big。Right。Because here's something that has L 1 norm 1。

 and the L2 norm is smaller。Right。So， in other words。Yeah。

So everything that has O1 norm1 has L2 norm 1 or less。 and all this stuff is scale and variance。

 So you may as well just focus on the unit balls。So that L one norm is only bigger。

 And for what kinds of vectors is this type。Theres only1，1。 It's tight at the corners， right。

 at the basis， vectors。 right， So if one，1 and the rest are zeros， both of these evaluate to one。

So tights。At the at basis at yeah，'s say Sp well。Basis vectors。All right。

So where do they seem the farthest apart， What kinds of vectors。

So when all the coordinates are equal。Right。So when all the coordinates are equal。How much bigger。

Is the two norm。Compared to the one norm or sorry the other way around。

 How much bigger is the one norm compared to the two norm。A ratioci of D T is the dimension again。

Squaity。Okay， so think about the vector。 that's all ones。 the L1 norm is n， the L2 norm is root n。

And so this。Is tight。When all coordinates are equal。Right。So like if we look at this gap here。

That's going to be a gap of route two。Between those two norms in that direction。All right。Okay， good。

So here' here's the definition。So we're going to say that x。Is spread out。For a parameter C。

If it's sort of much closer to satisfying this inequality with equality。Than that one。

So it's sort of a generalization of all the coordinates being equal。So formally。

We say that this holds in the reverse direction with an extra constant slack。

So this basically means geometrically that we're somewhere far from the basis vectors。

 We're somewhere much more kind of in the middle of these slices。

 Okay If you want to think in three space and you want to think about this sphere。This means。

 you can imagine sort of you know， the great circles corresponding to the axes。

 and we should be sort of far from those。 We should be more in one of the middle of the eight orphans。

So I don't know if you have this intuition。 but as you pass from two dimensions to three dimensions。

I'm going to plant the seed that maybe many more x's are spread out once you go to three dimensions than when you're in two dimensions。

Okay。So I'll give you intuition about why we're talking about this stuff as soon as I can。

 but I need to cover a few preliminaries to get to that intuition。So， intuitively。m。So the key point。

So what I'm going to do here is I'm actually going to state a technical statement。

 which hopefully sounds like it should obviously be true。

 given the intuition of developed for what this is。 but basically what this lemon is going to say。

 and this is what this is the property these spread up extra is actually going to use。

 which is that if you look at its L1 norm and then you just zoom in on a small set of the coordinates of a spread out vector。

 you capture a very small fraction of its overall L1 norm。Again。

 this is totally the opposite of a sparse vector， but a sparse vector。

 if you zoom in on its K90 coordinates， you get all of its L1 norm。So we're saying spread out。

 if you zoom in on just like， say K coordinates， you get very little。Co。

 you can capture like K over n of the original one， but you can't capture a lot like most of it。

 if K is small， okay。So this is the property these things are're really going to need，So。

Consider a subset of the coordinates。You know， maybe think of it being like a root end of the coordinates or something like that。

If you have a spread out vector。Then。So I'm using this notation to say。

 just focus only on the contribution from the coordinates in I so you can either think of zeroing out the vector x on the rest of its coordinates outside of I。

 or you can just think of just restricting the sum to these coordinates。

And so ultimately want to say this is not too much of its overall one norm。Oh yeah。

 so this is just true， good。Okay， so first of all。So what did we say here， Okay， here。

 we said that when you have N coordinates， the L1 norm can only exceed the L 2 norm by a factor of root n。

Okay， so here we have cardinity of I coordinates。 So if we switch to the L2 norm。

It's only you get a blow up of the square root of the number of coordinates。

 square root of Caral of I。So， that's the same。呃。The same squri root as we had there。

Sometimes the L2 norm。And then， using。That its C spread out。 We just pick up。

An extra C over square root of n。Of the L1 north。OK。So ultimately， you know。

 we care about the first term and third term， which are both about the L1 norm of this vector。

 So again， this is just some of the absolute values。 And we sort of use。

 we pass the Euclidean norm in the middle。Basically。

 to pick up the square root and to leverage the fact that it's C spread out。 Okay。

 the definition of C spread out is in terms of the L2 norm。 But really。

 what we care about is this consequence just for the L1 norm。To interpret this， maybe think of sorry。

 too many square roots here。Think maybe of C as like a constant and think of I as being subline。

Okay thatll be one case。 and then then this would be a sublinear fraction。

 this would be a sublinear fraction of the original L1 norm。 For us。

 we're actually going to be taking C to be the square root of n over K。

 and we're going to take the carbon out of I to be K。 I'll show you that when we get there。

So this is what we're going to use。All right。Any questions about that？So again。

 just given if we believe that it's a good definition of spread out。

 you'd expect properties like this to hold。Okay。So now I can tell you about， So finally。

 I'm to tell you the condition。 This is the sufficient condition on the matrix A。

 the constraint matrix under which the L P heuristic will work。

So we they say that the constraint matrix。Is she good。If we look at everything in its kernel， Okay。

 so meaning all。Vectctors， which when they applied to advantage that are nonze。

 every single thing in his kernel is spread out。In this sense。So if all non0 y。In the kernel of a。

Which remember is defined as the y such that AY equals 0。Is sea spread out？好的。

So this is going to be our division condition。So this of course is much less immediately interpretable than the sufficient conditions we were working with last week。

 so last week we had these stability properties we had this narrative saying that in the instances that arise in practice we're sort of hoping there's this sort of pronounced optimal solution。

 this meaningful solution， so that was kind of our non- mathematicalthematic story about why stability was a good condition。

Here if you just stare at this。 This is clearly just a technical definition。 right。

 And there's no real story for this directly。 But then there's this other part of the proof。

 which as well。 But if you pick a random， it's gonna to have this property。

 So kind of most constraint matrices。 and in particular， random linear measurements。

 if we're designing the measurements or work fine。So keep that in mind。Okay， so geometrically。

 what this is sort of saying。 So remember， you know， this is a subspace。Okay， this kernel。

 And so what it's saying， I mean， it's hard in low dimensions， but it's basically saying， you know。

If you have a one dimensional kernel， then it's far more likely。

To be sort of in these directions that are far from the base vectorors。

As opposed to being really closely aligned to one of these basis vectors for a random A or for a random subspace。

And again， try to develop the intuition that if we pass from two dimensions to three dimensions。

 and we again think about the sphere and we think about the three dimensional analog of the diamond embedded in the sphere。

Even more than here， most directions are not that close to the axes。 Okay。

 they're mostly piercing through somewhere in the middle of one of these orphans。 Okay。

 and that only gets more and more true as you pass a higher and higher dimension。

If one was close to an axis who would be in trouble， What do you mean even one？

Even one what let's it's I'm。So it's like a plane right so if the plane is close to one axis。

Then that means be a bad right， so maybe you want to think about like a globe and then a plane going through it。

And so basically， the plane should not be getting close to any of these axes。Okay。But again， I mean。

 with higher dimensional stuff， the analogies with low dimensional space on the go so far。

That's in effect。 In hindsight， that's in effect what's happening given we given what one can prove is true。

Okay， so。So fact。If we take M to be K log n。Then a random A in the various senses of random A I mentioned earlier。

The parameter we're going to use is one fourth square root of n over k good。Oh， I forgot to say。

So like， what， what kind of C should we be hoping for， Okay。

 so remember the definition of spread out， okay。So here， for a given vector X。

 C is going to be somewhere between one。And square root in。So this is one， if it's everywhere equal。

 and it's going to be root in if it's one of the basis vectors。So， you know， what is it saying。

 this is saying， you know， the， as a function of the sparsity K that we're shooting for。

 this is kind of saying how much， you know， below the trivial bound of root N。

 we're getting the spread out property in the kernel of this constrained matrix A。So again。

 you might want to think of like K to be root n。 And then this would be like end of the one fourth。

Which is， obviously， you know， significantly， if you think about it。

 significantly closer to that inequality than that inequality。When you say a random A is this good。

 is saying all random A or this good？What do you， I'm not saying。

 I'm not saying a random is this good with probability one。 Is it some constant probability。Good。

 so with high probability。So yes， being imprecise。I'll continue to be imprecise。

 but at least I'll be suggestive about what I actually mean。

 So with probability 10ing to 0 as n10s to infinity。Yeah， good。Okay， so this I'm not going to prove。

 It doesn't， you know， there are proofs that you know， don't require anything you don't know。

 but it would take a while。 I mean， it would take， I don't know。 Certainly an hour。

 probably more to prove this。 So I'm just going to put a link to a couple blog posts that I think are sort of enlightening on the topic on the course website。

 Okay so we're going take this just as a given。Another。

 I don't know how many of you has studied error correcting codes very much。

 but it might be for those of you who have。 it's worth keeping that as an analogy with what we're doing here。

 So when you study error correcting codes， one way to define linear codes is through its parity check matrix。

 So think of that as an analog to our a and the code words correspond to elements of the kernel。

 so now we're doing linear algebra over F2 not over the reels。 say in the binary case。

 So linear code words are just kernels of matrices and one is typically concerned with studying air correctioning codes with large distance or each two code words have a large hamming distance between them for linear codes that's equivalent to just asking amongst all non-zero code words which one has the lowest hamming weight。

 which one has the fewest number of non-zes。 So good binary linear codes are exactly the matrices for which every single thing in the kernel has a lot of nonzes。

 So here we're just saying the good sort of constrained matrices A are those for which everything in the kernel is spread out。

Okay， so in general， these， you know， not only have a lot of nonzes。

 but they also satisfy properties like this， which say if you sort of if forget about just counting the number of nonzes。

 if you actually count keep track of L1 norm， count L1 norm。

 you have an analogous property not only the not only do you not have all of the L0 weight concentrated on few coordinates。

 you also do not have most of the L1 weight concentrated on few coordinates。

 So you can sort of think of this as asking for sort of a more demanding version in terms of real values and L1 norm of what you typically ask for for binary linear codes。

Okay。Alright， so we're ready to prove the theorem， which I erased。 Okay， So the theorem。

 which says if you pick a random A and K is at least constant times sorry。

 If M is at least K log M times a constant， then the L P algorithm works with high probability。

And if you're willing to take this on faith， all I need to show is that for matrix A。

 which is one quarter root N over K good。I need to show that for such matrices。

 this is our division condition， the LP solves to the optimal。To the case force vector that we want。

So any questions before you do that？I guess we'll see。

 But does the with high probability come from this fact Yes， so， so given C good A is C good。

 exactly。 So the proof I'm do， I'm going to go from here on out says assume that a is good to this。

 then deterministically。It'll work。Yeah， good question。Other questions。政事と言ってる。

All right so we can forget about all this stuff all we're going to need is this property here。

All right， so let me just set up the notation， and then I'll tell you the intuition of what we're going to do okay。

So， proof。And again， what we're going to show。That。If a is good， LP works。So if from'm here on out。

All norms are L1 norms。Okay， we only had to pass to the L2 norm to have that one definition， Okay。

 I forgot to say you if you want to look it up further。

 these types of subspaces where everything is spread out。

 these are called almost Euclidean subspaces that's the technical word for it。

But you't have to remember that。 that's only if you want to read more about it。Okay。

 so now from here on out， everything is now one norm。So what does this mean that the LP works？

We need to show that if you show me any feasible solution to that linear system。So if AW equals B。

Then the L1 norm of W exceeds that of x。The planted solution。O。So if this is true。

 then when we minimize the L1 normal we're all feasible solutions， we're going to get back Xat。Aged。

好 right。So。Here's the intuition。So suppose so X hat， remember， by assumption。

 satisfies this linear system。 If W does also， then X hat and W differ。

By a vector in the kernel of the matrix A， they're both feasible solutions，Now， x is sparse， right。

 So all its L1 norm is concentrated on just K coordinates。On the other hand。

 anything in a kernel is spread out。I's L well norm is everywhere。

So if you look at X hat plus something from the kernel of this matrix。

 you can have very little cancellation because x has all of its norm on so few coordinates and something in the kernel has so much of its L1 norm and other coordinates。

 So when you add them together， they can't cancel much。 So you get a vector with bigger L1 norm。

That's basically what happens。So let me actually show you that that really works。So right， W。

As x hat plus y for y。In the kernel of8。So why is this defined as the difference between the two？

And by assumption of a being good， we know that y is one quarter square root of n over K。Spread out。

O。And， you know， I hope it was clear from the intuitive argument。 You know。

 we're going to use the fact that x has all of its stuff and just K coordinates。

 and then Y has to have most of its stuff in the other coordinates。

 So we're going to handle the two sets of coordinates separately。

So we're gonna let I be the support of x。 sorry， the support of x hat， I should say。

And then J are the other coordinates。 Okay， I compliment。So I has cardinality at most。K， right。

 because X had is K sparse。And then J is at the other， at least n minus k coordinates。All right。

 so then。So we're going to consider w is L1 norm。 We need to say it's big。 Okay。

 strictly bigger than x's。 Okay， so we're going to track its L1 norm separately for the coordinates and I where all of x's stuff is and then the other coordinates where X has nothing。

So let's write W。So we just break it into the two parts。

So theL1 norm is just additive so I can just sort of freely focus on two sets of coordinates separately。

嗯。Right right， so let me do it this way。So let me also expand。 So W's I'' written as x x hat plus y。

So。What is this？This can be simplified。对。Good， good， good。 Yep， So x hat is 0 everywhere here， right。

So， this equals。The Ja coordinates of Y。Okay。So let's think about how we can simplify this。

 All right。 And remember， we're trying to lower bound W's norm。 saying it's bigger than X。

 So we want to sort of extricate X from this interaction with Y over here。So note。

All right so we're just going to focus on this term for a second。ち。All right， so， and keep in mind。

 sort of the motivation here， right， So X has all its stuff in these coordinates And looking ahead because Y spread out。

 it can't have much stuff in these coordinates。 Okay， so keep that in mind。So。

How small could this possibly be？Well， sort of in the worst case， on each of these coordinates。

 X and Y have opposite signs。Okay， so you get cancellations。 I remember。

 L1 norm is the absolute value。 But when you add two vectors， if you have the -1 under1。

 it becomes 0。 So as far as the lower bound， that's sort of the worst thing could happen。 Okay。

 They have opposite times you get cancellation。 So that leads us to。

The total amount of stuff x has on these coordinates minus。

The total amount of stuff Y has on these coordinates。OkayAnd this is excuse me， yeah。Thank you。

Actually， we're going to use this for why I shouldn't do that。That's going to get really confusing。

Okay。So， in fact， it's also lower bounded by the opposite term。 I could take y minus x。

 That would be a second lower bound。 that lookss legitimate， but this is the only one I'll need。

 Okay， which makes sense because we're sort of thinking that like X is the one with all the stuff and these coordinates。

 And Y doesn't have much。O。So where does that leave us？This， of course， is also just the overall。

L1 Norma X。Because it only has stuff on eye anyways， right？

Sos the dust settles and we get the norm of W。Is lower bounded by。The norm of X hat。

Minus the norm of y。Just on the coordinates and eye。Plus， the overall norm of why。看。W。Why gay。

 price of gay。Yes， why sub J。 thank you。I I I and J minus I plus。Yes。No， that's the J， isn't it？Oh。

 I see the minus is the I， okay。Plus the J， let's do it this way。Mus the。Good。All right。Okay， so。

The next trick。So this we're pretty happy if we think about it。 So let's look ahead。

 So so we haven't used this one property we have about y being spread out。

 which means that if we sort of project onto any subset of the coordinateus。

 it's not gonna get much of the L1 norm。 Now， remember， I is sort of the small set。

 Okay I has size of those K with of that as being small Js of the rest。 So this。

 we're gonna have some ability to control okay。😊，So to the point that even let's just think of express this。

As the L1 norm of y minus。The O1 norm and just the coordinates of I。ちちち。ちち。个。

So now it's time to invoke the fact that y is well spread out。So using star。Over here。

So we have our I。 This is a most K because it's x was K sparse。 C。

 we've agreed is one fourth times root n over K。St of Ka。So this is the most half the1 norm of y。

 Okay， so we're left with something positive。And so that gives us that。

W's01 norm is at least that of X hat。So， that's proof。Any questions about that？All right。

Could you say what， why the I coordinates of X hat are equal to the。P X。Yeah。

 it's just just because it's sparse。So X hat is our ground truth case sparse vector equal to x hat Yeah。

 sorry about that。Y she wasn something better than one4。Yep。

 does that not affect like the probabilitybil。It does。 It does。 Yeah， I often make。

 often will give up a little bit on。Sort of the sharpness of the result。

 I think it'll make my handwriting a little more。Easy to read in lectures。

So having kind of a one over two plus epsilon everywhere didn't seem like a very good idea。So。

Other questions？