# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P168：40_04_02_匹配、流量与布雷斯悖论（可选）.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

One key reason why the stable matching problem admits an efficient solution is that you can。

 in principle， Mat any node to any other node on the opposite side。 Sure。

 the nodes have preferences and might not want to be matched to certain nodes。

 but there's no hard constraints preventing certain pairings When you do have such hard constraints。

 We wind up with the classical bipartite matching problem。



![](img/a270bb149163354095fd14766f438a15_1.png)

So the input to the bipartite matching problem is a bipartite graph， so remember what that means。

 that means you can take the vertices and put them into two groups。

 let's call one of them capital U the other one capital V。

 and every single edge has exactly one endpoint in each of the two groups。

 put differently there exists a cut of the graph that cuts every single edge。

The goal is to compute the matching。 Remember， a matching is a subset of edges that are pairwise disjoint。

 No pair of edges can overlap at an endpoint and to compute the matching that has the largest possible size。

So for example， in this pink graph on the right， there are various matchings consisting of three edges。

 and I'll leave it for you to check that there is no perfect matching。

 there's no way to have a matching of four edges。So bipartitech matching is a totally fundamental problem。

 there are constraints on which objects you can pair up and you want to pair up as many objects as possible。

I'm happy to report that the maximum matching problem is solvable in polynomial time。 In fact。

 it's polytimeslvable not just in bipartite graphs， which is what I'm discussing here。

 but even in general nonbipartite graphs。 So in nonbipartite graphs you have to work pretty hard to solve the problem in polynomial time。

 the bipartite case that I'm talking about here reduces easily to another problem you should know about called the maximum flow problem。

So I'll now move on to describing the maximum flow problem。

 I'll leave it as a good exercise for you to do why bipartite matching reduces to maximum flow。

You can study maximum flow in either undirected or directed graphs， the directed graph cases。

 in some sense， the more general one， let me state that here。So the input is a directed graph。

 one special vertex is called the source vertex S， and another vertex T is called the sync vertex。

Finally， each E E has a capacity used toB， which is the maximum amount of flow or traffic that the edge can accommodate。

Informally， the goal is to push as much stuff as possible from the source vertex S to the sync vertex T。

 respecting the capacities of the various lengths。 So you should think as examples as electrical current being generated from S and flowing to T。

 or you could think of water being injected into the network at S flowing through these edges representing pipes and then being drained out at T。

 The point is， you have conservation of flow at every vertex other than S and T。

 That is the amount of stuff coming in has to equal the amount of stuff coming out。

 except for S where stuff gets generated and a T where stuff gets drained。As a simple example。

 suppose in this pink network on the rights， I give each edge a capacity of one。

The maximum amount of stuff you can push from S to T in this network is two units。

 the way to do that is you send one unit of stuff over the top path from S to V to T。

 and you send a second union on the bottom path using W as an intermediate stop。

So I'm happy to report that the maximum flow problem can be solved exactly in polynomial time。

 there are many ways of doing it， many different cool algorithms that solve the max flow problem。

 but the simplest ways are in effect greedy algorithms where you route flow one path at a time。

One thing worth pointing out is the most obvious greedy approach to the maximum flow problem doesn't work。

 The most obvious thing to do is to just find a path where there's residual capacity along every edge。

 Send flow along that path， and repeat。So the subopity of the naive greedy algorithm is already evident in the For vertex network that I've shown you on this slide。

Suppose in the first iteration to find your first path to push flow along。

 you wind up choosing the path that goes from S to V to W to T。 So that has three edges on it。

 All of those edges have capacity 1。 So you're free to push one unit of flow along this zigzag path。

 But if you do that， you've now blocked up the other paths as well。 the Svt path and the Swt path。

 there is no way to send further flow along any of those three paths。

 So this naive greedy algorithm only computed a flow of value 1。

 whereas we know the max flow value is equal to2。 So instead。

 you have to allow a more generous notion of an augmenting path where you can send flow in reverse。

 in effect， undoing augmentations of previous iterations。

 But with this more generous definition of augmenting paths。

 the resulting greedy algorithm is indeed guaranteed to compute a maximum flow。Moreover。

 if you're smart about which augmenting path you use in each iteration of your greedy algorithm。

 you can prove a running time bound， which is polynomial。

 There's also a number of nonuging path based polynomial time algorithms for the maximum flow problem as well。

 In fact， this diversity of solutions for the maximum flow problem makes it a little hard for me to give you a succinct bottom line about what running time you can get for this problem。

 But roughly speaking， we don't have algorithms which are near linear time。

 but we have plenty of algorithms which are not much worse than that。 say in the quadratic regime。

 Think about， you know， Belman Ford like running time bounds of M times N。

 And a lot of these algorithms do quite a bit better than quadratic in practice。

And one thing that's cool is that even though this maximum flow problem is totally classical。

 these augmenting path algorithms were first studied in the 1950s by Ford and Fson。

 even in the 21st century， we've been seeing some really nice new developments with maximum flow。

 cool new algorithms based on things like either random sampling or connections to electrical networks。

😊，In some applications of flow networks， you want to think about flows as not being computed by some centralized algorithm。

 but rather as arising from the behavior of a number of participants。 think， for example。

 when you get in a car and drive from， say， home to work。

 Nobodys telling you which route you have to take， rather you choose what route you want to take from home to work based on your own preferences。

 For example， perhaps you take the shortest route available。

Such self under behavior in networks has been a major research topic in the 21st century。

 let me just show you one cute cocktail party ready example of that called Brace's Paradox。

So imagine we have a flow network and again you might want to think about road traffic as being a simple example。

 let's focus on a case where a bunch of morning commuters are leaving a common suburb represented by a vertex S destined for some nearby city。

 let's call it a vertex T， all leaving at roughly the same time and all of them get to pick。

 whichever routes they want through the network to get from S to T。

So to better represent issues in transportation networks。

 let's instead of thinking of links as having capacities。

 let's think of them as having delay functions。 So for each edge。

 there's going to be a function which describes as a function of how much traffic uses that edge。

 what is the resulting travel time that all of that traffic endures。

 So as you know from your own experiences， the more congested a road is。

 the longer it takes you to get across that road。So as an illustration in this pink network on the right。

 let's give two of the roads， the constant delay function always equal to one。

 So these would be roads that have， in effect， an infinite number of lanes。

 but they're also pretty long。 So no matter how much traffic is using it。

 it always takes you an hour to traverse one of these two roads。

The other two roads by contrast we're going to have the travel time increased with the congestion and just to keep things really simple。

 let's use the identity function so that if 100% of the traffic uses one of these roads。

 then it takes an hour if 50% of the traffic uses one of these roads。

 all of that traffic takes a half an hour to traverse the road and so on。

So let's now look at this pink network。 Remember， we have this one unit of selfish traffic。

 which is representing hundreds or thousands of drivers that are picking their own routes from S to T。

 Let's assume the drivers just want to get to T as quickly as possible。

 They just want to minimize their travel time。 And then the question is which flow is going to arise from this aggregate self interested behavior。

Well， the two routes are exactly the same。 Each one has one road that always takes an hour。

 and it has and also has a second road， which takes time proportional in hours to the fraction of traffic that uses it。

 So because of the symmetry， once things settle down into a steady state。

 we expect half of the traffic to be using the top path。

 half of the traffic to be using the bottom path with the 50，50 split of the traffic。

 each of the two routes takes an hour and a half overall。



![](img/a270bb149163354095fd14766f438a15_3.png)

Now， I mentioned something called braces paradox。 So what's the paradox。 Well。

 imagine that we view this hour and a half toute time as totally unacceptable。 Moreover。

 imagine that we have a new technology。 Someone just invented a teleportation device And we want to install it in this network so that people can get to their workplace faster than before。

 So let's install one of these teleporters at the vertex V to allow people to travel instantaneously to the vertex W。

 So we' represent that by adding to this pink network a fifth length from V to W with the constant delay function always equal to zero。

😊，So what are the ramifications of adding this teleportation device allowing you to go from V to W instantaneously。

 Well， suppose you were one of these drivers stuck with your current commuteton of an hour and a half。

 No surprise you would want to ditch your old route to make use of this new teleporter。

 So you would want to switch from your old path， whether it was S V T or S W T to the new zigzag path。

 S V W T。 It's looking like then it would youd get to work in only an hour。

 You'd spend half an hour on the edge S V instantaneous teleportation and another half an hour on the edge W T。

😊，But here's the catch。Not only are you going to switch your path to use the teleportation device。

 so are the thousands of other drivers， so in the new steady state after we've augmented the network with this teleportation device。

 everybody is going to be using the zigzag path， S VWT。

And now that everybody's doing exactly the same thing。 all of the traffic uses the edge S V。

 driving its travel time up to an hour。 Everybody's using the edge W T。

 driving its travel time up to an hour。 So now， despite the fact we've made the network intuitively only better in the unique。

 new， steady state， assuming everybody selfishly chooses their minimum travel time path。

 The commute time has actually gotten worse。 It's jumped from an hour and a half for everybody to two hours for everybody。

 That is braces paradox improvements to networks where you have selfish users can make the outcome worse for everybody。

Wow， so that's brace's paradox discovered by you guessed it。 Bce。

 a German mathematician back in 1968。 Ammaze your friends and colleagues at the next nerdy cocktail party。

 you find yourself at。 Actually， theres a physical realization of braces paradox you might find more useful for that purpose。

 Here's the idea。 The idea is you're going to take as ingredients。 Strs and springs。

 The strings are meant to perform the function of the constant delay functions。 Strings， of course。

 being inelastic objects。 The length of a string is independent of the amount of force you apply。

 Springs， on the other hand， are elasticastic。 That is their length is proportional to the force applied to the spring。

 So those play a role analogous to the linear delay functions in this network。

 So braces paradox shows that there exists a way to wire strings and springs together。

 and then hang this contraption of strings and springs from a fixed base。

 say the underside of a table。 You hang awaits from the bottom of these strings and springs。 So that。

😊，Sttches it out Now， in general， when you have a contraption that's holding some weight and you start chop。

 you take a pair of scissors and you cut things off from the middle of this contraption。

 you expect the contraption to be weaker and therefore the weight is going to sag further toward the ground。

 But in the same way， brace's paradox shows that removing a supposedly helpful teleportation device from a network can actually improve。

 can actually shorten selfish commute times。 That shows that cutting out ta strings from the middle of the contraption can actually get a weight to levitate further off of the ground。

 And this is not just hypothetical。 Students in my classes have built these strings and strings contraptions and have demonstrated this levitation。

 If you search YouTube， I'll bet you can find some videos Try it at home。

