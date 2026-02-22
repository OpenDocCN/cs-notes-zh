# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p02 Lecture_02_MSTs_&_Min_Cost_Arborescence_(MCA).zh_en -BV1a4cCeMEzb_p2-

应该是。So welcome back。And let us continue on talking about minimum spanning trees for a little bit more and so todays plan is that I talk I'll finish this randomized minimum spanning tree algorithm and then we will talk a little more about this problem which is like minimum spanning tree but for directed graphs its minco avariescence。

😊，And while many of you have seen algorithms for MSD before you might not or some of you might not have seen algorithms for Minco arbboorescences。

 so well talk a little bit about that and also allow us to segue into start talking about LP then duality。

 which is an idea that well use throughout the course pretty extensively。😊，Good。Any questions。

 any comments that you guys have。Perfect so by the way as with the last lecture chances are that after the lecture I'll remember a bunch of things that you know I should have said and didn't say or vice versa and also questions that you asked you know responses to that more measured responses to that let's put it that way so I'll put them all on piazza if you are not on piazza for any reason please let me know and I can add you to Piazza its not。

😊，对，O。So啊。And a couple more things to remember from the last lecture is that we talked about these two rules we said well all our MST algorithms essentially use two rules。

 the cut rule and the cycle rule the cut rule says take take your graph， take any cut。😊。

And look at the cheapest edge crossing that cut that does belong to the NnesT and the cycle rule say take any cycle in the graph。

嗯。四。And look at the heavieraviest stage on that cycle that does not belong to the MD。

 it is colored red for not in the MD and blue for being in the MD。And in essentially。

 all our algorithms so far used the。Use the cut rule predominantly The cycle rule was also used。

 but know had a subsidiary rule today today the algorithm will use the cycle rule。And the main idea。

 as we talked about last time， is that what I'm going to do。If I'm going to do the following。

I'm going to find。N MT on some subset of pages。 Actually， I'm going to find some3。

It's not important what the street is for just for the moment。Suppose I find any oil tree。

And then I look at edges which don't belong in this tree。😊，And suppose。

 so this edge creates a unique cycle with respect to history。😊。

And suppose this edge happens to be the heaviest edge on this cycle。

Then I can color it red because I can use the cycle go。😊。

Regardless of whether this green tree was the MT or not。😊，Right。So here' is what we are going to do。

 we are going to find a good tree。😊，嗯。We are going to find edges which are， which are。

Heavy with respect to this tree in this sense that we are edges。 So let me define this notion。

I going to define the notion of actually， maybe I'll write it out here so that you guys can see。

Even when I've got the board down， you know， so let F be a forest。

And so I want to emphasize this need not even be a spanning tree。 This could just be a forest。😊。

And an edge。Edge。E is F light。嗯。The edge E belongs to the MSP on this graph which consists of the forest plus this edge。

So what I did was I took this edge and added it to this forest。😊，And I'm asking。

 is this edge belonging to the MST of the graph that I just created。This graph is one cycle at most。

喂。And so it really comes down to the question of whether E belong is the heaviest stage on that cycle or not。

嗯。So， is a heavy。Otherwise。And in sometimes， I can say。The edge E is the H E is F heavy if he is the。

Heaviest。Edge。On the。Unique。细布。AF0年。Yes。Actually， I should say on。The cycle in fmin E。If any。

Safe in the forest。So adding the edge E might not create a cycle。But if it creates a cycle。

And e is the heavieraviest stage on that cycle， then。The idea is F。Is this definition clear。Yeah。

It would be at most one cycle。On the utmost one side。Just because air for the forest， absolutely。

Yeah yeah。So。没有。Union at the edge could that also be a forced to Yes， so for instance。

 F could be the empty graph。Then F union the edge could also be a forest。😊，In which case。

 there is no p cycle created。 so this edge can't be heavy。对对。For MST of a forest。

 does that mean just the minimum stay achieve each component Yeah。

 so let's say it's a minimum span forest。Are we happy with that minimum spending forest， know。

 you can imagine what a minimum spending forest。😊，It's the minimum span of every component。没 good。

So here here's the algorithm。😊，So the algorithm says。嗯。Okay。

 so basically what I just said was if you find any forest。And if you could throw away。

 then then you can mark all the F heavy edges as red。And throw them away。喂。So at a high level。

 the idea is going to be find a forest。😊，Throw away all the F edges。And then repeat。Okay。Now。

 you might ask a very valid question， how long does it take？You know。

 like why is this a good operation， So let me write down a theorem。So the theorem says， given。F。

And all the edges in E minus f。There， there exists an algorithm。呃 that。

E in a forest air earth is a forest。E minus f are all the other edges。嗯。嗯。Produces。A lift。

Of F heavy edges， of all the F heavy edge。And hence of all the F edges in order m plus。😊。

So given a forest。I can。Partarition all the remaining ages， in fact， all the ages。

Into F heavy and F light。In linear time。So， in particular， if I gave you a forest， a tree。😊。

And it's an MSD。Then this edge， then this procedure will just tell me that all the edges。😊。

Of the tree for a flight。And all the other edges were F。So this process。

 this algorithm is known as MST verification。MC verification is only one part of what it does。😊。

As a as a site product， it actually produces a list of all F heavy。😊，Yes。😊。

Light set also contains the set till the first it such like there's an edge in your voice already。

Still plus magnet has heavier di。It notSo if you gave any edge in the forest。

 it will definitely be a light by just by the definition。😊，Yeah。

So this algorithm happens to be deter。😊，And maybe I should give a couple of references to the authors of this。

 So the first question that you might ask is is it even possible like suppose I just look at the number of comparisons required。

😊，Is it even possible that the number of comparisons you need to do is linear？

It is not entirely trivial， and this was proved in a paper of comblo。

I forget whether the F has the A Internet， so let me not put it。

Youconlo showed that there exists an algorithm that does only a linear number of comparisons。😊。

He didn't talk about the running time at all。And then following that Valerie King。😊。

Gave an algorithm that actually runs in linear time。😊，But it。

It runs in a model known as a pointer machine model maybe at some point we'll discuss more about machine models I didn't want to get too much into this right now and for those of you who know these things I'm just mentioning this this was in the pointer machine model and then there was a paper following that of Dixon Ro。

😊，And Dn。Who gave it in the point of model。These are two different computational models。

 we can talk about this at some point。But for right now。

 the important thing to remember is that there are algorithms that do solve this problem in linearator。

😊，We come back to this this thing towards， you know， once I'm done with the MST。

So here is the cargo triintion algorithm I will just write this is Kkt or G。😊，And itll。

 it'll do the following steps。嗯。It's going to run。It's going to a sample。Half the edges。 So sample。

 So like E1。Be a sample。Of the Ed set E。Independently the probability half。

 And I'm being vague out here。 Let me just the。B。Each end。END。With probability half independently。喂。

It just sample half the edges of the graph。E1 is that， lets say T1。 I'm writing a T for three。

 even though it might be a forest。Let's not worry about that。 P1 is KkT。Run on the graph。G。

 restricted to。Maybebe去几4。对啊。你异。V。1万好。I'm just going to run the algorithm on half the edges。

This is D1。And now， let's say E2 is the site of all。B one。Light edges。元気？Okay。And no。return。嗯。

The3 do。It isケケ。On。I built some graph， I built some spanning tree， not spanning tree。

 I built some tree。I threw away all the T1 heavy edges。I just kept the T1 light edges。

The T1 heavy edges were edges that were red。 I knew they could not be in the MSD。😊，So。

This is going to correctly compute the MST younger。任民人。Is the algorithm clear。They just took in。

A graph。Big half the edge。Built an MSD on that。Then I throw away all the heavy edges。

Do you want heavy edges。I just kept being on light edges。

The MST of the original graph should be contained in here。喂。All the heavy edges were red。

They were read with respect to T1。But it just meant they were right with respect to the edgezure of the graph。

喂。So I threw away a bunch of edges， but I didn't need them anyway。On the remaining edge。

 I'm just computing an MST。😊，Questions， please ask a question。

 I feel like there's a question in the room。Yeah。if you do century be that at set minus 3100 exactly。

So， so， so， so this is E2 is equal to E minus。The D1。Heavy edges。Absolutely。Yeah。

You're not going each edge in flipping a coin and picking up。half edgeI'm actually picking。

 I'm going to each agent and picking it with probably one half independently。

It's going to make my proof slightly easier。The other one also works。모。Other questions。哎。

This is the algorithm。One of my favorite town really beautiful。It's almost。

I'm going to add in one line。I need it for technical reasons。 I think， I mean。

 I need it for the proof to work。So what I'm going to do is I'm going to run。3 rounds。어 그 뭐까。

So Im going to take my original drum， Im going to run Brovka once Im going to run Brovka second time a third time each time the number of vertices is dropping by at least a half right。

😊，I just want my graph to get a little smaller。I just need breathing room。你 see嘛。Okay。对。So do。

Get a new graph。You know new smaller。And let me call this graph G S， you know。

 let me just call this V and E。 I'm not going to worry about。 you know。

 I could put primes everywhere。 It'll take me。Yeah， it'll take me time。

 You guys know what I'm talking。I have just run Boov cut three times made the graph a little smaller。

😊，And now I'm just feelinging the list is exactly the same。Okay。😊，对。嗯。Yeah。Re fall three， you know。

 any large enough constant。 You'll see why the proof requires3 just for my proof to go through， but。

The constant number of fronts。Even one would be fine， but three is nicer。

So let me tell you the follow。那。Lemma 1， it's really， you know， it's a fact。

 It's not really anything。The expected size of T1。嗯。M forward。Now。

 I realize maybe I do good like pranks。嗯。Let's say TV is pick each edge in E prime with probably one half this。

 this in E prime。 this is E。I don't know。 I'm just being pedantic out here。

 I don't know why I'm being pedantic。安对我。Number of edges in the graph have。You know。

 I'm just sampling half the edges。In fact， I won't even improve this。 I。

 I don't know why I wrote Lamma。This is a real lima。The expected number of edges in E2。

I have no idea so far why the number of T light edges， T1 light edges was small。诶。

T1 could be a really crappy set。In which case， the number of T1 light edges could be very large。

 but here's what I'm going to prove。 This is like most two times and prime。😊，And。한 번 멀 디스。你看。

This is this is the mainle that I'm going proof。You'll see why。Why this is useful。

 But having done this， let me just give you the rest of the argument。嗯。Suppose you believe Lama too。

You shouldn't believe Laman2 so far， suppose you do。What's the running time。

Let's look at the algorithm。How much time does it take to run three round the Buchra？Linear。ついたいです。

另面书。How much time does it take to do sampling linear， I'm assuming that you。

 you have an access to an articleacle that give you unbiased going to us。

One recursive step we have to handle this。How much time does it take to figure out all the T1 light edges？

Linear time。So， it is basically linear plus two recursive calls of carbonplanageage。So basically。

 I'm saying P of。MN。This is， let's say， you know， think of this as the worst case possible time of。

So of running the algorithmm on Ms and invertics。Is at most。See times。

M plus n for all the linear amounts of time。Plus P or。です guy？So how many edges are there。

 there are m prime over two edges。In expectation， but let's。

Let's believe this to be the truth and in the lecture notes actually I you know do this more carefully。

😊，And and prime。This is a little annoying。Plus。D off， okay。And how many。Edges are there。

 They might be， I'm prime over。 no， no， no， no。This is pure N prime edges， right？

And how many vertices are there and prime vertices are there。😊，喂。Okay。

And now Ill do the standard thing whenever I see， you know。

 suppose I want to show I would like to show。That this is less than C times。2 M plus M。

This is my goal。So I can inductively assume。ThisThis claim on the other guys。So this is。At most。

See times in both hand。对。See some question， by the way， sorry， sorry， sorry， See the question。

 I should have。And by induction， this is two times m prime over2 and prime。Plus， C times。

Two times and prime to n prime。给。What is this c times m plus c times？

The tools cancel out M prime which is less than M。 So this is C times。2 M plus。And。Plus。OK嗯。

I'm sorry。Two times。Do。M。And I。So Im looking at these two terms。 these give me 2 m。

I don't know why I'm doing algebra on the board。 I hate doing algebra， and I always confuse myself。

But。I would like to say this。But I see a slight problem than maybe I need。Do an。Sorry， guys。

This is the one bit where I said， oh， I'm sure I can do this on the board。诶。Shall I just next listen。

Do you guys kind of believe that this will work out？Yeah。I'm sorry。It's in the notes。 Yeah， sorry。

哎哎 yeah。Two times m prime over2 plus2 n prime plus C times two times。2 and prime plus2 and prime。

 whatever。This， I claim c times m c times M prime is at most c times 2 m。C times N。So this is n。

C times2 n prime。Less to n time。Sos something like war。So this becomes nine and prime。刚始。

To end prime，2 end prime。诶。And Brian。O。How big was then prime？And over8。This skills that。

So this becomes another copy of n。 there's a copy of n that's2 n。没有。你差一个。I just save myself。对嗯。

We got so far some algebra out here not important。But actually， one thing that you did see。

 which was important was I needed a little breathing room。😊，I need my graph to be a little smaller。

That's why I ran through round the Brovka。Okay看。But。

So this this proves the the lemma almost completely apart from lemma。

 this proves the theorem almost completely apart from lemma 2。😊，I just need to show you 11。

Andlemma2 is where the where the sort of smart lies are。惯性做法。You believe everything except Lema2。

 Im happy to go ahead。So let me prove。Number two says， let。啊。以万。The sample。Of E。

 and I'm dropping the primes。 Let's not worry about that with probability one half。D1 is MSD。E1。

靓 the number。哦。D one。Like edges。I that most。It's quite the number of4。OK。😊。

This is what I want to prove。So here他1본。This fact。Is just， Im saying， you know， T1 is the MT of E1。

 I'm not now saying run Kkt on this algorithm。😊，N name Steve， you know， it's it's the correct object。

All I need to do is show you that the you know assuming that t1 was corrected correct correctly computed by Kkt。

 basically the number of t1 light edges。😊，Okay， so how do I prove this？So。

 for this lemma for the purposes of this lemma， let me start。

 let me compute this MSt not using this randomized algorithm， but by crosscal sound。😊，You know。

 all these algorithms are computing the MST。😊，They' are computing the same object。

I might as well run crosscal example。So I'm going to just run you know， classical。Only for the proof。

Okay。So here's how I'm going to do it。I take E1， and I want to run crosscalline。

And now I'll tell you the the real trick of this。So the trick of this proof。In。

An idea which we call the principle of deferred decisions。I have randomness out here。You know。

 what did I do， I first went to every edge， and I flipped a coin。And I picked all the heads。

 and I put them into even。I'm going defer flipping the coins。 I'm going to differ back。

 I'm going to just wait。I'll flip the coin only when I need it。So let's do the话。

Let's sort the edges in terms of their weight。 So the weight of E1 is that least the weight of E2。

 but at most the weight of E2 is at most the weight of E3。So all the edges。Aline about。

Lets start going from the left， so how do I run Crscal？I look at the first edge。

And I see if it connects two different components。 If it does， I add it， otherwise I throw it away。哎。

So I'm going to do the same thing， but I'm going to do it in the following way。At some point in time。

 at any point in time， T。I have some tree。In fact， I have a forest。Okay。I look at the next edge E。

Suppose this edge。Goes within some forest。Within some tree of this forest。哎O。

So even if this edge were， okay， So if suppose this edge were not in my sample， were not in E1。

 will I add it to my forest。And not还得 point。Because it's not even in the sample。

The that's in the sample， would I add it to my forest？😊，This edge goes within。

A tree that have already constructed。そ个。I'm not going to add it， right。So this edge is definitely。

 So this edge E， maybe I'll call it E1， is definitely F heavy。What am I doing。

I've got some forests that I've built inductively。I look at the next stage。

If this edge closes a cycle。Regardless of not， regardless of whether or not it is in E1。

 it can never be in my forest。😊，And in particular， it will always be F。😊。

Because this is heavier than all the previous green edges that I have out here。😊。

This is that heavy for sure。Let's look at this next stage。你度。Which goes between two components。어。

Just FYI， the dry makes a bit confusing because it looks like E1 is still drawing to。Thank you。

Let's look at E2。 It's connecting two different components。

Now I have to decide whether or not I'm going to flip the coin。

So suppose E2 connects two different components。😊，If it belongs to my sample， I will add it。

If it doesn't belong to my sample， I'll throw it away because it's not part of my sample。😊，喂。

So when E2 is you know considered， I'm going to look at my coin class。I'm to actually flip the point。

If it it comes up heads， it's added to the forest。In which case what will this edge be？Tomorrow。

 E have heavy or F light。F flight。Because it belongs to the forest。Suppose it comes up tails。

Is it going to be F or F line？It's going to be F light。喂。😊，Because this is the lightest edge。

 you know， tomorrow。Suppose I did not add it to my。是。Tomorrow， suppose my tree added this edge。

It created a cycle。But this edge E2 was lighter than the other edge crossing that boundary。😊。

E2 would be F light。So equal is definitely f。Okay。Moral of the story。

 I am running a crust skull on all the edges， flipping coins as I need to。

If I get edgedge which connects。Pover is in the same component， it is definitely a。😊。

If I get an edge， which connects two different components。It's definitely aff。So the question is。

 how many times will I get these edges which connect to different components？So what's happening。

 I'm going along。 I see an F light edge。 I flip a coin。Unbiased coin。

It comes up heads with probably 50%。How many edges could I possibly add to this forest？😊，And n-1。

 But who cares。How many times， So this is really asking the question， I'm flipping a coin。

How many times do I have to flip before I see N heads？And minus-1 has。That every time I see a head。

 I add an edge。😊，Every time I flip a coin， I see N F light edge。😊，But every time I see heads。哎呀等开是。

I looked at this edge。It's a flight。I flip a coin， If it comes up heads。 I add it， it comes up tails。

 I throw it away。It's not an anyone。How many times will I flip until I see N heads？对。

Gmeter random material。And that's the2 end。在这里也是清单上。真的是。Yeah。Questions。Okay。

Ill let you think about this for a second， but maybe just to wrap up。

 this just says that the number of T1 light ages is small。😊。

And since the number of T1 light edges is small。😊，The rest of the proof。Go through。

 we've just proved Lama 2。And now the Tulem proved there some inductive claim。

 some little algebra good。😊，Shows that we take a linear amount of time in expectation。

We have an an algorithm。That's randomized， that takes linear amounts of time and expectation and produces the MD。

对。Yeah so so。How well this translates before。It's kind of like if you have。

it just worked out very nicely for us then we would have to worry about whether the convexity is helping us or hurting us。

 absolutely。😊，And out here， this is like a hand wave proof， even when the algebra is correct。

 this is a hand wave we proof， be formal proof in your notess。😊，80块钱时间。快啲边。

that let you say the cr steel at some point but the left of the tree there would be edges that the classical algorithm does not get because were2 or something so really what I'm doing is I'm maintaining the fact that at every point in time the classical algorithm is computing the MST on exactly the edges zone E1。

So when I came to this edge。I first。Asked， is this algorithm interesting for classical。

I it this sorry is this edge interesting for classical if this edge happens to be going within a component。

 it is not interesting for classical。So I won't even flip a coin for it。

But if it is interesting go acrossco。😊，I'll flip a coin。

And so I'll do exactly what Crscoll would have done on E1。😊。

There would be edges lighter than what Crsco would have seen because they were in2 right so so definitely so there might be edges out here which are in which that Crsco might have seen。

We would not have seen because they were in need too， absolutely。So okay。

 so let me just mention this last bit one more time， maybe more clearly。😊，This edge E2。왜 나 일록 됐째。

It went between two components。Then I'll flip a coin for it。 if it came up heads。

 I'll actually add it to my green tree。😊，If it came up tails。

 I'm going to throw it away because it's need to， so I can't。Absolutely。Mostly happy。

Completely happy。sorry。Likequito is not less than1。ですね。It is in that x score8。

 so it is not less than in。So I want to say this edge， maybe I should have called this EA。

 this is called E B E1， so this is the lighter edge。😊，跟嘅月两。希望你对待。

NoSo so maybe let me say that one more time。Hopefully， I'm not confusing you。 Okay。

 these are all the edges of the graph。😊，Inssorted order。I'm going to run from left to right。

Whenever I see an edge I'm going to flip a coin so let me just do cross skillss properly whenever I see an edge I'm going to flip a coin if its if it comes up heads。

😊，I'll consider it in Crcal if it comes up tail， I want to throw it away。😊，O。And now I said。

 let me take one more step， let me actually consider it in crossscal first。😊。

And if it's interesting for crosski， then I'll flip the coin。Nothing's changed， really。And。

In that difference is then I realized that look， if this edge is interesting for crossco。😊。

Then it's F light for sure。If it's not interesting for classical， it's a heavy pressure。

And then the question is how many edges could have been interesting about Ksk？

And the final step is every time an edge is interesting but crosscal。

 Ksll will add it with probability1 harm。😊，And classical scale can add only energies。

So there are two energies which are interesting。还啊在。Questions。Yeah。

 so if you know some like relationship between N and M， like very sparse or dense or something。

 can you like？Reweight that， can you get a better bound in terms of Mine N if you like reweight like one half to square？

Is any better value possible or not？So it would improve the constant eventually。

But no more than that， because you definitely do need linear time to actually run the algorithm。是。So。

 so， so at that level， maybe。Absolutely， so， so there is sort of a limitation out there。

 You have to look at all the edges for sure。😊，So， we needed Bfka only to reduce the number of vertices to a slightly small okay。

 so let me show you why why you needed the。Yes， so eventually I have 8 N prime sitting around。

 I wanted N prime to be small， so that it。😊，Corresponded to my。Recurrence。

 so I just needed a little breathing room。O。啊，关系这样。Yeah， question question。

 do we need to run Sky in real life or just I I。I won't。 I won't be able to tell you。

 I don't know a proof that doesn't use some notion of Borovka to reduce the size of。对。So yeah。

What you Jack。So maybe one。One observation to make。Is that this algorithm was very nice and clean。

 except for this one step。😊，Where I asked you to find all the light edges in linear time。

 I didn't tell you that algorithm。And it's because the algorithm is a bit of mess。

So this is my guilty little secret that this beautiful algorithm has a little you know。

 dark underbelly to it。😊，It's not really。's it's a very nice algorithm。

 but its it's not got the same simplicity。😊，As。The got个。So heres another open problem for you guys。

Get a。嗯。Simply。For者说。Even randomized would work。 This is a deterministic algorithm。

So can you get a randomized MSD verification algorithm that。Is simpler。 You know。

 we can go over this sometime。 I have notes on this in the， in the lecture notes that I hand out。

That it requires a little bit of work。So can you do something。你出 really啊。

Completely nailed this problem。But， okay。Having said that， let me let me do the following， Let me。

Take a two minute break and then we'll come back and well talk about this next question that we need to look at main cost algorithmescence。

So。Okay， so then let's move on to the second question we want to look at today。

 it is Minco arborescences， so what's an arbescence？😊。

So for this problem we are going to it is basically a notion of minimum spanning tree for directed graphs。

 but it is a very specific definition。😊，So， we are considering directed graphs now graphs with vertic Cs and just to emphasize the fact that it is directed I will say be the arcs。

😊，With directed edges are rockrcs。😊，In this digraph， here the digraph， it's a bunch of veries。

 bunch of edges， weights on the edges。😊，And just for simplicity。

Let me imagine that the weights are not negative。It's not important， We'll see why。What do I want？

I want an arbescence。 So what's an arbescence。So by the way， in order to define an arbescence。

 I need a notion of a root， so I have a root vertex。And let me say this is the root verex here。

R is the root for this。And technically， what I'm going to define is then。Out ourescence。

So an arbescence just says this is a connected graph， it's connected。嗯。3。In the undirected sense。

And each。Vortex。Has。Exactly one。Out。Ark。Except the root。Okay。So， for instance。嗯。啊。ですです。

This vertex has one outer。What else do I know。Oh。S。那的案多了。Change the directions of。

So I painted myself into a corner。呃。Let me。Sa this is going out， this is going out。嗯。

This is going out。And what else do I need。Maybe this is going on。It's connected as a tree。

Maybe there was another verortex out here。嗯。s going on。没认。Every vertex has exactly one outer。

But it's connected as a tree。Be happy。It's an algorithm。Okay。

Everybody has one edge Basically you ask anybody how do you get to the root， they say， oh。

 go this way。😊，And indeed， you'll get to the。Okay， because it is connected So from every vertex。

 if you ask them directions and you just keep following the directions you will get to the root。😊。

That's an honor breath。And you can ask the question。How do you find them in Coa？因来。

Every verdictex has one out park except the root in the example you get which just a route。

So this one。This has several inarchrcs。That's perfectly fine。It has one hour。No exactly。So。

 because it is a tree there are n minus1 arc that must have been chosen。

 every verortex is choosing an out arc， the root cannot not choose an out arc。😊。

That is the definition clear。And， you know， since there are weights on the edges。

 I'm interested in the men。😊，Weight or mean cost。Arbescence。

the root given to in the graph or is itescence within No， so this is a given root vertex。

Specified rootwork。Good人。absolutelyutely so if you constrain the number of inarchRCs。

 then the problem becomes NP hard because you can start capturing Hamilton cycle Hamilton path that way。

Good。Other questions。About the definition。So， okay so this is when cause aorescence and if you play around with this you realize that the standard bag of tricks that you used to solve minimum spanning tree somehow don't seem to work so greedy algorithms seem to kind of fail。

😊，And I'm running a little slow， so maybe I'm not going to spend time going over to broken ideas。

 Let me just。Say you know， there are some in your lecture notes， but if you have proposals。你嚟。Yeah。

阿水我我。还。So one of the questions was whether。呃。Whether there was a constraint on the number of inarchrcs to a vertex。

And yeah， every verortex can have as many in arcs as you want， but the number of out arces。😊，Okay。

So here is the algorithm。 So you know this problem is indeed in polynomial time and the first algorithms were due toedms。

😊，嗯。By the way， you know， one thing I did not mention was on the previous。

For MSTs a lot of the algorithms were had the name Tarjan Tarjjan is Bob Tarjan one of the tuuring award winners Jack Edmonds is also one of the sort of greats of algorithm design in fact the notion of polynomial time is often attributed to him amongst other people so was a sort of very big name in the field so in the 50s I think。

Maybe early 60s， he came up with this algorithm for menco aberescence and around the same time。

 some other people actually， I would love to find copies of their papers， but。😊。

They also maybe within a year or two， they also gave independent algorithms that are attributed to sort of more commonly attributed to Eddmunds。

 so this algorithm is one that I'm going to present and I'm going to present sort the presentation is following that of Dickcarp also one of the sort of Teaing award winners。

But， good。So the algorithm is going to proceed just by a series of reductions。😊，And you know。

 the steps are going to be the following。So there's going to be okay。So the first， first step says。啱。

For every word you know pick a vertex which is not the root。

 so this is the vertex it has a bunch of out on code。😊，Remember。

 I assumed that the weights were non negative。给。By the way， if the weights are negative。

 suppose there are negative weights。😊，Let's just add the same number。To all the edge weight。

Until the weights become positive。Every tree， because we are looking at trees， every tree。

 every solution。😊，Its weight has gone up by n minus1 times this edition that youve done。

So every MST earlier， every Minco aescence is still a minco aescence in bicycles。😊。

So that's without loss subject。O。So this guy has weights， you know，2，3，7， and 61。喂。Do the following。

Reduce all the numbers out here by the min number。So this becomes 0。 This becomes one。 This becomes5。

 This becomes。This is the non root vertex， right？Has the main cost aescence changed？

Its weight has changed。But the Min course arbberescence has not changed。

Whichever age it used earlier。😊，Every Minco aescence was using one of the age。So。

 the weight of any arbescence in the old and the new graphs differ by 2。给。So basically。

 I want to say T is main cause arbescence。In the original graph G。

 if and only Ft is main cause arbexescence in the new graph G。ok。Do this for everybody。

Meincal salescence has not changed， just the weight has changed。😊，Okay。왜 얼굴 걸。That step point。

You we are one third of the way there。Okay。Let's go step。Okay。Yeah。We do that step forward this。

exSoActually， you can imagine that the root vertex has no outgoing edges。😊。

Because they are irrelevant to us。So， in that case， you could do it for the root vertex。

 it is trivial。😊，Yeah， but yes N。Other questions。Let's do step。Suppose， you know， let so by the way。

 this operation ensures that every vertex has a zero costage coming out of here。😊。

All the weights are not negative still。So what is the least cost？Of a mainco aescence。这样。So。

 let every vertex choose the one of the zero cost edge coming out of it。😊。

So let every vertex choose one of the edges coming out of it。Suppose this forms an arbescence。

We are done。So suppose this does not form an eyebrow。啊。Aha。Exactly。

 so if it doest form an arbestescence， what has happened？😊，Everybody is pointing to somebody， right。

A cyclist。There must be at least one second。Pick a cycle， any cycle。This is as I can see。你 know歌。

And there are edges。Going in， their age is coming out。Only kinds of stuff is happening。

Let's say this is all there is。Okay。Convert this into。A single vertex。We got yeah。So like0 cost I no。

 just one。it。なく。Im sorry no no no so this is this is a cycle in the in this aescence that we chose or in this whatever structure that we chose。

 but in the original graph it might have other edges coming out of Yeah these edges could have weight greater than equal to0 whatever。

😊，Okay。But these were the zero cost edges that were chosen。They found the cycle。Take the cycle。

 shrink it down into a single vertex calling it v sub C。It had， you know。

 whatever some number of ages coming out， these ages still come out。And the values still going。O。

This is a new graph。So this graph is called G， this graph is called G prime。对。

This is a smaller graph。I can compute a Min cost aescence on this inductively。😊，So on this graph。

Let me compute them in cost aescence。And suppose the solution that I got。😊。

Jos this edge coming out of it？And maybe there were a couple of edges there was this edge going into it as well and maybe there was some other edge going into it as well。

😊，哦。Suppose this was the solution I got back。Of some cost。Can you give me a solution？

In the original graph of the same cost。好。冇一管。然看。Good， so first， let me add in all the edges。

That were chosen。She。And now， on this orange cycle， I'm going to drop this curve。Same cost。Sa how。

 what's say。Aha same cost， even。You' are worried about the orange edges， right， No， no。

 but come on but we've already done the reduction。 This is the beauty of reductions。

 You don't have to worry about what happened in the past。It's all done。 What is past prelude。

Right now， zero host edges。Same cost。Question。If I gave you a solution in G。

Is there a solution in G prime of the same cost？So basically Im saying what we have just proved is that opt on G。

Is that most。啊等じ。Can you show the other ways？And my claim is yes。

 let me just just do this by a picture。😊，Take any solution in。异。And it's a solution okay。Yeah。直播就说要。

The blue edges were not zero cost。Or not necessarily zero cost。Okay。O。The question I'm asking is。

There is the question I'm now asking is。This was a solution。嗯。G。

Can you give me a solution in G prime？Of no more cost。I would like to say。O点 G。

Is greater than equal to。我定接备。How did you get G prime from G。

 you took a bunch of vertices and you squished them down， right？Suppose you squished down， let me。

Find the orange， suppose you squish down this vertex， this vertex and this vertex。😊。

How would you get a solution in。G prime。From this。Here is one way of doing this。Get rid of this edge。

Get rid of this edge。But notice that these three orange vertices have been squished down to the same location。

喂。So you can get， so this is claim 1。Opt G， that most opt G prime。Claim2 is the other way。

 which means the equality。Every solution in G has a corresponding solution in G prime in fact。

 given the solution in G you can given the solution in G prime。

 which is the important direction you can get a solution back in G。😊，Now you're done。

That's the entire round。The algorithm has two steps， firstly pick a vertex， any vertex。😊。

Reduce its its outgoing edge weight。Uniformly。Until one of them becomes there， stop。You big。Overall。

 the vertices。Now， everybody is got a zero weight coming out of it。

 everybody picks a zero weightt if it formss an aescence， you are done。😊。

If this does form an hardwarerbist， heres a cycle。😊，Contract the cycle。Repeat。

And then you get a solution back。 you have to uncontract the cycle。 You have to explore the cycle。😊。

How do you do this in the natural way？Okay， yeah。They always library。What do we be strengthening？So。

 we are restricting LG to some extent。😊，This graph， if the， you know， if if there is a。yeah。Yeah。

 something like this， clearly no no out arbberescence or no in arbescence。 I forget which one is。😊。

No arborescence as I have defined it。Good， so for every vertex check whether there is a directed path to the root。

😊，And you can do this， you know， just DFS， right。Just take all the edges。

 flip them around and just do D F S once。 linear time。 you can check。使做少啊哼。佢买嘅。It's not find out。

系人其实过。I absolutely。Absolutely。So， there could be， you know， yeah。

 these two vertices could be the same。😊，Just take the mid weight。哪个。😊，对。Now。

 you might think why did I you know talk about this one particular problem well there are various reasons one is it is acute algorithm。

😊，To this algorithm。Thank of。I is a precursor to what we will see in matchings very soon。

So in matchings， we will see a very similar idea of contracting cycles。And three。

 it gives me an excuse to talk a little bit about linear programs。😊，So in the last 10 minutes or so。

 let me talk a little bit what we need。对。By the way， observation， this algorithm。

 how long does it take？😊，Give me an upper bone， any upper bond。I'm sorry。Cdratic M， N。So。

 every time I have to find a cycle， I choose an edge， I check whether it' is connected or not。

Whether it's an arborescence or not。If it's not， I contract something。

Number of or these drops by a case one。Exactly。So， the naive method takes orderN time。

 number of edges， number of vertical fields product of those and there are smart algorithms which take almost linear time with log factors floating around。

😊，So for a change I am not going to talk about that instead I will talk a little bit about maybe the sort bigger perspective of where this is going。

😊，Min cost aberescence。It's， you know， it's a problem which is。

Related to matching in many different ways。 So let me just， you know。

 it'll take me more than 10 minutes to talk about that。 So let me just talk about the following。

Dnection。So here is what I'll call a linear programming relaxation Do you guys you guys remember linear programming right。

😊，You've seen linear programming。So here is a linear program programming。Relaxation。Yeah。

Of minco licenses。So I'm going to write a linear program。

Which is going to capture meanco arbescence and then perhaps more。And here is。

 here is one way of doing this。 So my variable， so you know。

 it always comes down to whenever you are writing a linear program。

 what are the variable for are the constraints。😊，So I'm going to have a variable。好。Each8 arc。

And I would call call that X A。And in fact。suggestugest something。I'm going to write an integer。

Programming。Formulation。Of mainco hardware residences。

Some of you are worried you know into your programming is the NP hard dude what are you doing it is okay we we will recover ourselves okay into your programming formulation and we to have a variable for each arc and this variable takes on values between in 01。

😊，Integer programs。Okay。Minimize summation。The cost of the ark。Times whether you chose it or not。

Okay。What are the constraints？Somebody suggests a constraint。

What are the constraints in arbor essences？In this case。

 outgoing from a vertex because I can choose only one。😊，So。

 this says look at all the arcs which are outgoing are going out of v and Im going to introduce some notation out here。

 Im going to look at the boundary of the vertex v。😊，These are just the arcs that are。

Hitting the verortex v and there is a plus setting out there which means they are leaving the verortex v。

😊，There is just some jargon that you will get used to if you haven't seen this before。

 So this says of all the arcs that are leaving this vertex v only one must be chosen。😊。

What are the constraints， Some suggests another constraint。 Is this enough。No， this is not enough。

 right？I'm sorry。Yes， so here is what I'm going to do。

 I'm going to write this in sort of a way that some of you have seen before， but some of you。

 this might be new。 I'm going to look at。😊，Any cut。So I'm going to look at an S。

Which does not contain the root。And I going to look at all the arcs going out of S。This subset。

 at least one of these arcs must be chosen right because these vertices need to be connected to the route。

😊，So， x sub a。A belonging to the positive boundary of S。The arks leaving us。Must be a case point。

For all S such that S does not contain the root。And S is not empty。And this was for all Ver Cv。😊。

V is not。Okay， so for every vertex， which is not the root， there is an edge going out。😊。

For every cut。Separating some vertices from the root。There must be at least one hour crossing it。滚。

this is the Minco aorescence， I mean， the solutions to this are exactly the minco aorescence。😊，看现这。啊。

Good， so let me make my life easier， say no arcs。For every arc， this thing， not。呃，leaing the route。

There are no variables for the arcs leaving the room。 there garbage arcs anyways。

 they don't serve me any purpose。嘅。This is a integer programming formulation。Okay。

And then if I wanted a linear programming formulation。😊，I could do the following instead。

I could say instead of this constraint， I'm going to write down the constraint。So， now。

The linear programming formulation says the arcs of the thing are between0 and1。I can choose at most。

I can practicallyly choose arcs。In't just feel like like up。 because you have like2 to the。Excellent。

Excellent， excellent。So。We have， you know， it seems like we have jumped out of the flyingrying pan into the fire right weve earlier。

 we wrote this massive IP。😊，Which had exponentially many constraints and also was an inte program。😊。

But what you are pointing out is that currently this has an exponential number of constraints。

That is true。That is true。So Ill defer that question， you know。

 that question is too good to be answered right now， so I'm just going to defer the question。😊。

But instead， Im going to claim the following that I can still solve。😊，This Lp optimally。In fact。

 Im going to make a claim I have already solved this LO。😊。

That algorithm up there is an optimal solution to this LP。😊，And how do you prove this。

 you prove this using duality， some of you remember this， others of you you know don't remember this。

 so I'm going to just show you how you prove this。😊。

Okay good so let me write down some claims right so firstly let me write down what the the integer program that I wrote down was IP the linear program I wrote down is called LP。

😊，O。So， fact。The optimal solution of the LP。Is at most the optimal solution for the IQ。

I'm relaxing the constraints。Earlier， I allowed only 01 constraints。 now I allow01 variables。

 Now I allow everything between 0 and1。😊，I'm relaxing with constraints。

 So the optimal solution is is is less constrained。 It can be lower。Okay。不。Yeah。Secondly， O。Now。

 this is equal to。My algorithm。On the， you know， my algorithms。Cost。Because I told you， you know。

 I actually found the optimal solution to the IP， right？😊，I found a Min cost a variations up there。喂。

You guys believe that I found them in cost arborescence， right？

So it would be great if I could show you that actually this was an equality。😊。

So that's what I need to show you。哦。So how do I show that？For that， Ill need another fact。

 actually I'll call it the theorem because it it's a theorem that you might have seen earlier。

 It is really a fact， but。😊，And it goes by the name of weak duality。😊，So what does week do actually。

So weak duality says。😊，Given any linear program， I can write down its linear programming to。😊，And。

Weig duality says that the sort of optimum value。Of the duel。

Is at most the optimum value of the prim。No end。嗯。I'm implicitly using the fact that the primal LP was a minimization problem。

 the do LLP will be a maximization problem。😊，Can somebody tell me what the duallLP should look like？

What do its variables correspond to？The constraints out here。What are the constraints out here？

The constraints out here correspond to vertices and to subsets。And notice that， actually， the。

The the constraints out here for a singleton subset。Are weaker in the constraint out here。ok。

So essentially for every non empty subset。Not containing the root， I have a constraint。

So I'm going to have a constraint。 So here I'm going to write down the do。Yhy is an S？火地纸。S。

 which is not empty and S does not。ok。For a moment， there is。Over time。

You can give me five more minutes。Okay sorry。For the moment。

 let me just imagine that the costs are not negative。 it makes my life easier。😊。

Then I don't need this upper pound。Okay。We can okay。

 the variables are all corresponding to subsets and here is going to be， you know。

 if you if you look at this， I want to maximize。😊，Yhy is a S， such that。嗯。Some over all ss。

Such that an arc belongs to。The boundary of S。Of y sub S。

Is less than the cost of the arc or all arcs。And why is the best？Its not negative。ok。

I'm summing over all。Subsject， so I'm going to say， look at an arc。

The constraints out here should correspond to the variables out there。

So for every constraint out here you know， it corresponds to some variable out there。

 the variables are as， so the constraints are as。And this is if you look at an arc and you look at all the cuts such that this arc crosses that cut。

😊，They must pack into the art length。If you take your time， you'll find this。

So you want to maximize the total value you get subject to this constraint。😊，1前0钱。嗯。

So the constraint says。😊，Look at an arc， any arc。Look at all the sets such that this。

Ark goes out of that set。It tailored inside the set。😊，And it's headed outside。

If you sum up the YS values for each of these。This must be at most the cost of you。嗯。

How do I think of this？These Yes are the amount of money。

That set S is willing to pay to connect to the route。Let's look at case1 up there。Look at verortex。😊。

The first time you know， it looks around at its edge。

 it says my cheapest age is too I'm willing to pay to。😊。

W of the single term vertex that vertex is going to be 2。对。For every vertex。

 you look at the cheapest edge going out of it that' is going to be the y of that singleton vertex。

Now， you found a cycle。The cycle says， look， guys。We can all reach each other。

But we don't seem to be able to get outside。How much should we pay as a group？To escape this quaary。

So， you contract yourself into some VC。And you look at the cheapest yet going out of it。

That is the amount of money that the sec see will be willing to pay。听到。

It's not necessarily connected inside， right as any subset think of a part in the could have like to So so in this case。

 remember， we had a zero cost cycle， right。So what we did was we took the zero course cycle and shrunk it down。

😊，And these guys are saying within ourselves， we can connect to ourselves completely。😊。

But going out of us。How do we pay。How much money should we paid to go out of this set？

And that exactly is going to be ys。Maybe what I should do is I should give an example you know way over time so I should let you guys go so okay let me do the following you know I don't want to make this decision those if you want to stay stay whatever。

😊，Let me stop here。 it's Friday， it's almost5 o'clock。嗯。Those of you who are interested。

 you you know come to the board we can discuss this more otherwise I'm going to post something on Piazza。

😊，It's it's just a picture。 there's nothing more to be done。Yeah。

And so whats the whats the bottom line， the bottom line is。This is a dual。

 I am going to get a value of the dual equal to the value of the primer。😊。

And this shows that this equality holds true。嗯。And okay， and with that。

 let me stop and we'll continue again in moment。😊。