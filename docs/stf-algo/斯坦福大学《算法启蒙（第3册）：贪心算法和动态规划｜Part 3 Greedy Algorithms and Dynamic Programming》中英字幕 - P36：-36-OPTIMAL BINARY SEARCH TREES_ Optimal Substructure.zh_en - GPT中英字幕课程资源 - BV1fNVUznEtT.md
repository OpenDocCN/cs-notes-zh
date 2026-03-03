# 斯坦福大学《算法启蒙（第3册）：贪心算法和动态规划｜Part 3 Greedy Algorithms and Dynamic Programming》中英字幕 - P36：-36-OPTIMAL BINARY SEARCH TREES_ Optimal Substructure.zh_en - GPT中英字幕课程资源 - BV1fNVUznEtT

![](img/36750a8ab22af00f97120c68d02d7355_0.png)

So now that we've motivated inform formally defined the optimal binary source tree problem。

 let's think about how to solve it after settling on dynamic programming as the paradigm we're going to try to use。

 we're going to proceed in the usual way， turning to the optimal solution for clues。

 asking in what way is it composed of optimal solutions to smaller subproblems。

Let me just remind you of a formal problem statement。

 There's n objects we got to store in a search tree and let's just name them in the order of their keys and let's name them 12。

3 all the way up to n for simplicity， and we're also given frequencies or weights reflecting how often the different objects are searched for。

 So that's P1 up to PN positive numbers canonically we think of these summing to one being probabilities。

 but I actually won't use that fact so that in general they're just arbitrary positive numbers。

 The goal is to output a search tree， it should satisfy the search tree property contain all of these objects1 through n and amongst all such search trees。

 it should minimize the weighted search time。 So to sum over all the items I of the probability of I times the search time for I namely it's de in the tree plus1。

Now， in case you're feeling cocky about the fact that the greedy algorithm worked to solve the seemingly similar optimal prefix free binary code problem in the form of Kuffman's algorithm。

 I want to spend a lot of time pointing out that greedy algorithms are not sufficient。

 are not correct to solve the optimal search Street problem。

So if we were to design a greedy algorithm， what kind of intuition would motivate a particular greedy rule Well staring at the objective function。

 it's very clear that we want the objects that have high frequency of access to be at or near the root and we want items with low frequency access to be in the bottom levels of the tree like the leaves。

So what are some ways we can compile this intuition into a greedy algorithm Well one perhaps motivated by the success of Huffman's algorithm is we could think about a bottom up approach now I'm not going to define what I mean here precisely。

 but informally we want to start with the bottommost levels with the leaves and the nodes we want to put there are the objects that are accessed the least frequently。

Any reasonable way of implementing this kind of body of greedy rule is not going to work。

 let me show you a simple counter example。So let's just assume we have four objects 1，2，3。

4 what I'm showing here on the right in pink is two possible search trees valid for those four keys。

 and let's assume that the frequencies are as follows， object1 is searched for 2% of the time。

Object 2 for 23% of the time。Object three， the bulk of the time， 73%。

An object for only 1 per of the time。Any greedy algorithm which insists on putting the lowest frequency objects in the very bottommost level of the tree is not going to produce this tree on the right。

 which has the 2% object below at a lower level than the 1% object。

 instead such a greed algorithm would presumably I'll put a search tree like the one on the left。

 which has the two is the root， and then the object4 at the lowest level at depth2。

But you should be able to easily convince yourself that for these probabilities。

 it's the tree on the right， which is the one you want。

 that's optimal because the object three is the one searched for the bulk of the time。

 that's the one you want at the root as opposed to the object2。

So I realize I'm being a little informal here， but I hope you get the idea that a naive bottomups implementation of a greedy algorithm。

 which if you think about it is really what we did in Huffman's algorithm。

 is not going to work here the same can be said about a top down approach。

 perhaps the simplest top- down approach would be just to take the most frequently searched for object and put that at the root and then recursively develop appropriate left and right subtes under that most frequently accessed element。

So let me show you again informally， just the same kind of counter example。

 we're going to use the exact same four objects， the exact same two trees。 I will， however。

 change the numbers。 Now， let's imagine that object1 is searched for almost never just 1% of the time。

 And each of the other three objects are searched for roughly a third of the time each。

 But let me sort of break ties so that the object number two is the most frequently one。

Searched for 34% so that in that case， the greedy algorithm will put the 34% node up in the root when really what should happen is you want a perfectly balanced subree for the objects 2。

3 and 4 because each accounts for roughly a third of the searches so let's give object 3。

 33% of the searches an object for 32% of the searches。And again。

 I'll leave it for you to convince yourself that this is indeed a counter example。

 the tree spit out by the greedy algorithm on the left would have an average search time of roughly two。

 whereas the search tree on the right would have an average search time of roughly five3s so we'd like to produce the tree on the right but the greedy algorithm proposed here will spit out the tree on the left。

This of course doesn't exhaust the list of potential greedy algorithms you could try others。

 but it's not going to work， there's no known greedy algorithm that successfully solves the optimal binary search tree problem。

So in particular， if we focus on the top down approach， the choice of the root。

 the choice of what to do at the uppermost level has very hard to predict repercussions for what the two different subprom look like。

So this is what stymi is not only the top down greedity approach but also a naive divide and conquer approach。

 so for example， if we just wanted to split the keys into the first half in the second half recursively compute noal BSC on each of those two halves and then put them back together。

 the search shape property would say that we have to unite those two subsolutions under a root which is the median in between the two subproblems and who was to say that the median is a good choice for the root again because the ramification is further down the tree。

 maybe that's a stupid root。But boy， is it tempting to try to solve this problem recursively， right。

 We're trying to output this binary tree。 It has recursive structure。

 If only we knew which route we should pick， we would love to recurse twice once to construct an optimal left sub tree。

 once to construct an optimal right sub tree。Okay， so if only we knew the right route。

 this is starting to sound familiar， actually， how did it work in all our dynamic programming solutions。

 we always said， if only a little birderie told us this one little piece of the solution， well。

 then you then we could sort of look up or recursively compute the rest of the solution and extend it back to one for the original problem easily。

 So maybe the same thing's true here， maybe if only a little birderie told us what the root was。

 then we could look up or recursively compute optimal solutions to smaller sub problems and paste everything back together and be done。

 that would be great。😊，So as usual we want to make this precise with an optimal substructure lemma。

 we want to understand the way in which an optimal solution to an optimal BST problem must necessarily be constructed from optimal solutions to smaller subproblem so in the following quiz I'm going to ask you to guess what the appropriate optimal substructure lemma is and then after that quiz once we've identified the right statement at that point I will show you the proof。



![](img/36750a8ab22af00f97120c68d02d7355_2.png)

Okay， so the answer I'm looking for is the fourth one is D， which is the strongest statement of all。

So the first point is that each of the trees， T1 and T2 now as subtrees of a binary search tree。

 these of course， are themselves binary search trees valid for the trees that they contain and not only can they be viewed as search trees on the keys that contain but the claim which will prove on the next couple slides is that they are indeed optimal they minimize the weighted search time over all possible search trees for the objects contained in those two trees so that gets us down it rules out A it rules out B。

 we can say something stronger than that we can even say something stronger than C that each of the two trees is optimal for the items that they contain we actually know exactly which items are in T1 and which items are in T2 and this is by the search tree property the search tree property says that at every node and in particular here at the roots everything to the left of the root is less than it everything to the right of the node is bigger than it so the root being R by assumption we know the objects one through R minus1 well they got to be somewhere the only way they can be is in the left subtree T1。

So that's exactly the contents of T1， similarly the contents of T2 are precisely the objects are plus1 through n。

 so the two subries are optimal and we know exactly which keys they are。

 it's everything less than R in the left， everything bigger than R on the right。

Okay so here's where things stand at the end of this quiz。

 we've identified the statement that we're really hoping is true。

 We're really hoping that an optimal BST binary search tree must necessarily be composed in this way of optimal binary search trees for the keys to the left of the root and the right of the root if that's true hopefully with the experience we now have we can sort of envision what a dynamic programming algorithm might look like I'll fill in the details in the next video if this weren't true if we didn't have this optimal substructure honestly I have no idea how it get started。

 It's really not clear what an algorithm would look like if this weren't true So in the next couple of slides I want to prove this to you The format you will not be radically different than the ones we've already seen。

 I don't think there'll be any big surprises。 but it's so important this really is the whole reason why the algorithms going to work I'm still going to give you a full proof of this optimal substructure Lema。

