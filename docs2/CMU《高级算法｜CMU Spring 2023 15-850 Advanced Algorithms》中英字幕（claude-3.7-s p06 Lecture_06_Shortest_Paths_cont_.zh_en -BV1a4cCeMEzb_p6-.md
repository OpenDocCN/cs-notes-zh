# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p06 Lecture_06_Shortest_Paths_cont_.zh_en -BV1a4cCeMEzb_p6-

OK嗯。Hey， everybody。So welcome back。15850 lecture 6。And so were going to do this very recent paper。

 this Fox 2022 paper on。哦。咩。但。Single solar shortest paths。And this is a paper by Barnstein。啊。な解。And。

我你有。And it won the。Fox best paper award。 It Co won it with paper by our own Richard Pang and others on。

A new linear time algorithm for min cost flow。And for those of you who are keeping track of these things。

 there is some subtlety between almost linear time and near linear times。

 you know there is this distinction between algorithms that run in and let's say the number of edges exam and to the one plus little of one run time。

😊，And， and。玻璃 log game。状态。One of them is called almost linear time and the other one is called near linear time。

 I can never remember which is which。So啊。What we are going to see today is we are going to see this。

 And I think this might be nearly。Okay， I'll tell you what what the various。

To the various things about this are actually， let me just tell you out here。

 We are interested in graphs。 These are directed graphs。Vty see and edges。 I'm not saying arc。

 Sometimes I'll use the word arcs， but it's the same thing。 V0 T and edges， and they have weights。

 right。And the weights are allowed to be。Negative。Wai。But of course， no negative cycles。

The algorithm suitably changed can detect the negative cycle。

But I'm going to assume that the graph is no negative cycle。 and I'm going to show correctness。

 Richard。He was the guy I was telling you what。 He won。 He co won the best paper award。呃。

Negative weights， no negative cycles。 What else do I need to know。 So this is a diagram。

And of course， there is the source verortex。S， and I'm interested in single source short path。

And naively， you would run Bagman Ford。Also known as Belman Ford， more shmble， et cetera。

 various other people have discovered this algorithm。

 but I'll just call it Belman Ford for simplicity because。😊。

And this algorithm runs in order in any time。And the algorithm is written。Right。And。

Youd run this algorithm。N rounds。And all it does is it starts off with the source being at distance 0 from itself。

 Every other verortex being a distance infinity。 and then it for n time。😊。

It relaxes all the edges of the girl。And remember what's happening in relaxing an edge when an edge is relaxed。

 really mean。😊，This is you。 This is me。I just say， look。

 the distance of V from S can never be more than the distance of U from S。

 So S to u plus the length of。So this is， you know， it can。

 And I'm going to maintain that D of V is always an upper bound in the actual distance。

 and I'll slowly improve it。And you can show。That。If you run this algorithm for K rounds。

When you are correctly computing all shortest parts which have at most k hops to them。

 which have at most ks。So if you look at a vertex which whose is distance from S。

 whose shortest parts from S has that most K edges。Its distance will have been correctly computed。

And this is the inductive proof that。So， that's Ben Winfold。

And you would run there for n rounds and you would say that， you know， after n rounds。

 no shortest part can have more than n edges。 So we should， which will be correct。Now。

 we want to beat this substantially。 we want to give an algorithm something like this。

And I'm going to give you an algorithm where the runtime is going to be m times polylo。

Of M and this parameter call C。Whats see。 So I'm， I'm saying。Where。The weights。Of the edges。

Are in teachers。They could be negative integers。But every weight is at least negative c。And in fact。

 in the， in most of the algorithm， I'm not going to use integrality。

It's only at the very end that I'll say， okay， you know， because things for vintagetegers。

 I can stop now。And you'll see how this comes about。Quions about the result，呃， why。

Well why dot you general see structures like see negative one still。Absolute。

 C negative one is quite hard。 I have like one set negative one。Absolutely， absolutely。 So， in fact。

 what's going to happen And those of you who are doing the homework right now。

 you know this algorithm， which is based on scaling， right。So basically。

 all I want to do is I want to just improve things ever so slightly。

And then that algorithm applied repeatedly。Well be able to handle all values of saying。So in fact。

 most of the time， I'll be just dealing with the weights are at least negative to let's say。

And this is the algorithm that Ill I'll give。 and then we'll see how it goes。But in in general。

 just to state the result， this is the result。It just changed the value of C by like adding some amount of good。

So you're thinking ahead。 you're saying， look， suppose I had。Short I had a graph。

Where the weights were at least negative two length。Could I just add on。 So heres。

 here's the simplest approach that we could say， look， this is S， and this is my graph。On every edge。

This could be negative。 They could be parts like this， whatever。 if just add on， let's say2 to it。So。

 for instance， let's just look at this example。The if you add on， let's say two to every edge。

 the shortest parts might change。So， for instance， this could be 1，1，1， and this could be a length4。

So this is 3。5。SoThis is the shortest path， but if you add on。

 lets say two to everything when this has become longer than that one。😊，So you don't want to do that。

 but。It's still a good idea。没没退吧。嗯。The algorithm。Needs to know the value of C。 I think it does。

 but it's a linear time operation。 So， you know， you can just scan over everything and look at all the edges。

Now， if it was in parallel， then maybe you could ask the question， you know， what can you do anyways。

 Yes， it needs to know the value of C， but that's easy。😊，Yeah。对。So just for the moment。

 I'm imagining that。I can read all， you know， I'm imagining unit time operations。😊。

On on the numbers that I'm interested in。But you are right that any number which requires which is of magnitude C requires log C bits。

 so arimetic operations on this should take log polylog C。😊。

But let's just imagine unit time mathematical operations。

I'm not going to be extremely pedantic about this。One should be the， not today。

There's plenty going on。OK。😊，So there is going to be four ideas that Im going to use。

 actually five ideas that Im going to use， Im going to use your idea。😊，Im want to add on。Let's say。啊。

Add on a number to every edge， and that' is going to distort the shortest part distances。

 but it is going to make things positive。😊，And positive weighted graphs are knife graphs。

 We like them。 We understand that。 and we're going to do stuff with。嗯。We are got to use ditra。

 but we are going to use this K round version of that。😊，We are going to use Belllman form。

We are also going to use a K round version of。 I'm not going to run into completion because that will take too much time。

And always think of K as being polynylo will come to us。好。呃。What else will we need？By the way。

 you know， actually in a shocking thing， I left my notes at home。

So I printed out some older notess which are also on the web page hopefully I'll be able to reconstruct it otherwise Richard will help me figure out the rest of it。

Okay， the extra Belman forward， I'm going to use。啊。L diameter you come this。M0B。Okay。

L a decompositions we have seen for undirected graphs。😊，Today， we will need a version for De graph。

So it's almost like all our familiar friends。 you know， ditra familiar friend。

 but we are using a K round version of it。Wellelman Ford familiar friend。

 but we are also using a K round version Dtra， we are running more than we usually do。 Wellman For。

 we are running less than we usually do。😊，No diameter decompositions， but on direct。So almost there。

 but slightly different。What else do we need？We need。The idea。哦，嗯。是。What I usually call potentials。

Other people also call prices。Whichever way you want to。Well'll remind you what these things are。

 you know， I'm hoping that you guys are checking out Piazza。

 I asked you guys if you could brush up on the idea of potentials。So what do I want。

 I want a map which maps every vertex。😊，嗯。Someum value。And then I'm going to define given weights。

 I'm going to define a potential， maybe I'll put the potential downstairs。

 though over the course of this lecture the fee might go up or down， don't get confused。😊。

P U V is equal to P of U starting birthdayex。 Remember， its directed you to。对吧。😊，ダユグマイナス。Okay。

And I call said said。You know， any mapping like this is a price function。

Al'll call see to be feasible。This is F W P。での。If I find such an object。

 Im in great shape because I can run by strong the resulting graph， why。😊。

Because the single source shortest parts do not actually， this really shortest parts do not change。

20。嗯。So what do I mean if I look at some vertic is I and J？And I look at this path。

Then I say this path is the shortest path under W。If and only if between I and J。

 if and only if this path is the shortest part under W73。😊，It length may change。

 but the fact that it is the shortest part or not the shortest path does not。Freasible potentials。

If I could find feasible potentials fast， Ill be done。😊，喂。Because， you know， given any old graph。G。

I would find。The feasible potential。 So， you know， this is， I'll just say w。

And I'll move to W P and here from there， I'll just run back。

So really all the magic will be happening in finding CB potential。Find the， which is Ph。

A feasible price。And how are we going to find the feasible price。Find the feasible price slowly。

So here's， here's the approach。So by the way， how do you find feasible prices。

Just to remind you and just to remind myself， here is one way of finding suitable prices。My。

 this is my graph G。 I want to find feasible prices for G。这黑我当公司。I want to add on new vertex。

 I'll call it S hat。S hat is the new vertex。Is wearing a hat。 makes it clear thats the new ver。

And I'm going to add in。0 length edges。ToAll the veres of J。好看。And then I'm going to say P of V。

Is the shortest part。In this new graph， in this new graph called G plus S hat。

 G plus S hat is this new graph。Is the shortest part wrong S hat。This is a definition。

I took my graph。 I added on a new vertex F hat。😊，And I've computed shortest paths from S to everybody。

We could have negative weights。😊，In general， it would， right。

 Why are you finding feasible potentials otherwise。喂。嗯。If it has negative weights， so。

 but it has no negative cycles。So this neo graph has also no negative cycles。你说。

Because I created no cycles in this。There are no cycles。 no new cycles have been created。

 F hat has no cycles that go through it。 There are no edges coming into us。No negative cycles。

 so I can compute shortest paths from mass。These are well defined。嗯。

So if I can compute shortest parts， I can compute feasible potentials。😊。

If I can compute feasible potential， I can compute short parts using ditra。😊，喂。

So it seems like a chicken and egg type problem。I want to compute feasible potentials。

 but in order to compute feasible potentials I need to compute shortest parts。😊，嗯。这些我追的。This。

 this J abstraction is computing these prices。😊，In one shot。We don't do it slowly。

They're not going to resting。So here's what I'm going to do or here's what these guys do。😊。

They start off with the original weight function。And they compute a potential call。P1， let's say， Oh。

 so the original weight functions。Have， have this thing being negative C， right。

They're going to compute。A P1， which is going to make such that the new under P1。

 every edge has negative c over2。And you see where this is going。This is a new weight function。

The maximum negative value has fallen。So I can compute a new wave function speed 2。

Such that these weights are at least in weight C over4。After some K rounds。

It will be negative1 over n squared。这到嗯。Whats that， so so at this point。

 basically I'm havinglving every time， the problem is I can keep havinglving and never get to non negative。

😊，也就。一绝都对。嗯。So it's negative c divided by 2 to the K。😊，And suppose， K is。log c。

So then this becomes negative1 half， let's say。I'm not maintaining integrality。 Let's say I haven't。

 you know， forget the fact that I ever said integrality。So these weights could be negative1 half。

Negative one quarter。 So at this point。This would be negative one half， right。

C over2 to the K oh negative one。Then next time， negative one half， negative one quarter，1，8。

Thats a bounce on the on the way't actually so here's， you know， here's what I'm going to do。 Let me。

 let me cut to the chase。 I'm going to make this。Negative  one of， you know， it's very close to 0。

 but it's not 0。And then there's going to be a last step。Well I'm going to make these guys。你。

Let's not worry too much about that。 Well come to it when we come to it。

I want to show you how to get from some weights。Which are negative to weights。

 which are only half as negative。I don't understand when you drew this。

After the angle the the distance from as had to。Is is just0。So so you might be， you know。

 so consider the following situation。😊，Oh， I see， so they're all zero or or less than zero。

The the prices are all negative。😊，嗯。喂。And in fact， if all the edges had positive weights inside G。

 then this potential youll get back will be a big fact0 everywhere。😊，But these could be negative。

negativeative 3。 then， then yeah。This price is at most negative3。So far so good。也嗯。个人。

So you need to compute prices。And what do I need to show。

 So really what I am going to show you is the main main step is going to be I am going to have weights。

W E， which are at least negative。死。😊，And I'm going to go to W P of P。W C of E。

 which are at least negative co。And in fact， for the rest of this lecture or most of the rest of this lecture。

 I'm going to show you negative2。没有。That's the main idea。And the same idea would work for negative C。

 negative C。How will it work for negative C negative C over2？Have I said anything about。

 I'm going to show this。Not just for integer weights， but for any weights。So what do you do。

 you divide everything by c over2。😊，But if you wait for negative C。

 now it becomes at least negative2。When you get back next。Not tricks。

So really all the action will be， Im going to show you that Im going to get the negativity of the edge from negative2 to negative。

😊，没付的。In the blank。没事。哈尔朵。嗯I don know。好快。快行。还有他。I want to do this in linear time and polyloggon。

Whatever M polylon， just this process。Okay， so suppose I could do this in M polylog n time。😊。

So each of these steps is N polyloggan， M polyloggan and polyloggan。

How many times do I have to do this。I have to do this。Lo of C plus and maybe this much time。追大に関。

To get it from negative C to negative one over end squared。So this will be the overhead。

 the number of round and this last step will be linear or whatever near linear。😊。

And whenever I say linear， I'm throwing away polylogue factors。下里。是在个。おえば。对。没。

So this is where I'm going to use the。This step， I'm going to use the integral。So this is where。In比。

Yes。Will be。So Ill do all this process not assuming integer weights and then finally I'll say oh。

 but the weights were integers。😊，So something good can happen。I can do around。No。你个。Questions， guys。

 you know， this is the first time I'm giving this lecture。 So chances are I'm forgetting something。

 Make sure that you keep me on track。😊，So let me let me tell you some properties you know this is going to be an interesting one because I really wish I had a little more board space but I don't so well make do with what we have。

😊，O。I should。What's my goal。So， my goal。I'll need a little bit of space at the top。

People learned bit of this。My军。Is。喂。Ting such that we get from W of E。Is negative two to c of W c of。

嗯。Thanks to it。So the first step I'm going to do。More write down an algorithm。

 And then you'll see how。The first step I'm going to do， by the way。

 So let me just define some notation。嗯。Where， should I define the notation。

 Let me define the notation now。W plus one of E is W E。I'm adding one to every。Same thing for W2。ok。

And I can define the graph g plus 2 to just mean the graph G where all the weights are plus2。😊。

What do we know about the graph where all the weights are plus you know， the original weights plus2。

😊，Non negative rates， Thank you。Okay。So here's what I'm going to do。

I'm going to or non negative wayss。 What can we do， I mean。

 the shortest part structure is completely screw。I have no idea what the shortest parts in this mean back there。

 I can compute shortest parts。 all I want。 they don't mean much。They may not mean。What do I know。

It's not negative weight， so I'm going to compute。A low diameter decomilation。看。Yeah。有人。

I haven't defined what low diameter decomposition is on directed。Yeah。We'll define in just a moment。

So this low diameter decomposition is going to do the following。😊，It's going on。

And we'll formalize this in just a moment。It's going to delete some set of edges。Yeah。So it's。

 it's going to delete。嗯。Let me take a different color。This deletes。The age I call E。We are arcs。喂。

Okay。Such there。G plus 2 minus E dell。Has。Strongly connected components。

 remember what strongly connected components are？These are sets of vertices that you know you can reach from any vertex to any other vertex。

 so its basically you know everybody can reach everybody。😊，그 응。Has strongly connected components of。

嗯。Diameter。Atmost some capital。This is the property element。😊，Previously。

 I was maintaining that the diameter， you know， remember strong low diameter decompositions just meant that every piece。

 every surviving piece had low diameter。😊，Now I'm saying every surviving。

 strongly connected component has looked。So the graph kind of looks like a blobs。

These are the strongly connected components。What do the edges between strongly connected components look like they look like a dam。

😊，They look like a deck。 No cycle is going between the strongly connected。Right。

Each strongly connected component has more diameter。嗯。what째？

Because if there was a strongly connected component that went that there was a directed cycle that connected different strongly connected components。

😊，That would be itself a bigger strong with。I'm sorry。Right。

 so what Im guaranteeing you is take the graph， look at all the strongly connected components。

 the maxim model strongly connected I mean those are you know that is how you define SCC right so these are the blobs。

😊，Just because these are different strongly connected components。😊。

There cant be any cycle connecting， there can't be any cycle crossing between them。

Because all I'm saying is I'm saying something trivial out there。

 Suppose these are three strongly connected components。 You could go from here to there。

 from there to there， from there to there。😊，Then the small thing is one strongly committed component。

实在。Same reason。Yeah， now forget about the diameter for the moment。

So basically all I'm saying is I'm going to take my graph and I'm going to delete a bunch of pages。😊。

This will give me strongly connected components。I'll maintain the property。

 So the strongly connected components are defined without respect to the notion of diameter。

So it's given me these strongly connected。Now， I'm fling。

Because these are distinct strongly connected components。 they can't be any cycles crossing between。

 Yes， that's the definition near。 That's the statement and。😊，On the side。

 I'm maintaining the property。This LD will ensure that each of these little blobs has low damage。

Let let me go a little further and see。So it's not that I'm saying， you know， I'm looking。

 I'm computing strongly connected components of low diameter。

 I'm just saying compute strongly connected components， no matter what the diameter。

My LDD is wonderful。Itll make sure that whatever strongly connected components are computed。

 their diameter will be small。😊，O。我系。Each strong component， basically itself has。

Like other strongly competitive components， that lump the special。Yeah， so， so like for instance。

 this guy could have these three vertices seated， which have this。😊。

🎼But the definition of a strongly connected component is basically all the。😊。

s this equience relation that we define。You' an equivalence relation， and that's the strong thing。

B good。Other questions？So this is something I have to maintain。 My L will have to maintain。冇。

So let me let me actually just define it。Msakking。It could have been easier to just define。

So what is the low diameter decomposition So this is a procedure ND that takes a direct graph G and a parameter D。

😊，And it deletes。Edges。You的。That' that two property for。换了。Every。SCC。offff。G minus。

Maybe I should call it h because I already have genes floating around H minus。而家。Has。diameter。

At most D， by which I mean， for all U V， which belong to the strongly connected component。

The distance in edge。Between doing 유는데。I that么。What you might think is definition in distance。

 but we should be precise。And secondly。I want， this is a randomized process and the probability of any。

Hdge E。嗯。饮料。Is at most。The weight of the edge divided by capital D。Times。

 times what if it were an undirected graph， what properties would we get？This is divide by d times。

Log last time， you know， we wrote some beta parameter around there in this case。Yeah。Yeah。

So I took my directed graph， I chop it up。As then I delete some edge。

This makes every strongly connected component more。

 Maybe the whole thing was strongly connected generation。😊，Now， maybe， you know。

 my whole goal is to make the strongly connected components that diameters one。😊。

Exact we delete a bunch of pages。They are all either。

And have maintained that their diameter is at most。And for this， I should delete a bunch of edges。

 I could have deleted all the edges。😊，Then probability would be one。

 but I don't want to delete all the areas。 So I delete as few as possible。

And the probability that any edge is deleted is this weight divided by the diameter divided by the diameter boundary。

😊，Thank log Square。Log squared just comes from a process， not important。

Is going to all go into that polyng。We good。We understand that， you know， the properties out here。是。

嗯。我自我认。Further， yeah， maybe it minus。对呀。This is saying on the remaining graph。 So such that， yes。

 the。H minus e de。Of youV is that。I look at what I have remaining and I say oh。😊。

A strongly connected component has a small path， only of phthy。We good。Good thank you。

 Please keep it coming。 I mean， chances are。I' mess up somewhere。So what did I do。

 I'm doing all this work。 I took my graph。 I chopped it up。 I deleted a bunch of edges。Such that。

 every component。Has small diameter。 Every strongly connected component has small diameter。Yeah。

So let me， let me do it。This was slightly differently。 Let me draw it。嗯。

These are the strongly connected components。哦。嗯。G plus2 minus e。对。So， strongly connected components。

 you know that you know kind of the properties are strongly connected components。

 you can make sure that you can kind of line them up so that all edges between the Fccs kind of go from top bottom。

They were topological sorting of the strongly connected people。So here's。

 here's the rest of the thing。Now。II want to do。Remember， our goal。

 you might have forgotten our goal。 Our goal is to fix the weight function。

To find prices that make them less negative。诶。So here is what Im going to do in step 2。At 1。

I'm going to， for each SCC。Let me call it C。Because there aren't enough seats on the line。

 I might as well put on other。But ES。Yeah。Maybe I should have mentioned one more thing。

I want to go from negative2 to negative 1， right？So there is this weird trick that they do which is fascinating and kind of crvy at the same time。

😊，So what they are going to do is they are going to look at the graph G plus1。

And they're going to fix the weights。어。Of G plus one to be non negative。Okay。反到。

So they are going to find a potential。This is going to fix all the weights。Of the graph G plus1。

What does this mean。This means the same weight function the same potential。Is going to give。20。

Reduce rates negative。实定性 the部。Yeah。It's an equivalent goal， at some level。Yeah。So， think about that。

只 now。Each of these is a component。四。And let me like plus one to denote that I am looking at these components according to the weight function w plus 1。

😊，Okay。Now， for every component， S plus one。finine。Fe one。Such that W。E under P1。

Greateaer than equal to 0 for all edges e belonging to c plus1。Too many， too many symbols out here。

I'm looking at the weight function。W plus one。Under this new potential， he is greater than。

我 wrong legends一。Inside each of these blobs。😊，I want to fix the ages。Okay。カに状対せ。

Ages inside the blocks。Edgeges， these red edges going from top to bottom。And the deleted edges。

Which killed the strongly connected component。I want to fix the white ones first， the red ones next。

 the yellow ones。Okay。Thanksgiving。I'm going to make their。Reduced weight。Don negative 돼。

By updatinging the being exactly。 So what am I going to do， Look at this bb。Look at this S hat， so。

I'm doing the same construction as before。That construction out there， that S had construction。

This the same construction。But just look at F hat and this little blob out here。

So I'm going to use the fact that。In order to， in order to fix all the edges out here。

I just have to kind of work on this little portion S hat plus。This has low diameter。

The good thing should happen。And we'll make this work hard。Then， secondly。I have to fix。化装了。Bagages。

SoMaybe I should write it like this。 I'm going to write it using red。This is where I， you know。

 I almost wish I had a whiteboard。 I could use various different kind of market。 this one。For装。

Dggages。Fix them。 so find。F 2， phi2， such that for all dag age is e。W plus1 under P field 2。

So speed is not。Yeah。好。好地方。Let's say in G plus so these strongly connected components are defined in。

the graph is the same， it's just the wave functions are different。😊，好。So when Im saying c plus 1。

 you should think of the weights plus one。😊，The the weight class one。

So these there are negative weights。Several moving parts。 So sorry， that's why keep asking。嗯。So。

Remember， there were three graphs， right， They were three weight functions， same graph。

 three weight functions。W， W plus 1， W plus。I use W plus 2 to compute the low diameter decomp。Okay。

 from now on， W plus 2 has no rule。原告。All my work is going to be on W plus。Okay。

What am I going to do， I'm going to look at w plus1。 I'm going to fix the edges out here。

 make that non nonlinear。😊，Then I want to look at the red edge is making non negative yellow edge is making non negative。

😊，I have to do three things。So the first thing I'm going to。

I am saying the first step make the white edge is not negative， red age is not negative。你等嘢来。Yeah。

So this was step。Okay， I should have。And step。3。F。See，3。Such that。W。嗯。3 plus1。嗯。What do。是。我会发这块有个。

It source all。关于。Yes。What。The hear the way。Yes。Exactly。Okay， what first though。The original。Always。

Which is either -1。 Oh， no， this happens。It's at least -1。 So my original weight， let's say。

 let's look at an edge of weight negative2。In W plus So this was W E was negative to。So W plus 1 E。

The negative negative one。And now， suppose I found a potential that placed。3 out here。

And one out here。Okay。Then the the weight of this guy is going to be what3。Plus， negative one。

3 plus negative1 -1。现Z关闭完。Okay。Yeah。对对。We they't have doing。No。

 so in some sense what's happening is think of this。What I am doing is I am first fixing all these。

Ages。Then I'm going to fix the red edges。😊，But I'm going to make sure that the white edges remain fixed。

Okay。So for all daggages， for all daggages。For all DAg， union， SCC edges。

I'm going to first fix the white h。Then Im going to keep the white edges fixed， fix the right edges。

😊，Then I want to keep the white and red I just fixed， fixed the。那会。纯着眼睛，还有是。

What's the high level idea。可。你 know可。还是。我们你讨问。就是来。对。So， so， so good。 So what's the high level idea。

So let me tell you a high level。😊，Excellent question， perfectf timing area。我 island。Idea 1。

This these pieces。They have low diameter。喂。Suppose low diameter means low number of hs。行。

So this means that for every pair of vertices out here。😊，The number of edges connecting them。

In the shortest part。Are few。What would you use？啊哈。嗯我键去。一多就会。那么。Good。好个。It's going to come there。

But right now， let's just look at the situation。In each piece。

 suppose the number of edges on every shortest path are few。What would you do， How would you compute。

This potential。Bllman for。Okay。😊，So if the diameter， if the diameter in terms of the number of edges。

On in each component were a few， I would use Belman for。Okay， so for the moment。

 imagine that die that the hop distance is small。对。Don我 how。Yeah。

 except that you need a large number of fls。Okay， so this is like it's not like if its it doesn't work。

 like if its lost， then it it costs a lot of money。

 You could have run Bamanford right at the beginning that would have cost a lot of money。

So what they will make sure or they are making sure we just haven't proved it yet。😊。

With the number of hops。On any shortest path within this piece。This is smart。

So I use Belmanfold to compute this。So let me， in fact， even write now。不。The number of hops。On any。

Shortest but。In the graph S hat plus C plus1， just notation gets in the way I should have just said C。

This is。The graph on which I'm fixing the edge of the white edges， right。😊，Is that most？Is at。

I want to prove this。Okay。Therefore。Bllman Ford。With D rounds。The好意思。Comps。嗯有。对。O C。

 this is supposed to be C plus one。So this is just this component。Plus。

So I'm just looking at disk graph。Because I want to fix all the edges inside here。

So I took this piece， added I had to it。And computer charge parts。He'll fix all the edges inside。

Yes no， maybe。关系不是样的关系。这PS是吧。So the question will be how small can we make D。

 So our first intent D will be bad。 It will be square root。😊，But then will。我。So the number of。

Hopps is B， so Belman Ford D round computes phase of1 in time。or的。M。Good。不。Next。

I need to fix all the red edges。Without screwing up the white edges。Right now。

 I don't need to use integrity。So that's the claim I have proved。That's the last claim I'll prove。

So I want to tell you why， why why we are doing this。Firstly， I made sure that the diameter is small。

😊，So the diameter was small。Benman for Wood work。But the original graph last diameter。

So we have to fix that。Let's fix the red edges。I want to fix。

All these red edges to have non negative weights。Can somebody suggest a weight scheme just for this little situation。

😊，If all the negative all these weights。at least negative one。Incasy all。建立。个人。

So I'm going to set the fee of this to be0。The fee of all these vertices to be one。

The fee of all these ver is to be taught。All the red edges in the weight w plus 1。I'd weighted。

 at least -1。Every。By adding on these ones。We are fixing their waves。How much time does this take。

 This is just， you know， this is a dag。明年对。2， fix。Dggage。O。对。공별 argument。

Apart from the proof of that claim， we are almost。H。嗯。Even this is going to be cheating。

 this is going to be D plus one， I'll do B plus2。😊，That's why。Thank you。Yeah那。OK。Good。

Let's look at the yellow edges。What can we say about yellow ages？Glow edges were deleted by。

Some random process。这他在。So there are not that many elements。是。

If there are not that many yellow edges。😊，Then they they can't be that many yellow edges on any shortest part。

So K round ditra should work。But let， let's do this carefully。Okay。

Have you guarantee like there exists some kind of。Why that's going。So， oh。

 there exists a phi that' is good because you know， there exists。

 there are no negative weight cycles。😊，So they always exist the potential that's good。😊。

We don't need to worry about that。But lets look at the edges in India。So let us look at an edge， E。

Which is。Negative。What is negative， There are too many weight。 W plus one of E。Is negative。

This is a Ni need fix， right？😊，All other ages I don't care about， negative weight ages I need。Yeah。

What does this mean。That the weight of the edge。Is life between。Negative 2 and negative  one。

Weight plus one is negative。The way two is between negative one。So wait plus two。Is between。这样。Okay。

This is the graph on which I run the low diameter decomposition。😊，So， the probability。

That's such an edge。Belongs to E。Is at most。The weight。Of the edge divided by D times poly load。

Which in the time honor tradition of theory， Im going to write is Poilda of one。Not important。

What is its weight at most？So this is atmost old tilder。That one of it。s there four。

The expected number。Of such。off。Negative。Wake edges。In W plus 1。Yeah。Is at most what。

All there or hand over。Number of negative weight edges in this graph。That's a lot， right。

Wold your horses， know， good things come in small， you know， sets。Suppose there are so many edges。

N weight edges。How many rounds of repeated ditra do I need to run？我的不。That whatever this number is。

 right。So I need order till the M over d。Ros。Of next。So what's the total runtime？

Total runtime is order M。Plus1。Plus。M squared over the。What should be said data？To balance this out。

SquareSquare root time。So this gives。呃，按娜了这个种。Whi event do。嗯。So much work empty the three。嗯。没反。

How are we doing that， Are you doing excellent K？So once again， we had。You know。

 if we had graphs where all shortest paths had few edges， we'd be in great shape。😊，Bllman 4 is great。

But that graph might have shortest spot with many。Then we said， oh， no， no， no。

 if every shortest path has few negative edges， we are also great。😊，But， you know。

 shortest path might have many negative areas。So what we are doing is we are basically saying， look。

😊，We are going to delete all the we are going to delete some bunch of edges so that strongly connected components have small diameter。

😊，好。And this means that very few， negative， very few。

It's still a lot very few negative edges are being delete。So we're going to balance the two。对。

And so this gave us m to the3 house modular， the proof of the claim。😊。

I the proof of the claim will take five minutes。 Let me not worry about。嗯。So can somebody suggest。

Where we are being wasteful out here。How do I get even better。嗯。关内容是对。And by D allow of text。Yeah。

But， you know， there is this tension， right。How do I reduce things？好。On the on one shortest path。

 But I don't know how to handle that yet。嗯。Here was one thing。I mean， ditra。

 I have to run at some point， but。Why am I running Belmanford。

Don't I have this fancy new algorithm that was supposed to be the substitute for Belman Ford？

First step， I hacked up the graph。 and on each piece， I'm running Belman forward again。😊，Come on。

 guys。 This is not。I should recurse， you know， S in this guy instead of using Belman food。

 I should use this。😊，我 that。So let's take a tuium break。And then when it comes back。

 I want to prove the claim。 Im going to write down the algorithm。

 You can prove it on your own suite time。 It's not complicated。 It's there in the notes。

The important idea is the following。 I mean， they like there are three like kind of cute ideas floating around Okay。

 you can see。The first one is that you know these two algorithms work in sort of two different cases。

😊，If we could hack up the graph so that distances were small， shortest paths were small。

Weve been great shape， in fact， shortest parts have to have few negative ages。😊。

And this is the crucial idea。 I mean， this is not， I would say this is an idea that we used to give。

😊，Homework problems。Long before this paper came out。

 but we didn't have the smarts to see that this idea could be useful。

That if you had few edges on shortest path， then just run extra a few times in a little quick。

But if only we had the。And the second， you know， so， so that's what they do。 they say， you know， LD。

 try the obvious thing。 raise all weights by two。 is want to screw up everything。 I was like dude。

 you know， youre dead right on the beginning。😊，But when life gives the lemons， make lemonade。

 So they make lemonade， they cut a bunch of edges。 not too many edges， in particular。😊，You know。

 very positive wages they might cut with high probability。 Who cares。They don't need to be things。

negative measures better being cut。Let me care about。And what they're saying is， well。

 not too many negative ages are being factor。So you control that。嗯。And then once you do that。

 then you say， oh， there will be strongly connected components。 We should run Bmanford， No no， no。

 we shouldn't run Belmanford。 We should use that fancy。😊，And that just recursively applied。

So the new algorithm will be compute L on G plus 2。Recurds on each of these gloves。

 as hat plus describe guy。That will fix all these edges。Red edge fixing was trivial。

 We figured it out in like two minutes， right。是。Yellow edges now because I am not cutting so dconally。

😊，아 레고 레권 볼。I'm not cutting so wildly。There will be much fewer negative weights。And we。

And that's basically the idea。Anyway， I told you， you take a two minute break and then I start talking。

 So let's take a two minute break。 and then we。Let's wrap it back。Here was the claim。

I got a component。I'll call it C， it is the same component C c plus 1。

 c plus 2 is the same component， just the weights are changing。😊。

So see the component I got out of the strong the low diameter decomposition。😊。

So its diameter in w plus 2 is at most d。It has no negative weight cycle， even at the beginning。

 This is what we assumed。Then I want to claim that any shortest path from S hat to any vertex。

 remember。Maybe I'll， I'll。What。叶路少天。These are0 bes。Thank you哪 being right。Any shortest path。

Can have at most D plus a constant number of edges。 We'll see how what comes out。Okay。😊。

In this graph， C plus  one。嗯。This is why we ran， you know。

 this is why we could run Belman forward on this graph。住福。Suppose not。

Suppose there is a path from S to V that has many more edges。That are some L edges。

It's not even a contradiction proof。 It's a direct proof， but anyway。Whatever， it has all。对。

What are the weights on these edges？W plus one。对。So this is W E plus1， W F plus1， W G plus one。

 whatever。So look at this part。 and maybe I'll call this part P。嗯。The weight。Of the part B。

In the plus one graph。Is。Non positive Tosons or。So what is its weight？In the original way sense。嗯。

What guarantee do we have about this blob？嗯。It's got low diameter。That， too。

Well it's got low diameter。 like。Exactly。So， not part。

So I know that there is a path like this of length。At most。对。SoW。In fact。W in the plus two world。

Between。Or whatever distance in the plus two worlds between。V and you。Is。Atmost D， right？

So distance in the original world between V and U。Can be only less。

The weight of this path is negative well。The distance from there back to here。Is at most be？

So in order for it to be in。There to be no negative weights。L must。We going。Cunning as all get out。

 know， like。I did not see that coming。You know， it's clever。 This is why they get the big bucks。Yeah。

Yeah， because I was covering。I back。We good with this。惯性词。6是我。有。我关于。我说这是一个。We。

 there should be something inside。你跟超说。啊哼。😊，So。如果你不是。

And do the low number of edges so here is one thing I could do I could just say lets ignore the the weights and run low diameter decomposition on just G with unit weight edges。

😊，But then。I don't know how to control for the you know。

 I don't know how to get the fact that there are a small number of negative weights in that third step。

So then I'm dealing I'm treating all edges the same。这个。接个诉。对今天。都是。嗯。不是。

Maybe now you have't been confused a little bit。Let hold that thought。 you know。

 we'll talk about that more。 There was at least one other question。や会す。不是。nice， but like right。

 so we use it only when you were getting going for it well， in reality， we're not。O。Good。

 so let me tell you what what the actual algorithm is going to be。我 thank therefore。E bit。

So here is what I'm going to do。 I'm going to say， look， so my actual algorithm。

Single so shortest parts。Is going to work on a graph。

And it is going to take a graph and it is going to take a parameter delta， let us say。😊。

And it's going to ensure it。That all strongly connected components in G。Have。Heop damn it have。

Diameter。At most day。diameter at most Delta。So I'm taking an L graph。

Which has diameter atno delta first thing I'm going to do is Im going to run LD。😊，On G plus 2。

With parameter。Delta over2。都。Delete。二到。Now， I'm going to。Recur。On the components。

The strongly connected components。Which have diameter at most delta over two。

 So Im going to for the strongly connected component， Im going to call。Sringd so shortest spot on。

See。😊，With。Delta over2。啊。And then I'm going to， so this will fix all the edges that are within the blobs。

Then I am going to fix。The bagg edges。Andm while I'm writing this。

 I'm still trying to answer figure out a compelling answer to Tulson's question。

 I think you might have a point that I don't even need this in the recursive version。

But well see in a moment。And then。And then， I have to fix。Edges。免一疗。mususic。嗯。Gay forward so。第ク。

And repeat it die extra。个人。嗯。嗯。嗯。Seems like I don't really need thelemma after all。I这原。啊 okay。O。

Good point。 No， no， no。There's the problem with not writing base cases。What happens。

 where should this whole process stop？The base case should be when the strongly connected components have very small diameter。

对。And then I should at least make sure。That。I can compute the solution fast。So at the very least。

 I should apply this on the base case。To say the shortest partss are very small。Let's say constant。

我我有。嗯我要是拿还证的。We could do that or if the diameter is less than 100。Then in that case。

 this is saying that the shortest parts are of length1 at most 100。

So 100 rounds of Belman Ford will suffice。What that。Maybe you can。

I should have asked for somebody a volunteer to write notes for this thing for next year。😊。

And then we could have figured out all these questions。In fact。

 it' is not too late if somebody would like to do it。

 maybe if two or three people would like to do it， we could do it。😊，Collaboratively。

 will be a resource for everybody。So if you are interested， please。呃。Let没有。

We should we should figure this out。 We should figure out all the details how to simplify it further。

 This is very new stuff， right。😊，So， the reason why I wanted to teach it was I wanted to understand it。

 so you guys are my guinea pigs。😊，But on the other hand。

 I think we all should understand the the latest developments in our area， right。😊。

We should figure out all the cool stuff that's coming out。And， in fact。It would be right now。

 the runtime in like order。Log to the8 n。I think this can be definitely improved。

 but won't it be really nice if you know， after we discussed and stuff like that。

 we had an algorithm that ran in this much time。😊，And then we could say we have solved the problem。

That would be convincing， you know， weve solved the problem。I mean， this is pretty convincing， right。

Do we have a lower bound？ I don't think we have a lower bound above linear。Actually。I should check。

 there might be a sorting based lower bound。 It says that if you can solve the extra fast， you can。

 you can， you can， you know， solve。 So there might be a lower bound of order M plus n。😊，Okay。

You have to read all the edges and you have to sort1 numbers。😊，I think this is the only。Good。就s道。

Yeah。Your diameter kind of blows up on every request separate So why is the diameter blowing up。

 diameter shrinking everything The diameter is shrinking everything square。😊。

Has M squared by D in it。Good point。 So what's going to happen is。OK。

So there is one more piece I should have mentioned we should look at not just the total number of negative weights so this was the idea that he proposed we should look at not just the total number of edges but somehow how many edges are there on shortest parts。

So it requires a little bit more work。They should stop right now。言えたら。白。Exactly。Exactly。Okay。

 so let me tell you the last step very quickly。😊，So what is the last step so the last step I said was suppose all the weights of the edges suppose I kept fixing things and I've got this potential and this potential is beautiful and it's made sure that the negative weight edges are one over and squared or higher。

 but they are not zero。😊，嗯。So do the following。A every edge so far， I haven't used integrality at。

So let's using。Take every edge whose weight。Is less than  zero。And just set its way to be there。

Thiss not only tough。So what's going to happen， what are you worried about？

Non shortest parts will become shortest parts。Or shortest parts will become non shortest parts。

 You know， things like this， right， okay。

![](img/64cd728595ab8361ac273920fd121872_1.png)

Let's look at any part。How much has its weight changed。



![](img/64cd728595ab8361ac273920fd121872_3.png)

Atmost one by n， right， So if it was， you know， the。

 the difference between a shortest path and the second shortest path is at least one。



![](img/64cd728595ab8361ac273920fd121872_5.png)

![](img/64cd728595ab8361ac273920fd121872_6.png)

But this tree is only。But this change is only， you know， a tiny amount。



![](img/64cd728595ab8361ac273920fd121872_8.png)

So it can't make a non shortest path become a shortest path。Ba。



![](img/64cd728595ab8361ac273920fd121872_10.png)

那。Almost is the simplest of all it clicks。

![](img/64cd728595ab8361ac273920fd121872_12.png)

Actually， I should have started with that。 two ideas that don't quite work。😊。



![](img/64cd728595ab8361ac273920fd121872_14.png)

But we can make it work。Adds the same amount to every age。 It doesn't quite work。

 But it's on the right track。

![](img/64cd728595ab8361ac273920fd121872_16.png)

And take negative age and make them zero。

![](img/64cd728595ab8361ac273920fd121872_18.png)

Only when the wait isma。

![](img/64cd728595ab8361ac273920fd121872_20.png)

Okay， what else guys。

![](img/64cd728595ab8361ac273920fd121872_22.png)

How are you guys doing， We survived that。Okay， actually， we can stop recording right now。

It's but yeah。I should have got you as cookies to to make up for this this marathon session。😊。

But yeah， don't you agree， it's beautiful。

![](img/64cd728595ab8361ac273920fd121872_24.png)

Yess。是是。Okay， so I'm going to stop the next。

![](img/64cd728595ab8361ac273920fd121872_26.png)

嗯。Next lecture on， we'll move on to。 So that's it for shortest parts for right now。

 Next lecture onwards， we're going to talk about matchings and were going to talk matchings for maybe three lectures。

 four lectures。

![](img/64cd728595ab8361ac273920fd121872_28.png)

![](img/64cd728595ab8361ac273920fd121872_29.png)

那个。Do all kinds of cool algorithms， right。