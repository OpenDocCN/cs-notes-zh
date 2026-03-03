# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P164：36_04_06_2-SAT问题.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/322300de5c7f0020f9a77acf877a6801_0.png)

In these next three videos I want to highlight for you an unusual local search algorithm it's unusual in that it's guaranteed to solve a non-trivial and interesting problem in polynomial time that problem is the twoatAT problem which also furnishes an example of how local search can be applied to constraint satisfaction problems。

We've now mentioned Tat in passing a number of times。

 but let me just give you a very precise definition of the computational problem here。



![](img/322300de5c7f0020f9a77acf877a6801_2.png)

![](img/322300de5c7f0020f9a77acf877a6801_3.png)

The input is a set of n variables x1 through xn at a set of M clauses。

 each of the variables is boolean， that is you're allowed to set it to either true or to false。

Each of the M clauses is a disjunction that is an or of two literals。

 a literals is simply either a variable or the negation of that variable。

Here's an example to make this clearer。 The example has four variables and four clauses。

 The variables are x1 through x4。So the first clause is x1 or x2。

 so it's standard to use this V symbol to denote logical or。

 So what this clause means is that it's satisfied if either x1 is true or if x2 is true。

 the only way you can screw up satisfying this clause is by setting both x1 and and x2 to false。

The next clause has the form not x1 or x3。The only way you can screw up satisfying this clause is by setting x1 to be true and X3 to be false。

 Then we're going to have a clause X3 or x4。 Again。

 this is satisfied unless you wind up setting X3 and X4， both to be false。 And then finally。

 we have a clause not X 2 or not X4。 And this is satisfied。

 except in the case that you assign both X 2 and X4 to be true。

Because we're interested in whether all of the clauses can be simultaneously satisfied。

 one often joins the clauses using logical and symbols， that's what this upside down V denotes。

So that's what a twoat instance looks like and then we're just interested in a decision problem。

 given such an instance we just want to know is it or is it not possible to assign values to the n variables true or false so that every single one of the M clauses is satisfied。



![](img/322300de5c7f0020f9a77acf877a6801_5.png)

The twoat instance that I gave you as an example is indeed satisfyisfiable。

 There's actually more than one satisfying assignment。 But here's a way to produce one of them。

 Let's start with the first clause to satisfy either X1 or x2 has to be set to true。

 So let's go ahead and set X1 to be true。 that takes care of the first clause。 Now。

 we look at the second clause。 and we notice oops， if we said X1 to be true。

 The only way we can satisfy the second clause is by setting x 3 to be true。

 So let's go ahead and do that。 So X1 and X 3 are true X2 and x 4， we haven't assigned yet。 Now。

 by assigning x 3 to be true。 We knock off not just that second clause。

 We also satisfy the third clause。 So that leaves us with the fourth clause。

 And now we just got to make sure we said either x 2 or x4 to be false。

 Let's just go ahead and set them both to be false。 That satisfies all of the clauses。

Much is known about the computational tractability or as the case may be intractability of constraint satisfaction problems。

2 set is not exceptional in that sense。 We know all kinds of things about it。

 It is exceptional in that it is polynomial time solvable。There are many ways of proving this fact。

 alumni of part1 may already be familiar with one really nice way。

 which to reduce the twoatAT problem to computing the strongly connected components of a suitable directed graph。

 that reduction in fact shows that the twoat problem can be solved in linear time。

Another way you can establish its computational tractability is using a type of backtrack algorithm and by backtracking here。

 I mean something sort of similar to what we did when we gave our faster exponential time algorithm for the vertex cover problem。

 for instances which have small vertex cover， small optimal solutions。

Both of these proofs of computational tractability are non-trivial。

 I'm not going to discuss them here because instead I want to spend our time on a local search algorithm。

 roughly speaking， the way the backtracking algorithm works in a twoat instance is you start by looking at some variable。

 let's say variable X1 and as a tenet of working hypothesis， you assign x1 the value of true。 Now。

 through the clauses， setting x1 to be true， has ramifications for what other variables have to necessarily be。

 if you're going to have a satisfying assignment。 So you go ahead and propagate those implications to the rest of the variables。

 if you reach a contradiction， if there's one clause demanding that x7 is set to true and a different clause demanding that X 7 is set to false you know that it didn't work out X1 is not going to be true in any satisfying assignment So you backtrack and you try again。

 setting it to be false and seeing if that works out。If on the other hand。

 you're able to consistently propagate all of these implications from X1 being equal to true to other variables。

 then you can just try to extend that satisfying assignment by walking up to a different variable and setting that tentatively to be say true。

It's possible to organize this search so that you can correctly determine whether or not a twoatAT instance has a satisfying assignment in polynomial time。

 again， a nontri exercise if you're interested， think through the details。

We're going to instead focus on a very cool randomized local search algorithm that again solves two side instances in polynomial time。

I don't want to give you the wrong idea， as we discussed earlier。

 generally local searchur are not guaranteed to run in polynomial time。

 as we said that's true even in the weighted version of the maximum cut problem。

 this too sad example is the rare case where we can prove it's guaranteed to converge with a correct answer quickly。

You can use local search not merely to identify computationally tractable versions of satisfiability。

 but also to improve over naive brutefor search for NP completete versions of satisfiability。



![](img/322300de5c7f0020f9a77acf877a6801_7.png)

In particular， let's talk about the threeat problem。 So threeatAT。

 no surprise it's the same as two sat except the clauses involve three literals rather than two。

 So while a clause in a twoat instance can be thought of as forbidding one of the four possible joint assignments of a pair of variables。

 a clause in a threeatAT instance can be thought of as forbidding one of the eight possible joint values for a triple of variables。

Buming up the clause length from 2 or3 changes the problem from computationally tractable to computationally intractable。

 Indeed，3 satAT is， in some sense， the canonical NP complete problem。

 You'll often see the cook 11 theorem stated as3 sat is NP complete。

But just because it's empty complete doesn't automatically mean we can't come up with any interesting algorithms。

 So brute for a search would just try every possible assignment to the variables that's going to take time roughly2 to the end。

Remarkably， randomized local search lets you improve dramatically over the running time of naive brute force search。

 rather than a running time of roughly two to the n。

 a very clever twist on the twoat algorithm that we're about to discuss。

 which runs in polynomial time， a twist on that for threeat runs in time roughly four thirds raised to the end。

 way better than two to the end。

![](img/322300de5c7f0020f9a77acf877a6801_9.png)

This is a relatively recent result only about a decade old due to sh。

I want to focus here on how to use randomized local search to solve two sat in polynomial time。

 the improvement over brute force search for threeSAT will have to wait till another day。

This algorithm is due to Papaimmiru from a little over 20 years ago。

 and the very elegant pseudocode is as follows。

![](img/322300de5c7f0020f9a77acf877a6801_11.png)

So the algorithm has two loops， but the outer loop's responsibility is just to run a budget of independent random trials。

For those of you who are alumni of part one， let me make an analogy with Car's randomized contraction algorithm。

 so for that minimum cut algorithm we had our basic randomized algorithm and then we ran it a bunch of times a bunch of independent trials。

 hoping that one of the independent trials would find us the minimum cut saying thing is going to be going on here。

 the meat of the algorithm is in the inner loop that has some probability of finding a satisfying assignment。

 and then we just run that basic subroutine a bunch of times hoping that one of the trials will find us a satisfying assignment。



![](img/322300de5c7f0020f9a77acf877a6801_13.png)

So conceptually， you should just focus on a fixed iteration of this outer for loop。

 they're all exactly the same， they just use different sets of random coins。

In a given iteration of this outer loop， we're just going to be doing straightforward local search。

 So we have to specify what's the space of solutions。 Well。

 those are just all of the ways of assigning the n variables to true and false。

 all possible assignments。 We have to specify the neighboring solutions。

 that's just going to be the one we discussed。 So two assignments will be neighboring if they differ only in the flip of a value of a single variable。

We have to make a decision about where we start the local search。

 we're going to do it in just the obvious randomized way from a uniform at random assignment of the variables。

After we've settled on a random initial assignment we just do local search that is we just keep flipping variables。

 trying to improve the quality of the current assignment Now。

 one thing that's going to be a little bit different from this algorithm relative to the generic local search algorithm we discussed in the previous video is I'm going to place an a priori bound on how many local moves we're going to do before we give up one obvious motivation for that is if we want a polynomial time algorithm。

 this will ensure that the algorithm will not run for too many steps。So the magic number。

 which we motivate when we analyze the algorithm is 2 n squared。

 That's how many variable flips we're going to make before we give up and return to the next independent trial in the outer for loop。

 Remember， N dens the number of variables。In each generation of the inner for loop。

 we first check just to see if the current assignment is in fact satisifiable。

 if it satisfies all the clauses， if so we're done， we halt and report that fact。

Suppose the current assignment is not satisfied。 What does that mean。

 that means there's one clause or maybe many clauses which are not currently satisfied。

 So for example， maybe there's some clause involving the variables x3 and x7 and we unfortunately set x3 to be true x7 be false。

 and that's exactly the joint value forbidden by this clause that is maybe the clause is not x3 or x7。

So what do we do next， Well， next we do an iteration of local search。

 We try and improve our assignment。 How do we do that， Well we pick an unsatisfied clause。

 if there are many such clauses， we pick one arbitrarily and we try to make amends with this clause by flipping the values of one of the variables in the clauses。

 So in our example， we're either going to flip X 3 from true to false。 That would satisfy the clause。

 or we're going to flip x 7 from false to true。 that would also satisfy the clause。

 assuming the clause is not X 3 or x 7。Now either one of these variable flips would succeed in changing this clause from unsatisfied to satisfiedsfied。

 and you could think of various clever heuristics about which of the two variables you decide to flip。

 but we're going to take the simplest way forward， we're just going to pick between the two 50-50 so again。

 how do we modify the assignment， we choose an arbitrary unsatisfied clause。

 we pick one of the two variables in that clause uniformly at random and we flip the value of that variable。



![](img/322300de5c7f0020f9a77acf877a6801_15.png)

Now， what makes this algorithm so frightening to think about。

 And my best guess for the reason why this very elegant algorithm wasn't analyzed before 1991。

 is that you can do some serious damage when you flip one of these variables。 I mean， yeah。

 the constraint you started with is going to go from unsatisfied to satisfiedfied。 But for all。

 you know， all these other clauses are going to go from satisfied to unsatisfied。If， for example。

 you take the variable X3 and you flip it from true to false。 Well， yeah。

 that's great for this clause。 That was not X 3 or 7。 It becomes true。 It becomes satisfied。

 but maybe there are a zillion other clauses where X3 appears unnegated。 It's X 3 or something else。

 and perhaps by switching X 3 to go from true to false。 A bunch of those have now become unsatisfied。

 So in no way are you always increasing the number of satisfied clauses When you do an iteration of this local search。

 It's very nonstandard local search algorithm in that sense。😊。

To complete the description of this algorithm， I have to tell you what happens if it never finds a satisfying assignment。

 of course if it does find such an assignment， it quits wallet it's ahead and just returns that satisfying assignment。

 but after all after these two n squared times log end steps it's never found a satisfying assignment。

 it does something very arrogant， it just declares that well。

 if I didn't find a satisfying assignment， I think that one doesn't exist。

Here's two obvious positive statements we can make about this randomized local search algorithm for twoS。

 First of all， it runs in polynomial time， and that's with probability one。

 no matter how the coin flips of the algorithms play out。

 that's because we explicitly control the number of iterations of local search。

 its big of n squared log n。 So even with the sloppiest implementation you could imagine of this algorithm。

 it's going to run in polynomial time。Let's turn to the issue of correctness and let's separate two sad instances into those that are satisfiable where there exists a satisfying assignment and those that are unsatisfiable。

 The second obvious good property of this local search algorithm is that it's always going to be correct if you feed into it an unsatisfiable instance why。

 but what's the algorithm going to do on such an instance。

 what's going to rummage around amongst the possible assignments for these twoN squared login steps trying out different ones。

 obviously none of them will be satisfying because there are no satisfying assignments and at the end of the day the algorithm will correctly conclude that the instance is in fact unsatisfiable。

But the key question is what happens on satisfiable instances。

 if there is somewhere out there in the exponentially big space of assignments one that satisfies all of the assignments。

 is this algorithm going to find one in its mere 2N squared times login steps？

Now I have to tweak that question a little bit， this is after all a randomized algorithm and there's some tiny probability that the coin flips could conspire to stymie the algorithm from finding a satisfying assignment。

 so what I really mean is could it be the case that with probability very close to one on every satisfyisfiable twoat instance this simple randomized local search algorithms actually going to come up with a satisfying assignment。

