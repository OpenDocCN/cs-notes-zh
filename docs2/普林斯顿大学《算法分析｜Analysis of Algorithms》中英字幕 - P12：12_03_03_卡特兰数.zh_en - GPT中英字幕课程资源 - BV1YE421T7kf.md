# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P12：12_03_03_卡特兰数.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/7f2ae6a38cff6139c97623b234314468_0.png)

As a poster child for the application of generating functions。

 next we're going to take a look at the Catalan numbers。

 which are a fundamental sequence of great interest in common toques。

One way to as many applications of the Catalan numbers and I'll give a few。

 so one of the earliest that people thought about was how many different ways are there to take a polygon with n plus two sides and draw lines from one vertex to another and make it all triangles。

 so for example if you have a pentagon， you have all these different ways to triangulate it well actually it's easy just draw from any vertex you draw to the two opposite in the five vertices you get five triangulations or if it's a square you just get two but if it's a hexagon there's lots of possibilities you can do three like that。

 or you can do these n shapes there's lots of possibilities and actually turns out that the number of triangulations of a hexagon is 14。

So that's a number sequence that is described by this recurrence relation over here。in general。

 if we and leave we draw our diagonal and leave k vertices on one side and n minus1 minus k on the other side and is one less because we draw the triangle。

 then you can triangulate those anyway that you want。

 and each one of them independently so it says that the number of triangulations has to satisfy that recurrence relation。

S from 0 to k less than n Tk， TN minus 1 k plus an extra because it's always one way to triangulate the triangle。

So that's a recurrence relation that we're going to take a look at solving but it applies in many other applications。

 here's another application， the so-called gamblerss ruins problem so you're a gambler and you start with $ zero and you make $1 bets and if you win the line goes up。

 there just a graph of amount of money that you have so in this case there's two wins followed by a loss。

 win loss， win loss， two wins and then a bunch of losses。

And the idea is the gambler will keep going until having$ zero dollars makes a bet and loses and then the game's over。

And how many different ways are there for the gambler to do that with say and wins in the sequence in Wallaby and losses too？

And so again， if you try out all the possibilities。

 it turns out that there's only two possibilities if there's two dollars， you can win， lose， win。

 lose， lose， or you can win two， and then lose three。And those are the only two possibilities。

 and there's five different ways for three wins and 14 for four wins。

And same sequence because it satisfies the same recurrence。

 you can just set up the recurrence by the first time the gambler gets back to zero。

 if that happens after K wins， then independently you have a gambler's ruin problems on K and an n minus1 k and it follows the same recurrence。

Here's another one， binary tree structures， so a binary tree is a root node that is connected to two binary trees。

 a tree on the left and a tree on the right。it could be empty what that's called an external node。

 so how many different binary trees are there with end nodes and we'll look in much in a lot of detail at binary trees later on。

So there's two different binary trees with two nodes。

 so that is you got one at the root and you could have a one node tree on the left or a one node tree on the right。

And every node has to have two children and the ones at the bottom have two blank children。

 those are called external nodes。For three， there's five possibilities。

 you have a note at the root and it could be empty on the right with either one of these trees on the left or it could be empty on the left with either one of these trees on the right。

 or you could have two trees of size1， one on either side。

So there's five possibilities for three nodes and similarly there's 14 possibilities for four nodes。

 so you could have empty on the left in any one of the three node trees， empty on the right。

 any one of the three node trees on the left， empty on the left。

 any one of the three node trees on the right， or you can have one on one side and two on the other side in four possible ways。

So again， same number sequence again satisfies the same recurrence if you've got k nodes on the left。

 you're going to have n minus1 minus k nodes on the right and you can try all possibilities on either side。

 so it's got to satisfy the recurrence where t is ns equal to the sum for all k up to n minus1 of Tk tn minus1 minus k plus a delta turn to make it true for zero。

Caalan numbers here's another one， how many trees within nodes a tree is a node connected to a forest of trees to any number of trees。

 so it's not restricted to be just two and again we'll talk in detail later in the course about trees and binary trees but for now I just want to point out all the possibilities and satisfies the same recurrence。

So CatalN numbers describe a lot of combinatorial objects of interest。

So how we're going to solve the cattleal end recurrence with generating functions。

 Well we're going to use the formula。 we' got the recurrence it holds for all in。Now we're going to。

 what's the next step， it's multipied by Z to theN and sum on in？

On the left hand side that gives us T of z that's the generating function for the Catalan numbers on the right hand side we'll get a1 for the delta term on the right。

 and then we get some n blu 0，0 less single K less than n Tk TN minus1。And that looks familiar。

 it is familiar， that's we're going to work backwards from the convolution derivation that we did before。

So now what we'll do is first thing we'll do with switch order of summation。

 so switching order summation means if you're going to try for every value of k。

 then the inner sum is just for n bigger than K。Now in that inner sum will change n to n plus k plus 1。

Change n to n plus k plus 1， n bigger than k， it's n bigger equal to k plus1。

 so that's the same as n bigger and equal to0。And then the t sub n minus1 minus k just becomes t sub n。

 and then we have z to the m plus k plus1。And that gives us a way to split it into independent sums by distributing the k's and the ans。

 And then you can see immediately the 1 Z comes out， and then it's2。

coopies of the generating function T of Z， so that's a backwards convolution that shows us that the cattlealN generating function has to satisfy this functional equation T of z equals 1 plus z times t of z squared。

So we're halfway there， we've got an equation that the generating function has to satisfy。Now。

 a common sense rule for working with generating functions that I want to point out and again。

 it's always worthwhile to check your math with your computer。

 and that includes symbolic calculations like this one。You know the initial values of TFZ。

 we did the examples， so we know that it starts out being 1 plus z plus 2 z squared plus 5 zq plus 14 z4。

Before we go any further we might want to check that this equation that we have really holds and you can do it in pencil and paper or you can use a symbolic mass system and you can see that if you take one plus z times one plus z squared and so forth。

 I just took it out to four terms here， the ones that we know if you multiply them out indeed you get1 plus z plus 2 z square plus5 zq plus 4 z4 and so forth now after a while the terms are no good because we didn't take these terms far enough but still that gives confidence and actually you can bootstrap this to get more terms but it gives confidence that we've got the right equation。

So that's just checking your math with the computer even when it's symbolic。All right。

 so now what we need to do is to extract coefficients to find an expression for the anthcaalan number。

So that's the GF equation， well it's an equation that we know how to solve with the quadratic formula and so that's the solution with the quadratic formula。

 just implying the eighth grade formula and then we have to pick one plus or1 minus and it's going to be the minus。

Just left out that one consideration and that you get from checking with the initial values。

So now how do we deal with that， we expand one over square root of 1 minus4 z we just use the binomial theorem。

 it's 1 minus4 z to the1 half power， so it's the sum of when half choose n 4 z to the n。

And then this one part goes away and and again we can check that from initial values。

 so that's a key step for this generating function。

 we have a solution that uses the quadratic formula， and then we have a an expansion。

 a function that we know how to expand， know how to find coefficients。

So that tells us what t sub n is， it's minus a half when half choose n plus1， minus4 to the n plus1。

 this extra z is what leads to the n plus1。Now that' it's okay。

 it's not totally satisfying because the one half n plus one is maybe not such a familiar function and as' a way to manipulate this to get it to be a little bit more familiar function and actually next time we'll talk about a much better way to continue to manipulate it to get really a concise representation。

 but let's just do just a little more algebra to get this in more of a form that we can people can relate to so。

This is the definition of the binomial coefficient when the upper index for any binomial coefficient。

 we just it's on the bottom is n plus1 factorial and on the top is n plus1 terms where we subtract 012 all the way up to n。

 so that's just the definition and there's the minus1 half and there's the minus4 to the n plus1。

So now what we're going to do is take we have n plus1 terms here and we've got n plus14s and we're going to take a bunch of those。

 we'll take the n plus1 minus2s and multiply them in and one of them kills that and then the others you get 1。

3，5 all the way up to2 n minus1 like that。So that's a slight trick but cleans it up quite a bit and now if you have that then if you fill in the Es。

 so2 to the n is2 over1 times4 over2 and so forth so now we have the odds and the Es and we have an n factorial so that's going to immediately give us two n factorial over n factorial times n factorial which is2 n choose in。



![](img/7f2ae6a38cff6139c97623b234314468_2.png)

So that's a proof that the number of binary trees and end nodes。

 number of general trees and end nodes， the number was triangulated n plus2 gun and so forth。

 the cattle n numbers is one over n plus1 times to and choose in and that's one of the most famous number sequences in commonatorics and we'll see in many cases we explicitly use data structures like trees in practical algorithms and data structures。

 so we need to understand these properties of them and we're going to continue working with the cattle n numbers and several other occasions later on in the course。



![](img/7f2ae6a38cff6139c97623b234314468_4.png)