# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P26：26_06_04_其他树类型.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/b8264fa61619a87760d358fe6fbcbabb_0.png)

There's many other types of trees that have been studied， it's a very huge topic。

 and I've really only talked about a few binary trees and binary search trees。

I talked at the beginning about general trees and how they relate to binary search trees and some of the results translate over on and many of the techniques do as well。

 but we're going to save a lot of that for analytic combinators in part two。

 and we'll do many other examples then。But I do want to talk about the other types of trees that can come up briefly to prepare people for the kinds of ideas that we'll be looking at。

So classically in mathematics mathematicians talk about classic structures known as the free tree。

 that's just a connected graph that has no cycles if you distinguish a root node that's called a rooted tree。

 and then there's ordered tree where the order of subtrees is significant and what we've been talking about what I defined at the beginning is really an ordered tree because usually in computer implementation we pick an order because we have to represent the thing in some way。

In this little diagram illustrates the distinction between these types of trees。

This is five node trees。 there's only three different free trees of five nodes。 again。

 these trees are defined just in terms of their connections， there's no root and there's no order。

So either four other nodes are connected to one， or if there's one node that three are connected to。

 and then there's another one hanging off or they come in a line。

That's the only three free trees of five nodes。If you pick a root。

 but you don't care about the order of the subtrees， then there's nine different rooted trees。

So in the first case。There's no difference， but in this second case。

 you can see that the tree on the left there's a root that's got three children and then the one that's hanging off could be in any one of the three children in the case a rooted trees that's not significant。

 so there's only nine of them， and then as we saw there's 14 a Catalan number of ordered trees where the order is significant。

Now in this diagram， each one of these gives us a counting problem and we'll see that people have solved this counting problem for these types of trees and also you can label them and treat them as labeled structures and then have orders on the labels and many other kinds of problems come up and we'll examine plenty of those in inlytic combinatorics。

呃。So stay tuned for part two of the course。In algorithmics there's plenty of natural ideas that come up as well。

 so what about having more than two children I why not have exactly three children or exactly four and there's plenty of applications where we might want to do that so there's the idea of the TA tree where each node has exactly T children。

Or maybe there's a bound on the number of children， so each note has n most tea children。

 but not necessarily exactly， so that's a tea restricted tree。And then there's something called the2。

3 tree which is actually the method of choice in symbol table implementations and that also generalizes to multiple and that's where you can have more than one key per node it's kind of a strange structure but actually it's easy to represent as a binary tree and I'll show that in a second and again all of these are going to give rise to enumeration problems for any value of T past length and all sorts of other things that we might want to analyze all these different variations just so far have talked about 12 different types of trees and more emphasize the need why we need general tools like analytic combinatorics that can get us the solutions to problems without necessarily going into the details is's why we need the general theorems that were that we've talked about。

A little bit and then we're going to talk about more later。

You can already easily see how easy it is to specify structures like this。

 I'm not writing it down here， but you can certainly。

Take the defining construction for binary trees and extend that to do turnernary trees or forry trees。

 and now you know that if you can do that， then you have a generating function equation。Now。

 a lot of these generating function equations are not as simple to solve or get asymptotics for as the catalan。

 but we will learn techniques for that。But at least I think people in this course are convinced that we can get to generating functions pretty quickly for all these types of structures。

But again， that's a topic for part two of the course。

I want to finish just by talking about one unsolved problem that is related to the things that we've been talking about。

 so in the real world， it's not enough to rest。Our faith in the use of an algorithm on this assumption that the keys are going to come in in random order。

 they might not come in random order and we want guaranteed performance and there's a method for getting guaranteed performance that's based on trees called balanced trees that's a method of choice。

They're the method of choice because they're extremely simple search code， in fact you can use BSTs。

 you can represent balance trees with VSTs， so much of the code is very much the same there's only a slight extra overhead for insertion and you can read all the details in section 3。

3 of algorithms。And it guarantees with that slight overhead。

 you can guarantee that no matter how the keys are inserted。

 the height is going to be less than two log n， so it's going to be less than twice the optimal guaranteed。

 no matter what the insertion is。And most algorithms use2，3 or 2，3，4 tree representations。

 which actually translate right to binary trees。So and again without going into the detail。

 this is just an example of leftleaing red black trees。

 which are the ones that are described in detail in algorithms and that's the two。

 three tree and don't need to even explain what that is。

 there's the binary tree representation of that where sometimes you have two keys per node but you can represent that just by left leaning node with a special link on it。

 and so now we have binary trees with that little extra overhead that we have to maintain those links in a particular way。

 but otherwise that's the method of choice for symbol tables。

So now the question is if you have a even though we have the guarantee。

 we're still interested in knowing the performance。

 if we assume that the keys come in randomly because again that's a reasonable model。

 it would be better to know that the guaranteed height was asymptotic to log in with a coefficient of one。

 and it'd be twice as fast， when you've got something that's in the inner loop of a major computation。

 speeding up by a factor of two is important。So we'd still like to know the answer to this question of what's the average cost of a balanced tree built from a random permutation？

呃。Now， again， that's not a property of trees。 That's a property of the permutation and the algorithm。

 The tree is just a container for the data。So this plot that we've been using as our logo is related to that problem。

 there's one kind of balanced tree called an AVL tree which again represents a binary tree and this is the normalized plot of the probability that the root is of rank K in a random AVL tree again that's random tree model just like random cattlean tree model you can specify what is an AVL tree can take each tree equally likely can develop generating function relationships and produce that plot。

And what this plot signifies is it shows that sometimes the root is in the middle。

 but sometimes it's like one/ third， two/ thirds， there's two peaks。

 it's quite a fascinating plot to stare at。So thats is that one， remember。

 and that's good because remember for Rnda binary trees。

 we had the cattleal and distribution where it was not balanced at all。

 it was more likely to be unbalanced。And for random permutations it's just flat。

 so this looks good because at least it's trying to make the root at the middle。

 but still our challenge is to analytically characterize that。And that's an unsolved problem。

 there's that plot and this is a empirical plot for LLRB trees。

It seems to have some of the same characteristics， but still we're not close to understanding how to determine。

The path length of mouse tree built from a random permutation， the other one random AL tree and 2。

3 tree has been studied with analytic combinatorics and we'll touch briefly on that in part two。Okay。

 so that's a brief summary of other types of trees。

 now I'll talk about a few exercises that you might do before the next lecture。

So there's plenty of exercises on tree enumeration to check out how comfortable you are with using the symbolic method for enumeration problems。

So this one is， so we've got a lot of forests， maybe we're interested only in forests that have no singleleton nodes。

So the question is， what's the proportion of forests with n nodes that have no trees in them consisting of a single note？

And this sketch shows that for one，2，3， and4， the answer is zero， half， two， fifths， and three。

 seventh， respectively， so find an asymptotic formula for that。And again， that's just using， again。

 the beauty of the symbolic method is you can take the basic derivation and you can modify it and still the basic structure of it follows through to give you a generating function equation that you can find asymptootics for or explicit forms。

And this is just practice in doing that。This is just。

A computation based on our observation about permutations in binary search trees。

 what's the chance that you get a perfectly balanced binary tree and that's just a fun computation。

And then this is the same kind of idea we did parameters from trees before。

 this is parameters from BSTs built from a random permutation。So。

The red ones are the average number of internal nodes whose children are both internal and the blue ones are the average number of internal nodes at one internal and one external。

For random cattlealan trees we did before we got the solution to that constant fraction。

 and so this is to compute that for random binary search trees。So in lecture five。

 we talked about that， and now you can compare these results against what we got in lecture5。

So that's the reading for the next lecture， another thing that some people might want to do is to run some experiments to validate the mathematical results we've talked about。

For example， generate some random permutations and build binary search trees and look at the average that you get and check that it's2 n natural log again。

 it's always worthwhile to do that。

![](img/b8264fa61619a87760d358fe6fbcbabb_2.png)

It's a little bit of programming but many programmers that's no problem at all and maybe a little harder is to try to do the same thing for random binary trees are that internal path lengths and Sc of pi in。

 how close are they， how big does Z have to get to be an asymptotic and so forth。

 it's always worthwhile to run experiments and some people might enjoy doing that？And then again。

 just to check your understanding the material， it's a good idea to try to write up solutions to some exercises like the ones that I gave。

That's an introduction to trees。

![](img/b8264fa61619a87760d358fe6fbcbabb_4.png)