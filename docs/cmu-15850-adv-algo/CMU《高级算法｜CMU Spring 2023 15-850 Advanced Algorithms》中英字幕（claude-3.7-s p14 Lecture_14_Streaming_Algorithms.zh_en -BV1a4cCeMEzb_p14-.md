# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p14 Lecture_14_Streaming_Algorithms.zh_en -BV1a4cCeMEzb_p14-

Let's get started with this。嗯。Welcome back。Today we do we'll finish up a compressive sensing and the last last lecture。

 the proof you know it got a little detail oriented so I'll try to draw more pictures and hopefully it'll make much more sense。

嗯。So I'll finish compressive sensing and then we'll talk a little bit about streaming as we'll see how much time we have and we'll talk about streaming and you know we can continue later on as needed。

😊，But let me at least remind you of what we were doing in compress sensing， we wanted to。

What did we want to do， we wanted to figure out。Some X， some signal X。

And the way we wanted to figure out signal X was we hit it with sensing matrix a。😊。

And we would observe this deep。So this is observed。These are observed a is something we construct。😊。

And we want to figure out x and so we all we know is that x is parse， so we want to solve this。😊。

And then he said， well， you know， in general， solving this problem is hard。😊。

So we are going to construct a in a nice way so that this problem， this L1 minimization problem。😊。

Is actually going to give us a solution。To the Lve minimization part。

And this idea is called basis pursuit。😊，Now you might ask why L1 and we I promise that I'll give you some intuition and we never got around to it so this time maybe I'll give you the intuition right up front。

😊，UAnd then the way we were going to do this was we defined a notion called T epsilon restricted isometry property。

😊，isometry just means that for vectors x， I'm maintaining its distance pretty do well up to epsilon。

😊，And I'm not doing this for all vectors， I'm doing this only for three parts vectors。

 vectors whose L0 norm e mostlyity。😊，Okay。😊，Great。And the proof we will go in two parts。

 claim one says。3 S you know s is the sparssity we are interested in remember s is the sparssity3 s110 you know this this is these are just some numbers that work out I need a little more room than s so I'm saying if every vector with sparssity 3 S is maintained recently well up to constants。

😊，By a。Then using this a as the sensing matrix。😡，Is pretty good the L1 minimization will give you the L neurons。

Okay。😊，And then the second thing is how do you construct these RIP matrices and we say， well。

 if a the random m cross and matrix by random I mean all the entries。😊，啊。Gausians， let's say。

 or any of these sub Gaussian distributions。With sufficiently many roads。

Then it actually is RIP with high probability。哎。And we'll use the sort of JL proof kind of。

Almost in a black box。Okay， general idea clear， right？So maybe let me give you the intuition for why。

嗯。Y L1 is a good idea and in fact you know as as we sort of pointed out in Piazza actually this idea of L1 minimization is a much more general idea is much more sort of more common idea than just this one application。

😊，Suppose I want to find a matrix with low rank。With rank k。

So I want to minimize over the space of all rank k matrices， rank S matrices。

 it's an NP hard problem。But。I can try to instead of minimizing the the rank of the matrix。

 I can look at。Something called， I think it's called the nuclear norm。

It's the L1 norm of the singular values of the matrix。Instead of the L0 norm of the singular values。

 which is just the sparsity， which is just the rank。😊。

I'm looking at the L1 norm of the singular values。So very often I want a low rank matrix instead I'll try to find something which has low nuclear norm。

This seems to work pretty well。Yeah。G。So why in this particular setting do we expect？

That L1 minimization is a good idea So so here is the picture that helps me hopefully it will help you what do I want I want to solve a x equals B。

And I want to minimize the norm。That's， so I'm really trying to。

Minimize actually here's what I'll do， I'll minimize the knot so I'll say solve。Instead of this。

 I'm saying solve。Minimize。The L1 norm。Subject of Ax sequencequeing。This is what I'm actually by。

 that's what I meant。Okay。So what does it mean that I want to minimize the norm of the solution？😊。

You know， I want to find a solution on this。P。On this hyperplane a equals B。哎。

I want the solution of minimum norm。So what does this mean I should take the norm ball。

And I should scale it up。😊，Until this normball actually hits。Appoint in my solution space。

So for instance， if ax equals b， we're sitting out here。I would scale up this norm ball。

Until it actually hits a point on this space。And the smallest scaling by which until you know by which an intersection happens is exactly that minimization problem。

😊，Okay。Now， notice that。The zone ball of L1 is pointier along the coordinate directions。Okay。

So the solutions tend to hit more along the coordinate directions。Whereas out here。

 the solutions tend to hit at non coordinate direction。The left one is actually L1。

And the right one is L2 L0 would be something which would look something like this。😊。

It it's not even a sort of convex shape。So， I mean， you know， this is tend to L 0。 L 0 is just。😊，啊。

You know， along the quaex。哎。Good。So the point is that somehow this is some intuition for why。

L1 minimization behaves much better than L2 minimization， both in theory and in practice。😊，Sure。Yes。

And in fact， L infinity minimization would be even worse。

 somehow it's kind of pushing everything away from the coordinate access。😊。

So that's some some sort of some more intuition for y basis pursuit or L1 minimization is a good substitute for L0 minimization。

😊，But let me give you the formal proof， the formal proof had two claims。

And maybe instead of doing the algebra this time， I'll just draw as many pictures as I can。😊，Okay。

So my first claim is。That if a has this restricted isometry property。

 it maintains length of sparse vectors， then actually L。

One minimization will give you the right answer for L0。Yeah。So let x be the。呃。Be the solution。

The Spar solution that we are looking for。Actually。

 S x star be there power solution and x P the L1 minimizer。

And I'm worried about the case where these two are not the same。😊，So let's say x is equal to x star。

Less than。Okay。😊，Both of them satisfy ax equals B， so I know that a okay facts a delta is equal to 0。

😊，Okay。😊，If Delta were sparse itself， let's say 3 S sparse。😊。

Then we could infer the delta is equal to 0。喂。Restricted ismetry。

A maintains the length of all3 s spa vectors， so if delta were 3 s spa the only way to get0。😊。

Out here， Epsilon is tiny。Is to have X be。So Delta is not sparse。Nタ danceす。

Delta's got a lot of coordinates。😊，Okay， so let's do the following。Let's take Delta。

And lets let's break it up。Into little bits。Yeah。So。The first set of coordinates。

Maybe I'll make it smaller the first set of coordinates。Are those。Corresponding to the support on X。

And then I'm going to break it up into some more。Buckets out here， each of lengths two ways。

This is capital S that's a big O S and these are twoists。Next。Okay。😊，And I'll call these things B1，0。

 okay。Let's sort the coordinates。So I don't know what's happening in these first S coordinates because the first S coordinates correspond to X star there's no control I have the rest of these let's sort by their absolute value。

Of the extras of Delta， Delta。Okay， absolutely。Okay。And Im want to call these guy B1， B2 in。

What's happening。A is going to preserve the length of each of these vector。😊，So D sub。B1。

Is a vector which contains delta。Which agrees with deelta and B1 and0 is everywhere else。😊。

Delta B2 is the same agrees with B， you know， agrees with Delta out here and 0 that。😊。

These are spa vectors。Okay。So each of these。A of this is approximately。The length of the delta。

In the。Okay。😊，So somehow a is maintaining the length of each of these little suckers out there。😊，去。

I want to use this。To get a contradiction。啊，这的是个。So。It seems to show that。

Like L1 is better than L2 higher right， but this is L zero that we're trying exactly L0 was N hard and in fact。

 any LP or P less than one event hard。😊，So somehow L1 is at the sweet spot where it's both polynomally attractiveable。

And it's actually giving you something， you know。Gect。滚。Okayk。So back to the proof， I want to show。

That a delta is 0， I want to use this to infer the delta is0 really。😊，没。

This would be ideal because if deelta0， then Ive actually found X。So what am I saying？

I'm saying I don't know anything about Delta， Delta could be 00。

But let's break up delta into these little bits delta restricted to s， delta restricted to B 1。

 B 2 and so on and so forth。😊，For each of these， A is maintaining their lens pretty well。😊。

And for the rest of the proof， I'm going to imagine that a preserving their lens exactly。😊。

It's not important。Let's see what's up。So I'm going to look at。This vector。

Which is deelta restricted to S union B1。The first3S coordinates。And then all these other vectors。😊。

Delta B2， Delta B 3， and so on。What I'm going to show you。Is okay。So what do we know？I know that A。

On Delta。Its length is zero because a delta is 0。嗯。A delta。Its length is solid， its two length is0。

Now a delta is equal to。A deelta S Union B1。Plus， the sum。bos。啊。What am I doing。

They don't share coordinate， but I can't I'm sorry you the square right I could have。い squares。

You don't want square， I thought I had the proof down pat， but somehow clearly I'm screwing up again。

Lets let's go ahead and let's look at a Delta S union。Bジ。Let's make it up this way。just beJ。

Thank you。😊，Because a is an ismetry near ismetry。Im want to scratch out is from each of these guys。

Okay。😊，Because there is maintaining distances pretty well。

 this is where I'm using the restricted isometry property and the fact that each of these is parse。😊。

O。😊，Now I want to say， well， actually， you know what， this guy out would here。

Cannot cancel out thisote， this is what I want to show。This sum。Some over the lens of the Bjs。

Cannot cancel out。S union年被。And this would finish the proof that because then I would have something non zero here。

😊，Actually， I know what I want to go。Let's forget about the squares。I want to put a minus okay。

And I'm going to say。ですか？I'm using the triangular inequality on norms。On the two marks。

Something whose length is zero is greater than the length of this long guy I have drawn it suggestively the length of this long guy minus the length of all these little。

😊，该走我。My claim is these guys will not be able to sum up to this。贯注一行。

The only way in which these guys can cancel this one is if Delta is just zero。Yeah。Yeah。

And why is that going to be the case？And again， as I said， I'm going to just kind of draw pictures。

Trying to not not do a algebra。They're the first S coordinates。And then。I have these buckets。哎。Cim。

So， so Ill have two place， so something。Sub claim a。The length of。Delta restricted to S。

In the one norm。Is at least the length of delta restricted to S bar in the 10。

Somehow Im I'll find one norm easy， I mean， basically I have to use the fact that。😊，呃。

I was looking at the L1 minimized。So here is where I'm going to use it。Look x in the L1 normob。

Is less than equal to。啊。Next star。In the oh， so good。X star in the L1 norm is greater than equal to。

X in the L1 norm。Because I found x in the L model right？This is my solution to the L1 minimization。

This is what I wanted to find。This must have been better because I've looked at that。

So let me write that of x plus delta。X star plus delta in the L1。Okay， this。This is the minimizer。

 this is what I wanted to make。😊，对。Now this guy。Is actually equal to。X。

Star plus delta restricted to s in the L1 norm。Plus delta restricted to f bar in the L1。

The L1 norm just sum over cold。This is greater than equal to。😊，X do。

Dstricted to s in the L1 norm plus delta restricted to s in the L1 norm。Trend of inequality on。Norms。

Plus， Delta restricted to F bar in the L1。Just copying this off。I just use this the triangle quality。

Okay。X star in the L1 norm is equal to x star S in the L1 norm。😊。

Because that starts support with that。哦。Tranangle inequality。

 I better use the triangle inequality in the right direction。

Second time I've made that mistake today， please keep me honest。Okay。So what am I left？

I should move this to the left。Delta sub S。Is bigger than Del doesn as。More mask。

Delta has more mass here in L1 than。So really the picture should be these guys should be pretty high。

最近平。Okay。So I can somehow， because I knew that I was minimizing in L1。

 there's more mass here in L1 than there。😊，对。Let's do the rest of the thing。So I want to show。

That some。Over Dlta sub Bj。J bigger than equal to 2 in the2 norm。Is much， much smaller than it's。

 let's say， less than one。Over square root2， this is the number that will come out。

Of Dlta at S union D1 in the two months。So。I'm going to do a comparison argument that very often ones。

 you know it's a general little algorithmic idea， very cute。😊，Let's look at。B。ジ？😊，AndBJ -1 and BJ。

Let's look at these two guys。What can you tell me about？Delta B Jing。In the two norm， okay。

Let me say this height is little edge。Yes。So can you give me an upper bound on deelta bj。

 the two norm of this？you want to like have that much。哎操虑都真的是吧。Good。

 so if each of these coordinates is at most edge。😊，What is an upper bound on this？嗯。Good。

What is the what's the lower bound on this L1 mass？JBj minus1 L1n is greater than equal to。

Edge times。6。Their are two S coordinates， each of one of them has mass at least each。

So this is at most。B J minus1。One norm over square root units。哎呀。

The two norm here is at most the one norm here divided by square root of。Okay。😊，Good。

So I'm going to arrange this bottom line。レシ。Itll confusing me。I'm already a little confused。来。

So I could sum this。Overall， J。Which is not the first bucket。

The second bucket can relate to the first， the third can relate to the second and so so fourth。

 so I say this is J greater than equal to 2。😊，And this is Jay Great。Yeah。No， no， no。

 so it's not quite bad。Okay。This is the L1 normob。😡，The L1 norm sums over coordinates。So this is。

 can you give me an upper bound on this guy？I mean， there's the delta sitting there。This is。

I should write this cleanly right Delta is sub bj minus1 double double subscripts or one。

This is equal to Dta S bar。Dividing by square root。是。关老师。Nope， actually me equal。

Oh less than equal first doesn made the last bucket。😊，啊，温啊。What else should I use？

What do I know about the one norm of Delta S bar？In like most the one norm of deelta S。

We just proved this subclaim。Some more sort of trick here it these are like clever tricks。

 these are just you know fily little tricks that every so often you need to pull out of your bag。😊。

I find this acute proof， okay。😊，Okay， good。 Now I'm down to Delta S。 the one norm of this。

 I need to relate it to Delta S the。😊，Do not。Right。😊，啊。What's this？So what can you say about Delta S？

Do not。How much do we need to multiply by to make it bigger？S has only little S coordinates。

The L1 and L2 norms differ by only root s root little S little little S coordinateor。And we are done。

Some it's this vague。Like a bunch of little tricks used in some sense。

 you know it's almost like if you follow your sort of intuition。

 if you're smart like Terry Ta whatever these guys Dono her Tao Ruen Ver China。😊。

Good problem solvers right I mean， they know that like each of these things。

 they are maintaining the restricted ismetry property。😊，So they can apply it only on small vectors。

And then， you know， what can you do？I mean the fact that they use the restricted isometry property itself is very interesting。

 but if I told you the theorem how to prove it somehow these are very nice ideas break it up into little bit try to relate each other so this idea of charging one bucket to the previous bucket。

😊，Hopefully we'll see it in sort of a later part of the course this comes up every so often。😊，嗯。

In car markers and carps algorithm for bin packing。Nothing to do with this setting。

The same idea as used， you charge this to the previous bin。

And the lens rush mo start a shell algorithm for matchings。For generalized assignment。

 you use the same idea， charge a bin to the previous bin。てみます。

I'm waxing lyrical instead of getting on with the work。啊。So far so good， claim one， okay？

It's actually not very bad。Let me do claim two。Also a bunch of nice tricks。

 these are more classical surf tricks。😊，哎。So this was claim one。

I want to show claim too that if a is a random m cross and matrix。

 then it maintains all sparse vector lengths。😊，嗯。So the proof is going to be in a few parts。

So let me prove。Okay， so now claim two， right？So here's the general idea。I'm going to show。啊。That。

I'm going to first focus on some set S of coordinates， some subset S of coordinateex。

And show that a will maintain。All these。All vectors which are S。

 which are whose support is contained in here。😊，And then there'll be an n choose S。

 so I'm going to union bound over all these guys。So I'm just focusing on some set of S coordinates。

And looking at all vectors who support lies completely。Okay so from now on。

 I'm working only in this S dimensional space。So my space is now as dimensional。And then finally。

 I'll do a union bound over all possible choices of these West coordinates。Okay。

I want to show all vectors that maintained by okay。😊，So I'm going to show two steps。I want to pick。

Ne， I'm going to define this。Off the ball。Of the sphere。In these less coordinates。

 in these S dimensions。This is going to be a finite set and I'm going to show the length of all these vectors will be maintained。

😊，And then I'll show you if a X。Is approximately is in one plus minus delta times the length of x。

For all X in the map。Then。AX。Is in1 plus minus3 delta。Of x。For all X。In this field。

So what am I doing， I'm taking a。哦。A sphere。啊。So fear。In S dimensions， often written as S。

B dimensions。I don't want to confuse matters there's too many acids floating now。

I'm looking at a sphere indeed D dimensions。I want to argue。

That I'm going to pick some subset of points on the surface of this scale。I'll call this a Mac。

Ill say if suppose a maintains the length of all these vectors。😊，On the surface。

Then a maintains a lens of all points on the surface， infinitely many points。准。Let's play。And then。

 you know this this dimension will be chosen to be little less and I'll choose every possible subset of coordinates。

 do the argument， do a union bound out there and then we'll be cut。😊。

So the important thing is to go from an infinite set of points that I need to maintain to a finite set of points。

😊，Simple lady。So I want to maintain。All points。On this D dimensional。对。So let's define a net。So N。

Heres a subset of。The D dimensional sphere is a delta net。If two properties hold。For all X Y。

In the net。The distance between x and y and the distance is always the Euclidean distance for me。😊。

I a Delta is at least Dlta。Two points are not too close to each other。This is a packing property。

 not too many points can be packed in。And B for all x in。The ambient space。

There exists a Y in the net such that the distance from x to Y is at most length。

Everybody has a representative at distance at most Dlta format。😊，Euclidean。

All my distances will be okay。每个。😊，This is a definition of a Dlta network。😊。

What's an algorithm to find a Dltaag？Start with the empty set， pick a point。

If this current set is delta net， you're done。😊，Otherwise。

 there is a point which doesn't have a representative existence at most Dlta format。

Add that point to your set so as long as property B is not maintained。

 you can add a point to your set。Keep adding it until you can't add anymore。아그。点见。

If any of the Delta net。N has size at most， let's say4 over delta to the dimension。

Let's say Delta is at most one third just for。A net cannot have too larger size。ok。😊。

Let's prove this。So let's look at the next points。They are at least delta away from each other。

 right， oh yeah， of course。😊，Thank you。The net can't have two larger size。😊，How do you prove this。

 let's look at all these points。😊，And let's draw little balls around them。Of radius。Delta over2。

They are all disjoint。Because of the packing property。And moreover， they all lie inside。😊，Her boil。

我 ladies。1 plus delta over 2。This was the unit sphere。So if I expand it a little bit。

They all lie inside that ball。So。The volume。You know end times。

And n times the volume of a ball of radius。Delta over 2。Must be less than equal to。

The volume of a ball of radius 1 plus delta over2。All leave you guys must back in there。

But I know that in the dimensions。The volumes go as the radius to the dimension。

So this is just saying the size of n。Times delta over 2 to the D is less than equal to 1 plus delta over 2。

对得你。😔，And this is less than， let's say2 to the D because delta is small。😊，Yeah， you know。

 I don't want to use S because there are too many as。S and D are the same。We got。That's it， right。

 we approved it。So when I take this guy over that side， the size of an is at most four over delta。

Simple packing argument matter。You can't pack too many balls into a bigger ball。 I mean。

 it is into a。Fair enough。So。I want to maintain so what's my claim going to be no matter what a subset I choose。

Once I've chosen this as subset， there is a subspace。😊，There's a ball in there， there's a sphere。

I want to pick a net on that sphere。I want to maintain all the lengths for all those guys。

And that will infer that every point on this sphere will be maintained again。😊，Yeah。

 so you can show that you can always。😊，拜O。And have to。Good。

 so you know it'll be up to this constant thing out here。Because here's the thing。

 you can always say， look。😊，Pick a point， any point and now make a delta ball around there。😡。

All those points have been thrown away because， you know you won't pick any point in that ball。So。

 as long as n times delta to the day is smaller than the volume of the unit ball。

There must be a point in the unit ball， which is not covered。

So I think if you replace the four by one， I think you are。That's a lo part。

And I think people are people might be able to give better lower bonds and things like this。

 but in general， I think that's the best ticket。If you if you choose the points carefully。

 you might be able to do slightly better。Yeah。Other questions。

So this idea of packing covering the idea of Delta net is also very， very general。😊。

You work with metric spaces every so often you say， oh yeah， I'll take a Dlta max。😊。

you don't have to worry about what it later and it has two properties， packing covering。

How do you find it greedy algorithm？冇 보면为 simple。Okay good。And now comes the third thing。

 which is the sort of crucial thing。Suppose I maintain the lens of all the vectors in this net。

 so basically Im saying you know these are the points on the surface of the sphere and I'm maintaining the lens of all these guys。

😊，I want to infer from this that I am maintaining the length of all vectors on the surface。😊，诶。😊。

Cllean clear。So I can actually write this， suppose。AX。Two is in one plus minus ealon。呃， deelta。

X2 for all x and n。Then。A2 is in1 plus minus3 delta。Of thanks。2e for all x and S b minus1。Yeah。Book。

I want to show that a times x is well maintained。X， if it's in the net， we are done。

 so its not in the net。😊，So if it's not in the net。

 the covering property says there is some close body why。😊，不人でなく。

I want to reason about the length of。Why。And then the gap between them， what is the gap between them？

Theta。So showing the upper bound has a little trick to it， I want to show you that trick。😊。

So do you say suppose？Max stretch。Is M。Stretch by stretch， I mean， how much is it stress。

 we'll talk about shrinkage later on。And suppose it's achieved。😊，For the point。呃，X。

So let's say M is equal to。A times x。住吗。X， by the way， is on the surface of the sphere。

 so it's normal with  one， right？😊，This is the stretch of。X。This special X that I'm talking about。

Okay。What is X this time I'm going to make not make a mistake， I think。

I'm going to say this is the length of y。Minus the length of x minus y。は。Triangle inequality orns。

What do you know about the length of y？各喂。Okay， well， maybe I am making a mistake anyway。Yeah。

I'm not making a mistake。And its just going wrong。This is the usual thing。What's the length of why？😮。

One plus de。What's this？M times deelta。You know， I said， oh。

 I picked the point which achieved the maximum stretch。So on the point。So on the point， x minus y。

Divided by the norm of x minus y。I would have achieved less stretch or no more stretch than M。Right。

And our map is linear。It's the jail map， right？So the amount by which a is stretching x minus y is at most m times the length of x minus y。

 which is delta。We wants supply。X is the point I'm interested in， Y is the closest net point？

So I'm saying， well， you know， the length of Ax is at most the length of Ay plus the length of X Y。

Lth of Ay is stretched up to。1 plus Dlta。And x minus y is some other vector。

So its stretch can't be more than named。And its actual length was Delta。M and M。

 so let's just move m over so m times 1 minus delta a white 1 plus L。And this was the sneakiness。

Somehow I didn't know like how to bound this a priori。But I know it's no more than now。

Because M is the maximum stretch。So M is at most one plus delta over one minus delta。

And Dlta is small。Between friends。1 over 1 minus delta like  one plus delta。And one plus Delta。

Times one plus delta is like one plus3 delta。So far so good。

To show the other direction its the triangle inequality it's this time I'll have to actually use you know a times x。

😊，To known is at least。诶。Y2 norm minus。え。X minus y。电脑。But aY2 norm is at least one minus delta。Minus。

How big is this， we've already bounded the stretch。So this is at most one plus3 delta。但是。

Abound in the Str of everybody。So this is a length delta this can stretch it by most minus plus3 delta。

 we just proved。😊，So this is attmost this and now if you do a little algebra。

 this is important minus。😊，Model of the story， if you take a fine enough neck。

And you argue things about that and your map is linear， you can extend to the entire space。😊，Again。

 I click you'll use again and again。Yeah， so you'll see in just one minute。

So what I need to do is I need to for every possible set。😊。

So I want to say every x ofrs you know of sparsity S is maintained。😊，So I'll say， okay。

 x has parityitys。😊，Where can X's support lie in some state of cge？

There's N choose S way of choosing that set。Now， S must be some point。Okay。

 x must be some point in this subspacecing。Let's rescale it because it's all linear so I don't really need to worry about general axis。

 just unit length axis would be enough。所以。Now x lies on the surface of this sphere。

I can't do a union bound over all the points on the surface of this sphere。

 but I can do a union bound over the1 over delta4 over delta to the S many net points on the surface of this sphere。

😊，And on each of these， my jailL construction will succeed with probability x of minus or will fail with probability x of minus some constant。

Times deelta squared times。M， the number of rows of this matrix。

This was something we proved last week， I had kept it by nicely in a box， but we never got。对。

So I wanted to kill。All these terms using that。Delta is like a constant Dlta is like 1/ tenth for us。

So this is some constant to the S。This is， maybe let me just。Do some approximations over there。

 this is n over S to the S。Upper barn。E and over S to be S if youre doing pedantic about。

This is some constant， you know， this is 40 to the S。This is Delta was 11。OhIn my tail。

 I'm I need it。So I'm just going to kill。Okay。And now what do I need I need this is x of minus delta squared is also a constant。

 so let's not worry about that constant times m。M needs to kill all these constants with garbage。😡。

It's really N over S to the。M E to the M needs to kill this， take logs S log n over S。That's it。

 that's the。Several little moving parts， so you know it's good to see this once at least。😊，But。

Its just yeah。I can maintain any fixed vector so I can maintain a net so I can extend to the entire surface of this here。

I can choose every subject。I can maintain those。It's just a careful counting of all the vectors such that if you maintain those vectors。

 you can maintain all of all Spar vectors。😊，That's。see if you have end points no。

 no no sorry I have n dimensions end dimensions sorry and then like you have a fixed precision delta that you want one and then you like you know S of them are like。

In your solution， but you don't know which one so you just so I have a I have a vector x。

 I don't know where x lies No Ill say S。RightYou know， you know their okay， yes。

 dimensions that are used don't know which one which ones they are， but a union model order Okay。

 so your union battle at number dimensions。I mean， like can't you say so that like I have to， yeah。

 I have to， this should work for every possible less part。That's what I'm looking for。Next one。Yes。

That's not。No， but where does that end？M， oh， okay， so my my J matrix。

This whole thing is a random and cross and matrix。So if you chose M coordinates and then you go back to a lemma we approved last time or maybe even with last time。

 we said that the probability of a vector。Being stretched by more than one plus minus delta。

Both like e to the minus delta squared m， where m is the number of rows of the geometry。

It just like you're selling even more Gaussians， even more Gaussian。

 so your concentration can be better。不不是聊。Other questions。

The last time can you tell me like the motivation for this problem first so the motivation for this problem is I have S parts。

A vector in my mind。You are allowed to ask questions。

 but the questions you can ask are linear questions so you can give me a vector。😊。

I'll tell you what A do X is。So if I didn't get you the sparsity。

 you could ask me what's the first coordinate of A having what is E1 dota， what is E2 dota and so on。

😊，So you would ask N questions and you would get the dial。And now the question is， I ask you。

 I'll allow you to ask only。S times。Some long。没 questions，给你就上了开始。Okay。

 why do I care about this you might ask okay so people want to you know。

 so so one of the big motivations that's given the nature paper on this and stuff like this。

 people want to get something called a single pixel camera。😊，So I want to take an image。

 but I don't want a big old lens。All I'm doing is I'm taking this image and I'm taking its dot product。

 so the image is really a bunch of RGB values let's say。😊。

I'm taking its dot product with a bunch of different vectors。And you can do this using， you know。

 basically a single pixel learning。リハの technologyーっていことです。

And what you want to do is you want to use this to avoid some problems you have with standard lenses。

啊。黑色那豆黑色那这的。this one's not quite right for okay， this one is good。

 but it's there are other ways of doing this as well it's something called group testing。😊。

You have a population of N。You are the Samsung S of these。Having disease。

You want to figure out which ones have going have。喂。So what you can do is you can。

 you can take linear combinations of people， you know you're taking the blood。

 you can can combine the blood together and this gives you intensities。

 you know different intensities for different people。😊，Okay。Yeah。

 this so actually came up in the Second World War there were stuff like this， I mean。

 there are other solutions for this， I'm not saying this is the only solution to this。😊。

If you're interested in this， you know， if you're interested in playing with this， I put up a link。

 you know at some point I was very inspired， I wrote a Jupiter notebook， I said you know。

 this thing should work。😊，So lets see if it works so you know the first time in my lifem okay Python I want to learn Python I want to write a Jupyter notebook I wrote a Jupyter notebook and it's awesome it's like you take a vector you know add some some some S spikes to it。

😊，Even even had a little noise here in it， this is very noise， robust， by the way。😊，You know。

 I don't really need it to be exactly sparsity yes if most of your mass is sitting in S coordinates。

 this will find it。😊，So if other people have tiny amounts of the residual disease， you know。

 it's like， oh， there's a certain amount of tubeulrculosis floats around indeed。😊。

We all have maybe different amounts of fat but if you actually have the disease it's much higher。😊。

So if the population noise， if the signal to noise ratio is high， basically。😊。

Then you'll be able to play。So these are kind of people call these the like。

Sparse variants of the Shannon night with steel at what rate should you be sample？

So if you have a sparse signal， you can sample much better。

This is the kind of story that goes with us。And people in Dub， you know。

 so if people are here from DoubE， you might know more than I do。It's a like。那厉害。对。嗯。

I put out some links on the course I have a look at。It's very nice story。呃， good quarters。

Yeah thank you for asking me the question which allowed me to tell you the motivation otherwise I just told you the problem you know why are you interested in S part signal？

😊，买掉。个人。Other things。Okay， so。Let's take our two minute break right now and then I'll tell you about a couple of problems in streaming。

Cute little problems we don't have time for much it's Friday as well。That's always my excuse。

 it's sunny or it's rainy or。Yeah actually it turns out during COVID in COVID times at Cornell they were doing they had a very serious testing regimen on everybody had to test once maybe and people who some people had to test three times a week。

 something like I forget and really you know they can't do testing at this scale if they're individually testing everybody's data。

😊，So you group test， you combine together like 100 people and you test that。And if it comes up， no。

 you're like， hey， I'm done。None of these people have it。If yes。

 and at least one person has then you can start doing binary research。那上。O。😊，So。啊。

I mean this is a topic on which we at CMU we have a course that teaches you stuff about data streaming and sketching。

 David Woodr teaches it， so if youre interested in this sort of stuff you should take the course。

 but I'm going to give you a very quick overview of the area。😊。

It fits in very nicely with dimension reduction， though I don't know if we'll have time to actually get into that。

😊，Okay， so what's the model， So the model is essentially it's。

Low space computation so the whole idea is I have a long stream of data hence data streaming。

I don't have enough space to store all my data。So think of packets on the internet Im some poor little router。

 I don't have enough memory I have only。😊，Log， polylo amount of memory， let's say。

But as packets go along， I want to keep useful statistics about the packets。

packets you know I'm seeing a million packets a second。

 so I don't have enough time to store all this thing I want to do things quickly， low space。

 that's the main idea。😊，So for instance， I want to do packet counting。

 I just need to keep a counter every time I see a packet， I just in by one。😊，嗯。So if I see n packets。

 I need log n widths。Can I do better？Can I store if I'm seeing end packets？Can I get away？

With lesson and login bits。I'm trying to keep track of how many packets I've seen。

There's a famous algorithm for this and if there's a famous algorithm which is're not just keeping an account I mean it must not be just keeping an counter so the thing is that there are two things that are really useful in streaming one is approximation and the other is random image。

😊，So， you know， clearly if I want to keep exact counts of how many packets I've seen。

 I need log inbits， information theory。😊，But if I'm allowed a little bit of error。😊。

Suppose I want to say I want to keep a counter which is correct， so if let's say that。啊。

N at time T is the number or whatever。If I want to keep a counter。

 I don't even know how to write it best。But what I want to say is。

I'm going to keep a counter such that Xt， my counter at time T。Lies in one plus minus epsilon。of啲。

With high probability， let's say。So I have approximation and randomization。

This is the kind of guarantee maybe I want。I can do this with log log ands。

Maybe we'll talk about this later on。 the important thing to remember is that I'm pretty much keeping track of。

😊，The number of bits in the representation of three。So if I just wanted a factor of two。😡。

I could try to keep track of how many bits are there in my current。That takes log log。

N if it's N packets。一个。often they don't remember。I think it's Bo one over the website。对。

So I can start doing things smarter and maybe you know my counts are so large that actually I don't have。

Enough room to keep track of my count。 So log log in might be useful。 It's actually， it's useful in。

Other problems as well， I'll try to dig up a good problem where just knowing that there is the counter。

 So this is often called the flagjole。😊，And Martin。讲嘅。I'm sorry。

Maybe it's called hyperlolo counter I know is the flagier Martin counter。

 there's like 100 names for these things when I'm sure Wikipedia will tell us the right answer。嗯嗯。

But yeah let's not ask beinging right now， it's a little sketchy。Good， okay。But let let's say， well。

 you know， we have log amount of space and I want to solve some problems。😊，So for instance。

 if I want to keep track of so let's imagine my numbers。

 my my my data values that each time are numbers。😊，I want to keep track of there。Meim。That's easy。

 I can keep track of their running song。I can keep track of how many elements I've seen I can divide。

Not a problem。I want to keep track of the median。M trick care。

I'm seeing numbers and I want to keep track of the media。Okay。

So simple problems become hard in this model。This model used to be very fashionable back in the early days of computing when we used to have these tapes。

😊，And so you didn't want to read through the tape many times so you you try to minimize the amount of passes over the tape。

 hopefully one passes over the tape。And now， you know， as things the more things change。

 the more they remain the same nowadays very often I hear sort of in data centers。

 you don't want to store all the stuff。😊，You put it out in tape because most of the stuff we are generating。

 nobody is ever reading it again。So you just store the stuff。

 it's all the like all the copies of your old files， you never look at them， it's on tape somewhere。

😊，You might look at them， so you have to keep them around。Tips， cheap。

Easy to and they probably have voltage tape decks floating around iron。Anyways。

Let's get to sort of questions so here is。A question which has a sort of interesting answer。

 I'll call this majority。😊，So。Imagine that your A， so A， let's say， belongs to some finite a bit。Yes。

啊。Majority asks。Does there， so basically at each time。啊。If there exists at each time T。

 if there exists an element。啊。Which occurs。我ring。Maybe strictly bigger than t over two times。

M A1 through A。Then。Rturn。This element。哎。😊，El。done whatever you want。

So if I' am seeing elements and you know it's time 20 and I've seen a B 11 times， I should report B。

😊，But I have seen a B nine times 10 times I don't I can report whatever I feel like。

Strict majority basic。Is the problem clear？And I'm reading over this thing。

 I basically have very limited memory， I'm reading over at any point in time if you and at each point in time I'll output an element。

😊，I'll say so far I have seen a majority， you know， there is the majority element actually。

 I'll just say the majority element have drawn。😊，I have to be correct only if there were the majority element。

Prom here。系好。So it doesn't matter in this case。And so you can ask how much space am I allowed to keep？

😊，Yeah， what's that？Yeah， so in this case， I want to keep。😊，What I want to keep one counter。And one。

Alphabet symbol。I can do this， you know， usually we just say I'm allowed to keep two pieces of information。

but I'm even telling you I'll keep a counter and I'll keep one alphabet symbol in my I mean。

 I need to keep one alphabet symbol right there's a majority element I better keep it。😊，Yeah。😊。

So this is sort of another sort of cute problem。So heres heres the algorithm for this does somebody want somebody who's not seen the solution before want to propose an algorithm。

😊，If not， let me tell you another。宝放で。like a Facebook question or something like that or like you want to like you go through a stream that you want to out a random element a of the stream right it's sort of analogous to that it's a little analogous that that one is。

Good，You like have some other replacing that exactly likely exactly and you know you can even figure it out so so his question was I want to maintain an element in my hand I just keeping one element in my hand and maybe a counter of how many elements I've seen so far。

😊，And I want to make sure that the element in my hand after time step T is a uniformly random sample from the elements I've seen from 1 to T。

😊，And the idea is kind of simple， right？😊，When you come to the T step。

This new element you have to hold in your hand with property 1 over t， right？

Because it should be a uniformly random sample。So with probably 1 over t。

 whatever the element you had， chuck it and pick up the new element。😊，Otherwise。

 keep the old element。Simple proof induction。The probability that you have that you have element AI in your hand at time Ts like 1 over 1。

😊，This induct。Known as reservvoir sampling。Whatever yeah， so for this problem。

 it's not clear that looking at the output of the algorithm。

 even if we had it would be of any use at all， unless we're thinking of this as like a promise。

 it's kind of like a promise you should think of as like absolutely。Um。

There are variants of this where you can you know。So probability come in and maybe we'll get to that。

😊，But hell， you're worried about， you know， I I told you B， you're like。

 is B really a majority or are you giving me garbage？😊，Sadly， in order to give you promises。

 give you guarantees like that， I need a lot more space。So here， okay， good， but such as it is。

 this is you know， some solution。😊，Okay， so so here is the solution to this problem。U。

At each point in time， I am in one of some weird sound effects going on anyways at each point in time。

😊，I that I have。Okay， I'll have an element in my hand and a counter。😊，If the counter is0。

 I don't have an element。😊，嗯。I see the first element。😊，It's clearly the majority I've seen it once。😊。

That's how a start。If I see， okay， I have a， maybe I have an element in my hand and I have a counter。

 maybe the counter says five。😊，I see a new element， if it is the same as the one I have in my hand。

 I make it six。😊，Well， maybe from four to five。Okay。😊，好。

If I if I'm holding element and I have five in my hand and I see a different element。😊。

I'll make it for。I see a different element， three，2， one。0， I throw very。My claim is。That。

If I have an element in my hand， it must be the strict majority。So always it's a little weird。

 you know。😊，What's happening with this algorithm， but then I think of this algorithm as being。

 you know okay。So think of this algorithm as the following thing。😊。

Suppose there was a strict majority。Okay。That's the only case in which I need to give you some guarantee。

 otherwise， I can return whatever I want。So suppose they're the strict。

Really what's happening is suppose I hand element in my hand and I saw a different element。😊。

I'm saying one of the copies of， you know， I have five in my hand。

 it means I've seen at least five of these this element。I want to reduce it to four because。

 you know， I had five a's。😊，And I just saw B。听。😊，So I'll reduce it to four and say， oh。

 one of you is。😊，Pair up in that way。That just came in。So whenever。I see two distinct elements。

In some'm batting them up。You know， it's like you there are all these elements that are floating around。

😊，And whenever I see two distinct elementsments， I going to just pair them out。😊。

You guys go and have a drink and resolve your differences。Now。

 the thing is if there's a strict majority。😊，Not all the elements of the strict majority can be paired up at somebody else。

They must be in my hand。So this is， you know， I forget who are responsible for these。

 the United I think Mi and Greece。Hes calledIt's called the boy moral。

 the Michel Greeces another animal。That's a homework。So。Ok。Good。

So like interesting variances on this thing you can you can what if I wanted to maintain all elements which have occurred at least a t over k fraction of time？

😊，YouYou can do this using K counters and K alphabet symbols。Similar的 idea。

let me tell you about a slightly different algorithm。

 which is not like this one is very stylized it somehow is too slick for its own good I am not a。😊，啊。

I don't see how to sort of generalize this idea， but actually yeah yeah， but anyway。

 let me give you a different algorithm。😊，This is known as。Count name。Okay， what do I want to do？

I have。I have this alphabet， right？And I want， and let's say that the alphabet size is n always。

And I want to allow operations of the following form。Now all my extreme elements are of the form。

 you know， oh element A is being added to my system element A is being added to my system element A is being separatedtracted dropped from my system element B is being added。

 element C is being added， element B is being dropped etc。Elements are arriving and leaving。

What's happening？I am some kind of sort computer thing。

I'm looking at how many active IP connections are going through there。

How many active network connections are going through network connections are being formed to this particular host。

 network connections are being dropped from this particular host。

How many active connections do I have？Question one might ask correctly。Oh， okay。At any point in time。

There are inserts and deletes going on at every point in time， either a thing is being added。

 I thing is being deleted or I have a query。😊，And the query looks like so insert， delete。Or query。

And the query says。How many copies of this element are there？Which are still active。

So it's the same kind of thing as before。😊，Where elements you know earlier elements were just arriving now elements are arriving and departing how many copies of this element so at this point if I got a query for a I should answer one for B。

 I should answer0 for c I should answer one and so on。😊，Yeah。So if I get a query。

 I should give an answer and the answer should be pretty good。😊，Of course， there will be errors。

 there' will be probability of you know， there will be some error bars that you give。😊。

But how would I maintain this？啊。So let me give you one solution。

It's all picture now now we can't prove anything I'm going to go a couple minutes over as usual you know me by now。

I can keep a table。The table is a size N。Every time I see an element。

 I increment the counter every time I。😊，They element leave they dec the count。

So there an there is an entry for a， there' is an entry for B， there's an entry for C。

 I see and insert one insert to delete one etc， I'm just keeping count this is like the most bogus solution in the whole part。

😊，Space N。Do we ever get deletes on elements that， let's say we don't get deletes。

 but this can handle actually， let's say we don't get deletes。😊，You can。Okay。Space and， right？

Here's what we'll do instead， I don't like space N it too much。😊，So heres我怎。

I'm going to create a smaller table of size M。And what I'm going to do。

If I'm going to use a hash function。So a has function with maps。My alpha。Into。M entry， M capital。哎。😊。

What does this mean， you know， each of these is the color， this is pink。😡，So each of these elements。

 you， some of these will be mapped。There is a guy who's orange。And maybe this is orange。

 maybe this is orange， maybe this is orange， whatever。The count I maintain。Is。

All these guys were mapped pink。Are going to get summed up。

 their counts are going to get summed up and put here。All the guys were orange。

 their counts are going to get summed up and put here。Okay。😊，So whenever you see。Element。E increment。

Location edge of food。Whenever you see element or you know ea plus when you see ea minus。

 then of course you decrement ettrophy。😊，Whenever you see query for E。😊，You return the value of that。

Okay。😊，It's a solution。各。Answer。Query of E is always going to be an upper bound， right？😊，Yes，好。

How many copies of this element are still in the system？😊，So I'll call this table。え。

So if query comes。So here you increment a of H of E。And you decrement a of H of E。

 and when a query comes you return a of H of。Just return the table according to the color。

So if we query a D right now， move from one， and that would be an inb overest absolutely。Absolutely。

 because D has nothing in it， but we have just put in a file。It's an overest。Now we could ask。

 what is the expected？Over estimate。For a particular element。This is equal to the sum over all f。

 which is not equal to e of the probability of。H of F is equal to h of e times the count。哦，看。

Let's look at every other element。😊，There' is some probability that it passeses to the same place as E times its count。

 right？😊，Okay。Oh， this is the over。😊，So Ive already release more okay。No。

If my hash function was pair wise independent， you know。

 I realized we didn't talk about pairwise independence， but you guys can figure out what pairwise。

So the probability that h of f falls in the same place as h of E is really 1 over m the size of this table。

😊，It's uniform paralyzing。What's the total count of f， it's the number of elements in the system。

In the system currently。O。😊，Now if M was something like one over epsilon。

This would be epsilon times the number currently in the system。So claim the expected overestimate。

I at most epsilon times the number currently in the system。

this assumes that the function edge is pairwise independent。

 which you know maybe I should define later on， but basically edge is being chosen randomly from a family。

😊，嗯。So what this means is that the total error is epsilon times the number currently in the system。😊。

And if you are looking at people who are you know heavy heaters。😊，Who are supposed to be， let's say。

 you know 10% of the time in the system。Then you can make epsilon 0。01，1% of the time。

So the  error can be small， you can make the  error smaller that way。By the way。

 this was only for the expected overest。😊，But by repeating this process many times and taking the min of those over estimates。

 you can get a much better guarantee。😊，And maybe you know， I will post on Piaz。那是为了。😔，It's not。

Anyways， this idea of just you know coloring and so bucketing very useful so this is appears in count men this is also the main idea and something called a bloom filter。

😊，Some of you might have seen bloom filters before。Same idea。

And if you haven't seen bloom filter before， if you use Chrome。😊。

Chrome uses bloom filters I poked around at some point to keep track of which sites are you know potentially spammy or whatever dangerous。

's it's a quick way of doing sort of retrieval basically you should think of this as trying to figure out which ones are non zero。

😊，对。Yes。So data streaming， huge area。😊，And you know I meant to say more。

 but you know I got distracted with compressor sensing。

 so maybe this this time in the course we'll stick with that there are some notes you can have a look if you're interesting。

And but maybe， you know， it's time to get back to。Business other business as well so next time I'll talk about the experts algorithm if you haven't seen it before。

 this is truly one of my favorite algorithms as opposed to all these which were also my fitness。😊。

But so it's the experts algorithm and we'll be getting into online learning。

 a little bit of continuous optimization， and then we'll go from there。😊，cool， thanks guys。

 have a good weekend。