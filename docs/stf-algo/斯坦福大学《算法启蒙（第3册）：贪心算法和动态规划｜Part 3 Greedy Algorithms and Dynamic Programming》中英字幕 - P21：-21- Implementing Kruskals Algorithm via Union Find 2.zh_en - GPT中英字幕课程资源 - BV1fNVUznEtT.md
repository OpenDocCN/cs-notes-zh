# 斯坦福大学《算法启蒙（第3册）：贪心算法和动态规划｜Part 3 Greedy Algorithms and Dynamic Programming》中英字幕 - P21：-21- Implementing Kruskals Algorithm via Union Find 2.zh_en - GPT中英字幕课程资源 - BV1fNVUznEtT

So let me now introduce you to the Union Find data structure， let's not lose sight of our goal。

 our goal is to be able to check for cycles in Ksco's algorithm in Conant time。



![](img/83022c2614612cc4f91a6fcbbce8dc53_1.png)

![](img/83022c2614612cc4f91a6fcbbce8dc53_2.png)

So the first and most basic idea behind this union fine data structure implementation is we're going to maintain a linked structure for each group that is for each connected component with respect to the edges Queesquicle has chosen thus far by a linked structure。

 I just mean each vertex of the graph is going to have an extra pointer field。In addition。

 with each group， with each kinetic component， we're going to designate one vertex and we don't care which one。

 just some vertex from this kinetic component as the leader vertex of that component。Al right。

 so what is the point of these extra pointers at each vertex and what is the point of having these leaders Well a key invariant that we're going to maintain is that a given vertex with its extra pointer points to the leader vertex of its connected component。

So for example， maybe we have two different connected components with three vertices。

 each one containing the vertices， Uv and W， another containing the vertices X， Y， and Z。

Any of these three vertices could be the leader of each of these two components。

 so perhaps u happens to be the leader vertex of the first component and x happens to be the leader vertex of the second component。

And then the invariant just says every vertex should be pointing to the leader of its component。

 so V and W should be pointing to u， U has its own pointer it should be pointing to itself。

 similarly in the second component x is pointing to itself， y points to x and z also points to x。

So in blue here are the actual edges of the graph and in green。

 there are these sort of extra edge pointers that we've invented where everybody's pointing back to the leader of their component。

And so one very simple thing in this setup， which turns out to be a good idea is each component is in effect inheriting the name of its leader vertex。

 so we refer to a group， we refer to a component via the object via the vertex。

 who happens to be the representative， who happens to be the leader。

And what's kind of amazing is even just this very simple scaffolding on the kinetic components is enough to have constant time cycle checks provided the invariant is satisfied。

How do we do that so remember that checking if adding the edge U V is going to create a cycle boils down to checking whether there's already a path between U and V well there's already a path between U and V if and only if they're in the same kinetic component。

 given two vertices U and V how do we know if they're in the same connected component we just follow the respective leader pointers and we see if we get to the same place if they're in the same component we get the same leader if they're in different components we get different lit so checking for a cycle just involves for each of you and V comparing a quality of leader pointers that is clearly constant time。

More generally， the way you implement the find operation for this flavor of disjoint union data structure is you simply return the leader pointer of the object that you were handed so if you're given a vertex you just follow the leader pointer or that vertex and you return wherever you wind up。

So that's pretty excellent as long as in this simple data structure。

 the invariant satisfied we have our desired implementation of constant time cycle checks。

 but and certainly this is a recurring theme in our data structure discussions。

 whenever you have a data structure and it needs to maintain an invariant。

 whenever you do an operation that changes the data structure so like in this case when you do a union fusing two groups together。

 you have to worry well does the invariant get destroyed when you do that operation and if it does。

 how are you going to restore the invariant without doing undo work。

So in the present context of Crusco's algorithm， here's how this plays out。

 So we're happily doing our constant time cycle checks whenever an edge creates a cycle。

 we don't do anything。 we skip the edge， we don't change your data structure。 we move on。

 The issue is when we have a new edge and it doesn't create a cycle， our cycle check fails。

 Now Crusco's algorithm dictates that we add this edge into the set capital T that we're building and that  fuses two connect to components together。

 But remember we have this invariant， every vertex should point to the leader of its component。

 Well if we had component A and we had component B。

 they are both pointing to the leader vertex of their respective components。

 Now when these components fuse into one， we've got to do some updating of leader pointers in particular。

 there used to be two liters， now there has to be just one and we have to rewire the leader pointers to restore the invariant。

So to make sure you're clear on this important problem， let me ask you the following question。

 so consider the case when at some point inesco's algorithm a new edge is added into connected components fuse into one。

 now to restore the invariant you have to do some leader pointer updates in the worst case。

 asymptotically how many leader pointer updates might be required in order to restore the invariant。

So the answer to this question somewhat alarmingly is the third answer。

 So it might require a linear number in the number of vertices n。

Poiner updates to restore the invariant。 Maybe one easy way to see that is just imagine the very last edge that crustesco is going to add in the set T。

 the one which fuses the final two connected components down into one for all you know you know those two components have exactly the same size。

 They have n over two vertices each。 you're going down from two leader pointers to one。

 one of those sets of n over two vertices are going to have to inherit the leader pointers from the other side。

 So one of the two sets is going to have to have n over two vertices get their leader pointer updated。



![](img/83022c2614612cc4f91a6fcbbce8dc53_4.png)

So that's a bummer we're sort of hoping for a near linear time bound。

 but if every each one of our linear number of edge editions might trigger a linear number of leaderer pointer updates。

 that seems to be giving rise to a quadratic time bound。

 but remember when I introduced the Union find data structure。

 I only said that first idea was idea number one， presumably there's an idea number two and here it is and it's very natural if you were coding up an implementation of union find data structure you would probably very naturally do this optimization yourself。



![](img/83022c2614612cc4f91a6fcbbce8dc53_6.png)

Alright， so consider the moment in time in which some component A merges with some component B。

 Each of these two components currently has their own respective leader vertex and all vertices from that group are pointing to that leader vertex。

 Now， when they fuse what are you going to do the first obvious thing to do is say well。

 let's not bother computing some totally new leader let's either reuse the leader from group A or the leader from group B that way。

 if for example， we retain the leader from group A。

 the only leader pointers that need to be rewired are the ones who come from component B。

 The vertices and component A can keep their same leader vertex and their same leader pointers as before So that's the first point。

 let's just have a new union of two components inherit the leader of one of the constituent parts Now。

 if you're going to retain one of the two leader， which one are you going to retain maybe one of the components is  a000 vertices。

 the other component only has 100 vertices Well， given the choice。

 you're certainly going to keep the leader from the bigger from the first component that way you only have to rewire the 100 lit pointers。

Second group right if you kept the leader of the second group。

 you have to rewire the 1000 pointers from the first group and that seems silly and wasteful so the obvious way to implement a merge is you just keep the leader of the bigger group and rewire everybody from the second group。

 the smaller group。So you should notice that in order to actually implement this optimization where you always retain the leader of the larger group。

 you have to be able to quickly determine which of the two groups is larger。

 but you can augment the data structure we've discussed to facilitate that so just with each group you just keep account of how many vertices are in that group so you maintain a size field for each group。

 that allows you to check in constant time， what's the population of two different groups and figure out again in constant time。

 which one's bigger and notice that when you fuse two groups together it's easy to maintain the size field it's just the sum of the sizes of the two constituent parts。



![](img/83022c2614612cc4f91a6fcbbce8dc53_8.png)

So let me now revisit the question from the previous slide， in the worst case。

 given this optimization， how many leader pointers asymptotically might you have to rewire when you merge two components together？

Well， unfortunately， this song remains the same。 The answer is still the third one。

 and it's because for exactly the same reason as on the previous slide。

 it still might be the case that say in the final iteration of Crsco。

 you're merging two components that both have size n over2， So it doesn't matter。 I mean。

 no matter which leader you choose， you're going to be stuck updating the leader pointers of n over 2 or theta of n vertices。

So while this is clearly a smart practical optimization。

 it doesn't seem to be buying us anything in our asymptotic analysis of the running to。However。

However， what if we think about the work done in all of these leader pointer updates in the following different way？



![](img/83022c2614612cc4f91a6fcbbce8dc53_10.png)

Rather than asking how many updates might emergingrging of two components trigger。

 let's adopt a vertex centric view。 Let's suppose you're one of the vertices of this graph。

 So initially at the beginning of Crusco's algorithm。

 you're in your own isolated connected component， you just point to yourself， you're your own leader。

 And then as Crusco's algorithm runs its course， your leader pointer will periodically get updated at some point you're no longer pointing to yourself。

 you're pointing to some other vertex， then at some point your pointer gets updated again。

 you're pointing to yet some other vertex and so on。

 how many times over the entire trajectory of Crusco's algorithm in light of our new optimization M you as some vertex of this graph have your leader pointer updated。

Well here's the very cool answer， the answer is the second one。

So while it remains true that if you always have the union of two groups inherit the leader pointer of the larger one。

 it's still true that a given fusion might trigger a linear number of leader pointer updates。

 each vertex will only see its leader pointer updated a logarithmic number of times over the course of Kscoll's algorithm。

What is the reason for this？ Well， suppose you're a vertex and you're in some group。

 and it has maybe 20 vertices。 So you're one of 20。 Now， suppose at some point。

 your leader pointer gets updated。 Why did that happen， Well。

 it meant that your group of 20 vertices merged with some other group that has to be bigger。

 Remember， your leader pointer only gets rewired in a fusion if you were in the smaller group。

 So you're joining a group at least as big as yours So the size of the union。

 the size of your new community， your new connected component is at least double the size of your previous one。



![](img/83022c2614612cc4f91a6fcbbce8dc53_12.png)

So the bottom line is every time you as a vertex has your leader pointer updated。

 the population in the component to which you belong is at least twice as large as before。 Now。

 you start a kinetic component of size 1， a kinetic component is not going to have more than n vertices。

 So the number of doublings you might have to endure is at most log based to event。

 So that bounds how many lit pointers you will see as a vertex in this graph。

So in light of that very cool operation， we can now give a good running time analysis of Crresco's algorithm using the Union find data structure。

 using the scaffolding on the kinetic component structure to do cycle checks。



![](img/83022c2614612cc4f91a6fcbbce8dc53_14.png)

We， of course， have not changed the preprocessing step。

 we're still sorting the edges from cheapest to most expensive at the beginning of the algorithm and that still takes big O of M log n time。

So what work do we have to do beyond this sorting preprocessing step while fundamentally crustal's algorithm is just about these cycle checks and each iteration of the fore loop we have to check if adding a given edge would create a cycle with those edges we've already added and the whole point of the union fine scaffolding these link structures is that we can check cycles in constant time just given edge we look at the leader pointers of a1 points and a cycle will be created if and only if their leader pointers are identical so for the cycle checking we only do constant time for each of the O of M iterations。

But the final source of work is maintaining this union find data structure。

 restoring the invariant each time we add a new edge to the set capital T and here the good idea is we're not going to just bound to the worstcase running time of these leader pointers for each iteration because that could be too expensive。

 that could be up to linear in just a single iteration。

 rather we're going to do a global analysis thinking about the total number of leader pointers that ever occur on the previous slide we observed that for a single vertex。

 it's only going to endure a logarithmic number of leader pointer updates。

 so something over all of the n vertices， the total work done for leader pointer updates is only n log n。

So even though we might do a linear amount of pointer updates in just one iteration of this for loop。

 we still have this global upper bound of n log n on the total number of leader pointer updates。

 very cool。So looking over this tally， we observed this stunning fact that the bottleneck for this implementation of Ksco's algorithm is actually sorting。

 So we do more work in the pre processing step M log n than we do in the entire for loop。

 which is only M plus M log n。 So that gives us an overall running time bound of big O of M log n matching the theoretical performance that we achieved in Pris algorithm implemented with heaps。

😊，So just like with our heat based implementation of Prims algorithm。

 we get a running time which is almost linear， only a logmicic factor slower than reading the input。

 and just like with Prims algorithm， you should find Crsco's algorithm to be very competitive in practice。



![](img/83022c2614612cc4f91a6fcbbce8dc53_16.png)