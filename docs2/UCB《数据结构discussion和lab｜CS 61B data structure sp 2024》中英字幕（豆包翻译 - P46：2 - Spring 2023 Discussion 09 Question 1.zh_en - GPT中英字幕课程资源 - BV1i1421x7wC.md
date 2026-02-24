# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P46：2 - Spring 2023 Discussion 09 Question 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼阿比阿 me。🎼Oh你。

![](img/eb60d3fceed9ad95788c61fda22ffe2c_1.png)

Okay let's jump right into the worksheet with question one trees graphs and traversals oh my so I know that the worksheet says that for this BST we want to write out the preorder post orderder in order and BFS traversals of this tree I'm going to focus on the in order and BFS traversals here and we will I will run through the preorder and post order really quickly at the end but I think it's more helpful for us to do1 C for pre and post orderder because it's more generalized graph rather than just a tree but we'll do it anyway don't worry I just want to make sure that you all understand in order and BFS really well on tree specifically because pre- and post orderder can be generalized other graphs as well。

So I just put the in order pseudocode down here， remember if T is now return。

 otherwise we in order on T dot left， we visit T。tru and we in order on T dot right so what that's going to look like is we're going to start at this BSC rooted at 10。

Right so we're going to go to 10 and we're going to try to call in order on 10s left right we don't notice that we don't visit 10 yet because visiting a route only happens after we visited that node's left subree so we're going to start at 10 and we are going to come down to three right because we're going to try to go to in order on the left when we come down to three we're going to likewise try to start again and call in order on the left and we're going to come down to one so when we get to one we're going try to call an order on the left there's nothing to recur on so we're going to visit one right visit t do root so we visit one。

And then we tried to do an order on the right but there's no right node right child of one so we don't have anything to in order on so then after that we're going to pop back up to the recursive call to in order on the three tree and when we do that we're going to pop back up to the three so we're done visiting the left child in order so we're going to visit the root so that's just three in this case right？

So after we do that we visited the left sub childild we visited three and now it's time to visit the right child of three when we try to visit the right child of three we're coming down to the seven seven is going to try to call in order on its left there's no child to rehearse on to so we visit seven。

And then we tried to recurse onto the right child of seven。

 but there's no right child to recururse onto， so we pop back up。

To this three we're done with this subree over here so we're going to pop back up to the 1 and by the time we pop back up to the1 that's an in order call on the tree rooted at 10 right and we've already in order process everything in the left subre so what's left is we need to visit itself the root and then we need to visit our right subre so we're going to visit our next we're going to visit 10 and next we're going to recurse onto the right subtree down here so when we recurse onto the right subre down here we're going to we're going to get to 2。

And then from 12 we don't visit 12 yet remember we tried to in order traverse onto the left child of 12 which is 11。

 so when we get to 11 we are going to try to in order traverse onto 11's left child there's no child to traverse onto so we just visit 11 then we try to in order traverse onto 11's right child there's no child to traverse onto so we hop back up to 12。

So let's hop back up to2。And now we have oh I skipped a gloss over that a little bit。

 but when we hop back up to 12， we've already finished in order traversing onto left the left subree of 12 right so now we just need to visit 12 itself and we need to visit its right subree in order traversal so when we visit 12's right subre and in order traveral we're going to traverse onto this subte rooted at 14 we're going to see 14 but not visit it yet because we're going to try to in order traverse on the left child of 14 right and when we left traverse onto the child of 14 we will get to 13 and then when we get to 13 once again because this is recursive。

 we're going to try to go onto the left child of 13 there's no left child so we just visit 13 itself。

And we try to visit the right child of 13， there's no right child of 13。

 so we'll pop back up to the subtre rooted at 14 and because we've already processed the left subtree of the node of the tree rooted at 14。

 we process 14 next and lastly we're going to go down to 14's right child right。

 it's this in order call to the right child of 14。When in order traverse onto 1515 is going try to in order traveral on its left child。

 there's nothing to traverse on so we'll just visit 15。

 we'll try to in order traverse them to the right child。

 there's no child there once again so we'll pop back up to the 14 will pop back up to the 12 will pop back up to the1 there's nothing left we're done traversing this tree in order traveral Something really cool that I like to point out is that we did in order traversal on this BST and the reason why it's called in order traversal is that you'll notice that the order in which it spit out the elements or visited the elements of this BST it has the elements in sortdid order right and then it kind of makes sense when you think about it because when you think about the invariance of a BST for a root every element to the left of that root needs to be less than that root and then everything to the right of the root needs to have a value greater than that other the root when you think about how in order traversal work it goes all the way left than up to the middle than down to the right it kind of makes sense that it works like this right because。

Everything to the left is smaller than the root then we process the root then we go into the right which has everything larger than the root right so that's just a cool little tidbit that might be helpful later in the worksheet okay。

So next let's do BFS so remember that the BFS pseudocode basically said that we're going to work with a queue a first and first out data structure right we're going to put our starting note on the queue and while the queue isn't empty we want to pop off the first element in the queue and add its unvisited neighbors to the queue so what that's going to look like is we're going to start out by adding 10 to the queue。

So what we do next is we pop 10 out of the queue and when we pop 10 out of the queue we're going to add 1s neighbors which are three and 12 to the Q right3 and 12 haven't been seen yet so we're going to pop those out and get three and 12 on the queue and you'll see that once we pop it out it goes into the next element in our BFS traveral so let's repeat the process let's pop out from the front of the queue so we're going to pop a three out and then we're going to put three into our BFS traveral and then we're going to put the neighbors of three that haven't already already been visited which are one and7 in this case onto the queue so after this the queue is going to look like 121 and 7 right we kind of just shift things along。

After that， we are going to pop 12 out from the front of the queue and add 12 neighbors to the queue so what that's going to look like is 12 is the next element we visit in our BFS reversal and our queue looks like 17。

 11 and 14 because we just added the 11 and 14 which were the neighbors of 12。😊，After that。

 we pop out the one。One is going to join our BFSQ over here， but there's no children of one。

 so we don't add anything to the Q。Likewise， we're going to pop out seven from the front of the queue right and when we pop out seven。

 we're going to add that to our BFS traversal and7 doesn't have any children so we move on。

Once again， with 11， we pop out 11， it joins our BFS traersal and it doesn't have any children。

 so we move on。And then。Next we have 14 to left in our queue so we're going to pop out 14 and then add its unvisited neighbors to the queue its unvisited neighbors here are 13 and 15 so we're going put 15 and  13 and 15 into our queue in that order here we're kind of just breaking ties by left and right child and in the case of BST it's going to be in ascending order so here we saw that 14 joined our BFS implementation traversal sorry and we pop out the 13 and added to our traal 13 doesn't have children so we move on and lastly we pop out 15 15 doesn't have children it joins our BFS traversal and our queue is empty and we stop execution of BFS there okay。

So。U。😊，Okay， so。Okay， so now we are going to move on to the preorder and postorder traversals of this BSD。

 I'm going to kind of zoom through this because again。

 like I think it's more important that you see one Cs preorder and postorderhesal on a general graph but here've just put the pseudocode for preorder and post- orderder so pre-order remember we tried to go as far left as we can or we visit the route then we try to go as far left as we can then we visit the right So what that's going to look like is in the context of this tree when we start at 10 following the pseudocode we're going to visit 10 so the very first the very first elements in our preorder is going to be 10 then we're going to preorder on the left so when we pre-order on this left sub tree over here we're going to visit three and they're going try to preorder on the left of three so we're going to visit one there's nothing left to preorder from one's children so we hop back up to three and then after we preorder on our left child we want to pre-order on our right child right so after we do that。

Hop back up to three and then we tried to pre-order on 7 when we preorder on 7。

 we visit7 and then we try to pre-order on seven children but there's no children to go over so the first four elements of our preorderersal are going to look like 10。

3，1 and 7 okay so coming back up to this overall BST we've already visited 10 and we've pre-order visited our left subre So now we have to preorder visit our right subre what that's going to look like is we are going to visit we're going come down to pre-order on the right subre we're going to visit the route right which is 12 and we're going try to pre-order on the left subree of 12 which is this 11 node over here So next we're going to spit out 11 and then we're going to try to preorder on left on the left and right child of 11。

 but there's no children to go through we're going to hop back up to this 12。

This 12 subree and then at that point we've already visited 12 we've preorder visited the left subree of 12 and now we have to visit a preorder visit the right subree of 12 which is this 14 tree over here so we're going to come down here over to the right we're going to visit 14 and then we're going to try to preorder on the left child which is 13 we visit 13 we try to visit 13s children but there's no children so we hop back up to the 14 over here and now we have to pre-order visit our right child which is this tree rooted at 15 so we visit 15 and then we try to visit 15s children but 15 doesn't have any children so we finish execution of that and then we hop back up to the 14 and then we hop back up from the 14 to the 12 and we hop back up to from the 12 to the 10 and at that point we' preorder tra this entire BST so what that looks like is going to visit 10 then three then one then 7 then 12 then 11 then 14 then 13 then 15。

When I have those answers up here， sorry that was like such a whirlwind。

 but like once again I kind of just want to get through this so you can build intuition for a larger graph on preorder and post orderder so post orderder traversal is a little funky it says I want to post order visit my left child then post order visit my right child then visit myself So when we start at the BST root which is 10 we're going try to post order on the left so we're going to come down to this subtre rooted at three and then the first thing we do when we call post order on the three subtree is we want to post order on the left so we post order on on the left and by the time we get here we try to post over on one's left there's no left child we try to post order on one's right there's no right child so we just visit one right so after we finish visiting one we hop back up to here。

And before we process three， remember that when we're in post order3。

 when we finish processing the left we have to process the right before we visit our right so when we're in the three。

 we have to process seven before we can visit three So we have to come down here to 7 and then we're going to try to post order on seven's left we're going to try to post order on 7's right it doesn't have either of those children so we just visit7 and then we'd hop back up and then finally we'd get to visit3 and that's what we mean by visit my children before myself because the first three numbers in the post order traversal are going to look like one7 and three right so when we hop back up to the10 because we finish processing this left subt and postorder traversal we'll see that10 is the group but we cannot process it yeah right because we need to postorder traverse on the right subchild that's the whole pseudocode we have here if we were calling post order on 10 we already postordered on the left subre of 10 and now we need to post order on the right subree of 10 which is what this line is saying right so when we post order on the right subtree of1 we're gonna see this 12 tree over here。

And the very first thing we want to do is post order on the left of 12 so we post order on the left of 12 we see this 11 node。

 we try to post order on the left of 11， there's no child there we try to post order on the right child of 11 there's no child there so we just visit 11 right so once we have that we hop back up to the subre rooted at 12 and before we can process 12 we have to process the right subree of 12 so we're gonna try to post order on the right subree of 12 which is this 14 subree over here and then the very first thing we want to do is post order traverse on the left subchild so we post order traverse onto the 13 we try to post order traverse onto 13s left child there's no child there we try to post order traverse onto 13s right child there's no child there so we just visit 13 as per this line right so we're gonna finish visiting 13。

And then we pop back up to the subree rooted at 14 and before we can process 14 we have to process 15 so we're going to come down here to 15 and then a 15 is going to try to post order onto the left child then the right child but once again it's the leaf right there's no children there so we just visited the route so after we visited 13 we visited 15 and then now we need to pop back up and finished post order processing the subree after which we we visited 14 right we visited the left we visited the right now we visited the note itself。

So when we take that into the larger context of the subree rooted at 12 when we get to this point when we're popping back up from 14 to 12 we've already processed the left subte of 12 and we've already processed the right subree of 12 and all that's left is to process the 12 node itself we just visit 12 and then after that we pop back up to the 10 so when we see this 10 we're at the stage where we already post ordereddered on this left subree over here we've already post ordereddered on the right subtree over here and now we just visit the root which is 10 and that's it for post orderder traersal so in。

In order of the notes that we visit in our postertroversal， we would visit one。

 then seven then three， then we'd visit 11， 13， 15， 14， and 12。Oh and then we'd visit 10 I'm sorry。

 I forgot to say 10 so it would be go all the way down to the left then go to the right then up to the middle And then when you get back up here from the17 and the three。

 you want to process the right subree before you process 10 so you're gonna do the same thing go all the way down to the left until you can't anymore in which case we process 11 then we want to go to the right and then keep going to the left as much as we can until we can anymore so left right middle left right middle it's kind of like that pattern Okay that was a world and I'm so sorry。

But hopefully that gave you a good idea of where to start like doing preorder and post orderder traversals as well as in order and BFS on a tree and for now let's move on to1 B so I'm going to breeze through 1 B a little bit because it's technically not in scope for midterm two I mean it's good to generally know of course like you'd like to know your graph representations but it's not in scope and I think that representations tend to be a little more intuitive for students anyway so we don't really need to spend as much time on this but first of all we're asked to write an adjacency matrix and an adjacency list so in an adjacency matrix。

We'd first want to set it up so that we have nodes ABC D EFG right so we have like rows and columns and the rows represent the from node and the two and the columns represent the two node so for example here if I marked G GA that would mean that there's an edge from G to a okay so。

Basically how we want to fill this out is we want to go through each row of nodes and ask ourselves is there an edge from A to A。

 is there an edge from A to B， is there an edge from A to EC and so on and so forth and we check off the elements in the grid that do actually have that do have an edge there so here on the slides you'll see me using checkboxes in the solutions you'll see zeros and ones and basically the one just represents whether or not the one represents that there is an edge from some node to another node if the intersection is marked with the1 if it's a zero then there's no edge between those two nodes something else that's really important to know is that the edges of this graph are directed and what that implies for a graph representation in the matrix is that there's an edge from a to B but it's a directed edge from A to B right so we know there's an edge from a to B but this doesn't necessarily mean there's an edge from B to a right we don't see an arrow going back from B to A because the arrow points in de from A to B。

So let's keep them in mind while we're filling so first off let's start with a so does a have a or we could do this。

One of two is you can I think about it as like going through row by row methodically does a have an edge to A does a have an edge B does a have an edge to C so on and so forth or you can just take a look at this graph right so when you take a look at this graph we see that a has a directed edge to B and it has a directed edge to D so what that would look like is we'd have a check mark here and a check mark here。

Okay now when we move on to B， we see that B has an outgoing edge to C so we'd see a check mark here。

 but really important to note like I just mentioned right this is a directed graph just because B is connected to a like a has a path to B doesn't mean that B has a path back to a right we don't see an edge pointing back to A so we'd only mark B to C here。

And then after that， we'll look for C's neighbors， we see that C has an edge going out to F so we'd mark that C has an edge from to F over here then in D we'd say that D has outgoing edges to E and F so we'd check off the boxes here。

😊，Oh oh and D also has an outgoing edge of B sorry I missed that yes so we check off the edge from D to B and then when we moved on to row E we'll see that E only has one outgoing edge to F So we're going to mark that F has zero outgoing edges so there'll actually be no check marks in this row because F has no directed edges to any other nodes and lastly G has one directed edge to F okay。

😊，Cool so that's a matrix an adjacency matrix If we're trying to do an adjacency list how we like to do it is sort of like a map where the keys are the nodes themselves so like node A B C D E FG and they map to a value that's a list of all the nodes that they have edges to so in the example when we start at a we'd see that a has edges to B and D so we'd map a to point to a list containing B and D likewise when we move on to B we'd see that B has an outgoing edge to C so B would map over to a list containing only C。

😊，And C would map to a list containing only F。And likewise。

 you'd see that D would point to a list containing E and F。

 E would point to a list containing just F F points to an empty list。

 and G points to a list only containing F。Okay。😊，4。Okay。

 so for the last part of question one1ie we're asked to write the order in which nodes are visited by DFS preorder and post orderder since this tends to be like a pretty tricky topic for students I just put the pseudocode that I had earlier with the stack and we're going to run through this algorithm when we're trying to determine what's in pre and post orderder okay so we're told to start at a I know it's not on this side but the worksheet says to start at A so what we do when we start at a is we want to put a into our stack to begin with and then run through this loop while stack is not empty we say a is the top node in the stack right a stack is a lasting first out kind of data structure and a is the one we most recently added。

And then wed add a to a visited set and the pre order set Okay， so what that's going to look like is。

When we run through a a is in our stack and then I'm going to use blue here to mark that we've already visited this node。

 Okay， so when we or when I say visit， I really mean like we've marked it and it's easier to think of it as marked here because we're。

We are like。Combining our pre and post order traversals here in this one algorithm。

 it just depends on when you add things to like the respective sets。

 You can think of it however you like， but I think of it as marked or visited。So。

We have a in our stack， and then while stackco is not empty， we said a is the top note in our stack。

 So we added a to the visited， which is why it turned blue。

 and then we also added it to our preorder， right our DfS preorder。

 And now down here we ask ourselves does a have unvisited neighbors if it has an unvisited neighbor。

 we want to push its next unvisited neighbor onto the stack Well。

 we see that A has neighbors B and D， neither of them are blue。

 so neither of them have been marked or visited yet right So what we're going to do here。

Is we're going to push one of these neighbors into the stack。 And in the problem。

 we're told to tie break by。By alphabetical order， so we're going to go with the one that has lower alphabetical order。

 So what we're going to put on the stock next is B， so we're going to push B onto the stock。

And so when we run through the loop one more time。What we're going to do is we're going to see that B is the top node in the stack and then we're going to visit B right so it turns blue and we also add B to our preorder traversal of DFS so far and our stack now contains and and B right now we ask ourselves does B have unvisited neighbors if it does have unvisited neighbors push its next unvisited neighbor onto the stack well B has one unvisited neighbor it's C right it's not marked in blue so we're going to push C onto the stack。

And when we push C onto the stack and we run through this loop again， as the top node in our stack。

 right the most recent node that we put onto our stack。

 we're going to visit it and we're also going to add it to our pre-order traversal and now our stack looks like ABC。

😊，So once again does C have unvisited neighbors yes it does it has F which is not visited so we're going to push F onto our stack right so after that when we push F onto our stack when we run through the loop F is joined going to turn blue right it's going to join our visited set and it's also going to join as the next element in our preorder and so now we have this stack with AB c andF and this is where things start to get a little bit interesting so we're going to run through this algorithm we're going to say F is the top node in our stack it's the most recently added one we visited F we added F to our preorder and does F have unvisited neighbors。

It does not have unvisited neighbors right it doesn't have a directed edge to anywhere so it doesn't have unvisited neighbors so what we're just going to do is we're going to pop F off of the top of the stack and add F to our DFS post order traversal list。

😡，So what that's going to look like is we're going to pop F out here。

And F is going to appear in as the first element in our post order traveral。

 and we've turned green to say that like it's fully out of our stock now， okay？こう。

So now we're left with this stack and while the stack isn't empty。

 we continue on we see that n is our top node in our stack。

 So we're gonna look at our second C oh C was the most recently added element to our stack that we haven't already popped up and it's already been visited。

 It's already been preorder added right we don't need to worry about adding to these sets anymore Does C have any unvisited neighbors that we haven't gone through Well C is only neighbor was F so we don't have any more unvisited neighbors of C So we're going to do is once again we're going pop C off of the top of our stack and add it to the post orderder for our DFS。

 So we're going to say goodbye to C here and C is going to join the postorder DFS over here。Likewise。

 when we run through the loop again while the stack is not empty。

 we're going to see that B is the topmost node in our stack and it's already been visited。

 it's already been added to preorders so we don't need to worry about that but we're asking ourselves does B have any unvisited neighbors it doesn't have any more outgoing edges right we saw that there's an edge from B to C but we already took C out of the stack C's already been visited so we say that B doesn't have any more unvisited neighbors so we're going to pop B out of the stack and add B to the postorder traversal and so we say goodbyebye B and hello in the post-order traversal and B turns screen because it's left the stack right？

Now we're on to a and a is the top node in the stack so we ask ourselves does a have any unvisited neighbors Well a does have a neighbor has D right so the only tie broke with last time so now what we're going to do is we're going to push D onto the stack it hasn't been visited right so after that we're going to add D to our stack and then when we run through the loop again as the top node in our stack we're going to add it to the DFS preorder and also mark it as visited so aD is going to turn blue it's in our stack now as the top node in the stack and it joined the preorder list right？

So we ask ourselves does D have unvisited neighbors well D does have unvisited neighbors it has E right so we have this neighbor F over here but we already visited F so we're not considering those neighbors the neighbor F we're only considering E because it hasn't been visited so we add E onto our stack so we're going have E as the topmost note of our stack next and when we run through our loop again we're going to add E to the preorder to veral and then we are going to market as visited it's going to turn blue。

😊，Great so now that we're focusing on E we ask ourselves does E have any unvisited neighbors well E has the neighbor F but F has already been visited right so we can't really traverse onto F and in fact F has already left the sack so what we're going to do here is we're to pop E off the top of the stack and then add E to the post order traversal list。

😊，So we're going to say goodbye to E here and E is going to join the post order traversal list over there and it's going to turn green to represent that it's left of stock。

 okay？All right， we're almost there， so once again we're going to look at our stock and our stock the top of our stock is D。

And we're asking ourselves， does D you have unvisited neighbors， Well， D has neighbors E and F and B。

 but。All three of these nodes have already been visited right。

 so we don't need to worry about adding more unvisited neighbors onto the stack。

 so what we're going to do is pop D off the stack and then add D onto the post order traveral。😡。

Likewise， when we get to a we'll see that a is the topmost node of the stack there's no more unvisited neighbors of A right B and D have all been visited。

 so we're going to pop a off the stack and then add a to the post order of this graph over here the DFs post orderder and now our stack is empty So now you might be wondering like wait a second don't we have this like graph G not this graph we don't we have this like node G in our graph well you'll notice that G is not actually reachable from a right because this is a directed graph there's no pads that actually take us to G right there is no parent of G So there's a distinction here between like regular Dfs and Dfs that allows restart on unmarked nodes So if we allow Dfs to restart on unmarked nodes a unvisited nodes like G over here then G would be added to the stack and ultimately it would be the last element in both the preorder and the post orderder traverals。

Okay so that was like a bit of an aside about restart yeah like restarting DFs something that I wanted to point out is like I remember when I was a student。

 I didn't fully really understand what like preorder and post orderder meant like what does it mean to process a node or visit a node as soon as it enters a stack or what does it mean to process a note as soon as it leaves the stack hopefully this made a little more sense in the context of here where like we only add things to the post order when we pop it from the stack and we add things to the preorder as soon as they enter the stack that's kind of like the idea here because when you enter a stack then you haven't seen any of its children yet or like it's unvisited children yet first right so we want to preorder process that node versus post orderder post orderder tells us that we want to visit all of our children before we visit ourself right in which case we basically。

Um that would be like visiting all of our children and having no more children to visit will be represented when we pop the element off stack right oh yeah。

 that's just like a bit of intuition for pre and post order traversal and that's it for question one。



![](img/eb60d3fceed9ad95788c61fda22ffe2c_3.png)