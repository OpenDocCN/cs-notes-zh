# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p36 -36-5.2-2 Bellman Ford Distance Vector Routing (updated).zh_en -BV1UMtueiEaA_p36-

Having now covered Dyktra's Li state routing algorithm。

 we're ready to dive down to the second broad class of routing algorithms， Take a look。

Dributed Belman Ford algorithm。 And this is really just， it's a beautiful algorithm。

 It's the best example I know of how simple local， intuitive distributed calculations can be used to compute the same result。

 In this case， least cost pay as a centralized algorithm。 I think you're really going to like this。😊。

The distance vector algorithm for computing least cost paths is based on what's known as the Belman Ford equation shown here。

 And while the equation itself might look a little bit daunting， it's really pretty intuitive。

The Belman Ford equation expresses the notion that if I want a minimum cost from source X to destination Y。

 then that path must have one of x's neighbors， say V as a first hop。

 So I'll sum the cost of getting from source X to neighbor V plus the cost of then getting from neighbor V to destination Y。

 This is x's cost of getting to destination Y through neighbor V。

 And then I'll take the minimum cost path over all neighbors V。

 Since x's minimum cost path must pass through one of its neighbors V。That's it。

 that's the Bellman Ford equation。Well， probably the best way to understand Belmond Ford is to take a look at an example。

 So let's do that in the context of the network， which you'll recognize we're going to look at a source node U and a destination node Z。

 And notice that U has three neighbors， V， X and W。 And here's what the neighbors know。

 neighborighb V knows that it can reach destination Z with a cost of5。

 neighbor X knows that it can reach destination Z with a cost of3 and neighbor W knows that it can reach destination Z with a cost of three。

 So that's what the neighbors know。 The neighbors are going to communicate this information back to U。

 What is this going to mean for you。For this example。

 the Belman Ford equation says that the minimum cost path from U to Z is going to be the minimum of three quantities。

 The cost of getting from source U to neighbor v plus the cost of getting from neighbor v to destination Z。

 the cost of getting from U to neighbor X plus the cost of getting from X to Z and the cost of getting from U to W plus the cost of getting from W to Z。

If you plug in the numbers here， you'll find that the minimum cost to get from U to z is V neighbor x and at a cost of4 Well the Belman Ford equation expresses a relationship among the distance vectors in neighboring nodes。

 but of course we still need to compute these distance vectors。

 but the way to do that is naturally expressed by the form the relationship between distance vectors and neighboring nodes function how we compute these distance vectors is going to follow form。

And here are the key ideas behind the distance vector algorithm From time to time。

 each node is going to send its own distance vector estimate to its neighbors。

 And when a node X receives a new distance vector estimate from one of its neighbors。

 It's going to update its own distance vector using the Belman Ford equation。

 That is node X is going to say， well， for each node Y in the network。

 I'm going to compute my distance X to Y to be the minimum across all of my neighbors V。

 the cost of getting from me to V。 and then v's cost of getting from itself to Y。

The distributed Belman Ford algorithm has three steps。

 and all nodes of the network are going to perform the same three steps。 So if I'm a node。

 the first step is， I'm going to wait。 I'm going to wait till either I receive a distance vector from one of my directly attached neighbors。

 or I'm going to wait for a local link cost change 2， after I receive one of these events。

 I'm going to run the Belman Ford calculation for all destinations in the network using the most recently received distance vectors from my neighbors。

3， if my own distance vector changes as a result of the Belman Ford calculations。

 I'm going to send my new distance vector to each of my neighbors。 and that's it。

 then I'm going to iterate again。 Well， this algorithm could hardly be simpler。

 and believe it or not。 And hopefully you'll believe it when we're done。

 this distributed algorithm will result in all nodes。

 having iteratively computed a distance vector that will tell them the least cost path to。😊。

Every other node in the network and the neighbor to route to to start a packet along that minimum cost path to a given destination and note that unlike the Li state algorithm。

 a node doesn't know the entire path from source to destination。

 but in the end it doesn't really need to does it， it just needs to know which neighbor to forward a packet to in order to reach a given destination along the minimum cost path。

While the distance vector algorithm has some amazing properties。 It's iterative and asynchronous。

 Each iteration is caused by either a local link cost change or the receipt of a distance vector update message from a neighbor。

 And we've talked about this as if it's synchronous that all nodes are exchanging distance vector in lockstep。

 but in fact， notes can iterate asynchronously from each other and with very different iteration speeds will still converge。

 The algorithm is also distributed and itself stopping。

 Each node notifies its neighbor only when its distance vector changes。

 neighbors then notify their neighbors only if necessary。

 And if no change is sent or no notification is received， then no actions need to be taken。😊，Well。

 that's it for describing the distance vector algorithm。 It's pretty simple algorithm， isns't it。

 Just three steps waiting to receive the distance vector from a neighbor。

 performing a distance vector calculation。 And then if my own distance。

 my local distance vector has changed， I'm going to send my local distance vector to all of my immediately attached neighbors。

 That's it。Let's now take a look at Belman Ford in action。

 And let's start with a high level view of the overall structure of a computation。

 Here's a simple9 node grid network that we'll use as our example。 It's pretty symmetric。

 except there's a missing link between C N F。 And this link here from A to B has a cost of8。

 While all other links have a cost of one。At t equals0。

 all nodes have their distance vector estimates to their directly link connected neighbors only Here you can see the distance vector in node A。

 Its Dv entry for destination B has a cost of a and its DV entry for destination D a cost of one。

 note that these are just estimates of the least cost paths even to direct neighbors。

 Since as we can see here there's a three hop path cost3 to get from a to B。

 which will found to be cheaper than this initial cost of8 via the direct link between A and B。

 So at t equals0， let's assume that all nodes have initialized their distance vectors and after doing so。

 send their distance vectors to their immediate neighbors。 At t equals1。

 all nodes receive distance vectors from their neighbors compute their local distance vector。

 And if any component of their distance vectors changed。

 they'll send their new local distance vector to their neighbors。

 at t equals 2 nodes receive distance vectors from their。

Compute their local distance vector and if any component of their distance vectors changed again。

 they'll send their new local distance vector to their neighbors and so on。

And let me stress here that we've described the iterative process here as if all nodes are operating in link step。

 It's easier to understand it that way。 But， in fact， nodes can iterate at different speeds。

 and this will still work。Well， the short animation here has shown you a little bit about the overall structure of the distributed Belman Ford calculations。

 but we still need to look at the local computation that's at the heart of the algorithm When we take the individual distance vectors from our neighbors。

 We run the Belman Ford equation over and compute our new local distributed distance vector。

 Let's take a look at this local computation。Let's recall that at t equals 0。

 all nodes have computed their local distance vectors， which you can see here。

 Let's take a look at B's distance vector。 B knows that it can get to a directly with a cost of A to C directly with a cost of one and to E directly with a cost of1。

 This is B's initial distance vector。 The distance vectors of A， C and E are also shown here。

After computing the initial distance vectors， all nodes send their initial distance vectors to their directly attached neighbors only。

 and let's suppose that t equals 1， B now receives these distance vectors from its neighbors。

And here are the bellman Ford calculations carried out by B at T equals1 following B's receipt of the initial distance vectors from its neighbors A。

 E and C。 Remember that at each step when a new distance vectors received。

 a node will recalculate its own local distance vector using this newly received information。

 Let's take a look at a couple of b's calculations。

 Let's first look at how B calculates its distance to A。 B says， well。

 my distance to a is the minimum of three things。 my direct cost to a plus a's distance to itself。

 which is0， my direct cost to C plus C's cost to a or my direct cost to E and E's cost to a。

 That's the minimum of8 infinity infinity， which is8。

 So there's no change here in B's distance vector with respect to A。

 But now let's take a look at B's new distance table entry for D。 recall that at t equals 0。

 B had an infinite cost to get to D。😊，Now it recomputes that cost as follows B says， well。

 my cost to get to D is going to be the minimum of three things。

 My cost to get from myself B to a plus A's cost to get to D My cost to get from B to C and C's cost to D My cost to get to E plus E's cost to D if you plug in the values that becomes the minimum of92 and infinity which is2。

 and you can see that B similarly recomputes new Dv entries for destinations F and H as well。

 And so here's the new overall distance vector computed by B Note that compared with B's previous distance vector。

 there are three new lower cost entries for destinations D F and H this new distance vector then becomes B's current distance vector。

Now， let's take a look at node C again at time T equals1。

 and after C has received B's initial distance vector。

 Let's see how C recomputes its own distance vector。 But before doing so。

 let's step back and take a look at the picture here and think intuitively about what B is telling C by B sending its initial distance vector。

 Well， B saying， hey， look， I can reach a at a cost of a， and I can reach E at a cost of1。 Well。

 B is C's neighbor and C knows if that B can reach E with a cost of1 and C knows that it can reach B with a cost of1。

 then C knows that it can reach E with a cost of2 V B。

 And this is precisely the beman forward equation。 That's the intuition behind Belman For。

 It's not clear。 Well， hit the rewind button and listen to that explanation again。

 And so here are C's calculations of its new distance。😊。

let's focus on C's DV entry to destination E here C's calculation simple since it's only got one neighbor C says for me to get to E。

 I can get to B with a cost of one and B tells me that if B can get to E with a cost of1 so my cost C's cost to get to E via B is one plus one equals2 Well you're probably thinking it's getting a little tedious to go through one example after another。

But you might want to do a few calculations for yourself just to test your understanding。

 For example， consider the scenario here where node E is receiving distance vector tables from its neighbors B。

 D， H and F。 What's the new distance vector computed by node E， which entries have changed。

The Belman Ford algorithm can be thought of as diffusing information throughout the network to appreciate this notion of diffusion。

 Let's take a look at node C and ask ourselves the question。

 what do other nodes in the network know about the state of node C。

 say at t equals 0 and when do they learn this information。At t equals 0。

 C hasn't communicated with anybody， so no other nodes have information about node C At T equals1。

 C's state at T equals0 has propagated over to B by the exchange of distance vectors。

 so at t equals1， C' state at t equals 0 can influence the calculations at B at T equals1。

At t equals2， information from node C at t equals0 has propagated further to nodes E and to nodes A。

 and imagine your node E at t equals2， you're seeing the first influence of the state of node C at t equals zero now at t equals two two time units later。

This notion of information propagation speed。 It's almost like looking at a star at night。

 The light you're seeing now is omted by that star many light years ago。

 And so it is with information propagation in a network。

 The cost that E is seeing at t equals 2 regarding C reflects C state at t equals 0。

 even though E receiving this information at t equals 2。 Well， continuing on， t equals 3。

 C state at t equals 0 can influence distance vector computations up to3 hops away。

 That's at notes D F and H。 And finally， at T equals 4。

 C state at t equals 0 can influence distance vector computations up to 4 hops away。 In this case。

 at node G and I as well。 And note that it's taken four time steps。

 the diameter of the network for information to propagate from one edge of the network to the other。

😊，So far， we've only looked at the initial distance vector calculation。

 After some number of iterations， the computational process will havequied。 Remember。

 if there are no changes in a local distance vector。

 I'm not going to send out distance vector updates to my neighbors。 So eventually。

 when there are no local changes computed anymore more。 The algorithm will have converged。

 there'll be no more distance vectors being exchanged。 Now。

 let's take a look at what happens if there are link cost changes because our distance vector algorithm can already accommodate that。

 and the steps are the same。 A link cost changes noted。 I'm a local node。 I note that local change。

 I recompute my local distance vector using the new local link costs。

 as well as the old distance vectors that I have for my neighbors。

 And if my local distance vector is changed once again， I just send it out to my local neighbors。

 So the algorithms pretty much unchanged。 So let's now take a look at an example of how link cost changes propagate。

Using the network shown up here on the right and let's take the point of view of node Y who sees the XY link cost change from 4 to 1 it goes down so at ts0。

 let's say y detect this link cost change updates its distance vector to note that now it's got a new cost to x of1 and sends its new distance vector to its neighbors。

At T 1， Z receives this updated distance vector from Y updates its own distance vector。

 Comp its new least cost path to x as 2。 And now， since z's distance vectors changed。

 Z sends its distance vector to its neighbors X and Y at T2。

 Y receives Z's updated distance vector recalculates its own distance vector。 And in this case。

 y' is least costs in its distance vector don't change。

 And so y doesn't send anything back out to Z or X。 the algorithmquieses and is done。

 So just after two iterations， the recomputation of the distance vector here concludes。

 And we'll note that the network wide recomputation of the distance vectors happen pretty quickly for this link cost change example。

 The exact amount of time needed， was related to the diameter of the network， As you might imagine。

 And that's as fast as it could happen。 Given our earlier， starlight analogy。

 And there's a saying in networking that good news travels fast。😊。

When a link weight goes down in Belmond Ford， all nodes recompute their final distance vectors relatively quickly。

 but what happens if link costs go up？In this example here。

 the cost of the link from x to y now goes to 60。 And you'll want to think about what happens at this example。

 But basically， this is what happens when the link cost goes to 60， Y says， a oh。

 I better start routing through Z since Z has advertised a path to me with a cost of 5 to x。

 giving me an overall cost of 6。 Y informs Z of its y' is new cost to x via a distance vector update。

 Well， Z then says this update and says golly， if y' is cost to x is 6。

 then my cost to x is now 7 through Y and forms Y。Y says， u oh， if z's cost is 7 to get to x。

 then my cost is going to be 8。 Z then says， well， if y's cost to get to x is 8。

 then mine is 9 and so on。 This is what's known as the count to infinity problem。

 and think about what would have happened if the link costs had changed to 6 million instead of just 60。

 Well， be a lot of iterations。 Of course， their workarounds to the count to infinity problem。

 But I think the larger lesson here is that as beautiful and elegant as distributed algorithms are。

 their operations and their pathologies can often be subtle。Well。

 let's wrap up our discussion of routing algorithms with comparison of link state and distance vector algorithms。

 And let's start off with message complexity。 We saw earlier that the message complexity to do link state dissemination order n squared for the link state algorithm。

 for distance vector， we learn that it takes the order the diameter of the network potentially order n for information to propagate from one end of the network to the other。

 And we saw that at each step， a node may potentially need to communicate with each of its neighbors。

 terms of speed of convergence。 We saw that link state is order n squared computational algorithm order n squared communication algorithm。

 And we saw that there can be oscillations。 case of distance vector。

 We saw that convergence times again can vary and there can actually be routing loops while the algorithms converge。

 And lastly， let's think about what can happen in a link state or a distance vector algorithm if a router malfunction。

😊，Or is compromised Well， under link state， a router can advertise incorrect link costs。

 but each router computes its own routing and forwarding tables so failures rather localized under Li state under distance vector。

 a router can advertise an incorrect path cost for example， a router could say。

 hey I've got a really low path cost to everywhere in the internet This is known as black holeing Since each router's distance vector is used by others。

 errors can then propagate through the network as additional routers advertise their new distance vector and this type of black hole routing failures actually occurred in the internet when a small ISP advertised。

 hey I've got a zero cost pass to a major ISP think that ISP was AT and T when this ISP wasn't really connected to that major ISP and hey what network can pass up a zero path cost to a major destination network and so many other networks in the internet who wanted to route traffic。

T sent their traffic to this small ISP where it was blackhold Now imagine your AT&T and you're saying。

 hey， why am I no longer receiving traffic from a good portion of the internet anymore Well。

 the answer was that traffic's been black hole in a small ISP instead due to a misconfigured router in that ISP。

Well that wraps up our discussion of routing algorithms， Dytra centralized Link state algorithm。

 the distributed Bellman Ford algorithm， in the next two sections we're going to cover the embodiment of these routing algorithms in internet routing protocols。

 the Open shortest path first OSPF routing protocol and the BGP Border gateway protocol。

 I think you'll enjoy them。

![](img/4357897f6f32e834d80f58e7d74792b3_1.png)

![](img/4357897f6f32e834d80f58e7d74792b3_2.png)