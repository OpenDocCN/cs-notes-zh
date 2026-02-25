# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P13：lecture 13.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/2dc53773fb17b1ef743af88313f761a9_0.png)

Welcome， everyone。Let's。Startat。Today we'll talk about a problem called sparsis cut。And。

And we'll see how embeddings into L1 or metric embeddings are very closely tied to this problem and we'll use that to construct an algorithm for this problem。

Okay， so。U。So。I guess let's start by talking about graph expansion。So。So graph expansion。

 expansion of a graph is。Measure of how well the graph is connected。



![](img/2dc53773fb17b1ef743af88313f761a9_2.png)

And。You know。So you know let's say you have a graph G。

 which is like a bunch of vertices and edges and let's assume that the graph is unweighted and whenever we want or I guess for all the time we can assume that the graph is also dregular。

 meaning all the edges are all the vertices of degree D。

Just make some definition simpler to work with。 Okay， so you have a graph and。

Let's say you have a subset of vertices in this graph。Okay， the expansion。Of the subset of vertices。

F of。Is the number of edges that cross the set。So the number of edges from S to S complement。Okay。

Of course。You want to divide this by the。Total number of edges incident on us。

So I can write it in a couple of ways， so you can let's just call it the volume of S。

So volume of s is the total number of edges incident on S。So if you have a degree D graph。

Then the volume of s is just d times。The cardinity of rest。So in a degree graph。Expansion is。

Just the number of edges going from S to S complement divided by D times the cardinality of s。

In a direct graph， and in general， you would replace the denominator by the volume。Okay。So。

What is this measure， Well， this measures the you know， effectively it's a ratio， It's a ratio of。

All they just leaving us do by all age is on incident on us。Okay。

 and another way to say the same thing is。This is effectivelyual the probability that。

If you pick a random。Vertex in S。You put a random vertex in S。

And you start at the random vertex and you take one step。这个燃灯。Edge out of the verex。

Take you take a random image word Uv。And。The question is whether you leave the set。

It's a priorityty that。You leave the same。As in V does not belong to us。

If you start if you start the random walk at。At a vertex in S and you take this one step。

What is the priority that you leave the set， that is what we call Phi of S。Okay， and。Yes。

 it's a number between zero and one。For every set in every graph it's a number between0 and1。Okay。

And here when we say D regularg， we're just saying that the degree of every vertex is exactly equal to D。

嗯。So it's a simple case and it's sort of deregular graphs sort of have all of the complications that you see when you try to think about expansion and most of that we talk about today can be generalized to general graphs。

Okay， so this is an expansion of a set in a graph and then the expansion of the graph itself。

Or you can call it the it's also called conductance of the graph or sometimes people。

 let's say expansion of the graph is basically the minimum value of。F of S。

Over all sets of utmost N over2 vertices。Okay， so you know。

So why does this sort of measure connectivity let's look at an example right so imagine you have the let's say the complete graph for instance。

 so let's say this is the complete graph on in vertices。Okay。no。If you pick any set。お使。おさイズ系。

Which is smaller than an over2。Okay what is the expansion of the set well it is the probability that if you start at one of the points inside and you take a random outgoing edge the probability that you leave it you leave the set so。

If you depict any set of size k， you pick a point in， there are k minus1 edges。

There are k minus1 edges into the set and there are， I guess。The rest of the ages。N minus k edges。

Going out。Okay， and so the probability that you stay。You leave the set is。

N minus k divided by the total degree n minus1。That's the probability that you'll leave the set if we get random vertex in and so this you see that it's like at least a half。

So in a complete graph， every set has expansion at least half。

And I guess the sets that expand the least are the set of size half like if you had a set which is。

Roughly half the vertices or exactly half the vertices in the graph。

Then you have about a half pro chance that you'll leave the set。When you take an edge。 So。

 so this is a。I mean， this is been some sense the best expander you can have it is the most highly connected graph。

 so this is probably this is the best。Or the I shouldn say best。

 this is called the highest sort of the highest expansion that you can have。Photograph。

In any other graph your expansion will be local。系。And you know it。You know。

 if you look at a little another graph， let's look at some other graph， let's say you look at。

Look at a grid。Okay， so you look at n by and grid。电。诶。There are pretty。

 it sets at very low expansion， for example， if I。Cut the grid in the middle。

The number of crossing edges is only n。the number of crossing edges is only n。

And the volume of the left hand side。The number of edges on the left hand side is about n squared。

it's a乜嘢。It's about n squared， so omega n squared。Okay。

 so the expansion of this set is like very small， it's 1 over n。So it makes sense。

 but the grid is not as highly connected as a complete graph。Right right。And so this。

Like this is actually a better notion of connectivity than if you just did mean cut。

If you did min cut， for example， if you did min cut in a graph like the grid。

The mint cut will always be sort of itll take out one vertex on one side and everything else on the other side。

It'll just say。Minard will always look like this。Take one vertex and everything else on another side because you only cut two edges or something。

 and in fact， in any deregular graph like a min cut would probably be like a single vertex from the rest。

And that's that is the minimum number of edges you can cut。

 but it doesn't reflect the connectivity because you're only separating one vertex from the rest。

 so it doesn't affect so many other right。And so this is a better notion or this notion is more useful in many contexts。

 I should say。Okay。Okay， so so so we saw the grid and we saw the complete graph you know you can try many of different graphs。

 you get you know different values of expansion and you know。If you could ask。Okay。

 so complete graphs。Are I guess the most well connected graphs。

The most well connected graph in some sense。So。Is there。

But the disadvantage of a concrete graph is it has too many edges， it has like n squared edges in。

Like how many edges do you need to have the same kind of connectivity as a complete graph？Okay。

 same kind of connectivity in terms of this process cut。 Okay， so in particular， let let's you know。

An expander graph。嗯。Is the following， so it's a graph g equal to V。

Such that the degree is some constant。So degree of。All the vertices is some constant。Let's say three。

 right， degrees  three。Okay， can you have like a degree3 graph such that the expansion。

Of the graph is at least some other constant。Okay， so if you look at our grid， for instance。

 our grid is actually a degree four graph， it's the kind of sparse graph you're looking for。

It's very sparse， it's very few edges， but it's actually not well connected。

 as we saw the expansion is one over M。And what we're looking for in an expander graph is a graph which has only like degree three or something like that。

But we want its expansion to be omega and meaning its connectivity is just like the complete graph。嘅。

And。You know， these things exist。 These are， in fact， if you pick。They exist。

 and you know if you pick a random deregular graph。If you pick a random D regular graph。

 let's say even let's not even say D， let's say you pick a random three regular graph。

It is an expander。With high priority。Meaning its expansion is at least a constant。Some constant。

So that's good and in some sense they're abundant and in fact there are very very explicit constructions of expander graphs。

 so here's an explicit construction of an expander graph。So。So you take your vertices。

A01 through p minus1。For a prime be。Pick a prime number and make0 and through p minus as one as yourtices。

And。Connect your edges。Are going to be。The following， So you connect x to。Like every word takes X。

Is connected to x plus one。X minus1。Moret p x plus1 more p x minus1 more p。And。1 over x smartp。F。嗯。

This big three。嗯。Okay， and the vertex0， you can basically do anything with it， you can。I mean。

 one over0 doesn't take this so， but you can connect it to。嗯。

I guess you can create a self loop basically what it doesn't matter what you do at vertex zero you still get a constant expansion so。

So this is a you know。A very simple construction of a three regular graph。

It is three regular basically it looks like a cycle because x plus one and x minus one。

 so if you put all the numbers0 through p minus1。In a cycle。Right， so this。Yeah。是。

So this connects x to x plus1， x minus1 and x plus1。Okay， so we have the cycle。

 and then you had to connect you to put a ch from x to 1 over x。

Okay and so that's a nice graph and you know it's expanding and but you know this is just one construction there are lots of like this is from I guess the 70s or something and there are lots of constructions of this in these graphs now and there's a lot known about these graphs and they're very very useful in algorithms。

You know， routing shortest path computation， spectral lap plus in solvers all over the places like lots of algorithms use graphs。

 expander graphs。And。嗯。And of course， there are a lot of work on this you know。

 literally books written on expander graphs and their constructions and algorithms and so on。Yeah。

 we'll see a little bit more of expander graphs later in this class。

But I just wanted to show the expander graphs here because we're talking about expansion。 So in fact。

So today we look at the problem of given a graph， can you compute phi of G？

That's the problem we to look at today， given a graph。G， can you compute P of G。

Or approximate P of G， since computing P of G becomes NP complete or NP hard。

 can you approximate P of G？So you just want to know how good an expander how good an expand what is the expansion of your car？

对。O。Yeah。Right there's a questioning right can1 over x be equal to x plus1 or x minus1 Yeah actually I don't know。

 it's a good question。Maybe you have to pick a prime p。

 which is a mod 1 mod4 or something like that to avoid such a like there might be some modularity construct constraint on p like basically you're asking whether x is equal x plus 1 is equal to1 over x mod p so this is the same as asking whether x squared plus x minus1 mod p has a solution and whether such a quadratic has a solution usually depends on。

With这。B has a。Some one more， one more four or things like that。Yeah。Yeah， and but yeah。Yeah。嘅诶。Okay。

 so。Right hopefully well come to at least a few applications of expander graphs they're all over the place in complexity theory algorithms and all over the place。

 like even random bits， random walks and all sorts of places。We'll see a lot more of this， hopefully。

Yeah。来。Yeah， actually it is true that you can have x plus one equal go to1 over x only at four values of x and similarly the other one can happen only happen at four values of x。

 but two values of x and here and two values of x here。Yeah， so yeah， I don't know what。

 whether they treat it special or what do they do there。Okay， okay。

 so this is about expander graphs and you know like if want to even given a graph know that it's an expander。

 we need to be able to approximate p of G and let's see how to approximate p of G。Okay， so let's。So。

So let's write down what phi of G is， so phi of G。Is the number of edges。From S to S complement。

 he divided by the。volumeolume of S or。Let me think of regular graphs for now。

 so let's say this D times cognitive phase。So。SoYou know。

 we're going to be talking about metrics and so on。 So you know the numerator。

Is the is sort of the edges。 So that looks like pairs This is about。Ps of vertices。

Right so that's nice the denominator on the other hand doesn't look like it's talking about pest。

 it's talking about individual vertices and you're adding up the this is talk about vertices。

So it's actually for solving this problem and it's actually nicer to look at a slightly different quantity。

诶。So let's let me call that quantity psi of G。Okay。

And what we'll do is we'll have SS bar on the numerator。In the denominator， instead of just having s。

 I'll have S times S bar。OkayS times as per so what does this look like well the numerator is of course pairs of what pairs of like it's the edges in the graph。

 right？You could say the numerator is edges between S to S bar。In the graph G。

Is the number of edges from SS bar in the graph T？Okay， and the denominator。Well。

 you can interpret it in many ways one way to interpret it is it's the number of edges between。

StS bar in the complete graph。The number of phases。Between S2 S bar in the complete graph。

The number of pages in a complete graph is just the product of the size of the two word。Whatex。

 such S timepar is new。So this quantitysi of G is directly comparing the number of edges in between S to S bar and G to number of edges between S2 s bar in the complete graph。

And。So， so this is a slightly different quantity， but。You know， these two are actually not。

Within the constant factor of one another。Or within a fixed alone。Let， let's。那个。I should say。

Within a fixed factor of one another， up to constant factors。Up to constant factors。

 approximating phi of G is the same as approximating psi of G。Okay。

 why is that well note that we are only interested in expansion of sets whose size is smaller than N over2。

Alway the size of the set we care about is smaller than N over2。

 and this is for the simple reason that if I if I have any cut。

Like in the graph like I'm cutting the graph I should divide the number of crossing edges by the smaller side of the cut if I divide it by the larger side of the cut。

 of course I'll get a really small value so I need to divide by the smaller side of the cut So S is always less than n over2。

So if s is less than n over 2， always less than N over2。

The size of S complement is always a number between n over 2 and n。

It's at least and over2 S complement and it's at most end。Okay， so therefore you know。

Dividing the by S complement on is is。You know， it only changes the。

Quantity by either like some number between n and N over2。

It's always some number between n and and over2， so you can say it's within like approximating psi of G is the same as approximating phi of G。

But if you want to make it fully precise， what you could do is you could also put in another end here。

For example， you can put in another n n times this， you can call it look at n times this。Okay。

 so then actually the two p of G and C of G are actually within order one like。

They are within like between half and one of each other。Within within a factor two of feature。ok so。

Because the size of S complement is always a number between n over2 and n。

 and so size of S complement divided by n is always an routine half and1。

 so it doesn't really make a difference。All right， so let's look at this different quantity now。

And again， write it in a way which is。Kind of nicer。 So I say。So we're asking。

 what is the number of edges？In ES complement divided by the number of edges。嗯。인 인지。

E is between S and S complement。Number of pagess from。S to S complement in the complete graph。Okay。

 let's call this site。Okay。系。Okay， so now okay， so now okay now how do we approximate this？All right。

 so now this we want to， what do you want to do， the real space we are searching over is the minimum of all sets as。

Okay， that's the real space we're really looking for。You know， let's。Look at this collection of。

Objects， we know what these collection objects are， like when we in fact。

 we started talking about cuts。A subset， we were talking about S and v minus S。

As and as complement is basically a cut。Okay there are two to the n cuts and we want to minimize this Okay。

 so let's write this in terms of cuts。Okay， so。You know， that leads us to the notion of you know。

Cut metric。Right， so。This is just the observation that， okay， suppose I have a set and。Of vertices。

If you look at the indicator。As of。Oh。V， this is the indicator that v is in1 if v is in s0 on the other side。

F otherwise。So this gives me an embedding onto the line。

Of the graph onto the line and the it induces the metric， which is a cut metric。

So what is the cut metric， the distance？Between two what is U and V。Is just。

Inddiicator S U minus indicator S b。This is a cut metric。Let me call the distances。Right。

 so it's just that。嗯。Distance between any pair on the same side of the cut。Is zero。

And if you cross the cut， the distance is one。And you can check that this satisfies the triangle inequality it's a metric。

Okay and so in terms of that， if I write this psi of G。Rightsi of g is minimum overall S。

Of the following quantity， the numerator risk。Like some of distance service。Of Uv。

 some or all it is Uv。Divted by some are all pairs UVv。Distance service of Uv。

So just to recall distance sub as as indicator S of u minus indicator S of V。

This is also indicator S of U。Minus indicator recipe。Right， too。So this is what we want to compute。

So we want to find a cut metric。Such that this ratio of these two distances。

 sums of distances is minimized。Okay， and instead of saying you come a V in V， you know。

 you can also say you come a V and we choose two， which is every pair， right？Okay。

 so this is what we want to minimize。Alright， so now the。The natural idea is， well。

 you can't work with cut metrics because they don't look。I mean， they look quite complicated。

 you know， because they are 0 one value right like these are 0 one value then you know it's。

Functions that you want to minimize over。 It's quite complicated。

 So let's just try to find some distance function on the set says that this ratio is minimized。

some distance function doesn't matter what， so let me write a linear program。

Here's a linear program for the expansion problem。So what is this linear program going to be for Ps achieved？

So you you find。So， minimize。Okay， let me write out what you find。

 you want to find a distance function， so what is a distance function， some function。D。

 like basically。Distance between every pair you want to solve for a distance between every pair。

So so it satisfies all the metric conditions distance from u to u is0 distance from u to v is equal to distance from v to U。

And distance from U to V plus distance from B to W is at least the distance from U to W is a triang inequality。

Okay， so no note that all of these are linear constraints so we are in good shape so far okay now we want to really minimize the ratio of these two distances right so that doesn't look like a linear program。

Yet， but。Because it's a homogeneous ratio。Instead of minimizing the ratio。

 ever if since everything is homogeneous， let's just fix the denominator to be at least one。

And minimize the numerator。So I'm going to fix the denominator to be at least one so I'll say some or all pairs Uv of D UV is at least。

one。是。That's the denominator with at least one。And now I will minimize the numerator。

Which is some only the distances on the edges。Okay， so now we have a nice linear program。

If we solve it we'll get some distance function on the graph。That minimizes this ratio。嗯。Okay。

 so let me go again got how we converted this ratio minimization into this LP。

So we want to minimize this ratio。And note that the ratio is homogeneous。

 meaning I can scale all the distances by a constant lambda， the numerator and the denominator。

 the ratio stays the same， so what we do is by appropriate scaling。

 we can just make the denominator at least one。Always。

 and then once you fix the denominator to be one。The minimizing the ratio becomes the same as minimizing the numerator。

So you put the deator at least one as a constraint and you minimize the numerator。Okay。

 so that gives you。Like you solve this LP and you get a solution distance function。All right， okay。

 that's good。 Okay， so now okay， this is all well and good。Now we want to。诶。Like， you know。

 round this LP solution， meaning we get an arbitrary distance function， we want to get a cut back。

Okay。So。How does one round it？嗯。Well， so basically now the problem is you just have a distance function date。

You just have a distance function D。A metric D on your。Graph。And you want to round it。

 get a cut out of it。Okay， a cut。The subsid this。Aactmetric。Okay。

 so the way well round it is we'll embed this distance function。是。Into the L1 metric。

On sum r to the K。I should say little L1 metric， basically L1 metric on r to decay K。

And from an L1 metric， you can get a subset。Yes。Okay can。Around L1 metrics to subjects。 in fact。

 this is。These two are essentially the same。Ln matrix and cut matrix are the same object。

Every L1 metric is basically a convex combination of cuts。

You can will see this I mean hopefully we'll see this today or maybe a little bit on it's very easy to see that every album metric is actually a conx combination of cuts so these two are essentially the same。

嗯。Okay， we'll defer that proof for now instead， let's go to the more interesting part of the proof。

 which is。This part okay， now you have just a distance function on n vertices。

 How do you em it into L1 with as small a distortion as possible。

 you want to keep get very low distortion here right。In fact。

 what we'll get is we'll get login distortion。In the distances。

 meaning multiplicily the distances will be off by a factor log n。

 which means you'll get a log n approximation to a problem。Okay， so。All right。

 so that's the that's the plan for I guess the rest of the time today。

 so it's going to be this if you this is going to be this fairly independent question okay。

 here's the independent question theorem we want to prove。If you give me any endpoint metric space。

 every endpoint metric。Embbeds into L1。嗯。With order log and distortion。Okay， that's the the proof。

 So for now， I mean。From this point on， you can forget about graphs for the rest of the lecture。

 it's really this question you have some distance function。

 arbitrary distance function and you want to。Put it inside art like some r to the K。

 some real space with the L1 distance between them。Okay。Okay， so how do we do this？

It's actually really nice。Very nice。Embbedding care。

So let's start with something which is very simple。

 so here's something called the freshre air embedding。Which is going to be like a building block。

For our L1 embedding。 So what's a fresh embedding。 So let's say give you some some distance function D。

Okay， so look at the following。Embbedding， I map， I pick。Some subset of my set space。Okay。

 fix some subset， fix some subset。Then。You map， consider the map。I guess let me use the letter F。If。

That maps a vertex v。In the。Maps a point let me use x mapps a point x in the space to。The distance。

From x to the set a。So this is a point on the real line。

So F is a map from my matrix space onto the real line。

It just maps my distance onto the real line and the map is just given any point。

 just map it to the distance from the set。 Okay， and distance from the set and I'll write on the definition。

 but。It's basically what intuitive you think about， right？ I guess yeah， I so distance of。

A point from the set。Is defined as you look at every y in the set。

And you minimize the distance from x to y。Right so it's like if you had。Actually。

 this is an important thing right so if you had， let's say。Some。Region like this， this is your set。

 then if I pick a point X。Then it's the distance。From x to the nearest point in a。

 I think thatll be this this would be distance from x to a。ok。Yeah。Yeah， you could add in a graph。

 it would be the shortest part say basically in any metric space， it's the closest point。

I the distance to the closest point in a from x。Okay， and note that so now we have a map。

From any metric space， give me any metric space at any subset of it。You get a map。

From that to the real line， and it's just this simple thing distance to the set。Okay。

 now this embedding has quite a few nice properties。Here's a property one。

Freer embeddings are contracted。Meaning they don't expand distances， they only contract distances。

 so what do I mean if I pick any pair of vertices x and y in my space。Okay。

 and let it be any subset a。Any subsidy。Okay， so for all A。

The fresh emdding corresponding fresh embidding is a contraction to any pair of points。

The distance from F of x to F of Y。Is at most the distance from x to y。

So this distance distance from f of x to f of y is basically as we defined it over the real line。

 it just a distance from x dx comma a minus dy comma a。

And we're saying that that is at most d of x comm y。ok诶。系。嗯。Yeah。

And this is a fact that's true in any。Another themetric space。Always。For all metric spaces。

 it's a property of a triangle inequality and it's。

I won't let me not try to prove it it's sort of something it's bad。

It should be intuitively clear why this is the case， right？一。If there is a point。

 look at d of x comma a if the minimum is achieved at z。

Then d of xz minus d of yz is at most d of xy， that's strality。So we。So basically， if I look at it。

 for example， if a was a single point， let me do that case okay。If he is a single point。

 I claim that this is true。Why is that， well， it's because of the triangle inequality。Right， because。

Well， you know。This is just a triangleality。Okay， so so this is nice。

 so fresh air embeddings never expand distances， they only contract distances。ok。ok。

So let me know if you have any questions about this fresh handbeddings。Because we'll use it so it's。

It's really an embedding of any metric space onto the real line and you have a lot of freedom。

 you can pick any set of the subset of the metric space。

 you'll get some corresponding map onto the real line。Okay。

 so now what we'll do is to construct our embedding is we'll actually pick subsets randomly。

And we'll use them all to construct this embedding onto L1。系。

So let me call F sub this fresh embedding for subsidy， it's maps X to distance from x to A。So。

All right， so let me。Okay， let's look at this embedding。 This is embedding in tail 1。

 So this iss got it's。Call bullin I bedding bullga。Constructor。Okay。

 so now what's the situation you have a metric space。O， actually， I've been using V today。

So we are going to pick random subsets and we look at distances to that subset。

Okay so here's what we'll do。Well pick several random subsets。

 So let me start by doing it for T equal to。1 through login。Okay， construct the set。A of B。

As follows。In A of T， you include。哦。对嗯。It'll be for each。啊喂。In the space。You include。

Y with probability1 over 2 to the t。Okay， so here。You know， a sub1。就。A sub one。Okay。

Consists of points like you pick every point every a sub1 is constructed by picking every point in already a half。

 So you should think of a sub1 as like roughly half the space。

Every point is picked with probably a half inside a sub 1， okay it has density about a half。

Okay and a sub 2 has density about a quarter。Each vertex is included with the probability1 quarter and similarly。

 a of 3 is included with priority 1 over8 and so on。

Okay that's the picture here so you know and S of T every point is included with priority1 over2 to the log n。

 which is one over n， which means that you're probably including just one point in the whole set。

Okay， and that's the。嗯。Okay， that's the way we are constructing these random sets。All right。

 so so then okay， now that we have these random sets。Our embedding is going to be。The following。啊零一点。

Is going to be capital F。Will map a point x。读。Distance of from x to a1 comm distance of x to a2。

The distance of x to 8。Okay， so this is a。Like a log n dimensional vector right now。

So right now we have an embedding into art to the login。And it's a randomized em right now。Okay。

All right， so so this is。Bo games and and let's see what distortion we get here。好。Okay。

 so what is the distortion we'll get？So firstly。嗯。Like here's a claim。

 if I look at the distance between F of x and F of Y， the L1 distance between F of x and F of Y。

I claim that it is at most like log n times。The original distance。Pretty next and why。

Right with Pro T1， actually。With probability one。Always， this is true。

Okay and this is for the simple reason that if I look at the L1 distance between x and F of x and F or y。

Right， of course， that is actually the sum over I equal to1 through log n。Of the。

Distance in the corresponding fresh embedding。RightAnd we just saw that every one of these fresh embeddings is contractive。

 so each of these terms at most distance from x to Y。And so log n terms， therefore。

 this is actually log n times。The distance from X to white。He said， that's nice。

 so we have an upper bound on the distance。What's really important is now we need to prove a lower bound。

So well prove the following。Cam。Like well actually show that。嗯。Since right now it's a randomized one。

 let's just prove a randomized claim the expectation of the。L1 Nom。Between x and y is。

At least some constant some constant times distance from x to y。Okay。

So this is right now not exactly what we want from an embedding in an embedding we want。

All the distances to be within a login ratio simultaneously well get that later right now we'll just get all the distances between Fx and Fy between every pair is in expectation at least。

The right out of magnitude。So it's within a log n factor of the two distances。ok。Okay。

 so this is the key step， this is the key claim that we'll prove。Okay。

 so how will we prove this claim let's。Right so。So。You know， to understand what's going on。

 you have let's say you have some point X and you have another point y。Okay， and。啊。嗯。Right so。

You imagine I drew a ball。Of some radius。A little la around it。And through another ball of radius。

Let's say capital around this。ok。ok。So imagine that， okay now basically when I pick this AI。

And he said AI， a particular saidI am actually picking points randomly right so randomly Im picking picking points。

Okay。So suppose。Suppose。Yeah。Doesn't contain any point。Within a distance。Capital R。From why。

Like it doesn't pick any point inside this ball。Get no point inside the green ball。But。E。Pixs。

Some point inside the lift。Other ball。It picks a point here where it doesn't pick any point here。

Okay， when that happens， what what happens when that happens well， the distance from。

W to AI will be at least capital。Because it didn't pick any point inside this capital size ball。

And distance from x to capital I。Would be utmost littleer。Because there's some point inside here。

 so therefore。You would end up that the distance of y to AI minus distance from x to AI。

Is at least r minus R。So that's how we' will get a lower bound on。

These fresh air embedding distances。Will sort of。Consider or look at balls of different radius and we look at the event that AI picks a point in the bigger smaller ball but does not pick a point in the bigger ball and if that happens with significant probability you'll get a contribution to the fresh air embedding distance。

Okay， and so now， you know， okay， so now。If I have a ball of radius capital。Let's say。

 let's look at AI AI picks every point。With probability 1 over 2 to the I。Right independently。

So whether AI picks a point inside this ball really depends on how many points are there in that ball。

Okay， so somehow we need to pick these little and big balls of appropriate radius。

So that this happens right like the event that you're looking for happens， for example。Okay。

 let's let's pretend， suppose that this big ball has。Let's say it has。嗯。Less than。

Two to the i points。Okay， and this。This little ball。Has a。

I don't know about the same order of magnitude， but let's say at least2 to the i minus1。

 two to the i by two points。Okay， so we have this situation where the big ball has。

At most to the points and the little ball is at least about half the points。All right， okay。

 so now we can calculate the probability that both of these events happen。Okay， firstly。

What is the probability that。嗯。AI does not pick any point。Inside the big ball。Well， it is just。

each point in here is picked with probability1 over to thigh。

So this is exactly1 minus1 over two to the I。To the power， the number of points in there。

So probability that AI doesn't pick any point inside a ball。Is actually 1 minus1 over2 to the I。

To the power， the number of points in the ball。That's basically because every point is independently included with Pro 1 over2 toI in AI。

ok。😊，Right now。So right now we just said， oh， the number of points inside this big ball at least is at most true to the eye。

So therefore， this is。At most。So this is empty。We're looking for this empty right we're asking whether this is empty and that's this。

This is at least。1 minus 1 over 2 to the I。Hold to the two to the eye。ok。Yeah， and。You know。

 this is a you know if this is like a constant。It's like point， I don't know，1 minus1 over E。

Right it's let's say half。Something like a half。At least to half。Or maybe even one， let's。

 let's at least a quarter just to be sure， Okay， one minus I think a quarter is probably okay。

 at least a quarter。Allright， so this happens with constant pro。 All right。

 so now what about the other key thing， you're asking what's the priority that AI intersect the other ball X comma little R is。

Non empty。Okay， so it's sort of the same thing， but one minus that because you're asking for non emptiness。

 so it's really one minus。1 minus1 over 2 to the I。Hold to the power。

 the number of points in the little ball。Okay， and well， what is that， That's again， you know。

1 minus。1 minus1 over2 to the I， the number of points in the little ball we said is at least2 to the I over2。

number of points of little is at least2 the I over2， so I'm going to say2 to the I over2 here。

So you get least。And again， you can see we have chosen these numbers so that both of them are like a constant。

 this is at least a quarter。Okay， and。So with constant probability。

You won't pick any point inside the big ball with consempity。

 you will pick a point inside the little ball so therefore。With constant probability。

You would have this distance to be at least r minus R。Okay， so let me， you know。

 I sort of improvised on these statements as I was writing it。 So let me state a claim。

 which is which should be sort of make the whole thing clear again。 So here's a claim。 Okay， suppose。

You have two points such that。Like， be of。The size of the number of points in the little ball is at most2 to the eye。

我 do。Okay， a number of points in the big ball。I'm sorry。

Is at least true to the eye over2 is at most true to the eye。Okay， then。With constant probability。

The distance from。X to AI minus distance from y to AI。Will be at least r minus R。Okay。

 and if we instead of talking about probability， if we talk about expectation， you'd conclude that。

And therefore， expectation of the distance from X to AI。Minus distance from y to AI。

Is at least some omega 1。Times r minus0。Oh yes， thanks， this is B of White God。嗯。

Okay so that's a very basic claim okay so now all we need to do to finish our proof of this result is that this claim is very existential I'm not saying what this capital are is。

 what is little r is I just said suppose there is this you know this is true so we just you know construct this raI explicitly。

Get to finish a approval。All right， so what are the RaI？So。嗯。Okay， so here are the。

 so let's say you have two points x and y。Let's draw balls of increasing radius。嗯。

So let me call Delta I。Actually， let me use a new page so that。Did I have enough space to say this。

Okay， so later have two points， X and y。And I wanted to start drawing。Circles around them。

I need some space， yeah。X and Y。Okay， let me define Delta I to be the smallest radius。

Minimum are such that both of the balls。With raius little r have。诶。You know。At least took the points。

so。So you have some circle， this is Delta 1。Okay， Delta 1 is the radius at which both the points see1 point。

ok。The smallest radius at which both the x and yc1 point。And then you have Delta2。

which is the smallest radius at which both of them see one point two points and again you write down the smallest radius at which both of them see four points。

And you repeat until。You don't want these balls to start intersecting。So。Actually。

 that's important here， I should say these two balls don't intersect。B of x R。

X little r intersect V of Y commma capital R is empty。

Because we assume that whether you pick a point inside this ball and well you don't pick a point inside this ball are independent events。

 that independent event assumption hold only if the balls don't intersect。

 if the balls intersect the probabilities are not independent。Okay， so let's。

So basically you start drawing larger and larger balls。

 deelta I is the smallest radius at which both of them contain two to the high points until the point where it sort of reaches half the distance when you reach half the distance。

You sort of you stop expanding these。嗯。Balls around。这试。Unless。This are。

Is bigger than half the distance。Okay， if this r is bigger than half the distance。

 then you define Delta I。To be just half the distance。Okay so just a definition once you once the。嗯。

都お。Once the radius reaches DxY02， you stop define this。O。

And so we need to prove that just note that we are trying to prove that non embedability result。

 so we need to prove that for every pair of points in the metric space。

 distance function the distance function satisfies this property。

For every pair of points so dn x and we are two arbitrary points in our matrix space and we are defining these delta I for them so if if X andware are really close by this will stop very quickly。

If they're far away， they'll continue for a while。Okay，Okay， so now， okay。

 so now we are basically done。 So now。Because of the way we have defined it。Right， if I look at。

Delta I。or x。Yeah。飞 look good。你。Delta I or just before Delta I。喂。嗯。Let me just guess before。

Just before， as in as a at if I look at deelta minus Epsilon。Think of Epil as going to zero， Okay。

 Delta y minus Epil。嗯。One of the balls。Has two to the I。Less than two to the i points。

RightBecause that's the definition of deelta is the radius at which both of them have2 to I。

 so just before deelta I hit just before you hit deelta I is a delta I minus that one of the balls has less than two to I points。

Okay。Okay， and if so if I set this to be capital R。And if I set little r to be deelta i minus1。

At deelta I minus1。Both the balls are at least two design minus1 points。All right。

 so then you know by our you know we get we can use our claim on these two balls。

So you would get that。Expected expectation of。The Dx AI minus D Y AI。is at least。

Some constant times this difference。Delta I minus delelta I minus1。RightThat's just what it is， yeah。

Bly。Now add this allI。Adding overall right。You'd get。嗯。The。

Expect of the distance between the two embeddings。The L1 distance between the two embedding。

Is at least omega 1 times this thing adds telescopes。Right， you end up with。嗯。Right， Delta。嗯嗯。

basicallyically， the largest delta minus is the small as delta， and that gives you d of x comm y。

That this is because sum over J delta J minus delta j minus1， this is d of x comma y by 2。

The sequence of delta j， it starts at zero essentially， it goes all the way to distance dx y over 2。

 so therefore you get。O。And you know one silly detail， which。You knowま。

An annoying detail which I pushed under the rug is I said deelta minus epsilon here and I ignored the epsilon really it's for every epsilon right for every tiny epsilon just just before reaching it so I mean the correct way to do it is to define one of them as an open ball。

And the other one is a closed ball。So。In this claim， you define BYR to be the open ball。

Meaning it contains all points whose distance is strictly smaller than capital R。

And be excild to be the close ball。All points of distance is less than or equal to。

And then you have everything else is the same。So we get this embedding。Okay。Alright。

 so so that's good。 Okay， so now we got both the sides of herping and the only okay。

 then the next detail is we， okay， we got an embedding says that。

Somehow for every pair of points in expectation， the distance is right。Right。

 now how do you get it to be？Like truly right for every pair of points。嗯。What you can do is。You can。

Repeatedly sample from this distribution over maps embed and concatenate them。

So we have a randomized map F， right， so let's pick。If one。If to。

Like some really large number of times， let's say I think about logins if your suffices。

 you pick like F you know，100 log n。All of these are maps just like we did。

These are maps from B to R to the login。Okay just the whole randomized construction。

 you repeat it some login times like 100 login times and what you do is you create this mega map f hat。

Which is basically the concatenation of these things， like as a vector。

 you concatenate each of these things。Okay see your entire map is a map into like log squared and dimensional space。

ok。But。That we don't care about the dimension log square in is still small。

 what you really care about is that the distortion is fine。And basically， essentially by。

 concentration。Whatever you had in expectation， like for every pair of points。

You knew something in expectation。For each of these things。

Right this is at most log n times the distance。You can get it with high probability。And in fact。

 you can get it with probability。exponential in this number of times you repeat this experiment if I repeat this experiment K times。

You can get like high probability for that。And then you say， oh。

 there are only n squared pairs of points I care about。要。

You union bound against all of the n squared pairs。to union bond against all the in square pairs。

 you need to pick at least 100 log repeat this experiment 10 log n times。

 but your union bond against this。嗯。I mean， note that actually I should also， for simplicity。

 I can even put in a one over k here。Again in the front of this。

 if I do k repeat experiment k times I put a one over k so now the distance is really the average of many experiments it's basically like you have a random variable and you're taking you know average of k samples of that if you get whatever is true in expectation will now be true in high probability。

And you would have the same you'd be able to。So that。

If you don't lose anything from going to high expectation hybrid。

 the only thing you lose is in the dimension， the dimension becomes larger lock you know becomes。

K login instead of login。And it turns out that this embedding actually also gives exactly the same construction。

 also works to L2。Not just2 L1， but the same exactly the same thing also gives you an embedding from any metric space to the usual Euccridean space。

With the same distort， the login distort。So this was so nice， actually。And because you get it to L2。

 you also get to L1 and all the Lp for any P。For anyP， you can embed to LP。

Space we have by the same exactly the same construction。Okay， so。

All right so so I think I have about two minutes I can actually show you the second part which which I didn't see is actually the easy part I said it's the easy part let me do that so what is it。

Well， it's this question。I have points on a line。Okay， I have the real line。

And the L1 metric on this。How do I get cuts？あるフです。Okay， I need to get a number。

 you need to get a subset as better cut metric。And this this we have done it。

 I think a couple of times， but okay， firstly， you can scale the embedding so that the whole the entire embedding sits inside。

The interval01， just scale it and shift it whatever you do so that the whole embedding sits inside the interval01 Okay。

 once your embedding sits inside the interval01。You can just pick your。

 you pick your set by doing this。 You pick a random。Tresd data。In01。In the interval01 and you know。

If we can random threshold data， everything on this side is s。

 everything on this side is as complement。Okay， and by definition。Theえ。If I look at。The cut metric。

The indicator that you and we get separated expectation of that over the choice of this threshold is going to be exactly equal to the L1 distance between。

The two points。It's exactly equal to that。So you're you know， you get a like you get a。

Distribution or cuts which are distributional subsets such that the distance。

 the cut distance or con cut distance is exactly equal to the L1 distance。

And we did this over a real line， but now if you want to do it or like really。

 we don't do it or r to the K。Okay， suppose you had R to the K。And again。

 you have some L1 embedding there and you want to go to subsets。A cut metric。Okay。

 what you do is you just do the same thing in each dimension separately。So you just say。

Right you are to the K so R to the K is just。L1 metric in not the case is some。我。You know。

L1 metrics in each of the dimensions that you have。

It's some over k copies of in each of the dimensions。

So what you do is you pick a dimension at random。And then in that dimension。

 you do this operation that we just described， you'll see that the probability that UN andV are separated is directly proportional to the L1 distance between UNV。

because it's just the sum everything adds。So you can get a randomized map that takes L1 metric in any K dimensions and map it to a cut metric。

I got distributional cuts。And that's how you get this log an approximation， you solve the LP。Yeah。

 I guess first you solve the LP， then you do this boin embedding。

 which is very simple randomized procedure， you pick these subsets。And then you do cuts on it。

By this threshold cuts in each dimension。And you get a login。One of these sets that you get。

Will have will be within loggan factor of the。ああ、ミニマ。The minimum being， the minimum value of they L。

嘅。Thank you， professor。Thank you。Thank you。

![](img/2dc53773fb17b1ef743af88313f761a9_4.png)

![](img/2dc53773fb17b1ef743af88313f761a9_5.png)