# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P28：28_07_04_多项式时间归约.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/ebca455796d41d8a06eb7de3aedd89ca_0.png)

Given these specific definitions， we do have a mathematical tool that'll help us get a start on classifying problems according to their difficulty called reduction。

 and that's what we want to talk about next。So what we want to know is which problems are in P。

 well that's the easier of the questions， it's the ones that we're solving with the fish and algorithms。

 at least we know they're in P。But really the question is which ones are intractable。

 which ones are in NP， but not NP， and that's difficult to know。

 and no one's been able to show that even one problem is in NP but not NP P。

And that's the basic answer that we want for so many problems can we just solve it on any mobile device or any computing device or we're going to need 10 to the 48 Uber computers so in order to get going what theoreticians have done is to start with a reasonable assumption and so that assumption that we're going to start with is that satisfiability the boolean satisfiability simultaneous satisfiability problem we're going to assume that that one is intractable that seems like such a fundamental problem and nobody knows a better approach than to just try all assignments of the truth variables now assuming that a particular problem is intractable already is assuming that P is not equal to NPp so bear that in mind so now we have at least the possibility。

Of under that assumption， proving that maybe other problems are going to be intractable。So again。

 we have a brute force algorithm for finding solution for any SA instance。

 but no efficient algorithm does so， so it's reasonable to assume that SAAT is intractable。

So what we're going to do now is use that assumption to prove relationships among problems now maybe the assumptionss wrong。

 maybe Ps NP and they're all tractable， but if we believe the pieces not equal NP and we just have that one assumption then we can prove things about other problems and so that's what we're going to look at next。

If SAAT is intractable， which again， is equivalent assuming p is not equal to NP。

 then which other problems are intractable？And to do that we're going to use a tool called polynomial time reduction and this is the definition if we have two problems X and y。

 we're going to say that x polytime reduces to y， if you can use an efficient solution to Y to develop an efficient solution to X。

 we know how to solve y we can use that to solve x， we call that X reduces to y。

 so a typical reduction is the following so I have an algorithm that solves y is guaranteed to solve it no matter what the input is polynomial time。

Here's my method for solving X。So first thing is I'll use an efficient method to transform whatever instance of x I have to solve into an instance of Y。

Then I'll use my efficient method that solves Y， and that's going to give a solution of some kind。

 and then I'm going to transform that solution back to a solution of X。

So that's an effective and efficient method for solving any instance of x。

 given an efficient method for solving Y。It's kind of like what we use when we use a library method when we're modular programming。

 we compute the exponential of x by calling the math library and that solves that efficiently and we use it and then any program we have that calls that we have an efficient solution for and so this is just a mathematical formalism of that。

 wrapped around the idea that y has to be guaranteed to solve any sense of y in polynomial time and that the transformations have to be guaranteed to run in polynomial time for the whole thing to work。

And there's lots of ways to extend this， this is the simplest way because we have polynomial time to play with。

 so for example we could use a polynomial number of instances of why and we could do lots of transformations。

 as long as none of the costs can be exponential in any situation。

 but we get pretty far just with this simple concept of reduction。

Now important point about polynomial time reduction is that it's transitive。

 if x reduces to y y reduces to Z， then x reduces to Z， and again。

 if you think about it in terms of using a library program。

 that one might use another library program and so forth。

So that is if x reduces to Y then that's a diagram that we had from the previous page。

 but if y reduces to C， you can do the same thing for this solution of y you can transform it into the instance of Z。

 use your infier method for solving Z， transform that to Y and then transform that result back to X and so forth so with this little diagram you can see that polynomial time reduction is transitive and we're going to take advantage of that in just a second so really from a theoretical point of view。

 there's two ways to exploit reduction so the first one is if I have a new problem and I want to solve it。

I can find a problem that I know an efficient algorithm that solves it like， you know。

 like a library program。 And I can say， how does that relate to my new problem if I can use。

If I can transform my new problem into an instance of this problem Y。

 then I can just use it polynom at time reduce x to Y。

 and that efficient algorithm for y is going to eventually give me an efficient algorithm for X。

 that's an algorithm design through reduction and we're not emphasizing it in this lecture but any time you take of course an algorithm。

 you'll see many applications where we take an algorithm like sorting。

 we take another problem like removing duplicates reduce it since we know we have an efficient algorithm for sorting。

 we can get an efficient algorithm for this other problem。

So algorithm design is a very important use of reduction， but in today's context。

 we're going to use reduction to establish intractability。So now I have a new problem Y。

 what I want to do is find a problem X that satAT reduces to。

And then find a reduction from x to y that gives me a reduction really from sat to y S to x and x to y。

 and that tells me that if I had an efficient algorithm for y。

 I would have an efficient algorithm for x， and I would also have an efficient algorithm for sat。

 but that's a contradiction because I'm assuming that sat is intractable， so I can't have。

 if I have these reductions， I can't have an efficient algorithm for y。

That's a critical tool for this lecture but actually just think about the easiest option。

 if I have a problem if I can reduce satAT to that problem and I'm assuming that SAAT is intractable。

 then I know that Y is intractable because an efficient algorithm for Y would mean I have an efficient algorithm for SAT。

So let's start with that， for example， here's an easy proof that sat polytime reduces to integer linear programming。

So remember satAT is solve simultaneous William sons the values are true and false。

 so that's an example of an instance of satAT， and that's an example of solution。

Integer linear program is solve simultaneous linear inequalities with variables are0 or1。

So here's a reduction from SAAT to an instance of linear integer linear programming。

All we do is every time that we have a knot of a boolean variable。

 we place it by1 minus one of these01 variables， so not x0 goes to 1 minus t0。

 and then x1 goes to t1， x2 goes to T2 in the first equation， and then rather than equals 2。

 we say greater than or equal to1。And then you can see the variables are  zero or1。

 that inequality is going to be true if and only if the Boolean sum is satisfied by the way that these things are set up so that is the T of I is0。

 if and only if X is false and T is one， if and only if Xi is true。

 and those inequalities are exactly equivalent to those Boolean equations。

 if we can find a solution to the integer linear programming。

 then we can just use that transformation to get a solution to that instance of sat。

 given any instance of sat， we can make an instance of integer linear programming。

 this easy think of having a a。Library method that solves inline program and it requires that we give inequalities and variables that are 01。

 so we take our satisfiability and convert it into that using this simple one minus thing for nots then the result that we get back gives us zeros and ones and we just go through and convert them to truths and falses to get the solutions to SAT。

So what this means is that there had if we had a efficient solution to integer linear programming。

 this would give us an efficient solution to SAAT， we're assuming we don't have an efficient solution to SAAT。

 so therefore we have a contradiction and therefore there's be no solution。

 efficient solution to integer linear programming just under that assumption if SaAT's intractable。

 so is integer linear programming。And that's interesting for sure。

 but what's even more interesting is many， many problems have been proven to be intractable if that's intractable in this way。

And these are just examples of problems and you can look up details of many of them， the subset。

 some problem， partition problem， bin packing problem。

 all of these are problems many related to graphs and other two sets of numbers。

So TSP is in this group of problems and these are very classic problems that people were trying to solve even as late as the 70s。

What happened was that Dick Carp proved that if under the assumption that satAT is intractable。

 all of these problems are intractable and for each one of these arrows。

 he developed a proof where given an instance of the one that the arrow points to if you had an efficient solution to that you could get an efficient solution to the one it points from and then therefore since it goes all the way back to satAT by transitivity all of these problems are intractable。

 Now so Kp's paper and that establish the idea that we can classify these problems at least in this way if SaATs intractable。

 they're intractable and that was a great step forward as it's kind of a way to establish what we think about these problems being difficult。

 all you have to do is is agree that maybe satAT's difficult to understand that all of these are also going to be difficult and actually this has been going on。

for quite some time for going on five decades now in so many fields of study where certainly computation plays a role where there's problems that it seems like there's computational solutions to protein folding and chemistry。

 financial markets with friction and economics， this is just a representative list of problems that people would like to have efficient solutions for。

 but they've been proven to be intractable if that's intractable just by reduction from some existing problem that has this property and the list is amazingly long。

 in fact there's thousands of scientific papers per year。

 proving that problems that people would like to solve are intractable if that's intractable it's a very important tool in trying to。



![](img/ebca455796d41d8a06eb7de3aedd89ca_2.png)

Understand that just under the one assumption that there's no guaranteed polynomial time algorithm for SAAT。

 there's not going to be a guaranteed polynomial time algorithm for any of these problems huge。

 huge number of problems， it's very important to understand for anyone trying to use a computer to solve difficult problems。



![](img/ebca455796d41d8a06eb7de3aedd89ca_4.png)

![](img/ebca455796d41d8a06eb7de3aedd89ca_5.png)