# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P54：2 - Spring 2023 Discussion 10 Question 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

All right hell everybody So in this video we're going to be going in question one。

 the shortest path of your heart Part A is going to test on our ability to understand running dike stress on this given graph and part B is going to test us on our ability to understand running the a star algorithm on graph we're going compare and contrast the differences that arise from using those two different algorithms So a bit of a quick primr on what dike Str does where we have this table and this part to Q and both of them are the first row distance to and the part of Q are going to contain the exact same information which the distance from the the starting node to whatever node that we're currently on well the shortest path to that current node that we know about then edge2 is going to contain the node that we last travel to before we got to the current node so for example if we have to get to C using A B then B well then the edge2 C will be B because that is the last node that we travel to before we got to C and also notice that we have a bunch of these infinities here Infinity shows that we don't know what the distance from a to that given node is and we only know what the distance to a given node is when。

Our spanning tree in our shortest path we have a node that connects to that given node right and so right now we're starting A and we haven't put a into our shortest path yet and so therefore the only node that we know about is A。

 we don't know where B， D， C， E， F and G are in relation A and so therefore their values are infinity because that way the prior to Q which always takes the which always pops the minimum value isn't going to accidently pop any of those values that we don't know about。

And now let's start with running this algorithm right so first of all we're going to add an a because well that is the only node that we know about right A has a distance to zero and now it grants access to a bunch of different nodes right we know where B is we know where E is we know where D is right so let's go ahead and that in and notice once again that the distance to B D and E is equal to their values in the part of the Qs right and also notice how edge2 is all a right because in order to get to E D and B we travel through a to get there and that was the last node that we travel to before we got to Bt and E and so therefore their edge2 is a now that we've incorporated all the information of which is game we're going to go ahead and remove we're going to pop the node that has the smallest value in the part of the Q and we're going to add it to our our shortest path right so we're going to go and pop B and we're going lock it in we're going confirm it by turning it green。



![](img/150831cde34b978efa47287e5cb9b021_1.png)

And now once again， B is going to reveal some new information to us now with B。

 we know that there is a path to C as well right and this path has a distance to of four because remember the distance2 is a total distance from a to the given node and in this case。

 A travels for B which is one and then B travels to C which is three and so in total we have a distance of four and also notice how H2 is B this time because in order to get to C as you mentioned our example at the very beginning we had to travel from B to C as we therefore last the last node that we travel to before we got to C is equal to B and the priority Q is updated to match。

All right， that's all the new information we have So now once's we have to make a choice。

 What is the next node that we're going to explore and that is going to be D because D has the smallest value in a part Q we're going to go ahead and lock it in and now we have once again new information and this really interesting because this information kind of is an overlap with information that we already had this tells us that in order to get to E we can also travel from a to D and then to E and notice that this total traversal is equal to two plus3 and that's5 and5 is less than is less than7 and so what we've done is we've discovered a more efficient way to travel to E and so therefore we don't want to travel to E anymore from a to E because're going also find the shortest path And if we're going replace the values that we had in B with this new path that we just have its distance two is now going to be5 its value in Part Q is also five and the edge2 is D because it tells us how this more efficient path travels。



![](img/150831cde34b978efa47287e5cb9b021_3.png)

All right， once again， that's the all the information。 Let's pop the smallest node。

 that's C C grants us the access to F and G right so now we're going to travel from C to F and that that total length is going to be equal to6 and we can also travel to G from C which total value is going be equal to8 All right everything in the priority value is done and we found a path G are we done no because that extra doesn't just find g and stop looking and it looks at every single path and wants to consider the shortest path each of these individual nodes so we're gonna keep doing this process until the priority to Q is entirely let's take like at E E we're gonna once again overlapping information we know that from E we can now get to G as well in a different way but notice that the distance to E from a is equal to5 and this is from e to G is equal to4 and so therefore that total distance is going to be equal to9 but9 is not less than a so it would be a less efficient path they go from e to G and therefore we don't want to do anything with that information we're not going to update it because once again our goal is to find the shortest path。



![](img/150831cde34b978efa47287e5cb9b021_5.png)

![](img/150831cde34b978efa47287e5cb9b021_6.png)

Not found a shortpathic of the G。All right so once again we're gonna skip over that information now that we consider everything let's pop six that's pop F and now F is giving us the information that's actually relevant right because a distance from f to G is all to one a distance from a to f is6 and therefore this new path that we've discovered is7 and seven us to a that is the shorter path and so therefore if we want to get the G we want to be using the path through F and finally we updated data prior to Q we're going to move it and this is our shortest path dike Strs considers every single node and it's going to tell us the path that we can take from a to get each of these interval nodes and also it might be a bit confusing to look at this table and kind of tell us going on so let me break it down right distance two is going to very simply tell us a distance from a to each of these individual nodes that is the shortest possible path right。



![](img/150831cde34b978efa47287e5cb9b021_8.png)

![](img/150831cde34b978efa47287e5cb9b021_9.png)

Edgege2 is going tell us how that path works right because if we just look at A and G and we said this is Su 7 we might not be sure which specific path we're taking get to G right because there are a ton of them we can go from A to B to C to F to G or we can go from A to D to E to G or from A to E to G It's not clear which path it is However by li edge2。

 we know that the last node that we travel before we got to G was F And then in the F column we know that the last node that we travel to before F was C and we can go back and then so C the edge to C is B and then the edge to B is equal to A And therefore we know that the shortest path to G travels from A to B to C to f to G and not some other thing and that how edge works。



![](img/150831cde34b978efa47287e5cb9b021_11.png)

Now let's take a look at a star so a star is a bit unique in that it takes in this thing that we call a heuristic right and in this graph the heuristic is indicated by these blue numbers right notice that G doesn't have a heuristic because it is the final thing and this is the key difference right a heuristic theoretically allows us to know it allows us to optimize it right if we have a good heuristic and we choose it and it sends us down a good path so to speak then we can get to G and then we can just say we're done right it'll theoretically be the fastest path right and so therefore a star doesn't terminate when every value has been removed from priority to Q and instead terminates when G is removed right when we get to G we don't consider anything else because if a heuristic is good then there's no way that there is a more efficient path to get G。

Right so how does the heuristic work Well everything in the table is still the same distance do an h the same。

 but instead the prior to Q instead of being the exact same as distance 2 it's now going to be equal to the distance to that value plus whatever the number is at that given node right so once again we're starting from a and let's take a look at how this works right the distance to a from a is obviously zero as we know but because a has a heuristic of7 we're going to add7 to the distance to a and put that value into the priority to Q So a is equal to 7 because a is equal to7 plus0 we're going go and pop it now let's add the new information that we've received right it's the same process is x us we're going to add B which is a distance to1 but notice that the value in the prior to Q for B is equal to 7 because it's a distance from a to B1 plus the heuristic of B which is equal to 6 so one plus6 is equal to 7 let's repeat this process for E the distance from a to E is7 and H2 is also a but the heuristic for E is equal to3 and instead therefore the value that we put。

Idq was equal to 10。And let's round this out， we're going to add in D right。

 but the distance from a to D is equal to 2 and the hereuristic port d is 8 and so therefore the value in the priority Q is 8 and notice how this table up above is this actually lay out same as we have questions。



![](img/150831cde34b978efa47287e5cb9b021_13.png)

All right， now that we consider all the information。

 let's go and add D into the value because that is the smallest value right and now let's look at the new information that we gained which is that the distance to C from a is equal to four。

😊，And heuristic for C means the value that is placed in here is that right and so now this is where the difference in start right the heuristic is luckily telling us that you know instead of considering D and E。

 maybe we just need to consider C right maybe we just need to consider C and we're going to add C in first right but whereas before we had to explore D and we explore E before we look at C here we're just going to look at C rather than that。

😊。

![](img/150831cde34b978efa47287e5cb9b021_15.png)

All right， now that we've have a the let's look at the new information that we have。

 we're going to go ahead and add in f as well， the distance to f is equal to6 but in the priority Q F is value at sub right and we're also going to add in c to G the party which is going to be a distance of eight but in the priority Q that's going to be equal to8 right remember the G doesn't' here six G's here six is zero。

😊，And so now the priority Q is once again different than when we had in dike stress right now we're going to instead of popping at this point。

 I think we pop C now we're going to pop F right we're going pop F we're going to add it to our thing and we're going to keep going F is going access to G and the access to G is going is going to be equal to7 it's a distance to G plus heuristic or G which is equal to zero and so therefore this is7 G is now the first value in a priority Q and we're going pop G and now we're done there's nothing else we need to do because heuristics are telling us that we have access to G there's no quicker thing right and therefore as going see a star has circumvented the need to look export all the paths from B and E to G and instead because we had a good heuristic sense we're able to ignore all those other things and just look at the shortest possible path and get there very efficient。



![](img/150831cde34b978efa47287e5cb9b021_17.png)

![](img/150831cde34b978efa47287e5cb9b021_18.png)

![](img/150831cde34b978efa47287e5cb9b021_19.png)

Okay now in question1， we're gonna take a look at the heuristic that we just used for the A star algorithm and1 B right and specifically the question is。

 is the heuristic for this graph good In other words。

 is it guaranteed that we will always find the shortest path from A to G by using the a star traversal that we use in question B Well the short answer to that is the answer is yes。

 However， there are two important criteria that we can check to see if a given heuristic is good there amissibility and consistency and I've copied definitions over from the slides as you can see here so let's go and check each of these on the heuristic to see whether or not they actually match right first of off is amissibility and the definition for amissibility is a heuristic for any given note on the graph So every single one of the node the heuristic for that note has to be less than a true distance from that note to the target and true distance is kind of a nebulous term but more specifically it just means what is the shortest path I can take from this given note to the target note which in our case is G。

So you don't want to take a look at a couple examples right that's not by looking at F right the heuristic for F is one right then the true distance from F to G is well also one。

 And so therefore the heuristic is indeed less than or equal to the true distance because one is less than equal to the1 now it's like look at another example D so the heuristic for D is6 and the true distance for D is traveling from D to e than from e to G which is going to be equal to7 So6 is less than equal to7 and so therefore D also satisfies the admissibility criteria right now let's look at a bit of a complicated example so C C has a heuristic of3 however it's not entirely clear what the distance from C to G is we can take the easy edge which is just c to G directly and that has a like the4 but more specifically we're actually going to want to look at C to f to G because that's actually going to be less than that and so therefore3 is less than C to f to G which is two plus1 which is three and so therefore C also satisfies the admissibility you can go in and check this for all the nodes and。

You'll see that matches our to you perfectly， but you know， just for the sake of time。

 we're going to skip over into that is true。Now let's take a look at the second part here which is consistency and consistency says that for each neighbor v of W。

 the heuristic of V is going to be less than equal to the distance from B to w plus the heuristic from w to the target and specifically now you we look at true distance in the past now we're going look at the distance from B to W which is just the weight from the edge weight of the edge from B to w okay let's take a couple examples right so C to F right for example the heuristic of C is equal to3 and the distance from C to f is2 and the heuristic of f is equal to1 so in fact you know3 is less than equal to2 plus1 for a bit of a complicated example that illustrates what distance is right so now let's take a look at a right and let's take a look at A to E the heuristic of a is equal to seven。

😊，And now the question is you know what is a distance from a to E because once again we have multiple paths we can just take a to E which is seven or we're going to take a to D to E which is a length of five right well notice in our definition of distance right it is the weight of the edge from B to W and so in this case we're going to specifically look at a to E which is going to be7 and so the heuristic of E is equal to three and so overall we have seven is less than seven plus three which is a true statement and you can check therefore any of the neighboring nodes。

And you will see that it is true and so that shows therefore like it is a mathematical proof that shows that the given heuristic is in fact a good heuristic。

 it is guaranteed that we will always find the shortest path from H to G and that should do it for this video。

😊。

![](img/150831cde34b978efa47287e5cb9b021_21.png)