# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P112：37_03_06_正确性证明一.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

In this video， we'll establish the correctness of Huffman's algorithm。

 meaning that that greedy algorithm always computes the prefix free binary code that minimizes the average encoding length。



![](img/52e21c831703317d434dde1bac3e7412_1.png)

Let me also remind you of our expression for the average encoding length in terms of a tree capital T。

We'll be working with this expression quite a bit in this proof， so we average over the symbols。

 so we sum over the symbol's I in the alphabet capital sigma。

 we weight the various terms by the frequencies which are given as part of the input and remember that the encoding length that we're producing for a given symbol I is exactly the same as the depth of the corresponding leaf in the tree capital T。

So I quite like the proof of Huffman's theorem。 It's a cool proof and we will give us an opportunity to revisit the themes that we've been studying in proving the correctness of various greedy algorithms at a high level。

 we're going to proceed by induction induction on the size N of the alphabet sigma so there's a vague parallel you could draw with how we proved say Dyster's algorithm correct back in part1 where by induction we show that each successive iteration of the algorithm is correct assuming that the previous ones were but in the inductive step。

 we're going to use an exchange argument， so to justify each of our mergers。

 we're going to argue that any optimal solution can be massaged into one that looks more like ours without making it any worse and that's how we argue that each of our individual mergers is in fact a reasonable idea。

 a good idea。

![](img/52e21c831703317d434dde1bac3e7412_3.png)

So more precisely， we're going to go by induction on the size end of the alphabet。

 I'm going to assume to make the problem non trivialvi that the alphabet size is at least two。

So as in any proof by induction we begin with the base case and then we do the inductive step wherein we can assume the inductive hypothesis。

 so the base case is when we just have a two letter alphabet。

 if you go back to Huffman's algorithm you'll see that it does the obvious thing in the base case so just outputs a tree that encodes one of the symbols with a letter0 and one of the symbols just with a bit1 and that's the best you can do you need a bit to encode every symbol and that tree uses exactly one bit for each symbol so Huffman's algorithm is optimal in that trivial special case。

So for the inductive set， we focus on an arbitrary problem instance where the alphabet size is at least three。

Now， of course， whenever you're doing a proof by induction。

 the thing you've really got going for you is the inductive hypothesis。

 you assume that the assertion that you're trying to prove in this case。

 correctness of Hpman's algorithm is true for all smaller values of N that is we're going assume that if we invoke the algorithm on any smaller input。

 as of course we do in this recursive algorithm， we get to assume that the algorithm returns the correct solution to that smaller subproble。

So to understand how we're going to pass from the inductive hypothesis。

 so this assumption that we're correct on all smaller inputs to the inductive step。

 the assertion that we're correct on the current input。

 we need to take a closer look at how the original input with its alphabet sigma relates to the smaller subproblem with the smaller alphabet sigma prime with the two letters fused into one。

 which is the one that we solve correctly by assumption recursively。

So recall our notation from the pseudocode for Huffman's algorithm。



![](img/52e21c831703317d434dde1bac3e7412_5.png)

What the algorithm does is take the two symbols with the smallest frequencies。

 and let's call those two symbols A and B， and it replaces those two symbols with a single symbol。

 A B， sort of meta symbol representing the presence of either A or B。

 We also in the quiz discussed how the sensible frequency for this new meta symbol A B is the sum of the frequency of A and B。



![](img/52e21c831703317d434dde1bac3e7412_7.png)

Last video， when we were developing our intuition for what a greedy algorithm for successive bottom up mergers might look like。

 we noticed that when you merge two symbols A and B。

 what you're really doing is committing to outputting a tree at the end of the day at the end of your algorithm in which the symbols A and B appear as siblings in which they have exactly the same parent。

 Therefore， there is an exact correspondence， one and one correspondence between on the one hand trees whose leaves are labeled with the symbols in Sigma prime。

 so that is there is no leaf labeled A， there's no leaf labeled B， there's instead one labeled AB。

 So there's a correspondence between those kinds of trees labels at the leaves corresponding to Sigma prime and trees for the original alphabets sigma in which the symbols A and B are Ss in which they have exactly the same parent。

Given a tree as shown in the left picture that is given a tree4 T prime。

 the leaves labeled according to Sigma prime， you can。

 and this is in fact exactly what we do in Huffman's algorithm。

 split the leaf with the metal symbol AB making an internal node and give it two leaves with labels A and B that produces a tree of the form on the right。

 conversely given a tree of the form on the right that is its leaves are labeled according to Sigma and just so happens that A and B show up as leaves of that tree。

 you can produce a tree for Sigma prime just by contracting A and B together so sucking up A and B into their parent and labeling the parent AB so you can go back and forth between these two types of trees。

 one arbitrary trees for Sigma prime and trees of a special kind for sigma。

 trees in which A and B happen to be siblings。This subset of trees for sigma are important enough to be given its own notation。

 So let me denote by capital X sub A B， the trees with las labeled， according to sigma。

 in which it just so happens that A And B appear as siblings。 So that'll be some trees for sigma。

 but not all of them。 only the ones in which A and B are siblings。



![](img/52e21c831703317d434dde1bac3e7412_9.png)

So this correspondence between solutions to the smaller sub problemblem and solutions of a particular form for the original problem has an important property。

 namely it preserves the objective function value， it preserves the average encoding length Okay that's not quite true。

 but it's almost true it's good enough for our purposes。

 it preserves the average encoding length up to a fixed constant。

 so let me show you the computation which demonstrates that point。

So consider any pair of matched trees T prime and T and by matched。

 I just mean T prime is any old tree whose leaves are labeled according to sigma prime and T is the tree you would obtain if you split the leaf with metallabel AB in the usual way。

 you replace it with an internal node and children with labels A and B so that's going to be the corresponding tree capital T so take any such matched pair and let's look at the difference between their average encoding length。

Now remember the average encoding length of a tree is just a sum over the symbols of the relevant alphabet and what we got going for us here is that sigma and sigma prime are almost exactly the same right so the only difference is sigma prime has the metas symbol A B。

 whereas sigma has the individual symbols A and B。 Furthermore。

 the two trees T and t prime are almost exactly the same the only difference being the t prime has this leaf with the metalabel A B。

 whereas t has two corresponding nodes， one level down with the labels A and B。

 So when we take the difference of these two sums， everything cancels out except that the tree T contributes two sumands。

 one for the leaf with label A， one for the leaf with label B。

 and the tree t prime contributes with a minus sign one sumand that corresponding to the leaf with label A B。

 So when the dust clears and we cancel out all the terms what we're left with is。

The term for the leaf A and with a frequency of a times the depth of the leaf A in the tree T。

A similar term for the leaf with label B in the tree T。And then with a minus sign。

 the frequency of the meta label AB in the times its depth in the tree T prime。

But we are certainly not done with our simplifications。

 There is a strong relationship between the frequencies that we're staring at and a strong relationship between these various depths。

Let's begin with the frequencies。 How did we define the frequency of the meta symbolble A B。

 Well remember our quiz， it made sense to define it as the sum of the frequencies of A and B。

What about the depths， Well， you know， this symbol A B is at whatever depth it is in the tree T prime。

 say it's a depth 10， something like that。 Remember。

 T is obtained from T prime simply by splitting this leaf A B and giving a two nude children with symbols A And B。

 So if the meta symbol A B was a depth 10 in T prime。

 then the leaves A and B are going to be a depth 11 in T。

 So the depth is simply one more than whatever it was previously in the tree T prime。

So these relationships are going to result in a second wave of cancellations。

 so just to make that crystal clear， let's call the depth of A B in T prime D。

 so D is what I was calling 10 earlier， so A and B are both a depth D plus1 in the tree T。

So the first term becomes the frequency of a times the depth d plus 1。

 the second term becomes the frequency of B plus the depth D plus 1。

 and then the third term becomes the sum of the frequencies of A and B， times the depth D。

 and when the dust settles yet again we are left with a constant PA plus PB so the sums of two frequencies。

And one thing I want you to really understand is that the difference between these two average encoding length is just some constant。

 it does not depend on which trees we started with。

 so if we choose a perfectly balanced tree and we do this difference， we get some constant like 0。

1 if we choose some totally different pair of trees that are really lopsided and we take this difference。

 we still get 0。1 exactly the same thing。So this fulfills the promise I gave you earlier that not only do we have this natural correspondence between the one hand trees labeled with sigma prime and trees of a certain type labeled according to sigma。

 namely those in which A and B appears siblings， but the correspondence preserves average andco length。

 okay， it doesn't quite preserve the averageaging coding length。

 but it preserves it up to a universal constant， and that's going to be good enough for our purposes as we'll see in a sec。

