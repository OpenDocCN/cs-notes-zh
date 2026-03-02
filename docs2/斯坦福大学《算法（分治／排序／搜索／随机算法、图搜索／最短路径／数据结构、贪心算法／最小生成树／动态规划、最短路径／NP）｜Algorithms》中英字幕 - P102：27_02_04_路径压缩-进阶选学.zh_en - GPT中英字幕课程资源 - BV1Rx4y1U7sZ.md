# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P102：27_02_04_路径压缩-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/a096bf816c4aa5d57e05cac415d845a4_0.png)

So I don't blame you if you're feeling a little bit restless。

 You've now watched three videos about this alternative approach to the union find data structure based on lazy unions。

 And frankly， we don't have any tangible things to show for it。

 We already had a perfectly fine implementation of this data structure based on eager unions。

 that gave us constant time fines。 And yeah， union could be linear in the worst case。

 but it was logarithmic on average over a sequence of unions。

 And so now we have this other implementation。 Both of our operations are requiring logarithmic time。

 It's true。 It's a worst case bound and its true union by rank is pretty cool。 But still。

 the bottom line up to this point is not that compelling。

 But I've still got another trick up my sleeve。 and just watch what happens once we employ a second optimization known as path compression。

😊，So the optimization is very natural， I suspect many a serious programmer would come up with this on their own if they were tasked with implementing union find with union by rank。

So to motivate this optimization， let's think about what would be our worst nightmare as someone maintaining such a data structure and hoping for good performance。

 Well， remember， the running time of a find is proportional to the number of parent point you have to traverse。

 that is disproportal to the depth of the object at which it's invoked。

 So what's the worst case find look like where it's going to be at a leaf。 And moreover。

 it's going to be a leaf which is furthest away from its corresponding roots。 Now， on the one hand。

 we're using union by rank。 So we know that this depth can't be too bad。

 We know it's going to be at most big o of log n。 However。

 there will be examples there will in general be leafs that our theta of log n hops away from their root。

 And for all we know we're just going to get those endless sequence of find operations where every single one is invoked on a leaf that's a log n number of hops away from its root。

 So for example， in the pink tree that I've shown on the upper right of the slide maybe someone just keeps searching for the object keeps invoking find from the object one over and over and over again。

 and then we're going to be suffering a log number of steps every single。Operation。

But if you think about it， it's totally pointless to keep redoing the work of previous finds to keep reversing the same parent pointers over and over again。

 So， for example， in the pink tree that I've shown in the upper right。

 imagine that find is invoked from object one。 So then we traversed the three parent pointers。

 We discover the ancestors4 and 6 before terminating at 7。

 and we discover that 7 is the leader or the root corresponding to the object 1。 Now， remember。

 we do not care that four and 6 or ancestors of one。 That is uninteresting。

 We only visited them to discover what we actually cared about that 7 is the leader the root corresponding to one。

 Well， but let's just cache that information。 Now that we've computed it。

 So this is now basically reconstructing the eager union find implementation。

 Let's just rewire one's parent pointer to point straight to 7。

 We don't need to recompute4 and 6 in some later find operation。And more generally。

 after we've invoked Find from object1， we may as well rewire For's parent pointer as well to point directly to its leader7。

So that then is path compression when find is invoked from some node X and you traverse parent pointers from X up to its root。

 call it R for every object that you visit along this path from X to R you rewire the parent pointer to point directly to R So R doesn't have its parent pointer changed just still points to itself。

 the penultimate object on this path doesn't have its parent pointer changed。

 it already was pointing to the root R， but anything below the root and its immediate descendant on this path from X will have its parent point updated and it be updated to point directly to R Now we couldn't get away with this if the tree had to be binary。

 but it doesn't have to be binary， we couldn't get away with this if we had to satisfy some other constraint like a searchry property。

 but we don't so nothing's stopping us from just casting this information about who everyone's leaders R because that's really the only information we're responsible from exporting from this union find data structure。

So pictorially if you like thinking about the trees， in effect。

 what path compression does is make the trees shallower and more bushy。

 so in our example on the upper right it rips out one and four and makes them immediate descendants of the root 7。

Refer to think in terms of the array representation。 And remember， in the array representation。

 the array index for I is recording the parent of the object I。 So in our pink tree 5，6 and 7。

 all  point to 7， they' all have parent 7。Whereas two and three have parent five。

Four has the parent 6 and one has the parent 4， and after applying path and compression following a find and vote of the object1。

 one and four are redirected to have parent 7。So what are the pros and cons of the path compression optimization well the con side is quite minor。

 really we're just doing a little multitasking on find and that introduces a small constant factor overhead we are already doing work proportional to the number of hops on the path from X to its root and we're still just doing constant work for each node on that path we're doing an extra constant work for each node after the fact to rewire the parent pointer to point to the root。

The pro should be obvious， this is going to speed up all subsequent find operations you're really making sure you don't redo redundant work。

 you don't traverse parent pointers over and over and over again so what's clear is that you know finds will speed up what's really not clear is whether they'll speed up by a lot so is this only going to affect the performance of the find operation by say a factor of two where we get something fundamentally better than the logarithmic performance we were stuck with without path compression。

So let me spend a slide on the subtle point of how ranks interact with the path compression optimization。

So the plan is we're going to manipulate rank fields with path compression in exactly the same way as we did when we didn't have path compression。

So how did we manipulate them previously Well at the birth of the Union find data structure。

 everybody has rank zero ranks never change except possibly when you do a union， when you do a union。

 you look at the roots of the two objects whose groups you have to union you look at their ranks if one of them has strictly bigger rank that becomes the root of your new merged tree。

 the root with a smaller rank is installed as a child underneath if you union two roots that have exactly the same rank。

 you pick arbitrarily which of them is the new root and you bump up its rank by one that is how we manipulated ranks before。

 that is exactly how we're going to manipulate them now。So in particular。

 when we apply path compression， when we rewire parent pointers following a find。

 we do not touch anybody's ranks， we leave them all exactly the same， so again。

 ranks only change in one specific case in a very specific way， namely during a union。

 when we merge two trees that have exactly the same rank。

 and when we do that kind of union that kind of merge whichever of the old roots winds up being the new root。

 we bump up its rank by one， that is the only modification we ever make to any ranks。

Now it might bother you that we don't recompute the ranks when we apply path compression in a way。

 I sort of hope it does bother you because by not recomputing ranks by just manipulating them exactly as before。

 we're actually losing the semantics of what ranks meant in the previous video。

 so the key invariant we had that ranks exactly represented worstcase search time to that object is now lost。

The easiest way to see what I'm talking about is probably through an example。

 so let me redraw the same tree we had on the previous slide。

 both before and after we apply path compression following a find in voked at the object one。

So what I've done here is in the top tree before the path compressions been applied。

 I've labeled ranks just as they were in the previous video。

 so for each node in the top tree its rank is equal to the longest path from a leaf to that node then I applied path compression from the object one resulting in the bushier more shallow tree on the bottom and as I said I did not touch anybody's ranks when I applied this path compression I didn't do any recomputs and you'll see now we've lost the semantics for the ranks just to give a simple example there are now leaves that don't have rank zero that have ranks strictly bigger than zero。

So what we can say is that for every node， the rank is an upper bound。

 not necessarily exactly the same as， but at least as big as the longest path from a leaf to that node。

 but because of the shortcuts that we've installed。

 we no longer have the equality that we had before。There is good news。 However。

 we can definitely salvage a lot of the technology that we developed in the last video for the union by rank analysis and applied fruitfully here to the case with path compression。

 In particular， any statement that we made last video that talks only about the ranks of objects and not about their parent pointers per se that will be as true with path compression as without why Well。

 think about making two copies of a unionfin data structure。

 exactly the same set of objects and nowll run them in parallel on exactly the same sequence of union and find operations。

 So by definition， we manipulate the ranks of objects in exactly the same way in the two copies。

 It doesn't matter if this path compression or not。 So at all moments in time。

 every object will have exactly the same rank in one copy as it does in the other copy。

 Pa compression or no doesn't matter。 exactly the same ranks。

 What's going to be different in the two copies are the parent pointers。 They're in some sense。

 going to be further along。 they're going point further up into the tree in the copy。😊。

With path compression， but no matter any statement that's purely about ranks。

 it's going to be equally well true with or without path compression。So in particular。

 remember the rank lemma that we proved in the last video that says there's a most n over2 to the R objects of rank R that was true without path compression。

 it's going to be true with path compression， and we're going to use it in the forthcoming analysis。

Another fact which is still true with path compression。

 in fact in some sense it's only more true with path compression is that whenever you traverse a parent pointer you will get to a node with strictly larger rank。

 remember in the last video we said as you go up toward the root you're going to see a strictly increasing sequence of ranks here each pointer with path compression represents a sequence of pointers without path compression so certainly you will still only be increasing in rank every time you traverse a pointer。

Let's now quantify the benefit of path compression by proving new performance guarantees on the operations in this union find data structure and finally the running time bounds are going to blow away the logarithmic bound that we had when we were only doing union by rank without path compression。

We're going to do the analysis in two steps and it's going to be historically accurate in the sense that I'm first going to show you a theorem by Hocroft and Omen。

 which gives an excellent but not quite optimal bound on the performance of this Union find data structure。

 and then we're going to build on the Hcroft Omen ideas to prove Ts even better bound on the performance of this data structure。

So here is the performance guarantee that Hopcroft and Oman proved back in 1973 about 40 years ago。

 they said consider a union find data structure implemented as we've been discussing， lazy unions。

 union by rank， path compression。Consider an arbitrary sequence of M find and union operations。

 and suppose the data structure contains n objects。

 Then the total work that the data structure does to process this entire sequence of M operations is M times log star of n。

What is log star of and you ask， well， it's the iterated logarithm operator。 So by analogy。

 remember when we first demystified the logarithm that way back at the beginning of part1。

 we notice the log base two of a number is just， well， you type that number into your calculator。

 you count the number of times you divide by two until the result drops below one。 So log star。

 you type the number n into your calculator， you count the number of times you need to hit log before the result drops below one。

 So it totally boggles the mind just how slowly this log star function grows。 In fact。

 let me give you a quick quiz just to make sure that you appreciate the glacial growth of the log star function。

So the correct answer is B。 It is5。 and you should probably spend a couple seconds just reflecting on how absurd this is。

 right So you take this ridiculous number 2 to the 65000。

 remember the number of atoms in the known universe estimated is way smaller than this。

 It's just 10 to 80。 So you take this ridiculous number， you apply the log star function。

 You get back5。 Why do you get back 5。 Well， take logger than once。 When you get back 65536。

 Also known as2 to the 16。 So you take log again， you get back 16， also known as 2 to the4。

 you take log again， you get back 4， also known as2 to the2。 you take log again。

 you get back a2 and then one more time gets you down to 1。

So you think of log star as the inverse of the tower function where the tower function takes。

 think of it as a positive integer t and it just raises two to the two to the two to the two to the two t times。

And this in particular， shows that log star， despite its glacial growth。

 is not bounded by a constant。 This function is not big O of1 for any constant C you can think of。

 I can， in principle， exhibit a large enough n so that log star of my N is bigger than your C。Namely。

 I can just set n to be2 to the two to the two to the so on。

 C times log star of that will be at least C。So that's the Hcroft O performance guarantee that on average。

 over a sequence of M union and find operations， you spend only this ridiculously small logstar and amount per operation we're going to prove it in the next video。



![](img/a096bf816c4aa5d57e05cac415d845a4_2.png)