# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P103：28_02_05_路径压缩-Hopcroft-Ullman分析一-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/7cf79afc05f3221682fa75317bb8c628_0.png)

In this video， we're going to prove our first performance guarantee on the Union find data structure with path compression。

 This is the bound first established by Hocroft and Omen。

Let me briefly remind you about the guarantee。 consider a union fine data structure where you're using lazy unions。

 you're doing union by a rank and you're using the path compression optimization。

 Consider an arbitrary sequence， say of M union and find operations。

 The guarantee is that over the course of this sequence of operations。

 the total work that you do as at most M， the number of operations times the glacierly growing function log star of n。

 Remember， a log star of n is defined as the number of times you have to apply the logarithm function to n before you get a result。

 which is below1。 remember2 raised to the 65536。 a totally absurd number。

 log star of that number is merely5。So the theorem is true， no matter what M is。

 no matter how many operations you do， whether you do very few， whether you do a whole lot of them。

 I'm going to focus on the interesting case where M is at least asymptotically as big as n。

 where M is omega of n I'll let you think through in the privacy of your own home。

 why the arguments that we're about to see imply the theorem no matter what M is。

So one final comment about this guarantee before we turn to its proof。

 notice what the theorem is not saying the theorem is not saying that every single one of these find and union operations runs in biggo of log star n time。

 and that's because that statement in general， which would be stronger。 that statement is false。

 there are going to be operations in general that take more than log star and time。 Now。

 on the one hand， we know no operations going to be slower than logarithmic time。

 even when we didn't have path compression。 no operations was worse than log n time and we're not going to do any worse with path compression。

 So the worst case time bound is log n， but some operations may indeed run that slowly。

 but over a sequence of m operations， the average amount of work we do on a per operation basis is only log star of n。

 This is exactly the sort of so-called amortized analysis that we did in our very first union find implementation with eager unions。

 we agreed that particular unions might。Takeake linear time。

 but over a sequence of unions we spent only logarithmic time。

 so the same thing is here with the exception that we're getting a radically better on average running time bound of logstar N over a sequence。

So before I launch into the proof details， let's just spend one slide talking a little bit about the proof plan and in particular。

 what is the intuition behind the performance that we're trying to make precise。

 that we're trying to encode in a mathematical way in the proof that's about to follow。Well。

 if we're hoping to prove a bound better than log n what we were stuck with without path compression。

 it better be the case that installing all these shortcuts really qualitatively speeds up fines and unions。

And on some level， it's sort of clear that things have to be sped up or replacing an old chain of pointers with a single pointer so you can only go faster。

 but how do we keep track of this progress， how do we compile this intuition and make it into a rigorous guarantee。

So here's the idea， let's focus on an object X， which is no longer a root at this point。

 its parent is somebody other than itself。

![](img/7cf79afc05f3221682fa75317bb8c628_2.png)

And one thing I want you to remember from our union by rank analysis is that once an object is nu is not a root。

 its rank is frozen forevermore。 Now， we prove that in the context when there was no path compression。

 But again， remember， we manipulate ranks in exactly the same way when there is path compression。

 So that's still true。 If you're an object and you're no longer a root。

 there is no way your rank will ever change again。Now。

 what we're certainly hoping is true is that finds that originate at， say。

 this object X are running fast， not only that， but they should even be getting faster and faster as time goes on because we're doing more and more path compression。

So here's the big idea。 The way we're going to reason about the worst case running time of the find operation or equivalently the longest sequence of parent pointers we might have to traverse to get to a root is we're going to think about the sequence of ranks that we observe as we traverse these parent pointers from an object X up to the root。

 Let me give you an example。 So it would be the worst case situation。

 Well the worst case would be if we have a data structure and let's say the maximum rank is something like 100。

 the worst case sequence of ranks， the longest sequence wed ever see would be if we start a fine operation at an object with rank 0。

 we traverse a parent pointer we get to its parent。 it has rank1， we traverse its parent。

 it has rank2 then3 then 4 and so on all the way up to 100。 Now。

 remember ranks half to strictly increase whenever we traverse a parent pointer As we discuss that was true wither without path compression。

 So in the worst case situation to go from0 to 100， you have to traverse 100 pointers。

So that' would be a bummer， wouldn't it be nice if every time we traversed a parent pointer。

 the rank increased not just by one， but by a much bigger number。 So for example。

 if we went from 0 to 10 to 20 to 30 to 40 and so on。

 that would guarantee that we get to the max rank node 100 and only 10 steps So again。

 the bottom line is if we can have a better larger。

 lower bound on the gap in ranks between an object and its parent that implies more rapid progress through the possible ranks of the nodes that we could see and it translates to faster fines to fewer parent pointer traversals。

So with that idea in mind that big gaps between ranks imply rapid progress。

 I want to propose as a progress measure for a given non root object X， the gap between X's rank。

 which again remember is frozen forevermore and the rank of its current parent。

So this progress measure is a good one for two reasons first as we just discussed。

 if you have a handle on this gap， if you can lower bound it。

 then that gives you an upper bound on the search time Secondly。

 this gap allows us to quantify the benefit of path compression of installing these shortcuts specifically whenever you install a new shortcut you rewire an object's parent pointer to point higher up in the tree。

 its new parent is going to have rank strictly bigger than its old one。

 that means this gap is only going to get bigger summarizing path compression improves this progress measure。

That is， if an object X previously had a parent P and then has its parent pointer rewired to a different node p prime。

 the rank of P prime is bigger than the rank of P。And just to make sure this is crystal clear。

 let's just draw a couple of cartoon examples。So first just in the abstract。

 if you think about an object X， suppose it has some parent P and suppose the root of the tree is some p prime so some ancestors strictly further up in the tree。

 remember ranks always increase as you go up the tree as you follow the parent pointers so that means P's rank is strictly bigger than X P primes rank is the important thing is strictly bigger than P so when you rewire x's parent pointer to point from P no longer but rather to P prime it acquires a new parent and its new parent is an ancestor of its old oneergo it must have strictly bigger rank for that reason the gap between x's rank which is fixed forever more and the rank of its new parent。

 that gap is bigger than the gap between its rank and the rank of its old parent。

You can also see this effect in action with the running seven object example we were using in the last video。

So I've shown that example that tree in pink both before and after path compression and again。

 before path compression， I just defined the ranks as re union by rank so that the rank of each node is equal to the longest path from a leaf to that node。

 and then of course we don't change the ranks when we apply path compression and what do we observe where exactly two of the objects had their parent pointer rewired。

 namely objects one and4 had their parent pointer rewired to point directly to7。

 and as a consequence， the gap in rank between object one and its parent has leaped from merely one。

 the difference each rank and the rank of4 up to three。

 the difference between its rank and that of its new parent 7。 Similarlyly， object4。

 its rank gap has jumped from one to2 It rank is only one less than its old parent 6。

 but it's two less than that of its new parent 7。So believe it or not。

 we actually have the two crucial building blocks for the Hocroft Oman analysis Build block number one is the rank lemma that we discussed a couple of videos ago。

 the fact that with or without path compression， you can't have too many objects with a given rank R and we have most n over2 to the R the second building block is the one we just covered that every time you update a parent pointer under path compression the gap has to grow between the rank of that object and the rank of its new parent the rest of the proof is just an optimal exploitation of those two building blocks。

 let me now show you the details。