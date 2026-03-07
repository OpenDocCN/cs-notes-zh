# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p07 P7 -BV1LvkgBtEQN_p7-

![](img/227abd4a5edac1be38c0aa3f8e39304d_0.png)

Okay， so last time。We showed that whole thing problem is is uncomputable。

 that is there is no tuuring machine that can solve。It on all instances。

And this technique is called dagonization， proof by aagonization。

 And there are many other results in。Fundamental results in math。

Like Cantor's proof of the accountabilityability of reals Russell's paradox。

That certain sets don't exist。And Godals incompleteness theorem that there may not be proofs of true statements。

There may be unprovovable statements。So， then we started。This concept， which。Will be。

A key concept in complexities， theory。In this course， which is called reduction。Su。😔，Basically。

You can reduce the whole problem if you can reduce whole problem to your problem F。

Right then that makes your problem F also uncomputable。 That is the idea so。

And what does reduction formally means， It means that。If you want to compute f1 x。

Then there is if there is a computable function F prime that transform X。

And then if you want to solve in fact， halting problem。On a program on our input X。

 then F prime will transform it and feed this as input。2 F。

And the answers will be the same so f of f prime x is the same as halt of x when this happens。

Then clearly， like you have seen in subroutines or functions in C programming。呃。

F and F frame together。When called， Queens hall also halt。Right， so this reduction。

Means that halt has reduced to F and hence f is also。On computers。That's the conclusion。

Now we will move to bounded resource instead of this。呃大 being。Fite， but extremely large。

For which you will run the tuuring machine， now we will restrict the time and the space。

And that will give us complexity classes。First， it will give us P， which is the notion of。

Practical notion of fast algorithms， efficient algorithms。And Np。So wes only study。😔。

Computable functions。So for duringuring machine M。We donote the maximum number of。Steps。

On an input of size in。As this sub maximum。Well， maximum because you want to go over all the strings of length end。

OhSo all the strings in 01 to the n， no matter which string is given。

The tuuring machine will not run more than。Timeim off and。Okay， this is the time complexity。

 but to be now it is more formal。 It is in terms of the。Input length。Okay。

 so we don't have to worry about。Time complexity being different for different strings。

So now we are just taking an upper bound over all the strings of length and。

 obviously it's a function of n。 so as increases。Usually， time will also increase。

So what is that function we are interested in that right and that is why we had defined asymptootics。

So now we can understand this function time of n in terms of asymptootics of n。So， for function。

P of N， let's say， think of TN as n square。Write or think of T n as2 to the n。

 So for a given function T of n。Collect。All the problems。Sooll building that much time。In fact。

 let me just say approximately to。So， we are interested in those problems that are solvable in around T of n time。

You not close。And that clause is。D time， we call it D time of。Din。D time stands for deterministic。

Time complexity。But it basically means that there is a tuuring machine， which can。

Solve a language contained in this set。In time。Around T ofn。 so formally。

 it is the collection of elses languages。Such that。Doing machine M。There exists a tuuring machine， M。

That decides。Ill。😔，With time complexity。Bgo of。Okay。

 so this is what I meant around T of n time it is actually big of T of n time。So。

 all the languages for which there is a tuuring machine aim。

Solving in this much time is collected in thetime T ofn。Okay。

 thats the first complex read class you learn。So for example， D time and square will mean。

Problem solvable in quadratic time。So， example， D time。In。Are the problems。Sverbilin。😔，Linear time。

 right， which is extremely fast。 This is like。Just few co few scans of the input。

 and you get the answer。 And there are many such problems。 If you have done data structure。

 algorithm scores。You could recall that there are many interesting problems。For example。

 breakfast search， connectivity and so on。In graph theory。Which are actually solvable in linear time。

 So this is D is the collection of those problems。So， as mentioned before。嗯。We consider。

Poly time fast。So if the short steering machine runs in time per normal in n。

Then we consider consider it a fast during machine。This is in contrast to exponential time。

K polymial time versus exponential time is fast versus very slow， and this inspires the definition。

Of the complexity class P。So polytime solvable problems。A。The form the class P， which is union of。

D time N the sea。See positive rules。Right， so。N and square。Or into the 10。

5 or even into the10 and so on， these are all considered。Time complexities， which are。Fost。

All of them are included in this class P。So， P is called the。Deterministic Parliament time class。

Let me give the full form。Okay so P stands for deteristic polynomial time。

It is a complexity class it contains those languages hence those decision problems。

Which are solvable in。Time N to the sea for some constantency。On a Turing machine。

 that's the full definition of efficient algorithms and efficient problems。Now。

 one point which has to be made here is。For practical people， this may not be fast enough。

Sppeially if sea is large。So， in practice in。When you actually implement these algorithms in practice poly time。

Example into the 10。May not be fast。Right algorithm which runs into the  ten0 time is actually pretty slow in practice when you actually implement on a computer。

嗯。So。This fast or efficient is always a subjective thing。In theory， we call still con。

 we continue to call it fast or efficient because。As I already said we are comparing with the exponential time。

Okay but in practice， you have to really optimize things。So theoretical algorithms。

 which are polynomial time。May not。Will still need work。When you imp to the implementation。So。

 even words。What can happen sometimes is。Ento the。Log login。Maybe faster。Then。And to the10。Okay。

 in practice。So， on inputs of size。Toourist to tourist to1。Right， that's the。So， I mean。

 what we say in theory fast， it may not be practically fast and what we in theory say slow it may not be。

Practically slow。Right， so n to the 10 may not be fast and to the log log may be faster because the input sizes。

Urgently。Limited。Right， so on those inputs， maybe there are。Theoretically bad algorithms。

 which were practically very sought。You always， I mean。

 this efficiency and speed are fast and slow when we use these terms， its always subjective。

But in the course we always mean polynomial time。Okay， that's the definition。

So we continue to use this definition， because。Historically， it has served us well。So， historically。

 P has。Serve。As a good abstraction。Of fast computation。Just like tuuring machines。

 abstract computers。So remove the architecture and other issues。Implementation or hardware issues。

 similarly P。Abstracts， fast computation， and removes。The actual time in seconds。

And the implementation details and the optimized algorithms。 Okay。

 all those things get abstracted out in P nicely， and then we can study it mathematically。

So historically， it has served us well。So， we'll continue with this。And。Basically， there are many。

 many interesting examples in P。So what are the problems in P。So there are many。

 many interesting examples。Okay lots of。I mean， almost all the practical problems they fall in P。

So whatever computers are doing， it is generally。These are P。Algothms in P。

 if you abstracted it as a Turing machine。You said be。So okay， enough of P， these are。

I must have mentioned in， initially。So你嘅。😔，Graph reachability。Arithmetic operations。Linear algebra。

Great search。So all all these things that you do in practice。They are all actually polymial time。

And algorithms。So what are the heart problems， problems which are。Not even MP P， even if you give。

En to the 10 into the hundred time， you cannot solve them。 What are those problems。

 Well let's now discuss them a bit。Some。😔，Practically hard。Problems。So。

The first is traveling salesperson problem。Also called PSSP。

So this is a practical problem and it is supposed to be hard there are no polymer time algorithms known。

Since the last。5 decades。So the problem is as follows， let G B graph on in vertices。

With edges labeled with distances。Okay， so it is an edge labeled graph in vertices。Now， question is。

 is there a close to。Visiting all the nodes， exactly once。Of length at mosky。Okay。

 so this is an optimization problem。That you are given a graph which is basically you can think of cities。

Or you in a city， you can think of localities。And or houses。

And three are the nodes and between houses， they are these edges which are the streets。

 they have distances written on them。Now， the salesperson。Or the post person wants to go to。

All these houses。In his or her set of houses。Oh。Exactly once。 There is no point。Again。

 visiting the same house so exactly once。And it should be a close tour。Start from one point。

 visit all the houses and come back。In obviously， needless to say。In minimal distance。Traveled。

So we are abstracting it in terms of length。Key， so given key。The traveling salesperson。

 the salesperson wants to find a close tour。Of this much length， if it doesn't exist。

 then the salesperson can increase K and again， call this。Subroutine。

So it's an optimization question， right， finding the minimal close to。What is that now。

Booot force algorithm is just go over all subsets of edges。Right， but edges。

or at least n and then if you go over all the subsets it will be two ways to n。

So it will be a very bad algorithm。And that's the best essentially the best algorithm。

 which is known。Okay， so there are no good algorithms discovered yet。Second is sub sum。

So as the name suggests， you are given a set。Of any integers。And natural numbers。And you are given P。

Another natural number。 So you are given n plus one numbers。

And the question is whether there is a subset of s。Summing up to D。So does the tear exist。

Subset of s。Suming duty。That's the question。Like before。呃。Again。

 the brute forces algorithm is go over all subsets which is tourist to end。

And check whether the sum is in D T。 Okay， nothing better than that is known。

Notice that you can sort the numbers， but that doesn't help much because。Still， teammate。呃。

Pick small numbers。 Big numbers。Bidttle numbers， and sum up， too。Some up to tea。Right。

 so sorting doesn't seem to help and then you don't know what else you can do with numbers。Third is。

In teacherger programming。So what is programming， Well， programming。

 what comes from linear programming， if you have seen。That concept before。

 so linear programming is the problem of solving linear。嗯。System where there are also inequalities。

Okay， equalalities inequities both are there and such a linear system you are given。

 you want to find a feasible。Point。A solution。So， that's a famous。Problem， again， in optimization。

But there， they want to find a real。Feaible point， real。Vald。In individual programming。

You have to find an integral solution。And that seems to change everything。Okay。

 linear programming can be solved efficiently， there are famous algorithms known。

Integer programming is still。呃。No algorithm known， except brute force。So， given M。

Linear inequalities。In M variables。Is there a bullion？In fact。

You can even ask about a boolean feasible point。Does there exist。A boolean， feasible point。

So since I'm only asking for Boolean feasible point， you can。There are n variables so you can fix 0。

1。 that's tourist twin possibilities and see whether。This point is feasible。

So that' is the brute force and nothing better is known。So these brute force algorithms。

 you can check as an exercise。So，1，2，3。Are solved。Are easily solved in time。First one。

Traveling salesperson， it's。Yeah， it is a bit harder than I said it is not just subsets。

 but also the order will matter which house you visit first which second and so on。

 so it is actually a matter of permutations。So that gives you n factorial。Time complexity。

You can think of it as just going over the permutations of the vertices。B the houses。

Whether you visit the first。which is the first house， which is the second house， third house so on。

 so you can look at all the permutations。And if there is a close tour， one of these will work。

So that is a search in the end factorial space。Second is two days to end。

 it's about subsets and third days。Again， tourist rest to end time。Respectively。Right。

 so work out these brute force algorithms。But these are all very， very， very slow algorithms。

 these are exponential time algorithms because。诶。If you take N to be。Hundred。

They just hundred houses。It's so。Not realistic in practice and the how number of houses will be far more than10。

 but even with  hundred， this is giving you 1 hundred factorial。So it's impossible to solve this。

 this algorithm will never stop。Bric an exponential。Search space。 And that's。That's always a problem。

You don't want to get stuck in an exponential search space。So yeah， this inspires。Or these problems。

These are all practical problems from real life and their exponential time。

We don't know how to solve them。So， so these problems inspire the。Exponential time class。So X。

 we call it。This is the。D time。 So time complexity。Two ways to entries to see。Okay。

 so instead of end to the C now you are talking about two ways to end race to C in that exponential time。

So， these problems。The problem，1，2，3。They are all in ex。And we don't know any better。Okay。

 so those brute force algorithms。Are the best we know so notice that n factorial is smaller than 2 race to n square。

So， clearly。D time and factorial is contained in X。And similarly， D time2 2 n is also contained in。

Subsid of X。So these problems are clearly inex， but we don't know anything better and。

You would like to know better， because these are all。Very useful problems。

 These are not artificial problems。They all have connections too。Combinatorial optimization。

 So these problems have one thing in common that if somebody gives you a solution， you can verify it。

Right， so if somebody gives you a close tour。Salesperson can verify。

Whether this close towards satisfies the properties and length is less than equal to k。

If somebody gives you a subset， you can test whether a subset sums to T。

And if somebody gives you a Boolean feasible point， you can Boolean point。

 you can check whether it' is feasible。Right， very efficiently， it's。Tvial to。Do those verifications。

So， these verifications protocol。Our。They are it seems trivial。

 but actually it is an interesting feature of these problems。And。We'll collect those problems in X。

 which have this feature。And give it a name。Should they have a。Common feature。Given a close tour。

A subset。Or a booleing point。It can be verified。Whether it's the right one。Whether it's。

 let's say correct。In a short time。Or by an easy algorithm， let me say。So。

 this brings us to the concept of poly time verifiers poly time verification。So， this motivated。

Cook and le。To study all the problems。That have poly verifiers。Okay， so。These problems we collect。

In a special complexity class。Which we call。Enby。So language L。Obviously。

 bullolean language decision problem。Is an NP p。If。😔，They exist a constant。And。Apo time。

Or let me see now， duringuring machine。Such that。For all x。Forex。X is in L。If and only。

 so basically yes strings。Of your decision problem L。If and only leave， there is a certificate。You。

 which is not too large。this is where C is being used。The certificate you could be bigger。

 slightly bigger than the input length， but not too much。We only up to。A polynomial blo。

And then M can certify it， verify it。Okay， so M here is the verifier。Checking the。

Checking whether given you is。Correct solution or not。Okay。



![](img/227abd4a5edac1be38c0aa3f8e39304d_2.png)