# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p35 -35-5.2 Routing algorithms_ link state routing.zh_en -BV1UMtueiEaA_p35-

![](img/056273c64328ab312b635856ff765a43_0.png)

In this section， we're going to cover two routing algorithms that are widely used in practice in today's internet for computing a path from a given source to a given destination。

 The first is known as a linked state algorithm， the second is known as a distance vector algorithm。

 and although they share the same common goal of computing a shortest path or a least cost path。

 what we'll see is they differ very much in the way in which they actually compute these shortest paths。

The goal of any routing algorithm is to determine a good path or a good route or a good route between a source node and a destination node through a network of routers to understand routing algorithms。

 We're going to need to unpack that statement a little bit。 What do we mean by a path。

 What is a path through a network of routers。 And also， what does it mean to be good。

 What does it mean for a route to be good or one route to be better than another route。



![](img/056273c64328ab312b635856ff765a43_2.png)

So let's define a path as a sequence of routers that packages traverse from a given initial source host to the final destination host。

 We see a path here from this source host on the left to this destination host on the bottom right。

 passing through these five routers and implicit in a path being a sequence of routers is the sequence of links connecting the routers in the path。

 These links are going to be important， as we'll see in just a sec。And what do we mean by good。

 well could mean a lot of different things， maybe it's the least cost path。

 maybe it's the fastest path， maybe it's the least congested path。

 as we'll see the definition of cost and the definition of good。

 it's going to be left up to the network operator。And let me add here before we dive into routing algorithms that routing is definitely a top 10 networking challenge。



![](img/056273c64328ab312b635856ff765a43_4.png)

We'll use a graph abstraction， a concept that's familiar to any undergraduate computer science student who's taken a data structures course or an algorithms course to describe a routing algorithm。

 So a graph consists of a set of end nodes。 These might correspond to the routers within the network。

 These end nodes are connected by edges or links。

![](img/056273c64328ab312b635856ff765a43_6.png)

And each of these links has an associated cost， the link cost between nodes A and B denoted C sub A B。

 is the cost of the direct link connecting A and B。 For example。

 the cost between links W and Z here denoted C sub W Z is5。 the cost between x and Y for this link。

 the cost is1。Liinnk costs can be different in each direction or be the same as in this case here。

 And lastly， the link costs between two nodes that are not directly connected。

 It's going to be infinity。 For example， the link cost between U and Z。

 which are not directly connected is infinity。 Now， where do these costs come from。 Well。

 the routing algorithm or protocol doesn't really care。 but in practice。

 it's defined by the network operator。 The cost could be one， in which case。

 the least cost path algorithm is the shortest path or the cost could be inversely related to the bandwidth。

 the higher the bandwidth， the lower the cost， or the cost could be directly related to a links congestion level。

 their queuing delay。 the higher the congestion level， the higher the cost。

We're going to look at two routing algorithms in just a second。 but broadly。

 we can classify routing algorithms， any routing algorithm。

 according to whether they're global or decentralized and whether they're static or dynamic in a global algorithm。

 the algorithm has complete network wide information about network topology and all link costs。

 algorithms with global state information are sometimes referred to as link state algorithm。

 Since the algorithm has to be aware the cost of each and every link in the network。

 Dytra's algorithm is an example of a global link state algorithm。

 in a distributed or decentralized routing algorithm。

 The calculation of the leak cost path is carried out in an iterative。

 distributed manner by the routers。 No router has complete information about the cost of all network links。

 Instead， each router begins with the knowledge of a cost of its own directly attached links。

 So just its local neighborhood and then through an it。

Process of calculation and exchange of information with its immediately neighboring nodes。

 a node iteratively calculates the least cost path to a set of destinations。

The Bellman Ford algorithm will study is an example of a distributed algorithm also known as a distance vector algorithm since it iteratively computes a vector of currently known least cost to all network notes。

Routing algorithms can also be classified as static or dynamic or quasi static based on the timescale at which they operate and itery。

We're now ready to take a look at Dyketra's Link state routing algorithm and I know if you're a student who's taken an algorithms course like Compsi 311 here at the University of Massachusetts。

 know you've seen Dystra's algorithm， isn't it great to know that the algorithm that you learned in a theory course is actually being used in practice can almost guarantee you that the packets that are being transferred to you now as part of this video were almost certainly routed to you using Dketra's Li state routing algorithm。

Dyextra's link state routing algorithm is a centralized algorithm because it assumes that the complete network topology and all the link costs in the network is known to the node that's making the calculation。

 The algorithm itself is going to compute the least cost paths from one node。

 which we'll call the source node to all other nodes in the network。

 And you can see how this then gives rise to a forwarding table for that node。

 Dyextra's algorithm has this very nice property， It's iterative。 And after K iterations。

 we're going to know the least cost path to the closest or least cost K destinations。😊。

And here's a notation that we're going to use we'll let C sub AB be the direct link cost between nodes A and B if nodes A and B aren't connected。

 this cost is going to be infinity， so it's just the one hop direct link costs between two directly attached nodes。

D subA is the current estimate of the cost of the least cost path from the source to destination A。

 and as we'll see， D subA is going to be iteratively updated for all destinations A as the algorithm proceeds。

Pie of A is what's called the predecessor node along the path from the source to node A， and finally。

 n prime is the set of nodes whose least cost path is definitely known at this point in the calculation。



![](img/056273c64328ab312b635856ff765a43_8.png)

Now let's take a look at the pseudocode for diyketraizzling state routing algorithm The easy parts。

 the initialization What we're going to do is we're going to initialize N prime。

 remember N prime is the set of nodes whose least cost paths are known from the source node U we're going to initialize N prime to just contain the source node U and for all other nodes a within the network and if a is directly attached to you then D sub a is going to just equal that onehop cost the cost from node U to a Otherwise d sub a is going to be infinity that's the initialization easy enough Step 8 through 15 are the heart of the algorithm and this is just a loop what we're going to be doing in the loop each time we're going to find one node a we're going to add it to N prime and we're going to do an update and then we're going to iterate back again So this loop has basically two parts finding a node and then performing an update let's take a look at it now。

In steps 9 and 10， we're finding a node A that's not in N prime。

 So this is a node whose least cost path is not definitively known。 and we'll find the a。

 not an N prime， such that D sub a is a minimum。 And then we're going to add it to N prime。 remember。

 once the nodes added to N prime it's in there for good because we absolutely know the shortest path to get to a。

 So that's the identification step within the loop。 And then we've got an update step。

 which we see here in steps 11 and 12。 So the update step is the following。

 We're going to update D sub B for all nodes in the network B that are next to。

 that is to say adjacent directly connected to a and not yet in N prime。 And here's the update step。

 We're going to say D sub B is equal to the minimum。 Well， of the old value of D sub B。

 and a potential new cost。 the new potential cost is the minimum。Cos to get to a。

 remember this is now known。 plus the oneh cost to get from a to B。

 Once we perform this update step for all nodes B that are adjacent to a。

 we loop back and we'll find a new a and so we start off again at step 8 and we continue this looping process adding one node a into n prime each time until all the nodes in the network are in n prime。

 Probably the easiest way to understand dixtras algorithm is to take a look at an example。

 So let's do that next。 So on the bottom left here。

 you see the network on which we want to run dixtras algorithm。

 There are six nodes and the links shown here along with the associated link costs。

 The source node from which we're going to be computing all the least cost paths is node u on the far left end side here。

 Well let's start off with the initialization step since that's the easiest。

 remember the initialization step says for all nodes A if a is adjacent to this source node U。



![](img/056273c64328ab312b635856ff765a43_10.png)

Dab A is equal simply to the cost the onehop directlink cost of getting from U to A and so let's take a look here。

 we can see here that the direct neighbors of nodes U are VW and X。

 and so you can see on the first line here the cost to get to V is 2 cost to get to W。

 the direct cost to get to W is5 and the direct cost to get to x is1 and we filled in the predecessor nodes simply to say that the predecessor to nodes V W and X the shortest path from U is actually node U itself。

Notes Y and Z are initialized to infinity because they don't have a direct Onehop connection to source nodede U。

And so now it's time to jump into our first pass through the loop， Step 8，9 and 10。

 and in steps 9 and 10， we're going to do a node identification。

 We want to find the node a that's not yet in n prime such the D sub a， the distance。

 the cost to a is a minimum， and then we're going to add a into n prime。

 So taking a look at the table above。 we see the cost of v is 2。 the cost to W is5。

 the cost to x is1。 So x is the minimum here。 we're going to add node x into n prime。

 and you can see on the bottom left here on the graph we've drawn a little red arrow to show that to get from u to x。

 that's a direct connection there。 Now let's proceed on the update step。

 and this is shown in step 11 here。 and the way we're going to update D sub b shown here。

 the new value of d sub B is going to be the minimum of the old value of D sub B or the cost to get to a D sub a plus the direct cost to get from A to B again。

The logic here is that we want to update the cost to B knowing well。

 it can't be more than the old cost to B， but now we know the minimum cost to a and we know the direct cost from a to B。

 so we going to add those two together and that would give us the cost to B going through a and we're going to take the minimum of those two values so you can see here shown in gray we update the values of d sub v d sub w and d sub y and as you can see the new costs for dw and dy are now less the cost to get to W has gone down from5 to4 and the cost to get to y has gone down from infinity now down to2 so we're going to update those values and the table above and then iterate back to the beginning of the loop。

Well， now we've completed two rows in the table and we're back at the beginning of the loop again。

 So we're at the identification step。 Let's find the node a that's not yet in n prime that has a minimum value of D sub a。

 Looking at the table above。 we can see that node Y。

 which has a cost of2 and node V also has a cost of2。 We can break that tie arbitrarily。

 Let's choose。 So we'll add y into the set N prime。Now we move on to the update step。

 given that we've added Y into a prime。 this is step 11。

 What we want to do again here is we want to update D sub B for all B that are adjacent to Y in this case and not yet in N prime。

 You see the update formula here。 Well， let's take a look at Y， we just added Y in。

 and Y has two neighbors that are not yet in N prime。 That's W and Z。

 So we're going to update the values of W and Z as shown here。

And you can see that the new cost to W is now decreased from 4 to 3。

 and the new cost to get to Z has decreased from infinity to 4。 So we update the table above。

 and we're ready to iterate again。 Well， we're entering the loop again at step 8 for the third time。

 And again， we start with an identification step。 Let's find the node A that's not an n prime yet。

 such that D sub a is a minimum。 And as we scan across the row that we computed in step 2。

 we see that V is now a minimum at a cost of 2。 So let's add V into the set and prime。

Now that we've done the identification step， the next step is going to be the update step again。

 and now we want to update D sub B for all nodes that are adjacent to this new node V that we just added into N prime。

 You see the update formula there。 let's take a look at node V down here that we just added in。

 Well what are the neighbors that are not yet in n prime that are directly attached to V。 Well。

 use in it already X is in it already。 but W is not in it。

 so we update W as shown in the step here shown in gray。

 and we see that the cost to W hasn't changed。 So we're all done with the update step let's loop back again。

 And once we enter the loop again， we first do the identification let's find a node not in n prime such that D sub as a minimum。

 Well， there's only two nodes left that aren't in N prime W and Z W has the smaller cost of3 rather than Z's cost of4。

 So we're going add W into N。Prime we're going to perform an update step once again you can see the update step Well the only node whose cost needs to be updated is Z so you see the step for updating the cost of Z the value of D sub Z doesn't change so table remains the same we loop back again the step8 enter the identification step and we'll find a node A not in n prime such that D sub is a minimum well there's only one node left thats Z so we'll add Z and N prime and now there are no nodes left so there's no update step we exit the algorithm and we're all done。

And now if you take a look at the network on the bottom lefthand side。

 you can see the least cost roing tree from node U to all other nodes in the network from this。

 we're able to recover the forwarding table， specifically from U， if we want to get to destination V。

 we go across this link here with a direct cost of2。

 otherwise if we want to get to X to Y to W or to Z， we're going to forward a packet to X。

 because x is the next hop node on the least cost path from U to all of the destinations X Y W and Z。



![](img/056273c64328ab312b635856ff765a43_12.png)

Well， I hope that discussion of Dytra's algorithm has given you a good idea of how a centralized Li state algorithm works。

 And let's wrap up our discussion here of Dytra's algorithm with a discussion its complexity。

 its computational complexity， its message complexity。

 as well as a discussion of a possible pathology。 Now， to think about the computational complexity。

 note that we need to pass through that loop from line 6 through 11 N times。

 And each time we go through that loop。 We have to make a worse case n comparisons。

 So that will give us an order N squared computational complexity。😊。



![](img/056273c64328ab312b635856ff765a43_14.png)

Let's analyze the message complexity of Dykstra's algorithm from the point of view。

 the number of messages needed to disseminate linked state information。

Each router needs to broadcast its link state information to end other routers。

 and there are broadcast algorithms， which are really pretty interesting that only require O of N link crossings to disseminate a broadcast message from one source to N other nodes。

 recalling that there are now in sources。 the overall message complexity to disseminate link state is therefore order n squared。

And before wrapping up our discussion at the link state algorithm。

 let's consider a really interesting pathology that can arise。 We haven't said much about link costs。

 but imagine now that link costs are dynamic， reflecting the amount of load on the link。 for example。

 the higher the load， the higher the costs。 Some of the earliest routing algorithms in the apant used just this kind of short term load dependent link costs。

We'll take a look at the example below of a simple network topology where link costs are equal to the load carried on the link。

 Note that the costs are now different in each direction on a link。

 let's assume that nodes B C and D each one route traffic only to node A and B and D sends a unit of load destined to a and C sends a small amount of load epsilon to A and suppose the initial routing as is shown here the far left When the link state algorithms next run。

 nodes C determines based on the link loads and therefore fourth costs that the counterclockwise path to a now has a cost of1 while the counterclockwise path to A which it have been using has a cost of one plus2 epsilon Now Cs least cost path to a is clockwise。

 Similarlyly B determines that its new least cost path to A is also clockwise resulting in the routing shown in the second figure when the link state algorithms next run nodes B C and D。

All detect now a zero cost path to a in the counterclockwise direction and all route their traffic to the counterclockwise routes。

 The next time the algorithms run B C and D allll see zero costs for clockwise routing therefore route their traffic clockwise and so on。

 Well， this was just a toy scenario， but it reflects the fact that dynamic routing algorithms can be very subtle。

 and it was perhaps because of such issues that later routing algorithms tended to shy away from defining costs based on short termm congestion or load levels。



![](img/056273c64328ab312b635856ff765a43_16.png)

Well， that wraps up our discussion of Dykestra's centralized Li state routing algorithm。

 but we're not done with routing algorithms yet， because coming up next。

 we're going to take a look at a very different kind of algorithm。

 Take a look at a distributed Belllman Ford routing algorithm。



![](img/056273c64328ab312b635856ff765a43_18.png)