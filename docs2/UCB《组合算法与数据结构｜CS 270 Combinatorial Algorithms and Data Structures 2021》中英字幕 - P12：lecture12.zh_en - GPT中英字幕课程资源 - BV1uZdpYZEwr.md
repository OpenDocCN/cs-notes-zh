# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P12：lecture12.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

seeよ。

![](img/50d97f9738c8cf4c38a3b4769642d2d2_1.png)

So。Today， we will。Look more about learn more about metric and。

And in particular today we'll be dealing with general metric spaces。

 so you have a general metric space so a metric。On endpoints。So。

So a natural example to keep in mind would be， for example。

 shortest path metric on a graph so you have some graph and the weights on the edges of the graph and once you have weights on the edges you can define distances using shortest path and let's say the metric is。

The shortest part metric on the graph。 So that's a good example to keep in mind。

 So we're talking about such a metric and you know。

It's these things can be fairly complicated to work with， so yout want to simplify it。

 So in particular the what we'll be looking for today are。Embbeddings。

That map such a general metric space to three metrics。Okay， and you know， three metrics。

As the name suggests what we'll call it is short epo metric on a tree。

Which is clearly much simpler and mean the advantage of doing such an embedding is that for many NP complete problems it's。

出る。The problem is many times efficiently solvable on three metrics。

So a natural approach to solve approximate and complete problems is to take a general metric on endpoint or a shortest path metric on a graph that you get and embed it into a three metric and solve the problem on three metrics。

And this gives you an approximation algorithm to the original problem that you cared about so it's actually a very。

 very useful approach， in fact， like lots of approximation algorithms。And。

Online algorithms also use this approach。嗯。是。So whenever you have a problem on a very general metric space。

 this lets you sort of simplified significantly。就。So let's see what's possible。Okay， so， you know。

 the ideal thing one would hope is that if you have a metric space X D here。

You want to find an embedding into a metric space which is on a tree and of course well decept to be the distance on the tree。

And ideally would want to hope that， you know。The distance。

And the metric space is equal to the distance on the。A tree。ok。But as you can expect。

 this is impossible。In fact。With lots of natural examples。

 you can take the complete graph and try to make put in a three or like a worse example is if you take a cycle。

Take an end cycle。And it has a distance function on our end cycle， you know。

 of course the distance function。Kinds of wraps around as in as you walk in one direction。

 the distance increases and it starts decreasing and it becomes zero again your distance function end cycle。

 if you try to embed it in any given three。You will incur。Order and mega and distortion。明令。

You have to either let's say never compress distances。

 let's say the distances on the tree are always at least the distances on the graph。

You end up stretching some distance by order N。Okay， and you know。

 it's very easy to construct a distortion or and embedding you just cut one edge here。

Just cut an edge here。Okay， if you cut an edge， the n cycle becomes a tree， becomes a path。

And then of course every distance is preserved almost except the distance between these pair of vertices was one and now it's n so you in an n distortion and it can prove that any way you try this you'll anchor an order n distortion。

Okay， and the sort of the。Key idea is that if you incur such heavy distortion only if you use a single deterministic tree。

So what we'll actually be interested in are probabilistic tree embeddings we want to look for randomized or probabilistic。

3 embedding。So what are these well。Okay， what is it well you have some metric space Xd？ok。嗯。呃。

Given the metric space Xt。嗯。You know， randomized embedding or randomized tree embedding。

Is a distribution。On trees。是。On on three metrics， let's say three metrics， one three metrics。

Such that。So let's say， you know， by convention， let's assume that the distance always increases in the tree。

For every tree that you sample， the distance increases。And。But it never increases by too much。So。

 in expectation。We I take expectation over the tree。Of x y distance between x Y。

 it's at most some factor， let's say alpha times the distance between x and y。是。几时一 sir。

So on average， you don't increase any distance by more than a factor of alpha。And。

And this is for all Excel slide。Okay， that's the definition of a randomized embedding。And。You know。

 in sometimes you want more than this， So sometimes what you want， you want， well。

 your X itself sometimes is。Corresponds to some graph。 So you have some graph G equal to V E。

You're like a shortest path metric on a graph， let's say。

If your graph if your x corresponds to a shortest part on a graph you would want your trees to be spanning trees of the graph right that's a natural thing you might want and that's something more then you would call the those。

嗯。Low stretch spanning tree， right？A low stretch spanning tree is the same is the same thing as a tree embedding except that now your trees are really spanning trees of your graphs。

So in particular， your tree must have the same edges or edges from the graph。

 the length of the edges should be the same as there in the graph and so on。

 so it's a much more restricted object。Today we won't be getting into low stress spanning trees。

 but it's sort of a related object which you can construct a little bit more complications in coming up。

 but today we'll be just concentrating on just randomized tree embeddings where you just have some metric space you don't have any graph structure on them and you just want to embed this general distance function as a distance on randomized tree。

As a distribution of。Okay， and what we'll see is。Here's at theorem Bill see and that。嗯。You know。

 for all XD。There exists distribution or three metrics。With the。With distortion。

 with alpha is equal to order log n。If you have1 points， then it takes order log and distortion。K。

And this。Okay。Okay， so that's the setup。So a key thing which we'll use in constructing these three embeddings is an object for low diameter decompositions which are actually themselves very useful objects。

 they're also like really used in lots of property testing， distributed algorithms。

 many different approximation algorithms。And so on。 it's a very simple notion。

 So what is a low diameter decomposition， So here。Here's the thing so what what do you have。

 you have some you're given。Again， some matrix space Xd。Okay。

 and what you want to do is to break this up。I want going to break it up into pieces which are small diameter right so goal is to just partition。

X as some partition， let's say P is equal let's say this is a partition P equal to x1 union x you want a partition。

X， so into some number of pieces。Such that。Diameter of each piece。Is。

At most some small diameter delta。嗯。Okay， so this is easy you can just you know given any set。

 you can just break it up into pieces with each of each are just one vertex or something and then you get that but what you really care about is a tradeoff right when you partition things into small pieces you don't want to just。

Break things up too much， meaning if two points are close by。

 you'd want them to land in the same place in the same partition。

Just like locality sensitive hashing， in a sense， if two points are close by youru metric space。

 you want them to land close by so。So what you want is， for example。If I look at two points。

 d x and y。Okay。And ask， what is the chance that they're separated？所。So if x and y are separated。

 this is。This should be。Proportal to the distance。It should be proportional to the distance clearly。

 right。And you know， you want it to be upper bounded by something like this。Okay。2。

So one notation of thing， I'm going to use the notation P of x。Means what does P of x mean it is the。

诶。Piece of the partition into which x falls right This is a set in the partition。To which。X belongs。

Okay， just notation。 so P of x not equal to P of y is is the same as saying x and y gets separated when you did the partition。

Okay， and now you're asking that the probability thattin were separated be upper bounded by something that's proportional to the distance。

And we will see why it's sort of natural， I mean， we'll look at maybe a couple of examples to see why it's natural to put this delta in the denominator end。

It's one but。But the goal is really just break it up into small pieces。Okay。

 so this is very similar to local sensitive hashing in a sense。

But the key requirement is that every piece has a diameter， which is small。Yeah。So okay。

 so what do you do， So for example， let's look at an example。

 so imagine you were just had the real line。Okay， can you add points in the real line？Okay， and okay。

 so this is X's。诶。Xd is just the real line with the magnet distance being just the absolute toilet。

 the usual distance on the line。Okay， okay， so now。What do we want now， Well， we want。

 let's say we want to break it up into pieces of diameter one。 Okay， what's the natural thing to do。

 The natural thing is， you know， just break it up at in。Let's know。

 let's say at in teacherger coordinates， right， So0。one。Do。Three and so on， and then minus one。Okay。

 so see so now each piece has a small diameter。ok 嗯。But。谢谢。So let me share my screen again I think。

Yeah， we can see。Oh I think it's not updating my iPad。Thank你。Yes， so。Okay。Okay， right。 So now okay。

 so this is a reasonable decomposition of diameter 1。 The only problem is， you know， this actually。

Is not valid as of now because firstly it's deterministic and but that affects it in a bad way in that suppose I pick two points x and y。

Which are just on two sides of this edge。Okay， just on two sides of this edge。

 then what's the probability that x and y are separated， well that's equal to one。Because， you know。

 we pick this partition and you know you have。D action were separated and。But you know。

 if XM were really， really close by， this is much larger than it's not proportional to the distance。

So what can we do in this case， any suggestions？嗯h。😊，Yeah， K means yeah， yeah。

 actually is a very simple thing one once one could do， which is to， you know。

 the only problem with this construction is deterministic it's yeah basically you have to choose your origin randomly So you you shift the。

Origin randomly between zero and one。Okay， so if you shift the origin randomly。

Meaning you shift these partitions randomly， then you will see that the probability that the part p of x is not equal to p of y is precisely equal to proportional to the distance between x and y。

 so in fact， you can say it's at most the distance between x and y。嗯。Buy one。SoSo beta is one here。

Beta is 1 and delta is1 and note that you need a okay。

 now it's also clear why you need a delta naturally Delta naturally shows up here because。

You'd expect that if I reduce the diameter， if I ask you to break it up into partitions of size half。

Should expect to separate twice as many edges。So therefore。

 it's natural that there should be a delta in the definition of the upper bound and really the parameter that we look for is the beta like。

How much more so in this case we got be I could do one， which is like the ideal thing。没掉。Okay， so。

So this is on the line， you know， if I give you the。Like if I give you the D dimensional space。

And the L1 norm in the D dimensional space。Then you can sort of do the same thing。

 You can take like a。Great。Well， this would be the。Yeah。

 you can take the grid and take a random shift of the grid。So that' will give you an embuding。

And I think you lose a factor D here because if you want the diameter to be。Delta。

 you'll pick the size of the grid to be Delta overd。

Because if you want the diameter of each of these boxes to be delta。

 the sizes each of the sides of the grid to be delta over the dimension。And now that means that。嗯。

Like， if you had。嗯。If you had two points x and y that distance。You know。Are away。

In along one of the axises， you'll cut them with ProD R divided by delta alreadyD。

It's a proty that PfX。Not it going to be away。关闭。The distance。

P R divided by some of the grid size that you're picking Dlta already should be like D times r over delta。

He said it's much less。Actually， I'm curious whether there's a better thing to do for L1。

I think that is a better thing to do for everyone。This is just。Yeah， thiss wasteful。Okay。

 so you see you get the sense of what's happening here。You want to break it up into small pieces。

Okay that's sort of。Okay， so now we see a very simple and really neat algorithm to get low diameter decompositions。

Yeah。Okay so here's an algorithm， so your input is of course some general metric space。

 it's a general metric space X and D， so you just give an end points and a distance function between them。

Okay， and here's the algorithm， it's quite nice。So。诶。So actually。

 you knowt know what before I describe the algorithm。

 let me just describe as more general strategy of how you would solve this problem in different spaces like okay。

 suppose I asked you to solve this problem in L2。Okay。L2。

 let's say R squared on in two dimensional space and the two norm Okay here's okay。

 so you have some region and you want to break it up in two parts。Which are all diameter at most one。

Okay so a natural thing to try would be to try like what we did here。

 what we did here was to sort of think of a partition like a grid does something very regular and you sort of start breaking it up you know break up the thing。

 but the problem with that，Approaches。Right， you。Some of the best sets that you can pick of a particular diameter don't really tile right so if I ask you what's a diameter one object in two dimensions you would say it's a circle。

Of diameter one。Right。And。嗯。And you you can't really tile the space with circles。

 so youd need something more like simpler and more robust than just really picking the grid。

 but you know there's a very natural thing to try you can just here's a natural thing you draw a circle of radius1 okay you take out everything inside。

Then you draw， you pick another random point。And you draw another circle of redius one。And so on。

And of course， what will happen is as you do this partition， you will encounter situations where you。

 you pick a point。And you draw a circle and some of it is already taken out by another partition。

 That's okay， let's just。let's just take out whatever is not taken out。So let's do this。

Does that make sense so you？嗯。So each time you pick a point there'll be some part which is already assigned to some partition so this is partition1。

 this is piece2， this is piece3， piece4，5， six7 okay these are all taken already now we pick another point randomly。

Okay， let's say you pick another point randomly and you draw a circle。

 you take out a circle around it。Whatever is not taken comes to you like eight。

Iith that be8 and so on and then eventually when you repeat this。

 the whole space will be tiled by in some sense， pieces of circles。Offer it is one。And of course。

 by definition the diameter of every circle you took out is one， so therefore the diameter of。

Every piece that you broke up into the diameter as in the maximum distance between points is that most one。

Okay， and you do this randomly。And， and this is a。It's a reasonable thing to try。诶。

And this works pretty well actually， so like how do you analyze such a thing？诶。

So let's you know let's analyze what happens to very small distances。

 thats easier that's the easiest thing to do。O。诶。Let's say I look at。Two points x and y。

 what is it that I need to analyze I need to understand。If I have two points x and Y。In our tool。

I want to understand what is the probability that they both land in the same partition or they don't land in the same partition。

 let's say。Okay， what is this related to？Well， so now I have two points x and y。

Okay and this let's assume that these points are really really close to each other for simplicity I mean it's not you know I mean it's not necessary。

 but I think you get the exact answer when you're really really close to as a distance close to zero so it's epsilon let's say they're a distance epsilon away。

诶。Okay， so what is the chance that they get separated？Well， let's think of。

The first point in time where one of them got gobbled up by a partition。Okay， so let's look at。

 let's say without loss of generality。Let， you know， X be。嗯。Assigned a partition。First。

It like it doesn't matter I just rename it， so let's say x is assigned the partition first。Okay。

 now the question is when x was assigned a partition。

What is the chance that why also fell into the same partition？ok。Okay， so。Okay。

 when X was assigned a partition， there was some center that。啊。You know。

 center that actually ate up x。So let's say Z is the center。That's sort of8 as。Okay。

 so Z wed drew a circle of radius1 around z。And it ate a x and it didn't eat y。K得出来。All right。

 so what's the chance that this happens？嗯。Basically， if I'm picking。

My center is uniformly at random or the entire space。ok。😊，呃あ。So。The probability。That。嗯。So诶。Firstly。

 the distance from x to Z。Is at most one。Okay， and since we're doing a completely random thing。

 like it's by symmetry， a completely random choice of points like Z can be any point。

In the around at a distance at most one。Aund X。Okay。

 Z could be from any point a distance around one text and。诶。In some sense。

 when does z not gobble up y when distance from x to z is less than1， but distance from y to z。

Is more than one。 so this happens。Basically， when。You write， so I guess yeah。

 this is an easy way to say it yeah， this if you draw x and y。And then if I draw。你。Circle around it。

This is sorry this is circular on y。And then there's a circular around x。Okay， and if I。

If I pick a point in the symmetric difference。If Z lands here。Z land in the。Like cemented difference。

Then X and y gets separated。So basically， it's called with the area of the symmetric difference divided by the total area。

It's the80 of。Of the symmetric difference of the two balls。嗯。You deelta is a symmetric difference。

by the area of the union of the two barss。Okay， and， and if you're。If you're。Distance between I mean。

 of course this is some quantity， you can define it for everything。

 but if the distance betweenx and y is actually epsilon。

This is the priority direction we are separated。And if they're really。

 really close and the points are really， really close。Epsilon， like as epsilon goes to zero。

 this is directly proportional to the surface area of the ball。Of the ball， I mean。

 and we didn't have to pick balls each time you could have picked I don't know， grids or I mean。

 cubes or some other some other the structureut。Shape doesn't matter like the the whole setup is still de defined if you didn't pick balls for some other shape。

 then， you know， the property that they get separated is directly proportional to the surface area of the。

Of the shape that you're picking out so in particular balls are like the best thing you can do balls afraid is one because they minimize the surface area for in volume in two dimensions。

Well， surface areas in this case since we're in two dimensions by when I say area， I mean。

The circumference， right because？The volume is the area and area as a circumference。

 but in general indeed dimensions the volume is this should be volume here。

Its volume of thesymmetric difference by the volume of the。有年。And。Good的。

Okay so so that's that's how you can calculate the probabilities of this process so this algorithm is just going to do roughly the same process on a general metric space okay so it's quite intuitive the algorithm is very simple to state。

There's only one sort of catch， but I mean， one sort of an extra idea。So firstly。

 you pick a random radius。Okay， input is this and your goal is to produce deelta bounded。嗯。

Decomposition， like deelta bounded partition。Meaning every damage of every piece has cut most delta。

Okay， so pick a random radius。All。In some range。Delta over 4 to Delta over 2。Okay you don't。

And then you。Randomly order。The set of points that you have。 This is like。

Randomly ordering is random permutation， right random permutation， randomly permute then endpoint。ok。

And then you start doing this procedure that we have right， so you you know you just pick。

A ball around the first point of radius delta。Okay， that's everything thing second， second point。

 you pick a ball。Outm the second point。And you have to give out whatever the first point has already gobbled up。

 you just have to give it up right so that's your second part set。B of x3， Delta。Yeah。B of x 1 delta。

Union B of x to delta。Ba give which your point。Every time you just go on ex in disorder order and you each time you just。

Pick out a ball。So this is ball。Of radius delta。Around x1， you go eat it out。

 then you take ball of x2 take ball it and delta and x2 and eat out and so on until。

All points are assigned a partition。Okay， that's。That's it。 And you know。

 when we say ball of radius delta like we we don't have any geometry here except for the distance function。

 So this is ball of radius delta just the set of points of distance within distance delta。

That's a set of points in within distance， oh I'm sorry。

I picked the radius and I I need to pick balls of that radius， sorry yeah。

Sorry about that it it's b of x1 comma R。You pick balls of radius r where r is some random radius between delta or 4 and delta over 2。

 know that if your radius is umost delta over 2， then your diameter is attmost delta。

So you have this。Okay。And so you're in a general metric space， endpoint metric space。

 all these notions are just somehow combinatorial， so you can talk about the like a ball is just a set of points within a distance delta。

 the volume of the ball will just be the total number of points like in that set， yeah and so on。

Of course， area would be settled， but this is what it is。

It's a bit extremely simple algorithm and it's a very nice analysis， so let's see the analysis。对。

Any questions on that little？Okay， this question， why do we need a random radius， Yeah， actually。

 that's a it's a subtle thing。 Like the reason you read random radius is in some sense because you don't really know the。

Distances geoally very well。 So if you use any fixed radius。

Your metric space can behave badly around the radius。

 so what can happen is note that everything here depends on like the analysis seems to be sensitive to the volume or the number of points at a given radius so you can have situations where let's say here's one point and here's another point and they say all the points are really really at distance half from both of them。

And exactly at a half from Boudda。Right all the remaining points like here a distance half and somehow。

If you if you use a radius， a fixed radius of half。Then you might be in trouble because。

You suddenly have a very high chance of separating x and Y。

It's just go with the you have no idea how these points are distributed as you。

And change the radius how these points are distributed。

 so therefore this randomization is actually help useful for that。嗯。

So fixing the radius is binary appeal particularly because of that reason。

hopefully let's see if we can see an example where a fixed star is bad。Yeah。

 maybe even this example might be good butlet。一次唔样。是。Okay。

 so here's a claim I'm going to state a somewhat different looking claim than what I。

What we shot shoot for， but what will get what we need as a corollary So let's say D of x y R。Then。嗯。

The claim says a probability that both x and y land in the same partition。Is at least。

Exponential in minus Eta over delta log of。嗯。So this expression does look pretty。Unintuitive now。

 but you know having this expression will be useful later。

 but let's simply me just state the corollary of this right so it the corollary is very simple。

Probably like probability that p of x not equal to p of y。Okay。

 that is one minus this six pointent two。It's one minus this exponential thing here。Okay。

 and using it。You know， using you do that。Minus x is at least。1 minus x。嗯。

You'll get that this is at most。Are divided by Delta。Times 8 log。B of x delta。

Ded by b of x delta over 8。And， you know。是。So what is this b of x delta I'm writing this is a cardinality of b of x delta what is a cardinity of b of x delta that's the analog for volume in this space right so you can see that the ratio of volumes of the balls is showing up as you'd expect and and you know。

In some sense， this expression is a little bit。To cleverly chosen。

 but really there's an exponent and a log so they sort of cancel out right effectively and what you have is minus8 R delta log of the ratio of the ball size so it's really8 R delta ratio of the。

嗯。Size of this log selection size of balls and you know that this is utmost log n because the B of x de is at least。

Atmost end right the number of points at most end， so you get eight log n。Times R over Dlta。

It is8 log n times Dxy order。So really in our。In the usual language we describe the load emit decompositions。

The beta parameter。Is login。So in some sense， you're incurring a distortion of log n when you do the part。

 you're incurring a distortion of log n， you could say that and but otherwise it's really。

This DxY or delta times login。Okay。对。So basically， once you prove this claim， this colon will follow。

It great。It follows that you get a login den boundary takingcomposition。All right。

 so so you know the claim will be very easy because we've already seen the proof in two dimensions for this thing it will be very similar to that so really it's again the same thing。

You look at the first point in time where x got captured。Okay。

 and you ask what is the chance that y also got captured okay， so if you write that down。

 it's basically the probability， suppose z is the one that captures x。The center Z captures x。Okay。

 and you ask what's the chance of y also got captured well the pro that p of x is equal to p of y。

Okay， what is that？Well， I want to get okay， in this case， I don't， we don't know the。Space。

Gemetrically， but we do know that that trianglin equality holds。喂。So。So here is Z。And x。

And y and x and y are distance little R away。Okay， and Z and around Z， we have drawn。A ball。

Of radius。donze drawn a ball。😔，Of radius。A。Right this random radius that we chose。 Okay。

 and so therefore， when does why land。But also land said the said， well。

 if you picked if the distance between x and z is less than r minus R。

If the dis Xs you are less than R minus is that， then you're happy so basically。

This is at least the probability that， you know distance from x to z is。Less than r minus r。不。

And if the distance is more than r plus r or nothing， you don't really care， right。嗯。

If you don't care what happens。So。So basically， this is。At most， the district。The size of the ball。

Of radius r minus R。Divided by。Actually， let's do the same thing that we did here。Al。

 let's not do that， let's do this I said yeah。Distance of the ball of radius r+ R。嗯。why is？

I mean this is very much similar to what we had here。

 the symmetric difference volume of the symmetric difference divided by or actually in this case。

 the volume of the intersection divided by the volume of the union。

This is like volume of the intersection。Deed by the volume of the union。It's a lower bound than that。

Okay， so that's。Okay， so so so that's it。 So now。Of course the radius r capital R is a random variable right so the probability of P ofx P of Y is at least this much in expectation over that radius R。

We picked the random radius。Okay， so now it's just。嗯。bick。You see that this from here。To。Sorry。

 from here to this theorem that we have。Is just some really simple manipulation。 So firstly。

 you know we write this as。Expectation over R。E to the log is related as that。So。😊，嗯。So then。

So then you once you get this then。Like there's an average of exponents。

Cavage of the exponential function is at least the exponential of the average by the convexity of exponential function。

 by convexity of e to the x。Like con v city f。E to the x。You can， you know， your expectation of。

E to the Z is at least E to the。Expectation of sleep。Okay。

 so what you can do because that is you can move the expectation inside and get a less than I quote greater than I quote。



![](img/50d97f9738c8cf4c38a3b4769642d2d2_3.png)

Okay， so you know this。

![](img/50d97f9738c8cf4c38a3b4769642d2d2_5.png)

Like this is somewhat too slicky for me too。I'm presenting this proof。

 but you know these proofs have been improved over several papers and now it's you can prove a lot of things in like a page and so you have all these tricks but you don't really need to do all these clever convex tricks and so on you can just I mean if you just did like first principle if you just worked out from scratch it'll take you a longer time it'll be more messy you'll get slightly weaker bounds。

But， you know。And it's slide feel yeah。This is just being perfected right the proof has been sort of perfected。

 so we have all this clever manipulation here。And a lot of these arguments are very robust。and then。

嗯。And so now what is this expectation over R， let's see what is expectation or R is。

Well expectation over we said we pick a rate radius at random between two quantities right we said well pick the radius at random between two values so。

You know， it's just integral right we said we'll pick a rateius at random between delta or eight。

And de of4 and deta of8。Was it that notic。Sorry。系咪。😔，Sorry， yeah， where is okay， yeah， yeah。

 delta4 and delta or2， you pick a radius at random between delta or4 and delta or2 so。So啊。

Let or phone， letter or two。And what are you integrating in that range。

 you're integrating this function minus log。The number of points in the ball of that radius。😔。

Ded by the ball of this radius。Okay， DR and again， you have to divide this by the length of the range。

 which is delta over4。Okay， because you're picking the radius uniformly at random in a range。

 the expectation is integral over the range divided by the length of the range， so it's down four。

RightAnd so now this is some function which varies over the range it's got do with as you increase the radius of the balls。

 how does the number of points change it could change arbitrarily right can we don't know anything about the space but let's just use a trivial upper bound right like r plus R。

Is you know let's let's assume first let's assume a little a bound on a little r like the distance between the points let's assume is at most the delta over8 just for okay and。

Or Dcap or in Dcap， we're changing the capital。It dis points at most delta rate。

 so then you know r plus r is at most delta over。2 plus。Delta over 8。Right。Yeah。

 so it's atmost deelta。And our minus R is。嗯。At least。Delta over 4 minus delta over8。

This is at least deelta array。So basically you know the denominator is at least a ball of radius delta or rate。

 the numer is at most a ball of radius delta and the number of points in the ball is mono right it's a function that monotonically increases has increased the radius right so this quantity in here is always at most like I can put the largest value for the top。

Which is log， what's the largest value Well it can be the total number of points in the radius of size delta and the smallest possible value for the bottom。

 which is。Number of points in the raius of。Delta 8。Right， then D。Dd by the thought。

K just just upper bounding the number of points to be the worst possible radius to the best possible radius。

 right？So de tower。2 four。Right， so then I should it。嘅。And then， you know。嗯。Yeah。

So I'm getting a little bit confused over here。😔，吓。Yeah， okay。

 so and getting a little countries over here should yeah。

 sorry but that it should be like you should get。E are over Delta log of the size of the ball I guess I'm just writing down what our goal was。

YeahYeah。Okay， so what are the things we have are nice？

Delta for like some constant times deelta here， I'm not getting the little r。嗯。

The little r should be there。Yeah。This should be a littleer。Like in particular， if two points are。

Like their distance is zero。 Okay， if the two points are， if the distance is0， then you know。

 log of the。Right r plus if little r is0， for instance。This log of this ratio should be one。

 log of one should be zero。And the integral should give you zero right。

 so which is makes sense because two points are the same point distance is0。

 they should never be separated， which makes sense。 So if you get a little lower times。

8ight times little R over de。Times this。Yeah， why am I not getting this little la？😔，嗯，尤其呢边。Okay。

 so yeah let me not waste your time any more time here on this Okay but but you know well hopefully i'll either clarify this or i'll post a note about this on piazza and'll clifies in next class or yeah yeah sorry about that but but。

Yeah， I guess the point is somehow in this integral when the radius r。

 it should be proportional to little r because if the radius little r goes to zero。

 clearly the log of the ratio of the volumes is one， like log of1 should be zero and if you get zero。

 right？And it's not obvious that in the way it's written like this bound is too weak。Okay， all right。

 so。Okay， so let's。Let's move on but。But I guess just to summarize。

 you have this very simple algorithm， pick a random radius， pick random permutation。

 keep eating of balls。For which we have a very nice bound。

 which is that it's basically log n times worse than the best possible situation。

Like D X y by Dlta is what the best possible situation， this is log n times was。Okay， and okay。

 and so now okay， now we'll go back to our original question that we started out with。

 how do you get an embedding into trees？Okay， how do you get load distortion three embeddings of the entire metric？

Okay， and to get the embedding into trees you。You will use a sort of for recursive procedure。

 so we'll call this hierarchical。3 decomposition。Okay， what is hierarchical3compositions， Well。

 it's this。Idea， okay， so what do you do you have some metric space and what we just figured out is to how to break the metric space into pieces of any given diameter。

Okay， so you start with take the entire metric space and you break it up into pieces of size。嗯ん。

Delta。Okay， some size delta。All， and now what you can do is now each of these three pieces is another metric space。

Right in some distance， the same distance function hold is there on them。

 So you can break them up further into pieces of。Smaller size， let's say。You know。

 like will decrease the diameter。あん。Exponentially so its let's say this delta。

 let's say the diameter of this one is delta over eight。Okay， and then we take each of these pieces。

 break them into pieces of size delta over eight squared。

 and then eventually it'll be left to just pieces which contain a single point。

Like once you get a single point you stop the clustering。

 so or do you stop this decomposition and you get a three。At least there some sort of a tree。

And now I want to。Like get a tree metric。 So what you do is you just。

Add like introduce weights on the edges of this tree。Like you have a tree。

Where your leaves are your original points。You have these extra nodes in your tree which correspond to partitions。

 but that's fine。And you know we picked the size of these pieces to decrease by some constant factor one over81 over8 just works with the claims that we had earlier you need some reasonable constant like yeah I think eight works and so what you do is you break up and you have this tree and now on the edges of this tree i'm going to put。

Like weight so。On the edges of this。顶。嗯。Right。So。嗯。So let me draw the three again。For simplicity。

 let's say on the top， you have a deelta which is8 to the power K for some K。

Like the topmost diameter of the topmost pieces is8 to the K。是。

Sa the diameter of this species8 to the k， the diameter of each of these species8 to the k minus1。

And so on。Okay， and on edges leaving8 to the k， I put in a weight of8 to the k。是。8 to the k minus1。

 and then eventually you have some noded with eight and then one。

Distance basically imagine the distance goes all the way doesn't like we don' we don't know what's the smallest distance in this graph。

 let's say the largest distance is8 to the K。This is the largest distance。

You know some upper bound and then you keep breaking， breaking and goes forever。

 but eventually it'll be left with just one vertex。But。And。

These are the weights of your edges of the graph and this is a treatment right now。

 if you look at the distance function on this tree。

We claim that that's a good embedding for the original graph。Original metric that you have。Okay， and。

诶。Okay， so let's see how why that's the case， it's quite simple and elegant。

 so let's take two points x and y。And let's say the distance original distance is between eight to the。

G冇。Mus1 and 8 to the J。It's between six some powers of eight。Okay， so so suppose this is the case。

Okay， now what do we know？Well。Okay， so x and y。X and y have distance 8 to the J minus1。

X and y have distance between8 to the J minus8 to the gender 8 to the J minus1。So note that like。嗯。

Like the pieces have bounded diameter so this this piece of the metric space is diameter8 this piece is of the metric space diameter h squared and so on these diameter are growing so x and y will not belong to the same partition。

Up to。Like X and y will get separated as。Sometime in the past， this is X is y。

X and y get separated sometime in the past and。嗯。Like they'll get separated at least at a height of。

J minus1。Right， because。はい in the。Up to height J minus1。

The diameter of at this height was8 to the J minus1。

 so the pieces are so small that they can't accommodate x and y together。Okay。

 and so the least common ancestor。Of x and y。Is of height。At least。じ。Maybe even higher。

Maybe they got separated at the very first step we don't know， but it's at least J。

Please common annce X at leastJ。So what that means is if I look at the path from x to y。一啲。

You will encounter。嗯。An edge which is8 to the power least common ancestor， right？坐列车。Has height let。

You know， let hedge be the height of the least common ancestor。Of x and y。嗯。Heches at least day。Okay。

 and what do we know about the distance between x and y in the tree？Well， it's at least。

A to the power。hatch。In fact， it's more， it's like8 to the power H plus8 to the H minus1 plus there's a path on both sides there's a path on both sides x and y。

是。But it's more， but it's at least eight to the hedge。

And we know that8 to the h is at least8 to the J。And what did we say about J is the distance from x to y。

 like he's an upper born of distance from x to Y。So。

It's easy to see that the distance in the tree is at least the distance in the original distance just by construction。

Okay， now we need to prove that you don't increase distances too much。

We need to prove that distance in the tree。Is at most some quantity times the distance in x x and y。

 so what is the expected distance in the three between x and y？

A expected distance in the tree from x to y。Okay， firstly， you know， we know that。Like。

X and y remains separate from each other at least up to height j because up to height j。

 the diameter of the piece is larger smaller than the distance from x to y so x and y remains separate at least up to height j but you know it could be that they're separated earlier we don't know how far back they got separated。

Okay， and。Basically。诶。Like we want to know。How far back they got separated， right so。Right。So。

Alterly。Like we expect them to get separated at height J。But。

Maybe they got separated earlier and don know how far back it happened right so what do you do well you say。

You know。嗯。Okay， so from J plus1。To infinity。Right， you say。8 to the J plus1。

t equal to j plus1 infinity。8 to the T。That's what you pay on that edge if you。Got separated earlier。

A to the T。Times the probability。That X and y got separated at that height。Like pump。你 if。

Pt of x is not equal to PT of y。系，就。This is actually。是。

So but we know what at distance t what is at high T， what's the chance that they get separated。

 well we know what that is， it is DxY。It's the distance between x and y？Divided by a to the T。

log of this thing， the ball sizes x comma8 to the t divided by ball of size x comma8 to the t minus1。

Okay， so where is this expression coming from， It's coming from like our claim， right our claim is。嗯。

买屁。Dclaim。I'm just using this claim。Okay I'm substituting deelta for8 to the t。That and then。

Everything else is。Okay。一样。Okay， and the nice thing now is this is at most a to the J plus。

Let you see that these eight to the T kind of cancer。And you're left with Dxy。

Times sum over J plus1 to infinity， this log right ratio of the logs of balls。

8 to the t divided by ball of8 x comma8 to the t minus1。Okay， this is a telescoping sum。

Why is it at riskcoing sum， you know， you see that you know it's a log of like each term is log the number the volume of radius of ball8 to the t minus log of the volume of the radius of ball8 to the t t minus one。

Okay it's a telescoping sound。 So if you sum it up all the way to infinity。

 you'll end up with the like the highest term， which is log of。

The ball of the largest possible radius， which is n。R log n， so let's get a to the J plus Dx Y。

Thanks， loggan。RightThat's。嗯。Yes， I think we are missing a factor of eight here。YeahYeah， thanks。

So basically we got order log n times dx Y。So we got both directions。

 the distance in the trees at least the distance and distance in the trees at most expected is distance in the trees at most order a log n time sort of distance。

 so it's bounded in both ways。不在是。Yeah。Yeah， so this is what's called this is called a hierarchical spanning tree sorry hierarchical 3 decomposition it's also typically referred to as FRT like often it's the word people uses for。

Tminology this is FRT and this is a fran ofal Rao our Satira and Talwar this is quite。

Quite an influential piece of work it's sort of like if you can use use this as a first step in many problems。

 you can just given some metric space you can put in a tree and then especially there's also not just a treats hierarchical all right in the following sense。

If I want to know what's the distance between two points x and y I don't need to add up the values of the edges on the path that's what we did。

 but you don't need to all you need to know is what's the height of the。Least common ancestor。

Like the in fact， that is in fact， the significant。

Is up to a constant factor and our approximation of the distance。

 the between x and y is basically8 to the power， the height of the least common ancestor up to order one。

 you know upper and lower mono so。Up to constant factors。Is height。

 So it's very useful structure because now it's you understand the metric very well。

 You can design a lot of algorithms on。Like by first doing this and then designing an algorithm monitoring。

Okay， and。嗯。So。はい。Yeah。诶。你。Let me show one application of。嗯。嗯。Of low straight spanning trees。

OkayUs the applications are in。Optimization comm optimization or online algorithms。

 so here's a comm optimization problem it's called buy at bulk network design。

So what is this problem right network design problem is you're trying to design a network that can support some flow or design some graph that can support。

That can support the flow。Right， imagine like building a network， a communication network， right？ So。

 So what's the situation， Imagine you have。But like you have a。You have a metric space。X D。And。

嗯 sorry。Yeah， imagine you have a graph。And。And and you have some demands like you need to be。

 you don't want to build a， you want to。If want to buy capacity on the edges of this graph。

 right like you want to buy network flow capacity on the edges of this graph。嗯。

Like you want to build infrastructure， right， but you have some demands that you want to meet。

 Let's say there is a source here and a sink here and S1 to T1。You should be able to support。A floor。

Of value。F1。Okay， and then there's another source and another sync S2 T2 you want to be able to support a flow of value。

底度。Let' do。you're given these constraints。Okay， and so on。And what and what you want to do is to。诶。

By capacity on the edges of the graph that can support this flow。Okay， and。一い。要 like。一。

It's not concurrent but it's not that your graphs support all the flows at the same time as in the capacity that you buy on an edge can be reused so if there's an edge of capacity3 then S1 to T1 can also send three units of flow on it S2 T2 also can send three units of flow on it at different times it's like you they can reuse the capacity but you need to and you and what you want to minimize you want to minimize the total amount of capacity that you want to buy。

Right you want not not just the total amount。 let's say the total cost of the capacity you want to buy。

 Okay， let's say to buy capacity on to buy。capapacity。See you on edge on an edge E。

Let's say you encounter a cost， which is like cost of C。ok。And what you want to minimize。

 you want to minimize the total。Minimize the total cost。Of capacity that you want to buy。

Usually there's a distance， right？The cost is per。嗯。Per length per unit length， right。

 That's what you。So。So you have some cost function and you want to minimize this thing and。finds。

The find C sub B， such that。Find the capis a such that you minimize this and support all the flows。

S1 to T1 flow and so on。Okay， and this problem， you know， as you can see。

 it's fairly intricate on a general graph， but a on a tree， it's very easy because on a tree。

This is only one part from S1 to T1。So you do not have an option。

 you have to buy F1 units of capacity on the path from S1 to Tiva。On and if you have a tree。

Then S1 to D1。This is just one part and you need to buy capacity F1 on that。

And as to T2 we need to buy capacity F2 on that and so on there's no option so so on a tree it's deterministic the solution is deterministic。

嗯。几。嗯。And therefore， the algorithm is， you first embed this graph into a tree with inring log and distortion。

And you get in log in approximation algorithm in leastly。Okay so many such examples of this thing。

Any questions？Yeah， I' look up this。Proof the the thing that we couldn fill fill in。

 I'll try to post on Piazza。That's the problem of these very slick proofs。

 you think you understand all of it within you。Miss something。It's better。 yeah。

 sometimes it's better to everything from scratch and first principles but。

Then it'll take longer time takes longer to describe。对啊。Okay。

 so we will meet next time and next time we'll do like one another very important problem。

 uniforms sparska problem。And see how metric cas can be used there。

And that will directly nicely lead into spectrograph。Thank you， Professor。



![](img/50d97f9738c8cf4c38a3b4769642d2d2_7.png)

Oh， sorry， it's better to do。老人老婆。提问。

![](img/50d97f9738c8cf4c38a3b4769642d2d2_9.png)

Okay you sorry。