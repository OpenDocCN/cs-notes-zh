# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p16 -16-Lecture 16_ The Traveling Salesman Problem).zh_en -BV14CAUeUEPj_p16-

Okay。So today's lecture is all about the traveling salesman problem。

Or TSP as it's usually called So the TSP， it's a very famous problem。 And really for about 70 years。

 it' sort of served as like the main challenge problem motivating people to figure out different ways to cope with NP complete problems。

 So for example， George Danzig， who we talked about back when we were discussing linear programming。

 he spent a fair amount of time in the 50s thinking about how could you use linear programs to at least get some traction on integer programs。

 including the traveling salesman problem。 And so you know MP Comp has only came around in 1971。

 but well before then there was this understanding that this is a hard problem。

 though even though it't clear how to formalize that idea at the time。

So it's really if you remember one problem from approximation algorithms。

 it should probably be this one。At least in terms of the name recognition。So what is the problem？

Well， I'm going to give you a complete graph undirected。With edge costs。And the goal。Is to compute。

Traveling salesman person tour of minimum cost， so with a traveling salesman tour。

 while that's something that's not to be confused with an Eer tour。

 an Oer tour visits every edge exactly once a TP tour should visit every vertex exactly once。Compute。

The men cost TSP。Tour， okay。So this is a simple cycle。Each vertex visited once。So， for example。

Consider the following graph。It's supposed to be a complete graph。What is opt？In this example。

Even for small instances， MP complete problems are a little confusing， right？

So what do you think at least give me an upper bound on opt。

 you can certainly do release as well as what？How do you8？One， two， five， six。We to start。

You have to visit everybody once， so that actually doesn't matter where you start。

 It's going to be a simple cycle visiting every vertex， so you can go around the boundary。

 that's certainly a feasible solution。 that's going to have cost 14， it looks like。Can you be 14？13。

One， three， four， five， yeah， so 13。Okay。Tll you an example。Okay， so okay。

 why is it called what it's called Well you know like a lot of problems is sort of a silly story which masks how actually practically relevant it is。

 you know， so the story is that there's some traveling salesman used to visit a bunch of places blah。

 blah， blah， but why would this come up like for reals So imagine there's a bunch of tasks you have to do？

😊，And you have to decide upon the order of operations， so you have n things。

 you need to pick a sequence， one of the n factorial ways of ordering them。

And imagine that between each two tasks， there's some kind of setup cost either you need to change equipment。

 you need to sort of change the people who are working， whatever， So between task I and task J。

 there's some setup cost like time or money or whatever。

Then the TSP problem is really just the problem of figuring out the best order of operations to minimize the some of the setup costs。

 Okay， so really， fundamentally， what the problem is about is about finding an ordering。

 People just talk about it as like finding an ordering in a graph and ordering of the vertices， okay。

So even you can imagine even just like with a disk drive。

 suppose there's a bunch of outstanding requests for reads from a disk and you want to know how to move things to complete them all as quickly as possible。

 basically a TSP problem。All right。So let me start with some bad news。

So I said this was a hard problem， and it really is even to approximate。So assume P not equal to NP。

 of course if p equals NP， you can solve this in polynomial time， but if they're different。

 then actually there's no reasonable approximation algorithm。Okay。For any alpha。

So remember what's an A approximation algorithm， it runs in polynomial time and it always outputs a feasible solution with cost of most alpha times the smallest possible so there's no two approximation。

 there's no 10 approximation， there's no log n approximation。

 there's not even any2 to the n approximation for this problem okay。So it's kind of a disaster。 So。

 you know， why do I still have a lecture to give， Well。

 most of the lecture is going to be about special cases of the TSP。

 which you can do something interesting for。 But let me just prove this to you。

So probably be the only NP hardness proof that I plan to do in lecture again。

 my inductive hypothesis is that you sort of know how to do these from a previous class like 154。

 but here it'll serve the purpose to also rule out approximations， plus it's simple。

 so let's just do it。All right， so how do you prove something's MP hard。

 generally you take a known MP hard problem and you reduce it to the problem at hand right and if you don't think there's any algorithm for that。

 then you certainly aren't going to be doing it by solving it the problem at hand either。

So reduction。From the Hamiltonian cycle problem。So what's the Hamiltonian cycle problem？

I give you an undirected graph。Like this one。And I want to know， is there or is there not？

A simple cycle visiting every vertex exactly once。So like in this graph。

 is there a Hamiltonlesstonian cycle？Excellent， I heard it yes， so I know simultaneously。

Andpic problems are pretty tricky。 Yeah， so if there were one。

 it would be easy to convince you Id just show you this cycle。 Normally。

 it's hard to convince someone there's no Hamiltonian cycle。 But in this one。

 there is sort of a sneaky argument。Which is I'll just think about the x's and O's。

 notice every edge goes between an x and between an o。

 So in the Hamiltonian cycle you'd have to have an equal number of x' and O's。

 but there's five x's and 4 O's， so no Hamiltonian cycle。In general。

 it's an MP complete problem to check whether an under write tograph is a Hamilton cycle or not。

 you probably saw this in some previous course。 It's kind of one of the standard MP completeness reductions you do when from threeatAT。

 usually when you're taking when you're learning about MP completeness okay so we're gonna to take it on faith。

 this really is MP heart。Now we want to reduce this problem to approximating TSP。

 so we want to show how given a good approximation algorithm for TSP that would allow us to solve this problem efficiently。

So we need to take an instance of Hamiltonian cycle and we need to reduce it。

 we need to exhibit a TSP instance， so we're showing that TSP instances can encode Hamiltonian cycle instances。

So somebody gives you a Hamiltonian cycle instance， an undirected graph。

 and the responsibility of our reduction is to output a TSP instance。

On some graph G prime with some vertices v prime edges E prime and costs cost C。

 there's no cost in the original instance。And。So let me just tell you what in fact is the TSP instance going to be？

New vertex set。Same as the old vertex set。Okay。TSP is always about complete graphs， so E prime。

 presumably is all edges。And then what's interesting is like where do we get edge costs from。

 there's no edge costs over here， we need to make them up。Well， whenever there is an edge here。

 we're going to have an edge with low cost here。Whenever there's not an edge here。

 we're going to have an edge with high cost here， that's the whole idea okay。So for。

And E sets C to be equal to one。And for。Edge is not in the original edge set again remember this is a complete graph so every single edge is there for each edge over here it may or may not have been on the left。

 so if the edge was not there on the left，Then we said the cost to be big， okay？

So bigger than alpha times n， say n here is the number of vertices。 Alpha is just， you know。

 your favorite number where we're ruling out an alpha for approximation algorithm。Okay。

So everyone went clear on the reduction。 So this is a polynomial time algorithm that translates a Hamiltonian cycle instance into a TSP instance。

 We need to show that if we could solve this TSP instance well， meaning an alpha approximation。

 we could actually figure out whether the original graph was Hamiltonian or not。Okay。

 so why is that true？Well， suppose the original graph G actually does have a Hamiltonian cycle。

What is going to be the optimal， the minimum cost TSP tour in the instance that we get？And， right。

Why， well， what is a Hamiltonian cycle， It's a simple cycle that visits every vertex。

 What's a feasible solution to the TSP problem， a simple cycle that visits every vertex。

So if it's Hamiltonian cycle， that means every edge was in there in the original graph。

 so all of those edges have cost one and the new graph G prime， so there's a TSB tour with n edges。

 one cost per edge， and overall。So often g prime equals n。It's the most in。

 but it's actually equal to n。On the other hand， so if G has no Hamiltonian cycle。

What's a lower bound on the best possible tour in G prime？All find squared。U。Yeah。

 I think more like alpha n plus1 or something like that or alpha n plus some stuff。

I don't think you necessarily have to， so basically in your TSP tour。

 every single edge was not in the original graph， then indeed you'd be getting the alpha n squared。

 but if only like one edge is not in the original graph， you'd only be suffering alpha n once。

But yeah， it's right。Okay， so the point being。Optin G prime。

All that we care about is bigger than alpha times n。Okay。Because again。

 how could you have a TSP tour which was less， the only way to do that would be to only use the edges which have cost one。

 then that would map back to a Hamiltonian cycle in G， okay？Therefore。

 if there were an alpha approximation algorithm for the TSP problem。

 here's how you'd use it to solve Hamiltonian cycle in polynomial time。

 youd just take the Hamiltonian cycle instance， you'd run this reduction。

 you'd run the alleged alpha approximation algorithm。

 if you get back something which has cost alpha n or less， you'd say yes， it's Hamiltonian。

 if you get back a tour which costs more than alpha and you'd say no it's not Hamiltonian and that's the correctness analysis right there on the left board okay。

So again， if there's no polynomial time algorithm for the Hamiltonian cycle。

 there's no polynomial time approximation algorithm for the TSP problem。Any questions about that？

Okay， so this of course strongly motivates putting some restrictions on the input。

 so remember we were talking about possible compromises for MP complete problems last lecture。

 one of them was to restrict attention to a special case Now sometimes a special case will actually render its polynomial timesvable vertex cover on bipartite graphs being one example that you've seen on your homework in other cases it'll still be MP complete。

 but you can at least get a decent approximation and that's going to be the case for TSP。

So there's a lot of restrictions you can make， I'm going to make a sort of well motivated restriction。

 which you already are familiar with from the Steiner tree problem。

So I want to talk next about metric TSP， so again the input's the same you have a graph you have an edge cost per edge。

 but the edges are going to satisfy the triangle inequality so the shortest path between two points is always the one hot path。

Okay。So you might remember you know why is it useful to have the triangle quality in an algorithm or an analysis what's because you can do short cutting okay if you produce some solution and you kind of want to massage it a little bit。

 you can always replace paths with direct edges， you'll get something that's only cheaper so we're going to use that again。

Here。I claim that this is still NP hard， actually。And I even claim that basically this reduction。

Proves that。Now， the reduction as I did it with these big costs alpha times n。

 that doesn' prove that this problem is NP hard because these edge costs do not satisfy the triequ。

It's totally possible you have a unit cost edge， another unit cost edge。

 and the direct edge in between them is alpha times n， just a violation of the triangleequ。不。

Suppose to recover the trigonequality instead of making this alpha times n， I just make it two。Okay。

 they're still bigger。For the edges which are not the original cost。In the original graph。

So if these edges have cost one。And these edges have cost too。When there is a Hamiltonian cycle。

 once again， the best TSB tour will have value n。When G has no Hamiltonian cycle。

 it means any TSB tour uses at least one edge with cost two。

 so it's going to have cost at least n plus1。Okay。So that doesn't rule out any approximation。

 but it rule definitely proves it'smp complete， right。

 So checking whether the optimal solution has value n or n plus1 tells you whether the graph had a Hamiltonian cycle or not。

 and notice， think about it for a minute。If all of the edge costs are one or two。

 then the tringgon quality definitely holds if you think about it。

 there's no way to violate it if you're only using ones and twos。Okay。So any questions so far？Okay。

So let me highlight one there's gonna be a lot of similarities where there are Steiner treee lectures in the next 30 minutes or so。

 let me point out one interesting difference， so Steiner treeree。

 which we talked about first for the online algorithm where we did the greedy algorithm then we did the MST heur stick last lecture so there we we also thought about this special case where the edges cost satisfy triangle quality but remember that was without loss of generality so for the Steiner tree problem。

 the general case of an arbitrary graph and arbitrary edge costs reduces to the case of a complete graph and the trilineality so you can translate algorithms from one to the other that's on exercise set7 I think。

TSP turns out to be different so it really turns out that it's not with all loss of generality restricting to the metric case。

 And remember， we have our fingers crossed about that because the general case is hopeless right so we're really hoping we get a strictly easier problem and we do So it's different。

 this part is different。 So it's really a restriction to impose the triality。

So what I want to show you next are approximation algorithms for metric TSP。Now， remember。

 often the main challenge in approximation algorithm design and analysis is to figure out what's your strategy for knowing that your algorithm is near optimal。

 how do you prove that your solution maybe it's not optimal， but it's close to optimal。

And the way you generally do this is you have some kind of bound on the optimal solution。

 so for a minimization problem like this， you'd want a lower bound so you want to come up with a number which is only better than optt and then you want to prove that your algorithm has value not too much larger than this thing。

 which is only better than optt and therefore not too much larger than optt itself。

So we need to come up with lower bounds on how small the traveling salesman problem would be now in the first half of a 261 duality really kind of did that for us and we will use duality again next week quite a bit。

 but for NP complete problems you don't expect to exactly characterize the optimal solution using duality because that would prove something like P equal NPp。

All right， so where do these lower bounds come from？Well， again， today， like last lecture。

 we'll be able to just have some pretty elementary lower bounds。So for TSP。

So consider any TSP instance。this part doesn't even use the tri onality actually。

 consider any TSP instance。I claim that the minimum cost to it has to cost at least as much。

As the minimum spanning tree of G。So the cost of a minimum spanning tree is a lower bound on the cost of the optimal TSP tour。

 triangangleal quality or not。Who would see my stream？So what is a TSP tour， right？

It's a cycle that visits every vertex exactly once。Well it's a spanning tree。

 well it' a subgraph that's a tree it's acyclic and hits every vertex。So just take any tour。

 take the optimal tour， remove your favorite edge， you get a very special type of spanning tree。

 right a path。Of length and minus1？So that's only better than opt， you only deleted an edge。

 and the MST， of course， is only going to be better than this arbitrary spanning tree。It a proof。

Op to minus any edge。Equals a spanning tree of G。So MST only better。Okay。

And this is actually this is already enough of an observation to get a non trivialvial approximation algorithm for the metric TSP problem。

So this is going to motivate what's known as the MST heuristic。F metric TSP。

And this is going to reuse the ideas we developed for the Steer tree problem。

 we're going to see doubling， we're going to see short cutting。

Here's the main difference to look out for。If you remember both our online and offlinesteinner tree algorithms。

 the algorithms themselves were dirt simple， right the online algorithm was just to connect the new terminal to the old terminal which is closest to it。

What was our offline algorithm， it was just compute the MST on the terminals， that was it。

So we did all this doubling stuff， we did all this shortcu stuff。

 but none of that was in the algorithm for Steiner treee， it was all in the analysis。

 which is our way of connecting the output of our algorithm to an optimal solution， okay。

Here in this MST heuristic， we're actually going to use all those ideas， but in the algorithm itself。

Okay。So the first step is we just compute a minimum spanning tree of the graph G。Okay。

 so we know this is sort of only better than not， that's what Lima 1 tells us。

 but it's not a feasible solution in general， right this is not a tour。 Okay。

 so now we really need to somehow massage the spanning tree into a tour。But actually。

 if you think about it， that's sort of exactly what we were doing in the proofs of our Stener tree algorithms。

 especially the offline algorithm。 where we really took the optimalsteinner tree and then sort of massaged it into a tour on those same set of vertices。

 So we're going to do that now just in the algorithm。All right， and so remember， you know。

 just sort of reverse engineering where this comes from。 we need to make use of tri inequalities。

 Why are they useful， They allow you to shortcut So what is it you might want to shortcut。

 you might want to shortcut an oarian tour。 Okay， before an oerarian tour。

 you need an aerarian graph。 How do you get that We use double every edge。 Okay。

 that gives you an aerarian graph and you're off to the races。So。So in the algorithm。Construct H。

Which is T。With all edges doubled。This， of course， is an alyarian graph， okay。

 it's connected because T is connected and all the vertex degrees are even。

So that means it has an olerian tour。And again， we're going to actually compute it in our algorithm。

 but that can be done in linear time。No problem。So compute oiler tour。

Now remember we want a TSP tour that visits every vertex once。

 this is an oiler tour visits every edge once， so every vertex at least once。

 so we just shortcut out repeated occurrences of each vertex。

 So just look for the first occurrence of each vertex on the tour on the。

Well therearian tour and that's your TSP tour。Okay。Shortcuts of got TSP tour。

And I'm sure you'll find it very easy to believe that all of this can be implemented in polynomial time。

In fact， pretty much very close to linear time。So you can implement this very quickly。

So that's the algorithm。Any questions on the algorithm before we move to the analysis。

 which is quite short。Okay， so I'll say more about the final exam later but let me just sort of remind you that we have one and it's at the normal time by listed by the registrar which happens to be Monday first day of finals in the afternoon。

 330 to 630 they have not confirmed the room for me yet so I'll keep you posted and I'll say more about the exam a little later。

Probably about a week from now， I'll talk a little bit about it。Okay。

So analysis of the MST heuristic。So RTSB tour。So the final output of the algorithm。

It's certainly no more expensive than the cost of the Euler tour。

This is where we're using the trianglineality， right so we shortcut from C down to our final TSP tour。

 it only gets cheaper by the trianglineality。And so what is the cost of C。

 well C uses the Oer to uses every edge of the Olearian graph H exactly once。

 so the cost of that tor is just the sum of the edge costs and H。What is H。

 H is just the MST doubled， okay， with two copies of every hitch。

What do we know about the minimum spanning tree， Well we've got lemma1。

 which says that the minimum spanning tree is only better than the optimal solution。

 It's a lower bound so we're very happy to see that we can upper bound our algorithm solution by a constant2 times something which is only better than ot。

😊，That was the plan all along。Okay。So summarizing this proves that for the metric case of TSP。

 the MST heuristic is a two approximation algorithm。 It runs a upon at of time。

 always outputs a TSP tour with cost almost twice the minimum possible。

Turns out and I'll put this on exercise set 8。 you can't prove a bound better than two for this algorithm。

 Okay， so the analysis is tight。 There are examples showing that you might be off by a of two。Yeah。

any questions about that。Next order of business I want to add one more idea which gets us a better approximation ratio。

 actually it brings us to the state of the arts。The stateate of the art in this case happens to be from 1976。

But it is the state of the art。So any questions before that？Chris far。Good。So what's the idea。

 so how could we do better？And again， we can't do better just in the analysis。

 we need a different algorithm。If we want to do better。We want to make use of triangleequality。

 So we want a shortcut。 seems like the right thing to shortcuts an our areaarian graph。Now。

 if you start with the spanning tree it's not the layer in， you've got to make it a lower end。

 how do we do that， we doubled all the edges。Maybe that's overkill。

Maybe there's some way we could add stuff to the minimum spanning tree to make it o therearian without actually this sort of very draconian doubling every edge。

That's sort of the idea， I wonder if there's some cheaper way we can add edges to the spanning tree to make it earlier in。

 if so， we're off to the races， we just copy the rest of the MST heuristic。

And so there is this way to do it。So limit two， so this is going to be a second lower bound on the optimal solution。

 in effect， this one actually does use make use of the trigonality。So let M。The a min cost。

Perfect matching。Of some subset of the vertices。Okay。Now for this to make sense， of course。

 S is going to have an even number of vertices， otherwise you can't have a perfect matching。

 but suppose S has even cardinality and suppose we think about the min cost matching on that set， S。

Vge costs here are exactly the same as in our TSP instance， Okay。

 so we have this TSP instance with a bunch of vertices。 we say here's 1 thousand vertices。

 if I just match them perfectly， okay match them up 500 to 500， what's the cheapest way to do it。

So call that M。Then the claim。Is that the cost of this perfect matching is a most half the cost of an optimal TSB tour。

Or if you prefer， we have a second lower bound on the optimal solution， we already have the TSP。

 here's another one which is if you double the cost of a min cost perfect matching。

 that's also a lower bound on the optimal solution。Me。And this is quite slick。

 this is really quite pretty。Very short proof。All right， so first of all。Take the optimal TSP tour。

Of S。Okay， so of just these thousand vertices in S。Now this has cost。At most。The original ox。

By short cutting。so if there's a million vertices， you show me a tour on all of them。

 and I just want a good tour on a subset of 100 I can always take your to on all million and shortcut it down to these thousand vertices。

 short cutting only makes things better。So whatever S is。

 I know there's going to be a tour just of S with cost to most of the original opt。And you know。

Just to see the points， suppose the tour has six hops。What does this have to do with matchings？Well。

Color every other edge of the cycle blue。And then the other。Edges of the cycle red。So remember。

 S has an even number of vertices， so it's an even cycle。Evidently。

This tourr contains two perfect matchings of the vertices of S。The blue edges and the red edges。

Taken together， those two perfect matchings。Have cost a most opt？

The cheapest of the two is going to be a most half that。So yields two perfect matchings。

Cheaper one has cost at most。Optto 2。Okay。So that's lemon two。Questions with that。So if not。

 that brings us to Christto Fii's algorithm。From 76， as I mentioned。And really。

 we're going to take the MST heuristic， but we're going to do just like we said。

 rather than doubling， we're going to use a matching instead， otherwise it'll be the same。

So compute MST of G。Now again。The spanning tree is not oarian， So what are its failures to be oarian。

 Well its failures are its odd degree vertices。 Those are the things preventing this thing from being an aarian graph。

 So really the vertex degrees we need to correct is just the odd degree vertices。

Those are the ones we're going to stick a matching on top of okay。So at WB。

The vertices with odd degree。so like every leaf of the tree， certainly in W。

 but in general you have some internal nodes with odd degree as well， so those are also in W。Notice。

W， the cardinality of W is even。Why， well， in any graph， think about the sum of the degrees。

In any graph， the sum of the degrees is equal to twice the number of edges。

Because each judge contributes to exactly two degrees。So in any graph， to sum of the degrees is even。

That means there's no way you can have an odd number of odd degree vertices because then the sum of your degrees would be odd。

So in any graph。The must be an even number of odd degree vertices by a pary argument。Okay。Gooden。

So now we compute capital M。Which is。The min cost perfect matching。Of W。 Okay， so again。

 W is some even subset of vertices。 We think about only the edges that go between endpoints of w。

 so a complete graph on W if you like。It's even， so it makes sense to talk about the min cost perfect matching of the vertices in W。

Question， is this a bipartite matching problem or a non bipartite matching problem？

It's on the complete graph。Right。Complete graph is definitely not bipartite so it' is a nonbipartite matching algorithm So in fairness I never actually told you in this class how to solve the min cost or even the cardinality version of nonbipartite matching we did cover the Hungarian algorithm which gave upon amount time for the bipartite minco perfect matching algorithm。

I did mention a little bit about generalizations， we had a lecture about sort of more general algorithms。

 and we talked about how you could indeed solve both the minimum cost and nonbipartite matching problem in polynomial time。

 basically sort of a Hungarian algorithm on steroids okay。

So we're going to be using that algorithm as a subroutine to do step three。All right。4。

So our new graph H， remember previously， H was the spanning tree doubled。

Now H is going to be the spanning tree plus this perfect matching on the odd degree vertices。

That's our new H。看。It's possible that there's an edge that's in both the matching M and in the tree T。

 that's fine。 just means we get two copies of the edge in H， not a problem for us。Now。

 the point is H is olearian。Why， well， when we add the matching to the tree， remember a matching。

 adds degree， it adds a single incident edge to each of the match vertices。

 so it adds exactly one to the degree of every odd degree vertex in T。So after we add that matching。

 everything has even degrees in ourarian graph， and we can talk about the Oular tour of H。

So we compute this。And then so these last two steps are exactly the same as in the。MT heuristic。Okay。

And that is Christtofiti's anym。So is everyone clear on the algorithm？If I gave you an API。

 if I gave you a sort of black box non bipartite matching algorithm， subroutine。

 feel like you could code this up in 30 seconds or very quickly。Makes sense。Certain polynomial time。

 all of the steps are very easy except for step three。

 so it's really dominated by the computation time for the matching in step  three。

So the question is just how good is it， does it beat the factor two of the MST heuristic？And it does。

And the analysis is just as simple as before。Right， so again， we got this tour from shortcu from C。

 short cutting only makes it cheaper。This uses every edge as an auditator uses every edge of H exactly once。

 so this is。Some over the edges and H of their edge costs， here's the step which is different。

 H is not double the minimum spanning tree。Rather H。There's the edges in the minimum spanning tree。

Plus。The edge is in the perfect matching of the odd degree vertices， and again。

 it's fine if there's an edge that shows up in both of these sums that doesn't bother us。Again。

 this is just by the construction of H。Okay。This is the cost of MST， what do you know about that？

MST can only be better than the best TSB tour， that was our Lemma1。

What do we know about the min cost perfect matching？On any subset of vertices。

 we know it's the almost half of optt。 that was lema2。And we're done。

So this shows that Christtofii's algorithm is a three/2s approximation for the metric TSP problem。

Questions。So you should always be asking yourselves whenever you see kind of any algorithmic result。

 can we do better？So either can we have a better analysis of the same algorithm or can we have a better algorithm？

As far as the first question， the answer is no， we cannot have a better analysis of Christtoiti's algorithm。

 there are examples that show it might be off by a factor of three/ hves。

 that's a nice homework problem I may or may not put it on exercise set eight。

So if you can do better， it's got to be by a different algorithm and whether or not there's a different algorithm。

 which is better than Christtoiti's algorithm is you know one of the very biggest open questions in approximation algorithms it's been open for 40 years。

 literally nothing better has been known and it's not for lack of effort a lot of smart people have thought about this problem It's really kind of driving a lot of people crazy frankly。

Okay， so open。Can we beat three/ hals， it is not known okay？

Now one possibility is that you can't beat three/hals。

 What would that mean maybe you could prove a theorem kind of like our first NP hardness result。

 maybe you can prove a theorem saying that unless p equals NP is nothing better than a three/hals approximation that's consistent with our state of knowledge。

 but people don't really think that's true， it's widely conjectured you can beat three/hals。

 at least that you could get four thirds but no one's figured out how to do it。All right。

Any questions？Is。Yeah， so you have to argue that you have to argue two things。

 you have to argue it's connected， and you have to argue that all the degrees are even。

So the reason it so remember that's a necessary and sufficient condition to have an euler tour。

It's obviously necessary because you're going to go in and out the same number of times and then I think about it on exercise set number seven。

 but frankly you probably saw your discrete math class and just forgot it so basically if I give you an oarian graph where all the degrees are even you just find a cycle。

 rip it out and repeat。And then you're sort of done that kind of just you know， you stitch them。

 then you stitch them back together basically， to get an no other tour。

So right so you decompose the graph into kind of a you disjoint union of cycles and then you just sort of stitch them together that gives you the oiler to so that's all you need to argues it's connected because T is a spanning tree so adding M keeps it connected Why does it have all even degrees well this was the whole point of how we chose the matching M So we looked at the flaws in the spanning tree I It's odd degree vertices and what's cool about a matching is it adds exactly one to the degree of everything that's being matched。

So you take all the odd degree vertices and you toggle their parodity and become even without screwing up any of the other even vertices。

 which is important。Yeah。So that's why you can actually do the Euler tour。Any other questions？Okay。

Moving right along。So I want to tell you about one more algorithm， it's a little bit。You know。

 it's only very slightly more complicated than these two， it's still really quite simple。

And this is for。An almost equally famous problem。The asymmetric version。

Of the traveling sales and problem， this just means TSP， but in directed graphs。So input。

It's a complete directed graph。Okay。So between each pair of vertices。

 you have edges going both directions。So n times n minus1 vertices。And then you have a cost。

For every edge， okay？For edges that go in opposite directions between the same pair of vertices。

 they do not have to have the same cost， you can have different costs depending on which direction you go。

 hence the word asymmetric。If， in fact， you have the same cost on edges going either direction。

 that if you think about it is equivalent to the undirected version of the problem？

And as far as motivation， well I mean even sort of the ways I motivated the original TSP problem。

 you can see why you might have asymmetries I suppose you're thinking about minimizing the total setup cost in an order of operations。

 it's not it's easy to think of applications where if you do task I followed by task J。

 the setup cost between the two as different than if you do task J first and then task I so asymmetry of this form arises very naturally in many of the applications of the traveling salesman problem。

Okay。So as I said， this is also called ATSP。So ATSP includes the normal traveling sales and problem as a special case。

 so it's at least as hard because it's at least as general。So we're certainly going to have to。

 again， assume the tri inequality。Okay。If we want to prove anything interesting。

So notice that in a directed graph， the triangle quality still makes total sense。

 it just says that if you have a two hop path from A to B。

 if you replace it with the direct edge directed from A to B， it only gets cheaper。

So the math is exactly the same。呃。So trying on a quality。All right， and it seems。

 although we haven't really formally proved this， I mean， no one's really formally proved this。

 but it would seem that ATSB is really a strictly harder problem than the metric TSP problem。

So what's the strategy？At a high level， it's going to be the same as the MST heuristic and Christtofii's algorithm。

 we're going to build kind of Olerian thing and then shortcut it back down to a tour。

So the first thing to do， first order business。Is construct an mal arearian graph。

Now I have to remind you， we've just switched from under the graph to director to graph。

 so I have to remind you what lirian graph is in the directed case。

 so the analog of having all even degrees，Is now that every vertex should have the same in degree as out degree。

Okay。So。In undered graph， an aarian graph is both connected and has even degrees。

 And a directed graph， it should be strongly connected。

 Remember strongly connected means from any pair of vertices。

 you can go from one to the other and back。It should be strongly connected and the n degree of every vertex should be equal to the out degree。

Again， again， it's easy to see that this is a necessary condition and any Oer tourr that uses every directed edge exactly once you're going to grow out of a vertex the same number of times you go in。

The proof of suffiency is pretty much exactly the same as the underreed case。

 you just peel off cycles and then stitch them back together to get the oiluler to okay。

So we're going to do this， have a directed version of an oium graph strongly connected in degrees equal out degrees。

And then， of course， we can just shortcut same way。And by trying on quality。

 that will only make things better。 So the whole point reduces to cheaply constructing an hilllararian graph。

So that's the plan。So how are we're going to do this。

 where are were going to get this orlearian graph from？So in our last two algorithms。

 we started from an MST。And then we did various things， with a double dig we added to matching。

In the directed graph， it's not totally clear what should be the analog of this MST object。

 You could look at a directed version of a spanning tree， but doesn't seem to work quite as well。

 So we're going to use a different。're we're gonna So one way to think about the MST。

 You really want a TSP tour， which can't have it because it's going to be hard。

 So you compute something。 you know， which is sort of only cheaper。

 And then you massage it back into a tour。 So we want something which is only cheaper than a TSP tour and directed graphs。

 So the MST worked in under graphs。 We tell you about cycle covers， which are going be a lower bound。

 something only better than optt。 in the directed case。

So the algorithm will make use of the following subroutine。ポんん。

So we're going to compute a minimum cost cycle cover。Cycle cover is hopefully what it sounds like。

It's just a partition of the vertices into disjoint。Directed cycles。So again， what is a cycle cover。

 its directed cycles one or more？He should have at least two vertices。

It's no problem if you have just two vertices， so a cycle from one vertex to the other and back。

 that's okay。Size at least two each。And。Each vertex in exactly one cycle。好的。That is。

 the cycles are a partition of the vertex set。 Okay so that's what a cycle cover is。 Obviously。

 you can look at its cost out of the edges。 And so of all cycle covers。

 we're talking about the cheapest one。So what can you tell me about the relationship between？

A TSP tour。And between a cycle cover。Is one a special case of the other， for example？Every。Good。

 every TSB tour is a cycle cover， specifically the cycle covers with k equal to one。

These are exactly the TSP tours，So remember what was the point we wanted to have something which is only better than opt and which we can compute efficiently。

 so we've just argued that the Minco cycle cover is only better than opt。

 Any TSP tour is a candidate solution and it finds the best one okay。

So if we invoked the separate routine and it returned us a TSP tour， we'd be done。 We'd be golden。

 We'd just return that。 That would be optimal。 The issue is that it might return a collection of cycles。

But this is going to play more or less the role of the MST in the directed case。Yeah。

So the question you should be asking is it's like， okay， well， in the underre case。

 and I said we're going to start from an MST。You all know， okay， cool， MSTs are easy to compute。

 just run Pri on Crusco， whatever。So now I'm presenting you with this like new subproblem。

Min cost cycle covers， and it's not really especially obvious how you would do that in polynomial time Okay。

 so what you should be wondering is like， okay， have you just sort of replaced one MP hard problem with another one？

And the answer is no。While it's not obvious to see that it's in polynomial time。

 if you're a 261 CS261 student， it actually is not very hard to prove。

That it can be solved efficiently。Specifically。On one of the problems on Pro at4。

 which is also on ATSP， I'll ask you to prove this okay。So polyly time。Computable。In fact。

 it's a really nice reduction to the min cost bipartid matching problem。

 as solved by the Hungarian algorithm。So I don't expect you to see it right now in real time in lecture。

 but trust me， you actually know how to compute these efficiently。All right， so。

So let me show you an ATSP approximation algorithm is again quite old。

 this is from the sort of early 80s earliest parts of the '80s。

 it's not the state of the art anymore， but it's not that far from the state of the art。

 amazingly okay。U。Good。So remember our strategy， construct an oerria and graph in the directed sense and shortcut to get the tour。

So we're going to build up this olearian graph in iterations。

 it's always going to have in degree equal to out degree。

 but we have to work toward it being strong and connected。Okay。So in the main loop。

 while the current graph G。As at least two vertices， this may look weird right now。

 but in this wild loop， we're going to be deleting vertices from G。 So this is the exit condition。

Compute a Minco cycle cover of the current graphG。Called those cycles C went up to C。Or equals。

 that's what that was。U。Take all of the edges in the cycles， So for example。

 up there it would be those nine edges， Take the edges in the cycles and add them to our running set of edges。

 capital F。So add edges of the cycles to F。Right。Now I promise you we' be deleting some vertices。

So delete from the current graph G。All but one vertex。From each of the cycles。Okay。So for example。

If this is your cycle cover。Maybe you delete these two vertices and you keep that one。

 you delete that vertex， you keep that one， you delete these three vertices。You keep that one。Okay。

 so the graph just went from size 9 to size 3 in this case。Yeah。

So after this while loop completes after you've deleted all the vertices from your graph doing these successive cycle covers。

Now our graph H。Is going to be。The original vertex set。

And all of the edges that ever participated in any cycle cover， okay？

So H is just the union of all the cycle covers that we computed over all of the iterations of the W loop。

Okay。Now I'm going to argue to you in a minute。That H is in fact， oliium。

 it's both strongly connected and the n degrees equal to the out degrees。

Given that it's on our area in， we can finish this algorithm just as the last two，So4。Compute。C。

 which is a directed Euler tour。Of H。And shortcut。To a TSP tour。Okay。So that's the whole algorithm。

For this algorithm to make sense， for step four to make sense。

 I have to convince you that H is oureium， so that's what I'll do next。

 that once we agree we have a well definedfined algorithm。

 we'll talk about how good is the cost of the tour that it computes。

So any questions about the pseudocode？Okay。So why does step four make sense， why is H orian？J。Well。

 let's look at two invaris， first variance quite easy。So one is that you know in H。

 if we look at the union of the cycle covers that weve computed so far in that graph。

 all of the in degrees are equal to the out degrees。 that is for each vertex。

 it has the same in degree in out degree。Is that easy to believe？

So I think about the first cycle cover， right so after the first cycle cover。

Everybody has in degree one， everybody has out degree one。Yeah， so it's only true to one iteration。

 Now you delete a bunch of the vertices。 Not the vertices you delete will never participate in any cycle cover ever again。

 so they'll at the end of the day， they will have in degree in out degree equal to one。

The vertices that are left over for the second duration you'll do a cycle cover on them。

 and when you add that in， it'll increase both the in degree and the out degree of each of those vertices by exactly one。

 in particular the in degreegr and out degreeses will still be the same。

And that's just true throughout the algorithm。So summarizing at the end of the day in H。

 you look at a vertex v， you just say， okay， how many cycle covers was it part of。

 it was part of 10 cycle covers， it's going to have in degree 10，'s going to about to 10。

So that's not the problem， okay？Inviewes will always equal to be out degrees if you're just taking unions of cycle covers。

But remember， being oerarian doesn't just mean in degree equals out degree。

 It has to be strongly connected。 Okay The empty graph has in degree equals out degree。

 We don't want to call it aarian。So why is this strongly connected？

Well that follows from our second invariant。Yeah。Which is that for。If you look at any vertex。

 so we're sort of thinking about this algorithm， this wild loop kind of halfway through。

 So some stuff has been deleted， some stuff is still hanging out。

The variant is any vertex which has been deleted。There's a vertex which has not been deleted。

Such that this deleted vertex V can both reach that current vertex W and vice versa。Okay。

So for all deleted vertices， V， there exists an undleted vertex W。And current G， such that。

The graph H。Contains paths both from V to W。And from W to V。Okay。So that's the claim。

That this holds just inductively over the iterations of the algorithm。So let's see why this is true。

Well， again。Think about the very first cycle cover， like up there。Okay， in the upper right。

So maybe we compute that cycle cover and now we're going to delete five vertices， six vertices。

Leaving three。 So the claim is that for each of the six vertices we delete。

 there should be a vertex that remains a red vertex。

 where there's a path both to and from that vertex。

That's certainly true for these six vertices because each of them shares a cycle with one of the vertices that's left。

 remember。One way to think about it is we we delete everybody but one vertex from each cycle。

 that is one representative。Of each cycle stays around。Anybody that you deleted。

 look at the representative of their cycle along the cycle。

 there's both a path to that vertex and then back to the vertex along the cycle。

So that's why it's true after one iteration， okay， everybody delete share a cycle with someone who remains。

So you can reach them and they can reach you。And then if you think about it。

 this just holds inductively so say after this second iteration。

 right so now you do another cycle cover， you delete some more stuff。All right。

 so think about somebody who got delete， so I deleted people in the first iteration and in the second iteration。

 okay？So by our same argument， it's certainly true that if you got deleted in the second iteration。

 you can reach somebody who's left and they can reach you because you were on a cycle with them。

If you were deleted in the first iteration， well， at least you can reach somebody who is still there in the second iteration。

 you can reach them and they can reach you。Well， but we just said that everyone in the second iteration can reach someone who's still around back and forth。

 So you just stitch those two paths together and even this vertex that was deleted in the first iteration can reach somebody who still exists and backwards。

Okay。So this is a key invari Yeah you've deleted stuff， but from anyone who's deleted。

 you can reach in the union of the cycle covers so far。

 you can get to some undedleted vertex and back。All right。

 so that's the second invariant why so again， what are we trying to do。

 we know that all the degrees are correct in H and degrees equals that degrees。

 how do we know it's strongly connected？Well， think about the very last iteration of this while loop。

Okay， so you get down to the end， there's like five vertices left。What does it mean that this ends。

 It means that in this last iteration， the minco cycle cover was actually just one cycle。

 If you had two or more cycles， you're going be left with two or more vertices。

 So you haven't ended yet。 So in the last iteration， you compute a single。

 simple cycle on the vertices who remain。Okay。So when you put in that simple cycle on the vertices that can remain。

 obviously they can all reach each other in a cycle。

But our invariance says that everybody we ever deleted can reach the cycle and be reached from this cycle。

 so you put all that together， everybody can reach everybody。Which means it's strongly connected。

So that's the proof that it's hoary。All right， and so that means the algorithm makes sense。

 that means we really can talk about the Oular tour of H and then shortcut it。So any questions about。

The claim。It should still not be obvious whether the tour that it computes is any good。

 but it should at this point be clear that we have a bona fide algorithm。Yep。Questions。

So how's the cost？So let me show you what's true about this algorithm。So claim one。Okay。

This is a familiar kind of claim in every iteration。Every re iteration of this wild loop。

If you look at the current graph G， okay maybe we've deleted some stuff。

 if you look at the current graph G and the optimal TSP tour for just the current graph G。

 that's not going to cost any more than the original optimal tour again。

 just by shortcut so if there used to be a million vertices now we're down to 100 you could just shortcut the original tour down to these  thousand vertices。

 it would only be cheaper。Okay， so just by short cutting。

So every iteration there is hanging out this TSP tour that's cheap， of course。

 if we don't know what it is and we can't compute it。Instead。

 what we did is we computed a minimum cost cycle cover。But of course。

 a tour is just a special case of a cycle cover， so the Min cost cycle cover is only going to be cheaper than the best tour。

Okay。Cost of the computed。Cycle cover。Can only be smaller。Again。

 because any TSB tour is one candidate cycle code， so it's only better than not。

What does claim one really mean what claim1 means is that as we're building up H。

 remember H is this union of cycle covers。So as we're building up H over this while loop。

 claim one says that every iteration we pay at most opt。Okay。

Every iteration we know there's a TP tour that's most often we compute something which is only better recycle cover。

So that's claim one， every iteration we only pay off。

So claim2 is that so we'd be in trouble if there are a lot of iterations。

 right because we're paying perhaps opt de iteration。

 So we'd love it if there are only two iterations。 that's a little too good to be true。But。

At least we can say。That this while loop will have a most log based two of n。Iterations。

T you that's true？This is the figure to be thinking about。R of at least half。Perfect， perfect。

 So the proposal is that you're getting rid of at least half the vertices each time， each iteration。

 That's correct。 Why， well， remember in a cycle cover。

 I insist that each cycle is at least two vertices， okay。😊。

We only keep one vertex we delete the rest， so for every vertex we keep。

 we delete everybody else on its cycle that's at least one vertex。

 So if everyone we keep we delete at least one so the number of vertices drops by a factor 2。

Obviously， that can only happen log based2 n times before this wildder completes。

So because each cycle。Has size at least two。Half of vertices。Deletd each iteration。Okay。

And so now we're done， really。So cost。Of our tour。The tour of the algorithm。Well。

 how do we get our tour， we got our tour by short cutting the graph H。

 short cutting only makes things cheaper， so this is at worst to the sum of the edge costs in H。

What is H， it's this superposition， it's this union of a most logbase2 of N cycle covers。

And each of those cycle covers costsa most ought。So the most log base two of n。

This is the number of cycle covers， that make H1 pro iteration。

And this is an upper bound on the cost of each of those cycle covers。 It's most the cost of the。

Optimmal TP tour in the original graph。Okay。Any questions about that？Al right。

So this one's about 35 years old。This algorithm。And you know another one of the biggest open questions in approximation algorithms。

 in fact， most people would rank these open questions as number one and two in the field。

 the metric TSP and ATSP open questions， does there exist a constant factor？Approxiation。Okay。

So even like maybe a two approximation for all we know you can get for ATSP， okay？

Opinions are sort of split， but I think most people at this point think you can probably get a constant that probably there is an algorithm out there waiting to be found。

So I told you that this log n wasn't quite the state of the art。

 but it's almost the state of the art， so the best we know for polynomial time algorithms is O of log n divided by log log n。

Which was viewed as a huge breakthrough at the time because no one had even gotten that for 30 years but that's where things stand。

 that was from 2010 okay， so that's really quite recent this log over。

 log log up bound and that's where we stand。 It could be a small constant。

 but that's the best that we know。Any final questions？All right， that's all I got for you。

 I have a good weekend， see you Tuesday。