# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p10 Lecture_10_Weighted_Matchings_cont_.zh_en -BV1a4cCeMEzb_p10-

Welcome back。And this is going to be the fourth lecture and matching。

 We're going to continue talking about the。The mean weight or max weight matching problem and in particular perfect matchings So the last time in the last lecture you saw you know we defined this notion of the perfect matching poly of a graph G。

Is really the。Convehu。哦。Guy am。M is a perfect matching。In G。

So this is an object that I defined just as a convex hu of a bunch of points。

 and this is a subset of R of the size of the a set。😊。

There is a polytop because it's a convexile of a。Finance set of points， bounded。But what I。You know。

 it's kind of difficult to argue about this， but then we saw that this is the same as this LP。



![](img/bb038d567457f92345111c86b65da234_1.png)

That we wrote down where we said X I J。I belongs to O， J belongs to R。

 Let's say sum of X I J equals one for all I and L。And sum over X I J over I and L equals 1。

For all J。Belonging to our。Where this is a bipartite graph。So， far。G being a bipartid graph L。

 comma R， comma E。Bypart， right？And XI J。顔に投げてほ。So this was， this was a polytop that we defined。

 We first showed that this polytop is。At least as large as the polytop above。

Because every perfect matching belongs to this polytop。 So it's convex cell belongs to this poly top。

 So we are good。😊，And then we showed using two different definitions。 We showed using。

The definition of extreme points。That。This compact polytop by compact。

 I just mean it has a small number of constraints。Is actually equal to this convex hull or at least is contained in the convex hull and hence is equal to it and then secondly we showed this using the idea of basic feasible solutions。

😊，Okay。So in today's lecture， we're going to see a third view。😊，Using the idea of。V6。

And in particular， what we will show is that the problem of finding a max weight perfect matching is doable in polynomial time。

 which weve already kind of。😊，嗯。Okay， so we haven't quite seen so far， but。Let， let's。

 let's run with that。 And what we're going to do is we're going to use a different style of algorithm。

 It's going to be an interesting price raising algorithm。 It's going to be like a market。

 And I'm going to argue about this。 and we'll see what comes out of that。

Then in the last little bit of the lecture， what we'll talk about。

 and I'll just give you a preview of what we're going to talk about。

 So we said for the for bipartite graph this object。😊，The convex hell of all matchings。

Is actually representable in this very compact form。But what more for general graph。

And so for general graphs， you can start writing the same kind of linear program。 So you could say。

 well， here is a convex body。😊，The convex body is the set of all vectors x， which are non negative。

Such that， if I look at。Any。Vtex v， and I look at all the edges。😊，Which are incident to the vertex v。

 So this is my usual notation for the boundary of V。

If I look at a vertex v and I look at all the edges that are coming out of it。😊。

This set is called the boundary of V， which I'll always denote by this partial of V。Notation。

 its just notation。 So all the ages E， which contain the vert X v of X E must be equal to one。😊，Okay。

 this is just compact。Even more compact than writing this。

 And this is really equivalent into writing this。Okay。So I can ask。

If I wrote just these inequalities。For a bipartid graph。

Is this polytop the same as the perfect matching polytope the answer would be。😊，Yes。

This is this object day。But what about a general graph， And the answer is。What's that。

 You don't think。 So what's an example。So whats an example where this body。 So here is the fact。

 of course， it's the same factor as before KPM of G is a subset of this K。

Every perfect matching is still in here。 Can somebody give me a point which lies in K。

 but is not in K PMm of G。So， basic。I'm sorry we have a， so for instance。

 you could have a graph which which just consists of three vertices。😊。

This does not have a perfect matching。So， that polytop is empty。But on the other hand， the point。

1 half，1 half，1 half。Belongs to this poly。What if I say， well in that case you know。

 this is a trivial example because if a graph has only three vertices。

 it clearly doesn not have a perfect matching。😊，So I shouldn't shouldn't even consider this such a graph。

Can somebody give me an example on。A graph with an even number of edges。Just two triangles。

 two triangles。 Thank you。예对。One half， one half， one half。And this is a point。I mean。

 there are a whole bunch of other edges。 Let's imagine that it is a complete graph。

But this is a point that's inside this polytop。But is not。A convex combination of matching out。

So what should I do。So this object。 And okay， so picture in my head， right。

 So a picture in my head is。This is the perfect matching particle KPM。

And what we have is I've made K。And K happens to be bigger。It contains KPM。

 but it contains other points as well。I don't want this。No。Perhaps still has ever。

This graph so this is why I said， imagine the the， the complete graph， really out there。So。

 so for instance， imagine the following。Graph。This graph does have a perfect matching。

 the yellow matching。😊，However。So， for instance， imagine that the yellow edges had weight。1。

And the white ages had weighted too。Or the white ideas like ba， you know， whatever， something。

So if I was trying to find a max weight， perfect matching。

I would pick the white edges because they seem to be much more valuable than the yellow edges。But so。

 so this is like a cheating matching。Fair enough。Be happy with this。

That this object is actually this this cake。😊，Is actually bigger than KP。

It has points which are not representable as convic combinations of。嗯。Of。Matchings。So。

 what should I do and this is an idea which is known as sort of a cutting play method。😊。

What you should do is you should throw in constraints。And what are constraints。

 constraints are objects which you know throw away parts of the space。They say， oh， no， no， no。

 you should be on this side of this constraint。I forgot to write this constraint。

You should be on this side of this constraint， and so on so forth。So I should write more constraints。

Each of these constraints， know， you can call them constraints。 You can call them cutting planes。

 you can call them whatever。So we should write more constraints。And what constraint should be right？

So。Here was one proposal。So what's the problem with this solution。

 this white solution that we came up with？Here's one problem。Suppose I take。This sec。

It contains three vertices。Any perfect matching must have how many edges crossing this cut。

At least one。But this solution doesn't have any of them crossing。 I mean。

 has no mass crossing the cut。 So we should say X， E。S over e in Delta S。Must be at least one。

For this cut。Good， so for this cut， I should throw in this constraint。 and， in fact。

 I should throw in this constraint for all S， such that the size of s is on。😊，Every odd set。

I need a perfect matching， right。 So if there's an odd number of vertices。

 there must be at least one edge crossing the car。😊，These are known as valid inequalities。

 because these are true for every integer solution that we are trying to。呃明 day。

So this is a valid inequality。The point， you know， of course。

 is that even after adding these inequalities， this。😊，In this， this containment is still true。

Every perfect matching satisfy these inequalities。And the interesting thing is that now what theorem says and this theorem is again due to Eddmunds。

 who did a lot of the pioneering work。😊，In this， in this area， especially in matchings。嗯。嘅 b m 。

那是还必道。Once you have the offset inequalities。This object。

 this polytop is exactly the perfect matching part。😊，人工。Because we want。やほ多。So the question is。

 what point are we trying to make？😊，So I said this was an annoying object to deal with just because it was so unwieldy。

 I had to define it in terms of the vertices of the polyto。😊，Okay。Exponential number of vertic Cs。

 Oh， I'm Im， you know， I'm all worried。 So I， I come up with another representation。

 which has an exponential number of constraints。😊，All this work for nothing。But。

And quite defeat the point。 And this is going to be kind of the punch line。 So two things。

 One is that often you can solve this LP。😊，Without solving this therapy。

You can come up with combinatorial methods to solve this LP。😊，And， you know。

 you could do the following。 You could somehow come up with a solution to this LP。

 come up with a solution to this duall。😊，To the dual of this LP and then ensure that they have the same value。

Ensure that these are optimal。 We've already seen this for arborescences。

 We found Minco arborescences using， or at least arguing using LP， which was exponentially sized。😊。

So still， this is a useful object。And secondly， well come back to this later on just a bit later。😊。

That you can solve these LP without actually writing out these L。And this is going to be one of the。

 again， one of the crown jewels of， of optimization， I would say， in general。

That you can solve L P of exponential size。Provided， theyre nice。And I have to define what nice is。

And we'll come to that in a couple of lectures。And those of you who know what a separation Oracle is。

有。嗯。But those of you who don't just wait for three lectures，4 lectures。Something like that。無理なす。This。

 this LP is still going to be very powerful。Yeah。One， one， yeah。

Maybe I'll come back to this towards the end of the lecture。 If we have more time， we。

 we'll discuss this LP。 this is very， very nice LP， very interesting connections。😊，なす。But。

 let's get back to showing。For the bipartite case， I want to show。That this LP。Is actually。Exactly。

This LP is equal to the perfect matching product。And in fact。

 what I'm going to do is I'm going to give you yet another algorithm。For finding a。Max weight。

 perfect matching。 Actually， I， I， if I remember correctly， last time we talked about a mini weight。

 perfect matching。😊，But， it doesn't really matter。You know。

 every perfect matching has how many edges。And over two edges。

So you could add the same number to every edge or no， so you could negate。The weight of every age。

And now you could ask， you know， for Min weight， perfect matching， Max weight， perfect matching。

 They're the same thing。So what am I interested in？

I'm interested in finding a max rate perfect matching in this graph。

And I might need some sort of animation。 some Im gonna of。Try to cheat and look at my。

Drawings out here。 I clearly need bigger drawings。 I can barely see。Okay。

So I'm going to draw an instance out here。Three。I think this is the one。This is a bipartite instance。

I have some。Weights on the edges， I want the max weight perfect。And really。

 there is a story that goes with this。 There are。嗯，那个。Items out here。And there are buyers out here。

Each buyer has a value for every item。I want to assign one item to every buyer。

 So I want to find a matching between items and buyers。Such that this matching has high value。

So the now， instead of a weight， I just have a value because it makes it easy for me to remember。

 high value is good。 High weight， you never know。 High value is definitely good。So VIj and the value。

哦。I。By。好完了。By。And what do I want to do， I want to。那行啊。そ。V I J， X I J。Such that。Sation X I J3ドオG。VI。

Somewhere the all I X and J is equal to one3 of D J。Ex。And by N items， I want to maximize the value。

By the way， in the， in the sort of， if you were talking to an economist， they would say this is。

The social welfare。I'm assigning items to people， and I'm looking at how much happiness people are getting。

😊，This is called the social welfare。Okay， so I want to maximize social welfare。

And I'm making these connections because， you know。

 I won't get a chance to talk about this stuff later on。

 But there is some very nice connections that will come on。Good。So I want to find a matching。

 And the way I want to do this is there's going to be a market associated。

And therere going to be if theyre markets， we know that there are prices。So what are we going to do。

 we are going to have a price。😊，So every item is going to have a price。This is very。The one the two。

So a price for every item。And now， given a price。A buy it。Dive some utility from the item。

So I'm going to define a utility。Of buyer。Jy。Given a price vector。And， in fact。Let's。

 let's just say that you。系啊。So let me actually call this U IJ。So what am I saying？

Bio J is looking at item I I is for item。J is a buyer。 I could call it B。

 but let's just stick with J。How much。Utility， does buyers J get from I to I。

 It's how much value they would get from item to I。Minus the price that item I is currently selling。

This buyer has to give money。To buy this item。 So this is the neck utility。 This is kind of the。

Sort of value， minus price。嗯这款。Buyers are utility maximizers。 Sorry， buyers are utility maximizers。

You know， so each buyer。Has by J has。Rereferred。Items。Whats the preferred item for Berj？It's hard。

Max。Overall。Items， I。Of u I J。はスピ。The buyer sees how much utility it gets from item 1， item 2。

 item n。It looks at the maximum of those utilities at the current prices。😊。

You know that that that brownie cost me 10 bucks。 I don't get that much value that much value from it to justify the。

嗯。The， the price， my utility is low。Like cookie， which I don't like otherwise， but it's free。

 You know， maybe it's good。So it' is looking at all the items at the current prices and it' is looking at how much utility it's getting from each of these。

😊，And this is these are the preferred items。This is a set of items。Okay。

So let's look at what happens。 The market， you know， the market opens。 everybody's got price0。

So let's， let's do a little。Example of。So the prices were zero。Buyer1， let me call these guys' names。

 A， B， I C。M make it easier what buyer is preferred item。おあざます。one。Ber has one preferred item。

I don one。And it's U63。Ber B has。Go on again quick。1 and two。the price is zero。Yeah。

 let's say they're starting at  zero。Bercy。one。Okay。Each buyer wants to buy only the preferred item。

Bless you。So we draw what is called the preferred graph。

These are all the edges which correspond to preferred item buyer item pairs。

If this preferred graph has the perfect matching。Weas them。There might be many perfect matching。

We choose one of them， and we assign items to buyers， according to this perfect matching。So。

 I'm going to write down the。Algom on the side out here。 I don't know how much room I need。

 but we see。So the all those says。Create。Re forward。G。GCP。エGピ。Has perfect matching。あ。Okay。Otherwise。

This does not have a perfect match。What should happen？Rise the price until you keep。Raise the prize。

YouItem 1， everybody wants item 1。It's in high demand。 Clearly， its price is too low。

You should raise the price。Solect the price of item1 become one。What's the new matching。

What's the new preferred graph？B a。Still has。This is a preferred edge， but its utility is now two。

What about buyer be？You're just going there， right？Because now， it has two。It is。2 edges。 bless you。

 It is， you know， it had two edges of， okay， so what's the utility on this one，2-1，1。

The utility on this thing is 1 minus0，1。The utility on this edge is 2-0，2。This is a preferred edge。

 unique preferred edge。What's the preferred edge for buyer C。哦。Sickment you。哦， o。What's that？这这个可以。

So previously it had values 3，2 and1。But now， I mean， in fact， it still has values 3，2 and 1。

 but the utility become 3 minus-1，2，2 minus-02 n。😊，Okay。Does this have a perfect match。

This had the perfect mention in this case。And we stopped。Otherwise， we would find another sect。

So let me let me actually say， suppose G doesn't have a perfect matching。😊，CanSomebody tell me。

What will happen in an sort of unweighted graph。If in an unweighted bipartidite graph。

 if you don't have a perfect matching， can somebody say what must have happened？It true。What's that。

No， no， no， You screw。 I understand， but can somebody say like what， what structurally， what。

 what should I have found。Youll like increase the price。

 you'll keep increasing the price of something Yeah， so， so the question is。

 whose price should I increase。So you increased who like？Yeah， but there in this example。

 there was a single person and most people wanted it。In general， what should I do。So in the。

I need a procedure that， you know， there's some number of people want some said， you know。

 there's no perfect matching。What structurally must happen if there is no perfect magic。

This is hall's condition。 So if you haven't seen hall's condition before。

 it's equivalent to kig theorem。And just let me take it， you know， say it and take it on faith。

 And if you know， we， well discuss why whole condition comes up。If there is no perfect matching。Then。

 there exists a set。Yes。Of buyers。With。The neighborhood of the sec S。

Being strictly smaller than the size of s。The number of people in the set。Want items。

Which are too few。This is Hall's condition is getting violated。There is an over demandded sector。

I should raise the price of the over demandmanded center。Raise。A price。哦。哦。I in。

So reason you could raise the price of those one。Here I could have raised the price of both one and three simultaneously。

Because what I could have said is that， look。The neighborhood of faith。You know。

 what I really said was， oh， the neighborhood of。O， what are over demanded sets in this example。玩的。

So hang on So AC。Is a set of two buyers。Whose neighborhood is one。This is the proof。

That this graph does not have a perfect matching。But also ABC is the set of three buyers whose neighborhood is a size too。

😊，So， I could have。Raise the price of both。1 and 3。 Let's see what happens in that case。

 Let's just do this。What changes？A's preferred item is still one。B's preferred item is。Still。

 one end。Actually， these preferred item will become 1，2 and 3。 All three are preferred items now。

C's preferred item is。2。one。Right。No。2 and one。Because C is getting value3 3， but paying one。

 So 3 minus-1 is 2。2-0 is 2。So these are still the preferred item。And now I could have。Assigned。Yeah。

 the same perfect matching still exists。But maybe other perfect matchings， also。

Do other perfect matching exist。No no noO。Let's stick with this one。So the algorithm anyways。

 the algorithm is the following。Create a preferred graph at the current prices。

If this preferred graph is a perfect matching assign， according to the perfect matching。

 my claim is that this will be optimal。😊，If not。There's an over demanded set。

There is a set of items such that more people want it than there are items in this set。

Raise the price of this。No。Cl。So we are trying to solve this problem。

 We are trying to solve a max value， perfect matching problem。是单做一点。Every。

But so somehow we are choosing。我认。Sure it's updating them，absolutelybsolutely。

So we want to solve just this problem。Maapps value， perfect matching。The prices。

 the utilities are all part of our algorithm。And the way we are doing this is we start off with prices。

 we。We try to see if everybody is happy at these prices。

 if everybody can be made happy at these prices， we are done。😊，If not， we raise prices。

Until this process stops。行改。The G graph is unweighted。There are several questions you are asking。

Well。First of all。Why is assigning according to a perfect matching， O K。And， secondly。

Why will this process ever converge。And thirdly， where did this come from。

How would you come up with this stuff right。So let me answer these questions，1 by one。

I did not say here how I'm going to raise the prices。So let me， let me make things a little precise。

 I'm going to assume， and this is not necessary， but it will make my life much easier that the values are all。

😊，Non negative。And they are integers。Okay。So， all values are integers。😊，So initially， oh， by the way。

 I'm going to say initial prices are all0。And when I raise prices， I raise prices by one。

And you'll see， you know， almost all this， you'll be able to immediately see， oh， I should， you know。

 if these were rationals， I should do bh。But， we'll do that。Other questions about this algorithm？

Questions， I feel like somebody should ask a question， yeah。そ是个可。Yes。

 so so this algorithm is going to be like weekly polynomial。

 it is going to really depend on the I mean， if the weights were very large。

 then this could take a lot of time。😊，But really， you shouldn't raise the prices by one。

 you should raise the prices enough that something interesting happens。Etettera。

 So there are ways of optimizing this， but I'm not going to do that。 There enough going on。

Other questions。So in order to understand this guy。You should do what， you know。

 very often I do when I see a linear program。I write the door。

Now I want to write the duall of this linear program。So let's write down the duall of this thing。

the dual of a maximization problem is a minimization problem。Let's say that the variables are called。

 what should I call the variables。我在。All those the variables up are there up up there are called X I J for the duals I need variables corresponding to。

Items。And buyers。Just for the heck of it。Yeah， I'm gonna， you know， I'm going to call these。啊。Bs。有这。

What the heck？I need two letters。 These are as good as any。And then I'm saying B I plus U J。Is。

Greater than equal to what。Yeah。For all lines。OK。Any other constraints。No， no， you know。

 there are equality constraints up there。 So they， you know， in the dual。

 there won't be any non negativity constraintsstrain。It's one of these  quarks of linear programs。

 You know， whenever you have equality constraints in the primal。

 the the dual variables are unconstrained。So these are the only constraints。Veryair enough。

We can think of P I as prices。And UJ is is utilities。Yeah。In our algorithm。We define some prices。

And we define some utilities。So we defined the okay we defined a utility for every pair。

So let me actually do one other thing。 Let me def。Utility for a buyer。To be equal to U J。At prices P。

 let me define。To be。Max overall。Bye。It's the utility that buyer J gets from their favorite item。😊。

I have just defined the utility of a buyer。At the current prices。How much happiness are they getting。

Suppose I gave you a third of prices。So given any set of prices P。I have defined。

 according to these prices P。 I have defined U J of。B right。The question is。

 do these prices and these utilities satisfy this constraint？😊，How did I define the utility of bioj？

Their maximum value。So， you know， this is biologyerj。

 this is their preferred item and suppose they are getting$7 from this edge。😊。

Then how much utility are they getting from this edge。At most 7。At冇性。

And so so this is just saying that the value of this edgech minus the price of this item I。

The value of I J minus price of I is at most。U J。That's true for all。For any edge， this is true。

So this is just saying V is less than equal to U U J plus P。So given any set of prices。

 these utilities。😊，Satisffiyed。The dual constraints。Happy day。

Given any prices of defined utilities for every buyer。These satisfied duality。

So they give me a lower bound。我啲学嘅嘛。Good。Now you see， you know， you're already seeing or maybe like。

There's a method to this magnet。The dual variables are capturing how important this item is。

What should its price be。And this is exactly this economic interpretation of duals。

But I'm getting ahead of myself。Two things to show。Suppose。GB。Has a perfect matching。

Let's look at that example up there。GP has the perfect matching， right？GP and the perfect matching。

 let me just do it for that example， you'll see exactly what I mean。😊，What's the value of this edge？

The value of this edge。Is equal to。The price of this item， actually value minus price of this item。

Is equal to the utility of this buyer， right， So this is P。This is U J。This was an edge。

 in the preferred graph。With equality out here。We want their reach be。3个人。So hang on。

Let's not even talk about tight constraints。 Today is not the day for tight constraints。Today。

 the day we're talking about just optimality prices and stuff。Look at this edge。

The value is equal to the price of this guy plus the utility of this guy。😊。

So if I sum this up over all the items。The total value， summation。VIJ。

I J belonging to the matching is equal to the sum of the prices of all the items plus the sum of the utilities of all the buyers。

There was the perfect matching。Every item got sold。So every item appears in that sum out there。

Every buyer got an item。So every buyer appears in that sum out there。

Every edge of the matching appears the next。です。Is a solution to the primer。

This is the solution to the duall。They have equal value。This is feasible for the prim。

This is feasible for the doo。I have a primal solution and a dual solution of the same value。

Both must be opt。We are done。This is often known in the jargon as market clearing prices。

 I said some prices。Everybody took a favorite item。All items got sold。All buyers got items。

Market clearing prices are optimal。We just proved。Be good。Something's worrying， Charlotte。ok。Yeah。

やります。Are there many possible market clearing prices， yes。So， for instance。

 I could raise all the prices by one。Also， market clearing prices。No。

It's slightly protein interpret because。There's no。I guess in the thing that we're trying。Mhhuh。😊。

Absolutely。They the real world。And we're like， okay， well， this is market。

billionionThat is an uniqueli good solution。Okay， so so let me come back to that。😊。

So that's the difference between social optima， social welfare and other notions， which Yes。

 so maybe you're one step ahead of me。 if you throw in the seller into the bargain as well。

 So you know， all the buyers are there and there's also the seller。

So if you look at the sum of all these things， then that's being sort of raised overall。Good。

So that was one thing。 I found an optimal solution。 So if this beast converges， it will be optimal。

Will it converge。Let's look at that。So okay， so why will it converge。So for this。

 I'm going to write down a potential。Actually， know， the potential is。Someumers take a potential。M真。

来。You need a summer API and you。Yeah。Good。What's happening。Remember。The duall。

 so I'm trying to maximize my value。So this is， you know， this is the primal。咁데 저度。

Every time I give you prices， I give you a feasible to us。I'm trying to minimize the do。

Trying to maximize the primer。My claim is going to be。In each it。The total dual value。Decreases。By。

At least。It'll start off at some large value， and it'll keep decreasing。Okay。Why is this true。

So at any point in time。What did I do？はし。What did I do。At any point in time。You know。

 I checked it whether they're the perfect matching， if they're the perfect matching， sure。

 everything is fine。 We have an optimal solution。😊，If there is no perfect matching。开始。

I'm increasing the prices by one。The value of the utility of all these guys is dropping。😊。

It's dropping by one。These guys went up by one。Their utilities dropped by one because their favorite item。

 their prices went up。😊，But this set of buyers is bigger than this set of items。

So the sum of prices plus utilities drops by at least one。Okay。We happy。

So we making progress at every step。Oh， by the way， yeah， I haven't told you one important thing。

 right。I start off at some， you know， what could the initial value of the duall be。

Maybe the sum of the values， whatever， some very large quantity。

What's the lowest value that the dual can have？Just the。Conmotiontion to the。The solution to the LP。

 which conveniently have already assumed that the V I J are non negative。

So the solution to the LP has value at least 0。Right。

It's like if there's a perfect matching that then you have。Right。

 so if there's no perfect you have like two things subscribe to the same item， then you like。有我不是这。

So， so， so， so what's gonna happen is maybe， you know， here。

 I was assuming that there was a complete graph。 I could imagine that the values are 0 for all ages that are not present in the graph and stuff like that。

 Firstly， you should check whether your graph is a perfect matching。😊。

The graph doesn't have a perfect matching。 Then it doesn't have a mean weight。

 perfect matching or max weight perfect matching。 We don't even need to go any further。

 So there's always the perfect matching。The is perfect matching。

 If you assume that the weights are non negative， then， you know， you have an upper， you know。

 you don't need to assume the weights are non negative， but you know， you， you have some。

 some bound on how low the dual can be。The dual will start at some value。In every iteration。

 it will decrease by at least one。It'll stop at some point。When it stops。

 we would have found a perfect matching。 And this perfect matching would give you the optimal solution。

😊，So the algorithm is just this。 The algorithm is just there， right。At every point in time。

 look at the prices， everybody says， I want my favorite item。😊。

The favorite item graph has a perfect matching we are done， if not， raise prices， keep going。一直。

So this is sort of a price raising algorithm。It's essentially。Okay。So actually。

 before I go into philosophical and historical remarks， questions。开始。我个。一推。

The prices keep exceeding the values。Yes， so， so， for instance， you know。

 exactly the example you you， you saw， you know， there are two people。And they only want one item。

Then this， you know， this will go on forever。Because this price will keep going up and up。Br down。

If there are other people， if if there is a you know， there should be some value to this market。

 whatever the value to this market is， that's where the process will stop。

Is there like a dual dual version， so like here I'm thinking。呃。

You give it a loose circumstrain that you can take as many items of each item as you want。

But is there like in opposite or like the seller sell to？Oh， I used。And have to think about that。

 often， I don't know。嗯。Good， okay， so this algorithm， by the way， is。😊。

finds you max weight perfect matching。 also， you know， by just flipping the signs， Min weight。

 perfect matching。 And you can extend this to non perfect matching， all that sort of jazz。 you can。😊。

In fact， one of your homework problems actually talks about market inspired algorithm for。

Perfect matchings。 Oh no， for， for finding matchings in general graphs。嗯。With fast run time。

This algorithm is essentially the Hungarian algorithm。😊，Of Harold Khn。

He wanted to solve a matching problem back in the 50s。

 he went and read some papers and he found papers by these two Hungarian guys。

Egggervari and and Kaig。And so he wrote an algorithm called the Hungarian algorithm。 because。

 you know， were these two Hungarian guys who written papers that。And he is very clear about it。

 He says， you know， the ideas are essentially in this， in this， in these papers， I'm just。

Reating them。And then other people restated his ideas later on。

 people found out that Jacobbe had already found this algorithm， et ceter， it's again a mess。😊，But。

This presentation。Is。Is slightly more modern。There's some notes on the course web page。嗯。

There's some， some nice connections to。嗯。To things that you might have seen。So。

Let me just mention one thing。Suppose。There are end buyers。And there's only one item to be sold。

There's essentially one item to be sold。Now， in order to put it in this framework。

 I'll create n minus one other dummy items。And Ill create。

 I'll say the value of every buyer for these dummy items is0。So I'm creating a complete graph。

Where n minus1 dummy items such that everybody has value0 for these dummy items。

And there is this one item。And each of these buyers has a value。For this one item。

 And let me just call this value V1， V2 F to V N。哎。Let's run this algorithm on this。the。

What's going to happen， Price are 0。And let's imagine everybody's value for this item is non negative。

It's a painting。 It's a monet painting。Everybody wants this item。

 The preferred graph is going to be just this。And then， the prices start rising。Okay。

 and let's say that the the the price， this was like， you know，100。 and this was like2。

And the price is at， you know，10，95， etc cetera， down to 2。 Suppose they are ordered。

What happens when the price out here becomes2？Re毕。This guy。

His preferred graph now contains all these other edges。When the price becomes 3。

 his preferred graph only contains dummy edges。As the prices are rising， more and more people。

 they prefer going empty handed。To buying this item。When will this process stop。I'm sorry。

When you get to V 2。When you get to 95。V 2 and V1 will both want this item。When it gets to 96。

We are the perfect matching in the graph。Okay。95 plus epsilon，Actually， there is a perfect。

They're the perfect matching。 They're the perfect matching at 95。😊，The process stops at 95。

What's the price at which this item is sold。95。What's the significance of 95。

The second highest price。 This is only the second price auction of bakery。So this， this， this is。

 you know， the start， you know， this is kind of the basics of a theory。You， you start talking about。

 you know， auctions and how to set prices。And this is somehow saying that the second price auction。

In fact， is， you know， we short that the second price auction is a truthful auction。

 Nobody has an incentive to lie。So the prices you get is you know， exactly the second price options。

And in fact， what you can do is you can run this algorithm。And get prices for general matching。

 So now you have2，2 monet paintings to sell。😊，These these people have different values for these two monet paintings。

You want to price these two。To maximize the social welfare。You have N rooms to allocate。

 You are a university called Carneinggie Mel University。

 You have N rooms to allocate to end students。 Each student has the value for every room。

You want to assign them in a way to maximize the social welfare。 How should you assign them。

You can run a pricing mechanism。You don't have to ask people for what their values are。You know。

 the beauty of this whole thing is you didn't have to ask people what their values were。

You just set the prices and then people vote with their feet。Here， I just， you know。

 said the price to there。 all these people say， yeah， yeah， I still want to remain in the room。

Then I said the price to3 or price to2。 This person said， I'm out of here， guys。Right。

You don't have to ask the people for their values。You set the prices and the people vote with their feet。

This ensures truthfulness， because I didn't need to ask you what your value was。

So what you can do is you can find matchings。Such that the allocation is truthful allocation。

And this is one special case of a mechanism known as the Wiy Clarks Grove mechanism。😊。

If you play around in， you know， a little bit in sort of algorithmic economics。

 you'll see this a lot。 V C G， Viy Clark and Grovees， they won the Nobel Prize in the year。

 Hong Kong， whatever for their work on auction theory。😊，They came up with a general mechanism。

Which ensures truthfulness。Nobody has an incentive to lie。

The price raising mechanism produces VCG prices。 Nobody has an incentive to lie。I don't have。

 you know， time。 Itll take more time and effort than one can put in the rest of today's lecture， but。

You can， I can point you to references。 You can have a look。In fact， maybe I'll， I， I'll mention。

 you know， I'll take the question and I'll mention a different way of looking at V C G。I。

 I'll tell you about that because it's cute。 And， you know， every time you see B C G。

 it will be kind of like a mystery。 But yeah。And guarantee that alls not negative。

All the buyers have non negative utility higher。So in this case。

 if you are thinking of you know people in rooms， then everybody will have to get a room。

 So this is for the perfect matching setting you can extend it to the situation where people have like you can just add in dummy items。

😊，So that people have zero value for that item。 This is exactly what was happening out here。

 When I said the value too high， when I said the price too high。

 this person just defected to the dummy value。 So you can do that。 and it'll work out just fine。

But in this case， I was looking for perfect matching， perfect on both sides。😊，So maybe， you know。

 actually，4，30。 maybe let's， let's stretch for two minutes。 and then I'll let me tell you just。

You know， this whole thing about VCG prices。Let， let's just look at the following experiment。

There is a single item to be sold。 Theres N people with values in it。

Who should I give the item to and how much should I charge them。Me。I'm trying to， you know。

 I'm the benevolent dictator。I want to give it to the person who values it the most。

But if I just ask you， how much do you value it， you will say 1 trillion。 I say。

 how much do you value this thing， You'll say 1 trillion。And then somebody will say， oh， plus one。

 then you know，Truthfulness is not guaranteed， right。This is why we go for the second highest value。

Okay， but here's a different way of viewing it。 You know。

 the second highest value seems a little arbitrary。 So let me mention a different way of viewing。

This item， I'll ask everybody for their bids。 You might say。

 why am I asking just after I said I don't have to ask you for the beds and stuff。

Let's consider this auction。 Im want to ask everybody for the bids。

 I'm going to give it to the person who bids the most。But I'm not going to charge them。 So， you know。

 of course， if I say， oh， you bid some money and I'm going to charge you that money。You'll say， oh。

 this will you 1 cent。The other person will say half a sentence。 You know， we， we go towards。

So if I don't charge you anything， you will bid over bit。If I charge you what you what you bid。

 you land up paying。So that's why I charge you the second highest pay。But here's a different way。

YouYou can say， oh， I'm going to give it to the person who bid the most。I'm going to take your bed。

But I'm going to subsidize you。Yeah。How much am I going to subsidize you， you by being in this room。

 you by bidding。Make the world a better place。If you were not there。

The value of this painting would have been 95。Because of your presence。

 the value of this painting is 100。You made the world a better place by fire parks。

I want to give you back5 bucks。Hundred -5 and 95， which is second highest。Good。Now。

 I have two identical paintings to sell。Moonnet painted two identical paintings。

Each person wants only one painting， by。Theyベ onです。Who should I give it to。Well。

 I should give it to the two people who beat the most。How much should I charge them。Same principle。

You say， well， you know， if you weren't there， the high the two highest would it be 95 plus 65，1，60。

😊，Because you are there。 It's 1，95。That's 35 bucks extra。 I'm going gonna to give you back 35 bucks。

Same for the second one， you know，1，65。You made it 1，95，30 buck，This principle。

Just extend to general sets。Is the VCG mechanism。You find the solution， which maximizes the value。

And then for each person， you say， well， if you want there， the max value item。

 the max value solution would have been blah less。You made the world a better place， by。

This difference， Im want to give you back that。And if you sit and work it out。

 you realize that everybody makes a calculation， How much should I bid。 Well， if I bid， if I overpa。

Then， you know， I might be paying too much。If I aren bed， then I might not be making the cut。

If I be somewhere in the middle， I might not be getting back enough rebate or something like that。

 You say， it's not worth my effort to lie。 I should just tell the truth。

And this is the VCG mechanism。I'm not saying that you should， you know。

 if you didn't understand anything about V C G， you， you'll go ahead。 you know。

 you'll be an expert on this。But now you just， you should go and read up whatever you want about PCG。

 if you're interested。This is the principle。And like zooming this break down。If people collude。

 then Im assuming this will break down。 Yes， right now， at least as far as I can see， theres。

 you know， this assumes no collision。Because otherwise， the top two people could say， oh。

 I'm going to bid this。This is。Individually rational。Yeah。向こは。そです。In this case， it's a single bit。

You can think think of like someone's controlling。Yeah， but no， no， no， is a simple game man。

 You know， we we are in those sort of old movies。 You guys have seen north by northwest。 you know。

 people standing there bidding for anyways。 O， I have 10 minutes left。😊，啊。

Let me tell you a little bit about the perfect matching pal of little bit。Yeah，那我问。

questionions之 okay。For this scenario with too money paintings。

 So how much is each person paying Okay， so how much is this person paying？

This person is making the world better by 35 bucks。So this pays0-35。You see Y 35， right。Because it's。

 you know， together， they make 1，95。 If they weren't there， the best solution would be this。

And this person would say， well， if this person wasn't there， the best solution would be this。

So they are making the world better by。30。So this person pays whatever this person pays whatever him。

You can do the calculation。 I think both of them pay 65， the third one。

But now you could have different situations。 You could say， oh， this painting， I like more。 You know。

 it's got the little gilded frame on the side。😊，So I value this one at 95 and this one at know， 99。😊。

And now you can， you can start to do all these calculations again。

 You can say what's the best allocation with everybody。😊，And what's the best allocation without me。

What I pay is the difference between these two。Okay， or sorry， what I get back is the difference。

 I pay what I paid。But I get back the difference。How much I made the world a better player。

So let's look at the third person。I'm claiming the third person pay 65。But what do they get back？

But actually， the third person doesn't get an item。 They don't pay。 Sorry， I I'm just hall night。是。

いたまり。Yes。Yes， so if they bit this much。They would， you know， whatever。They were yeah。They would pay。

1 trillion minus。The difference。Exactly。So the top person， yeah， if you had extra for me， I mean。

 yeah， So the top person definitely does not depend on their。 theres a segue。

 It's got nothing to do with the rest of the course。 I won't have time to get into this。

 I'm not also a specialist on a theory， but this is， you know， there's a little bit。

 There nice connections that come out。And。That， yeah。And often by viewing。

 So maybe I I will make a pitch for if you view dual， sometimes duals。

 you want to assign meaning to them。In this case， prices were a very natural meaning you could assign to them。

So often， you can think of what is happening with the duals。That's a good algorithm design strategy。

What the heck are they dual telling me。Good。There's only five minutes left。

 Let me mumble something about the perfect matching Paul I talk。嗯。

Let me mumble something about the perfect magic point。 It's too nice not to say anything。

So I have a general graph。I want to capture all perfect matchings。So I wrote that poly talk。

I want to argue。That this polytop。If equal to the perfect matching polytop。

It's exactly the perfect matching point。So how would I argue？O。And I'll give you a proof。

 it's late in the day。 I realize take a deep breath and just just see how the process works。For。

I want to say， let's take a corner of this polyto。Right before。

I want to argue that the corner has is in integral。Okay， so take a corner of this。

So let's say x is the corner of this。Let's look at the support of X。All the edges where x is non0。

As before。You know， we saw well。Suppose there is a tree like structure。Then。

This vertex must have one unit coming out of it。 So this edge must be one。

 and then there can't be any other edges incident to this other vertex。

So there will be a bunch of edges in the support。If there is a cycle。Of even length。

We did this business， right， We added plus epsilon， minus epsilon。

 We wrote this cycle as a convex combination of two other cycles。😊，And said， oh。

 this can't be an extreme point。Okay， so even cycles I get rid of。But the support as stated。

 could have orderline cycle。是。I can't do this plus minus business。I'm stuck。你看个。Andの so。So， if。

So if I had any even cycle in the support。I'll claim that this is not an extreme point。

 because on this even cycle， I could do the plus minus this。

I could write this solution as a convex combination of two solutions。So what do I have。

 The support really consists of a bunch of edges， plus possibly a bunch of odd cycles。Ohやば。

And if I have an odd cycle， you have an。It's。If I have an odd cycle。

 what should the x values on the edges be？Half。That's the only thing the ages can have， know。Half。

Good。It can also be just like A and。No， oh no， no， Yeah， it's an hard cycle。 That's the whole thing。

Okay。So an extreme point， its support must look like this。Okay。So now let's， let's， let's。

But what next。是。你就现在话用那个对。You take the on cycle。Good numbers are。Because they are。

You can't really have。So this would be a problem。If。嗯。Okay。Here's one thing I need to。Argue about。

So this would be， this would violate the constraint。Okay。

So I thought I needed to do one more argument out here， but I'm clearly。咩啊。Like， what if you got。

Hedges coming out of my all。有文件一个。I guess if you。That edge that's connected to another trying。然后到那个H。

Okay。So I could have。😊，Other structures。 I need to sort of think about how exactly I would have other structures。

 right。But， O。就。I might have some， some other stuff going on。That's what I'm worried about。Right。

So let's do the following argument。I have a solution like this。嗯。Okay， no I' I'm screwing up this。

Let me not sort of waste your time。Let me stop here。 And next time， maybe I'llll。

 I'll finish the proof。 and then we'll take it from。And cyclemh。Coming out of there must be once。

 which means it'。An odd cycle must be as a generic point I listening。Yeah。This would be fine， right。

don't know， if there's like take the biggest offset。ContractNo no no。 I agree。

 contracting should should work， but I'm losing the thread of the argument out here。So， okay， I mean。

 here'm done with。 So， so here is more or less the sort of argument。Look。At this extreme point。

 there are a bunch of tight constraints as well。We've used only this。 you know。

 we were talking about extreme points。But also， at this extreme point， there are a bunch of。

Tight constraints。 How many tight constraints are there， There are you know。

 some number of tight constraints。Either the tight constraints all look like this or there is a set that is tight。

😊，So， the argument we need to make is if this if the constraints only are tight look like this。

 then there is a contradiction。😊，And if there is a effect that is tight。

Then what you would do is you would you know。This set is tight。

 there is one unit of edge coming out of it。What you' are going to do is you're going to take this set and you're going to contract it down and you're going to induct on that。

But， you know， I， I lost the chain of argument。 Let me not go into that。 Let me just stop here。

 and we'll just do it on Friday。Thanks。