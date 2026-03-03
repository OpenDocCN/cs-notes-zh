# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P123：48_04_02_动态规划算法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/9bceb64f3377371fcbc735e418931afd_0.png)

So now that we understand that the optimal solution to the sequence element problem has to be only one of three candidates。

 we're going to be easily able to formulate a recurrence。

 identify the relevant subproblem and derive an efficient dynamic programming algorithm for the problem。

So here is the culmination of our work on the previous video。

 We thought about an optimal alignment of some pair of strings X and Y。

 and we noticed that there are three cases for the contents of the final position。

 Either there's no gaps or there's a gap on top or there's a gap on the bottom。 In case1。

 where there's no gaps， X M and y and get matched， and we proved that the induced alignment。

 which is of this smaller strings， X prime and y prime has to be optimal in its own right。

 In the second case where the character， little X sub M gets matched with a gap。

 the induced alignment， this time of x prime and Y has to be optimal in its own right。

 And in the third case， where little y sub M gets matched with a gap。

 the induced alignment now of x and Y prime must。Optimal。

 so one way to think about this kind of assertion is it says that the optimal solution to a problem to a sequence alignment problem depends only on the solutions to three different smaller subproblems。

 one involving X prime and y prime with characters peeled off of both of the strings。

 one involving x prime and y and one involving x and y prime， but in all of the cases。

 all that we care about are sub problemsblem in which a single character was peeled off from the right from one or both of the strings that we started with。

And the situation is very similar to in our previous two examples relateded independent sets on line graphs and the Napsack problem and the independent set problem。

 whenever we only cared about subprom obtained by plucking off either one or two vertices from the given line graph So all we ever cared about were prefixes of the original line graph in the Napsack problem we got subproble by plucking off the last item and perhaps also reducing the NApssack capacity by some integral amount。

 So there were two dimensions in the Napsack problem for which subproble could decrease in size the number of items and the residual NApssack capacity。

 So we used two parameters to keep track of the subpro what we cared about were all possible prefixes of the items and all possible residual integral capacities at most the original Napsack capacity So what's up in the sequence alignment problem or here subproblem get smaller by plucking a character off of the first string and or the second string So again there are two ways in which the subproblem could get smaller either the first string or the second string So we'll again use two different parameters。

 one to figure out。How much we've plucked off of the first string。

 the second one to figure out how much we've pucked off of the second string， but all we care about。

 the only relevant subproblems involve prefixes of the two original input strings， X and Y。That is。

 the only sub problems that we care about have the form X I， Y J。

 or X I denotes the first I letters of capital X， some prefix of x， and Yj denotes some prefix of y。

 the first J letters of y。So let's now move from the subpro we're going to use in our dynamic programming algorithm to the recurrence that we're going to use。

 and the recurrence really all it does is compile our understanding of the optimal solution and how it depends on the solution to smaller subprom into an easy to use mathematical formula。

So I'll use the notation piece of IJ for the value of the optimal solution to the corresponding sub problem。

 the one involving the prefix XI and the prefix Yj。And so for a given set of positive values for INJ。

 what is PIJ， Well， there are three possibilities。Case1 is where the final position of the optimal alignment doesn't have any gaps。

 so it matches the final character of x sub I that is little x sub I and the final character of the prefix capital y sub J。

 that is the character， little y sub J， it matches them together and just reuses an optimal alignment for the smaller strings。

 X I minus1 and y I minus1。Case 2 is where the last letter of the first string that is little X sub I gets matched with a gap。

In that case， the penalty of the corresponding alignment is the penalty of a gap。

 plus whatever the optimal alignment is of the first I 1 letters of capital X plus the first J letters of capital Y。

The symmetrically case three， we pay for a gap and then we pay whatever the optimal alignment is of all of the first I letters of capital X with the first J minus1 letters of y。

 this is the case where the last letter of the second string gets matched with a gap in the final position of the optimal alignment。

So we know that the optimal solution has to look like one of these three things， we don't know which。

 so in the recurrence we'll just in effect do brute force search among the three outcomes。

 we just remember we just choose the minimum of the three possibilities。

So that's the formal recurrence， its correctness really just follows immediately from the work we already did understanding what the optimal solution has to look like。

 so before we state the algorithm where we systematically solve all of the subproblem using this magical formula。

 let's just make sure we get the edge cases， the base cases where I or J equals zero correctly sorted out。

So specifically， what is the value of P I comma 0 and also it turns out p of0 comma I where I here is just some non negative integer。

All right so the answer to this question is the second one is B and I hope if you could keep the notation straight then the answer was fairly clear so let's remember what does pij mean。

 that's the total penalty of an optimal alignment between the first i letters of x and the first J letters of y so consider a pi0 so now we're asking about aligning the first i letters of x with the first zero letters of y that is with the empty string Well the optimal way to match any string to the empty string is you're just going to insert gaps into the empty string to equalize their lengths and so if your string has length I you need to insert i gaps what's the penalty of that alignment is just I times the penalty for a single gap and that's the answer here in B。

So we're ready now to give the algorithm and as with all these dynamic programming algorithms。

 once you know the subproblems and once you know the recurrence that relates their solutions。

 there's really nothing to do， all you do is systematically answer solve all of the subproms moving from smallest to largest。

So we're going to use an array A to keep track of the solutions of all of these subproble。

 a is going to have two dimensions， the reason for two dimensions is we have two independent parameters which are keeping track of the subproblem size。

 one for how many letters of X we're dealing with and a second dimension for how many letters of Y that we're dealing with that's analogous to the NApsack problem where we also had two dimensions to keep track of the number of items in play and the residual NApsack capacity。

We just figured out what the base case is， so we just solved those in a preprocessing step。

 so if one of the two indices is zero， then the optimal solution value is just the gap penalty times the non zeroro index。

And now we just go to our double four loop， a double four loop because we have two indices into our array。

 and whenever we get to a subproblem， we just evaluate the recurrence invoking the solution to the already computed smaller subprom。

So one sanity check you should always apply when you're writing out the code for a dynamic programming algorithm。

 when you look at the right hand side of your recurrence。

 when you look at these purportedly already solved subproblem。

 whose solutions you're using to solve the current subproblem。

 make sure you have actually already solved those subproble so in this case we're good to go because the indices of the subproblems are only less than the entry that we're filling in right now so indeed all three of the relevant subproblem Ai -1 J minus-1 Ai -1 J and AI J minus-1 they've already been computed in earlier iterations of our double4 loop so they're just hanging out waiting to be looked up in Con time。

And as usual， once you've actually figured out the key ingredients for the dynamic programming solution。

 namely the subproms and the recurrence， it's pretty much self-e why the thing's going to work and it's also selfedent exactly what its running time is going to be。

So why is the algorithm correct that is， why does it terminate with every entry AIJ equal to the true optimal penalty PIJ of the corresponding subproblem？

Well this just follows because our recurrence is correct。

 that's where all the hard work was and then we're just systematically solving all of the sub problemsm。

 so formally if you like it would be approved by induction。

So the running time is completely trivial to evaluate in each iteration of this double for loop we do a constant amount of work。

 we just need to look up three strings in constant time and make a couple of comparisons how many for loops are there while m iterations of the outer for loop and iterations of the inner for loop。

 so we suffer the product M times n that is the running time is proportional to the product of the lengths of the two strings。

So depending on the application you may be content to just have an algorithm compute for you the NW score the total penalty of an optimal alignment。

 or perhaps you're actually interested in the alignment itself。

 and just as we discussed with independent sets and line graphs by tracing back through the filled in table。

 you can indeed reconstruct an optimal solution so let me just give you the high levelvel idea of how it works it's going to follow the same template and all yet you think through the details of why this really works in the privacy of your own home。

So assuming that you've already run the algorithm on the previous slide that you've filled in all the entries of this 2D array capital A。

 Now we want to trace back。 So where are we going to start tracing back this filled in table。

 we're going to start with the problem that we actually care about to namely the largest problem A of M a comma n that's what we want the alignment for。

 Now we know this optimal alignment looks is one of three candidates。

 we know there's three possible situations for the contents of the final position of that alignment。

 Moreover， when we filled in this entry of the table。

 we explicitly compared the three possibilities to figure out which one was the best。

 So perhaps on the forward pass， we actually cache the result of the comparison or in the worst case。

 we can just go back and recompute and figure out which of those three cases was used to fill in this entry and depending on which one of the three candidates1 that tells us what should be the contents of the final position of the optimal alignment。

 if case1 was used to fill in this entry， we should match little x of M and little y sub n if case2 was used to fill in this entry。

 we should match little x of n with the gap。 if case3 was used。



![](img/9bceb64f3377371fcbc735e418931afd_2.png)

Fill in this entry， we should match a littlewise end with a gap if there's a tie we get to pick any of them arbitrarily all of them will lead to optimal alignments then of course after figuring out what to do in this final position we have it induced subproblem involving X prime and or Y prime that tells us a previous entry of the table to go to and we just repeat the process we again figure out which of the three cases was used to fill in this entry that tells us how to fill in the next rightmost position of the alignment and we just keep going till we fall off the table。

So what do you do when you fall off the table， well。

 once one of the indices I orJ gets all the way down to zero， now you have no choice。

 so now one of the strings is empty and the other one has some number of symbols so you should just insert the appropriate number of gaps to equalize the lengths。

One thing that's pretty neat is that this traceback procedure is efficient。

 in fact it's way more efficient in general than the forward pass for the forward pass you have to fill in every single one of the m times n entries。

 but in this traceback procedure each time you trace back one of the two indices at least will get decremented。

 so that says you're going complete this traceback in O of M plus n time with an optical alignment of the original two strings。

