# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p07 Lecture_07_Matchings.zh_en -BV1a4cCeMEzb_p7-

ok。Hey guys， so welcome back。And。Some of you volunteered for describingibing the。

Lecture notes from last time thank you if any of you if any others want to volunteer feel free to send me mail therell be maybe two or three of us well sit down。

 we'll write down the notes。😊，It might be a week or so before maybe a couple weeks by the time it comes out。

 but hopefully you'll have notes for。Monday lecture。

Today at lecture the lecture notes are already there。

 I was reading over it there are a few bugs a few typos and stuff like that， but we will fix them。😊。

O。But today's topic is matchings。 and， in fact， matchings are going to be the topic of the next。😊。

Maybe three maybe four lectures we'll see it's a rich topic in fact I should have brought my matching theory book theres a book by Lova and Cllumber on this topic and this book is like 30 years old so theres a whole bunch of stuff thats happened after that but it's one of these sort of rich and diverse set of results that come out of a very simple concept that of a matching。

😊，I imagine， you know， it's given a graph。The matching。 So in this lecture， graphs are unweighted。

 undirected。And matching is a subset of edges。Such that no two edges of the matching share an endpoint。

So。Yeah， so so for instance， the empty set of edges is matching。

But we wanted matching of the largest size possible。 And， for instance， this。And this is a matching。

What key in that。This is the matching of。Size one in this graph。And so， okay。

 so what's the matching Emma the matching。If， for all。E andF。These are two edges belonging to M。一。

Interssect F。 So now viewing E as a subset of two vertics， F is a subset of two vertic Cs。

There must be destroyed information nature。So they can't share an endpoint。 So， for instance。

I can't add this engine because then these two yellow edges will share the input。哦。

But this is another possible matching， and in fact。

 this graph has the maximum matching size these too。😊。

You can run over all possible sets of three edges。 None of them can form can be used to none of them form imagine。

嗯。What else。What's a matching， what's a sort of maximum matching in this graph， for instance。This。

 this and this。Oh matching。And that's a matching of size3。There are six vertices in the graph。😊。

Any matching any matching in a graph of size with six vertices can be at most three。😊。

Because you know， just this condition says that every matching。

 every edge of the matching uses two of the vertices。

 so any matching must be of size at most the number of vertics divided。😊。

And since the matching sizes are the integers， there is a floor。😊，Yeah。

So clearly thats that's a maximum of matching。 So M is maximum。😊，And is a max。妈妈。Mine。

Maximum and I'll make it clear I'll call it a maximum matching but this is a maximum cardinality。😊，呃。

那。Okay。If。For all matching and prime。The size of N is that is the size of N。

It's a maximum cardinity match。I want to just distinguish this。 This is a common mistake。

 So I just want to make sure M is。Maximal。And often when I say maximma， I'll say inclusion wise。曼婷。

If。保装就。异议。嗯。Not an M。M union。嗯。Yeah。Not a mess。You take this matching， you add niche to it。

 it no longer remains match。Okay， so this is just max model matching， inclusion by of maxim matching。

😊，嗯。These two objects might be different。 So here is an example。The yellow matching。I a maxi。

Mom matching。嗯。The blue matching， consisting of single edge， is a massive model matching。Yeah。Good。

 good， any maxim mu matching is also a maxim mu matching， but not vice。😊，Heres a claim， I'll say。

 it's an exercise show that。If can。Maximal。Then the size of M。Is at least。The size of oh。

 And let's say M star is Max Mg。Then M is at least M star。Oh good。

Show that any maxim mu matching is a two approximation to a maxim mu matching。😊，There exercise。

 we should try this。Useful fact， So it just says you know pick edges one by one。😊，And， you know。

 getting a maxim mal matching is easy， right， you can edge。

Try to pick another edge which maintains a matching property， try to pick another edge。

 keep doing this until you can't pick any more edges。That's a maxim mu match。Yeah。

So this can be found。Efficiently， you know， just the。Greedy algorithm。

And today actually I am just going to talk about polynomial versus non polynomial run times。

 I am not going to worry about whether I have linear or near linear run times。😊。

I'm not worrying about right now。So the goal， oh， maybe one more definition。M is a。Perfect。Matching。

The size of M。If we过度。ナンドルワピースにしてらりたい。If every vertex of the graph is matched by the matching。

 then it's called a perfect matching。😊，嗯。So let's just for a moment。

Look at just this kind of example。A notation that Ill use all the time。

These vertices are matched in the yellow matching。😊，They have an edge， yellow edge。

 which is incident to them。This vertex alcohol is open。我然 going it three。Okay。Good。So these were。

 as I， matched。Maybe I'll call it close， but I don't think I ever call it closed， they match。

A perfect matching is one where every vertex is matched。😊，A perfect matching is definitely a maximum。

 maximum everything。😊，Perfect is just perfect， right that's why it's perfect。Good。Various facts。Yeah。

 okay， let me not get into that。 Today's lecture is going to be about finding maxim mum matching。😊。

风哥。对。How do you find maximum matching in graphs， and that's what we want to talk about。嗯。

How do you find maximum matching and growth？哦。So how do you。You know。

 one of the things with algorithms and this is it starts presging the definition of various complexity theory。

 things like you know， the idea of polynomial time。

 the idea of NP non deterterministic polynomial time。😊，Kind of comes from。You know。

 asking questions like this， how do you suppose I have a maxim mum matching？😊，嗯。How do I show you。

 how do I prove to you that this is a maximum matching。

 I have an algorithm that produces a maximum matching。😊。

It should prove to me that the output it produces is maximum。On。You know， so。

 so how do I assure you like M。Is Ill just call it max， so from now on it's maxim mum。

 so I'll just call it max matching。😊，啊。So， how do I prove to you that m is a maximum match what is the characterization of a maximum match now one thing you could say is you know try all possible laser matchings the definition says all of them have size which is at most soci of effect。

😊，But that's not very good， that's not very compact。Let me try to give a different character version。

嗯。And so this is a theorem。Often attributed to Claude Burch。嗯。

So in order to say this theorem I need a definition， so let me give you a definition。

I should have done the definition out there， but let me do the definition in this little。😊，过来了。

あの六月で話新。Fix the matching。So I have a graph and from now on what I' am going to try to do is unmatched edges。

 So I have a graph where some edges are matched and some edges are unmatched。

 Some edges are in the matching， some edges are not in the matching。😊，Unmatshed edges look like this。

 mashed edges look like this。If it's unclearki， just ask me。A path like this or a part like。This。

Which just alternates between matching and non matching edges。Its called an alternating part。

 it alternates。Non matching， matching， non matching， matching， non matching， whatever。So such parts。

I known as M。Alternating。Okay。哦。嗯。Look at an M alternating path。In this case， so notice that。

So I'm going to take the free vertics and I'm going to make them into little circles to emphasize that they are free。

😊，This spot。Starts and ends at a free verortex and is alternate。Yeah。So if B is。嗯。哦你度你点。And。Starts。

And ends。At。Free verortex。Then， P is called。And augmenting。系。In the in the graph。

 I have a path that starts at a free vertex。😊，So it has an unmatched edge because it's free。

 So this edge it must be unmatched。 It must be not in the matching。In the matching， not in not。

And ends there。Yeah。This is called M Ogm。ok。Fact。The length of such a pe must be。Order， even。O。

How many matching the edges does it have half rounded down？😊。

How many non matching does it have half rounded up？So now， suppose you took。You took the matching。

The original matching。You dropped these two edges and instead you added in these three edges。

So just because an alternating path has alternating。😊，In and out ages。

In out in out or whatever out in out and etc cetera。If this vertex is open。😊。

Then this edge must be out。And the last year， it must also be out。So if a path ends with an outage。

And ends with an outage， and is alternating。When this parity save that it must be odd。嗯那个那么。

The number of edges in there。冰。Has。And more number of letters。Thank you， I can see the confusion。点咩。

So given a path P， now I can define matching， so p is M alternating。Oh， sorry， P themm augmenting。

And。😊，Sysymmetric difference P。Symmet difference means whenever， you know。

 whatever was in it now out， whatever result it was now。😊，Is also。I matching。And。

The size of MP is strictly more， but equal to the size of。什么呀。If the is。And。我命定。こそ。呃，M表示。

So let me let me do an example。 let me see if I can bring down one of these。

 I have some pictures out here we can do。😊，嗯。没。Select source lock into camera。I just want left。Okay。

만 뭐 다학교 안噶。ItDoes't matter。 Let me show you guys。There's a lot going on。

Let me just turn the lights off for a second。

![](img/8d97c76b2921cf10af211364fb8e61fe_1.png)

O。Here's the graph。 It's some crazy graph。 Can you guys see。It's a。Okay。It's a graph。

the dark blue edges， maybe some light is needed， I dont know。Yeah。

The dark blue edges form a matching。And now。You might have to borrow a pen from somebody or a marker from somebody。

Somebody brought her。Can somebody tell me and。So actually， look at， look at this path。We you。

So this was out in， out in， out in out。That's an am augmenting path。So what I could do is。I could。

Now， ensymmetric difference that parts。😊，Well have this would be in。This will be out。In out。And。Out。

嗯。The size of the matching has gone up by one。本人呢。Here is another augmenting path。

 I think this is an augmenting path。I'm going to bring this in。 this will go out。

I'm going to bring this in， this will go out， I'm going to bring this in， this will go out。咁我咯。

Bring this in。 This will go out。 I'm going to bring this in。That's one more augmenting part。

 The size of the matching has gone up by one more。Okay。😊，So if you can find an augmenting path。

You can kind of toggle the augmenting path。And the size of the matching goes up by one。咩。So。

 that is one way of getting larger matchings if you find augmenting path。呃。要。哦可了。Yeah。マンスクト。

So if you find an augmenting parts。😊，Dog love banking course。And you'll get a large image。So。

 this shows。That if M is a maxim mum matching。Then this means there is no。And。Amenting。Contrapoitive。

 if there was an em augmentmenting path， M is not a maximum matching。Yeah。

So we proved one direction we proved。This generation。If M is maximum matching， it has no oing。

I want to prove the other direction。 If M is not a maximum matching， then it has an augmenting part。

喂。So let's do the other interaction。Suppose。M is not maximumim。So there exists an M prime。

So whose size is bigger than the size of them。Now， I want to show this means there is an augmenting part。

How do I prove this？And this is the classic matching argument， you know。

 if there' is one argument you should take away actually theres several arguments where I'll say， oh。

 this is if there's one argument you should take away you should take away this one。

 but definitely take away this。😊，De。So M and M prime are two matchings。

One I'm going to draw using straight lines， one I'm going to draw using squiggly lines。적感지를。

M symmetric difference M。This contains edges which are in either M or in M prime， but not in both。

Fair enough。对。What does this consist of？This consists of a bunch of edges from M prime， let's say。Oh。

 by the way， what is the degree of every vertex in a matching？😊，Atmost one。

So if I look at the symmetric difference， think of this as a union。 It doesn't really matter。😊。

What is the maximum degree of a verortex2？What does the graph of degree 2 look like？반쪽 버튼 사이。

OkaySo this has。8。And scientists。Qu over。These parts and cycles must all alternate。😊。



![](img/8d97c76b2921cf10af211364fb8e61fe_3.png)

So it must look like this。And there might be a cycle like this。😊，There might be longer cycles。

 there might be parts that look like this。Maybeパーツ know whatever partsツ likeます。Look at any cycle。

The edges in M and Em prime alternate。So this cycle must actually have length even。Yes， no。Yes。

 thank you。So all these cycles have an equal number of edges from M and from M prime。😊，So。

 the score is equal here， the score is equal here。😊。

There are parts which are of even length and parts which are of odd length。

Can all the path be of even length。没有。Because in part of even then， thes score is even again。

And I know that M prime must defeat him。So there must be at least one part。Where M prime。

 there are more M prime engines。Then images。ok。This edge was in em， but not in M。

And this was the path， right， I mean， this this vortex must be open。😊，In M。

Because if there was an A and M coming out here。This path would have been longer。

In fact don't even worry about this。だね。I'm allowing parallel。

So this is they must exist at least one path where there are more em measures than images。😊。

And this is an augmenting process。There's no， maybe questions。Let somewhat。

Everybody is a little subdued。Im some due too。 So it's okay。安住。Also this。啊。그やです。Does this make sense。

 Does this proof make sense？Yes。唔该。That shows that if。M was not a maximum matching。

 there was a larger matching then they must exist at least one alternating parts。

A one augmenting path。One M of。And so this gives you an algorithm augmenting to find maximum matching。

If M is not a maximum matching， find an augmenting parts。It will increase the size by one。

 keep finding it until you can't find any more augmenting parts and then I is a mass。😊。

To the question， big question becomes。How to find。M called9。Also， here's another question。

How to show。That there exist no argument。See I need to figure out。😊。

When how to find an augmenting part and then once there are no more augmenting parts I need to be able to show that there are no more augment。

😊，Do I need to know when to stop。I should do both things。Yeah。So， by the way， you know。

 if you find an augmenting path， you can just look at it and say， look， this is an augmenting path。😊。

But how do you show that there exists no augmenting parts。This again， comes down to this question of。

定。What's the short proof。That there no。In the graph。Which is the same as asking the question。

 how do you show that M is maximum？😊，I have given you a way to show an easy way to show M is not maximum。

 you can show me an augment but I will say okay M is not maximum。😊，But how do you show am is max？

Exactly， so that's a non compact object。😊，I would like to give you a compact。 perfecterf。So。

Which leads us to the second theem。 So by the way， this was like the theorem number one in the theory of matchings。

😊，멀 you세요。M is maximum if and only if it has no augment impulse。

Theorem number two in the theory of matchings。Okay。Is called。你心心唔楼会牛听。关念铁。行。😊，Soう。

I'll tell you what connect theorem is。So， you know。

The theory of matching really breaks down into two parts。For bipartite graphs and non bipartite。

The case of bipartite graph is much easier。呃。It gave a number yeah。

So conterum is now only it calls for bipartite。And what it says。Is that it relates？

The size of a maximum man to another object， which we will call。A vortex cover。What's a vertex？

A moretx cover。😊，Is a collection of。Vertices。Next。Hits。All the ages。So V is a vertex sorry。

 C is a vertex curve。If。For all edges in the graph。E viewed as a set of two vertices， is an edge。

 two vertices。😊，Interssectex C。It is a set of vertices such that every edge has at least one end point inside sea。

😊，So can somebody give me a vertex cover of any graph， I mean， for any graph。

 suppose I ask you for a vertex cover， whats a vertex cover。😊，The entire set。

But we can have much smaller vertex covers， for instance。This is a verortex cover for this graph。😊，对。

What's the vertex cover for this graph？😊，Let say。This is the vertex component for this graph。😊，不在。😊。

Oh， this is not a vertex killer to describe。Quite right， thank you。I记个。

What is the vertex cover for this graph？😊，This is the vertex cover for this graph。 Let's just check。

 am I cheating again。😊，It's right。If I were DVS， I would have said， oh。

 I was just making sure you guys are following clearly I was I was goofing office。😊，啊。Good。

 what's the verortex covered for this graph？😊，メビ です。です。Yes。Okay。Cim。Okay， so from now on。

 I'm going to write MMm to denote maximum matching。And we see to denote verortex cover。So。Can。

So this is part one。A vortex cover。The size of any vertex cover。

Is at least the size of a maximum matching in。喂。Think can imagine。

The edgeages of this matching share no endpoint。So if a verortex cover has to hit all the edges in this matching。

😊，I need one vertex for the first edge， one for the second edge， one for the third edge。

And maybe more。The size of a vertex cover is at least the size of a maximum match。 in fact。

 any vertex cover is her size at least the size of any matching。😊，That's the samescape。

What Knning says is for bipartite graph， the size of a verortex cover is equal to the size of a maximum matching。

😊，What is the bipartite graph bipartite graph is a graph where there are two sets， you know。

 the verortex set consists of a left side and a right side。😊，And all edges go between left。

There are no edges on the left。 There are no edges on。good， so。Our vortex cover is any。😊。

So this should be min vertex cover。And you are absolutely right this I should be saying max。Yeah。

Absolutely。So I want to say that the minimum word takes cover。😊。

Has the same size or bipartite graphs。As the maximum match。Let's just check we got two examples。

 these two are bipartite。😊，In both these cases。😊，The size of the maximum matching and the size of the verortex cover are equal to each other。

😊，Thats an example which is not bipartite。An odd cycle cannot be in a bipartite graph。

 because you know。Left， right， left， right， left。And then there would be two left left。

 There would be a left left edge， not lot。Bypartite graph here the maximum matching is size2。

 the vertex cover as size。😊，这就是感。So clinic theorem。Is false。For general graph。

But for bipartite graphs， it's true， it's et。Okay。So。

 if I wanted to show you that you know whatever solution we had come up with out there is a maximum matching。

 I could show you you know maybe not on that graph because that was nonbipartite but in general for a bipartite graph if I found you if I found for you a matching of size。

😊，4our。And a vertex cover of size 4。😊，I know that the two must be both often。

Because any word is cover。Is an outer bound on the size of the matching。

And if both of them are equal， then both of them are wrong。What does this remind you of？Dualality。

 strong dual。Also， you know， one example of duality is the maximum Min cut theorem。

And those of you who remember the maxlomen Cartheum from your previous classes。

 this is a special case of maxlomen Carium。😊，But we are going to prove it， you know。断过钱。And in fact。

 you know， I said this at the first lecture， but you know。

 at the end when not all of you were here secretly the the the the。😊。

The protagonist of this course is dual。You know， again and again， we'll be like， oh。

 how do we argue about this object， what do we do。Well。

 we are going to look at sort of dual dual relations like this。

 These are often known as max Min Max relationships。😊。

How do we show that something is a maximum object， you say well， I am going to find something else。

 which is a minimization problem and they are too optimize。Just one example of that。

But this is coming here， and were going to show So one direction was easy， right？😊。

This was we just proved it， we said look the vertex any vertex cover has size at least the size of the match。

😊，I need to show the other direction。So， in fact， I'm going to。Two words with one stone。

I'm going to give you an algorithm， so I'll give you an algorithm。To find。An m augmenting part。

And when this algorithm succeeds， it succeeds， it's fine and a augmenting path。

 you get a bigger matching。😊，And when it fails， it will give you a vertex cover of whose size is equal to the size of the match。

😊，嗯。It's perfect。 You， this algorithm says， look， here is the bigger matching， or it says no。😊。

There is no bigger matching。 In fact， here is the vertex cover to prove that there is no bigger matching。

😊，没有。SoLets， let's show this out。And remember， this is all for bipartite graphs， right。

 so let me give you an example。😊，So this is a bipartite graph。And let's say。This is my。Grauff。

And this is my current match。Is this a maximum matching。

 no its not because the maximum matching is the matching that goes straight across at size3。😊。

This is a size2 matching。But there is an augmenting part like this。Yeah。So I should find this。行。

And remember our notation we just said。It is a bipartite graph all the edges go from left to right the left edges are the left vertices are called L。

 the right vertices are called R。😊，So here's what I'm going to do。

I want to find a augmenting path what is an augmenting path it is a path that goes from an open vertex to another open vertex and is alter。

😊，So let me start off with all the open verticC， so by the way。😊，嗯。In a bipartite graph。

 an alternating path sorry an augmenting path。😊，Must。Have the start and end on opposite sides。

Why we said it has an odd number of edges。In a bipartite graph， every time I take an edge。

 I cross the river from left to right or from right to left。So if it has an odd number of edges。

 I must end up on the opposite side where I started。😊，So let's look at all the open vertices。

These are the open vertic Cs。嗯嗯。If there' is an augmenting path， it must start from one of these。

Okay。It must start from one of these and all the edges coming out of these vertices。😊，Are unmatched。

Because， hey， they're open。Suppose one of these ver season is open。We are found in alternating parts。

 We are found in augmenting parts。So none of themあろう。They are not open。They matched。

So what do I know， I know they are matching。And is coming。

Can these matching edges going be going to these guys no， no， no， these are open vertices。😊。

So these matching edges must be going。Further down。

Can these matching edges be going within this piece？No why빨 때个。行。So remember， by the way。

 we started on the left， we went to the right now we are back to the left。😊。

Can any of these verticaltices be open， not at all， I mean。

 we reach them using matching matching edges。😊，we were clearly matched。Just look at their left side。

 they've got a matching tail coming out。Yeah。Some of the vertices might have， you know， that's it。

Other VTCs might have other edges coming on。Can these be matching edges， No， it's a matching。

 These guys are already matched to the left。😊，They cannot have more matching edges。

Look at un match edge is coming out of this case。They must lead to other vertices。不。They might also。

Lead back。Previous that's。Fair enough。Suppose one of these is open。😡，What then。마는 엄。た 딱 딱。

So none of these are all， all of these data I taken。T 플。They must have matching age just coming on。

Let's continue this process。嗯。Some of these vertic Cs might have nothing more coming out of it。

 some of them there。Matching edges might oh， so D R， this is there。It might be going back there。

Oh actually， it cannot be going back。The， immediate， right。LR L RL。

So they could have edges going back later。一 적게。Some of these might have other edges coming out like this you will repeat the process we look at these ver see are they unmatched if they are unmatched I have found in all generatingating parts。

😊，If not。Matching edges。So。Keep doing this process。At some point， you run out of ver。

So either you found an alternating park or you ran out about。嗯。对。啊。啊。该a。We tried， we failed。

To find an alternate an augmenting parts。So then what do I need to do。I need to show you a ver。

Of the same size of this matching。I got a matching M。I tried to find an augmenting path， I failed。

I'll show you a ver X cover of the same size。没。How do I緒です？对。By the way。

 let's just say at this for a second。Can somebody tell me a vertex cover for。

Just the vertes that I have seen。You know， they might be notice that this might not be the entire graph。

So for instance， here is an example that might be useful to keep in mind。I have。What do I have。

I have。Maybe a graph like this。This is my left side， this is my right side。By matching。

 what's the maximum matching in this graph？用。And let's say my matching is this。

I start exploring from this vertex， this is an open vertex。😊，So this will be the zero layer。

 this will be the first layer， this will be the second layer and I will be out of sport tissue。😊，嗯。

But there is some other portion of the graph which I have not really looked at。😊，In this exploration。

 that's okay。Let's just look at this portion。Can somebody tell me a vertex cover for this portion？

A set of vertices。A small set of vertices。Whose size equals the number of matching edges out here？好有。

All the Rs。

![](img/8d97c76b2921cf10af211364fb8e61fe_5.png)

So let's look at these guys， let's look at this， this。Yeah。哦。你说。

Not necessarily because they could be think about this example。😊。

I have just explored only a portion of the graph。Because I started from the only open vertex on the left。

I looked at its neighbor。And I followed the matchingtting edge。

There might be other pieces of the graph that have not explored。我你现在。多你多。到时。我知道。

Ask the question again so they missed the first talk？

Or we reached a stage where there are no more edges that are going out。

 I can't extend this any further。😊，There could be other edges which we could not reach from here。😊。

That's all。是。They could， you know， for the moment， ignore this portion。There could be other stuff。

 but let's just ignore this。In this。Portion of the graph。

The claim is that the size of the the total r's， the number of verities in all the r's equals the matching size。

😊，Is this true？Notice that each vertex in R。Had a matching edge coming out of it。Yeah。

And we Ver seasonar are covering all the matching edges plus all the edges going backwards。😊。

So in this portion， at least。😊，The Rs， the union of the Rs。Equals the matching。S。是。没了。

I need to worry about the rest of the graph。 there is some remaining portion of the graph as well。

 so let's just do the argument， so here is the here is the final argument I just Ill just complete the argument now。

😊，This is all of the left， this is all of the right。😊，This portion is the portion that was seen。

Exent。This is the remaining portion。对。How did we do this here what the open world is？😊。

We took their neighborhood， we came back along matching edges。We took their neighborhood。

 we came back along matching edges， we took their neighborhood and so on before。

Until we could go no further。Our proposal for this portion was take this。

This is the vertex experiment。My proposal for in general is。Stick。This part and this part。

This is a vortex car。And this is vertex cover。😊，So my claim is that this verortex cover。

Has size act most。The size of the matching here。So I have to show two things that this is a vertex cover。

😊，And。It has the right size。Yeah。Just to be clear， it's not。

Just that we could have a disconnected drive。That allows us to run out emergencies。

The other thing that can happen is that。We go to some vers to the right。

 then we take it to matching edge right in order to sort of a little more verncies from reality。

But it might have had other non match， non matchshed edges。So the graph might be connected。

 but we don't take those from the right roots and only take long。

 we only take the matching vertex so that can't sort of expand absolutely。So here' the verortex。

Which has a non matching edge coming out of there， which is connecting to this portion of the graph。

But we never explore that。嗯。Good。So we need to show two things。This is a。Vortex cover。So。

 let's look at it。Where are the edges going。The edges might be going from left to right。Up on top。

 this covers everything。There might be edge just going left right out here， discovers everything。

There might be， I just going。Bottom left， top right。Both cover。

The wording edges are the edges which go like this。The question is。

 can there be an edge that goes from the top left？In the bottom right。那你这个。Whats that exactly。

 so let's look at the cases。Suppose this is a non matching edge。Then when I looked at this vertex。

 he would have explored this vertex。😊，This would have been on the left and we explored all the non matching neighbors。

Coming out of this late。So I would have seen this guy。This vortex would have been upstairs。

 He would have been seen。The other case is this is a matching edge。

Can this matching edge go to the open vertices？No， they are open。

 they don't have matching edges to that。In this matching edge go to this vertex。😊，No。

 because this vertex was reached via matting edge from upstairs。It can't have two matching edges。

 one from downstairs， one from。这个是为。아 그 뭐。So this is a vertex curve。😊。

So this is the ver zone at least。😊，Now I need to show that its size is at most。

But that argument is almost the same as we just did back then。The number of vertical is here。😊。

Equals the number of matching edges going backwards。That's what we argued out there。

atI don't need to do all that。哦。So on the top half， the right side is smaller。 whereas the top half。

 the right side is。Is equal to the total matching。Yeah。

 so on the top that I can say equal the size of the matching because every node there is guarantee to be the end the data。

😊，Of of one of these matching edges。And on the left hand side。Each of these vertices。😊，Remember。

 are they open or are they not open？哦。They are not open because the open vertices are sitting up there。

😊，So all these guys have matching edges going。Boing out。

So the size of the matching is at least the size of this。Second。

And there are no matching edges which are going like this。We are never go。一。

So the the shows that look when I stopped。I have， I can show you a verortex cover。

Whose style is at most the size of the matching， this shows the opposite direction， and so we get it。

关性思。I think I the some。啊。So more details than one should see on Friday。

 Wednesday afternoon at3 o'clock， but。😊，You should see these Bruces one second actually later。😊。

Actually， this is really pretty proof。 I I really like it for two reasons。

 maybe I'll give you the philosophical reasons and then I will compel you to go back and give it the proof do it by。

😊，But the second time。It's one of the earliest proof。 It's actually a fairly early proof。

 which shows one of these first maximum relationships。😊，It says， look。

Even though this is like just a graph theoretic proof， it's really giving you an algorithm。😊。

It's saying， look， I want to find a maximum matching。I want to fail。But when I fail。

 I give you a certificate。😊，That I found the maximum magic。And easy to verify certificate。

 not just that oh。You know， check all possible augmenting parts。 none of them alternating parts。

 none of them are augmenting。It's actually saying， oh， here is a small object。Check it size。

Thank you on matching sites。 They are the same。But， we know。This inequality out here。So hence。

 both must be off。是。And the proof gives you an algorithm。

 So this is the algorithm and it finds the matching。

 so it finds an alternating path if there exists an augmenting path I keep saying alternating when I mean augmenting。

😊，It finds an augmenting path in linear time。So you can increase the size of your matching in linear time。

😊，How many times can you increase the size of your matching？😊，Any times。

So this gives you an algorithm which runs in order。开名片。Can you do faster？

So hopcroft and carp in an algorithm in。1970， something gave M square root n。And for a long time。

 the progress was stuck out there。嗯。About 10 years back。A algorithm was given， which was m to the 1。

4。Using some very nice ideas from interior point methods， which we'll talk about later in the course。

😊，And。Building on that very recently this was the paper I was referring to last time now due to Richard and others there is an algorithm which runs in one plus little of one times。

It's merely almost linear。For。In most cases， it's not that。Yes。

 so its better only for situations where the graph is very sparse。😊，Oh。你啲。

But this one indeed does better than this。Hopefully well get to the point where we can see some of the ideas out here I'll try to do that if that happens then I might ask you for help in describingibing it again because we don't haves notes for this but first have to understand it well enough to actually explain it。

😊，Oh yeah， forget the big O。That。O。😊，U。Good。Bippartite groupss。But not bipartite graphs。😊。

The situation is a little different。Conict is wrong。 We' have already seen an example。 In fact。

 here is a simpler example。Oh。The maximum matching is the size1。

 the minimum vertex covered is the size 2。😊，啊。没事。M with three。Deals 2 is strictly bigger than max。

Matching， which is one。Yeah。Also。So， Burge's condition is still true if you can find an augmenting part you are golden。

 you you can improve the size of your matching， but how do you find an augmenting parts？😊。

And the problem is that once you start doing this， there are edges that can be going like this you run into trouble。

😊，So， let me tell you the main ideas behind both these things， how do you get around this？

And we love。We will see how much we can do。Yeah。It's explained in your notes， but。

Let me see how much I can explain。Inlect。See。Oh。So firstly， I need to give you a replacement。4。

For cuterum， actually for yeah cuter。Because， you know。

 really the problem is if I gave you a max matching。😊，Even if I had found a max matching。

 I need to be able to prove to you that this is a max matching。I need a compact certificate。

Now how do you show how do I convince you that this is the max matching？嗯。对。

So the corresponding theorem。Forcanic theorem is theorem 3， and this is known as the。That。Barge。包面的。

嗯。Maybe I should mention one word about Will Tut。 and we hear a lot about the Second World War and how。

People at this place called Bchley Park in Britain were developing computation。You know。

 they were developing a lot of the fundamentals of computation in order to break codes。

And we heard the name of Turing for sure because he used computers for the first time。

To actually search through a large number of permuts to find solutions to these ciphers fast。😊。

What we don't hear of is the name of Bill Tat。嗯。Who also， who， you know。

 there was the Enigma machine and the Lorenz machine。 And he broke the Lorenz machine。

 which is supposedly。Even more instrumental in ending the war， or whatever。

It's all difficult to say these things， but the part of the reason why we don't know of his name is because for the longest time he didn't say anything because they were swn to secrecy。

😊，And they were like， dude， you' are not allowed to say anything， So they said， okay sure。😊。

SoFor 30 years after the war， heard nobody say the thing and then finally some facts come out and he you know after the war。

 he came back， he was a graph terroristist。😊，And he is you know commonlyly proving theorem。

 he is proving a theorem like the one that I am going to show today。

 so actually I am not going to prove it， I'm just going to show you what this formula looks like。😊。

And it's another one of these maximum formulas。So here is problem。

So I wanted to show that the maximum matching， or this is for non bipart。

I want to show you the maximum matching。Es。The minimum of some object。

So let's look at what this object。You know， if I write it down， you'll be like， whoa， what happened？

So， let let me try to show you an object which is clearly going to upper bound the size of a matching。

😊，And then I'll claim， without proof that。The minimum of that object is equal to。M likematic。

Look at the graph。Look at a subset of vertices U。Use the subset of what see equal。

Suppose I delete you from the the graph falls into pieces。Yeah。These are all disconnected pieces。

That is there are no edges between them。 Of course， there are edges going like this。反了。哦。

Let's look at where a matching might lie。I'm looking at a max。Where would this matching lie？

How many of the matching edges can be incident to you？Sa a few。And let's call these components C1。

 C2， C3， C4。How many。Matching edges， So Ive counted basically all the matching edges amongst the edges within here and crossing。

Where else can matching edge lie inside C1， inside C2 inside C 3， inside C4。😊，Yeah。The size of。

The matching edges inside C is summation is C over 2。And it's an integer， so。Okay对。

And this is equal to。The size of you。Plus actually， let me just write it as C divided by 2。😊。

Minus the number of odd。Comorents。嗯。Gマイ u。Okay。네 말 막 있죠。You， I should be。对。This could be。3。5。

 but really it should be3， so I should subtract of half。For every odd component。对，就说你送了。那个这是问。

USo C1 and C2 are defined as if I delete you。😊，These are the connected components。

 so there is no edge between C1 and C。😊，Yes， this is the definition of these components。

That are coming out of deleting you。So there could be edges in here。

They could be all kinds of play edge in there。But once I deleted you。

 we are the connected components。😊，And I'm saying how many edges can be inside here， so many。😊。

And how many edges can be up there。I most so many。In the matching。嗯。I'm just rewriting。

 I'm just doing algebra now。 you've got the main idea。Okay， this is just this。

 what is the summation C over 2？😊，And minus the size of you。So this is。

The size of u plus n minus the size of u divided by2。

Minus the number of all components of G minus u divided by2。Which is。

N plus the size of u minus the number of all components of g minus U。一般的。OhThis is a man over。

 And this is true for every subset of the vertex。Yeah。

So what I've shown you so far is that I've shown you。That are matching。Can never be smaller。

 It can never be larger than that。What the claim is， what the theorem is。Is that this is strong。

So in order to prove something in a max matching。What I can do is I can give you a matching。

And then I can give you an object like this so actually lets see you know I don't know how much we can prove anything about anything so far but lets see if we can show that the max matching for size 2 is equal to the main of this object。

😊，On this side。Can we show that the men of that beast。Its good。What。好的。都嗯。

So I selected you to be two adjacent nodes。Yeah。So that's。So，5。And its five。Plus，2。Minus。

And now I have one odd component。1， divided by2。It three。Oh。Yeah。You to be。Nothing， excellent。

 So if u is nothing use the empty set， then I do 5 minus the number of odd components of g minus u thats。

😊，佢。Yeah。So。If you came up with an algorithm to find a max matching in a nonbipartitegraph。

 what you would do is you would find the matching and you would give you give me a corresponding set U and I could just go I could look at how many vertices are there in you。

😊，I could look at how many components are odd when I delete you。😊。

And compute this formula very quickly。And that's what the algorithms do。That's how they show up。

But how do they find the。那。How do they proceed and for that。

 I you know I need more time than I have so I can give you a picture instead of。😊，Oh。

I have six minutes I'm not going to try to do the algorithm in six minutes。😊。

Im going to instead give you the main ideas of to start off and then next time we will talk more。

So the question is， can we find a？诶。Augmenting parts。Yeah。And the problem is that we run into。

Ard cycles。So for some time people tried， they were not succeeding。This was back in the， I think，60s。

And then Jack Edmonds came up， remember Jack Edmonds。

 he was the guy who proved that arboreescence theorems。😊，He said， oh， you know。

 we did in lecture two or something like this way。So the idea is going to be very simple。

So here's going to show。So you know， here is the ideal here。Given。And。Find。嗯。An am augmenting parts。

On。四。None exists。And。Gamme。You， which is a certificate like this。This would be the ideal situation。😊。

Instead。What Edmund said is no， no， no， you know， I can't do this， but here's what I' will do。

Given M， I going to find an ML pot。嗯。O。Or say that none exists you know。

 whatever I'm either going to find an a augmented bar or I'm going to find this weird beast。

 It's actually a very pretty beast。😊，Go blossom。Or say that none， what is none no。am augmenting part。

Ex this。那我怎不。こんでよなります。The blossom is， as the name suggests。😊，It's got a stem。Yeah。

Followed by a flower。Actually， this is called a flower and this object is called a blossom。

 but we all get confused。😊，We call these things and。This is a is technically a flower。

 but lets call it a b。😊，This is not an eye augmenting part。 There' is only one open vertex。😊，嗯。

Somehow， you know， its almost like when you try to do the obvious thing。

 you try to find these augmenting parts， you you'll start you know， hitting yourself。😊。

Just because they aren't fighting。And you get these weird beasts。With beautiful objects。我 do you点。

这些是我提供的。So， first of all。What you can do is can you can toggle the stem。行。

What do I mean by toddle the stem， just make this in the matching out in out。嗯。So。

 what I mean is I did this， this。です。です。嗯。Now， this verortex is no longer open。But this vertex is now。

嗯。So， let me just。Draw。Thank。So now this vertex has is open。It's just a blossom。嗯。Remember。

 it's an odd length cycle like this。With one open building。晚上好。So I'll call this blossom B。

And here's what I'll do。I have a graph with a blossom in it。😊，I take this blossom。 by the way。

Look at the edges that are hitting the blossom。😊，This vertex is open right， just by definition。

 I mean， just by construction， we just to the stamp。😊，This vortex is open。

 So all the edges coming into it must be open， It must be unmatched。How about be guys， all bee edges。

 can they be matched？😊，No， because each of these vertices are matched。😊，Within the blossom。

So we are all un my status。You think。somehow号。Edmds had one brilliant idea。 I mean。

 he had many brilliant idea， but he could use this one brilliant idea two times。 You know。

 it's called a technique after that。😊，So you take this vertex and you shrink it down。

And this is the vertex v sub B。😊，Okay。And here's the kid。G has and。Andm augmenting parts。淀粉农烈。

G contract B， which is exactly what I did。Has an M contract B。我跟你点讲。Basically。

 you' will find an augmenting path out there。And you'll pull it back up。

In exactly the same way as we did earlier， you know。

 this augmenting path maybe will do something like， oh。

 this augmenting path must start from here and then it finds something like this。

 and then it goes like this。😊，So then you say， oh， this edge corresponded to this guy。SoMaybe this。

This was this tu tuk tu。But this is not open up here。 What are you going to do。

The only open vertex is here， right？Okay。Exactly。So what you do is you actually start from here and you see。

 you know， either this is going to be an augmenting path or that is going to be。😊，And in fact。你这是是。

Just that。So really the thing is you know， when you know you have two options you want to make progress or you want to prove that this is optimal well actually there is the third option lets shrink the graph。

😊，And make progress next。And that's what he did。Maybe this is a good time to stop Edmund's algorithm is apply this thing if you find a blossom。

 shrink it down， keep going。😊，The graph is smaller。

 you can't do this too many times eventually you will find an augmental path your done。

So the one piece that I havent told you is how do you implement this， how do you do this in polych？😊。

And。跟这个。Its you could try to do something like that。

 but maybe for now I'm not going to tell you anything more。 All I'll say is it it's an algorithm。

 which is very similar。😊，To this algorithm。But it just requires more work。

So I don't know whether I'll do it in the next lecture。

 maybe well move on to another way of looking at matchings。

 maybe we'll do it we'll decide later on but if not it's there in your lecture notes you can have a look see and feel free to ask questions but anyways。

😊，Maching is done two ways， well， matching is done essentially one way finding augmenting parts。😊。

Next time we'll do matching done another way。What would you like to say？

How many of you want to see some linear algebra？You can do linear programming。

You can do linear algebra。You can do。Matrix reason is let's go with these two options and then we'll decide later on whether we want to do more。

😊，Okay， so maybe on Friday， we' will do some linear algebra。

We haven't done linear algebra in the course so far， it's high language。

