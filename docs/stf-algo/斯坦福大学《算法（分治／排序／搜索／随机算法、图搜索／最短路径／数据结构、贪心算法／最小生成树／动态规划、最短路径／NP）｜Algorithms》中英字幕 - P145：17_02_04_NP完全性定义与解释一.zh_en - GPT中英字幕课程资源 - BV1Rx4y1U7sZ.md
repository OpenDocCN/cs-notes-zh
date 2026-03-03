# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P145：17_02_04_NP完全性定义与解释一.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/bd6514236927f2cc323b1bced374e556_0.png)

We now arrive at the heart of the discussion， the definition of the complexity class NP as computational problems where you can efficiently recognize a solution。

 roughly the same thing as problem solvable using brute4 search。

 the idea of NP completeness that a problem can be as hard as any other problem where you can efficiently recognize a solution。

 the ubiquity of NP complete problems including possibly a problem you're working on right now in one of your own projects。

 and what should be part of your toolbox， a simple recipe for proving the problems or NP complete。

We left off the last video noting that the travelinging salesman problem by virtue of being solvable in exponential time using brutefor search is certainly not as hard as notorious problems like the halting problem。

 So perhaps we can instead amas evidence of intractability for the T SP by showing its as hard as any other problem solvable using brute force search。

 that as every other brute force search solvable problem reduces to solving the troing salesman problem to turn this idea into mathematics。

 we have to identify the minimal ingredients necessary to solve a problem using brute force search。

 And the key idea turns out to be the efficient recognition of purported solutions。Specifically。

 we say that a computational problem， like say， the shopping salesman problem， or frankly。

 almost any other problem we've talked about in these classes。

 is a member of the complexity class NP if it meets the following two criteria。

The first property is sort of a simple prerequisite。

 it asserts that solutions have length polynomial in the input size。The second property。

 and this is really the key one， is that if someone offers up to you a purported solution to an NP problem。

 you can verify its correctness in polynomial time。To make sense of this abstract definition。

 let's think about some concrete examples。 Let's start just with a traveling salesman problem。

So consider an instance of the traveling salesman problem。

 it's specified by some invertices and distances amongst all of the pairs of vertices。

 and suppose we really want to know whether or not there's a tour that has total length at most 1000。

So let's， for the moment， set aside the problem of checking whether or not one of the n factorial tours does indeed have cost in most 1000。

 Let's instead think about the much more modest question of whether or not a single proposed tour has cost in most 1000。

 Well， that computational problem。 Just verifying whether or not a single suggested tour meets the target or not。

 That's an easy computational problem。 The to is specified just by an order in which you're supposed to visit the vertices。

 The length of that ordering is certainly polynomial in the length of the input and all you got to do is add up the n edges that get traversed in this tour and check if the sum is at most 1000 or not。

This argument shows that checking whether or not there exists a tour with total cost at most some threshold does indeed belong to the complexity class NP right You can write down a purported solution in polynomial length。

 All you need to do is specify the ordering， and you can verify whether or not a candidate solution。

 whether or not a proposed tour meets the threshold in linear time。

 just by adding up the corresponding edge costs。If it bothers you that I moved away from the problem of computing an optimal minimum cost tour and studied instead。

 the seemingly easier problem of just checking， does there exist a tour that has total cost at most a given threshold。

 notice that the former problem reduces to multiple indications of the latter problem just by binary search over the threshold。

The same reasoning can be applied to pretty much all of the computational problems we've seen in these courses。

 placing all of them into the complexity class NPP。

 So for the types of problems we've been thinking about。

 solutions can generally be specified in linear space， correctness can be verified in linear time。

Another genre of problems that we haven't really discussed in these classes。

 but are important in many application domains and are also canonical NP problems are constraint satisfaction problems。

In general， in a constraint satisfaction problem， you have a bunch of variables。

 the simplest case would be binary or boolean variables， and then you have a list of constraints。

 and each constraint specifies for a subset of the variables permitted list of configurations of those variables。

 So one simple case， which some of you will have seen。 And if you studymp completeness properly。

 you'll definitely see it will be the threeatAT problem。

The threesap problem does indeed concern boolean variables so each variable Xi can either be0 or 1。

 and you can think of the clauses as forbidding a single assignment to a triple of vertices。

 so clause might say you are not allowed to simultaneously assign x3 to 1 x5 to0 and x8 to 1 so clauses forbid particular triples of assignments and the question then is does there exist an assignment of all of the variables to0 and1 that simultaneously satisfies all of the constraints。

These kinds of constraintsstraint satisfaction problems also belong to the complexity class NP。

 so here if you have a purported assignment of all of the variables to values that meets all of the constraints。

 well you can write it down very simply just the value for each of the variables and it's easy to check I just iterate through the constraints one at a time and see if yes indeed。

 the values that you're suggesting for the variables in that constraint are on the list of permissible value combinations。

At the beginning of this video， I suggested that the complexity class NP P would represent problems that are brute force solvable in the same way that the traveling salesman problem is。

If you look at the actual definition I just gave you of the class NP。

 it's in terms of efficient recognition of solutions。

 but let's now observe that this definition of NP in terms of efficient verification of purported solutions does indeed imply that these problems can be solved in exponential time using brutefor search。

So really all you do here is check each of the candidate solutions one at a time。

 and in doing so you see very clearly the role of the two properties in the definition of an NP problem。

 the role of the first property saying solution length has to be polynomial in the input size。

 in turn restricts the number of possible solutions。

 the number of bit strings of that given length to be at most exponential in the input size。

The second property， of course assures you that for each of those only exponentially many possibilities。

 you can verify whether or not it is， in fact a correct solution。

 whether or not it's a short TSB tour， whether or not it's a satisfying assignment to some variables in a constraint satisfaction problem in polynomial time。

Now， because the requirements for membership in the class NP are so weak， the class NP is very big。

 right all membership and NP requires essentially is the ability to efficiently recognize a solution。

 You know one when you see one， and as you can imagine。

 that property is met by many of the computational problems that we ever think about factoring almost any graph problem you'd ever think about。

 sequencing problems， most constrain satisfaction problems and so on。



![](img/bd6514236927f2cc323b1bced374e556_2.png)

As we have said， it's true that not every natural computational problem is NP。

 The halting problem is an extreme example。 That's， in fact， undecidable。

 There's no algorithm at all。 There's also some natural problems in some application domains which are neither in NP nor they undecidable。

 So model checking is one domain that furnishes lots of examples of problems strictly harder than NP。

The vastness of the complexity class N P means that N P completeness is strong evidence of intractability。

 Remember what it means for a problem to be complete for some set of problems。

 It means it's as hard as any other problem in that set。

 Every other problem in that set reduces to the complete problem。 Therefore。

 suppose you had a polynomial time algorithm。 for just one N P complete problem。

You would get automatically by the definition of a reduction。

 a polynomial time algorithm for every single computational problem in NP。

 every single problem for which you can efficiently recognize a solution。That is。

 solving just one NPP complete problem in polynomial time would imply that NP is the same as P。

 Every problem in NP can be solved in polynomial time。

It's pretty hard to really gr all of the ramifications of this kind of result if P were to equal NP。

 so just as one example， modern E- commerce， as we know it would fall apart like a house of cards。

That's because it depends on the security of cryptoytems like RSA。

 which in turn assumes the computational intractability of problems like factoring。

 yet an efficient algorithm for even the most obscure NP complete problem would automatically imply。

 at least in principle a polynomial time algorithm for factoring。

So this provides a satisfying resolution to a narrative we began in the previous video recall we were discussing the traveling salesman problem and like thousands of other people。

 we were wondering whether or not theres a polynommal time algorithm for it or not， for example。

 Edmonds conjectured in 65 that there is no polynomial time algorithm for it。

Now obviously what you really want is the answer， you either want a proof of Edmin's conjecture that there's no efficient algorithm for TSP。

 or even more astonishingly， you'd want a polyno time algorithm that solves the problem。

But we also have to face the reality that we may not know the answer for sure to this question for quite a while。

 years， certainly， decades， probably centuries， Who knows， maybe。

So the challenge then for people thinking about algorithms and computation is to nevertheless devise a theory which usefully differentiates tractable problems from relatively intractable ones。

 even in the face of this massive deficiency of our understanding of what is possible and what is impossible。

And the brilliant way out is relative difficulty， as now personified by N completeness。

 If you want to amass extremely strong evidence of the computational intractability of a problem。

 prove that its's NP complete， prove that upon all time algorithm for the problem if it existed would solve thousands upon thousands of unsolved computational problems。

