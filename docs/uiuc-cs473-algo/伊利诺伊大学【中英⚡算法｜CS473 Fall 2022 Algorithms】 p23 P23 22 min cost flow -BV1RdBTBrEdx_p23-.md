# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p23 P23 22 min cost flow -BV1RdBTBrEdx_p23-

![](img/52c280a15b3d54fd395e0e1593acb9c6_0.png)

我。野の完全部が。

![](img/52c280a15b3d54fd395e0e1593acb9c6_2.png)

そ is。あじゃ。Okay。Okay， thanks everybody for showing up on the last day before winter。

Tomorrow the temperature is supposed to dive down so by five o'clock tomorrow the temperature should be in the low 40s and then every day the following week。

The high should be in the mid 40s， the low is getting down to like 2018。So winter is coming。Um。

 if you want to， you know， completely understand you'd rather like spend time outside of the sun while you can。

 oh， maybe I should like turn on the projector。That would be a good thing， wouldn't it？嗯。是不是？Goish。

See if that works。All right。Yeah。I had every time it blinks。

 some piece of software is talking or some other piece of software。

So this is like blink five or six times that tells you something about how these things are built。

Okay， so administrative stuff。Homework nine， which is going to be the last graded homework。

Is due next Thursday。UPartly because it came out last night， partly because it you know。

Some extra time doesn't hurt know going into break。

 I didn't deliberately did not make it due on Friday because I assume people are leaving and want to get adopted。

There will be a homework 10 released after break， but it will just be for practice it won' be it won't be graded。

 it'll basically just be some more kinds of problems on this part of the material。As you know。

 warm up for the final exam。And we'll release solutions the following Tuesday？Um。

So after Thanksgiving break。There'll be two lectures on something or other。

I've got lots of good suggestions， but if you have others， please come me。And then the。

The following week after that。Tuesday， I'll walk through at least part of a fake final exam just to again go over the material and maybe some of the earlier stuff that caused issues just to remind you that it's still exists。

The actual final exam is the Tuesday after that。In this room， not in Lumis array。

U and I'll talk about more about the logistics， but basically it's the final exam is a midterm and a half。

Sos six questions， three hours， two pages of cheat sheet。啊，啊。

Slightly more emphasis on the last third of the course better。And then we'll be done。

At some point you'll start seeing announcements about ISIS forms。

please do fill those out please do fill those out for everybody the university hasn't yet figured out a way to incentivize students to fill out ISIS scores。

To fill out the ISIS forms。I am serving on the College of Engineering's Promotion and Tenure Committee this semester。

We do look at ISIS scores for the faculty in engineering。For promotion cases。

So this really is your opportunity to give your instructors a grade。😡，And more importantly。

 narrative feedback on what you think went well and what you think could be improved。I really。

 really wish we to adoptt the system that CMU has。😡，Which is。

The day that grades are supposed to be submitted。If you have filled out all your course evaluations。

 you can see your grades online immediately。Otherwise you have to wait three weeks。😡。

You still get the grades they're still there， you just don't get to see them。😡，Until later， because。

You didn't fill out the forms。They have like a 90% response rate。

We have like a 20% response rate on a good semester。So please do fill those out when they come by。

They really are helpful in particular narrative comments that you give about this class are extremely helpful for me。

 I do take this very seriously so please any feedback you can give is great。Right。All right。So。

One more lecture about flows and generalizations of flows in particular。

And the thing that I'm going to add today。Is in addition。To every edge having。A capacity。

I'm now going to give。assumingsuming every edge has another number attached。Which is costs。

So this is how much it costs to send one unit of flow through the。Okay。

 we imagine that the flow network is modeling a rail network。

If you have a line of track would cost 10， that means it costs 10 units to send one train down there。

 so that means that the the cost。Of a flow。Is equal to the sum overall edges of the flow along that edge times the cost along that edge。

And we want to minimize this。喂。😊，So this is a different objective。

Then maximizing the value which the show。😡，So what we've been doing so far。

We have some flow network G。And I've got a source in a target。

 and I need to be balanced everywhere in the interior。

 and I'm trying to maximize the net flow out of us。

 which is because balance is equal to the net flow into。😡。

I only have capacities in the standard formula。Right so。Max flow。And she。嗯。

So I'm going to change that formulation very slightly。I'm not going to add one edge。

Going from T back to s， this has capacity， it's infinite and it has costs that equal to negative one。

And everything inside G has cost the equal equal to zero， and I'll call that new graph product。喵。U。

In this case， I'm assuming。Every node has to be balanced。

I want to send flow through this network that is minimum total cost。😡，But I want every vertex。

 including SC， get the same amount of flow in as it has flow out。

But now that means any excess flow that's going in T is necessarily going to get re routeed from the blue edge back to us and it'll exactly cancel out the excess flow coming out of us。

😡，The total cost of this flow that I'm computing over here on the right is the amount as minus one for every end of the plug along the bluebed。

嗯。So this is。Men cost。Because everything is。Is balanced？

The flow that I compute here is called the circulation。It doesn't have any sort or sinks。

 it just the flow just moves around。😡，These are basically equal to each other。😡。

If I have a flow in G， I can send it to the circulation engine prime by routing the rh amount flow along this green edge。

And then the cost of that circulation will be exactly minus the value of the。Sthemetrically。

 if I have a circulation in prime， if I just restrict it to the MG G， I get a flow。

 and the value of that flow is minus the cost of the circulation。

So maximizing value on the left is the same as minimizing parts。嗯。So。

So that's a very simple example of minimum costs。😡，H minimum cost circulation。

 but more generally I'm going to assume every edge。As its own capacity in every edge as its own cost。

 which could be positive， could be negative to zero。M起。So。This is the。Minimum cost。

Circulation problem。So。Okay， so my input。Consists of a directed graph。G courttices， hs。

And every edge。every AGE has a capacity。The child called COV and it has a cost， dollar of E。

 the capacity is necessarily not negative， the cost could be anything could be positively negative。

50。The outputs。Is a function from the edges to the reels， this is a flow so I need balance。Yeah。Yeah。

InV is equal to themselves out。It's feasible。So the flow along an edge is。

Between zero and the capacity of that edge and the again， this cost， not the cost of E。

 but the cost of the flow， which again is defined as the sum of float breach edge and cost for each edge。

Is minimized。对。喂。😊，So。I'll get a。Refer back to this slide because we're starting now to get to the point where。

嗯。Most human beings have the ability to keep about seven things。

At the front of their mind are the once。Right you can kind of pay attention to only the a limited number of things we're starting to get into the realm of the number of things to track of in terms of what the input is。

 the goals are， what what the learning times we're going to get this is starting to creep up towards seven。

So are。嗯。If you' taking notes， please write this down and kind of refer back to you as I'm talking about this and as I'm talking about this I'll occasionally back and if you want me to refer back just raise your hand and ask me to go back。

If I had two screens， I would put this permanently on one screen working together。But。

For some reason， despite people using laptops and PowerPoint and things like that for 20 years。

 you know one figured out how to make one laptop drive a presentation on two different screens that two different things might。

U。So one thing to notice about this is。If the cost of every edge。Is positive？No。

Then the zero flow is up。Right。If it costs me money to send any flow through anyed。😡。

Then I'm just not going to send any flow through any energy。😡，Yeah。嗯。That's a one way implication。

If you have flow where if you have a cost function where some edges have cost zero。

 this may not be the only optimal flow。You might be able to send some flow around a cycle where every edge has called zero。

 that would be fine， but it's still the case that you know the zero flow is the best you can hope for。

Okay， so the problem is actually only interesting when some of the edges are negative。😡。

And this is actually going to be significant in the algorithm。嗯。Which that I'm going to present。

 which is called cycle canceling。Okay， so I'm given G， I'm given the capacities， I'm given the costs。

So I'm going to start by setting F， this is the flow that I'm going to build initially it's just going to be zero on every edge。

That's feasible， it's balanced。😡，But it doesn't necessarily have minimum costs。

And then I'm going to do something similar to Ford Folkerson。

Which is I'm going to look in the residual graph of my current flow and ask if it's possible to make the flow better。

😡，If you remember from homework。The condition that a certain flow isn is a。嗯。Unique maximum flow。

Right the condition there needed to look for was。😡，If there is a cycle in the residual graph。😡。

At least link three， it's a simple cycle， but not just as spur。

If there's a cycle in the residual graph， then F is not unique maximum flow。

 I can push flow around the cycle and get a different flow with the same value。😡，So。

Under what conditions？Do you think？So let's suppose G has some negative edges。😡，嗯。

So the zero flow has total cost zero。Under what conditions do you think you can compute a flow that has negative total cost？

😡，好的。There's no S。Re周题。There has to be a cycle。That includes a negative edge。

But more interesting than that。ItNot just that it includes a negative edge。

 there's a condition if I push flow around a cycle， what happens to the cost？

The cost increases by total cost of the cycle。😡，Times the amount of flow on the。

The amount of flow that I put around the cycle is positive。😡，So if I want the cost to go down。

 the cycle itself has to have negative costs。😡，哎。So while this residual graph has a negative cost。

Cycle。Why is this？嗯。So C is。Any。Negative cost cycle。And now I'm going to augment the flow。😡。

By pushing around C。嗯。So this expression here， this is the minimum residual capacity among all the edges you see。

😡，I'm pushing this much flow around this cycle capital C。😡。

Me give this a little clear this the capital sea。Recycle。系。

So and then I recompute the residual graph and I look for negative cycles now。Now。

 one thing that I need to be a little bit careful about is if I have an edge in the original graph that say has capacity five and cost negative two。

😡，And I push one uniform flow。Along that。Edge。So flow value one， then in the residual graph， again。

 as usual I'm going to have two edges。The residual capacity tells me how much more I can push along the edge。

So in the residual graph now I'm going to have capacity four。

 I can push four more units of flow along the original edge。

And the reverse edge will have the capacity of one。

 I can push one more unit of flow along the reverse edge， in other words。

 one less unit of flow along the forward。But I also have to put costs on the individual levels。

The cost on the forward edge is going to be exactly what you think it is。😡。

What it was the original graph。What is the cost on the reverse edge when it shows a individual of that？

😡，It'll be positive too。Okay， so this edge will have。When I reverse an edge。And negate its cost。

If it costs a dollar to send one meter to flow forward。

 it costs negative$1 to control one meer to flow back。😡。

Okay so I can either pay by going forward or get paid by going back。

So when I talk about negative cost cycles， that's with respect to this residual cost function。

 not with perfect in dignity。When I introduce a backward residual edge。

I define its cost by negating of the forward。And that's the entire algorithm。喂。😊。

So just to give you an idea。😡，Again， to connect this back to things you've already seen。

As long as the residual graph is a negative cycle， push flow along that negative cycle。目的。Okay。

 if I go back to this reduction and I apply this algorithm this graph here。嗯喂。

Every edge in the original graph G has cost zero so the only way to get a negative cycle。😡。

Is to have a path going from S to T and then I follow the edge back from T to S and that cycle has cost negative one。

😡，So I pushed flow on that cycle。That's the same as pushing flow on the path too。Okay。

 so cycle canceling the this graph and you like is。

Ford Volkerson in the that in the left and everything that we said about Ford Fkerson about。Well。

 if you have integer capacities， then every time you push you'll get an integer flow。

 it'll stop after a certain number of iterations， you have irrational capacities。

 you can inter loop and do weird stuff， but you can choose the path carefully if you choose the cycle carefully。

 then you can get the vision model。Everything that we did for focus and generalizes to this particular case。

Now it's a little bit。And it's not a little bit， it's actually quite a bit more complicated analyzing these algorithms in the case where lots of edges have lots of people。

😡，啊，好啊。I'll write down it the time down in a second。The moral that you should remember is。

I consult solve with some polynomial pie。嗯。Okay。Right the exact time balances。There is a book called。

Commonatorial optimization。Written by a Dutch colleague Lep Schhrin。It's a three volume book。

It's yellow， so those of who do math are immediately scary。It's three volumes， it's this bit。😡。

in your book， it's almost thicker than it is wide。It's something like。3000 pages。And you think。

 oh my God， that book must go into so much detail about everything you write every detail down that don't leave any stone unturned when you actually open the book。

😡，Read it， realize it was nothing but a barely sketched survey。😡。

It talks about the fundamental results like For Fkerson， and then it has pages of just tables。

Of here are 20 algorithms for solving minimum cost flows with different running in time spending on different parameters。

嗯。Let's talk about more interesting things in page 50 and just goes on from there。

Gobs of work on this。Trying to figure out， especially at this stage。

 an algorithm that I can both explain to you in full detail and analyze in full detail is almost。

Opoす。So I'm just going to say what you should remember is， oh， that's Min cause flow。好像没有发。

And in particular， this cycle canceling algorithm， means I choose the right cycle。😡。

I will get a polynomial time algorithm。Um。So before I go on to like like sketch one easy analysis。

There are questions about the algorithm。😡，Questions about the problem。Yes。

This is an algorithm finding a minimum cost circulation。The case where everything is。

There's a more general version of in potlo where you've got thousands and strengths for the few and then it's not pair to upon it。

O。So。嗯。Okay， so if。The algorithm halts。It returns。A min cost。Circulation。

But it doesn't always halt because you can have weird irrationion capacities and loops just like we' focusing。

 but if you have。Integer capacities。Then the running time is v times e times the cost of the final flow that you end up computing。

And the argument is。Well。What's the speed time key？Well。

 the V times E is the time to find a negative cost cycle。All right， so this。

You can do by using development for short H。You pick a new vertex to get your source to attach that。

All in the entire graph with edges with weight zero。

 and then you try to compute the shortest path from S to every other node in the graph。

If Belmond Ford doesn't mergeverge in order heat time。

 some edges are still tenses that means there're negative cycles in there。

 presumably will further actually find the negative cycle。

 the whole thing ends up in running in order of heat time。So this is finding one。One negative cycle。

The cost of the final flow on the。Actually， this is not， oh yeah， I should also say integer costs。嗯。

If I've got integer capacities and intever costs。😡，Then whenever I push flow around a cycle。

 I am decreasing the cost of the flow by at least one。I started with a flow with value zero。😡。

I suppose I should really put an absolute value on this because it's negative。

 I started with the flow with value zero every time I audit I meant the flow go down by each one。

 so the number of steps to get down here to negative 473 was at most 473。Okay， again。

This is exponential in the number of fits that I need to represent the input so this is。Not great。嗯。

So there's a bunch of heuristics。Thank。I mean， in practice， it's probably fine。

Just find any negative cycle around it and in practice it'll probably be as fast enough。Um。

 but if you really want to create the timeouts， you need to find a good negative cycle。😡。

So can anybody suggest what a good negative cycle might look like？

Which cycle do I want to pursue flow rent？没个。Yeah， okay， so。The most。Negative cycle。

So I want to minimize the cost of the total cost of the sending one unit around the cycle。嗯。There's。

Only one problem。嗯。Finding that cycle is in hard。Sorry。

What did we do for flows to get an efficient algorithm？

We use Grford search to find the shortest path， so maybe the thing to do is to find the shortest。

Negative cycle。The negative cycle that has the minimum number of edges。Unfortunately， that's NP hard。

It turns out that to get an efficient algorithm， what you want to look for is the minimum mean cycle。

 so what you want to minimize。😡，Is the cost of the cycle divided by the number of edges？

So can't spell， sorry。In the cycle。This， it turns out you can actually find in order vegan time。

I'm not going to explain the algorithm， but I have many details。

 but it's first of all not obvious that you can find this cycle quickly。

 especially given that other things are hard， it's also not obvious。But it's true。

That you end up with V log V。Iterations。And so the running time ends up being b squared E log B。

This is。An album body。哦。Goldberg and。And this is an algorithm by。2。

You might have heard of some of these names。系。嗯。So。Again。

 I'm not going to prove either of the claims about running time。😡。

But just I want to point out that it is possible to achieve a running time that's polynomial in the size of the graph and that works even if you don't have intererger capacity need。

不好意思。This is nowhere near the best algorithm， but this is the fastest implementation of cycle canceling。

😡，I know if there are other strategies， and I'll talk about one more strategy。I'll the minute。

 few minutes。So this is the fastest I know how to do。The cycle cancer number。Yes。So。Questions。About。

This algorithm。🎼要听。好。So。I hint at this already。But this particular formulation of。call problem。

It's not the most general。OkayThe more general formulation of minimum cost flow has a few more parameters。

😡，Okay， so you've got a graph。Again， vertices and edges， again， this is director graph。

I have capacities。Rereach edge。I have lower bounds。PasThese are positive lower bounds are。嗯。

This is an Ed saying， in order to be considered feasible， I need at least five units of Florida。😡，咁。

Okay。😊，I have costs。Free charge。Which could be again， positive could be negative could zero。

 I have balances。T vertex。With the condition that the sum of all the balances is zero。

 otherwise I can't do anything。And what I want to output。So again。

 a function from the edges to the reels satisfying。A couple of conditions。It needs to be feasible。

 that means that the flow value along an edge is between the lower bound。

And the upper bound capacity。It needs to be a flow。

 so the total flow into a vertex minus the total flow out of that vertex。

Is equal to the balance that vertex。And it needs to have minimum cost。Which again。

 is some of the flow value through an edge times the cost of that edge。Sorry。flow。嗯。Okay。

 so the balance in a vertex says。If the balance is five。

 that means I need to have five more units coming into the vertex that leave the vertex。

 so positive balance means a demand at a vertex。A negative balance means you have a surplus at that first。

 five more units coming out can come in。😡，So there's a lot going on here。😡。

I've got some vertices that are producing stuff， I've got other vertices that are consuming stuff。😡。

Um I've got edges that say I need to have some flow going across these edge， but not too much。

U and every edge has a cost which might be positive。

 you have to pay and use this edge or it might be negative。

 please please use this edge up a you money。😡，And again。

 your goal is to find a way of satisfying all the various constraints。

You have to satisfy the balance constraints so you route the surplus to all the deficit routes slightly demand。

And。You say within the upper and lower bounds， apost judge and。😡，Do all that as cheap as possible。嗯。

That's one， two， three， four， five， six， seven3。系。So what I want to argue is that。I can in fact。

 solve。😡，This more general version of the problem by reducing to the minimum cost circulation problem where all of the。

All of the lower bounds are zero and all of the balances are zero。😡，喂。Then I can at that point。

 I can just go back to the earlier algorithm。Okay， so I'm going to do this in。诶。😊，So as usual。

 you know， I start out by by having the zero flow now the zero flow is not balanced。

Zero flow is not feasible。And the problem is interesting the zero plug doesn't have minimum cost。

 so I've got three conditions that I need my foot to satisfy I'm going to try to satisfy the easiest one I can。

Which is to make the flow feasible。So what I'm going to do。Now。

 I've actually simplified things slightly by assuming the lower bounds are positive。

Any edge that has a lower bound， I'm just going to put that much for on。Now that's going to。

If I'm putting a value， a positive flow value on an edge in isolation。

That means I'm increasing the demand that the source of that edge is going to meet later。

 and I'm increasing the supply of the target of that edge the later。😡，系。So。

First thing i'm going to do is basically just set f to be equal lower bound now I've got a feasible。

嗯。啊。But it's not necessarily balanced。And it's not necessarily minimum cost and now I'm going to work in the residual graph of this book。

😡，Yes。Well， it's not the。There is no S， there is no T there is no amount of flow， there is no S。

 there is no T。😡，F is a function from the edges to the reels。It is zero at every edge。

And then it's equal to the initially。😡，And then I change it by setting it equal to the function L。

 which is also a function from the edge。This is a function F here。

 this is a function from the edges to the realel zero is a function from the edges to the reels it assigns the value zero to every edge。

😡，L is a function from the edges to the reels， establishing the lower bound that I want for that edge。

喂。改。嗯。So at this point。All I've done is to say any exit that wants flow， give it flow。😡。

Now this changes the balances and in particular， in the residual graph。😡。

I've updated my residual balance the same way that I have residual passess and residual costs and I have residual balances。

😡，嗯。But within that residual graph， the zero flow is feasible。All the lower bounds。

 all the residual lower bounds have been reduced to zero。

But the balances might be different than what I started with。

Now I need to figure out how to make this flow balanced。So what I'm going to do is ignore the cost。啊。

And repeatedly through the following。Find any node that has negative residual balance。

 this is a supply node in the residual。😡，Find any other node that has negative residual balance。

 this is a demand node residual dual balance。😡，Find a path from that supply node S and node T。

 which is much flow as I can along that。That will reduce the excess at S and it will reduce demand of T making it closer to thebal now I don't know what it's going to do with the cost。

 but I'm not thinking about costs right now。And I'm going to do this within the constraints of trying to keep the flow feasible。

 so essentially what's going on here is I can attach a source node to all the supplies。

 attach a a target node to all the demands， and I'm running or focusson to psychotatic clear all the supply demand。

😡，嗯。So this is you know， Ford Fulker Center or， one of one of it' there。So at this point。

 I of a flow F double prime that is both feasible and balanced。😡，I maintain feasibility as I。

As I do this augmentation。And every time I augment， I make it more and more balanced。😡，系。

This is really just the standard maximum book。So order meeting time。

Now I look at the residual graph with respect to this new flow F double prime。😡，Now。

 within this new residual graph of F double prime， the zero flow is feasible and the zero flow is balanced。

And now I want to minimize costs。All my node， all my vertices have zero rescical balance and zero recical lower bounds。

 which means at this point。😡，I need to compute minco circulation。And then I get my final flow。

At triple5， that is a minimum cost flow in the original。So my strategy is going to be。😡，Um， first。

Find any float that is feasible。😡，Then keeping the flow feasible， improve it until it's balanced。

And then keeping it feasible and balance， improve it until it afternoon。So。Priorities here。One us。

To balanced。3。Minimum cost。Now。set three years the cycle cancel mode。

Now the cycle canceling algorithm works by looking for negative cost cycles in the individual graph。

 if there are no negative cost cycles in the individual graph， then I know that I'm done。😡。

So because I'm going to play with these priorities a bit。I'm going to actually recast this。As。

Locally optimal。😡，No。Negative。Residual。Cyclees。So a flow more generally， regardless of the balance。

 a flow is locally optimal if its residual graph doesn't have any negative cycle。😡。

If it's not locally optimal， that means I can push flow around without really changing anything about balances or fe and make cost them。

😡，对。So this is the order that。That the general reduction goes。I think at this point。

 I should stop and make sure。This kind of makes sense。可以。Again， getting to step one is oh。

 we're just directly assigning via this is bru course order in time。

Getting the balance that's essentially for Fson that when order VB time。

 and then the last step of moving cycleed cancer。我两。O。So。

The other solution strategy that I will describe。Handles these three priorities in different order。😡。

喂。😊，Instead of。First， feasible， then balance， then minimum cost or rather then locally optimal。Again。

 first， I'm going to try to make the thing feasible。😡。

Then I'm going to try to make it locally optimal。😡，And then finally。

 I'm going to try to make it valid。😡，系。So。This other strategy。Is called successive shortest paths。嗯。

And the successive shortest path strategy is going to be one。Viasible。2。嗯。Loocally optimal。And three。

Bs。嗯。So the feasibility step is going to be exactly the same as it was in the earlier reduction。

If I have any any long zero bounds， I'm just going to push that much flow。'Through the edge。

That's going to change the balances that are in。That's fine。Okay。

 so I could assume that the zero flow is at least feasible。不错。Now， remember。

 locally optimal means there are no negative scientists。😡。

The way that I'm going to resolve this by enforcing the assumption that at this stage of the algorithm。

Somehow I need to get all costs hidden positive。Now this isn't going to work in general。

 I might have， you know， here's。Some flow network。嗯。

And maybe you know this has these edges all have capacity one， maybe this has cost negative one。

 this has cost negative two， just cost three， this has cost four and this has cost two right。

Well let's say we should capacity one，0 down zero。I want to do something simple to this graph。😡。

That changes all of that。Changes all the edge in deposits。The way that I'm going to do that is I say。

 okay。Any edge that has negative cost， I'm just going to saturate that edge。

I'm going to push as much slow through that edge as I can and grab that patch。

Okay just good any opportunity I have to go get money， I'm going to go get money。

 so I'm going to push as much flow as I can through this edge。😡，And so if that has capacity one。

 what happens in the residual graph？Is now I get the reverse edge。

And the residual cost of that edge has gone from negative to positive。Similarly。

 I'm going to send one unit to flow through this edge but what that means in the residual graph。Is。

That the reversed edge shows up and it has cost positive one。嗯。Once I've done this。哦。

All costs in the original graph a positive， which means those cycle in the original graph can be negative。

Since's the sum of not negative not negative edges， so here F is。Um。Either of the capacity。

The next flow value here is either the capacity of the edge if the cost of that is negative and zero otherwise。

Yes。Okay。But when I reversed those two edges。I also changed the balances in the residual graphs so now i'm sending one unit of flow into that vertex on the top right。

 so in the residual graph has a this is a supply node it has one unit of supply likewise this has one unit of supply and finally this has two units of demand。

Okay， so when I'm you know， pushing flow through these edges。

 that has an effect on the not only the cost but all。你冇先。

And so this is the setup for the main part of the algorithm。At this stage。I have。好。

Lower bounds are equal to zero。All costs are greater than you equal to zero。Balances can be anything。

And capacities， of course， are non negative。Okay， so。Lower bounds don't really exist anymore。

And now I want to take。This。Low network， which at this point I've established。

Feaasibility and local optimality。Now I want to reduce pulse。Oh sorry。

 look up the now I want to no store balance。Okay， so。I didt ever store balance before？Yes。

Find a supply note。Thank man though。Ill find a path from one to the other and I push slowly。对。

I want to do that in a way that affects the cost as little as possible。😡，You' grabbed all that cash。

anything I do now in this network is going to cost me money。😡，I don't want to spend money。😡。

How should I restore the balance， what do you think I should do？I find a supply node。I demand though。

How do I route flow from the supply node then？没。The lowest cost pack or in other words。Shortest path。

This is why it's called success to path。And now treating the cost is the length of the edge。😡。

The total cost to send one you to the flow on the path is the length of that path。

I want that cost to be as small as possible。😡，Because I want to pay as little money as possible。诶。😊。

Yeah yeah the one two。TheyNo， like this cost。Cost is linked， capacity is not linked。

Capacity is width。😡，O就对就是一个样子。Yeah。So this this is again。

 you've got lots of numbers attached to the edges， it's important to keep this straight。

The intuition you should have is I've attached two important numbers to the edge at the input stage。

 one is the capacity， the other is a cost。The capacity is how many trains I can push from Berlin to Stalingrad in one day。

The cost is， how much does it cost to push one train from Berlin to Stalingdad and one dad？

So capacity is width。Hot is length。嗯。So at this stage。I'm going to do。TheFollowing。

 so the successive shortest path algorithm again。嗯。I've got capacities and I' got costs。Again。

 I'm really working in the residual graph from the two previous stages， but we'll just call it G。

While Gf is not。Balance， meaning there's some node in the residual graph。Actually。

 let me just say it this way， well F is not balanced， well F doesn't meet the balance them might。B0。

I'm going to let S be。Any node。In the residual graph。With residual balance。It's negative。Oh。

See the any node。In the residual graph。Where the residual balance。It's positive。

Then I'll let Sigma be shortest。下。With respect to residual costs。From S to T。

And then I'm going to push。As much flow as I can。Along that edge。Okay， again， this expression here。

 this is just the minimum capacity among all edges on that path。

Here I'm treating Sigma as a flow from ST。Value one， I scaleor out of this minimum amount。

 I add that to my。This。Se is really， again， kind of like For Berson。

 except the source of the targets move around various iterations into pick a source that has too much stuff。

 pick a target that has not much stuff。The biggest difference here is that I'm always using Georges path。

And this is shortest， not by number of edges。But by was。Now this looks like。😡。

If I just left out the word shortest。This looks like exactly the same algorithm that I had before when I got I've got a flow network with weird balance things and I want to restore balance to network。

 I find some supply， find some demand。I route this supply to the demand。

Eventually this is going to lead to something balanced。Oous。So obviously。

 when this fault it's going to return something balanced。Obviously。Right， obviously。

What goes off in your mind when you hear the word， obviously？Instantly。

 whenever you hear the word obviously， what do you think？😡，Pve it。

 I think something slightly more cynical， the wrong。いくね。U。So there's some subtlety here。😡，对。Um。

 so it is possible that I may have to spend more money in the third stage than I earned these。

That is possible。 that's not好。It just means that the minimum costs flow in this network had positive costs。

系。Well， so the subtlety here is I'm pushing things around in the residual network now the original network G here I started off by saying once I got to this original network G。

 all the edge costs were positive， but as soon as I start pushing throw around。

 I'm going to be introducing residual edge just going have to add。😡，F。Was there something？

About negative costs and short。Yeah。So shortest path isn't even well defined。😡。

Unless I can convince you。There are no negative cycles in the residual graph。

Now I started with there no negative cycles in the residual graph because all the edges had positive cost。

😡，It started with locally optimal， all cycles have positive cost。😡。

And now I'm updating it by this shortest path， but in order for this algorithm to even be meaningful。

 I have to convince you that I maintain that invariance。😡，喺。😊，So I claim。Is that？There are never。

Negative cycles。In the residual graph or uncommonly F is always。Locally often。

And this claim implies that at the end。F is feasible。And balanced。And locally optimal。Which means。喂。

But this plane。It's proof。嗯。All right， so again， I need to stop。

I really understand at least this part of the algorithm started with a network that maybe has some balanced things at the nodes。

But all the costs initially are positive。嗯。听到过的。To try to restore some balance into this network and we can pick。

 source so supply node， meaning we it has negative balance。Demand node means positive balance。

I pick the shortest path in the residual graph between those two notes and I push as much flow as I can along that path。

So the idea of find a path that makes things better should be reminiscent in the for focus。😡。

But in order for this algorithm to be well defined， I have to know that shortest pad this。😡。

And shortest paths are well defined。Only if there are no negative cycles in crowd。

That was that's fine， that's a condition that I want。To。I want to maintain anyway。

We refer the end of result happening。But in order to make the algorithm even like an algorithm。😡。

I have to convince you at every stage。The residual graph has no negative sight。诶。😊，Yes。

So let's do that。ok嗯。So this is， of course。How do you prove things？Induction。

And in particular this is going to be by induction on the number of iterations of the main loop。

 so I'm going to assume that at the beginning of an iteration of that loop。Um。

 my residual graph has no negative cycles， and I'll prove that at the end of that iteration that my residual graph still have no。

Okay， so。Let F be the flow before some iteration。And let F prime be the flow。After。That iteration。

 and now I know that F prime is equal to F plus the shortest path times the minimum capacity along that shortest path。

系。So my induction hypothesis is that the residual graph of F has no negative cycles。

So that means that this shortest path sigma is well defined。Good。系。So here is。

Pture of what's going on， we found the source。On the target。The source has excess balance。

 the target has demand。I picked some shortest path sigma。From E when I got forward。

And for the sake of arguments。Suppose the new residual graph does have a negative sum。😡，Right。So。

Suppose。crime has a negative cycle。See。人。😊，Now， the original residual graph didn't have a negative cycle and the new residual graph does。

😡，That means some edge in C wasn't in the original residual graph， but it is now。😡，Okay。

 so that basically means that C has to have an edge。😡，Like this。

That that sigma pushed flow along some edge and its reversal showed up。😡。

And that reverse edge is in that negative effect。That's the only way new Ed。Okay， so。The reverse。Of。

Some。Edge。In C must。Be in。Sigma。Okay， there might be more than one such edge。

Maybe there are two edges in this cycle that happen to all cities。ok。

So let me draw the rest of the off。Any of the psycho goess like this。

And then this cycle goes like that。Okay， so this is my cycle C。Great。That has negative costs。Now。

What can I say about the flow？声物角色。我 you方 on直个。Wder one see。What do we get？

You get a flow from ST to value1。I pushed one unit flow from S to T that increased the flow value by one。

 then I pushed one unit flow around the cycle C that didn't do anything to the flow value。

 so this is an ST flow。With。Value。What。Don't worry about whethers out it care。

 but worry about it' awesome。what it means is that this is a function that attaches one to every edge of sigma that isn't in C。

 one to every edge of C that isn't in sigma， two to every edge that is in both C and sigma in brawni in that place。

And zero to any edge that's forward in sigma and backwards and see。OkayThis is a flow from S T。

It satisfies all of the conditions of being the flood， its balanced everywhere except。

And what that flow actually looks like。Is the backwards edges？The backwards edges in。

C and the forward edges in Sigma cancel each other out。

And so what you'll notice is there's another path。In there from S to T。if I decompose this flow。

I'm going to get a half。Sigma prime。From S。To T plus maybe some cycles。对。

So I started with my shortest path sigma and my negative cycle C， glued them together， I got a flow。

 I decompose that flow。Pas and cycles where I'm only going to get one path because the flow had got only one and a bunch of cycles I ignore。

Now I've got this new path。Here。Sigma prime。What's the cost of Sigma prime？Well。

 it's at most the cost of C plus the cost of sigma。😡。

The cost of sending one unit to flow along a crime。

Um that's at most because sending one on sigma and then sending one uniform along the sea。

 it's it most because I'm ignoring that little cycle up there at the top。mightight not be。

But this is a negative cycle。So that's less than the cost of sigma。But Sigma was the shortest path。

And I've just described another path that's shorter than signalma。So you have a contradiction。

To this。Something。So I assume after I push flow on the shortest path。

 that there was a negative cycle， that assumption implies that I can find an even shorter path。

I'm predicting the fact that I。的色里面放大。Okay， so。That means there are no negative cycles that is now the end of my proof。

可以。So in other words， if you push flow along the path， that isn't the shortest path。😡。

You will create a negative sum。😡，And that negative cycle is basically push push along your favorite path and then push backwards along the short of path。

 their vice ver。😡，The difference between two paths will have cost equal be the difference of their weight。

嗯嗯。Okay。All right。So for those of you are only interested in how you would actually implement this algorithm。

 and not proving works。😡，你冇得样。Yes。And in the last minute。啊。

How do you actually compute the shortest path？Well。

 what does Dkester's algorithm need to be efficient？😡，Yeah， but so。Again。

 I'm using Belelman Ford and again， this is exactly like the cycle cancer using Belelman Ford there to find negative cycles here。

 I know there are no negative cycles， but I'm using Belman Ford to find fors patents。😡，So again。

 this takes order of even time and now the efficiency of this algorithm boils down to。

The number of iterations that you need to go through。Again， you can choose。😡。

The number of iterations carefully sorry， you can choose the。

Which shortest path to augment along carefully and you'll get a better result。😡。

The best running time that you can hope for is。Squared log squared V。Don't ask me where the V went。

 I'm not really sure。嗯。But this is the fastest implementation of successive short paths runs in something like this a naive bound is。

Order VEB， where B is equal to the sum of the absolute values of the initial balances。

Every time you push along the shortest path， you improve the residual balance。嗯。This。

Is the version that you will use in Home 9。1。嗯。Or you can just say， oh， it's been cost flow。嗯。

And then one last thing I do want to mention， it'd be really nice if we could use Dexford's algorithm because then I wouldn't。

 you know， itd be a lot faster。😡，But I can't use Dyster algorithm when they're negative edges。

So there's a version of this algorithm where you do adjustments to the costs as you go。

So that in fact， all of the positive are positive and youd like to。

But that would take me another few minutes and I don't have that。

This is as much as I want to talk about flows， happy to answer questions up front or in office hours。

 otherwise we're done for the day， have a good weekend dress warm。我估计是。



![](img/52c280a15b3d54fd395e0e1593acb9c6_4.png)