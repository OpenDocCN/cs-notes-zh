# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P166：38_04_08_Papadimitriou算法分析.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/cd568539bd812c73e1551aa8bcc6cd73_0.png)

Now we'll see how our understanding of basic properties of random walks in the non negative integers unlocks the analysis of Pope Deometri's algorithm showing that randomized local storage yields of polynomial time algorithm for the twoatAT problem。

Let me remind you the details of Pp Diometrio's2atAT algorithm， consider an instance of twoat。

 supposeupp it has n Boolean variables， the algorithm has two for loops， the outer for loop。

 its only responsibility is to run login independent random trials。

In each iteration of this outer for loop， we're just going to do randomized local search。

 So we begin with an initial random assignment。 We flip a fair coin independently for each of the n variables to determine whether it starts out true or starts out false。

 Then we get a budget of two n squared local moves。

 in an attempt to transform this initial assignment into one that's satisfying。

In each of these two n squared inner iterations， we first check if the current assignment is satisfy。

 Obviously， if it is， we're done。 So suppose the current assignment is not a satisfying assignment。

 then there's at least one， possibly many unsatisfiyed clauses of them， we pick one arbitrarily。

 It's a twoat instance。 So this clause involves two variables。

 And if we flip the value of either of those two variables。

 We're going to make amends with this clause。 It will flip from unsatisfied to satisfy。

 There's a tricky question of how you pick which of the two variables you flip。

 but we take the easy way out。 We just pick one of the two uniformly at random。

If at the end of the day， after these two n squared times log n local moves。

 Poometry's algorithm has failed to find a satisfying assignment。

 It somewhat arrogantly declares that therefore， one must not exist。

 What's clear about this algorithm is that it runs in polynomial time。 After all。

 we've explicitly bounded the number of steps it's permitted to take。 Secondly。

 it's clear that if there is no satisfying assignment。

 then the algorithm will naturally fail to find one and correctly report that it's unsatisfiable。

What's not at all obvious is the probability that Pope Deometri's algorithm will find a satisfying assignment in instances where at least one such assignment exists。

 that analysis is the subject of this video。

![](img/cd568539bd812c73e1551aa8bcc6cd73_2.png)

And again， what's remarkable and surprising about this theorem is that if you think about the most natural measure of progress for Pope Diometri's algorithm。

 namely the number of clauses which are currently satisfied。

 that number can actually go down when you make a local step by flipping the assignment to one variable。

 yeah， you fix the one clause， but you might screw up a bunch of others leaving you with an assignment that seems worse in the sense that even fewer clauses are satisfied than before。

Nonetheless， if you define the right measure of progress。

 you can argue by a random walk analogy that you are making progress over time resulting eventually with a satisfying assignment。

 Let's see the details。

![](img/cd568539bd812c73e1551aa8bcc6cd73_4.png)

![](img/cd568539bd812c73e1551aa8bcc6cd73_5.png)

![](img/cd568539bd812c73e1551aa8bcc6cd73_6.png)

![](img/cd568539bd812c73e1551aa8bcc6cd73_7.png)

Each iteration of the outer for loop represents a fresh opportunity to discover a satisfying assignment。

 all of these iterations of the outer for loop are identical， they just use fresh randomt coins。

 so let's just analyze for now the success probability of a particular outer iteration。

We're assuming that this instance is satisfiable， so there's at least one。

 perhaps many satisfying assignments， pick one an arbitrary one I don't care which call it a star。

Let's denote by a sub T， the assignment that Pau Diometri's algorithm is considering after t iterations of the inner for loop have completed。

 so a sub0 that's the random initial assignment with which we begin this iteration of the outer for loop。

 and then after we've done T local flips， that results in the assignment A sub T This is of course。

 a random variable， it's a function of the random choice is made by P deometri's algorithm。Now。

 the great idea in this analysis is to use the right progress measure。

 rather than counting the number of clauses that the current assignment satisfies。

 we're going to count the number of variable assignments that it got right。

 That is the number of variable assignments with which it agrees with this reference satisfying assignment a star。

Evidently， x sub T is an integer， it's zero， if a assigns every variable。

 the opposite of what a star does， and it's equal to n if a and A star are exactly the same assignment。

Of course， if we ever get to the point where X sub T equals n and a star is the same as A。

 then A is itself a satisfying assignment and we're good to go， the algorithm halts correctly。

Now we come to the key point in the analysis， now we're going to understand the sense in which the algorithm on average makes progress。



![](img/cd568539bd812c73e1551aa8bcc6cd73_9.png)

![](img/cd568539bd812c73e1551aa8bcc6cd73_10.png)

So suppose we're currently looking at the assignment A sub T and suppose it's not a satisfying assignment。

 Then there's one or more clauses that are unsatisfied。 The algorithm picks one of those。

 let's say it's a clause involving the variables x sub I and x sub J。 So for example。

 if it looks at the clause， not x sub 3 or x sub7， then it's involving the variables x sub 3 and x sub 7。

 So here's an easy observation， our current assignment a sub T is failing to satisfy this clause。

 The reference satisfying assignment A star naturally is satisfying this clause。 Therefore。

 a star must give a different value to one of the two variables X I or Xj。

 then our assignment a sub T does。

![](img/cd568539bd812c73e1551aa8bcc6cd73_12.png)

![](img/cd568539bd812c73e1551aa8bcc6cd73_13.png)

![](img/cd568539bd812c73e1551aa8bcc6cd73_14.png)

It is also possible， of course， that A star makes different assignments to both of the variables X I and X J。

 All we know is that A star satisfies the clause， whereas our assignment A sub T does not。



![](img/cd568539bd812c73e1551aa8bcc6cd73_16.png)

![](img/cd568539bd812c73e1551aa8bcc6cd73_17.png)

![](img/cd568539bd812c73e1551aa8bcc6cd73_18.png)

And the amazing part is just this simple observation is enough to imply that we're going to make progress on average。

 here's exactly what I mean。

![](img/cd568539bd812c73e1551aa8bcc6cd73_20.png)

![](img/cd568539bd812c73e1551aa8bcc6cd73_21.png)

So Papamitri's algorithm is going to choose either Xi or Xj。

 that choice is uniform at random and it's going to flip the value currently assigned to that variable Now the situation in which this is guaranteed to be good for us is where we gave the opposite assignment to both Xi and Xj relative to the assignment a star if both of our value assignments to these variables was the opposite of a star than whichever one we flip we are going to share one more variable in agreement with a star than we did before that is in our previous notation X sub t plus1 the number of variables in which we agree next time step will be guaranteed to be one more than it is right now。



![](img/cd568539bd812c73e1551aa8bcc6cd73_23.png)

The situation is more subtle when the current assignment A sub T agrees with the reference satisfying assignment A star on exactly one of the two variables X I and Xj。

 So， for example， maybe the current assignment agrees with a star and X I。

 but it disagrees with the reference assignment A star on X J。 Now， of course。

 the algorithm has no idea what a star is。 This arbitrary satisfying assignment。

 So it has no idea which of the two variables X I or X J should flip。

 It just picked one of the two at random。 Now， if we get lucky。

 and we flip the value of the variable on which a sub T and a star disagree。

 then this is just like case 1。 The flip causes the two assignments to agree on one more variable than they did previously。

 As a consequence， x sub T plus1 is going to be one more than x sub T。In the unlucky case。

 we wind up flipping the variable on which we agreed already with the reference assignment a star。

 then once we flip it we're going to disagree on yet another variable with the reference assignment a star。

 so in that case， x of T plus1 is actually going to be one less than x of T。And now at this point。

 I hope things are starting to look a little familiar relative to our previous video about random walks on the non-neg integers there。

 we again had a random variable， namely the position of the walk。 and at each time step。

 it either went up by one or down by one with 5050 probability each。

 So the situation here where the X of T's is clearly not identical to random walks on non-ne integers。

 So the next quiz asks you to identify the differences between the random process governing the X of Ts and your vanilla random walk on the non-ne integers as studied in the previous video。

So the answer is D。If we think about two random processes。

 the first one is your straightforward random walk on the non-neative integers。

 as discussed in the last video， the second random process is the evolution of these random variables。

 the x sub T's。 the number of variables on which the current assignment in Papitoometri's algorithm agrees with a reference satisfying assignment a star。

 there are exactly three differences。 One， we already pointed out in the vanilla random walk on the line unless you're at position 0。

 if you're at any bigger position， it's always 5050 left or right in Popyoometry's algorithm。

 you might sometimes have a0% probability of moving to the left， 100% chance of moving to the right。

 that's when the algorithm zooms in on an unsatisfied clause in which the current assignment A sub T happens to differ with the reference assignment a star on both of the two variables。

 then it doesn't matter which of the variables you pick you're guaranteed to agree with a reference assignment a star on one more variable than before。

The second difference is that when we studied random walks， by definition。

 we always started at position  zero。That would correspond to this first random variable x n being equal to0。

However， in general， x n will not be equal to 0。 in general， it'll be strictly bigger than 0。

 Why is that， Well， remember， x n is defined as the number of variables that have the same value in the reference assignment a star and the initial random assignment A not。

 So the only way that x n is going to be 0 is if you randomly chosen assignment where every variable had the opposite value as what it is in a star。

 And that's very unlikely to happen。 General， you start with a random assignment。

 you're going to get lucky and some of the values will be correct will be the same as in a star。

 So X n will generally start out bigger than 0。Here's the third and final difference in the random walks that we studied。

 the process by definition stopped exactly the first time you reach position N。Now。

 in Papi deometri's algorithm， what is true is that if you ever get to the points that x sub t equals n。

 then at that point， the algorithm will terminate。 Why， well， if x sub t equals n。

 that means that in the assignment a sub T， every single variable has exactly the same value as in the reference assignment A star。

 Now， a star is a satisfying assignment and Po deometri's algorithm halts as soon as it finds a satisfying assignment。

 So if x sub t equals n， you found a star and you're good to go， you stop。 However。

 the converse is not true。 Papi deometri's algorithm might halt。

 even though the current value of x sub T is less than n。

Why is that Well remember Xcept t measures your distance from this this one satisfying assignment a star。

 but nobody said that was the only one。 There might be other satisfying assignments out there in the world as well。

 and Papamici's algorithm might well stumble upon one of them before it finds a star。

 so it halts the first time it finds a satisfying assignment and that can happen before X t equals n。

So where does this leave us， On the one hand， there does seem to be a strong metaphor between the distance between the assignment in Pou Diometri's algorithm and this reference assignment a star and the position of a random walk on the non negative integers。

 On the other hand， there's kind of a lot of differences。 Some of them are pretty subtle。

 So what you got to be wondering is， was that whole analysis last video useful。Well。

 what's amazing and what allows us to transfer the random walk analysis over to that Apoyittris algorithm is that every single one of these three discrepancies between the two random processes only helps us。

 It only means the algorithm is going to terminate even faster than we might have suspected from the random walk analysis。

So here's another way to think about it。 Imagine I force you to run Poometri's algorithm under an extremely unfortunate set of circumstances。

 So first， I give you a two sad instance with just one satisfying assignment。 So there's a unique。

 satisfying assignment。 A star。 You're looking for a needle in a haystack。

 There's no way you can get lucky by halting early with a different satisfying assignment。 Secondly。

 I force you to begin from the worst possible initial assignment where every variable value initially is the wrong one is flipped from what it should be in a star。

And finally， imagine I further contrive things so that whenever you pick an unsatisfied clause to do a variable flip。

 I force you to pick a clause where one of the variables is set the same as an A star and the other variable is set the opposite of A star。

Well， for this kind of execution of Popeyometri's algorithm。

 the correspondence between the evolution of the random variables， the exs。

 and a random walk on the non-neative integers is perfect。

 the two random processes are identical under this worst case set of circumstances。Therefore。

 in the worst case circumstances， the probability the Po deometrius algorithm fails to find a satisfying assignment。

 that is a star within two n squared steps is exactly the same。

 as the probability that a random walk beginning at 0 fails to reach position n within two n squared steps。

 and we analyze that failure probability in the previous video。 We proved it's at most one half。

 That is the success probability is at least one half。Now。

 if you look at any other circumstances other than the worst case circumstances。

 Pometer's algorithm is only more likely to succeed。 So first of all。

 it doesn't start as far away from a satisfying assignment。 Second of all。

 there's other satisfying assignments that might be able to find。 and thirdly。

 sometimes is guaranteed to make progress as opposed to having only a 5050 chance。

 So the success probability under any circumstances a Pos algorithm is at least 50% in a given iteration of this outer for loop。



![](img/cd568539bd812c73e1551aa8bcc6cd73_25.png)

And now we're home free， the probability that a given iteration of the outer for loop fails is a most one half。

 the probability that each of the log base 2 n iterations of the outer for loop fail is then at most one half raised to the log base 2 of n also known as1 over n。

 so the overall success probability of the algorithm is at least one minus1 over n as claimed。



![](img/cd568539bd812c73e1551aa8bcc6cd73_27.png)