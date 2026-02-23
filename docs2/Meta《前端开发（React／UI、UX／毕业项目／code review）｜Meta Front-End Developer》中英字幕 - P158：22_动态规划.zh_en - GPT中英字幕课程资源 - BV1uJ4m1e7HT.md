# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P158：22_动态规划.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

In the build up to dynamic programming， you have learned about the divide and conquer paradigm and recursions。

In this video you will learn about the concepts of memorization and dynamic programming dynamicy programming is a programming paradigm that promotes solving problems by breaking them into smaller problems and solving these。

😊，The solutions are then stored in an appropriate data structure for later use。

The advantage to this is that if these sub problems require being computed again。

 one only searches for the answer instead of computing the problem again。



![](img/81a6432207f288b002bb0bbcae282718_1.png)

The technique of solving sub problems and storing them to save time on a potential future look up is known as memorization。



![](img/81a6432207f288b002bb0bbcae282718_3.png)

Dynamic programming relates to two concepts already encountered in the previous videos。

Let's have a quick refresher on these concepts。 The first is divide and conquer。

 That is taking one large problem and breaking it into a smaller set of sub problems and then solving these。



![](img/81a6432207f288b002bb0bbcae282718_5.png)

The second is a subset of this known as recursion。 Recursion is the practice of coding a solution that avoids running loops。

 but instead uses multiple self calls in coming upon a solution。

Dynamic programming is an extension of these approaches。

 which in addition involves keeping a record of results generated from running the sub problemsble each time they are newly run。

😊，In subsequent runs， instead of recomputing results。

 a lookup is queried for the last time the question was asked。As said。

 this approach is called memorization and to reinforce the concept。

 This is when the results of previous calculations are stored and used in place of rerunning the calculations when the compiler identifies that the computation has been run for a previous task。

To exemplify this， consider the question posed in the video about binary numbers。

How many combinations were possible with a binary lock of six digits？😊，In a previous video。

 it was shown that you can discover this through exponnunciation or finding the power of a number。

 so the same lock with six digits would have two to the power of six or 64 combinations。😊。

So two to the p of six equals two times two times 2 times2 times 2。Alternatively。

 you can divide these into two groups where you have calculated two times 2 times 2， and again。

 two times 2 times2， that will result in 8 times 8 and again give the same result。

 applying a divide and conquer approach to computing this efficiently using memorization would reduce the computations by first calculating to the power of three and again two to the power of three。

😊，By applying memorization， the first two to the power of three would be computed。

 then reused for the second bracket， reducing the overall computation required。

So what sorts of problems are good fits for a dynamic solution。

 The dynamic programming approach is commonly applied to combination or optimization problems。



![](img/81a6432207f288b002bb0bbcae282718_7.png)

One example of a combination problem already mentioned is the Fibonacci sequence。

 Another instance you may encounter in an interview is thenapsack problem。😊。

This is both a combination and an optimization problem。



![](img/81a6432207f288b002bb0bbcae282718_9.png)

Save for a planned camping trip。 You can fill a knapsackack with required items。

 Each item has a weight cost to it。 A torch equals 1 kg。 water equals 2 kg， and the tent equals 3 kg。

 Additionally， each item has a value。 The torch equals 1。 water equals 2， and the tent equals 3。

In short， thenapsack problem outlines a list of items that weigh different amounts and have different values。

 You can only carry so many items in yournapsack。 The problem requires calculating the optimum combination of items you can carry if your backpack can carry a certain weight。

 The goal is to find the best return for the weight capacity of thenapsack to compute a solution for this problem。

 You must select all items that add up to a given weight and contain a given value。

The weight carryable will change。This problem can be applied to resource allocation where you have so much CPU power and X tasks to run。

 just like the capacity of a CPU dedicated to completing tasks。 Sometimes the weight will be 7 kg。

 and other times it might be 10 kg Dy programming involves saving the computations used to come upon a given solution。

😊，So if you have computed an optimum selection for 7 kg and it is raised to 10 kg。

 you will not have to rerun the initial computations again。 This can be a time saving metric。

 When computing dynamic programming solutions， you must firstly determine the objective function。

 That is the description of what the optimum outcome is to be。 Next。

 you must break the problem into smaller steps。One approach already discussed for achieving this can be the use of recursive functions。

 That is functions that will call themselves repeatedly until a solution is come upon。

 They should be written in such a way that you can change the outcome without altering the code for the methods already written。

😊。

![](img/81a6432207f288b002bb0bbcae282718_11.png)

To conclude in this video， it has been shown that dynamic programming is an approach that looks to optimize solutions to a given problem；

 it uses principles of memorization and overlapping subpro to identify when an objective function can be achieved quickly。

 optimizing the computation steps required。😊。