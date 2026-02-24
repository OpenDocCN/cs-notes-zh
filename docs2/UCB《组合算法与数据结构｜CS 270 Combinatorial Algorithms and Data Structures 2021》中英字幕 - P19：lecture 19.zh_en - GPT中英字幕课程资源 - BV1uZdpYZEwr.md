# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P19：lecture 19.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/52f932fb79b1de2a13e652bd92fe84a2_0.png)

Welcome， everyone。 Good to see all today。 well talk about。Similarative programming。

Today is lecture 19。做。嗯。So what is semi different programming you could say that it's。

One way to say it is it's a generalization of linear programming。

So I'm sure all of you have seen linear programming in the in earlier algorithms classes。

 so what is linear programming it gives you。It's not just a single algorithm it's a it's a language in which you can express a problem and then you can you can use it to solve a problem in many cases or approximately solve the problem and semi different programming is just like that it's a it's a very expressive and powerful。

Optimization， primitive。Okay so it is essentially a convex optimization perimeter so at the end of the day。

 if you look deep into semi def programming or an algorithm based on semi different programming。

 of course it is going to be doing some form of gradient descent or mirror descent or something at the end of it so it is at the end of the day really a convex optimization procedure but just like linear programming is more powerful than did in decent semi defite programming gives you a very expressive and powerful language to express your problem so it really you know this section that we'll talk about in the this lecture and maybe a couple more is you know one way to think of it is。

It it's like a highlel programming language like you know this versus gradient and decentcent is like Python versus assembly right so you have the same sort of tradeoffs of course it's a very high level and powerful programming language or way to design algorithms so it's a sort of gives you a first cut if you want to know if some problem is solvable or probably very hard to solve you would want to first try out semi different programming so it because it's a very powerful tool on the other hand the algorithms that we construct using it。

Are not necessarily going to be very efficient。So at first cut。

 I guess for many of the problems that we。Some different programming and its variants give you the first polynom time algorithm at all and then of course you know if the problem is interesting enough you'd hope that that algorithm can be simplified further and further to make it really efficient。

Actually， useful。But you know at first it'll be a somewhat a fairly distant a poly normalmal time algorithm。

 which is fine for a lot of purposes but you know itll be much easier to design this。So。

So and I had to say one more comment about it well。

So it I say it's a generalization of linear programming in what sense is it a generalization of linear programming essentially。

If you take clean programming。And。要。ad定。Eigenvalue computations or eigenvector or eigenvalue computations。

Basically the power method。These two together。Sort of give you amer program。 So in some sense。

 it's a。Similarary programming combine the power of。

 I guess you have linear programming and convex optimization and spectral techniques。

LikeT from spectrograph theory here。Just PCA and things like that， I baked into it。Okay， so。

So let's just see what the semi different program is We already sort of saw it in our earlier homework。

 so as general semi different program is。嗯。嗯。Its basically is you could say it's a linear program。我文。

Positive semi defite matrices。Okay， that's what it is so what you have。

 so basically you have you always have a matrix of variables。

So let's say this' is an end by n matrix of variables。

And what you constrain this matrix of variables to be is that you constrain this matrix of variables to be PSD。

Okay， and just to recall a PSD， a matrix is PSD， we had bunch of characterizations of this。

 we did this I guess a while ago。A matrix。M is PSD。It actually let me write on a separate page。是。

If and don't leave， I'm just recalling what we did， I guess in the first homework。

 I guess if from leave， okay， firstly， all eigenvalues。A non negative。

And then second these are all equivalent conditions。It is the same as。

All eigenvalues of m are non negative the other thing is of course x transpose mx is greater and equal to0 for all x in real vectors M admits such as key factorization m equal to Vv transpose。

嗯。For some week。For some end by N matrix week。And then what else？He could say this。

X transpo a x is actually equal to a sum of a bunch of square matrix squares。

 So this as a polynomial， this is equal to sum of。はい。三么姐 c i j x j好 square。Okay， these are different。

 equivalent ways of saying that a matrix is PSD is all of these。That exists。Phon is there exists C。

 I J。such that。Exentence was I mix a sum squared。Okay。

 so it's and the how should we think of the set of all PSD matrices。

 they form what's called a convex code。其数。对。Se of matriceses that MPSD， they form a convex cone。

And in what space， well， it's a convex code and r to the n squared。I think these are essentially。

 I guess the way， let's say it's。We are always going to be talking about symmetric matrices。

 so it's actually essentially it's r to the n squared， but MiJs should be always equal to MJI。

 so you could say it's n plus n choose2。Okay谢。It's a cone there and you know。

 I have no way to visualize this high dimensional space， but I do。In my mind， I think of a poem。Okay。

 and。Which is fine for most practical purposes for many cases， it's really like a cone。

 What's the properties of a cone cone of vectors， if I take any vector。

 I scale it it's I'm inside the cone。Okay， and。If I take two vectors in the cone and I take the line joining them。

 the entire line is inside the cone， It's a convex set， which looks like a cone。

As in you can scale a vector， if m is in the cone， I'll see times n。

Is also the cone for C greater than zero。And no it's really a cone in r to the n squared or r to the n plus N2 just depends on how you。

是。インネックです。Okay， so this is a set and what a semi different program lets you do is it lets you add a constraint that you have n squared variables arranged as a matrix and these variables。

For a PSD matrix， meaning x is restricted to be inside this cone。

And then you can add any additional constraint you want， you're allowed to add linear constraints。

On the matrix， so I'm going to write it this way。So。Okay it's a linear constraint on the variables。

 some are all I the end squared variables， so it's a linear constrain on these n squared variables。

 and you know， of course I can always write。The notation for this is a。Oh。X。W a。

Is the you write the coefficients AI JL as a matrix， you get A。It's just a notation。

So this notation that we have here。嗯。Is an inner product on matrices。So the inner product。

 if I give you two matrices， AB。The inner product on them is summation AI J， BI J。

Just treat them as vectors and take the product， but if you I mean if you know it。

 you can also write it as trace of a times speed。嗯。But basically for now。

 you just think of it as actually just in a product。

 so you can write our linear constraints on these variables。Okay， and then of course you can write。

 so let's say for L equal to one through M， we have M constraints。And finally。

 you can have an objective function， so objective function again for simplicity。

 let's say it's a linear objective function。嗯。Let's say minimize。嗯。Okay， so。Does that make sense？

And of course， again， you can do minimize or maximize for a linear function it's fine in general you would want to minimize a convex function or maximize a concave function。

On the X。Okay。So that's what is semideinite program is。インジェル。It's a linear program over。PSD matrices。

Okay。Okay， so that's good。Okay， so what do we do next。嗯。

Let's reinterpret another way to interpret this thing is to think of it。In terms of vectors。Okay， so。

I should let me add to my list of things for a PSD matrix。嗯。So。

Here's another thing that screw about a PhD matrix， which is the same as。

 I guess condition number three。Is that。The entries of the matrix are actually can be written as inner products between vectors。

 so there exists vectors v1 through VN。In or to the end。Such that。m车。

Is equal to the inner product between V and Vi。Okay。

 I'm saying that a matrix is PD is exactly the same as saying that there exist vectors such that the MIj is equal the in the product。

Okay， so what that means is you know you can take the program that you can solve here。This program。

And you can also interpret it。Purely in terms of vectors。 So you can say I'm not look construct。

 I'm not looking for X Js， which are matrix， but I'm actually looking for。Vectctorors v1 through VN。

In N dimensions， I guess。Reectctorors we through Vn in n dimensions such that。You know。

 all the constraints and objective function， you can you need to write in terms of the inner products between the vectors。

 so you are minimizing I guess summation CIJ。VI in a product VJ。Okay， and what else。嗯。Subject to。

Summation AI JL。A l。VI in a product we。Is smaller than BL。嗯。ok。So in some sense。

You can say we're solving for vectors， it's a vector program or you can solving for vectors。

 but you have to be careful the only you're never allowed to add a constraint on an entry of the vector I cannot say the fifth entry of VI or the fifth coordinate of VI is at least four or something。

Okay， the only thing you're allowed to do in the vector world is you're only allowed to write down this program as a linear program on the inner products between the vectors。

 the only things you have access to have。I guess rotationally invariant quantities which are thener products between the vectors。

 you don't have access to the entries of the vectors when you write the program。Okay。

 so this is good。All right， so let's see an example。

 I guess let's look at the sort of the most classic example。So this is a maximum cut problem。So here。

 what is the problem you are given a graph G。Equal to V E， you'd given a graph。And your goal。

Is to find。A cut。 A cut is just a partition。Of the word disease。That maximizes。

The number of crossing edges。Maximizes the edges crossing。Okay。

 so this is an NP complete problem and there's a very natural is a trivial half approximation for this problem。

 just pick a random cut right so a random cut。是。In expectation gets you at least half of the maximum cut of the graph。

It cuts at least as many ages as the best possible。

 so it's a half approximation is a naive algorithm， just pick a random cut。And。

For a long time actually this was the best known and if you try several linear programming relaxations for this problem。

 it doesn't budge， you don't get a approximation factor better than half in fact。

Up to close to sub exponential size linear programs， we know don't get you better than a half。

 so really， really large linear programs also don't get you better than a half。嗯。And。

In I guess in the early 90s， 91 or 92， the very first。

Semi defite programming based algorithm for this beating half was designed and it's called the Gomans Williamson algorithm。

It's quite influential because it's start of。Really。诶。

Really propelled semi different programming in approximation algorithms quite a bit。

 though the really the earliest applications of semi different programming to comm optimization was from I guess the 80s so maybe even the late 70s。

Its's called the lowest theta function， but there wasn't much after that and after this result in the early 90s。

 things really kicked off。So basically， okay， so just to summarize for this max cut problem。

Like we know for now now that I guess here's a theorem， I guess， certain sub， I guess Lear theorem。

 sub exponential size LPs。Don't do any better。Don't do any better。Then this random trivial algorithm。

So this Goldman Williamsson algorithm for based on semiative programming really beat tough。Okay。

 so let's see what the algorithm is。Okay， so we'll derive this logo and s algorithm。 So the idea is。

呃。As follows。So， you know， let's think of this thing in terms of the vectors。ok。😊。

In terms of this vector program， let's think of semi different programming in terms of vectors okay。

So。5。What do we want to do？We want to。Take the graph。And compute vectors， we1 through VN。Okay。

 and these v went through Vn， these vectors。Should somehow denote the cut， right。

 they should denote the cut。The cut that we care about。Okay， so let's you know。

 let's have an intended solution in mind， so here's the intended solution。So for normalization。

 let's say。Or we want all the vectors to be length one。Okay， and let's say， you know。

 really what we can hope is that。We find vectors which look like this。So let's say if S complement。

SS bar is the best cut is the maximum cut。Is the optimum max card。连。

What you'd hope is that you'd find a vector configuration that looks like。You know， VI。

Like all the we， all the。All the vertic is in S。Get map to。The vector。

 which is like the plus one vector。Take the plus one vector。

And then all the vertices in S complement get mapped to the minus1 vector。Okay。

 so this should be the intended solution like ideally we'd want VI to be equal to plus1 if I is in S and minus1 if I is not in S。

Okay， that's three。 And then okay， so if suppose this was the thing。

 then you suppose this in the solution， what would。The number of edges cut would be。

The number of edges cut is says bar。Would be。Okay， for every edge， I。

If I look at the distance between。VI minus V J。Whole square。

If you look at the distance between VMSVj squared。This indicates whether the edge is cut or not。

 because if the。Like this quantity， VMS Vja holds squared is。If it's 1 and minus1。

 then it's two squared， it's four， it's four if the edge is cut and it's zero if the edge is not cut。

It4 if。You know。Like I is in S， J is in S complement。Or vice versa， zero if IJ are in the same side。

If they're in different sides， the length is2 and so the two squared is four。

 and if they're in the same side， the length is 0。O。So you know， if I want the number of edges cut。

 I'm just going to divide it by four。Take I look at this quantity。嗯。

The sum over IJ E VI minus Vj whole squared that tells me the number of edges cut。Okay。

 so now you know， we have a semi different program that we can write。

What is it well it's maximize the number of edges cut， which is one over four sum over Ij in E。

VI minus Vj whole squared。Okay， and what other constraint we want Vs to be plus or minus1。

 we can't really enforce the the vector to be plus or minus one because。As I said。

 you can't access the coordinates of these vectors。

 but you can actually say the length of the vector V squared is one。Okay。And again。

The reason I'm able to use VI minus Vj wholequad or the Nomquad is because if I have Nomquad is just the inner product between VI and VI。

And you know， similarly。VI minus Bj whole squared is VI VI。That you can expand out it's really。

V I minus Liz。Inapp with V minus Vi。So you can expand our so basically this is a valid semi different program。

It's a linear。Linear objective in VI in products。 VI is an in product VJ， and then it's a linear。

Constraints。In Lena products。Okay， so it's linear objective。

 linear constraints on the inner products between vectors， so you know it's a valid semi program。

And you can solve it。To an accuracy Eilon in time， which is poly and polylog1 of Epil。

So you can solve it approximately。Okay， so。That's good。Any questions so far？

So this is an optimization problem now we call this the Gomans Williamson GW SDDP relaxation。

For Mexico。It's a semi different program， semi which is a relaxation for Mexico， so in what sense。

It's a relaxation， usually what it means is if you give me any cut。

Any actual solution to the original problem So any cut or alternately any plus minus1。

Assignment to vertic。At any integral solution for the original problem。There exists， I mean。

 it corresponds to it is also a solution。To the SDP。It's a feasible solution too。レ地品。Okay。

 so I don't know if we did cover relaxations in 170 we do cover it sometimes but basically。嗯。そ。

I mean， I guess the if you haven't seen it， the picture that you want to keep in mind。

 I guess which is a basic picture is。In these problems， okay， have a combinator optimization problem。

Okay， you have a commal optimization problem which is。Like Mexico， right？Let's say max cut。

And the space of all solutions is a discrete set。It's a discrete set。

 in fact it is really in our case， it is just plus minus one to the n。

 all vectors which are plus or minus one。This。Like it's a plus minus1 assignment to every word。

 it is the ver is of the graph。Okay， so geometrically you have this is your it's a discrete set of。あ。

Soolutions。And。So you can't really use convex optimization on a discrete set of solutions。

So what do you do？You try to convexify it， okay。And so you sort of want to look at。诶。Convicts。

Like usually you would say some sort of a convex hull。Of your space of solutions， let me call it S。

Space of solutions says convex Hull of is like is a convex Hu of a set of points is。

The smallest convex set containing the points。Okay， so it's the smallest con。You would want to， okay。

 we could construct the convex Hull and optimize of the convex Hull。And。That would be great， but。

Typically the set。The convex hull of these discrete sets for NP complete problems are exponentially complex as in you cannot optimize over these these are as if you try to write as a linear program if you need exponentially many constraints this convex set is exponentially complex so what you end up doing is you end up optimizing over a different set convex set and we're to。

Just。So this is a different convex set。四。And what is the property of this。

 Lc contains this convex  h。office。And it contains it's a relaxation。

It's a relaxation of your original problem。But you can optimize overseassea。So you optimize oversee。

Okay， and when you optimize over C， your optimize your linear program or semi different program or something like that will give you some point in C。

At what you'll end up with is some point in C。Okay。

 this is what you end up when you solve the semi program linear program， end up at some point in C。

And。It will not be one of the original integer points。

And then the strategy is to round this some point in C to an integer point。I the ideas too。

Sol the relaxation。And then round the solution。To the relaxation。

Because this is like a very general framework and I mean there's a。是。It's a。嗯。

There are big books full of algorithms which do this。

 but of course in every problem the relaxation is important and finding the the relaxation and rounding both are interesting Okay and so what we have over here is a relaxation。

So why， because we had any plus minus1 solution will give you a vector solution。

Because V is equal to plus1 if I is in S and minus1 if I is not in S。

This gives you a vector solution， so any plus minus solution gives you a vector solution。

 but a general vector when you solve the SDP you will not get a plus minus1 solution。

 what you'll end up getting is。Some vectors， you get some vectors， V1 through VN。

In n dimensional space for these vertices。Okay， so。Okay， is the one key observation which。

Is important。Is that the。Objective value。The maximum。Like the optimum。Of the Gos Williamson SDP。

On a graph gene。Is at least。The objective value of the maximum cut。On the graph G。For every graft。

So basically when you solve SDP， you will get back some vectors and the objective value for the vectors。

 meaning the this quantity here。Thebit squared distance is going to be only higher than the max cut value。

 This is just because any any max cut solution is also。Any actual cut is also we。Solution to G。Al。

 since you're maximizing over a bigger convex set， your value will be higher than if you maximized over true solutions since your SDP is allowed to output false solutions or pseudo solutions。

 its value will be only higher than if it were forced to truly output true solutions。跟一出嚟。

The optimum of the GWSDP is an upper bound on the max square value。

So I think there's a confusion so the assignments are plus one but the VIs are vectors right so can you really explain that bit yeah yeah so actually when VI is a right so here when I say VI is a plus one vector what I mean is okay let's say we're in n dimensions pick one direction so let's make plus one times some direction e1。

Like and minus1 times e1。So so basically the geometrically the embedding that puts s on one side on one end of a vector and s complement on the other end of unit vector。

 like minus v and that's the embedding vector talking yeah yeah I guess when I say plus one for the vector V we mean plus EI or plus some fix sum unit vector and。

Okay， so now we are okay， we solve the SDP， we got these vectors。We need to produce the cut。Okay。

 so here is where。What happened？嗯。是。So after we solve SDP。是。GWSDP on a graph G， we get back vectors。

 right V1 through VN。Which are unit vectors。Okay， unit vector and。嗯。

And really what they maximize is this the average squared distance。Okay， total square distance。

 but you know， I can also。I we call this total square distance。

So in some it's very very intuitive what it is trying to do the SDP is trying to put the vectors on the sphere so that you maximize the total square distance between them so it's trying to push them as far away as possible。

 right all the edges as far away as possible， Ij and edge。And we'd be happy if it really did this。

If it really pushed all the some set of points here and another set of points here。

 that would be great， but。There are other configurations which give you more objective value。

 so it'll give you a different configuration。Okay， so now our goal is to recover our actual cut。

Okay so， here's the。Ebedding。Of the graph。嗯。All right， so you have a graph。

And this is the unit sphere in n dimensions。In art game。

And so to recover the cut is a very simple and very elegant algorithm here。

Which also turns out to be optimal for this。 What is the simple elegant algorithm just cut。

The unit sphere。But I half space。Okay pick a plane going through the origin。Pick a random plane。

 which is say random hosp space。Random hot space， So I guess。Hyperplane， random hyperplane。

 you could say， yeah， so。You pick a random hyperplane going through the origin。

And it doesn't look like a hyperplane， but you can see it picture so and whatever vertex falls on one side。

 you call it as and whatever vertex falls on the other side， you call it as complement。

It's geometrically just cut it and whichever vertex falls on this side。

So how do you achieve it and algorithmically， you know。

 you just pick the normal vector randomly so you can， for instance， pick。A randomand normal vector。

Random normal vector G。Okay， and you're asking which words is fall on this side of the cut so and which on other side you say。

Xi is equal to。1 plus one if。嗯。G in a product VI is greater than zero。

 it's on one side and minus one otherwise。It's a sort of a rounding。

 you round everything on one side to plus one3 minus one。Okay， and。Ordnately， I mean。

 I belongs to Sif。G dotV is。This is a same I belongs to S and this I belongs to S complement。

OkayThat's the only。It's very simple。Okay， so let's analyze how well this round does。哎。Okay，Actually。

 we can analyze how well the round does on an edge by edge basis。So let's look at a particular edge。

fiixer。Analysis， so you let's look at a particular IJ。Okay， and then for this edge， you have。

Two unit vectors， VI and VJ。VJ and VI。Okay， and。嗯。Okay。

 so what is the probability that VI and VGS separated？

We want to know what is the plot that INJ is separated or A Ij is cut。

What is the probability that the JJ is cut？嗯。So。Right so we are picking this hyperplane in。

In a sort of in n dimensional space， V I and VJ are also in n dimensional space， unit vectors。

 This whole thing is happening in unit and dimensional space。 So at first。

 this seems a little daunting。 But really， the important fact about n dimensional space is that。

If you're only interested in， let's say， three vectors in n dimensional space。

The geometry looks just like three dimensional space。

RightSo it doesn't matter what dimensional space your actual vectors live in if you're talking about three vectors in n dimensional space。

 if you look at the subspace span by those three vectors。

 that subspace is isometrically or isomorphic completely to three dimensional space so in order to answer this question of what's the probability that this hyperplane you know cuts this it's enough to just look at the span of VI and VJ like look at the plane in the of V and Vj and just you know answer the question there and you'll get the same answer。

So。So basically， imagine look at the plane spanned by V and VJ。And。So， there。Good this is a。

Plain of your V music。Con B and Vi plane containing V and Vi。

 And then your hyperplane is going to cut this in some way， right， So you。Let's say。

 you know you have a。I'm just going to。Extend this line。Okay， so let's say this is the angle theta。

Yeah， so。VI and which I get separated only if the hyperplane ends up going between them。

Right like this。So the green。Hyperplane separates ING。嘅。On the other hand。

 if the hyperplane goes doesn't go between them， then it doesn't。

 right like if it is this yellow hyperplane。It doesn't separate ING。Okay。

 so the probability that INJ gets separated is exactly equal。To the probability that。This lead。

This line goes between I and J。Which is。Theta divided by。闭。Which is the angle between I andG。是的。

It's the angle between I andJ。Divided by pi the 180 degrees。so it's just。Daタ by by。

This is the probability that you separate them。And you know you can write down what the angle between I andJ is in terms of the inner products right we already have access to these inner products so the angle between INJ is our cosine。

嗯。Of the inner product between VI and Vijet。Do were bye bye。

This so the pro R J cut is exactly equal to this。Allright。

 so the expected number of edges cut by my by the。By the algorithm。

 by the cut output by the algorithm， expected number of edges cut is you know， it's。It's basically。

Expectation of the sum over I J。In E of the indicator that Ija is cut。Okay。

 this is actually sum over the probability that IJ is cut。Okay， so it's really equal to。

Some or I edges。Pros good some other。Ide of the edges。Of this quantity are cosine。你系你知。バイぱい。是。Okay。

 so the expected number of phases cut is this。All right， so that's good now。嗯。

What do you want to compare this with？Well， we want to compare this with the best cut in the graph。

 and that's what when approximation ratio would be。

 you want to understand how does it compare to the best possible cut。Okay， so ideally。

 we would want to say。嗯。What is the the expected number， so let me just do here。

What we want to look at is。How does this compare to the best cut？The max cary。

And we'll be hopefully that， you know， be able to say， oh， it's at least some alpha times that。

But you know， we have no real access to maxcoto G。Because you know it's a quantity that's exponentially hard to compute on。

 so we don't have access to the value of max cutter， there's no simple expression to write that。

But we have an upper bound on it。Okay， so。What we'll do is we'll show that。

The expected number of edges cut by our algorithm。Is at least。

Some constant alpha times the SDP valued。The my optimum SDP value for this graph。

And we already saw that SDP value is at least the max cut right it's a relaxation SDP value is at least the max cut。

 so therefore this is at least alpha far times the max cut of chip。Okay， this。

Inequality is because of relaxation。The fact that we talk relaxation。

 this inequality is because we need to prove it to prove。To prove this incorrect， the first one。

And if we do this， then we know that our algorithm outputs and at least an alpha approximation。

 and we'll see what alpha is going to be， Al is going to be some 0。870。Okay。

And this inequality looks something which is more manageable because the left hand side。

 we already know what it is in terms of the vectors， it is some or Ij in the edges。

A cosine of the inner product between vectors， V IVJ。Do it bye bye。Okay， and the right hand side is。

 of course， in terms of the vectors， GWSDP is。嗯。Some over I J in the edges。

 one quarter V minus Vj hole square。Okay， and we're comparing these two quantities and we want to show that this is at least alpha times this right hand side。

Okay， and。Okay， this is what we want to want to compare。The rounded value to the actual is DPL。Okay。

 this actually， you know， it turns out。There's a very simple way to do this。Let you know。

 let's do it term by term。Okay， let's just look at a pair of vectors on the left and a pair of vectors here。

up like one term here and a single term here。Okay， so that's just a。

You know it's something that's happening in two dimensions， it's in fact a one parameter thing。

We already saw that this was like theta or pi or something。With theta has the angle between V and Vj。

It这是。And。And this term is， of course you can write it in terms of angle between V and Vj， right？

Because it's the distance distance in terms of the angle there。嗯。啊。嗯。I think it's the same。

Squared theta over 2。Yeah。Right， so。Okay， in terms of angle， you know？

The distance between the and here is really just science squared the two just some geometry。Okay。

 so so then， you know， I can ask what's the worst possible ratio between these two quantities Okay。

 let's call that alpha let。Alpha GW be the。Minimum value of theta over pi divided by sine squared theta over 2。

As you vary theta between0 and pi。It's the worst possible value ratio。Okay。

 this ratio you can calculate on a computer， it's at least some。Poin it so I need something to do。

Okay， so what we just did was term by term， this term is at least。878 times in this system。都没得。

So therefore， the sun is at least 0。878 times the sun。做。So therefore。

 the sum is at least so you've got expected number of edges from S to S complement。

Is at least this alpha Gw， this is like 0878， blah，h， bla blah。Time times the gom SDP value。

Is DP optimal？And that is at least point the same constant times the max cut well。

So that's the algorithm。We solve the SDP。Cut by a random hyperplane and you get a 。

878 approximation for the problem。Any questions on this？Or do you know if this like the 0。

878 is tight？Yeah， so it's a great question。诶。Yeah。

 we know it's tight under a conjecture called the Uni Game conjecture， as in it's NP hard to beat 0。

878。Under the Uni Games conjecture。But the Unii games conjecture itself is。Open。

 as in we don't know if it's true or false。It's one of the big open questions。嗯。So there's some。

 you could say there's some evidence that you couldn't beat this， but。It's conditional。

 it's based on a unique games conjecture and we don't know how to prove the Uni games conjecture。

Yeah。It's one of the big open questions， whether this is tight。

 you could say is one of the big open questions in the area of hardness or approximation。嗯。

But this rounding is tight， what I mean is if you try to accumulate these vectors in n dimensions and you could try to extract a cut in a different way。

 maybe you don't cut halfway cut do something else that you cannot improve that。そで。Yeah。

 you cannot improve that。嗯。Inth is。So you know， so this is very slick algorithm and works and everything。

 so what really。Happened in this。嗯。Is that。 if you recognize it。

 this matrix that we're talking about here or this quadratic form is just the actually the laplaian of the graph。

At the VMVJ whole squared， this is in fact the laplu of the graph。

 and we're maximizing the laplu of the graph really。And so。诶啊。

So just to give context of what happened here is that。Okay， really this function。

Xi minus xj holds squared， this is just x transpose Lx。Okay。

 and what we're trying to do is to maximize this。In fact， max cut。

 the original problem max cut of G is just maximize this quadratic form。Over plus minus1 vectors。

If you could maximize x transpose Lx。Over plus minus1 vectors it's exactly equal to max cut。Okay。

 all right， so the natural first thing to try would be。You know。

 we've done spectrograph theory for a long while now to do it。

 you know try to compute eigenvalues of the plusian so what would that be that would be。

Just same as saying， I'm going to maximize if I compute the largest eigenvector of the Laflian。

That is same as saying max x。In art to the end。And like a vector x， this is that its length is。

 let's say。L squared is n。X transpose L LG X。Okay， you can take a problem which is optimization over the plus minus1 vectors。

To optimizing over a unit ball and this would be the largest eigenvalue of the plus。

 this would just be eigenvalue computation。Okay， and you can do this。

 you can compute the largest eigen weight for the lapplian。

And what's goes wrong if you just complete the largest s vector le is that you'll get an n dimensional vector x。

Okay， get an endal vector x。Whose length is in。W length is n， so sum X squared is n。But。

The vector need not be。Balanced at all， so。Here we want an x， like in originally we wanted x。

 which is completely balanced， like you know Xs squared is equal to one for all I I mean every coordinate is of the same order of magnitude it's plus one or minus1。

It's the magnitude is the same app of every coordinate when you do the eigenvalue computation。

 you completely throw away the restriction on the magnitudes。

 you just say that the total squared length is n。Which means you can get a vector， which looks like。

You're allowed to get root and0，0，0，0。 This is a this is a valid。Valid vector， right。

 It can put all the mass on a particular coordinate。 I couldn't do this。

So that's what goes wrong when you try to compute the largest eigen vectorctor。In fact。

 here's what will happen， imagine I have a big graph G。Okay， and then just disconnect it to that。

 I put another edge。Let's say this is mine。Okay，If I。It my G it looks like this。

 has a big graph and another edge。Okay， if you compute the largest eigen vector of this。

Digen vector is no。whichs not at all compelled to solve the graph edge。

 it just needs to maximize this form if what it can do is it can do let's say I think it can do root root and over the eigenvector could put all its mass on that little ledge there thisjoin edge。

It could give you the eigenvector would be plus root n over to here。

And minus root and over2 here and0，0，0，0，0，0，0 here。Right because it can。嗯。

You can move around the mass as it warms。Okay， so just using eigenvectors， you don't really get。

Vectors， which look like。Max cuts， that you want to balance vector you don't get that。Okay。

 that's a little sad what does SDP get that you do SDP lets you combine eigenvalues and eigenvectors with linear constraints。

Meaning and somehow effectivelyly allowed to say。And if you look at my SDP that we wrote。

 where is it？Yeah， if you look at the SDzP that we wrote。

 we added these linear constraints on the vectors we saying V I squared is at most one for all I。

Or it is equal to one， let's say you said it's every coordinate you need to put a unit vector。Okay。

 and so。It lets you compute the eigenvector with this additional constraint that VI squared is at most one。

Meaning every coordinate must get the same amount of mass。Okay， and that's what。

Helps you so basically there Dp combines the power of computing eigenvalues。

 which is clearly important， otherwise you can't you can't solve this problem better than half with the power of just adding linear constraints on these entries like。

你度。Its lets you add a constraint like V squared is atmost one。OkayAnd。That's the。 That's the basicか。

That's what happened in New Mexico。Any questions so far？Allright， so so。Okay。

 so we saw this is an application of Maxcard sorry SDPs。

 so I'll show another application of SDPs just because it's kind of。It's kind of a cute application。

But yeah。嗯的。Okay， we'll see what this other applications。So these other application just cute。

 So that just， you know it's it's going takes 10 minutes。 let me just show you anyway。

 So it's called the。Between mass problems。做。So what is this problem well you know a lot of the problems that we're seeing they are in the category of what are called constraint satisfaction problems。

 you have some n variables and you want to find some assignment or some permutation and you have some constraints on them。

So here， what is the between this constraints satisfaction problem？It's this so you have。

Somebody tells you that find the permutation of one of n objects， let me call the objects。

Find a permutation of。And。We call the objects O1 through ON。OkayFind a perutation going through n。

Such that。He gives you constraints on the permutations。And what are the constraints？

Like there are constraints like。Or oneお five。Is between。0，6 and0，10。Right， and O I is between。

おナイエン要オージェーエンオッケー。Okay， so these the constraints out of the form Oi is in between Oj and O。

These are kind of constraints here。Betweenness constraints here。Okay， so you have。

And you want just want to。Find a perutation that satisfies all of these constraints or as many of them。

Okay。And， let's say we are guaranteed。That there exists some permut satisfying all the constraints。

All the between this constraints。 Okay， so there's some permutation that says all the between this constraints and。

You know， even then it's MP complete， even if there is a problem to find this best find a find it is MP complete。

 So your goal is just to find。嗯。Satisfy as many as possible。Okay。

 so that's the problem so it's a it's a constrain satisfaction problem a bunch of constraints。

 it's a max constrain satisfaction problem because you want to。

End up with a solution that setses as many as possible at the end。Is the problem clear？Okay。

 so now what is the algorithm， the algorithm is。Fairly simple SDP SP algorithm。

 So here's the algorithm， so。Okay， we want a permutation。So for each Oi， the object I。

Must be in some position， right， So there's a position。objectbject I will be in some position。

 let me call it。Beify。That's and we are solving for these positions and it's PFI， you know。

 like it's the the PFI is like it's some number in one through n。

It' it's in position I in the permutation。This is what we're trying to look for。And。

Our betweenness constraints is that。You know， if or O I between。O J and okay。Is the same as saying。嗯。

You have DJ。Between less than the。Les thanン pk。哦。PK less than actually just just use strictly less than I don't need less than equal to I think this strictly less than。

PJ less than p I less than p K。R B K less than B i。Les than B i。listing feature。Okay。

 so that's what you'd want。Okay， so now how do we find。诶诶。Soution like this， we'll write an SDP。

 the SDP is going to be。Okay you have As vector VI。To vertex to object I。At what is a vector VI？诶。

It's going to be。Right， it's going to be in sort of this。嗯。How do I write。

It's going to be the silly thing， so you're just going to say。All right， you want every。

 you want to order them right you want to order the object， so let's say。奥运。Through o and。Ex， or one。

 or five， or seven， or eight。And some ordering right and let's you know。

 let's say the origin is somewhere I don't care so much the weather so let's say this is the origin。

0ero and my vectors are just going to be the nine， the simple thing that。You know， this would be V1。

And this would be v fired。Right， we7。铁定。The end。And the8。It just that。

Just all in one dimension going this way。All right， so。Okay， so now that's fine。

 so how do we write the constraints now？If I want't。if I want I to be between J and K in this order。

Oi is in between Og and O。连。Basically， the。Vj minus V and Vk minus VI point in different directions。

VJ minus V。And V K minus V。These vectors point in opposite directions。

That's what it means for the I to be between J and K。

These vectors are a point in opposite directions， that means that the inner product between them is less than zero。

So let's just add that constraint。So far。For every betweenness constraint。

Whenever you say Oi between。O J and okay。You add a constraint saying。

The inner product between Vj minus V。And V k minus V。Is strictly less than zero。Gemetrically。

 this is the same essay。It's the same as saying the angle。Between。

Right this the angle bit like if I look at VJ。Minus V and Vk minus V。If you look at this angle。

 this angle is obtuse。Okay， in fact， that angle is supposed to be。

180 degrees right there have to be sort of facing the opposite directions to each other。

 but you know we don't know how to add that constraint as a constraint in the sena products。

 so let's just add this one。The angle is at least 90 degrees。Okay， and so you solve this SDP。

Right find me vectors， find V1 through VN。Such that。This is true。Okay。

So that's good you have N vectors now。K all the。And SDP will give you vectors such that。

If for every betweenness constraint， this angle between Vj minus V and Vk minus VI is actually obvious。

Okay， to get V1 through VN。And these are vectors in n dimensions with these optous angles in them。

What do you do， you need to again get back an ordering like a real ordering on a line。

So you just pick a random direction and project onto to that it's one of the most natural。Tings you。

Do we just pick random direction G。And you just project V1 through VN along that。V1 dot g。

Let X I v V I do T。So I should not use do we use this notation at excise VI in a product sheet。

This is just。Project。安示。Okay， so now we have all the points on a line， right， The X 1。

3 x are numbers， right， So they real numbers。 So and I mean， you just project it onto a line。

 So therefore， you have a permutation right， So the permutation is the ordering。

Pmutation is given by。The ordering of the excise at the increasing order of excise， let's say。Okay。

 that's the algorithm so you solve the SDP， you pick a random direction and project on to that。

So here do we have an objective function or right this here we didn't have an objective function it was just a feasibility thing in fact this。

Yeah， we assume that we are guaranteed that there is a permutation that satisfies all the constraints and only in that case we are able to write this SDP because we had these constraints and。

Yeah。And so it's a feasibility thing SDP， you find vectors that sat file SDP and you just pick your random direction project onto that。

Okay， and then， you know， what happens Well， we need to understand what the approximation ratio is well the。

So， so again。I want to know what's the probability that Oi。Is between Oj and O。Okay。Again。

 the if you're only interested in。What happens to two vectors or three two vectors。

 you have to worry about quite only in two dimensions so。So what do you do。

 so let's look at the configuration。So let's look this configuration。I'm going to。

Put the eye in the middle。V接 v剧。So let's just look at Vj minus V and Vk minus V。

 right these two vectors。And now I am picking a random direction to project on。

If I pick a random direction to project on。嗯。When does I fall between them。Right， so I guess。

If I picked a random line to project on， let's think of a random line to project on。

If the line is like this， then the projections satisfy that I。Is between J&k。ok。Only if the line。

Actually。Goes between J&K like this。If it goes this way。Then the projection of j will be here。

 projection of k will be here， and projection of y will be here， so I will not be between J and K。

So in sometimes， the only time you will violate this constraint。

 the pro that Oi is not between JNK is when the line passes in here。Sorry， the yeah。

 the line passes in there yeah。RightMy picture is not so nice， it makes it confusing。So alternately。

 the normal vector to the line。Is。So， okay， what do I want to do。

 I want to prove that let me say with the statement I want to say the priority that O is between at least O J and k is at least a half。

Because。The angle is obvious。In fact， the probability is at least the angled theta divided by。喂い。

And so therefore。And。In my picture， it looks like。嗯。Yeah， I mean okay。 so so the its。Right。

 so my picture is sort of very。Misleading。Okay， so really， you know it's a bit like。You have I。又唔知。

了企。ok 嗯。I guess one way to see what's going on is let's look at this angled theta if you want to just do it。

Without looking too closely， you say， oh， if the angle theta was 180 degrees， what would happen？

If theta was equal to pi。Okay， let's say if this was theta equal to pi。

 no matter which way I project。I will be between Z and K。Which no matter what line I project。

 I will limit in J&K。And if theta is0。Of course， no matter which way I project。

I will be outside J NK。Right so it's， in fact data pi is sort of like the probability。

 but really the。The normal vector to the plane。じ。Yeah， I guess you should work with yeah。

 if you look at the normal vector to the plane。That has to be in between I this here。

 and that happens with probability theta or pi。And so you get at least half the constraints are satisfied。

Oh。Okay， so this is this is what good I mean， so we saw two examples of semi defite program today。

 these nice cute examples， but you know I didn't deliver on my promise that you know this is going to be like a。

you know like a higher level programming language where you can encode many problems。

 it seems like in the both these examples some of geometry came into play a lot。

 like a lot of geometry came into play， you know but you'd wonder what if the problem doesn't have much geometry in it like。

I don't know three sat right or two sat let's say max two sat that you satisfy these clauses。

 but it's not really geometric so right at least there's no apparent geometry so。

So it would seem like sulator programming is purely about this geometric configurations。

 but in the next class well see how to sort of systematically write down these SDP relaxationations。

 not doing this clever geometry， doing systematically write down these relaxationations and。

See what they lead to。Any questions？嗯呃。Can you reiterate like the。

 I think you are mentioning the runtime or the hair of STP？Okay， so the runtime。So the runtime for。

 let's say， solving Gomans Williamson， you could。I mean。Right。

 so the the reason you can solve it in time poly N and。Log 1 over Epsilon。えル。

Only in n and log 1 or Epsilon and you can I mean we saw how to do this using ellipsoid method and separating oracles in the first homework basically。

You see that this is basically a linear program。And there's some convex set here sitting here which is a PSD matrices and you can just need a separating verticalacle for this convex of this PSps of PSZ matrices and the separating verticalacle for that in the first homework we constructed using eigenvalue computations so you can use ellipide method to solve SDP to poly and logan or epsilon。

You can do interior point methods also， but。If once you write down an SP for a particular problem。

 like， for example， max cut。You shouldn't use a general ellipide method。

 You should use something more tailored to this。 So for that， you can do something like。

Mirror descent， really mirror descent in this setup is called matrix multiplicative weights。

Multipulative weight， but a matrix version of that。嗯。So can do mirror descent。

Or matrix multiplicative weight and get you can solve the max cut SDP in nearly linear your time。

 so in time which is basically oilda of the number of edges。嗯。对。I want to say poly when or Epsilon。

And one more thing I want to add is that， you know， national numbers or even。Just algebraic numbers。

嗯。The't be if， you can never solve it exactly， you cannot write down the solution exactly。做。

You can only solve it approximately。If you use interior point method， you are aipide method。

 you'd get poly and logan overpson in general， and for max cut and so on。

 you can actually do it in linear time。Our professor。The definition of appears。ThePD matrix。

And can you scroll back to it Oh yes， oh yes， yeah。



![](img/52f932fb79b1de2a13e652bd92fe84a2_2.png)

So， yeah， very okay， let me find。

![](img/52f932fb79b1de2a13e652bd92fe84a2_4.png)

Yeah。so for number three， should say V is like R N by N。Like these are oh yes， yes， thanks。

 yeah these are in Bayenia。Yeah。Are you also requiring M to be symmetric。Yes， M has to be symmetric。

 Yeah， we we will always， yeah， this will always be symmetric matrix， yeah。Yeah。

 and a real symmetric matrix yeah。是。And so when you say like it's hard。

 like MP hard to get better than like 0。 like87。mean like。

No randomized algorithm can like do better than that in expectation。No。

 it's just even determinist like algorithm also and I mean we don't okay for max max cut we believe it's NP hard。

 it's NP hard assuming Uni games conjecture， but the general format of hardness approximation result is for example。

 if you take。I guess which pro vertex vertex max 3 set。

 it's NP hard to get better than seven8s approximation。Yeah。

 what that means is whether it's randomized， the deterministic dec doesn't matter。嗯。啊，有。嗯。I mean。

 so basically it goes on to this complexity theoreticaloretic belief that。

basically the problem is NP hard now you can ask the question。

 are randomized algorithms more powerful can randomized algorithms solve NP complete problems whereas。

Deterministic ones can't， but we the general belief is that。

NP hard should be hard for both randomized and deteristic any it should take。嗯。

Both of them should take super poly normalmal time。

 so it doesn't matter whether it's randomized a data mistake。

What is the requirement on the objective function？Oh it has to be just a convex function right if you're minimizing an SDP。

 if you're minimizing in an SDP， it has to be a convex function of the PSD matrix of the entries or of the。

Minimizing a convex function of XIj is fine。It F of X I J economics function。

 but typically when they say S GPp， they usually mean a linear function and so then it's really。

Just a linear function on the entries of X。So really all the optimization is happening on entries of Xj only we are just interpreting that as inner products of vectors at the end。

 so we solve SDp and then do Chilesky decomposition and we get vectors。

 but the vectors are not canonical as in。嗯嗯。Every PSD matrix has。

Infinitely many tlesky decompositions it's not unique， so the vector configuration is not unique。

 but the angles are unique VVJs。When do people use this algorithm in practice？系啊。Yeah。

 I guess I don't know actually， I mean， I guess the question is really。

 does Max cut show up in practice？😊，That's the real question and I think the issue there is really that。

LikeIn practice， you'll never see an optimization problem purely in the form that you see in a class like this because。

neverever want to you know your goal is never to purely optimize max card it'll be like oh max cut but I care about these edges more and I care about these vertices more and these two should never be together and so on So really in practice I guess you'd be solving a constraint system with sort of mixed constraint and so on or mixed constraintss or something more。

Complicated， this is like the basic。It's like a bit like yeah。It's a bit like studying。A motor right。

 but you'll never just use a motor you have to put in wheels in the body and everything to have a car or something so。

So it's a bit like just literally what we're doing retros is is really two magnets and a coil and just looking at the motor。

 but it'll never be。And when you look at， you know， the， yeah。That's basically what's going on。

Thank you， Professor。

![](img/52f932fb79b1de2a13e652bd92fe84a2_6.png)

That's just the question about the final as Im like I've been trying to do the questions。

 but I don't think like I'll get the time to。Take like try all of them so like would the solutions be out after this or like would we get time to submit this again。

 but like not for as a final but as a homework only。Yeah， I mean。

 I guess the the some of the like a couple of students because of DSP other reasons are submitting late。

 So I and so we won't post， I won't post the solution at least Tuesday or something and I mean。

 there's no hurry to post the solution if you want to。Think about it longer。

 I can hold off on posting the solution。嗯。これは。Okay， and also like for theorems。

 if I'm like putting theorems directly from the notes from the class or like from one linked on the website。

 some of them are like like not。Tightly bound， but like if I if you like， look other papers。

 they are like much tightly bound with a much difficult proof。

 So is it okay if I just use like the the the ones in the notes or yeah Yeah。

 I mean we don't don't really in。I mean， it doesn't have to be exactly in that form or。

If it's sort of implied by what's in the group very easily， it's fine me or yeah。嗯。

Also generally like I'm a sophomore right now I'm taking this class or like I'm having fun。

 but at the same time I feel like while doing the final even though I'm able to do a lot of it。

 I'll just have to like go back and like go again and check stuff from the class like again and again which wasn't the case of 170 like if you give me a 170 problem I would be like able to do it without checking the concepts like if Ive like take them once so is it because like I'm just prematurely taking this class as and like I haven't been exposed to the right amount or would this be a thing for like if I would have taken the class any time Yeah I think it would be a thing anytime I think it it's not it's not unusual I mean。

Right， so like the thing， I mean， like thing with the material in 17 is。

Veryry high level paradigms like dynamic programming and on there's really very few concrete things you need to use in an actual problem solving thing you learn how to do dynamic programming and but here concretely you'll be using some theorem and some things like that so and even for us you know like like when you're thinking about these problems of course a lot of this material will be sort of。

Because you used it so many times in memory， but half the time in research you're just looking up things and even things that you've done it several times you look up。

Because it takes a while to just derive it by hand and then。I just always look up and。fine。

Also like I don't know like I've been trying to get into research related to this。

 but like like that's why I like the course project that we have this time so I get like that would be like my first。

😊，Me exposure to research or something like that but what would you recommend after this class like where should I look for research in this direction we should talk I mean we can chat consider a meeting and chat I mean maybe like in the early summer just soon after to the class we can chat and you know you can start with me or any of the other faculty if you like Geni Nelson or Saia I mean they are experts in algorithms much more and you can chat with them about any of these topics and yeah we can start work doing on research yeah。

Yes， that would be awesome because even though eigen is starting because the gradient decent was convex optimization。

 I thought like okay， maybe I won't like like the like it too much but once we started like studying our embeddings and then the the spectral graph theory that was like pretty awesome for me like like learning about how eigenvalues and eigenvectors could be used to like simply bound or like talk about different graph structures was so amazing。

 Yeah Yeah you know its so much interesting material to explore This is the thing。😊。

I turn when theyre in this stage the early early PhD students and on it's really。

 I guess's my going back to analog。 It's like visiting。Ysemite or Rimalas for the first time。

 so I mean I have fun going through this areas， but I've seen it so many times at some of the fun but the first time it's so much fun to see all the places and things a bit like that。

The first time， yeah， you learn this thing is' good lot。Definitely cool。 I I like to talk more。

 I I have to go back and complete the final。😊，YeahThank you， Pro。



![](img/52f932fb79b1de2a13e652bd92fe84a2_8.png)

おsね。