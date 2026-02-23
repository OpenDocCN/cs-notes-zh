# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P150：23_贪心算法.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

In this video， you will learn how you can implement this paradigm to solve complex problems by using greedy algorithms。

 There is a philosophical principle called Oham's Razor。

 It states that the simplest solution is almost always the best one。

This problem solving principle argues that simplicity is better than complexity。In our case。

 the greedy algorithm is the simple solution。

![](img/2f88322829d79a98deb0e8d2d0f43a4c_1.png)

This is an alternative approach to dynamic programming。

 as this approach seeks to present an immediate solution for a task and favors local optimization over a more holistic global approach。



![](img/2f88322829d79a98deb0e8d2d0f43a4c_3.png)

When engaging with a problem subdivided into segments。

 utilizing a dynamic programming approach would find a globally optimal solution so that each subpro is solved and the best subset is selected and implemented。

A greedy approach would instead look at the list of solutions and implement a local optimization。

Usually， the current most rewarding option is chosen。



![](img/2f88322829d79a98deb0e8d2d0f43a4c_5.png)

To make this more clear， let's take an instance of a CPU that has a list of tasks to be completed。

Applying the dynamic programming approach would entail selecting a subset of activities that could be completed within a given time and executing these tasks with thenapsack analogy。

 This would involve determining what subset of items to pack that would max the value in the process of filling the bag。

 A greedy algorithm approach to this would be always to select the most valuable item and place this in the bag。

 giving no thought to what other items， this would exclude from the process。😊。



![](img/2f88322829d79a98deb0e8d2d0f43a4c_7.png)

Thus， in our CPU example， a greedy approach would involve selecting first the shortest running program and then the next shortest program and so on。

While this might not lead to a globally optimized solution。

 it will reduce any overhead in calculating the most efficient subset of items。

To better understand how these two approaches would differ。

 let us consider the problem of the shortest path。The image shows a map with 9 different nodes， A， B。

 C， D， E， F， G， H， and S。 Each node is connected to another node by a weighted path。

This weight reflects the cost that would be incurred by selecting this path。Thus， in our CPU example。

 a greedy approach would involve selecting first the shortest running program and then the next shortest program and so on。

While this might not lead to a globally optimized solution。

 it will reduce any overhead in calculating the most efficient subset of items。

You are now faced with making a journey from E to F and want to plot the most effective route。

A dynamic programming approach would involve creating a table and calculating each potential node from E。

From there， it would introduce the next set of nodes and calculate the accumulated cost。

This approach would undoubtedly arrive at the most efficient solution。



![](img/2f88322829d79a98deb0e8d2d0f43a4c_9.png)

Using memorization after the initial calculations were made。

 they would be saved and subsequent journeys would benefit from a quicker computed time。😊。

This is a bottom up global approach to the problem。

 A greedy approach would differ in its methodology。

 Instead of trying to find an optimal subset of connected routes， it would instead begin at node E。

 and look at each available connection。 Thus， it would have a selection of weights， namely 5，3，2。

4 and 12， which correspond to node C， B， D， G and H。 The lowest value in that array is 2。

 which corresponds to node D， following the greedy principle。

 It would make this selection and progress to the next node。



![](img/2f88322829d79a98deb0e8d2d0f43a4c_11.png)

Assuming that the data structure was a directed graph。

 it would be presented with a further three nodes， A， F and G that have the values of 7。

5 and 6 respectively。Since F is the final location。

 it would select F and arrive at its destination happily。

 having amassed a total penalty of7 for travel time from E to D and then to F that carries a weight of2 plus5。

😊，Visually， you can see that this is the most efficient approach。

 and it was come upon without creating an exhaustive table of combinations and computing or roots。

 However， had the node between G and F had a penalty of 2 than it would have selected a less optimal solution。



![](img/2f88322829d79a98deb0e8d2d0f43a4c_13.png)

This is the trade off when choosing a greedy approach over a dynamic one。

While the overhead for a greedy algorithm is low and coding a solution is quite straightforward。

 it will not always guarantee that the best option is returned。



![](img/2f88322829d79a98deb0e8d2d0f43a4c_15.png)

You now have a greater understanding of the greedy algorithm approach。 In addition。

 you have seen how it compares with a dynamic solution and thus deepened your grasp of the strengths and weaknesses of this alternative approach。

Next time you are plotting a route in Google Maps， consider the selection of routes that are offered and think about how these routes might have been calculated。

😊。