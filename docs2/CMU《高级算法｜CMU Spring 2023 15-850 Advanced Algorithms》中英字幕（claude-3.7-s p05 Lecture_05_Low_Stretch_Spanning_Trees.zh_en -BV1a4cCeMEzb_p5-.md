# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p05 Lecture_05_Low_Stretch_Spanning_Trees.zh_en -BV1a4cCeMEzb_p5-

Hey， everybody。So welcome back。Today we'll talk a little bit about low threat spanning trees。😊，So。

 you know， the way I always think of low stress spanning trees are essentially that every metric space on endpoint。

😊，Is essentially a tree。But it's a tree only in some randomized sense。

 and we'll talk about in what sense it is you know it this tree is approximating the graph。😊。

So lets let's talk about that but before I do that let me just give you the plan for today in order to get low rates spanning trees I'll also tell you about low diameter decompositions。

😊，which are an important tool in themselves so even if this wasn't a good application and map this one is very useful so you should know this and then so once we have this tool in our toolbox the construction of low stress span trees will come just like that。

😊，えす。Good。So what's the setting so the setting is I'm given a metric space。😊。

And you know it's much easier for me to think of graphs instead of a metric space。

 it's essentially the same object， so I'm given a set of points and I'm given all the edges between them。

😊，And the way it' satisfied the triangle inequality。Yeah。What's illustrate planet tree？Well。

 it's not really a illustrates spanning tree， it's a distribution over spanning trees。

 but I'm being lose in my vocabulary out here。So it's really a distribution over spanning trees of G。

😊，Such that two properties， horse， two properties。😊，For every pair of ver of the graph。

 the distances in the tree are at least the distances in the graph。😊，And this comes as you observed。

 this is not really a condition， this is just you know it comes from the fact that the tree。

 the sub subgraphal graph。😊，But the second condition is the interesting one。

 which is that the expected distances。😊，So if I fix the pair of ver fees。

 then I take a random tree from this distribution。That the expected distance is going to be at most some alpha times the original distances。

And this is alpha is what I want to reduce， this is what I want to get to be small。😊，And the theorem。

That'm going to show today， well actually the theorem that is known is that alpha equals order log n。

Is possible？What we will do today， R is order log。嗯。Is essentially， and we'll talk about。

 I'll refine this in just a moment， log square。So it's slightly weaker。

 but it doesn't require me as much effort to prove this to you。😊，Yeah。

So let me introduce a couple more pieces of notation that would be useful。😊，And then will be done。

Okay， this often， by the way， this alpha is called the stretch factor。😊，Hence。

 low stretch spanning trees。嗯。And maybe I'll just mention。One more piece of notation。The diameter。

Of a set。As of what he is。In this setting， so S is the subset of this is all of V。😊，嗯。

As to the side of word freeze。😊，Is I'm going to write as。Diameter。Off S。

Is the max overall vertic C UVv belonging to S of the distancecing between UVv？

And I should technically write diameter in G of S， so this is the distance in G。Between UVv。

And of course， one thing that I haven't done is I haven't defined what the distance in G between UVv is the distance in G between UVv。

Is the shortest part of distance。Between。UB。One almost trivial observation is because of this metric property。

The distance between Uv and G is just W UV。The shortest part distance is actually just the weight of the edge。

哎。So I've defined the diameter of a set and also finally， let me just define。Yeah， okay。So really。

 what I'm going to show is not this。But alpha is order。Log。And。Log。Diameter of the。哎。😊。

All these things can be removed， I can go from here to there。And this is a simple observation。

 maybe we'll do this on piaz or something like this。😊，Um， but。

This improvement from here to there was done in back in '96。Going from here to log in。得金。

A few more years， 2003。And this is， as I said last time， I just mentioned it， I'll remind you。

This is alpha。Must be at least， so there are instances。Where alpha is no be than log in。Yeah。

 that absolutely。So in fact， we'll give an algorithm that will sample from this distribution。Inbota。

So the ideals， I mean， it's almost the best you can hope for。

 in fact there are algorithms known which do this in almost linear time。

And this is really useful for past algorithmism。😊，Okay。Good。

 so this is this will be an algorithmic result， completely algorithmic。😊，Okay。对。Other questions。Yeah。

 or what？So the first condition is not really a constraint because he is a subgraphgy。😊。

But somehow I'm used to writing it， I'll write it anyway。是啊。对。

Actually you'll see why I'm writing it because I'm going to come up with trees I'm going to kind of cook up trees and I'm going to put distances on the edges which are not the same as these waves。

 but I'll just make sure that those lengths that I put on the edges are longer than the length that will also be there。

😊，Yeah。Good。Other questions。诶。So the other protagonist of today's lecture。😊。

Is this idea of a low anmity composition？And you know， maybe I should actually like on this。

So what's a low diameter decomposition？So，啊。blue diameter。Be公不在。I often call it LD。😊，啊，对。So， given。

Graph， much as above。啊。And a parameter。嗯。DD。greater than zero。Fd。What I'll call clusters。

So these are just subsets of BCs， V1， V2 up to B K， let's say。

Each of these are subsets of the vertices there is a partition so these which partition。😊，8。

Partition off。V。Such that。Two property food， actually， yeah， such that。啊。The diameter。In G of B。

You like more step day。They have low diameter。Low diameter decomp， okay。

And the second thing I want is that the probability。😊，That an edge。用v。Is cut。

What do I mean by cut so the picture is this。I'm breaking up。This into four pieces， V1， V2， V3， V4。

And an edge is cut if one of its endpoints lies here and the other endpoints where there。对。

So the probability that some edge UVV is cut。I that most， okay， so this is。For every possible ledge。

For every you will be in the a set。The probability that B is cut is。So what should it depend on？

It should depend on the length of the edge， if the edge is long， it should be cut more often。

So the distance in the graph between U and Z。It should depend inversely as this diameter bound。😊。

If I give you a large diameter bound。The probability of an H being cut should be lower。系。Yeah。

And then I want some parameter beta on here。And I want to make this beta as small as possible。

Yeah so that's the goal。Yeah。😊，这个理由。AhWhat's the probability of very good point？😊。

So this process will be done。对。So the low diameter decomposition is also a randomized example。😊，在这。😊。

So let's do a couple of examples just to get our feet wet。Suppose my graph。Is really line。

Of course I'm always thinking of complete graph， so really there is a complete graph sitting on top of it。

 there' is an edge going between every I and J。😊，Of length equal to J minus I absolute well。

There's a complete graph out there， but really think of the line。😊，I give you a parameter bound D。

How should I decompose this graph？好。一个不是。It's like very different do you agree。八。How do you mean？

lect the random point and grab everything within the so select random point and grab everything within distance D over two of this。

 so select a random point go D over two distance here and D over two distance here。What next？Repeat。

Here's a slightly different approach， which is almost。呃。

Exactly the same kind of thing up to constants。Actually。

 your approach will be will come back to your approach in a moment， so here's what I'm going to do。

Start off from the left。And go some。Choose a random offset X。😡，Uniformly。In the range zero through D。

你。😊，何回の支援金がないので。My construction each piece is of size。

It is more difficult to generalize your approach will generalize more， but well come to that。😊，Yeah。

😊，So the the diameter of each piece in the middle is actually D by construction the first it's only the first one which is random and we could we could choose each one of these at random as well that's a perfectly reasonable thing to do so on average then it would be D over two。

😊，But in this case， I'm just doing something very naive。Does this make sense。

 yeah absolutely bigger absolutely so if the smaller I make this。😊，The more I'm suffering， okay？

So let's actually look at what is the probability。😊，Of U and we being separated。In this case。

The distance is so if I look at， say。You andV out here。Just a single edge out here。

 what's the probability that one of these vertical lines will pass through it？One over D， right？

Exactly。The probability， you know， it's basically think of this。

 this vertical line is moving uniformly。😊，Atラ know。好。In a space of width D。

 so the probability that this vertical line goes through this vertical edge。

If the weight is one is one by the。Yess no， maybe good， okay， so in this case。We just gave。

A beta equals one variable。And basically， you know。

 I can't hope for anything better than beta equals 1。

 this is like the best possible algorithm I could have hoped for。😊，Okay。

What would you do if I gave you a grid？😊，How would you cut it up？tolyYou choose to uniformly。嗯。2。

Because then youll guaranteed that each piece out here。

The two vertices are at most D over2 plus D over 2 D away from each other yeah。😊。

is it like a complete graph with blocks between？I just talked about the line。

There are other arcs going there。But there a beauty of this， this guarantee。😊，Is that it doesn't。

Each of these arts， their length was given by the triangle inequality， really。😊。

And linearity of expectations plus。😊，The triangle inequality。这个。LetLet me answer your question。

So suppose I should。That the probability of each edge in this graph probability of each edge ii plus 1。

Hiss God。They at most beta times。1 over this。Then。What's the probability that I comm a J？Is cut。Yes。

Is at most by the union bond。The probability。呃。A K plus one。A going from I to J minus1。Is good。

If I and J are going to be cut。Then at least one of these engines must have been cut。

On this one particular part。And this is at most beta times1 over d times J minus。

So if there's an edge whose length is being given by。Some other part。

Then I can just argue about the edge of the that。So far so。Am I losing you guys， ask a question？

I would like you to understand this stuff。Practice a grid。I cut every d over two distance here。

 every d over two distance there。I get it。呃呃呃。Low diameter decomposition。

 what's the beta parameter for this guy？😊，Now it becomes something like two， right？

Because every little edge out here。Has a 2 divided by d chance of being cut Emma this is because the probability that this edge is cut。

😊，Is actually in this case， at most1 d over2。That's two div。ok。😊。

And you can imagine that if I have a3 by three grade， it becomes d over three and so on and so forth。

It's getting worse and worse， right？over the probability。

 no for a fixed edge because I need to do this argument for every possible edge。😊。

So if I fix an edge， what's the probability that it's got？

I mean your current one is either in three or one because you're tomin so I drew this thing。

 but of course what I'm going to do is I'm going to shift this way and I'm going to shift in there。

Exactly the same way。个人。So what think of for the moment， don't think of the complete graph。😊。

Think of just just this only these edges， the rest of the edges will be in play。😊，Oh。

This is the way you get with。We。Okay so maybe I， you know。

 every year I try to either talk about metric space just think about this graph。😊。

Don't worry about the complete graph， just think about this graph。😊。

And I want to make sure of these two properties。哎。That's all I wanted to about。嗯。

Does that make sense now？Line， okay， great， okay。3 dimensional grade beta equals 3。

4 dimensional grid beta equals 4 log n dimensional grid beta equals log n。

Can you go much further than log in？Yeah。ones woke see。

 but the thing is that each of these edges is either vertical or horizontal。😊，That's all I'm doing。

 right？I'm just looking at the grid。 I'm looking at a very simple example。😊。

So every edge is either vertical or horizontal。😊，又月初号。Right。Oh。Very simple examples。So far so good。

Okay。So it seems like I can get examples where beta becomes two， three， four。

 and so on and so forth gets worse with dimension。But then， you know， once I go to log in dimensions。

 I kind of run out of room because login dimension it's like the hypercube。😊。

Seems more difficult to come up with examples like that where this beta is worse than log ns。

So here's a conjecture that one could come up with that it's always possible to get beta equals log n。

Okay。So let's。What Im going to show you is I'm going to show you aterem。哦。Every。Mantric space。Great。

And points。There exists a low diameter decomposition。Great。例体一コです例体イコです。

If you understand the low diameter decomposition， I'm saying。😊。

There exists low diameter decomposition with beta equals logan。诶。So far so。Okay， let me prove this。

And as always， I'm going to tell you the picture I have in my mind and then hopefully that picture might be useful。

😊，Okay。So I'm going to draw actually two pictures out here。The first one is。嗯。

What am I going to do I'm going to pick a vertex？😊。

And I'm going to look at all points which are within some distance。😊，嗯。So I'll call this vertex v1。

 I'll pick some distance r1。And I'm going to cut out all these vertices。😊，So capital V1。Is equal to。

Well， maybe let me not call this little V1， let me call this center one。😊。

So I'm going to pick a center， I'm going to pick a radius， and I'm going to look at all vertics。😊。

U says the distance from C1。To you is that most are white。

I'm going to take these from the graph and I'm going to throw it again。

And then in the remaining graph Im going to pick a vertx v2， this is basically your algorithm。😊。

I'm going to pick some distance R2。I'm going to remove all these verticcess from this graph。

 so this is really VI is the set of all verticess whose distance from C is at most R。😊，This is C2。

Then C three， I'm going to take something out， C4。S five。C six我。喂。😊，I want to make sure。

That R is at most be divided by2。Okay。😊，So if the distance， okay。

 so this makes this means let me just clean this up so that I can。Nuternneica mess， this is C1。

If I look at any two vertices。You and we in this region。This distance is at most this distance。

 whatever a at most R1？This distance is at most R1， that's2 R1。2 r1 is at most D。

Is the radio versus diameter business factored too？😊，Okay。😊，Therefore， the diameter。哦 v i。

Iact message。Okay。😊，So I've got the first property downpack。I just need the second property。

So here's the algorithm， so let me give you the algorithm。Um。And what I'll call this algorithm。

 I'll call it LDD。On the set of verticcs， so I'll get the set of verticCs。And a diameter bound。

And I would say C。Is an arbitrary。Vortex。嗯，人。嗯。I have to tell you how to choose al right。

And then I'm defining VI。To be。All the ver is you， as we said， says that the distance from CI。Do you。

Is that most RI？And then I just say。啊。This recur。On。V minus VR。WithSame damage。诶。

Thinkk up this piece， put it aside， move on。bigger告。😊，How do I choose our right。

 that's the real question。哎。Hello。Please， okay， geometric with regards to something new overde， why？

Because like。If it's geometric there's a height probability Ill say within some bound that you said so let me ask the polymer question why not uniformly between zero and d over2 Okay so uniformly between zero and the over two that means things that the edge have a very high。

It's very hard to analyze what the chance the two things are going to get cut how far was good so let let let's look at your argument right I like it。

So here's the argument。How is RI being chosen， RI is going to be？A geometric random variable。

With some probability。And what's the geometry kind available。 It's some coin。

 I keep flipping until it come up comes up heads。 I look at the number of flips until it came up heads。

😊，诶。And what's the probability P？And it's going to be。1， divided by。你。Thanks。老公。

And maybe there's some constant sitting out here。Iterine eight， I don't know。Yes。

 I need some corn soup。Forget the concept， not important。Yeah。Let's even forget about the login。😡。

Let's look at a geometric random variable。With probability p prime equals 1 over b。

What's the expected value of this dominant rhno variable？令。

So suppose x is like this then the expectation of x。Is decent。哎。😊，I don't want D， I want， you know。

The expected value of R is going to be d。😊，Maybe I could even make this， you know？都。你嚟姓我咧。Actually。

 I'm probably going to， this is not correct。Good， I should have。Then absolutely。

I want the distance not to be d but D by 2。😡，So I made the probability of heads。

 that' slightly higher。But this just says that the expectation is deep。😊。

There's some chance that we like exceed the expectation， I don't have any room to breathe。😊。

So let me give myself more room to breathe。By making this。By cleaning this up a limp bit？

And making it。Divided by d。8ight times long。You'll see why I log in in just a moment。So this is。

 you know， whatever。エ timesス。You know again。So what's the expectation？Okay。😊，What？That the。

Let me now ask question， what's the probability that x becomes more than d over2？张木林。

Yeah exactly so this the probability of this is really the probability that I got coins so so now this is my fee。

😊，I got tails。Be over two times。Which is at most， oh by the way。

 I haven't had the chance to tell you the most important inequality ever， right？😊。

In the near Yeah yeah， yeah， no， no Cheche is pretty good， it's up there。😊。

This is my favorite inequality ever one plus X with less interview。😊。

Goown through the picture is that right？So let's use this， so this is e to the minus p d over 2。

Which is p times D is very conveniently8 log n， so this is E gamar4。Log in。

 all my logs tend to change their basics whenever they need to。But right now they are base E。

 so this is like one over n to the slope。对。😊，So， the probability of。

This radius being small is very tiny being large is very tiny。😊，In fact。

 the probability of any of the radii during this process being large is very time。😊，Okay。

 so this means by union bound。Says。The probability that any。Our I is bigger than the over2。

Is less than one over I don't know why I needed eight， it was just some number。

Because every time I take a verortex， I can cut out that verortex。😊，So far so。So this process。

Is with high probability， it's giving me a radius bound that's not too large。😡，G。Last piece。

 this is actually the sort of cutest piece。😊，What thatOh okay， you know who reads the lecture notes？

😊，Just yeah， that's。 I need to。I needed to take a pass over this， but I'm here。

The paper deadline today。O。Okay。So the diameter bound is okay with high probability， but it's okay。😊。

あ。What else do I need， I need the probability that an edge is playing country。

So I need to bound the probability that edge。mus逼。か。哎。And for this， I'm going to draw a picture。😊。

In fact， I going to draw the other picture， which I find useful lot here。😊，I pick a center。

And I start looking at。You know， what am I doing？I'm looking at all distances from this center。

Of all the vertices， right？😊，So let's put all the vertic scenes at various distances from the center。

So we are all the vertics of the graph。😊，Remaining in the graph and they are all at some distance from sea。

😊，From CI， Bri from CI， it's important。Okay。😊，And what is this process doing， this process is saying。

😊，I am going to a what else yeah。な使。I'm starting off with r equals0。And I'm flipping a point。

If it comes up heads， I cut。If it doesn't come up， hence。I move this further。Tents， tails， tailts。

 tails， tails， heads。过来啊。That's where I like。O。😊，So it's like I started off at CI。Tlls， tails， tails。

 heads。That's the process。Okay。Let's look at these two vertices U and V。Suppose。

You know how is the process evolving， you know， I picked a center。

I go some distance and I make a cut。Suppose this cut did not even reach the left。😡。

Left of the two vertices。Nothing happened。I'll continue with C+ one。Make a new death firstry。

The breakfast tree， shortest pot tree。Okay。😊，So if I keep cutting to the left of。The two vertices。

 nothings happened。All the action will happen if at some point in time， in fact。

 I shouldn't say if at some point in time， when at some point in time。Eventually， one of these。

One of these thresholds that I was running will actually reach you at least。对。

And now there are two options。Either， oh okay， I shouldn't have drawn this thing because these I was using to denote the cut。

😊，I have reached you。Now the die is cost。是喂。Now， either the threshold will reach V as well。😊。

In which case I'll make a cut like this and the pair UB will not be separate。😊。

Or I'll make a cut somewhere in the middle。😊，In which case you we will be separate。Okay。😊，对。

So I have reached this point。If I make a cut in the next so many steps。😡。

So now maybe I will draw these two bars if I make a cut in the next so many steps。

 if I get heads in the next so many steps， UV will be separated， otherwise they will be together。😊。

What is this width， can somebody upper bound this width？D U。

What is the probability that I will get aheads in the next DUV time steps？By union bound at most。对。

Yeah， well that's's you know， too fancy， right， it's at most the number of steps。

Times the probability of getting aheads in that step。Union board。How many steps it's at most？理 you俾咧。

What's the probability？不だ。It's as simple as that。Some of the whole processes。

 you know this memorylessness of the geometric。Is like amazing。It's like， you know I keep cutting。

 you know， I made some radius， U were not separated， it's like， okay， it doesn't matter。Next。

 I made some other cut somewhere， you know， it's it's this process that's going on I made a cut somewhere you and we are not separated。

They don't even care。I make some other thought to you and we are not separated， they don't care。

I take a center and suddenly I' have reached you。And now U say， okay， the danger has begun。

There's only DUB steps that we need to be safe。And then we are together。

And the probability of screwing up is exactly the number of steps， densityP， do U need1P。😊，Yes。

 why don't we go back and like change a definition so that like the chance of being cut is less than some exponential thread so we can clearly removal like。

Negative exponential bound with this dive。Maybe I don't need it。We could we could look into that。

 but yeah， for right now let's just run with this， we can discuss this。😊，Yeah。

 good so sos here's the deal。So consider the following situation。啊。

Let's consider the following situation。There are a large number of ver out here。😊。

And suppose this distance is exactly like D or something like that。

Suppose I took uniform between0 and D。we can play with the parameters。

 but I'm just cooking up something out here。Suppose I chose this guy to be the first center。

What's the probability that this edge of length 1 will be cut？Yeah。One over。Right。😊。

But suppose this edge is not cut。😡，Then I took a cut somewhere。I took a cut somewhere out here。

 I separated this vertex from the center。😊，Then the second guy comes and says， I'm ready to cut you。

😊，The probability of that is again， one over0。So that one over Ds are just piling up。😊，嘅。

basicallysically towards the end of you know， this is like remember this is like D right or d over 2 or whatever up to constants。

😊，The probability of reaching somebody at the very end of cutting at somebody at the very end is very small in the exponential where in the uniform is equal。

😊，And that's exactly this tension that's coming here。So the advantage out here is that look。

 you know， the people who are far away from me will be cut with very tiny probability。😊，And in fact。

 the geometric is really nice about that if I didn't even reach this guy， it doesn't even matter。😊。

But once I release that time。Then I can say， oh， memoryless， geo， everybody is very happy。

You could use the exponential instead of a geometric， you know， it's the same thing， right I mean？😊。

Whenever somebody said exponential， I think job click。Question。This is a low diameter decom。😊。

Very useful。It comes up in all kinds of different applications I know problems in distributed computing。

 I know problems in solving linears actually， you know maybe we'll do this later on。😊。

I want to solve linear systems。Linar systems as then I want to solve solutions to Ax equals。

Lal algebra， right？If a is a nicely behaved matrix， it's a Laplaceian matrix or something like this。

😊，Whatever that means， you' are not supposed to know。Then solving the best current algorithms。😡。

For solving such linear systems。Go via under the hood。Low diameter decompositions。

You won't have expected it， I won't have expected it。And in fact， in the next lecture on Monday。

 we'll do shortest path via low diameter accomplishment。😊，Of course。

 low diameter decompositions require shortest path， so it's like a。😊，Ticken and egg thing going on。

Is there a question？你个。Okay。So we got a low diameter decomposition with parameter log n。😊。

Now I just have to give you a low straight span tree。With parameter log n times log of the parameter。

Yeah。Okay， so let's take a two break。😊，And then we come back and we just do that。Back to business。

Okay， so so far you've seen how to get for any metric space a load diameter decomposition with parameter beta equals log n。

😊，And the theorem I'm going to prove to you is put any metric space that exists the low spanning tree。

😊，With parameter alpha equals this beta。😊，Time log of the diameter。OfG。Yeah。And you know。

 whenever I see log of the diameter， I ask there's only one idea that comes into my mind。

 I must be having the diameter every time。😊，What else can I get to it？

So let me tell you the algorithm that's exactly what I'll do and in fact。

 if I left you guys to yourself， you'd probably figure out this algorithm in no。😊。

So here's the algorithm。So the algorithm says in pictures。

 the algorithm says start off with the original metric space。So I'll say low stretch spanning tree。

on。V。O。And then I'm going to give you a parameter I。没。And whenever I'm going to call this。

 I'm going to guarantee。That the diameter。Of v。Is at most。Do to be。It's like a precondition。

 I mean very and better maintained。And you know， occasionally， I lapse into writing pseudo code。

 but you don't have to。Okay， so what am I going to do？I'm going to find。Oh。Low diameter decomilation。

O the ver he is in V。With。Oh， sorry。She。Go to the I minus1。So I have a piece。

 the diameter of this is at most2 the R。I'm going to find a low diameter decomposition。

Into pieces of half the diameter。Okay。I am going to。Regrively。咩。BI。Whi is a low straight span tree。

On VI。With parameter eye on okay， this is terrible。Vj is Vj with this parameter I minus1。

I'm just passing on the information that the diameter is helped guys。😊，Okay。😊。

I called with VJ called it on the sec Vj with i minus1。

 notice that the diameter of Vj is at most2 to the i minus1。😊，系 a。Promised。喂。😊，So this call is okay。

I'm maintaining the invari I wanted to。 so what's happening， I took this decomposition。😊。

And basically， I'll get back a tree。For each one of these things T1， T 2， T 3， T4。诶。

Each tree that I build will have a special root words this is you know。😊，啊。AllI Jay。

So this guy will come with a specific vertex， which is called its root， it Br 1， it will be rootar2。

 Roar 3， rootar 1。没看。😊，Now I have to define a new tree。For this guy。He is the tree。B。okay。

 instead of writing in words， let me show you what I'm going to do。😊。

These are the trees that came back。I'm going to add an edge like this and let's like this and I' just explain this。

This is going to be my new route。But。哎。I'm going to put some distances on these edges， as I said。

 you know， I was saying， oh， I'm going to put some distances on these edges。😊。

What's the maximum distance that can be there between R1 and R4？好的这持。Okay。😊，This is my new trip。

Basically， I took my graph， I hoped it for each one I built a tree。

And then I just connected these trees together。Does the construction makes sense， why it's good。

 we'll see in just a moment。Somebody ask a question， any question I don't care。Yes。

 me you might as well choose and Ruth vertices the treat right yeah， so you know。

 you'll see how the proof will make it you know it'll become particularly nice。

If if we choose the roots like this， if I choose a random root vertex， I have to be a little careful。

😊，I might have to jiggle the parameters and work a little bit this way you'll see why。😊。

With diameter of the so the diameter of the new， so let's look at the diameter of the new。😊。

Can somebody give me a bound on the diameter of the new？to theI plus。But I might。Plus。

 because this whole thing is inductively some some three， right but？😊，Okay。😊。

The diameter of this new tree that moves due to the I plus one。😊，This is your lemonma one。

And this is where actually you choosing the roots carefully was very nice。😊。

I didn't have to keep worrying about it doubling every time。You can believe this。啊。Inside this thing。

 there is another construction like this happening。And these lens are2 to the I minus1。

2 to the I2 to the I minus1 geometricxa。Through the I plus1。哎， good。Great， so。

But the subtrees have they have they return turn with diameter to the eye or to the alines point so each of these subtes so what did we get we got a sec whose diameter was to the eye and what I'm returning is I'm returning some tree。

Who's okay， maybe I shouldn't have said diameter I should have said。两次。

Orernaneius or something like that。What's the maximum distance from this root to any other verortex of the graph？

It's like most through the eye。Plus this is the root of this guy。

 so from there to the next route is to the I minus1。Inductively and so on and so forth。Remember。

 what's happening inside here， I just built this thing。But this guy itself was this root with。

 you know， a couple of children like this， right？😊。

You could just make the promise that like I'm going to return to something exactly death that's our most double and then exactly so so this is really a lemma that's being proved inductively。

I'll be guaranteed that the depth of this guy is at most to the eye。😊。

And I added it on two to the eye， so thiss true to the eye plus one。Okay。😊。

So the distance from the route to anybody。Maybe I can be even more pedantic out here。And I can see。

For all vertic Cv in V。The distance。In the tree。From the root。To we is that most to the are last one。

Okay。😊，O。We are pretty much done， so let me just do the last。So now。What do I need to do？She。

This is a tree， right？😊，By construction， etter。The distances are only more than the distances in the original graph。

😊，Because we set them that way， you know， the every time we added an edge。

 we put a distance which was more than the distance in the original graph。😊。

So I'm satisfying the distance property that I had。I just need to bound the expected stretch。

For I to vertical to see what's the expected distance between。😊，So let's look at these two vertices。

😊，This is。There's some probability that UV we are separated。Thanks。Distance。

Let's say we expected distance。In the tree between UVv condition on them being separated。Plus。

 the probability that they are not separated。In the first cut， you know， it's all inductive， right？😊。

Times the expected distance。Not separated。O。Let's look at each of these。

What's the probability that UV are separated？对。Yeah。

D tens and D in this case was something like2 to the I minus1。😊，哦，我啊。嗯，是的，是的。Dines beta。Okay。

 suppose U are separated so then you lie somewhere out here and we lie somewhere out here。

Can you give me an upper bound on what their distance will be？我。All the way2 per5 plus 1。

Do by i plus one。Herere the power I+2？Oh。Okay yeah。呢度。No。

 ask me you have two to the power of+ one from through R but you also got two things from I from R right to R2 so this。

 I was claiming you know this is the outcome of this whole thing so I was saying the distance from U to R which is the new route。

😊，Is inductively2 to the i+1。If you just want to look at this distance， I will say this is at most。😊。

2 to the eye， because it's at the next level now。It's plus to plus exactly but you know。

 this situation would be the other case， so this is two to the eye2 to the I2 the I2 to the I2 to the I plus2。

😊，个人。So far， so good。😊，If they are separated， this guarantee says that both of them are not too far from the root。

😊，So both of them can't be far from each other。ラ。Probability not separated one minus this crpo。1。

Upper。And now what's the expected distance given that they're not separated， well。

 they're not separated。😊，So what of them？We're sitting inside here。I can use induction。

Did we expected。this by induction is at most their actual distance be U V。Ts the diameter。offff。

Whichever piece they。Went in BJ。What was the diameter of Vj oh sorry， not diameter of Vja？

So inductively， I'm going to claim that it's this times beta。Times log。Pos the diameter。Of Vig。

What was the diameter of VJ？啊。Yeah， so it's  two to the i minus1。

 let's say right so log of that is i minus1 now suddenly my log they become base two for some reason。

😊，But it's okay， you guys are running with that so this thing is just。This piece is。

 let me just lift it up。The distance times beta times I minus 1。

And there'll be constant that will come to bite me。

 so maybe I would to inductively assume that this was eight times that maybe this was the eight I was thinking of。

So8。Distance beta I minus1。And this guy is going to be。嗯。8ight times distance times data。

8ight distance beta minus-1，8 distance。A distance beta I induction done。P。

Okay so the claim is that this is at most。Eight times the distance UV。Thanks， beta。Ps， log。哦，再拜呢个。Pa。

And this is what I prove by induction。Of course it's always dangerous to write these things down before you prove it。

 so you might as well prove it first and then write the numbers down later。😊，嗯。

And more or less what's happening， you know， this is some algebra out here it' is actually very simple algebra。

 but still more or less whats happening there is some probability that UV will be separated in which case they will pay about to the2 to the diameter。

😊，Oh sorry， not the two to the diameter， they'll pay about the diameter。

But the probability that they will get cut。😊，With is the distance divided by the diameter times log times beta。

So the two diameter kind of cancel each other out。These two diameter tend to cancel each other。

And that's exactly right so you pay log at every scale， there are log scales。😊。

Or log of the diameter scales， but log scales， you pay log at every step or you pay beta at every step beta rank log。

😊，End of proof。It takes a few minutes to write all this down。

Every step here is almost like a toology， there's nothing happening。You've already done the work。

And again， how we got the second part， like poverty not separated times I haven't done good so let' let's do the proof again just very quickly。

靓。This expectation is at most this quantity。😊，Growth by induction。I just put in the fact that。

This UV now lie in a smaller piece and which have half the diameter。That's it。哎。😊，Yeah。各种。So。

Coming up for tear， where are we？We were doing low diameter decompositions no we were doing low straight spanning treess。

 sorry you guys low straight spanning trades。And we are saying， look。Given any graph。

I can find a random tree whereas the randomness its all in the low diameter decomposition。😊。

All right chop， chop， chop， chop， chop， get pieces of half the size， build trees for each one。

 cook them up， and done。😊，Completely algorithmic。So you can use it for your favorite trial guidance。

So the low diameter decomposition was what， you know， you know， flip， flip， flip， flip， flip， cut。😊。

And。Also very simple。You can try doing these things in parallel。

 actually Gary Miller and his students had a nice perspective on doing all these things in parallel。

😊，So you don't have to do the sequential you know， flip and then cut and then recurs on that。

 you can do all the flippings at once。😊，So Ive pointed to a paper that they did。Right now。

 the algorithm as I give is a quadratic running time algorithm。😊。

Because kind of you explode the graph completely， then you explore it completely and then you know you're doing a whole bunch of work out here。

 you can make these much faster。U，And people have been working on much faster because， you know。

 yeah， if you want to solve linear systems fast， you better do this fast。嗯。Good。嗯。

A couple words about improving， so this is log n times log diameter。How do you improve it to log in？

好。So somehow what's happening is we are paying log at every step。

And we are not taking into account the interactions between points between these layers。

So really the smarts here is coming up with the right interaction between these layers。😊。

If you catch me sometime office hours， something like that， I can tell you what the idea is。

So perhaps even more for the specialists， if you're really interested。But at the first cut。

 this is a perfectly good app。😊，And this allows me to save for most metric problems。😊。

So what do I mean by metric audience？So for problems that involve metric spaces， so okay。

 so my my loose thing that I say is suppose my problem is linear。😊，And it's on a metric space。

And I'll give you an example in just a moment。😊，As soon as I see this， I'm like。

 you know this metric space， whatever G， you know I put on my magic glasses。

 it really looks like a tree to me。😊，And if I can solve the problem here。

 I can solve the problem there， that's more or less what I， you know。

 this is the rule of thumb it's not a theorem， of course。😊。

But it really helps me know again and again， this is like， oh yeah。

 the first cut algorithm I can just get this way。😊，And going from there to there。

 Im losing a log gap。Log in from that better result here， what we showed was log and log diameter。

But， of course， you can get rid of it using a better potato。So what do I mean by a linear problem？

So you remember on homework one， we asked you to， there were these points on the line and you needed to put down case centers。

Suchs that every there were these points on the line at non equalal distances， some points close。

 some points far。And you said for each of these points。I'm going to go to the closest center。是是。

So really what I was doing was I was looking at the sum。Overall。Points I in my verortex set。

Of the distance。Of eye。To its closest。Centered。See in my solution fix。

It's a problem which is summing up a bunch of distances。It's a linear。

 it's the objective function linear in the distances。😊，And it's on a matrix space。

So this is what I call a linear metric space problem。

So what you could do is you could transform this metric space。

 this happens to be a line and you gave a dynamic programming algorithm for this， or most of you did。

😊，嘅。Suppose it was a tree， you can still find a dynamic programming algorithm。

 you have to work a little harder。😊，So now here is a way to solve this problem on general metric spaces。

 losing a log。😊，Approximate the distances by a tree。Find the best solution on the tree。一。

And just just the best solution says open a center here， a center here and a center there。

These are three points in my matrix space。Open there， there and there。

 which I will you know go have a solution there was。Yeah。

You can show that the optimal solution on this tree。

Is at most in expectation log times the optimal solution okay？Same argument as last time。

 this linearity of expectations。😊，And as you there's only two minutes left。

 I'm not going to bore you with the algebra。But ask me on P if something is empty。

So this allows you to say that actually， you know， let me just do it。

 it's just two minutes I'll do it。😊，So。What's the optimal solution me let me call this some notation last time I used opt and then I confusedfuse some of you。

Let's say that C Star is the best solution for this guy。Okay。😊，So how much am I paying out here？So。

 the。I was paying the distance from。Each point I。To its close center in C。

 which I'll just write in the shorthand。喂。Now look at the distance or this is distance in the graph。

😊，This is how much I was paying。In this optimal solution。If I look at this solution， C star。

 so C star happens to be this， this and this， I don't know。If I look at the same solution。😊。

On the tree。This is the distance in the tree from I to C star。In expectation。

This is at most log times。This quantity。I took this solution， I'm interpreting it on the tree。😊。

Every distance in expectation is only long times higher。Now I find the best solution on the tree。

It costs less than this。Best solution。On tree。Was less than this。Because it's the best solution。

 He is some solution。YouEverything's an expectation， of course。Now take that solution。

 this yellow solution and interpret it back on there。😊。

The distances out here were more than the distances out there。So we expected。Best。Solution for trade。

On original graph。Ifs even less。Because distances were stretching the tree。

Distances were stretched in the tree， I found the best solution on the tree。

But this solution in expectation costs lock time storage。All I'm using is linearity of expectations。

And expected distances are stretched by low。Okay。😊，Good， so if you have a linear problem。😊。

And you are working on a metric space， it's really a tree up to logs solve the problem in the tree。

 come back。😊，And this is the way in which you'll most of the time use low stretch embes。

 low stretch spanning trees。OhAnd since I use the word embeddings。诶。

Let me hear were done with the sort of the main part of the lecture， let me just tell you about。

This area which you know， actually I did my PhD on sort if it's an area I really like。

 is this area called metric embeddings。😊，And actually it should be really called the algorithmic study of metric spaces。

😊，So in my mind， any metric space is close to being a tree in this randomized sense。😊。

And here is another theorem that hopefully we'll see later on in the course。😊，Yes。走你好。

Suppose I have endpoint。In。D dimensional space。Some D dimensional space think of this as being like a。

Billion points， 10 to the nine points。In a million dimensional space。Not unreasonable nowadays。

Now what are these points， these points are documents。However they represented。

 they are represented in some crazy format called TF IDF， whatever。😊，三不去。啊。Oh I'm being taped。

 I should mind my language， but these are the number of words in the English dictionary， right？😊。

It's maybe 70，000， but 100，000 or whatever。啊。10 to the five。Yeah。嗯。

I don't like this high dimensional space because my algorithms are very poor in high dimensional space。

So the question is， can you map these points into lower dimensional space？

So that their distances don't change。And the answer is yes， so you can get a map。

And I'll call this F into。Some number of things log of the number of points。Over epsilon squared。

Such that。The distances。Oh。Uklinadian distance is up here。

Are approximately the same up to one plus minus epsilon as f of x。Minus S plus's fine。

And I should be careful this is all only for Euclidean space。

 and this approximately means that the distances are changing by at most one plus minus epsilon。😊。

So if you didn't want to change things by more than 10%， let's say。Then this is 100 times login。

900 dimensions。Much better。嗯。So this is sort of dimension delta reduction and in my mind I think， oh。

 every Euclidean space is low dimension。😊，And so you know。

 so this area is trying to understand what properties or metric spaces could be used to get faster algorithm or better algorithm。

 so whatever happened？😊，Anyway anyways， we'll talk more about this later on， but for today。😊。

This stuff， and I guess I'll see you guys one day， have a good weekend guys。

