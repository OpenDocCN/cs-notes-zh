# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P78：03_01_01_贪心算法导论.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Today we're going to embark on the discussion of a new algorithm design paradigm。

 namely that of designing and analyzing greedy algorithms。

 so to put this study of greedy algorithms in a little bit of context， let's just zoom out。

 let's both review some of the algorithm design paradigms that we've already seen as well as look forward to some that we're going to learn later on in this course。

So it's sort of a sad fact of life that in algorithm design there's no one silver bullet。

 there's no magic potion that's the cure for all your computational problems。

 so instead the best we can do in the focus of these courses is to discuss general techniques that apply to lots of different problems that arise and lots of different domains。

 so that's what I mean by algorithm design paradigms。

 high levell problem solvinglving strategies that cut across multiple applications。

So let's look at some examples。Back in part one， we started with the divideiv and conquer algorithm design paradigm。

 a canonical example of that paradigm being the merge sort algorithm。

 so remember in divide and conquer what you do is you take your problem。

 you break it into smaller subprobles， you solve the subproblems recursively。

 and then you combine the results into a solution to the original problem， like how in merge sort。

 you recursively sort to subarrays and then merge the results to get a sorted version of the original input or array。

Another paradigm that we touched on in part one， although we didn't discuss it anywhere near thoroughly is that of randomized algorithms。

 so the idea that you can have code flip coins that is make random choices inside the code itself。

 often this leads to simpler， more practical or more elegant algorithms。

 a can application here is the quickword algorithm using a random pivot element。

 but we also saw applications for example， to the design of hash functions。

So the next major paradigm we're going to discuss is that a greedy algorithm。

 so these are algorithms that iteratively make myopic decisions。In fact。

 we've already seen an example of a greedy algorithm in part one。

 namely Dykestra's shortest path algorithm， and then the final paradigm we're going to discuss in this class is that of dynamic programming。

 a very powerful paradigm which solves in particular two of the motivating questions we saw earlier。

 namely sequence alignment and distributed shortest paths。So what is a greedy algorithm anyways。

 Well， to be honest， I'm not going to offer you a formal definition， in fact。

 much blood and ink has been spilled over which algorithms precisely are greedy algorithms。

 but I'll give you an informal description， a sort of rule of thumb for what greedity algorithms usually look like。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_1.png)

![](img/dcc71ec79468373b3efe5d2a071ff2ad_2.png)

Generally speaking， what a greedy algorithm does is make a sequence of decisions with each decision being made myopically。

 that is it seems like a good idea at the time， and then you hope that everything works out at the end。

The best way to get a feel for greedy algorithms is to see examples and the upcoming lectures will give you a number of them。

 but I want to point out we've actually already seen an example of a greedy algorithm in part one of this course。

 namely Dyktra's shortest path algorithm。

![](img/dcc71ec79468373b3efe5d2a071ff2ad_4.png)

So in what sense， is Dyxtra's algorithm a greedy algorithm， Well。

 if you recall this pseudocode for Dxtras algorithm。

 you'll recall this one main while loop and the algorithm processes exactly one new destination vertex and each iteration of this wild loop。

 So there's exactly n -1 iterations overall， where n is the number of vertices。

 So the algorithm only gets one shot to compute the shortest path to a given destination。

 it never goes back and revisits the decision。 In that sense， the decision are myopic， arevocable。

 and that's the sense in which Dxtra's algorithm is greedy。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_6.png)

![](img/dcc71ec79468373b3efe5d2a071ff2ad_7.png)

So let me pause for a moment to discuss the greedy algorithm design paradigm generally。

 Probably this discussion will seem a little abstract。

 So I recommend you revisit this discussion on this slide after we've seen a few examples。

 And at that point， I think it'll really hit home。 So let me proceed by comparing and contrasting it to the paradigm we've already studied in depth that of divine and conquer algorithms。

 So you'll recall that in a divine and conquer algorithm。

 what you do is you break the problem into subproblem。

 So maybe you take an input array and you split it into two subarrays。

 So you solve the smaller subproblems recursively and then you combine the results of the subproblems into a solution to the original input。

 So the greedy paradigm is quite different in several respects。 First。

 both a strength and a weakness of the greedy algorithm design paradigm is just how easy it is to apply。

 So it's often quite easy to come up with plausible greedy algorithms for a problem。

 Even multiple difference plausible greedy algorithms。

 I think that's a point of contrast with divine and conquer algorithms。

 Often it's tricky to come up with a plausible divine and conquer algorithm。

 and usually you have this eureka moment where you finally。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_9.png)

Figure out how to decompose the problem in the right way and once you have the eureka moment。

 you're good to go。So secondly， I'm happy to report that analyzing running time of greedy algorithms will generally be much easier than it was with divide and conquer algorithms For D and conquer algorithms。

 it was really unclear whether they were fast or slow because we had to understand the running time over multiple levels of recursion on the one hand problems size was getting smaller on the other hand the number of sub problems was proliferating so we had to work hard we developed these powerful tools like the master method and some other techniques for figuring out just how fast an algorithm like merge sort runs or just how fast an algorithm like Str and fast matrix chipps multiplication algorithm runs In contrast with greedy algorithms。

 itll often be a one liner， often itll be clear that the work is dominated by say a sorting subroutine and of course we all know that sorting takes n log n time if you use a sensible algorithm for it。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_11.png)

Now the catch and this is the third point of comparison is we're generally going to have to work much harder to understand correctness issues of greedy algorithms for divine and conquer algorithms。

 we didn't talk much about correctness， it was generally a pretty straightforward induction proof。

 you can review the lectures on quick sort if you want an example of one of those canonical inductive correctness proofs。

 but the game totally changes with greedy algorithms。 In fact， given a greedy algorithm。

 we often won't even have very good intuition for whether or not they are correct。

 let alone how to prove they're correct So even with a correct algorithm it's often hard to figure out why it's correct。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_13.png)

![](img/dcc71ec79468373b3efe5d2a071ff2ad_14.png)

And in fact， if you remember only one thing from all of this greedy algorithm discussion many years from now。

 I hope one key thing you remember is that they're often not correct， often。

 especially if it's one that you proposed yourself， which you're very biased in favor of。

 you will think the algorithm， the greedy algorithm must be correct because it's so natural。

 but many of them are not， so keep that in mind。So to give you some immediate practice with the ubiquitous incorrectness of natural greedy algorithms。

 let's review a point that we already covered in part one of this class concerning Dytra's algorithm。

 Now， in part 1， we made a big deal about what a justly famous algorithm。

 Dyketer's shortest path algorithm is， it runs blazingly fast and it computes all of the shortest paths。

 What else do you want。 Well， remember， there was an assumption when we proved that Dyketra's algorithm is correct。

 We assumed that every edge of the given network。 has a nonneg length。

 We did not allow negative edge lengths。 And as we discussed in part 1， you know。

 for many applications， you only care about nonnative edge lengths。

 but there are applications where you do want negative edge lengths。

 So let's review on this quiz why Dys is actually incorrect。 Despite being so natural。

 It's incorrect when edges can have negative lengths。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_16.png)

![](img/dcc71ec79468373b3efe5d2a071ff2ad_17.png)

So I've drawn in green a very simple shortest path network with three edges and I've annotated the edges with their length。

 you'll notice one of those edges does have a negative length。

 the edge from V to W with length minus2 so the question is consider the source vertex S and the destination vertex W and the question is what is the shortest path distance computed by Dxts algorithm and you may have to go and review just a pseudocode in part1 or on the web to answer that part of the question and then what is in fact the actual shortest path distance from S to W where as usual the length of a path is just the sum of the length of the edges in the path？

All right， so the correct answer is D。

![](img/dcc71ec79468373b3efe5d2a071ff2ad_19.png)

So let's start with the second part of the question。

 what is the actual length of a shortest path from S to W where there's only two paths at all in the graph。

 the one straight from S to W that has length2 and the one that goes via the intermediate point v that has length3 plus minus2 equal to1 which is shorter So Svw is the shortest path that has length1 Y is diixstra incorrect Well if you go back to the pseudocode of diktra you'll see that in the very first iteration it will greedily find the closest vertex to S in that case this is Ww is closer than V itll greedily compute the shortest path distance to W knowing the information it has right now and all of those is there's this one hop path from S to W So itll irrevocably compute to the shortest path distance from S to W as2 never reconsidering that decision later So Dyixtra will terminate with the incorrect output that the shortest path length from S to W is2 This doesn't contradict anything we proved in part1 because we establish correctness of Dixtra only under the assumption that all edge length are not negative an assumption which is violated in this。

but again， the takeaway point here is that you know it's easy to write down a greedy algorithm。

 especially if you came up with it yourself， you probably believe deep in your heart that it's got to be correct all the time。

 but more often than not probably your greedy heuristic is nothing more a heuristic and there will be instances on which it does the wrong thing so keep that in mind in greedy algorithm design。

So now that my conscience is clear， having warned you about the perils of greedy algorithm design。

 let's turn to proofs of correctness。 That is， if you have a greedy algorithm that actually is correct and we'll see some notable examples in the coming lectures。

 how would you actually establish that facts or if you have a greedy algorithm and you don't know whether or not it's correct。

 How would you approach trying to understand which one it is， whether it's correct or not。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_21.png)

So let me level with you， proving greedy algorithms correct， frankly。

 is sort of more art than science。 So unlike the divine and conquer paradigm where everything was somewhat formulaic。

 we had these black box ways of evaluating recurrences。

 we had this sort of template for proving algorithms correct。

 really proving correctness of greedy algorithms takes a lot of creativity and it has a bit of an ad hoc flavor That said as usual to the extent that there are recurring themes。

 that is what I will spend our time together emphasizing。 So let me tell you just again。

 very high level how you might go about this， you again might want to revisit this context content after you've seen some examples where I think it'll make a lot more sense。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_23.png)

![](img/dcc71ec79468373b3efe5d2a071ff2ad_24.png)

So a method one is our old friend or perhaps nemesis depending on your disposition。

 namely proofs by induction Now for greedy algorithms remember that they do is they sequentially make a bunch of irrevoical decisions So here the induction is going to be on the decisions made by the algorithm and if you go back to our proof of correctness of Dyster's algorithm that in fact is exactly how we proved Dykester's algorithm correct it was by induction on the number of iterations and each iteration of the main while loop we computed the shortest path to one new destination and we always proved that assuming all of our previous computations were correct。

 that's the inductive hypothesis then so is the computation and the current iteration and so then by induction everything the algorithm ever does is correct So that's a greedy proof by induction that a greedy algorithm can be correct and we might see some more examples of those for other algorithms in the lectures to come。

Some of the textbooks call this method of proof greedy stays ahead。

 meaning you always prove greedy' is doing the right thing， iteration by iteration。

So a second approach to provingrov the correctness of greedy algorithms。

 which works in a lot of cases is what's called an exchange argument。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_26.png)

So you haven't yet seen any examples of exchange arguments in this class。

 so I can't really tell you what they are， but that's what we're going to proceed next。

 I'm going to argue by an exchange argument that a couple of different famous greedy algorithms are in fact correct。

 It has a couple different flavors， one flavor is to approach it by contradiction you assume for contradiction that a greedy algorithm is incorrect and then you show that you can take an optimal solution and exchange two elements of that optimal solution and get something even better。

 which of course contradicts the assumption that you started with an optimal solution a different flavor would be to gradually exchange an optimal solution into the one output by a greedy algorithm without making the solution any worse that would show that the output of the greedy algorithm is in fact optimal and then formally that's done by an induction on the number of exchange is required to transform an optimal solution into yours。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_28.png)

And finally， I've already said it once， but let me say it again。

 there's not a whole lot of formula behind proving greed algorithms correct。

 you often have to be quite creative， you might have to stitch together aspects of method one and method2。

 you might have to do something completely different， really any rigorous proof is fair game。



![](img/dcc71ec79468373b3efe5d2a071ff2ad_30.png)