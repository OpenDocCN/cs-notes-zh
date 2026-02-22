# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p30 Lecture_30_HDXs.zh_en -BV1a4cCeMEzb_p30-

So welcome back and indeed， you know after one false alarm。

 the final lecture of 850 for this semester。😊，嗯。For the year， even。嗯。

So today we'll just end up with what we promised high dimensional expanders， I'll give definitions。

 examples， I'm going to keep it light because you know。😊，The stuff is fairly technical。

 a lot of the proofs tend to be technical and i'm not going to give you the details i'm going to give you the intuition at least the part of the intuition that I have and then we'll take it from there。

😊，So I'm going to basically define what's high dimensional about them， what's expanding about them。

 and then I'll give you a proof sketch of what meteoid mixing。

The I'll remind you of the problem and then we'll prove stuff about it。So what's。

Let's just remind ourselves， we saw this last time。Expand a grass。So。嗯。Again， expand the graphs。

We could。Define， okay， so so G is unweighted。Undirected。Dregular， let's say。For simplicity。

And then we were saying， oh， let us look at the eigenvalues。

Of this the adjacency matrix and the top eigenvalue is going to be D and the second one there was going to be a gap。

If the graph is connected， G is connected。And then lambda 3 could be equal to lambda 2。

 and then we said lambda n。And maybe this was strictly bigger than D if G if not bipartite。诶。

And what we were interested in was we were interested in the spectral gap。

 the gap between Lada 1 and Lada 2。And in fact， what I'm going to look at is I'm going to look at。

What I'll call the。Spectral radius。So this is a definition， the spectral radius is the max of lambda。

杜。And lambda n， the absolute value of that。And we know that if the graph is connected and not bipartidite。

 then this is less than lambda 1。So let's actually divide by lambda 1 out here。And we say this is。

Okay， this is the spectral radius。Um。Different in different context。

 people might define it differently what I'm interested in that I'm interested in this quantity and I'm asking the question。

 is this at most epsilon？😊，嗯。So epsilon is smaller。The graph is more and more of an expander。

 so if if I'm saying basically these two quantities are very far away from this quantity which is D then the graph of an expander this gap is huge。

This is tiny and this is D， then the gap is huge and that's what I want to capture and but I want to capture it relative to D。

😊，In this case。So。Let's just say。And N the。Epsilon。Gra off。Is N vertex。The regular。Epsilon， specius。

没。Such graphs exist for you know it really depends on what values of epsilon you want。

But these are the kind of graphs that will be really interesting we want good expanded graphs and this is the kind of properties we want。

这。Now， in some cases， we'll try to relax things， we might not want regularity。Such is life。

 we might want weightedness， such is life， but all these things can be extended。And maybe I。

 you know， it'll depend on how much， you know， how much time we want to spend， but well。We'll see。

 but most of these definitions extend to situations where at least unweightedness can be relaxed。

 the regularity can definitely be relaxed undirectedness gets more complicated。😊。

The theory of directed expanders and much， much murkier。Okay。And then we saw two examples。

 we saw a little bit。😊，One thing we saw was suppose you know the random walk， so we did random walks。

On an Nd epsilon graph。You know is this is just a walk where there is the graph and you have a verortex and it has。

 let's say five neighbors。😊，You are sitting at this vertex。

 you choose one of the neighbors uniformly at random， you go there， this itself has five neighbors。

 you choose one of its neighbors uniformly at random and go there， you might end up coming back。

 it doesn't matter。This is the random walk， so this is the natural random walk and an end epsilon graph。

😊，We notice that the uniform distribution。呃The the。If PT is the sort of probability distribution。

After。These steps。Then we showed if PT is this， then we showed that PT tends to the uniform distribution。

As。He tends to infinity。And also， so this is one fact that we showed and another fact that we showed was that the total variation distance。

Between PT， remember， this is half the L1 distance between PT and the uniform distribution。

Is less than equal to deelta。After something like order， log off。N over Delta。Over epsilon steps。

So if the graph。Has n veres and after about log n over epsilon steps， we are close to being uniform。

In this sense。Okay， good。Today， we are going to use。

Exactly this property on an exponentially large graph。😊，To show that random walk on trees mixes。

On spanning trees mixes， but you know a random walk on general meteorroids will mix and that's where we'll use this technology。

Yeah。对。嗯。We saw another example about using this for chs。

 it was a little hurried and some of you got a little confused we will come back to this as we need。

😊，Because so so I'll tell you what what I wanted to do， I wanted to give you two examples out here。

 so one was random walks on regular graphs and we know that it mixes fast。

And then we would do random walks analyzed again on regular graphs。

 but analyzed using high dimensional expanders and you would get more power out of that。😊。

Then the second thing was that expanders are also used for coding。

 which we kind of sketch last time if you remember that。And again， using high dimensional expanders。

 you can get even better codes。😡，This was a best paper at one of these Fox talks。

The other coding paper was best paper at stock 22 last year。

So these are ideas that use this technology。😊，So it's very。

 very recent technology and hopefully it' will be useful to you。

 so that's the main goal of telling you guys about high dimension expanders。😊。

And also partly to learn about highmenal expand is because I don't know myself。

 lot about the stuff I'm learning。😊，Good， okay。So this， this is。Check。

So what's a high dimension so this these are expanded， these are just just regular budol graphs。😊。

I didn't get it right。系。So now we're going to go to。😊，A high dimensional expander， which is just。

 okay。As we said last time， it's just a sial complex。It's just a downward flow set system。

 so think of。嗯。sett U of elements。And a collection F of sets。So these are elements。呃， sets。So， one。

And I'll call this this pair X。And now the first thing I require is F is downwards closed。

It just means if S belongs to F。And T is subset of s when t also belongs to F。Nowward closed。Okay。😊。

And that's it， this is the only assumption I'm asking for。😊，And this object。

 this downward closed often is also called a sial。Complex。SC for shark。诶。嗯。

Each of these sets are called slicies， they are also know sets。😊，Al call。

Simply see also called spaces。Maximal sets。Are called facets。哎。对。

And often because it's a down load set system， actually it's you know nice set system。

 you can draw it。😊，As sort of a containment diagram as a has diagram。嗯m。

And I'm dropping the this is the set consisting of two elements A and B。😡，I'm dropping the braces。

 I'm dropping the commas。变。This is just a graph。It's a draft consisting of。You knowA呃B。Let's see。

Its just a。It's also a s complex。😊，Because if you have edges， you have the ver see then。

And we have the empty set。So this is the s complex I'll call x。😊，X has。Elements。

 it has sets of size two and so on and so forth。The dimension of a set is the size minus1。

A line is a one dimensional object， and edge is a one dimensional object。Dimension one。

 dimension  zero， dimension minus1， this is just for。😊，P for beauty。And。

But you can have objects like this。😊，Which are you now you have hypers。And they are downward closed。

 you can check ABD， so AB is there， BD is there， A is there and so on and so forth。Fair enough。

Simplicial complex。Good。嗯。Good， and then a sial complex would be called pure。😊，Means all the facets。

Have。Sam。Dimmenion。All maximal sets， so for instance， if I had a set out here， you know。

 if I had an element f out here。Which was not involved in any sets of size two or three。

This would not be a pure simial complex。嗯。And as somebody pointed out last time。Maroids。Ourre pure。

Simimplicial complexes。Plus， they have a nice exchange property。Okay。😊。

Good so in fact meteroids are your canonical example of sial complexes and a lot of people study this you know the fact that you're calling it slicial complexes already suggest so maybe there are people who are there in sort of combinator topology and stuff like that who are interested in this and indeed that is the case。

😊，And in fact， people have been studying this people have been studying matteoids for some time。

 not just from combinatorial optimization as we have， but from the sort of combinatorial topology。

呃 great。嗯。In fact， yeah。呃。So there's。Good， so that's that's some definition。 So youve。

 you've seen a bunch of definitions already。 you've seen the definition of pure。

 you've seen the definition of the simple whatever an essay。 So let me give you。

couple more definitions。Okay， maybe I'll need this thing。嗯。What else do I need to tell you？哦， ok。

So given an object like this。嗯。By the way， if I have an object like this， I can， you know。

 essentially I can imagine that there are four verticCs ABCD。😊。

And then there are five edges between them， indeed the only edge that's not present。Is。CD， right。In的。

Fair enough。And then， there are two。So these are all edges。And then they are do。Triangles out here。

 So is this。The top triangle。In fact， I should have drawn it differently， right I should have。

Drawn D and C and A B like this。对。And now I have two。Triangles two slicies out here， two facets。

Fair enough good。What's the one skeleton？It's what you think exactly what it is。

 ignore all the objects of dimension2 and higher。😡，Just take all the objects of dimensions 0 and 1。

These are these are verticC， these are edges。😊，This is just the one skeleton。Okay。So again， again。

 we'll talk about one skeleton of a sial conflict。It's just the graph associated with this。

 so ignore the fact that I've shaded in all these portions， it's just the graph。😊。

So one skeleton is a graphe。😊，Consisting of x0 and x1。Good。And then。The one other。

Objects that people talk about。Is the idea of a link。Terrible name。

 but let's stick with this because everybody does。So suppose alpha belongs to。The collection of sets。

Okay。Now， define。ASial complex。F subSo so you can define okay， you can define x alpha。

To be the set of all betas such that beta intersect alpha is the empty set。

But beta union alpha belongs to it。Okay。So look at alpha， alpha， let's say。

 is this this guy out here。诶。Now， look at all the sets。😊，All the， you know， objects which are。So now。

呃。Basically， I want to say。嗯。The empty set belongs to this link because the empty set union alpha。

 so just imagine that alpha is equal to the set a。Alpha and beta will always be sets。😡。

So look at alpha， which is the set a。😊，So if you add the empty sec to alpha。

 it it is in this thing if you add B， if you add a。😊，If you add D。

All these will give you sets out here。And if you add BC out here， no， not A。

If you add BC and if you add DD out here。呃， speeddy。These things， when you add a to them。😡。

You will get saids okay。So it's just the upset， you know， whatever。The up simial complex。O。喂。

This is called the link of。对意思应对。I's another way to please。这个。All those questions containing A。

And you just take like a matching of removing a the removing a from each of them。

Absolutely and it like matching exactly so so the way I always think about it is exactly like this I take a and I look at everything that contains a all lights up and then a kind of removes from gets removed from all of those guys absolutely。

😊，You contract exactly and in fact， contraction is the right analogy to think of。😊。

Because if you think of this as being a matteroid。Then this is exactly the notion of contraction in a matrix。

 right？If you took a graph。😊，And if I took an element of the graph。Well， you know it's a meroid。

 if this were a metteroid， then each of these would be edges of a graph。

So I would take an edge of the graph and I would contract it。😊。

And that would be the object that I'm looking at。But I'm looking at all， yeah。

All independent sets you these would be independent sets of metroid I'd be looking at independent sets that contain a and abi。

😊，诶其时我会。Yes。そうなですぜ。Coner thehuh。Those。我我冇 time。Perfect。hu。😊，Perfect。

 very nice so for instance out here what is the link of a。😊。

The link of a is going to be exactly the graph consisting of the edge of BD and BCc。

So this is the neighborhood of A。So you're looking at just the neighborhood of a and now you're removing all the edges from a to the neighborhood。

 so you're just getting this edge so for instance， the link of C in this case。

Just consists of two verticess A and B。And the edge between them。

So the link of C this consists of A and D and just the edge between。ok。😊，So for every state out here。

 you can talk about the link。对。喂喂。嗯哈。😊，啊哈。😊，可这合式。This feels a lot like。啊吓。😊，没。Okay。安可度。Okay。

I learn something new every day。 I don't know。I'm happy to find out more。It's entirely possible。

Its in possible。So， yeah。Any other sort analogy that people see， I'm happy to。O。If not。

 let's go ahead。So this is the link， so for any alpha。😊，And often， you know， I won't say alpha and f。

 I'll say alpha and x， this is x alpha， you know， I'm mixing types a little bit。😊。

X used to be a pair， but suddenly now you know x is a collection of sets。

 maybe I can call this F alpha and but you know it's easier to just。😊，Let's say X phi is equal。O。😊。

So I have defined a link。And now once I have a link， I can also talk about the skeleton of links。😊。

It's just a bunch of graphs。That I'm getting。And once I have graphs， I can talk about expansion。

So now I can finally define that。And epsilon HBx， okay， no and HBx。嗯。

Yes so so this is this is forget HDX， a sial complex X。😊，Has。Epsilon。Spectral。Expansion。If。

For all alpha。Which belong to。X系。And k， okay， I I I yeah。A that most d minus2。

So notice that if I take an element out here and I look at its link there there I don't have two levels above it。

 so I can't talk about vertics and edges of the link。😊。

So I'm going to talk about veres and edges of the skeleton of only these links。😊，So you know。

 always D will be the D is the dimension。Of the assets。It's the size of the largest set minus1。😡。

Remember， edges have linked dimension 1。These have dimension too。These are triangles， faces。哎。

So an sial complex has epsilon spectral expansion if for all alpha which lie in this point downwards。

😊，No。Skeleton。Offf X alpha。Has。Spectral radius。At more steps。

You are getting a bunch of graphs out here。😡，You know。

 it's like the neighborhood of this vertex should be an expander。

Neighborhood of this verortex should be an expander， so on and so forth。哎。And then you might。

 you know， if this had many levels， you might take sets of size two sets of size three and so on and so forth。

 take their links。😊，We want all of these guys to be expanders。

There is an expansion an expander gone crazy。So。This is a high dimensional expander。So this is。

Is a sort of crazy beast so one the first time I saw it， how do you argue about this thing right。

 how do you even get started。😊，So thankfully， there are some theorems which will help us argue about these。

😊，And that's going to be the basically I'm going to tell you the theorems and then we'll see why those theorems are useful。

😊，I'm having trouble with tu on this because I think of expanders。A grab witch。

Rotes of small debris and are connected to。You know， its neighborhoods were spread out， exactly。

And a small number of cures in the neighborhood。呃呃呃。A lot of edge is going out of。

 so I always think of it。They have a particular ver。呃。Right。Okay。Okay， so。I could expand as possible。

Thank。Absolutely。Absolutely。Okay。Oh I see fair enough I see what you mean。 it seems like。

That was my absolutely so good， so this is this this brings us to sort of to the question of if I took a verortex and if I have。

 you know， if I have a small degree。😊，Then chances are it would be disconnected if you know it wouldn't have any edges in that。

 and in particular if I were to take a random graph，😊，Definitely， you know。

 a random constant degree graph or a random log degree graph or something like this。😊。

I have only lo many edges。And theres there very few edges going between these guys。

 so almost you know all these will be isolated vertices so in fact， random constructions。😊。

Do not work for these objects。The only constructions we know as far as I know。

For high dimensional expanders are algebraic constructions。As in theres a you what does that mean？

Kelly graphs of， you know， they come from so called k complexes。

let me tell you about one way of getting a graph。You start with a group， nowge the group。别人过嚟。

Js broke。Okay。And ge， let's say， has n elements。Here's the way in which you can construct a graph。

You have n verticcs， one for each element of the group G1， G2， G3， and so on and so forth。

You take a set of generators。Ex。Subet of G。How's this graph？And I connect G1 to H G， you know H1， G。

 you know G3， H2， G3， H3， G3 and so on so forth， so for every h in h。You take an element of G。

And you start now connecting this group element to all its neighbors， according to this thing。

This is one way in which if you choose GNH carefully， you can get expanded graphs。Okay。

Now you can also define and this is the way in which one of these papers uses。😊。

You can can define objects like。Okay， I'm going to have h and h prime。Be two sets of generators。

Now from G。I can， I can get， you know， HG。You can get GH prime， these are two elements。

And now you can go to Hg，H prime。And this will define a phase。Now， of course。

 this is a square and not a simplex。😊，But you know。

 it starts to give you ideas of how you can start generating these sort of crazy objects。It根据到 that。

我 okay。Okay，Okay。啊哈。😊，So in that case， you should not choose that group。But like。So， it。Probably。

 I don't know， but indely if you choose your hs carefully。😊。

Then those graphs give you those graphs have interesting expansion properties。Definitely。

 so there are crappy ways of constructing kgraphs which won't give you expansion。😊。

So you would have to do something smart about it。那我不确认。Yeah。Good， what else？Anyth else。So indeed。

 I agree with you that。😊，A standard notion that an expander， a random graph is an expander。

 definitely does not carry over to this this setting。Good， okay。嗯。

Now so one more thing that you could do is that it need not always be the case。

 so in expanders we usually look for graphs with low degree。😊。

Here we might be interested in even in graph with high degree。

As long as it has some nice properties so for instance like there is a boring high dimensional expander you can get which is the the full sial complex you basically take every side of size one。

 every side of size two， every side of size3。😊，And it's not surprising that that is a high dimension expansion。

😊，There's no way it cannot be here and expandedly。Okay。Good。So now。Given this。好对。

Let me let me mention a couple of things。It's actually。wantedanted to do one more。It's。

There's one change I'll need to do。As， kind of。Expecting one of you guys would have caught it because you。

So there is this weirdness。I just defined。I asked for the skeleton to have spectral radius at most eil。

But the skeleton is a bipartite graph。So I can't hope for such a。Roperty。

And maybe what I'm going to ask for just as the spectral has has。嗯。

I'm not going to look at the Lambda n。But this guy。

I'm just going to look at the gap between Lambda 1 and Lada。But the thing this is often called。One。

 excited。Back。I'm just asking for there to be a gap between the first and second angle。

It's a bipartite graph， so you here we know。It's slide part。So this。对。O。😊。

So there's there's two facts that might be useful for if you want to deal with this。

 at least as far as I can see there here are two things that are。Useful。诶。Did I want to say okay。

Sorry you guys。There is one additional， okay， so I'm going to extend this ever so slightly。

AndBut this this extension is almost sort of trivial。I'm going to take my high dimensional expander。

A B， A C， in fact， I'm taking the most boring one， I'm taking a graph。

And I'm going to define a probability distribution over the。Bas of dis thing。

Then want to define a probability distribution。And this probability distribution， let's say。

 is one half， one half， it's the most simple probability distribution。嗯。In some sense。

 the way I'm thinking of this right now is I'm thinking of this as the。

As what do I want to do if these were spanning trees。

 I want to find the uniform distribution on them， this is my goal distribution out there。え。

Given a set out here， this defines a probability distribution over children of it。

How do I get from from a setup here to a set down here， I drop a random element。

So this guy who had half masks can go to one of its two children。

So each will get a quarter from here。This guy who had half mask can go to either it two children and each will get a quarter out here。

 so the probability distribution on the next level is going to be one quarter， one half。😊，能挂着。Yeah。

The probability distribution on this guy is of course one。

You can also think of these links as from B。You can go to one of two places。

 I mean these are sort of bidirectal in some sense from B。

 you can go to one of two places B A and B C。From C， you can only go to one place， BCC。啊。

So if you look at what's the probability of getting to B fee。

 it's half of half because you chose one of its parents out here and one times a quarter。

 they sum up to a half。诶。So if I give you a probability distribution out here。

 which I'll denote by pi。This naturally induces the probability distribution over every level below it。

😊，This just says look at all its children uniformly go to one of them。😡，And then this guy says oh。

 how many parents do I have， each of them is giving me some mask。

I'll collect all that mass so this gives me a probability distribution and if I can say this is pi of1 because it's at level1。

 then this will be pi of0 and so on and so forth So if I give you a probability distribution at the top this induces a probability distribution at every level I'm not going to write down the actual you know expressions they're just annoying and if we are not doing the math you don't have to see those expression。

😊，But hopefully it's clear to you that。😊，You know， given a probability distribution。

 you just percollate it down。Yeah。So from now on， our SDX will be called U。F and p。

 or I'll just call them x。Thatby。There's a probability distribution on the top as go。对了。Okay。So， now。

The thing is。You know， how do you？Argue so。This object said。

 look for every link I want to have good expansion。😡，Good spectral gap。So， there's a。Pretty。

 you know powerful theorem of Oppenheim。Open， Oppenheims。Wickle down。Het him。

Says it's enough to show。That all the。So look at all alpha。At levels d minus2。At the highest level。

Such that there's sort of two levels above that。Okay。😊，Suppose for all alpha。X， alpha。As。嗯。Epsilon。

One sided moretga。Specttorly gap。Just the top。😡，Guys have the spectral gap。And。

The graph at the bottom。Which is， you know， x0。Next1， this is the this is the skeleton of the bottom。

Is connected。As a graph。Yeah。Actually。Not just this。And。Every。One skeleton。Exhibitator。Is connected。

For all beta belonging to， you know， X K for all K at most D minus-2。Every skeleton is connected。😊。

Every neighborhood is connected。But the expansion property you are assuming is only on the top level。

Then。You can argue。That。That。X is。And。懒得多。off。没。I think I might have painted myself into a corner。😔。

I'll write down what I want to be true， but I might need to sort of change the definition every so slightly。

 I want to say then this property is true。Then the SC。X。As Epsilon。

What did I call spectral expansion one sign。So。Model。I'm saying there is some。

High dimensional expander out here。For every link which is sitting just at the top。😡，If these guys。

Have good expansion。Then I want to claim this guy has good expansion。

 but since I'm arguing about this also this guy has good expansion。

 this guy has everybody has good expansion。😊，So I want to say just arguing about the top level。😡。

Should give us。Information about every other level， this is not true。

 so this is epsilon over one minus。Da epsilon。Expansion。

So if I assume some kind of spectral gap for the top level。

Then I get some kind of spectral gap for the bottom level。And in fact。

 I can get some kind of spectral gap for each of these levels。诶。Seemed like a。

Sort of at least a useful statement， I don't have to argue about every single person out here。😊。

I only need to argue about the people at the top。Why is this useful。

Does this statement even make kind of sense？People seem worried。People seem tired。Anyways。Please需。嗯哼。

That's just every every so so it's the link of every， you know， you take a beta out here。

 you look at the， you know， you look at its link， its link is some neighborhood。😊。

That has some vertics and some edges that should be connected。So every link， so this is a link。

You are looking at this link。There's some words even can edge and that's connected。

So this is one more time， I'll say exactly the same thing again if you can argue something about the spectral gap of the people at the top。

😊，And everybody has links which are connected as graphs。Then you argue something， you know。

 this allows us to trickle down this gap。To gaps for everybody。Yeah。This is kind of。Okay， you say。

 well， you know， I didn't know anything earlier。About the whole whole structure。

Now I just need to know something about the top people and then everything else will be done。Yeah。

Is this good， is this bad， we don't know？😊，So let me give you one example。In fact。

 it's the only example in。Suppose this was a matteroid， suppose this was a spanning tree meteroid。

Spanning tree。Spning treemate， right？What's the dimension of the spanning treemate， right？

How many edges would you have in a spanning tree and minus1？诶。

So the largest elements in this metroid are of site n minus1。If you want links to be interesting。

You would go down to level d minus 2， which is n minus 3。Okay。😊。

I need to argue something about a link of an object。Of dimension n minus3。What is that？

It's a forest with n minus3 edges。Okay。😊，The forest within minus three edges and I'm looking at its link so it's a forest you know there is some edges。

 theres some edges， how many connected components can this forest have？😊，N minus three edges， forest。

 how many connected components？There's three connected components。You are looking at its link。😡。

What are links links are consist of elements that can be added to these three connected components。

To still maintain independence。So your options are you can add edges like this。

You can add as like this。And you can have it just links。哎。So these are the verortices。

 each of these you know edges， colored edges are verortices in this link。😊。

What are edges in this link？Two guys of different colors。You can't add two people of the same color。

 it's not valid。喂。So what's the adjacency？Matrix of testing。Well。other。

It's a graph with all these colored edges。As。Elements。So these are the vertices of this graph。😊。

The skeleton that I'm building。I can create。An edge again。

 always when you're dealing with these things。Es edges are elements of the matrix right？

And you are allowed to have two element collections， which are two different guys。喂。So now。

can actually start to argue about what's the structure of this thing？B you know。What's this this。

 what's this graph structure？So this graph structure。This edge。Cannot be a neighbor of this age。

 right？So if I put all the blue edges at the beginning and all the pink edges in the green edges out there。

😊，I'll have once everywhere。But there was here。This is what my graph looks like。不好。Now I can ask。

 you know？Is this graph does it give me an expander？我 say。😊，唔该系。Does this kind of make sense？你哋。

You know， ask a question somebody asked anybody else。

That doesn't matter all this is arguing about is this is arguing about spectral gaps。😊。

And because we had nothing to do with，So you have to ask whether this is an expander or not what is the second eigenvalue？

😊，Yeah， when I first saw this thing， I had no idea， you know。

 what would the second eigenvalue of this matrix be right？Say that again。那。😡。

It's the adjacency matrix， you know basically。😊，What am I doing？Green edge1， green edge 2。

 blue edge1， blue edge2， pink edge one， pink edge2。Whatever B1， B2， p1， p2。

And I'm looking at the adjacency matrix。😊，The adjacency matrix is capturing which pairs can be in the same set。

 right， which pairs can be in independent sets。These guys cannot be。But these guys can be。

And with the same thing I would say， and I mean， you see what I'm doing。This is just。

The all once matrix minus。A block matrix one。Minus a block matrix 2 minus a block matrix 3。Yeah。Good。

This is the rank 1 matrix。😊，All these are rank one matrices。Okay， by the way。This matrix。

 I mean all these four are actually positive semi definite matrices these are just rank one you know xx transpose right？

😊，So let's look at。What's that。😊，The eigenvalues between plus and minus4 I don't know。

 but here is something I can definitely say。嗯。How many positive eigenvalues can it have？

My claim is we can have at most one positive wagonvalue。Why。😮，Let's look at its saigenvalue。

So its eigenvalue correspond to， you know， I should look at。When can this be positive？嗯。我的。对。Good。

So this is just x transpose Jx。Minus。X transpose B1 x right， which is a positive quantity。

 this is a positive semideite matrix。Right。So all these three are non negative minus something non negative。

And I want this quantity。To be greater than equal to0， right？Okay， so。Good， let me。

 let me step back for a second。I want to claim。This matrix has at most one non negative eigenvalue。

My claim。Is that。です。As at most one。No negative， I can。诶。So let's try to prove it， right？房间。With that。

😊，At most one non negative eigenvalue。AndThis is where。这个。Tell me why。包有。Do that again。啊哈。😊，好对。啊哈。😊。

Sure。我。Thanks。Absolutely。对。对唔该。So you're saying let us look at what x transpose J minus b1 minus b2 minus B3。

X。What is this value？So what is this value？So what is this value， it's really x transpose J x minus。

暂天。Non negative， right？Because x transpose B1， so this is a positive quantity。啊。Right。跟他都不认说。

What's that？Good， so basically I'm what Mabu was also saying， so look at x transpose Jx。

 maybe I should give myself more room。啊。After all these days of saying， oh。

 I don't want to do algebra on the board here I am doing algebraron。啊。What is x transpo Jx？

It's actually x transpose1， one transpose x。So this is actually equal to。The one norm of x squared。

Just surehhuh。Okay， so summation Xi。Squa， that's correct。Minus， and now this is x transpose B1x。

So this is something like this is a sum。So this should be some over。I is belonging to some S1。Of X。

Square。Because B1 itself is like11 transpose。For some sec。The same thing for S2。

Xs squared minus the sum。我ect晒。It's3 squared。There is。And S1， S2 S3 are this。I'm a partition。

 in fact。And I want to ask the question， well， how many suggestses？By the way， what is the rank of。

This beast at most。Most four， right。Good。嗯。Now I want to say。O。不管你们呢。对这子。Good。Good。But。

Okay so actually you know， trying to do this online， let's take a tuent break。

 maybe we'll do a cookie break and then we'll come back and we'll finish this proof and that's pretty much all the proofs that we'll have time for today。

😊，Well， it's。So the just group the。Under is a one side in fact。

 I want to show that it's a zero one sided expander so if it had at most one non negative eigenvalue then epsilon equals you know then we would have a0 one side in。

Ex。Epsilon equal0。And then this would give us that the whole thing。Has an excellent spectral gap。

Yeah for this particular in this picture。We're actually like at the bottom part of this right we aren't up the point it take again good so in fact I was thinking of being up here。

 this is why we had three components right what I'm。Or spanning trees。Its。These our。Yes， absolutely。

We're looking at set the container most down minus one， but this this higher this。

The top of that is at order and square。可以。有的。So the top of this should really be at n minus1。

Because no， so。Oh， I see， I see what you're saying so you're imagining that this is。

So you're talking about here the actual entire set collection of sex and the high dimensional so so this we are only arguing about these guys yeah we are not interested in these people at all in fact we are not even interested in people down here which are not independent in some sense I'm only looking at the independent sets okay。

😊，啊。ok。Sorry， I didn't think through this。Yeah。Wing wish we actually want to show。诶。Dotly。😊。

Absolutely。This trickle down。Oh， absolutely。Good， so maybe instead of doing this， which you know。

 hopefully we'll be able to figure out。😊，Thank you。Okay， get me。LetLet's just finish this thing。

So what what are the eigenvectors of this？So maybe let's let's do this on the piaz just tell me how to do。

Me would。Come up。😡，Let's do it。对个。Let's make it interactive。对起。😊，就整多。hu。就可以。Sure。诶诶。点本见。不是。我s that。😊。

We sky。你不是来都。啊哈。😊，But then don't you need to also？Right。

 and don't then you'll need to start expanding along。There it well， right。系咯成系。I mean。

 I need I need to expand okay。诶两 would be好容易。This that is。第个咯。And multiplication。喂。Maybe。是等不对。对。不我再问。

没有。嗯。It's like you can do this。You can use the formula to give determine it。Right。

 so you need to pick one entry Oh， this is one。嗯第先时。Negative two negative two zero， zero， zero。没有问题。

You open Matla。Okay。So maybe let's do this offline man。

I was hoping that there would be a sort of a slick proof。😊，So。Okay。Okay， let's let's step back。

 where are we going？We have this object。We showed a theorem that said， well。

 if you can argue something about。The， the top。Linkths。

 you can argue something about the whole thing。And from this， you can infer that each of these links。

😊，Has spectral gap which is zero， you know， it has exactly one positive eigenvalue。

So it's actually a very good expander， at every layer。Why does that help？

So why that helps is I want to move this upstairs。Is maybe。One other， one final piece that remains。

So what do I want to do？What I really want to do is I have。This expander。

 maybe I'm going to draw it just like this。These are all the spanning trees out here。

I'm still going to draw it， you know， maybe let me draw it this way to avoid confusion。

These are all the spanning trees Okay， what I really want to do is I want to I want to look at。

The random walk， which takes the spanning tree， drops an edge。Add another edge。Comes back。

Ts you know goes from this span tree， drops a random edge， add the random edge。

And this is known as the。down。U。Walk。诶。And this is a down up walk on all the。Elements。At size D。

 where D is。panning trees。This is what I want to understand。I want to understand。

How good this downup market is。Okay。😊，What is this downup work doing it actually。Walking on Xb。

And X d minus1。Each time it comes down to some guy out here and then goes back up there。

That's what's happening。The way they argue about this is they do the following。And again。

 it's going to be a cartoon because。I thought I'll finish early。

 but I'm probably going to be five minutes over。I'm working only on full dimensional objects。😡，嗯。

And I'll call。The random walk that I'm taking。To be the。Down up walk。At level D。

You go down and then you go up。You could define another walk where you went up and then down。

Where you're walking on D minus1。It is defined on the same bipartite graph。😊。

I'm either walking on the top tuk tuk or I'm walking on the bottom tuk tuk。😡，Okay。😊。

This is an up down walk。😡，At level D -1。I would like to show that this has good spectral gap。😡。

Then it mixes fast。What you show is or what this is a paper of Anari。リオベ。And。嗯。Well else。Cthiavinson。

Thank you。So the first thing they showed。Is that the spectrum of this thing？

Is the same as the spectrum of testing。Same spectrum。

It seemed too good to be true you know before I proved it。

 I actually took a little example and to show that。

 you know they have different numbers of eigenvalues。😊，But the non zero eigenvalues are the same。

So what I know is I want to understand this object。Instead， it suffices to understand this object。好。

啊哈我系啊。Then the next step is。You know， there is a down up walk associated with this level as well。

Okay。The eigenvalue is out here。Are almost the same。As the eigenvalues。Of the downup walk。Up to。度。

Puddge factors that will come in。Actually， in this case， only one fudge factor that will come in。啊。

You'll start losing a little bit out here。So you'll start losing some fu factor。

So what you're doing is you took the down up walk and you related to drop down walk。And now you say。

 well， actually， instead of going up down， I'm going to consider down up at the same level。D -1。

And I'll lose only a tiny little bit in the spectrum。哎。And so now you add to a down up walk out here。

 so you go to the up down walk at this level and then go to a down up walk out here。

And you keep going from level to level。And these fu factors。😊。

Depend on a the number of times you do this。But B， this depends on the number of iterations。😡。

But B also on the expansion at each level。So remember what we will saying expansion。

And each level the spectral gap。So if you had a poor spectral gap。

 you would start losing a lot at every level。In our case。

 the spectral gap or the gap was epsilon was0。So I didn't lose anything extra。

 I just lost in a number of iterations。And when this finishes， if you use this process。

 what they show is that the up down。Spectral the thing at level D。The Lada two of this thing。

Is at most 1 minus10 B。Where day is the number of levels。And therefore， the number of rounds。

The number of steps you need to converge。Is something like D。Because the gap is then1 over D。

 you'll need d times log of the number of spanning trees。Over burn。Distance。

The number of spanning trees itself is n to the D so you get。This is continuing out here。

 d squared log of the number of vertics of the graph。The particular expressions don't really。

 you know， are not the most important thing， the important things were。

You related the up down walk to the down up walk to the up down walk。And then secondly， you related。

 you know， the up down walk to the down up the other way。对。Maybe。Let me stop there。

 let me say a couple of words about this as far as you know。

My understanding of this thing so my understanding of this is that so far。

 at least previous approaches to try to show mixing of spanning trees。😊。

Was just looking at the expansion， just very local properties of the expansion。

And these arguments are doing very fine grain analysis of expansion where theyre trying to argue。😊。

Somehow， they are looking at。They're looking at things much more deeply。

 they're looking at sets and they're looking at how。Each locality。

 locality defined in terms of links are expanding。That' seeming to give them a lot of power。

Is it more power than previously we don't know？It would be great to have a purely combinatorial proof that doesn't use any of this machinery。

 I don't know if such a thing is possible。😊，UThe people who do this stuff， you know， of course。

 they're like， you know， we should use this machinery right know。

 this is a powerful machinery and we should use this。😊，And。

 but it would be nice to have a sort of selfcon proof that after essentially one lecture of waving my hands madly。

 it's still kind of， you know， it's perhaps just as mysterious as it was at the beginning。😊。

Maybe just a little less mysterious it's like， okay， we are throwing high powered math at it。😊，啊。

And yeah， I haven't given you almost any of the I mean， in fact。

 I haven't given you any of the proofs I thought I'd give you one one simple proof， but even that。😊。

嗯。We stop。嗯。对。All this is very specialized to meteoids。

If we can use this machinery to get mixing for other objects。That would be awesome。

But this technology seems very tailored towards mes。We don't know。

 for instance it would be nice to understand here's one of the sort of famous open problems that are still there understanding aic orientations you guys know what topological sorting is right given a directed draft laid out so that all ages are going forward。

嗯。Can you sample from all topological orderings of a directed basically graph？

They are known as basically orientations。Yeah。3号。Exactly。

 but I'm not asking you to sample exactly sampling approximately is good enough。😊，Prospect。

Absolutely。Absolutely。It doesn't form a metoid。Can we do something？对。嗯。Understanding matchings。

 you know bipartite matchings， we understand well， general matchings， you know。

 we have some techniques， but。Just understanding it， giving a clean proof would really be nice。

Other combinatorial structures， you know understanding colorings。

 so it's known that every graph with degree D admits a coloring width。Or D plus one colors。

 D plus one， right？Good。Suppose they give you。1。5 timesD many colors。It's a maximum degree d graph。😊。

You can color it very easily， you can color it using D plus once 1。5 times d is a lot of colors。

Can you sample from all these colorings？Physists are interesting in this。

 This is known as something called the。I forget， I think it's called the parts model。Some诶。嗯。

It's's a problem that people have been trying to understand。

 and we do know that some makes chains of this form。Recently。

 now progress again has been made using this high dimensional expander machinery。

How far can that be pushed？Kuku Liu last year came and gave a job talk。嗯。

He was talking about this kind of machinery but anyways。

 you know understanding this stuff would be better understanding this stuff better would be great and in fact if you understand it please come and explain it to me as well because I'm trying to read this stuff myself and it's been slow going so some of your intuitions are helping me because at least she' was like oh yeah that's a good way of thinking about it。

😊，That's part of my goal with presenting this stuff。

And thank you for sticking it out through the course and through some of these lectures where we went off the deep end。

😊，But you know it's more fun that way when I have company so anyways。

 there's one last thing to mention， which is that I know I had promised that there would be one more homework so there's not going I mean promised hasn gone I'd said there would be one more homework I'll put out an optional homework in case you want to do one more homework to make up you know a few points for some homework that you skipped or something like that you are welcome to。

😊，It'll be optional and you can get some extra points。We've been very。Llayaceical and grading。

 but will the fault is our， its not yours。😊，So we'll work on that。诶。And other than that， yeah。

Thank you for sticking it on and there's cookies aren't there。这样。I'll see you guys sometime。

