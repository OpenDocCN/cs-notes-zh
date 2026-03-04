# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P26：26_07_02_合理问题.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/a9e7df1a58fb719b419b4d8e3dbbc851_0.png)

Turing's work about computability really taught us about the difference between things that we can compute and things that we absolutely cannot compute with any computer we can imagine。

 We didn't pay any attention at all to efficiency as to how difficult it is to compute things。 Today。

 we're going to address that part of the situation。

So we're going to start by just addressing some reasonable questions about things that we might want to compute the same way that we did with computability。

So we talked last time about the fundamental questions that were addressed by Turing's work。

 like what is a general purpose computer？Are there limits on what we can do with digital computers and we found that there were with the halting problem and several other examples？

Today， what we're going to talk about is， are there limits with what we can do in the machines that we can actually build in this universe。

 that's the focus of today's lecture。This question was actually first raised by Gerirdel in a so called lost letter to Von Neumman。

 and actually John Nash also asked this question in another so called lost letter to the NSA。

 of course both of these letters were later found。Then one of the first breakthroughs were due to Michael Raven and Dana Scott。

 who introduced the idea of non determinism that we'll talk about in more detail。

But really the main question was posed in the 70s by work by Dick Carp。

 Steve Cook and independently Leonard Levin， and that's really the question that we're going to talk about and unlike in the last lecture this question is still unknown so we don't know the answer to it or who's going to provide the answer。

 this is a fascinating context for such an important question that's still unresolved many decades after it was first proposed。

So to get thinking about it， let's start with a well known problem that's known to be difficult。

 it's called the Travel salesperson problem or TSP。

And the idea is you're given a set of N cities and you're given distances between each pair of cities。

 and you're giving a threshold distance N。 And so the problem is， you want to know。

 is there a tour that goes through all the cities going back to the beginning that's of length less than N。

It's going to be formulated in different ways， but we're going to think about this particular one just now。

So clearly one thing that we might do is to so-called exhaustive search where we try all n factorial orderings of the cities to look for a tour of length less than M。

 and you can imagine that's not going to work for a very large set of cities for n very large and so that's the kind of problem that we're going to be addressing。

And so how difficult can that be， this is just excerpts from a blog recently found on the internet。

And someone says， well， if one took the 00 largest cities in the US and wanted to travel them all。

 what's the distance of the shortest route？Of course。

 if you could solve this one with a threshold of M。

 you could use binary search to find the shortest one。So it's an equivalent problem in many ways。

 So I'm sure there's a simple answer。 Anyone want to help a quick Google reveal nothing about this。

And then the next thing as well， I don't think there's any substitute for doing it manually。

 Google the cities， pull out your map and get to work， it shouldn't take longer than an hour。Edit。

 I didn't realize this was a standardized problem， well it might be a standardized problem。

 but there's another edit needed here。While writing to a program to solve the problem would take five or10 minutes for an average programmer。

 well， maybe a little more than that， but certainly all of you could write programs to solve this。

However， the amount of time the program would need to run it is well a long， long time。Well。

 my garmin could probably solve this for you or my cell phone nowadays， my maps application。

Then there's an edit， well， probably not。呃。Someone needs to write a distributed computing program to solve this in my opinion those are the types of things that well it can't be that difficult。

 can it really well let's do a little bit of analysis so in order to think about this from the right perspective I want you to imagine a giant computing device we'll try to make this the most powerful computing device that we can imagine soll call it an Uber computer。

So it's got a processor on every electron in the universe。

 so that's trying to get the biggest computer we could imagine。And let's say that each processor。

 there's one on every electron in the universe， will say that each one of them has the power of the fastest supercomputer we know today。

And that each one of them is working the lifetime of the universe。

 So you take your fastest supercomputer。 you put one on every electron in the universe。

 and you have it work for the lifetime of the universe。

So and this is just conservative estimates and you can use other estimates if you want。

 but let's say 10 to the 79th electrons in the universe。

 maybe a supercomputer does 10 to the 13th instructions per second or make a 10 to the 20th。

 whatever you want say the age of the universe and second is 10 to the 17th so maybe that's an under maybe 10 to the 30th but let's stick with these and then we say okay so suppose we use this algorithm of trying every arrangement of the cities and looking for the smallest could the Ubercomputer solve it using that algorithm and the answer is not even close100 factorial is more than 10 to the 10 57th power and if you have every electron of the universe with a supercomputer and running for the age of the universe then you want to get to about 10 to the 10 and9th so not only are you not going to solve it using that method with the Uber computer。

But you'd need 10 to the 48th Uber computers。So this is a difficult problem。

 you're not going to solve it with a computer using that method and it's really important lesson to have in mind when you're thinking about the topic of this lecture and the whole point is that exponential growth when you have a number to your problem size is the amount of time that you're taking that the technological change is irrelevant。

 exponential growth is so huge is to take anything that you might think about technology totally out of the question。

So we have questions like are we going to be able to solve this problem。

 are there better computers and that's the kind of question that we want to address it's nothing to do with the technology that we're using really so these are the kinds of questions then that come up。

Which algorithms are going to be useful to solve practical problems？So we'll just use a very。

 very simple model of computation to try to address this question just to get started the same way that we did with theoretical with the question of whether we can compute or not。

 we'll try to take the most basic model that we can to get going。

And so what we're going to think about is the idea of a polynomial time algorithm so polytime means that the running time is less than a times n to the B for some constants A and B and so we talked when addressing real applications problems about the need to get solutions that are faster than n squared or n cubed and so forth。

 those are all fine but for this purpose we're saying even if it's n to the0th。

 we're interested because what we want to avoid is exponential time it's definitely not polynomial time where the running time is proportional to C to the N for any constant C bigger than one so our separation is between polynomial time and exponential time and again the specific computer is generally not relevant because when you simulate one computer on another it generally uses only。

A polynomial factor， that's called the extended church Tring thesis。

 and we'll talk about that in a minute。So in the context of this lecture。

 what we want to say is that an algorithm' is efficient if it's guaranteed to run at polynomial time no matter what the input is。

We're just going to use the word efficient and we're going to look for efficient algorithms or for problems that emit efficient algorithms for solving them。

Now outside this lecture we might say guaranteed polynomial time or sometimes they just say polynomial time。

 we want to make sure that it's polynomial time for all inputs。

 but for shorthand we're just going to use the word efficient。

And understand that we're separating those kinds of algorithms for ones that might be slow。

 that might take exponential time。And the question。

 the basic question we have is we have a lot of practical problems and we want to know if we can find efficient algorithms。

 it seems like a reasonable reasonable question that we should be able to answer， that's our topic。

SoYou can turn around that and say which problems can we solve in practice and those are the ones that we know efficient algorithms for those problems。

 if we have a problem that we want to solve and we have an efficient algorithm fine then we're going to save for the purposes of this lecture that those are the ones that we can work on implementing algorithms and solving and so forth。

On the other hand， if we can show that there's no efficient algorithm to solve a problem。

 we're going to call it intractable， this is analogous to what we did for computability。

 we could talk about the idea of something that can be solved with a Turing machine and we talk about something that we can't solve with any tuuring machine that's computability not computability。

 we want to have the same idea， same kind of separation between problems that are intractable and problems that we know efficient algorithms for。

Would like an easy way to know whether there are problems intractable。

 that's what we're going to talk about today。So for example， sorting， that's not intractable。

 we have algorithms that take time that are guaranteed to take time proportional to some polynomial。

 and it doesn't matter that we have a faster one like N log N。

 as long as it's any polynomial at all we're fine for this lecture。But for the TSP， for example。

 nobody knows an efficient algorithm， but we also don't have a proof that there's no efficient algorithm。

That's the issue that we want to talk about so to get started we're going to talk about four basic fundamental problems so first one is probably familiar from secondary school L solve。

 so we want to solve simultaneous linear equations。

So we have some unknown values and we have some equations that those values have to satisfy simultaneously。

 the variables are real numbers and so there's an example of three equations and three variables and you learn in school how to develop a solution for that in this case the solution is this one x1 equals a half x2 equals a half。

 so x1 plus x2 equals1，3 x1 plus 15 x2 that's 18 times a half that's nine and then the other one you can check is adds up to a half。

So you've may be familiar with Gaussian elimination， which can solve that problem。

There's a similar one called LP or linear programming。 again， the variables are real numbers。

 but now we're going to make the equations that they have to satisfy inequalities。

 So here's four inequalities and three or actually six and three unknowns so we have a bunch of variables and we have inequalities and we want them all to simultaneously satisfy those inequalities In this case the bottom one says that the solution should all be positive values。

 they're all real numbers and then you can plug in these values and you can see that check that that solution satisfies those inequalities。

 that's called linear programming。 how do we get to that solution。

And then there's one called integer linear programming。

 which is the same problem except that the variables have to be either zero or one。

 one of the two values， that's integer linear programming。

And there's another one called satisfiability and now our variables are Boolean values either true or false and then we've got simultaneous Boolean sums that have to be satisfied simultaneously so that is not x1 or x2 is true and so forth and then that's an example and then there's a solution that first one is satisfied because x2 is true and the second one is satisfied because x0 is false。

 so not x0 is true， and the last one satisfied because x1 is true。So again。

 given the equations develop the solution， that's the problem。

Now these problems are very similar and they're actually all very important problem solvinglving models with lots of practical applications。

 we take a practical problem and formulate it very often in one of these regimes and then the solution is going to tell us what we need to do in some kind of practical situation many。

 many applications for each one of these so it's a pretty reasonable question to ask is do we have efficient algorithms for solving these things they look so similar how what's the story on these things and as soon as computation came around people started looking at using computers to solving these problems and it's very difficult to tell which ones are atable and which ones have efficient algorithms for solving them。

So L solved solving simultaneous equations， yes， in fact。

 we do Gaussian elimination itself doesn't quite work in this model because the numbers are real after representing with bits in a computer。

 but still with an appropriate modification， Gaussian elimination can guarantee to solve this L solved problem。

 simultaneouslyimultous linear equations in polynomial time， no matter what the input is。

Linear program， the answer is also yes， but that was decades after the problem was first formulated。

 it was opened for a long time a people debated whether or not there might exist fission algorithm for linear programming and then the ellipsoid algorithm was an amazing tour of voice in the 1980s was a proof that linear programming could be solved in polynomial time and actually in the years since that's been developed and once the idea was known other polynomial Italian algorithms were developed that are actually useful and practical situations are important part of our computational infrastructure now but integer linear programming。

 nobody knows a polynomial time algorithm and nobody knows whether one exists and satisfiability the same no polynomial time algorithm known and nobody knows whether one exists。

These are quite reasonable， similar interesting， important practical questions and we don't know the answer。

 that's the basic question， can we find efficient algorithms for integer programming and satisfiability or can we prove that no such algorithms exist those are the kind of questions that we're going to be talking about in this lecture。

So the idea is intractability。 the let's do the definitions and then talk about it some more。

 So we said that an algorithms efficient if it's running time is guaranteed to be polym unless it's some polynomial for all inputs。

We're going to call a problem intractable if there's no efficient algorithm to solve it。

 we can prove there's no way that you can solve it with polynomial time guaranteed polynomial time algorithm。

 we're going to call it intractable。By know converse of that is a problem is tractable if we have an efficient algorithm。

 So， of course， we're interested in knowing whether or not a problem is tractable or intractable。

 And again， touring taught us something fundamental about computation by identifying a problem and we might want to solve and showing that it's not possible to solve it and then by knowing that then we could see other problems that were related could reduce to that problem and and helped us understand more about computation So it's a pretty reasonable question to say can we do something similar for intractability。

So with touring we had decdable and undecidable now we have tractable tractable versus intractable so the first question is。

 well there's a lot of problems not just integer linear programming and satisfiability but many。

 many problems that we don't know efficient algorithms for solving them so the first thing that comes up is can we prove one of them to be intractable。

 that's the critical question that we face and that's what we're going to start laying the groundwork for next。

So this is a profound connection of the real world that's analogous to the church Tring thesis。

 it's called the extended church Tring thesis and the idea of this is so church Tring says that any computing device that we build is going to have the same power as a touring machine。

 what this one says is that the resources used by all reasonable machines are going to be within a polynomial factor of one another。

 Of course you can conjure up some machine that that must take a huge amount of time for simple tasks but the kind of reasonable computational models that people have developed a machines that have been designed always are within a polynomial factor。

 Again， this is a thesis。 It's not a theorem， It's not subject to proof somebody maybe can come up with a computer that can't be simulated in polynomial time on any other computer but the question is is this a new model of。

Computationer is just something new about the universe so always we use simulation to prove a polynomial bound so for example。

 we're going to look later at a simple machine that is like your computer processor and we're going to write a Java program to simulate the operation of that machine or you could write a program called a compiler that translates a Java program into that machine。

 so that proves that those things are equivalent and the cost of these computations is definitely bounded by a polynomial it's easy to show and that's been true for again every reasonable machine model that people have been developed。



![](img/a9e7df1a58fb719b419b4d8e3dbbc851_2.png)

So this validates the focus on the distinction between exponential and polynomial time algorithms。

 so polynomial time on one machine， it' going to be polynomial time and all the machines that we can think of and that's a whole different thing than exponential time on a machine and it really enables us to rigorously study efficiency in the same way we're able to rigorously study computability and that's where we're going to go in this lecture。



![](img/a9e7df1a58fb719b419b4d8e3dbbc851_4.png)