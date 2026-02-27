# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p18 20231019-Oct 20_ Depth-first search, dags, and strong components.zh_en -BV1Mh7RzaEL2_p18-

![](img/80e38720eeda2d45d345c6eb23c87f57_0.png)

是反。

![](img/80e38720eeda2d45d345c6eb23c87f57_2.png)

而且。Okay， good。And actually seem to have worked all right so。嗯。

Last time we started talking about graph algorithms and in particular。

 I introduced this family of algorithms So letters。

So whatever for search is a sort of generic family of graph reversal algorithms。

SoThe idea here is I have a data structure called a bag， a bag can do three things。One。

 I can insert an object into the bag， I can extract。One object out of the bag。

 but I don't know which one I'm going to get that's up to the implementation details of the bag and I can check whether the bag is empty。

So standard samples of facts are huge， stas， priority huge。Where thing I extract priority。

 I can use binding searchries where again， the thing that I extract is say the offer of the cloud take lowest value。

 that's not just an implementation of a priority do。

But the idea is that I'm going to be begin with whatever graph I'm interested in。

In putting one vertex S。Into the bag。And then as long as the bag is not empty。

I will take the vertex out of the bag。Whatever on the about was skip me。

Check to see if I've already visited this vertex before so every something I to that I have somewhere in whatever data structure is representing my graph associated with each vertex so I will mark S。

😡，And then I will put its neighbors into the bag and then I will continue and I'll continue doing this process over and over again until the bag is empty。

So maybe I'll take the upper vertex out market and put its neighbors into the bag now。

There's a bit of optimization that one can do optionally。Which is。If something is already in the bag。

 maybe you don't want to put it in again so you can tweet the bagage structure so that it only stores one copy of very verts that would affect the correctness or in any significant way the running time of the algorithm。

啊。So maybe now I'll take this out of the bag and I'll market neighbors。

 I'll take this out of the bag and market unmarket neighbors。

 I'll take this out of the bag and market， I'll take this out of the bag and market。

 I'll take this out of the bag and market and then I'll take this out of the bag market neighbors and finally I'll take that out of the bag and。

The algorithm is done。The overall running time of this algorithm is proportional to the number of vertices in the graph plus the number of edges in the graph。

A bit more。To the point。Well， actually， let me say I can say a more refined statement about the Run time。

 but I think I'll say that in a second。The important point here is。The WFS marks。Every。Vertex。

That is reachable。From the start vertex S。This is the first vertex that I pass in at the very the beginning。

That V， I guess I'll go ahead and say it now that V in the running time。

 actually it's not all received to the ground。Just breakfast walked month on birthday thought that the is really the number first。

オぐラ？And in is the number of legends connected I think the versus the so this is really。Reachable。

Vertices。And edges。哎。😊，And the proof that this is the actual running time。

 this is something I did the very less maybe2 minutes of lecture yesterday。

 has to do with the number of times I execute this line here I'm highlighting in green。

And the observation is。That'。啊。I could associate each execution of the line highlighted in green with an edge up the graph。

 so I put the W into the bag， and causes W is the neighbor of some of those vaccine that I'm in the process't。

Prother。Okay， so each end。In some sense， because a women possibly be。Be put w into the back。对不对。

And when I cross the W， W plus me is that bad to accommodate that as the W so for each edge in the graph。

And strictly speaking for edge that's reachable from the source。This line is going to be executed。😡。

Exactly two e times。Twice the number of ethic。each。

AtAny point of the edge is going to put the other end of that edge into the bag。

 but that hair is involved in that transaction exactly what ones that these。what put that like我。

I put S to the back， then I take something out of the bag and call it V now I happen to know this is the first it。

 the thing I took out of the bag is what I previously called pests。

I'm now getting the new name there。Just went through the bag on the way of my head。Yeah。嗯。

So that means that。This line also happens， sorry。Strictly speaking。

 this line happens to e plus1 times。Because there are two e plus one occurrence instance of thoseop act。

 one very1 and one very on them。The other two need said that everything is put into that has to take house。

那系要写你算拜。So the number times I take things out of the bag is order E。

And then the number of times that I mark any vertex。Well。

 is V times because every vertex is marked only once。And everything else。

The overhead for running the for loopop， even inside。

 the overhead for checking whether evers is unmark。

 the overhead for checking whether the bag is empty or not。

 the overhead of putting past in the bag at very beginning。

 all of this is like in parallel with something else that I've already analyzed。

Or it's a pump of putting the S into bag as soon it's taking constant Im checking whether the bag is not and well the last iteration that took constant time and then every other iteration I take something from the bag so I know the total number of times the water loop runs is what equal two。

I check whether B is unmarked at most once for every time I take something out of the bag。

 so everything boils down to every line of code， I can say this line of code executes once or order V times order E5。

😡，Oh across the entire algorithm have not just within。

This is one of this rare instances where you don't little pollute and ask how many pine this a little bit and let around any kind in pollute。

 but it's more， but you actually need to tear things apart。

To understand sort of more globally what's going on。

Are they questions about this algorithm or its analysis？谢谢。What the last line4 down back。

I you whether it's， so there's a question about the last line highlighted in green。

And why I would I check before I go to versus student bag whether it's already markeds？啊Yeah。

 do that。How wouldt that the time it will reduce the running time for big O of v plus each to big O of v plus。

It'll change the big out constant， but that's all that will change。

Because it's still the case that for every edge， you're going to use that edge put something in the bag potentially at least once。

Yeah。So yeah， you can do some optimization here， but it's not going to have any effect on the overall running time and it kind of ruins the generosity of the algorithm because if you do that optimization。

 then when you're using a you， I believe no， when you're using a stack。

 you don't quite get up for search and get something else。Yeah。

Whatever represents all the neighbors correct so what I'm saying for each HW here。

 what I'm really saying is。For each neighbor。W of V。So it's。

Looping over the neighbors of the or equivalently it's looping over the edges into the t。

But V there fixed by the I would think about that and don't use the actual variable。还告诉你这个东。

Because again， for every edge UVv。You puts V to the back and V puts you into the back。

The first time I visited V， it will put you into the bag。First time I visit you。

 it will put the into that。嗯。So。for example， the first time I visited this node。

 it put the node in the bottom right into the bag。And the first time I visited this note down here。

 it put the note at the top of that edge to the back。So for every edge。

 there's two wordstzs that putting complement pie。So what I'm showing here down below is a very slightly modified version of whatever for search。

 where the bag， instead of storing a single vertex， I'm going to store an important pair of vertices。

It would the exception that there's a spectral gloss I of X called at the beginning。

 which I just used because S doesn't have any incoming edges doesn't have account so the idea here is as I run my algorithm I'm going to assign a parent。

To each node as soon as I work。And what happens inside？

The for loop here is I'm looping over all of the neighbors of aver being that I pro the first sign。

And remember I want I putting convenient into that， but whatever you is， I'm sorry w into that。

 but I'm very exceededing it did。So when the vertex is pulled out into the bag。

 it knows you could blame for each visit。The objects that we blame for it a sense it's called our appearance。

So what this does is it assigns a parent node。😡，To every vertex in the graph， except S。

 if you walk through what happens here， the parent of S is only you can nu。

OkaySo what you're going to get here， let me just build that same example graph from the 1200s Roman legal documents。

Here's S。对。嗯。So I put S null into the null s into the bag now I needed to take a pair Pv out of the back now I know this null S that people need to give the bag that that initial itereration loop P is null and V is S。

So then I'm going to mark the for the first time because I haven't marked anything yet。

 so I'll mark S， and then I will assign。😡，This parent we this parent as to be enough。

This means V S doesnt have a merit。Then I put the other neighbors of asking the bag。

 but they remember that they were put into the bag。By S。So the next iteration。

 maybe I pulled this note out。I market for the first time I assign its parent。

And then I put the neighbors into the bag。But each of them is now blaming the whatever whatever that note is now this note over on the left it's been put into the bag once by S and that again this is part of this you could optimize and copy I think it's cleaner actually think about don't do that optimization so that when I pull something out of the bag maybe what comes out is this pair。

And so in the end， what I'm going to end up doing is for every node in the graph。I'm going to assign。

Apparently。有。This。嗯。Thanks， so now WFS assigns。A parent。To averi。Vertex。Reachable。From S。

 strictly speaking except S itself。And moreover， these edges that go from V to V dot parent。

There are no cycles。In the directed draft of character endod this。

The reason there are exampless is that whenever I might。Wake up， I'm bored and I blame my parents。

My parent was born earlier。And he claims his parents and claims his parents set out on all the way back to birdness。

So they're cant be in cycles because when I married。

Every person I compare is sometimes that's older than。So when I walked down these directed edges。

 the vertices are getting older and older in terms of when they were discovered。

 when they were put when their parents were， when they were marked。And they're exactly v minus one。

Parent edges。And so these two factss。The fact that there no cycles and the fact that they're exactly the minus1 parrot edges means that the parrot edges。

Define。A spanning tree。Strictly speaking of the reachable vertices。Okay， so with wrap。

Where number that is long last when I。And interact has。第份。It's one of the working definition of I。

 three sa thats nose titles and connected。Um， but equivalently scrap that has no cycles and emergencyity that would one less。

numberumb of managers is both enough member。Okay， so。This。Spanning tree。

Is often the thing that you actually want to compute when you are doing a of a personal graph it's not merely that you want。

To vision ever know， but want to build this larger structure from within the violence。

Um that connects all those reach over to seeds together。

 but using the minimum possible number of edges。没有。Now， depending on。嗯。What you use as your bag？

The spanning trees are going to look very different and they're going to serve very different purposes。

 so in particular if。I use a stack。As my bag。I get an algorithm known as depth for search。

The Spanish trees for debt for third had the main least to death had to be very deep。

The idea is that Drcker as smooth that he out the inan immediately to top of that new place he before it for。

It tries to explore downward outward quickly。From wherever it happens to me。

 and so for this written graph that ever heard light is speaking for a single very very long path。系。

Now you said at the fair amount was time talking about why that's actually something that's useful。

The other side of this。Is if you use a PIOq as your。That you get out this all breakfast。

And as mostly the Navy suggests， breadth search treats are broad rather than team。

 so one way that you can think about how breadth for search behaves。

s it starts at just considering the single vertex at its center。

 and then the next vertices that are processed are the neighbors of S and the vertices that are processed after the neighbors of S are the neighbors of neighbors of S。

And so you get this sort of expanding wave。Coming out from us。Where。Everything that is。

Once step away is processed two step away， work everything three step away and so on。From the source。

So what you get in this case。Is。Not just any tree。But a shortest path。The pads in the in the。

Bretfast search tree from say， you know here's some node S to some node V。

That path from SV has the minimum number of heads among all paths for me。

This is be pro for it's not algorithm。Now usually when people say your towards as they're meeting their knee joint in name as an spectrum。

 doctor doctor lip is a variance of reference or will then have weights and in that case you're not using the standard for per as your bag but rather。

You know， Dykester's algorithm。Uses a priority queuee。As the bag。

Where the priority is to estimate a dissonance to the priority index in the。

This is not the only algorithm that could be phrased as whatever person using a priority queue if you simply use the weights of the edges themselves as your priorities。

 then you get。😡，An algorithm that everyone calls Prims algorithm， but is due to yarnnic。

Which needs a standard。Go how starting to grow that holding the lighting set can holding the life can holding the lighting set it can to grow3 that turns out to be the minimum standard be graph if you modify diktro to instead of adding ups。

Go along the path that you're embedded the tree， you take the minimum weight that you slow the tree。

 you can think of the weights now as set length to that just taking the bits and how there finding go why is path from that you I a truck thiscent light。

Fund private or or as some left in the many wide。This is useful for some algorithms that we talk about in。

473。So you can get you know， widest pads， again， using a primary queue in a way that's more similar than what extra does that can used in a difference。

But。Again， all of these three examples over here are what I would call varies of that birth approach。

You have some way of ordering ob or ver tube so that when those our back so that we use to that。

 this is， the best thing on that。So these are。You know， best。First。Search。

All of these are avatars of whatever per search， all of these run in using a order B must bag on license。

So her priority queue change log in times within winter kind ordering in。

All of these algorithms build span trees。All these challenges are。诶。

Any questions about sort of whatever for search in general before I go on to the next point？Yeah。

So typically when I say whatever first search， I'm sort of assuming that each of these operations takes a constant time。

 unless I need to say it's a priority space' log and a different data structure than it'll take off the longer run。

But in general， if I don't care。What the bad is， the right way to describe the algorithm call is whatever her search。

 don't decide to use a stack or a queue if you don't have to。

There may be other reasons why G algorithm that other parts of the algorithm that you're designing would prefer that you use a queue and so if you decided to use a stack that would have to do more work。

So just say whatever， I don't care， implement the bag and hole we want。Okay。So。

The kinds of questions that this。This algorithm can answer。

So I'm going to think specifically about undirected graphs for a moment。呃。So one is connectivity。

So U and V are connected if there is a path from UVV or equivalently if there's a block from U so walk path not allowed to a walk can repeat whatever it wants。

 but if there is a walk from you to be， then there is also a path from U toV that basically you just say。

 oh， whenever I it's only repeat then that walk defines a solution throw。嗯。So I can ask。For example。

 which nodes are connected to you are you would be connected just by running whatever particular from you。

😡，More generally。😡，The relationship you send to be is an aous relationship。Thats pretty。

if you the be that is to you， if you would be protected and be un be protected。

 then you would protected。So it's an equi relationship。

That means it partitions the vertices into the equivalentvals classes which are called the components or sometimes redundantly the connected components of a graph。

 so if I have a graph that looks like this， for example。

Then maybe I want to identify all of these vertices as belonging to one component and all of these vertices as belonging to a different component。

And I can do that using this wrappper algorithm。So instead of just running the anniversary influence for a motor verx。

 I'm going to run it multiple times。By wrapping it and a loote over all purposestics。Really。

 I think that this as like my data structure represents verticesis integers so that for all birds be。

 that's really just per V goes from to one to end。And in particular。

 now inside the whatever for search， I can maintain a counter。

So here I'm passing in an expert variable count。This is the number of what I call label one count is the label that I want to give every vertex that's connected to the neutral vertex Z。

 so everything in that component is going to be labeled as belonging to component count。

Encounting an encounter that goes up by one every time I visited a new component。

 so in if I run this count label algorithm on that disconnect connecteded graphite there。

 maybe every vertex that's colored red would be labeled one and every vertex that's colored blue would be labeled two。

At which point I can then check the cause of time whether it's student versions are connected by others staff and。

This algorithm runs in order V plus E time。😡，Um， and you may say， well， wait a minute。

 every time I call whatever for search that runs in order V plusy time， but remember。😡。

The Republican time was being dependent only on the numbers headed weaker or from the back。

So what I'm going to get。So my running time for the red search is order v1 plus E1。

 where v1 and U1 are the number of ver and edge in that component。Plus。Order V2 plus E2。

 where that's the number of versus headers in the blue cloud。And these are misjoints。

So over the street， the entire wrap up algorithm， I at constant find every verex and I was spent constant finding Ed。

嗯。嗯。I mentioned earlier， I can also compute shortest paths。But this I need。

Either breadth for a search or diktra depth for a search will not complete the short path。

In director drafts， the security， then in the standing room is the security ca。

 and so there only one half notice three， so did not control that。But in general。

Deb for research is not usable towards status。You really do need bread。

Or you need something that depends on the weights and edges if they have weights。可以可以。Again， here。

 the running times are。嗯。Order v plus E。Order V plus E。Breth for search is order V plus E， Dyktra。

 I'll keep it simple and just write it as e log V。Okay， questionsestions about undirected graphs。

So directed graphs are not。That different。In terms of the algorithm。

 whatever first search looks exactly the same， except now when I talk about edges。

 I'm talking about record edges。😡，The analysis is the same except now I can say whatever to erect it in。

I' going to put one vertex into the bag， namely the head of that edge。

 the edge that the vertex that the edge is pointing to。So again， I'm using the。

This notation of an arrow instead of just in order to prepare to make it sort of visually more apparent。

 whichs we then pointing the direct to the tail in which is the ahead so really are a head the tail our arbitrarybitarily of the prison the lives。

I could't put to easily well time from another order， I couldt used you know child and parent。

 I could't used left hand and right hand， but for a number of reasons I think it's helpful to imagine that。

Directed edges are things that you traverse from the tail to the head。

 so if you want to think about a method with one way roads。

 the direct edges naturally modeled not only how the roads impacted intersections。

 but the direction probably along with its roads hit hint homework。

So the basic algorithm is the same。There's a little bit of subtleby here in the definition of connectivity。

So here is。A。Directed graph。IfIf I run whatever first search from this vertex。

 I will reach this and this and that。😡，So it's true that。Whatever ver will mark。

 every vertex reach a full from S。Okay so reachability is for the directed analog。

So I say that that you can reach the so you can reach。The or the is reachable。From you。

 that means there is a directed path and more're generally a directed walk from UVv。

Sees of edges can have to tail they always going into it exactly to our address。诶。So。

Whatever first search now builds。A spanning tree。Of the vertices。That are reachable。UmFrom S。

But this reachability in relations is no longer a center。嗯。

The S can reach this vertex over here on the right。

 which I might as well call T just get these names so I don't have to keep talking about this or and that goes X so S can reach T but T cannot reach S but T can't reach any。

Directed graphs have sexual her be called sources and stins， so a source vertex。

Is one that has no incoming edges， a sink vertex is one that has no outgoing edges。

So diane water is slowing along the head in their indicated direction and the solar is like a spring where water is appearing out of the ground。

cent like the sink where the water goes down drain。嗯。Nothing is reachable from the sink side itself。

So if I run research T， the only vertex that would be marked as T the other if I run whatever the did。

 you do every vertex is graph that you marked is every vertex in is this graph。So iss a bit new。

There's a。A symmetric restriction of this called strong connectivity。



![](img/80e38720eeda2d45d345c6eb23c87f57_4.png)

Which is。

![](img/80e38720eeda2d45d345c6eb23c87f57_6.png)

What will。Okay， strong connectivity means。There is a directed。Path in each direction。

So there's you and V are strongly connected if you can reach V and V can reach U。U。

This is an equi installation。And its equivalentvalence classes are called strong components。

The strong components are a bit more subtle than regular components in undirected graphs。

So just to show you through an example， here is a directed graph。

With its strong components highlighted in various colors。Okay so if I look over here。

 just let me just focus on this part。Um。If I look just say at these four vertices。

Within this cluster of vertices， each vertex can reach any the other vertex and that's because these vertices are just connected in a directed cycle。

系。嗯。😊，So every A can reach G， G can reach out。FHG and so on again this connected this strong component down here again is just a single directed cycle the yellow strong component is a bit more complicated it isn't just a single directed cycle。

 but it's really two directed cycles。Join at this vertexa H except that it also has this extra edge in the middle the point is that that yellow subback is strongly connected。

And really reverse text and really February very load than that。In both reference。嗯。

On the other hand， we've got a couple of strong components like P here is a sink。

 it can't reach anything except itself， so it is its own strong component， E here is a source。

 it can't be reached by anything except itself， so it's its own strong component。😡。

And more generally， you might have isolated vers and strong ps that are div sources。

These strong components are organized if you imagine taking each strong component and collapsing it down to a single vertex。

😡，These strong components to organize teams on many days often river to as the strong component graph。

Or the meta。Or the condensation。Let's call this the meta。Of G。

So each vertex of the metagra is a strong component of the original graph gene。So A B。

 F and G form one strong component， so there is a technical ver in the matter labeled ABFG。

There is a defense。From one vertex of the metagram to another。

If there was an edge from the tail strong components to the headstr component， so for example。

This edge here。Exist because there is an edge from some vertex in the pink component to some vertex in the yellow component。

 so this one will do。😡，Actually there may be more than one such edge， in fact。

 in this case there are three， there's G2K， D2C and FL。

The fact that there's at least one means that I can put an edge between these strong moments in the me。

E is a fourth in the original gra， such as strong components。

 corresponding to E is all forth in the meta graph。E is at the same in the original graph。

 so that being appears as an audience related vertex in the metagra， but it's still also the same。Oh。

Now， do you notice？Anything in particular that interesting about the metas。As a breath。

Here's a graphic here on the left， it's got five vertices， got five edges。

But there's one thing that whenever I。1ざ。And this is something， this is a directed。Acyclic。Rough。

This graph has no effect。And the fact that the graph has been recycled is really really useful。

 but it needs something very different than what it means for an undirected graph to have been solve。

An undirected graphic with nerve cycle is to hold the horse。It's a graphic village poll。系。

That's not a tree it's got the stain that branches out emerges again。

 the too many edges to be a tree it's not those have the right kind of connectivity。

 but it's still really useful。嗯。I'm not going to。I'm going to talk about directed basic grasp for the rest of the lecture。

 but I want to mention before we get too much further that this structure，😡。

Both the identification of which nodes are in which strong component and how those strong components are connected in the better。

😡，This can all be computed in linear time。Using a couple of different algorithms that are described in detail in the textbook。

 the one that is easier for me to remember， it is an algorithm by this， its 1030。

 which is guided byF search。And I know that doesn't make any sense， but the punchline is。

You can compute the structure。And the structure might actually be useful for something that you need to do by next Tuesday。

啊 in your time。嗯。So let me go back to sort of looking at the。啊。啊。

Different questions that one can ask about。And directed graphs。Rereachability， again。

 this is a question that I can ask answer in order V plus E time using whatever for search。😡。

If I want to check whether two vertices are firmly connected， again。

 I can do that in order V plus E time by running a letter search you and then knowing whether that's two narrs of whatever for search。

 still V plus E time。😡，If I want to know more generally。If the entire graph。Is the entire？Graph。

Strongly connected。Again， I can do this in order V+ at each time using whatever for search。

If I want to know whether the。The graph is a directed acyclt graph。

I want to know if it has any directed cycles in it， this I can also do in V plus E time。

 but I really need depth for search， not whatever for search。And likewise。

 identifying strong components more generally， I can do that in linear near time。

 but I really need that search， not whatever for search。Ben。

So let me talk about the dad thing in a bit more detail， how you need the tech cycles。

So here's here's depth for search in more generality Now I've added a couple of lines to the algorithm one I've added this sort of preprocess line at the beginning。

 the other is the first time I do anything with the vertex I call this previsit subroutine and whenever I'm done with the vertex I posted sub lots of application that that first this outline。

 but just with different subroutines， differentkeeping put into those three slots that I've highlighted in in blue。

诶，啊。When I was counting components in undirected graphs。啊。S sense。Now。

 I't need to put another line in there so it sorry would this is not quite fault that structure。

The simplest version of what I can imagine doing here is just keeping track of when I visit Vertices。

Okay， so preprocess， I'm just going to set my counter to be zero。And pre visit， I'm going to say。

Let's increment the counter and set。Record。The time at which I noticed this vertex for the first time。

And in post visit。Again， I'll increment to the counter and I'll record。

When I was finished with the weres。嗯。So this years the。But those they clients。With。

He got agreed the three at the time， this is the first time that I ever go the。

He got close to the time， this at the time when I was completely done with anything that ever had to do that。

Now， you all know in trees。The difference between the three order reversal day post board。

You treat a free order commercial， you visit the， and then youar visit objects。

In the post quarter traversal， you visit the subries impcursively and then you visit the roof。Hey。

Dan， normally you think about this probably in terms of black black circuits。

U prior Wilson had an working day down down Les， post murder her we had a visiting police person Florida at least to involved。

If you wrote this algorithm， then sort the purpose you buy their appropriate timestamp。

That is a really order reversal of the graph。Borea for the trees at the exactly the same day that realomaly min。

But this downloadward generally applies to the record graph。

If you sort the birth by their post over time。That gives you a post forward to first the credit。

So if I wanted to do something to every vertex of the graph in post order。

According to a post order traversal， I would do it inside that subrantine post visit。And then就对明白。

If I wanted to do some of the universities in great organizations。

 I would put that something into the website so can revisit and I wouldn't put anything into the green separatebri system。

Now， what do these pre and post order things actually look like？

So here's exactly the same algorithm again except I've just made。

 I guess I called it clock instead of count so yeah。

 just I've be the clock whenever I seen the vertex for the first time I record that time whenever I see it the last time I record that time。

Here is a directed graph down at the bottom of the screen。U thisarrowing one。

 this is the first time I call whatever for， I'm calling on vert pay。And that。

In vocation of whatever for search。Creates this spanning tree。

Of all of the adveres reachable from Vertex A。The other edges you see in various types of dashed lines。

 those are other edges in the graph that are not part of the san tree。

 color back patterns of edges represented if there weren't types of nonsanry edges there are some that called forward edges theres something called backward edges。

 there's something called cross edges， I don think we're going to talk about those in any detail。

 but you can read about those in the book。Once I call DWFS， no sorry， DFS to A。

 I get this diverse span tree of the vertices region from a。

 then the next time I visited it'll mark vertex I go alphabetical order will be vertex E。

 and then it'll mark this spanning tree of the verticose C that are reasonable from E but noninable from any earlier source vertex。

And so this is the spanning forest。That I'll compute by running TFS all where the forral versus beans go in alphabetical order。

😡，And I make the right choices for the order to consider the evidence。

But this is the structure of that I get。No。This。Is a chart？Of the recursion stack。So at time one。

 I call depth for search of A so I push a onto the recursion stack and it will sit on the recursion stack until DFSA is done then get popped off but while DFSs A。

 I noticed that A has a neighbor called B so I'm going to call DFSB and while I'm running the depth research of B。

 I'll notice B has a neighbor called F and so I'll run depth for search of F。And the recurnce stack。

 in this case broken the downward， I realized that's backwards from the way when we usually visualize stacks。

The idea is that the person that had a huge lever， eventually at R out here at Ver D。

 you'll notice that's a leaf in the spanning tree。There's also a belief in this recursion degree that I've described here。

So these green boxes which describe the behavior of the stack。

 also describe the recursion and pattern the recurs of that for search where you have with one box connected below another directly below。

 that means the larger solid problem is calling recursively to the solid。Okay， so。

There's a BFSA called DFSP called DFSF called DFST called DFSC called DFSH called DFSD and DSL。

 DFS L DFSO and so on。This tree you get by looking at these recursive calls。Is。

That green spanning tree of the graph。There's an edge from G to C。Because depth are certain signs。

The gene parent C， but also because death first are the gene Paul's death first if you see person。

And so the structure that you get out， the spanning forest that you get out of depth for search is in some sense。

 just。A record of the patternner re that debt first search。Similarly， when I pop all the way back up。

 and then I start my second implementation in the third for E。

 this recursion tree over here is just a path that's exactly what the say is the path E on and J the other component spanning for us。

诶。走咩。These bars when vertex started to be active， when the stack frame for DFS of that vertex was born。

Those are the preorder numbers。So if I wanted to sort these vertices in preorder， it would be A， B。

 F， G， this is preorder， C， H， D， L， O， K， P， E， I， N， JM。诶。This is sort of。

I don't know that in any applicationss of pre oral， but except for detecting cycles。

 which what I'll get to in the next minute。And then post order traversal is just the order of the right end pointss。

Of these intervals， when those intervals get popped off the stock for the last time。 So that's D。

K O P， L， H C GFBA。MJ NI。e， importantly， three order is not a reverse supposed post order。

And then I think the last thing that I need to say here， and I'll give a proof of this next time。

Which is。Dlemma。Directed Graph G has a cycle。If and only if。Or some。Edge。You to be。We have。

V dot post。Is smaller than W doc post。So if I have an edge that's incompatible with the postover reversal。

 then I know that there's a cycle。I guess said I'll prove this next time if I don't have a cycle。

 then the post order gives me something called To it's going to be a way of order to the vertices so that all of the veraces all of the edges points forward in that order it's just do a post order fromal then right the post order con value。

This will be really useful， but I'll talk about that on Tuesday， thanks everybody。See you next week。

Yeah。Please lecture video for Tuesday's lecture and the to that。Yes。



![](img/80e38720eeda2d45d345c6eb23c87f57_8.png)