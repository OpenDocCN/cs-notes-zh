# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p04 Lecture_04_Shortest_Paths.zh_en -BV1a4cCeMEzb_p4-

So maybe let's get started guys。嗯。A couple things to mention。

 one is that I've just put up homework number one on the course web page。It's。

There are four problems in there。 you are supposed to attend only two。

 So it hopefully should be short。 on the other hand。

 I do urge you to solve as many of the problems as you can。

 It's these the problems that we've chosen because they are kind of interesting and hopefully theyll teach you something to you about the course。

在。对。So today's plan， by the way， any questions did people have。Questions about the course so far。

Good so today's plan is going to be I'm going to talk a little more about short paths I'm going to just mention a couple of approaches using matrix multiplication and this will give us an excuse to talk about fast matrix multiplication and in general of matrix methods which well see a little more of in the next few lectures as well I'll also briefly talk about LP approaches maybe I'll first talk about LP approaches and then I'll talk about the matrix based methods。

And then if we have time and we'll see how it goes。

 I'll talk a little bit about this idea of low diameter decompositions that we'll use in the following two lectures so I'm going a little slower than I was anticipating but that's okay because you know that's one of the advantages of going a little three lectures a week we can pad out a little more if we have to take a lecture or two more so that you guys don't feel rushed I don't feel rushed we might as well do that。

😊，So yeah， don't buy your flight tickets day。The day after the lectures are over， actually。

In week 11， you shouldn't be buying a flight tickets anyway。Good， okay。

 so let's talk about shortest paths a little bit。You've seen。

Sure paths all through the last lecture and。EAD chance。And remember that shortest paths。Okay。

 there were two variants of shortest paths， single， so shortest paths。And all pair shortest path。aP。

In both， we are given a。Directed。Graff。Which Im going to write as vertics and edges。

 even though Im youm not emphasizing too much that these are arcs， but these are directed edges。😊。

There are weights on the edges， which may or may not be positive。And in the single source case。

 there is a source verortex。呃，S。And I want to find charted paths to the rest of the graph。嗯。

I'm gonna good。So we already mentioned that there are ways to solve single source shortest paths with non negative edge weights。

 it was die extra with negative edge weights， it goes Belman Ford。And then for all pair short paths。

 we very quickly mentioned that you could run anxs if everything were positive。

If things were negative， you could use Belmon Ford to come up with this idea of feasible potentials。

 Maybe we'll remind you what that was。And then use those to convert the graph into a non negative edge weight graph and then use di。

 So I'll pay the shortest parts。 you could use Belman Ford plus n ditras。

Or you could use a algorithm called Fyd Was and both of these naively are pretty much cubic time for single short。

 shortest partss depending on whether it is positive or not positive negative if it is positive use diextra。

😊，If it's positive and negative you development for。

So this was this was the scope of all the work that's been done。嗯。Maybe。

There's one more approach for all pay shortest paths。 That's very。Interesting approach。

 And perhaps one that bears mentioning。嗯。Which is a matrix based approach。

 So let me just talk about the matrix approaches first。嗯。

And this is chancellor that you've seen this before， but let me just remind you of what's happening。

So， what。We could do here is that I could write a matrix。 and let me just write our matrix a。😊，As。

This matrix where。For every AI J。If equal to the weight of the edge I J。If I J， if I comm a J。

Belongs to the head set。And it's equal to。力舍。0。If I J is not in the head set。Okay。

And then Im going to define a matrix product。三分度该。Were going to multiply A and B。So， you know。

 how do you define matrix products， Normally， this is just the sum。

So the I JF entry of this thing is the sum overall K of AI K。理けジ。

What we are going to do is we' are going to define a different matrix product。

 which is going to be a and I'm going to write it like this。Which is going to be。门面。我게。O I见。

Let's be careful。So maybe I don't want this， I。The， notice。What I've done where I had a product。

I'm putting a summation And where I had a summation， I'm putting a in。Okay。

And I am taking in some sense， the product of these two matrices。According to this， so called。明。不。嗯。

Algebra， this algebra where。Mulipplication is like， addition。And on the other hand， audit is like me。

And so this is often called the Min plus product。Of A And B。哎。So let me ask the following question。

 Suppose I look at the min plus product of A and a。And I look at the Ige entry。Of this。

What is this object， What is this computing。好那行。The shortest part of length。To all one。

 So it really sort of comes down to this question of what am I putting in the diagonal。

 I should be a little careful out there。 And I'll just make sure that I do want to put a。

0ero in the diagonal。So let me put a zero out here。Yes。I b改读者。大借。Is not an edge。诶系。Okay。

So what is this computing， this is saying look over all possible values of k。😊。

And look at the length of this2 hop path from I to K and from K to J。

And take the mint over all possible such intermediate value scale。嗯。So this is the shortest spot。

Using。At most2好。对。We good so far。And similarly， I could define a。诶。哎。

And there's going to be n of these guys。Is the shortest box。Using atmost N hops， let's say。

And if I look at the shortest part using at most N hops。

 then this is really the shortest part in the graph。Are we kind of happy with this。

 Do you want me to say a little more about this。Yeah。对。的。This one。You guys can see what's happening。

And this is really， you know， any shortest path can use that most N hops because if I want to go from I to J。

 any path can use vertic C that most wants。😊，So the shortest path can use at most N hops。

 So this is really just the shortest path。😊，Shortest。In G between I and G。对。So this， you know。

 I can write in short as A。Is the endhole product of。And then I use one more fact about this。

That this product。iss。Associated。I can compute a。Using one product。I can then compute a。

To the fourth。By just， this is just the same as a。诶。诶。哎。These things have already computed。

 so I can just。包 it。And I can compute all the way to a。You know，2 to the T。

 Well2 to the T is approximately n。And they should be good enough， right， I mean。But， you know。

 in fact， if I want to go any further， if I want to actually compute A N。

 I can use these powers of two to product them together as well。So the point is。

 this is approximately。So， the number of。Products， I need。De order login。Bless you。

And how much time does it take to compute one of these products。And cubed， know， just naively， right。

So this gives an order。And you。留嘅仔。Char by its computation。嗯。Its very easy， almost naive。

 I would say yes， please， good。😊，Good， excellent question。 So the question is。

We just said in order to compute this mint mint plus product。I could do this in order。And cube time。

And as always， we ask the question， well， is that the fastest you can do？So for general。

 for ordinary matrix multiplication by which ordinary， I just mean if I wanted to compute a B。

A times B over some， you know， let's say。Ring or a field or something like this。 you know。

 standard over standard algebras。😊，Which have some nice structure。 So in this case， you know。

 computing this can be done fast。So it can be done faster than。Order and cubed。

And most of you know this， So you know， it won't come as a surprise that this was a paper of Strasson。

In 19。What was it，60 something，69， something like that。Where we computed it into the 2。7 something。

 Basically， this is log。Base two offset set。And this was a big deal。 I mean， this is。

 this was an amazing I。 you've heard of this before。 And then there's a long line of work。

 And then theres this work of Co Smith。😊，And whenold grad。Who got it down to order and to the 2。37。

 something something。And then there is some more recent work including some ideas using you know there is using some deep nets to optimize things and the running time is ordering to the 2。

37 the changes in you know this third or fourth digit but I mean that is not the important thing like we can discuss this sometime with these sort of improvements out here would the essential ideas remain the same。

😊，As before。嗯。So really， if you want to， you know， if you haven't seen this before。

 you should definitely check out Strin's paper。 It's like a。Beautiful toopaste paper， Threepaste。

 maybe。But so so this line of improvement is all when the the the algebraic structure is very nice。

 it's either a ring or a field。😊，Sadly， this algebraic structure is not that nice。

This is what is called。呃，310。Because the minimum operation doesn't have inverse。

And products over semi rings， we don't know how to do better than order and cube time。

We don't know lower bounds， but we don't know after bonds， which are better。肯데是在。

It' a great question。Can you do faster semi ring products， In particular。

 forget about general semi rings， just do faster minless products。There are some barriers， but。

The barriers essentially come from single source short paths and related questions。

If you're interested， I can post something on P。Yeah。One thing I can't say。

Currently the best known worst case runtime， of course， or all pay short paths。Still remains。哎。

Essentially。En tune。And the question of， can you get n to the3 minus epsilon for any constant epsilon remains open。

怎的。However， there's been some progress。 You know， it's a small， small amount of progress。

 but it's it's worth mentioning because it's。This is a very interesting thing when it came out。

 There are algorithms， which run in。😊，Look at this run time。 Don to the square root log。Yes。

So it is not quite polynomial，2 to the login would be polynomial。A2 to the square root log again。

 it's not quite poly。But it's not quite logarithmic either。

 So its a function that is strictly super logarithmic and strictly sub polylynomial。😊。

This kind of runtime can be obtained。And this is a very nice paper of Ryan Williams。

And I should mention that R Williams was one of our own students and graduated in 2005 or so。

And the idea out here is to use some ideas from complexity theory and some ideas from algorithms together。

So， you know， if you take a course in complexity， you shouldn't just imagine that that's useful only for lower bonds。

The complexity guys are just showing reductions in the wrong way。

They are taking heart problems and showing that you can use you can use。

 you can reduce problems to heart problems。You can reduce heart problems to other problems。

 and we are trying to show be you know。You can reduce problems to。It's all reductions。

But in any case， it's a。The point I want I want you to take away is that all pay shortest passed getting a sub cubic algorithm。

😊，The big open question。Again， one of these questions， you do this， you get a PhD no questions ask。

Of course， the。What as， as is typical。Since we can't break this barrier。

 we haven't been able to break this barrier。 people have been asking the question。 Well。

 assuming that this is a lower bond。 What else， what else can we show as lower bonds。And there。

 there's some work。 it's called fine grain complexity。 So if you're interested。

 you should look up pine grain。嗯。But。That's beside the point right now。Yeah。So all pay short spots。

 How do we do better。We don't know。Well， actually， we know in some cases。If there's some structure。

 we can use that。And let me give you an algorithm。And since we just talked about。诶。

Mattrix multiplication， let me give you an algorithm using matrix multi。Yeah。So let me okay。

 So what's， what's the result。 I'm going to tell you。 I'm going to tell you a result of。

On financial response。And。And to the omega。 Oh oh， I didn't define it even。So。

 since the exponent of matrix multiplication remains you know changes over time， we just say， oh。

 the runtime is going to be n to the omega。😊，SoN to the omega is just the run time for matrix multi。

Omega is exponent of matrix multily。So if there is an improvement。

 the runtime goes from enter the oinina to enter the omen。哦。

So I'm going to show you how to do a PSP in order n to the omega。罗洋街。And of course。

 if I could do this， I'd be breaking the barrier I just talked about。

 So this is for special classes of graphs。😊，So， far。Unwaed。Unit weight edges。And undirected。

Very special class of graphs， but for this class of graphs I can give you an algorithm which just takes matrix multiplication time。

😊，怎呀。Yeah。Quest sorry， I got feel like what is APSP all pair short spots。O。我被说吧。Yeah。Oh。You罪。这个对。好问。

ASo the algorithm that I gave earlier。😊，Used this form of matrix multiplication， this min product。

 min plus product。😊，Mein class product。 I only know how to run in cute time。

Right now Im saying the runtime that I will give you will use standard matrix products。

That makes sense。Questions。Okay， so let's do this。And this is a paper of Raymond Sale。

From the early 90s， I think。嗯。95。Yeah。So let's let's do the following。嗯。

So the basic idea is going to be the following。I'm going to go， I'm going to take my graph G。

And I'm going to take this graph， and I'm going to square it。And I'll tell you what exact。

Form of squaring。 I'm going to use。嗯。So my distances in G are denoted by little D。

Distances in G squared， I did not by capital B。嗯。And then from this， I'll come back to G you know。

Infer little B from capital。세트 는 끌 쓰면 안 돼요。I square it。I square the graph， I compute distances。

 and I from these distances， I'm going to infer the original distance。😊，So far so good。对。

And the log will just come from the fact that each time you know Im going to the square of a graph and really when I take the log log squares that is really like GN。

 which is the。😊，Good。So let me define G squared。So G squared has。嗯。An edge。I J。If it exists。啊。

You know， if I J belongs to。The edge sec of G。Or there exists two hop points。印机。그마든지。

So if I gave you， let's just do a very little， you know， very small example。嗯。So in this case。

 what are my edges of G squared， there will be all those edges。Plus。These three edges。Okay。

And if I had。I just like this。Then I would also have。This edge。I would have this edge。I would have。

Any other edges。你在这。OK。可以。From the first one to the So I'm looking for only two hop parts yeah。你看。

This is G square。喂以。Fact one。The distance between U and V。In g squared。Is。

The distance between U and V。嗯记。Divided by two。让这个。Let's look at these two vertices， U and v。

Their original distance was three。Their new distances。就。We believe fact one。嗯。somehow so yeah， going。

Yes， yes， thank you。Okay， we an to。Well。好的。So in this case， by the way。

 notice that G squared also has these edges。😊，It has all the edges of the original。

So if the original graph is connected， then the new graph is definitely connected。😊。

Its just connected using chartered lines。Okay。So， the distance is out。佢。So this means。That D U V。

Belongs to。Either twice do U V。Or twice B U V-1。So if I have computed distances in the new graph。

 I can infer distances in the old graph up to this。😊，Additive one。Okay。Now。

 lets figure out when will the little D be equal to twice capital D and when it will be twice capital d minus1。

So let's look at an example。So this was the situation。The distance from U to B。Is four。

Let's look at the distances from you。To the ver fees of the graph。

And we might have other edges coming out of。So what's capital D？Capital D from u to itself is 0。

 This is one。 This is one。 This is 2。 This is 2。What can capital D be for this guy？2 or one。

 Can it be one。Suppose equal equal one。要对。Suppose this was one。Good supposeupp this for one。

 What does this mean about little D for this guy。这个我说。응。好晚呢。1 or two， right at most two。

Little D is in green。Little B that most。Then what would the distance of U of weB at most 3？

If this was the shortest part。Then we would have got a contradiction。

Because I said the shortest part is of length fault。

So if I'm just looking at the shortest parts from U to me。This guy can't be。完。系。对。This must be。

 at least。My claim is。Suppose the distance from U to V， the shortest path， distance from U to B。

Suppose。Littlely， you be。Was two times capital B。嗯对。Then。This is one such situation。

Then all the neighbors。Of费。没有。All needle。哦，V。Have。Capital B。因为。你こ以죠。Or greater than meこと。

Two times little。Think of。This is two。 This is4。Suppose the shortest part is of length 4。

Capital days， too。My claim is that all the veres， which are neighbors of we。😊，Must have capital。

 at least two。Must have capital， at least。啊，哦。啊嘅。My mistake。哦。嗯。I don't know what I'm writing。 sorry。

 you guys。All neighbors， W。Of we have the。UW。At least B U V。Thank you。😊，If something looks confusing。

 please， just， you know， I'm making a mistake。This do we believe？

You guys look less puzzled this time。Keep this example in there。Suppose。It was the other case。

This is you and this is me。Let me write down the capital Dvalue 0，1，1，2，2。3。

Let's look at the neighbors of V。What can this value be。It could be2。It could be3。喂。

Can it be more than3。Because。Here is the path2。 this is suppose this is W。

Here is the path of to w of length 6。So this guy's capital D can't be more than three。So when came。

 this is like most。3， this is like most。Okay。So the other cases， suppose。你愿。

I equal to two times B u be -1。Then。All neighbors。W。嗯，是这。嗯。你。UW。At most be， you。All neighbors of we。

Have D UW at most D UV。And。1 neighbor。嗯。W。你 quite could be you。慢。O。Two cases。At least so。Two cases。

I want to distinguish whether this parts was odd or even of。Even for odd。In this case。

Suppose I look at these neighbors。All their values must be at least this guy's value。😊。

So their average must be more than this guy distance。The average distance from you to all these guys。

Must be more than the distance from you。Look at the other case。What can you say about the average？

It must be strictly less。So what's the claim I'm making？So， my claim。And。Little D Uv。Is equal to。

Two times capital D Uv minus。An indicator。明啲。Average distance。From you。To these neighbors。

Is strictly less than。The average the distance from U to V neighbors is strictly less than the the distance from U to v。

If I look at these neighbors。If their average distance is smaller。

The average capital B distance is smaller。Then the deep distance of V from you。Then you'll subtract。

你看。Now， the only question is， how am I going to。どで吧。So how do I do this fast？Let's do。

Suppose I have a matrix。Where I have all the values that B values。And to玻璃。Multiply it。

With the adjacency matrix。对。Remember the graph is。Undirected。The adency matrix is symmetric。So then。

Let's look at。What am I looking。I'm looking at。This product。The Uv entry of this。

You the entry of this。Is the sun。我会了。你。UW。AW V。喂。As the adjacency matrix。

 It's got once exactly on the ver C。 So this is the same。😊，And oh， this is overdoly， right？

Where are the zeroes of a， Where are the non zeroes of a。Exactly in the neighbors。This is w。

Such that W is。那个。哦。嗯明。The。嗯，や。So it's the sum of distances。Of all neighbors of。I wanted the average。

So I should divide。So this is what I want to do。 I want to divide out。By the degree of the。

So I should just put out him。멀리 그었스。So I can just say， this is one over。

So I need to just change the entries of a。So that all the relevant entries out here are divided out by a degree。

So what am I going to do， I'm going to take the column corresponding to B。

And I'm going to multiply that by one over the degree。And I'll do this for every vortex of the graph。

Did that make sense。Its some algebra if you you know got slightly lost in the algebra。

 but basically I want to say I took this capital D matrix。😊。

And multiplied it by a single matrix out here。Which is just a column scale version of the adjacency matrix。

And what pops out。What pops out。Is exactly。The average degrees。This is just the average。Deegree。

 so this is just saying this is the average distance from you。To neighbors of three。

And depending on whether this quantity is strictly less than DUV。I want to subtract one。

So let me just write down the final algorithm。 So the algorithm says。细啲。On the graph G。

What did he do。He first constructs。G quag。I need to construct G square。My claim is， I can do this。

Ming。One matrix multiplication。Okay。Because I was just looking for two hot pointss。

So I use an idea like the one before。So this is step one。Step 2。Run side down so。Get capital D。

 which is the output of Cel。On G squared。Recursive call。哪也不准。所。Set little day。有咩。2弊。

Two times capital B U V minus correction term。How do I compute these correction terms。Yeah。Multiply。

D。With this scaled version。U。T D times this scaled version of the adjacency matrix。嗯。

This uses one more matrix multiplication。再追。没说。我个 chance。Questions。嗯。是 I'm gonna stop。

That's a very good point。Yes。G has。嗯。嗯。Yeah， if g squared equals G。靓啊。呃 returnturn。呃，对。

So what's the distances， then the then return DI J。Is equal to one If I is not equal to J is 0。那是。

If this make sense， Yeah， How do you construct。Good， so there was。Let， let's， let's do that。

SoI want to construct G squared。I was going to give this as an exercise， but let's destroy it。

So how do I construct G square？So first of all， I have given the graph G。Here is adjacency matrix A。

OK。So let's look at the standard matrix multiplication a squared。😊，A squared is exactly this object。

Is actually equal to the number。Of do好吧。From。A squared I J is the number of two hub spots from I to。

😊，O。😊，So if there is at least one2 path， then I should be fine。

Now you just set so the the the adjacency matrix。Of G squared。The I J entry。Is going to be。

What's it going to be？It's going to be one。If。A squared。IJ is strictly greater than0。All AI J。

Either there is an age in I J。Or they at least want to happen。

So I needed one standard matrix multiplication。Plus， and quited righttic amount of work。张梦凯。

Did that make sense。嗯。啊，好，So that okay， and I can leave it up there you guys can see。

I these condition like， why is it one？So my claim I made this of the cuff。

 but I think this is correct that if I take a graph。😊，And if I squared it。

Then my claim is that the only case where G is equal to g squared according to my definition of squaring。

Is when there is's a complete graph。Make sense right。

this is like a missing edge and there is like a two half path， then I finish fill in that path。😊，那关系。

做个个。Yeah， so first check if the original G is connected and this is only for connected， undirected。

 unweighted graph。😊，Other questions。So it's also undirected。 you you needed properties out here。

I everything would like like work our。So it's not clear。 So in this analysis out here。

 I said all its neighbors must be at most three。你实好紧哦。So actually， in this case。

 I needed all its neighbors to be at least two。 I don't think this condition would necessarily hold。

If the this edge was， so let me draw something。If this edge was going this way， if it were directed。

This guy could have a tiny level。This guide could actually be you。

So I won't have this property that all my neighbors have high labels。

So this breaks down for directive graph。In fact， I don't know if even for unit weight directed graphs。

We are able to， convincingly beat。啊。Cubic， though， I should check。

This paper of Sel was very interesting。 It was one of those papers where the entire algorithm is in the abstract of the paper。

😊，So， yeah， the paper is like three pages。The abstract says here is an algorithm。 we show that run。

 it correctly computes the shortest parts in。N to the omega log n time。And actually。

 it's even more interesting because apparently Saidel came up with this algorithm while he was lecturing。

😊，In his advanced algorithms class on a paper by a different group of authors。😊。

And he got confused in explaining it。And so he figured this one out。very cute， I really like it。

 and I like the fact how it uses multiplication in like two different ways。😊。

One way to compute this square of a graph。Fast。But the second one is somehow using this idea that oh。

 the local averages are telling you something。About how。The， the label of this guy changes。嗯走。Sauble。

 interesting and unusual。And so I wanted to share this with you guys。嗯。But it also shows you。

 you know， one of the powers of fast matrix multiplication is you never know where youll use it。😊。

number of times where you just like。So it comes out of nowhere。Is is amazing。

 And this is one of those。Okay， so with that， let me stop for two minutes。

 we can stretch and stuff like this。 And then after that， maybe I'll。Until then。

 I'll decide whether I I want to tell you more about short parts or should we just move on to low damage decompositions。

 okay。😊，So let's， let's you know step away from shortest parts a little bit， but not well。

 you know well stay in the general vicinity we will talk a little bit about。A fact that you probably。

Have seen at least once before is the idea of a shortest。Part three。

So what's the shortest part three， whats the shortest part three？You are given this graph G。

And you're given a vertex。And it's， it's a tree in this graph。So， okay， so， so given a graph G。

 again， the same setting as before， It's a graph。 It's a source vertex S。And he is。Short as part 3。

If。The distances in T。Between U and V between S and v is equal to the distances in the original graph。

It basically captures all shortest parts of the graph。

This distance from S to V is actually a shortest path in G。And you know。

 that ditras algorithm actually produces the shortest part。

You can take all the shortest path put them together， you might create cycles。

 but you will realize that some of these vertical fields。

Suppose you took this shortest path from S to U。And this shortest part from S to V。

And these two shortest parts did not。But not disjoint。If they intersect， I mean。

 it could be the case the shortest parts from S to U。And as2 B look like this， That's fine。

But if they actually create a cycle。You can just remove。This one。

The distance to this verortex x has not changed。Because if this was the shortest part。

 this was the shortest part。 I mean， both of these must be shortest parts to x。

So shortest part three。 you know what the shortest part。

And we can find short parts trees in linear time。So question。Does they exist？嗯了。All pairs。

 shortest part。So what do I want I want a sub3 T of the graph。

Such that the distances in3 t between U and B are equal to the distances in G between U and B for all U B。

In the vertex。So。No， I mean come on， what am I talking in the bar？个人。Whats an example。Yeah。Hang。

So what can they do？我见啊。Any tree looks like this and then we are wrong on these。Does that exist？诶。

Approximate shortest part three。What do I mean？That the distance is in T， Oh， by the way， okay。

So T is a subdra of G， right。Distances in T can only be higher than those in G。Because， you know。

 every path thats in T is also the。Okay， such that distances in T are at least this and the distances in T between U V are at most some factor alpha times the distances in the graph between U。

😊，Well it depends on what alpha， if I take alpha to be you know some large quantity， then maybe。😊。

关的 the那个小。I'm sorry。是。What are you talking weren't me？OhYeah， oh funny。I like it。呃。So， you know。

 here's the fact I can， you know， maybe I leave it as I exercise the MST。I。And alpha， approximate。

A B SB3。我们。As play equal plus n minus1。It's you know， alpha equals 10 -1。 And it's there。

 I don't like it， though。Can I do better？ No why consider an cycle。

These two guys used to be a distance one。 now I distance n -1。This is tight。哎。This is。那这个。嗯。

But suppose a person can hope。Suppose I， you know， suppose I had an alpha approximate allpa shortest part three。

 I could solve all kinds of problems I wanted。😊，喂。So let me， let me just look at。嗯。Okay。So examples。

 application。I want to solve the traveling salesperson problem approximately。On ametric space。

You guys remember what the traveling salesperson problem was。You know， there's a metric space。嗯。

Which Ill write as a bunch of vertices。And distances。Okay， you know what？

I'm going to write it as a graph。I'll call this a metric。知。What is this， It's ver seedss and edges。

 and the edges are you know， edges are。Vtic vertic C is choose2， So every possible edge is there。

And the weight of the edge UV is itss you know distance。It okay， forget。 it satisfies。W。

 I J is less than equal to W， I， K plus W， K， J。What all I J。It's a complete graph。

Distances on edges， they satisfy the triangle in。It's a metric space。

 but I'm calling it a graph just because I need a graph somewhere。Okay。I want to solve。

 I want to find a small tour in this。A short tool。So have this good。Now， suppose。

I had an all pay shortest， part。没。Which was alpha approximate。冇。O。My claim is。

That I can find an alpha approximate。Traveling salesperson tour on my original matrix on my original matrix。

Its a clean。Actually， let me give you an algorithm。So here is， here is。One thing I could do。

I have this street tea， right？Suppose you asked me to do a traveling salesperson tour of this tree。

 what should I do？Yes。That's exactly。And then start from there， I'll do an Euler tour of the tree。😊。

So call this tour the tea is already taken。 What's a good letter for a tour。嗯。啊。因会吧。Fact 1。And let。哦。

Be the optimal tool， opt ESP。Be the optimal tour。 use a different color。那对。How are we doing。

 How are we。This is the optimal to。So suppose， suppose I visit all the vertics。

knowSo the length of this is opt， right？Suppose I take exactly the same tour in tea。What is its land。

So， length。哦哦。And G is off。I'm using opt have both the cycle and its length。

As long as you're not confused。Therefore， what is the length。Of off。And蔽。What facts do I know about？

对出现的本。At most alpha times。O。This tool that I found。On the tree。Is the best tour for the tree。Okay。

Therefore。The length。好发。In the treat B。Is at most。How four times。Here is the tour。

Of land at most alpha absorb in the treaty。This was the best tour on the treaty。

So its length is at most alpha times。Okay。Does this make sense？Have I lost you guys。Now， R is a tool。

 R is visiting some vertices， right it withs this vertex and this one and this one and this one。

 and you come back to this， this， this。😊，I is a tour。In G as well。

You are visiting vertices multiple times， who cares？😊，What is its length。At most。

Lent of R and T is at most alpha。So， I found a tour。Whose length is that most other potential？O。

So I said， well， if horses could whistle。😊，Then some very good things would happen。

But then I already showed you that， you know， the alpha is very poor。Horses can't whistle。

 or pigs can't fly， whatever。So I assumed something that， you know。

 there was a small alpha approximate AP 3。And if there was a small one。

 then I would get a very good tour out here。 but I know that only crappy tours it。😊，好。

So what should we do？We should do something smart。And the smartness。Is。Yeah。So actually。

 there are two，2。Tricks that you two， two approaches that you should always try whenever youre stuck in a problem。

The first was approximation。We just try back。Can somebody suggest a second one。Thank you。Okay。

So here's what I'm going to do。I going to say， does that exist in approximate？Randomized。

All pay short。What does this mean。This means I'm going to generate a random tree。In particular。

 it means you know， the thing that you should keep in mind is I'm going to have a randomized algorithm。

That takes in the draft G。And outputs。 And it also takes in some random coins。It flipped some coins。

And then it outputs a 3 P。And this T is a random variable， right。With what properties？So。

 the two properties I last for are that the distances in the tree are at least distances in the graph。

😊，哎。They expected。Distance in the tree。Is at most alpha times the distance。嗯。

We take any two vertices， look at the expected distance where the expectation is over the random  tree。

😊，我从来这觉 that have been good。Absolutely。It's going to happen for any tree。

 So it's happening with probably one。 absolutely， it's not。Now， I can ask the question。

 how does this improve。Does it improve。です。Okay， so suppose I had this thing。

 Now let's do that thought experiment。😊，Suppose I had such an object。What do I mean。Yeah。Okay。

 so I know that the length of opt in G was opt。So the length of opt t is at most。😊。

And now I can use linearity of expectations。I can use linearity of expectations。

Every hop that I took en opt。Stresched by alpha in expectation。And so the length of R and P。

Is at most you know the same quantity as alpha times soft and it's all now an expectation。😊，我就是。

Somehow， the expectation just filters。So it's great if you can maintain distances in this sense。

 in expectation we are in rate。😊，And so the question you should ask is， well。

 can you get a small alpha？So now that we've checked。Well as Carlson said， look。

 you know we should make sure that this is a useful concept for our application。 It is useful。

 Its okay。😊，嗯。So let's now figure out， can you get a small alpha。If you have a cycle， what do you do。

 right？So let's check。😊，Exactly， so， so lets， let's do this thing。So on the cycle。

Here is how I'm going to produce a tree， I'm going to delete random man。To get the。

And we expected distance。So let's just look at two adjacent vertices U and V。

The expected distance in the tree between U and V is exactly one over n。Times n -1。

 There is a one in n chance that this edge was deleted， and then you have to go all the way around。

Plus。If it wasn't deleted。千你百万。And this is2。このぐら。I'm very happy that。The randomization was awesome。

Sa as a here。Now， this is one example。What next？So。

What I can tell you is I can tell you the punch line。啊。And the punchline is the following。

 and we'll explore this next。So you pay them。Okay。说一下。Or today's events is and Friday。

 the other advanced。There exists a random procedure。By。Ces。Alpha equals。

 What do you think is possible。Guees。That。Sadly not。It read really awesome。嗯对。Now。

 the diameter is too weak because is yeah。 So here is what you can achieve order log of n。😊。

And this is best。that in the second， something like it。 that the right thing。No。

 so in this case there will be an unconditional result。

 I'll show you a graph for which any construction must have log and stretch on some edge。你是问你。

は have我 very。これちる。我错。No， so it's going to be a random tree。分据被哪的。

So if I look at a random node and I compute a minimum we get the shortest part three out of that。

So that I can show you examples where that will behave poor。That will behave poorly。

So imagine the following thing。 Let me even show you an example。So I have a cycle out here。嗯。

And let me attach。So this cycle is on n over2 vertics out here。哎。

Let me attach n over to vertices out here。So with probably1 half， I'm going to choose this vertex。

Or one of these vertices。And then the shortest part three will cut。This edge。

So with probably one half this these two vertices will get a stretch of n over 2 minus1。😊，那这个。

So I need to be a little more careful。 This example already shows me something。😊。

Another sort of question that people ask is， what if I take a uniformly random spanning tree of the graph。

So then there are two questions。 Firstly， can use sample from the distribution of uniformly random I mean。

 can you sample from the uniform distribution over all spanning trees of the graph there could be n to the n minus2 spanning trees right Kelly' theem。

Can you sample from that distribution， the answer is yes。If you maybe towards the end of the course。

 we willll cover that。Okay， you have a cl with like infinite wave edges and one spanning tree that has。

We wanted to okay， almost certainly。来意思。But see， the thing is that， you know， if you have。

 so you're imagining that this is my weight one edges and all the other edges are infinite weight you have weight one。

the everythingIf you take take that's a very good point So one could ask the question。对。嗯嗯。

So what did I want to say， let me think my whatever， why I needed a sophisticated example。

 You're absolutely right。 That seems to be a bad situation。嗯。对你今日。Good， so in any case。

 the question is clear I want a process to pick a random span tree。Such that。

Things are stretcheded only by alpha and expectation。Yeah。So since I'm out of time。

 it seems like a good time to stop。But next time I'll show you how to do this。

 I'm not going to show you the login。It requires a little bit more effort than， you know。

 I don't know if the extra information actually will teach you something sort of more generalizable。

 but I'll teach you how to do polylo log square。And that will so the next time we will talk about something called a low diameter decomposition。

And then we will see how a low diameter decomposition immediately gives you log square。

That will be on Friday。 and I'll see you。