# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P11：lecture 11.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

最多啲。

![](img/41bb9cdf25adf8c6dbc6c265a52bd07b_1.png)

So。呃。So let's formally define what metric space is and what embeddings are just for concreteness。

 so a metric space。You know， it's。It's basically。A set。With the distance。A set of points。

 a set of objects with a distance on it， so it has x， which is a set。

And then you have a distance function D， which is it takes two points and gives you a non negative real number。

And you would want the distance function to satisfy the usual properties that a distance function satisfies。

 which is， you know， distance from u to U should be zero。Distance from。

U to V should be the same as distance from V to U。And then finally。

 the most important thing that you don't want is the triangangle inequality。

Distance from U to V plus distance from V to W is at least the distance from。有不得表。Okay， so that's。对。

That's what we would call a distance a metric space and you know we have we obviously we have lots of examples of this。

 so we have a。The Euclidean space。啊你。Usually。You would call this L2。

L2 space to the you know and any dimension L2 to the D for an E。Our。You have the L1。L one。Matric。

And more generally LP metrics and so on or R to the D。

 lots of different metrics or R to the D and then there are other metrics like。For example。

 edit distance。Between strings。This is a distance function on strings。嗯。

And so that's another metric and it's more interesting。And then there is a。You know。

 something called the Earth moer metric。This is this is a distance function on。

You could say it's a distance function on probability distributions。Over matrix。Over a metric space。

So and there's lots of other examples right of course another key example that will you know for us is。

Is the shortest part pat on graphs。That if I give you any graph， any weighted graph。

There's a distance function in the graph which is just given by the shortest part distance right so that's these are all examples of metrics okay and。

You know， they naturally show up in several problem domains and what's。What's an embedding。

So an embedding is just a map from one matrix space to another。Right， so you have a function。Fee。

From one metric space， x comm D to another metric space， let's say x prime comm D prime。给。

So it's just a map and what you'd want from this map is you'd want to preserve the distances。

Between points so you would say that a function likem from one matrix based to another is a distortion D embedding if it preserves every distance up to a multiplicative factor of D。

If you for all pairs X and y in the matrix， let's take any pair of points in the original space。

That if I look the distance between。Let's say the images。De prime of Vx VY。

 the distance between their images is。You know， let's say。It's at most the original distance。

And at least。The original distance divided by capital D。

It's that's a distortion D embedding so a distortion one embedding or an isometric embedding is one where the distance are exactly preserved and you know here if you think of D as a number more than one this is just saying that you can。

Preservve distance is up to a multiplicative factor of d。Okay， and。诶。Yeah。And you know。

 there are a couple of different ways to write this definition， you mean。

 I can write it as here I've written it as though the function fee always shrinks distances。

But it never shrinks anything by more than a factor D。

 you could also write it the other way around and say your function fee always expands distances but never increases something more than D and that's usually okay but you know those are all equal and because of scaling typically which is there in these spaces。

ok and。And you know， so in this language， you know。

 what we just proved with this Johnson Lynden's cross theorem。

 we could say as follows if if I give you any。Mattrix space， any set of endpoint。So。

Any set of endpoints？Let me call it B。Which is a subset of r to the D with the two norm。ok啊。

For any such set of end points。You know， there exists some。Map field there you can embed it。In。

Into L2 of。A small dimension L of log n over epsilon squared。With distortion one plus epsilon。做。

Essentially saying that you can embed any dimension of any high dimensional L2 into a log and roughly log n dimensional L2 space if you to care about and。

Endpoint。K of that's。That's what we proved all right。

 so that's basically just some language around metric and buildings。Okay。

 so let's look at a concrete computational problem today。

 which we will you know which which you know which is a very basic problem on metric spaces so here's the rather basic thing on metric spaces that。

You often encounter。It's the nearest neighbor problem。So the nearest neighbor problem is。Basically。

 you have some。嗯。Data set or a set of points。A set of endpoint。P in some metric space。For the moment。

 just think of this metric space as let's say。A to the end。R to the D。

 like a D dimensional space with a two norm。 So let's see just have a bunch of vectors。

 a bunch of points in D dimensional space Okay and then。

And so a natural thing is let's say these are images or documents or something and the nearest neighbor problem is basically you have some query point Q。

Okay， and your goal is to find this nearest point to Q right， so just it's very simple。

 so just goal is。Find。The nearest point。To you。Inex。硬币。Okay， so it's quite。

obvious what you need to do， you need to just go over each of the end points and see which one is the closest compute the distance。

 which one is the closest and that's it right。Okay， that's what you would want to do so but now。

 you know， that the naive that's a naive brute force solution。Would be that。

So it it you just store all your points and then you。You know， let's say you're in。D dimension。

 so you use a space。You just store all your end points it's use Nd space and then you know query time when you when I ask you for a particular point。

 you go all of your points and then check the distances let's say distance computation takes D time so you know it's。

Like it's a more na thing， okay。And what you'd ask now is can you build a data structure。

 can you do some preproces？On your data so that you can do this faster than this Nive run query time。

对。So you're asking whether you can pre process the data in some form。To reduce the query time。

 And of course， you want the data structure to be。佢到 small。

Yeah so I see a suggestion that you'd want to use a war or I partition yeah so that's that's actually a good suggestion so that's what you would do So in fact。

 so you know if you're working in let's say the simplest setup would be okay your your metric space is just the real line with the let's say the two metric like just if representss one dimensional line then of course the natural data structures is just sort the numbers and then you do binary search right so sort and binary search so。

That's quite efficient obviously it's what we do So if you look at R squared or our cube like any reasonably lower dimension space。

 what you would do is youd build something like a Kd3。There are lots of。

And then there's also veronized diagrams of so there are many ways to do this。In low dimensions。

 there are many different solutions。嗯。And。And so the one issue with all of these things is their query time is quite good。

 usually， but the storage is usually exponential in。So the space needed。

For these solutions grows exponentially indeed。So it's infeasible if your dimension is large。Okay。

 and。In fact， you know， the way to think of this is。

 let's think of the situation where your dimension is。

really runs in the thousands right which is not unreasonable for example。

 if you have a bunch of images even if it's a 40 pixel by 40 pixel that's about 10500 pixel600 pixels right so each each even a 40 by 40 image is a600 dimensional vector in the naive representation and let's say you have 1000 of them or 10。

000 of these images。嗯。So building a Kd3 in such high dimensions seems infeasible。And of course。

 what you could do is if youre working or if your metric space is L2， if you're really doing。

Nearest neighbor search or L2， then we could apply what we did just now with regards to dimension reduction。

 you could first apply dimension reduction and then construct you know kd3 in the lower dimension of space。

But even that is bad because， you know， what is the dimension reduction that we would achieve？

So if you did。Dimenssion reduction， the naive thing that or the JL lemma gives you a dimension which is roughly log n over epsilon squared。

And then your space is usually exponential in that。

 so it be space will be two to the log n or epsilon squared， which would be。

About n to the 1 over Epsilon squared。Which is quite large。

So even with the Johnsonlin of dimensionmentia reaction。It doesn't seem。Feible。Okay。

 so now what we'll do today is we'll look at。Algothms for related or relaxed problems。

So it turns out that computing the nearest neighbor itself。This problem can be quite。Hard， as in。诶。

Either you incur an exponential in D blow up。Or you don't get much improvement in the query type。

But we'll look at a somewhat relaxed problem for which we'll be able to。Design and algorithms。

 So here's the relaxed problem。So it has。Like it has this two levels of relaxation here。

 one is it's C approximate。A near neighbor。So what is it。

 well the input is still the data set is a set of points。

 it's an end set of end points in some metric space。Okay。

 and your query is some other point in the space。And your goal is to do the following。

The goal is your algorithm should have the following guarantee。If there exists some point。P。

 within a distance。They exist some point P within a distance。Ad。From your。A query point。Then。

The algorithm。Must output。Some point， P prime。With distance， within a distance。C times R。Okay。

 so in this picture， you see that I drawn this picture。

 so here my query point is a center of these two balls that I've drawn here。

So the Q is in the middle。And there are electron on two balls of radius R and Cr。

And these blue points are data points。And you see that there is one blue point within a distance R。几。

😊，There's one blue point within a distance R。And。Your algorithm is allowed to output any data point within a distance c times R。

 so can it's allowed to output any of these points。Okay， and。

So this particular problem is called C approximate r near neighbor。Okay， and then。You know。

 the more net。A little bit stronger version of this would be the following。 It would be。

 I would say C approximate。Nearest neighbor。So see approximate nearest neighbor is a slightly different problem whereas is a。

Okay， the input is again， points and query that input are still。B人。You have a great boring Q。

And here， of course the natural thing is。If the closest point is。Distance R away。

 you want to find a point which is this utmost c times R。系嗯。I'll go。Outputs。

Some point P prime such that the distance of P prime。Do。嗯。Q。

 the query is at most C times the smallest distance。Like the best nearest point。你啊。Okay。

 that that's the C approximate nearest neighbor， so it's only a slight。

You know it's a slightly stronger statement just trying to find that I should be atmost C times the closest point。

 but it turns out that it's really not much stronger than the near neighbor problem that I've defined here in that if you once you have an algorithm for。

The near neighbor problem。You also have an algorithm for the nearest neighbor problem。

So if I call this n and2， and then I call this n and one。

If one you have an algorithm for a n and one， you also have an algorithm for nN2。

 essentially you need to sort of do binary research on R。

The n and one problem presumes that there is some distance R about which you care about and all the actions happening within some distance are。

In the nearest neighbor problem might didn't specify where any distance are and somehow you just have to do a binary research and thread to use an algorithm for a and 1 and in and 2。

好。But for now you know for this and it's a very simple de I let you figure that out and for now you know we'll consider just on gain and one so you what it does is your。

Fixing a scale that you care about， as in you care about things which are within a distance R。

 that's the sort of the distance scale that you care about and the claim is if there is a point within the distance R。

 you want to find some point within a distance C times R。Okay， so that's it。Thats。Okay。

 that's the problem if if there isn't then we just don't return anything Yeah。

 if there isn't you are allowed to not return anything or return something arbitrary。

 it doesn't matter。Is C like a free parameter we are free to choose or is that define does that become defined by like whatever like solution we find out right C defines by C gets defined by C is like a guarantee of algorithm in some sense we want to produce an algorithm with the smallest value of C as possible so we'll design an algorithm and then we'll prove that oh that it gives you a two approximate r your neighbor Thank you。

就。Okay， so how do we solve this。Well， you know well use a variant of hashing right so it's natural that you'd use hashing because。

You know， the problem that we are solving is。Quite similar to what hashing is used for hashing is used to solve the dictionary problem right you store a bunch of objects and then you ask is this object in the dictionary and then the dictionary data structure is implemented using hashing so it's not surprising that you'd use a version of hashing here。

And so let me just recall like what is typically happens in Hahing， right so in terms of。

What kind of hash functions do you define？So。Like just to refresh your memory， you have the。

Notion of a universal hash family。Right， so what is a property of a universal has family。

 if you recall it's a。So a function it's a set of functions。From some finite set of。

Keys to some range， I guess。Let me just。Actually， let me use。

Let me use some domain D to some range one to Q。U。It's a set of lease functions。

With the with the property that。If I pick any pair of values。That are different。ok。

If I pick any pair of values that from the domain that are different。

Then when I pick a random hash function from the family。We would want x and y， H of x and H of Y。

To be different， meaning they go to different bins。You want probability the h of x equal to H of Y。

Proty that they collide。Let's say the product that they don't collide。嗯。Is。

I is what you'd expect if H of x and H of Y were completely random。

 if H of x and H of Y were completely random numbers in one through Q。

 then the probability that they callide is 1 over Q。So this would be one minus1 hourki。Okay。

 and that's what a universal hash family is。 and you know， like in a natural day。

Dictionary data structure， What you do is you have your domain。And you have points in the domain。

 and then you just。Have a， I mean， in it' nice simplest version。 you have a， you know。

 you have an array of one through Q and you store your point at each of。store。

X at H of x and the location H of x。And then you recover。Okay， that's what happens。你做。But， so。Okay。

 so that's the definition of universal has value essentially the functions H behave like or each I mean。

 individual value of H h of x。Behaves like a random value from one or Q and for every pair it behaves like independent random values。

Okay， in particular， there's no notion of。嗯。Like the domain has no metric on it。

Right thingss are a no no nontrivial metric on it this is a very trivial metric every pair of things are either same or different right but now if you change the domain to something more interesting let's say your domain consists of vectors in r to the N or r to the D and you have a two norm on them So now actually there's a notion of a metric on them。

 it's not just that two vectors are different or same its it's also how different are they the distance between them is defined right says a metric on them。

So essentially what you want is a hash function that respects the metric。

It sort of preserves some information from the metric the universelash family sort of oblits of all the。

Information in x and y as in X and y could differ in just one bit， for instance。

 you even if x and y differ in one bit， it is required that a hash function H of x and H or Y。

 they behave completely randomly right that's important for that but here what you'd want is if x and y differ in one bit you'd want H of H and H of Y to be same with a very good probability。

In fact， you'd want them to collide right so that's what a locality sensitive has。

So let me just define this thing。So very natural definition。 So I mean。

 all the things that we'll talk about today are quite。Non technical and input so should be a。Yeah。

 we should be able to breeze through much of it today。 So let let's see。 So what is。

So I have a hash family again。I have a hash family again and it's a set of functions H this time it's these are functions from a metric space to some domain。

Let's just say。Integers for now， it can be some domain， some range， some range。Okay。

 and what do we want from this？Well， we want the following property， let's say if。

For all X Y in this domain， in the metric space。I the distance between x and y。Is less than R。

Then we want them to collide with high probability。

So then we want the probability of H of x equal to H or y。To be at least some value。

 let me call it P close， so close by points collide with probability P close。And faraway points， Dx。

 Y， at least C times R。Things that are really far away。I want them to collide with。Probably at most。

Some other value。对。So I want to hash family where if I pick a random function from the family。

 close by points collide with pro is P close， far away points collide with pro most P。Okay。

 and then I would call such a family a locality sensitive hash family。

 so I'll just put all the parameters in there well a hash family is what are the parameters where there's the distance are。

And then there is a distance CR， which is the what is close by what is far away。

 and then there is a peak close， which is a pro of close by things。

 and then there's a pro of faraway things。Eicit。Hsh family is。

Our CRRP close P for locality sensitive hash if this holds。佢。嗯。Okay。Professor。

Should it be C instead of CR in the definition in the name， RC， et cetera， LSH？Yeah， I mean。

 I guess yeah， I guess we could parameterize by anything yeah I mean。Yeah。I mean I guess it's yeah。

 right， we could use RC or RCR。Yeah。Yeah， it's that yeah， I mean， we could call it。Actually， I mean。

 like you could call it r near r4 p close p4 things that are closer than R near should be p close and then farther than R4 should be yeah。

Yeah， but yeah， that's fine。Yeah， we could。对。Okay， so that's the locality sensitive hashing and we'll see examples of this are very easy to construct many examples of this such a hash formula。

 but before we do that let's just see how once you have a local sensitive hashing you can actually construct a dictionary quite easily so。

So okay， so what would you do？Well。Right so。One thing that is going to be true is let's assume that the Plos and PF are not really。

You know， that much different from each other。 Let's say peak close is like。t6。嗯。Sorry。

 am I getting this wrong？Pfa is， let's say 04。Okay， yeah， that's it。Yeah。

 so let's say peak closes points， so close by points are together with priority point6 faraway points are are we together with priority 。

4 so it's a little bit it's a small gap。Right it's not a big gap so you know the natural thing is can we amplify such a gap supposeupp I have an LSH family can amplify such a gap well it's quite natural we can amplify the gap easily as follows so what you can do is you can take many copies of a hash function right so so many different hash functions independently so for example so look at the following class of functions G which is。

Basically， you take T independent。Hash functions from this family。Okay。

Each of them is a hash function from X D to z。明。So and you cancatenate them as in you just。

 if like you're outputting， this H1 through Ht is outputting。

 each one is outputting an integer z to the team。对。Ok。Okay， so let's see what。嗯。

LikeWhat is true about this well， you know again。Let's look at any pair of points。

If the distance between the pair of points is。Less than art。Then every time you pick the hash。

 the probability that they collide。Is。Be close。And then what is the probability that？

All of them collide。Every time you do it， you recollide the pro that g of x equal to g of y Well。

 if I say G of x equal to g of y I mean that for all I H of x is equal to H of y right？

The protein that all of them collide is just going to be at least。P close to the T。Okay。

 just multiplication。On the other hand， if the distance between x and y is。More than CR。

Then the probability that all of them collide probably the g of x equal to g of y。Is at most。be far。

To the deep。So just by taking T copies of the function。You can get sort of a new family。Where the。

 you know， the gap， like in some sense， has become exponentially more like now the gap is between。

This is 0。6 to the T versus 0。4 to the t now。Okay， so multiplicily。

 the gap is much more starker than it was earlier。走。系。Okay。

 so this is a like natural trick just repeat the function。Okay。

 so now you know we have this way to amplify the gap okay。

 so let's just see what we can get by re data structure thing okay so one thing that you do like when you do build a dictionary using the usual universal hash family is that you pick the size of the range。

About like if you have any objects， you pick it to be like all the n。

 like you pick the parameters so that。Like the expected length of it。

The expected number of things that collide with any object is order one。meaning啊。

The expected length of each of these expected number of objects that fall into a bin is order one。

That's what you typically do。 So that gives you like you know order and space and so on。

 So let's try to do the same thing。 Let's make sure that for every point X。嗯。嗯。Like， you know。

 you expect about。Like you want to make sure that you expect about。Order one。

Other like utmost order one， other points to collide with it。

So suppose let's say we try to go by this collide so I mean I'm just trying and see how to pick the parameters here so if I want that that means n objects I want to pick the probability of collision to be one over n。

right，你。Probty of some other point colliding。あん。Protive G of y equal to G of x。

 I want this to be one over n Okay， so you know。系。And of course， we want like we won't expect。

We want less than order one。Like。Far off points colliding with us。

 but basically don't want any far off point to collideiding with you so I could put one over so。

So you know， essentially you can achieve this by setting the T。To be if I set T to be。

Log n by log1 over P。Suppose I said this then。For any far off point for。For any white。

Says that its distance from x is large。any far off point。

 the proty that it actually collides with the x is like1 over n。Okay， so that's nice。

So you want to set t to be this。So that， you know。For evening point。

 you won't have any far off point colliding with it Okay， so we decide on the value of T， all right。

But then our goal was to recover close by points。RightSo we don't like we want to now check what's the probability that a close by point collides with this point。

 right？Right。Like I mean effectively our algorithm is going to be they're going to create like a hash table for for the images of the points where the hash table is given by some function like this okay and given a new query point we just hash and see if there's an image in the same bin right and do like for to do our to solve our problem we want close by points to fall in the same bin。

So。So let's see what's that probability， so suppose you have some close by point。X。

 so proposed distance between y and x。Y in x here I don't know why I switch to x。 Yeah。

 X is my query point。 So to suppose my distance from y to x is smaller than art。 Okay。

 then the probability that。Like I will hit this， it'll collide with the X。嗯。Is a。

Like is at least all I know is at least。Be close。To the poverty。Okay， let's speak close to the party。

Okay， so。So。So， you know。い。This is。Not quite， not that large。

 It's actually one over end to the row where。R is like。Where。Yeah。you know。The role is。

Let me not write through， let me write。Where。Be close。Is equal to P5 to the row。Or essentially。

 a draw is。Log of。Re close。Developed by log of PFA。One of， yeah。So I'm just， you know。

 substituting the value of T that I got and seeing， you know， if I avoid all far off points。

 what's the chance that I？Collide with a close by point it's one over end to the row right and row is this parameter it is it's an important parameter of the hash family and this parameter let me write it here it is basically row is this log of t close。

Developed by log of P4 P4。Okay， that's this it's sort of the gap between P close and P4。

And you take the。measured by taking the ratio and of the logs。And that's。

Oh have a question so which one is like a row and which one is a P in the final expression。😊，OhRight。

 So Okay， good。 let me just not avoid this completely。 Let me call it beta。 Yeah， Okay， so let's。

 I'll call this end to the beta。 Yeah， thanks here。 So it's going be a recurring problem now。

 So its said beta。 And so this is beta。Yeah。Thanks，So， you know。

You think of p closes and P4 as two constants like 0。6 and 0。

4 and you compute log of p closes by log of P4 to be some other constant， let's say0。

3 or something and then what we got was that two close by points collide with probability one over end to the beta which means that you will get recover the close by point with probability quite close to0 to one over end to the beta but there' still hope and it's at least one over end to the beta so the natural thing to try is to like if you succeed with a tiny probability you repeat you try the same thing sufficiently many times you succeed constant probability so that's what we do so instead of using one hash table let's use n to the beta hash tables。

So you put l equal to n to the beta hash tables。So you do the each one like n to the beta hash tables。

 G1 through GL， right？Where each GI recall is actually concatenation of our original like tea copies of her original hash function。

So that's the final data structure your data structure involves enter the be hash tables。

L hash tables where each hash function is this it took your original LSH function and took two copies of that。

Okay， so now you know both of things work out， you can check that。

So your algorithm is a natural thing， right， if you given a query point。Just to spell it out。

Given a query point Q， all you do is you just try， look at each of these hash tables。

See if like you know going equity point Q， you know， you look at G1 of Q。You know， gee， I love Q。

Each of the hash functions point you to some point in the hash table。

In one of each of these hash tables and see if there is a point there。And if it is close by。

 you return it。ok。So。That if I had to write down the。Storage， I use here。So the storage， as we said。

 was you， use n to the beta hash functions。Hash functions or hash tables， right？

And each of them takes order in space， so this is like n to the one plus beta bits of memory。Okay。

 and what is a query， query time， query time is also。What is the query time Well， I need to go。

Look at n to the beta hash tables， right， And so it's n to the beta。嗯。一记。

And maybe I need to calculate distances that many distances or something。

 so it's basically it's into to the beta times， whatever time it takes to compute distances。

Into the beta distance computations。系。So I have a question about this so just to see if I'm understanding this algorithm correctly。

 is there any reason why they have to be like grouped together into these tea copies or is it just for the convenience of analysis？

嗯。Oh right so。So， I mean， the locality sensitive hash functions that we are going to construct。

You know， by hand now we'll have a small constant gap between Plo and PF， it'll be like 0。6 and 0。4。

And this sort of。Like putting them together into one。

Single hash function is important to get this exponential blow up。

Or you know you get gets of an exponential block in these probabilities from 0。6 and 0。

4 it becomes 0。6 to the t to 0。4 to the t and and this exponential b was necessary right because that's what you know made sure that like you。

Basically， you have this parameter T。As you increase it。あぼ the。Both the probabilities。

Get traced to the power t or decay exponentially I mean the correct way to say is both the probability is decay exponentially because 0。

6 to the t is also going to 0 0。4 to the t is also going to  zero。

As you increase the So what you do is you pick a value of t so that none of the faraway points fall in the same bin。

But now the close by points fall in the wind with some。Tiny probability。

 but significant one hour end to the beta。And you repeat that， you know。

 you sort of construct that hash table though。So， note that your hash function， like the domain the。

对对嗯。There are L hash tables。Each of them。Uses a hash function onto。嗯。Z to the T。As in。嗯。Yeah。

 the range。Or the indices of each of these hash table are really T copies of H1 of your original domain。

So it's important that。I mean， actually let's we go concretely。

 let's we can construct a hash family edge such that these edges are bits， the output not integerous。

 but let's say just output just bits。Okay， so we look at sensitive hash function where it just outputs a bit and the bit is either same with probability 0。

6 or the same or you know same with Pro at most 0。4 is a single bit and then what this G does is it concateates t bits and gets you a key which is either same with probability1 over n or same with probability1 over n to the row。

Okay， and then you use。These key bit strings as your indices to a array。Okay， and you do it L times。

Separate and what。Okay， thank you， that helpful。Yeah。

 so in the runtime actually there's also a factor of T， but T is usually like log n or something。

 I guess the key， you know， effectively， I shouldn't say that。Yeah， I mean。

 query time is a little bit more。Yeah， query time is about t times n to the beta and t is like logarithmic and the main factor here is really the end to the beta the distance computation is sort of same。

Yeah。Okay， so that's。嗯。Right， so that's a locally sensitive action。Okay。

 so now we'll see fairly natural constructions of locality sensitive hash functions。And。

Lots of the quite easy constructions of them。So I guess one of the easiest one is the one。

So suppose your spacex is just。呃嗯。Bulllion strings。And your hash function。

So sorry your distance is hamming distance。So let's。Extly natural， just having distance。

 having distance is a number of bits， number of differing bits。It's also the L1 distance。On0 into3。

Distance between X and y。Is the number of differing bits。Okay， so诶。So here， you know， it's。

So the really simple hash function hash family is just the coordinates right so you have a H of x is equal to X。

Okay， so for I equal to1 through n。1 through deep。So each function maps the Boolean domain to just01。

It's just a one bit hash function it's rather silly， right I mean because。Clearly， what's the。

If your distance are away， right the probability that H of x equals h of Y。

What is proty that if I pick a random bit， x is equal to Yi？Well。

 it's basically directly related to how many bits are different。So it's， of course。

 equal to one minus the distance between x and y， let me even just a P close。

If I pick a random bit the product that they're different or the same is basically one minus the hamming distance between x and y。

 right？Baly。嗯。Well maybe I should use a different rotation here x minus y。变咗。

It's my display definition， right。嗯。What fraction of the bits are different is x minus the hammer distance guard by d。

Right so therefore， you know P close will obviously be to1 minus RD and which is roughly e to the minus RD and then P4 is。

1 minus CRO D， which is E to the minus CRD for a smaller。All of these are for smaller。Okay。

 so what that means is， you know， like our parameter beta， which is this log one over。

whatever the log of P loss by P4 is like one overse。Okay， so what that means is， you know。

 eventually our data structure will have a space n to the one plus one over C。

And space into the N plus 1 over C query time like n to the1 over C。嗯。

About into the one over and as you can see。I can vary this parameter。

Capital C like and the space and query time obviously improve because you're solving an easier problem。

The sea approximate nearest neighbor problem gets easier as we increasing。

So's another simple hash family。ok呃。Let's do something else。 Okay， so here's another one。

 which is also。Quite simple， but。So here my。My metric space is。The unit。Unit sphere。

In order to the D。So these are vectors， right？Unit vectors in art。And the distance between U and V。

Is basically the angle between the vectors。Right to the。

I'm going to just say angle between you and me， let's say divided by pi or something。

It's a cosine distance between。I think it's called the cosine distance between vectors。And you know。

 it's sort of。It seems like an， I mean， it's sort of a natural。

Meeasure of similarity or distance between vectors right so imagine vectors which come out of some sort of documents or images or something。

 this seems like a natural measure of similarity。Like so。嗯。And here。は。是。

So here's a natural hash function。 So natural hash function is basically what we're going to do is。

Okay， our metric space is the unit sphere in r to the D。Right， so I'm going to。

I guess let you draw it a little bit better so you have a units unit sphere in r to the D。

That's our metric space。And so my hash function will。Just be。You know。

 pick just be pick a hyperplane。Through the center。Cut it in the middle by a。

Slice it in the middle by Hy planee and。knowEverything above the hyperplane you map to one and everything below you map to zero。

Right so。I think if you had to do it informally， it's a hedges。Sample as follows， you know。

 pick a vector。V at random， like this is a normal vector， this is a hyperplane normal V at random。

From the sphere or from the Gaussian distribution doesn't matter。

Let's say the Gaussian distribution and then you know。你四。

H of x is equal to1 if the inner product V dot x is greater than equal to 0 and0 otherwise。

So geoally is just one side of the hyperplane is one。 the other side is zero， so it's a natural。嗯。

还是 function。Okay， and what like。What is this， how does this behave？嗯。Well， this is this also， I mean。

 it's sort of tailor made for this， the metric is tailor made for this analysis。

 basically if I have two points x and y。Okay， and。Let's say the angle between them is theta。Okay。

The chance that x and y x goes to1 and y goes to zero or the other way around。

 chance that x and y gets separated by the hyperplane is basically the chance that your hyperplane sort of passes between x and y。

Right， probability that。Its a effects。Is not equal gauge of y。

Is probability that hyperplane passes between x and y。

RightAnd you can see that that just depends on the angle。Goes between x and Y。

You see that it goes just between the angles and it's sort of like a theta by。喂。

So that's like I mean， we defined our distance to be that。It's the angular distance。Okay。

 so that's that's。是。那ural thing。Right， so okay， so。And， you know， this。嗯。This。嗯。

Hash family has some value of beta I don't know， but it's some constant it has some value of beta which is like a constant so and that works I mean some constant that gives you some constant into the some constant and yeah。

Actually， I think it's maybe even a reasonable constant because it's I mean the way I've defined it the properties are very nice it's one minus r versus。

1 minus C oh， actually sorry， beta has one over C here。Beta is 1 over C。He it just。Okay。All right。

 so let let's look at something more。Different， okay， so let's do should we do this。Yeah。

 let's do the jack something called the jacketard similarity similarity。So。So basically， you know。

 this is like a similarity metric that's used between documents。And it's widely used， very popular。

 and so what is the document， what you do is you have a document。And。

You know you're just defining some sort of a similarity metric。

 so what you do is you treat a document as just a bag of words。

So you obliterate all the order information in them and you just treat it as a set of words。结分闹。Okay。

 have a set of words Okay， so now now you need to define what' similarity between two sets if I give you two sets A and B。

Of some larger set two subsets of a larger set in this case。

 it's the dictionary of all possible words， right， it's the dictionary of all possible words I give two subsets。

 then the jaard similarity between E and B is。Sort of。诶。

Is the size of the intersection viewed by the size of the Union？So if you we have the same set。

 same document or the same set of words have the same set of words， then this will be one。

1 fA is equal to B， and if N B disjoint sets of words， then this will be0。嗯。And so of course。

 theres a corresponding distance here， the distance is， of course， one minus the similarity。

 so distance is1 minus a inter sec B divided by。你要人逼。

Which is the symmetric difference between A and B。嘅。Okay。

 so this is a distance and there's actually a very， very clever。

Set of hash functions on this and on this family or on this space within is a set of subset。

Which nicely works with Jaard symbol and this is widely used and。

This natural hash family is called the Min hassh。Functions， so what is a mean hash function。嗯。

So essentially the idea is you pick。A random。Permutation of the dictionary。

So pick a random permutation pi of the entire dictionary。

So sort of redeffinine what it means to be lexxiographically。

 just read it just pick a random ordering of all the words。Okay。And then， you。Map every document。就第一。

First or the lexxiographically first。Or the first word according to this authoring。

 the smallest word according to this author。Dfined H p。Of any document， any subsidy to be。I guess。

Let me say the first word。边诶。And asper。Permutation by。So， I mean。

 there should be a less clunky way to say this just you know。

You look at all the words in your document and you see which of them appears first in the permutation and you use that as a hash of the document。

Okay。啊。Good。Yeah， so the。This is。Itき。It's an extremely impressive hash function this one is。

Why is that well？If you pick any pair of sets， any pair of documents or sets。The probability that。啊。

H p of an a。The collide with the H of B。Is exactly equal to the。

Jacket similarity between the two sets。Okay， and。It's a extremely powerful way to sketch a document。

You pick a random permutation of the words and the sketch of a document is to just look at the first word in a as per the permutation P。

Okay， why is this true， Well， it's just a very natural。I mean， basically you have E。And then。

 you have B。Right now you have a lot of words in A and B。

What you're doing is you're picking a random permutation。

Of all the words in the dictionary or in particular， random comm of all words。In。A union B。

At all elements in the N B keeping a random permutation。So， the。

Smalllest word or the first word can be any point in a union B uniformly random。

 any point here can be。The smallest word in A and B。系。With probability。A intersect B by a union B。

The smallest word。In the A union B。Falls in the intersection。

The proity that like you know when you build the permutation。

 the very first word you pick can be any point in A B， the proy that it's in this intersection。

Is precisely。As of a intersection B by a B size of a。

So that's exactly and when that happens when the first word you pick falls in eight sec B。

That will be the first word in A， and also be the first word in B。So therefore。

Or it'll be the smallest word in a。Yeah， it's mostworth me and so there for you。

You get this nice fact。And once you have such effect。You basically get。For the checkard distance。

You have a locality sensitive hash。So the priority that。一ぱ of。People do expire be。

Is equal to 1 minus the jaard distance。I mean， you can clearly see that。

If your documents are less than R away， then。The pro there equal is 1 minus R there more than CR。

 the pro there equals1 minus CO you know。CR and therefore you again get be to be the same value。

The data that we were talking about will still be one over here。It's a very simple idea。

 but it wants you。I mean the notion of min hassh is a very simple idea， but it's very powerful。

 I mean not just in the context of local sensitive hashing， but just in lots of different contexts。

 like imagine in a whole bunch of documents， you want to be able to compare pairs of documents and you know。

Instead of if comparing for every pair of documents， you can compute this distance exactly。

 it takes a long time instead。For all the documents， you first do this Jaquard in this min hassh。

And then you just compare the hash values。Which will be an indication。

 which will give you an estimate of the similarity between documents。It will be much faster。

 so it's a very simple idea， but quite powerful。So the key thing to remember in this min hassh function is there is some sense a correlated choice。

 it's random there's a random permutation， but the same random permutation is used for every document。

So。嗯。RightSo so there's a random permutation of the entire dictionary that you pick at first and the same random permutation is used for every document。

And that correlated choice is crucial in getting this。Probability of。Hewe this。

IfIf we just picked a random word for every document separately。

Then then we wouldn't have this like if even if。Like if you had two documents that are essentially the same。

 two sets that are essentially the same， except for， let's say， one small change。Right then。

 you know， if you。Picked a random word for a and a random word for B separately they'll be different with very good troty in fact。

 almost other time they'll be different The key here was that we made a random choice which was this random permutation of D we did that at once and that's a correlated random choice and we。

Use the for every document， the first word as per that permutation。

And that's the reason why if your two documents are very close to each other， very similar。

 then both of them would be mapped to the same word with very high poverty。Yes。

 this correlated choice is critical here。嗯。Yeah， actually some of this actually we。

 I mean sometimes we do cover it in 170。Like there's another very interesting application of this is a streaming application。

 but it's quite surprising at first I won't cover it， but if but if you haven't seen it。

 you should go see it so the application is okay so it's a streaming。

Algorithm to estimate the number of distinct elements。 So it's sort of very similar to this。

 I should check it out if you haven't seen it， but let me just say， you know， it's beautiful。

 So it's the following thing。 I give you some。Let's say all of Shakespeare's novels or something like let's say a huge novel。

 a lot of words or it's just a huge novel， and I give you a tiny piece of paper。ok。😊，And。

I ask you to read the novel and estimate the number of distinct words in it。

How many different words are there？You have a small amount of memory。Which is a tiny piece of paper。

And can you do it and it's a very clever algorithm。

 which is sort of related to this random permutation thing。ok。All right， so let okay。

 so this is one another one。 Okay， finally， I'll show you another easier。Quite an easy hash function。

L do。So these are natural metric space at two distance。Okay， so sorry our matrix space is。

So themetric space is this。So is R to the D and the two node。

OkayAnd what's a natural hash family here？诶。So let's think in terms of embeddings。And。

You know let's embeddings let you map one space to another and let's repeat do this。Two steps。

So you have indeed dimension。First， let's map it to something we understand better， one dimension。

And our favorite technique to do this is to do random projection。Just by random projection。

So I'm defining a。Hash function， random hash function。 So what I'm going to do is I'm going to pick。

Victor V。With Gaussian coordinates， let's say。And。M个。嗯。Like if vector if I had a point X here。

 I'll map it to just v in a product X。Okay， so I'm in one dimension now。Okay。

 so this point is in one dimension。Right which is almost like the hash we want。

 but really you know when we say hash we usually mean a map to some I mean finite set at least integer something discrete set this is not discrete yet it's a continuous thing so we should fix that。

Okay， but at least this one dimension projection has these nice properties right so we saw that like in the proof of Johnson and Mistr。

 like the very first thing we saw was that。嗯。If I pick two points x and y。Okay， in R to the D。

 if I pick two points。You can show that the expected distance。Between their projections。

Let's say I take the two norm of the。LikeThe absolute value the expected distance of the projections is proportional。

うん。You know know， if you pick the scaling correctly。

 it's basically equal to the two norm of x minus y。Okay， up to a constant factor。

sorryrry if you pick the scaling appropriate， it's equal to the two norm。So like this is good。

Over a random choice of me。The distance between x and y looks like it's the right。re value。

After the projection， okay， this is good。But now we want to get it to a discrete set。Okay， so。

So what what is the situation now， let's forget about the D dimensional space。

 let's say I just have a one dimensional line。I have one dimensional line here and on the line I have these points。

And the metric I care about on the one dimensional line is like the。

 let's say the absolute value between the point right it's the usual distance between point numbers。

Okay， and that I want to sort of map to something， let's say Z like Z。Right。And。

And let's say for now we are interested in distance of some scale， right so let's say you know。

You know， because our the real line with absolute value is like a。

 you know it's not compact like it's goes all the way to infinity on both sides。

 let's just for now pretend that we care about not the whole of our but。

let's just say we care about just minus11 or01。the close into is01。Okay， and let's see how to map。

The closed interval is 01。With the absolute value distance。do。

Something discrete that you want to go from the continuous close interval to something discrete。

So here's a map。hel。So let's map to0 and one and the way I'm going to do it is。I'm going to。对。

Like let me just show the map more carefully here。So01。So my map will be pick a random threshold。

Pick a random threshold theta in the interval。Like somewhere。And。嗯。

H of x is equal to1 if x is on the right。And zero fx is on the left。Okay。

 so this side will be zero and this I will be one。Okay it' is a random threshold。Okay， and again。

 what is the probability that H of x is。Not equal ratess of y。Let's look at that。 So let's say。

 I have a。诶。Okay， let me draw it here again， so let's say I have two points。X and Y here。

And what's pro H of x not H of Y？Well， HFx is not about H of Y。

 if and only if the threshold that you pick like the random place to cut lands in between them。

This is basically the probability that the threshold。Lands in the interval between x and y。

And what is a pro that happens while it's proportional to the length of the intervaltrovert？

So it's y minus x。Do it by the length of one， that's the property。ok， so啊。

So that works right so so what is the entire like okay。

 so that's a good like you see that that's a map that preserves， you know。

 in fact it has this exact dependence that you want。

The priority the H of x node H y is exactly equal to the distant between y and x。Okay。

 so what is the map from L2， the hash function from L2 to let's say，01？

You first apply a random projection。And then。You， let's say， scale it so that。

You applied a scale random projection so that。Your values lie in some region like 01 or something。

And then you pick a random place to cut the line。Between0 and1。Okay。

 and that gives you a map from L2 to 01。And it has this property that the cruelty that。H of x is。嗯。

Not equal D of y。is basically some absolute constant， you can work out some constant。

 some absolute constant times the length distance within x and y。嗯。

Like it's proportional to actually， although they should say it's proportional to the distance between x and y。

That's what I。I mean， the proportionality constant to adjust just by the scales and so on。

 but you can do that。So that's a natural。嗯。顶 and。Yeah。

 and you can similarly do things with L1 distances and so on and so forth。嗯。

OkayOne final thing I want to say is okay， so we've been looking at very natural metrics so far。

 but you know you eventually want to use this on other metrics like we you know edit distance right I guess what we care about edit distance or。

Edit distance between strings because that's actually that like you're dealing with genes or something that's a natural place to have work with added distance or earth mo metric or more like these are fairly much more。

Intricate metrics。And what usually works or what's the best solution in many of these cases is to first find an embedding of these metrics into L1。

L1 metric。So you find a way to embed。Edit distance between strings。Into L1。

 as in you map every string to。A vector so that the added distance between x and y is。嗯。

Close to the L1 distance between their images。Of course it's not going to be exactly close。

 you lose some distortion， in fact you will lose a distortion D， which is not even constant。

 it's going to be like log log n or log n something like that。

 but it's some function of it's some small slowly growing function of n。And then you on L1。

 we have very nice LsH， look at sense you hasing， right？The hash funds that I discussed just now。

We just discussed just now with this。Yeah。This random cut。This hash family works on L1。那差多。

Any questions？Okay there's a question about edit distance so im okay so i'm basically done saying what I wanted to say today so in the next class we'll talk about different boin em so there's a question about edit distance so edit distance is really very intricate distance function because。

It's the number of you know additions deletions， insertions deletions that you need to do to go from one string to another。

 so when you know when you insert when you delete something things shift。

To the left or right the only way to calculate any distance is to use the dynamic program。

So it's quite a complete， it's quite an intricate metric and because you can shift things where by delete letters as you did。

How to insert it shifts。 So it's quite quite interestingtri。 In its， you know， at first。

 it's even surprising。 you can calculate it at all。And。So you can embed it into build one。

But you will incur。Some distortion like it。 I think if you have end strings。

 you have to distort the metric by like a。一定。i want to say。唔攞嘅。So log， log in。あるや。

Eit distance on end bit strings incursor is login。The best known it's impossible to embed every distance and1 better than that。

But there's a whole line of work on embedding edit distances into L1 and so on and what's the best embedding possible Also there is a line of work on。

嗯。Can you approximate edit distance fast because the dynamic programming based algorithm to compute edit distance takes time order and squared？

Like because you built the dynamic programming table， right？This work on how whether you can get。

Lanar time or close to linear time， approximation of every distance because it's important because it's a like people want to compute at distance between。

DNS strings， again， genetic strings， which are quite long， super long。

 so there are lots of heuristics to calculate it。走。

Do you know that edit distance can't be computed any faster？Exactly。great question， actually。

 there is some evidence that。You can't hope to well basically we know I think we know that if you can calculate compute80 distance faster than n squared。

 then you can solve。K act versions of sat faster than two to the end time k act faster than two to the end time。

 and so there's an strongly exponential time hypothesis which says that。

You shouldn't be able to solve S first and the end time， not a case act first and through end time。

So there is complexity evidence saying that you can't do better than then squared based on assuming that S is to do the end。

 I mean then that's all you can hope in terms of lower bounds and runtime right like for now there are no absolute statements and very few absolutely provable statements and complexity everything is relative because we can't prove lower pointss maybe you can solve even three S or MPcomplete problems like TP in quadratic time there's nothing preventing that。

So， but we can prove that if you solve any distance better than square。

 that amounts to some way to speed up， do better than brute force search for like general St。

And that seems unlikely， so there's evidence in that sense。

But we can concretely prove non embedability results， not runtime results。

 we can prove you can prove that there is no embedding of any distance into L1 because it's just a structural fact about the two metric spaces。

I think non embeability and non embeability has not results they had called with just the。

Structure the mental spaces so like some like there is very there' is a a lot of work on that actually。

Like we saw Johnsonlinnden Str， you can do dimension reduction in L2。

 you can prove that there is no dimension reduction in L1。

Because some of the metric spaces sits there。You can't do demand reduction there， but there's no。

There are endpoint matrix space in L1， which have no analogs in lower dimensions。

 like things like that。So similarly， there are endpoint metric space in edit distance which have like the metric looks so complicated that it doesn't emed into like L1 at all。

Thank you。

![](img/41bb9cdf25adf8c6dbc6c265a52bd07b_3.png)

嗯。