# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P51：3 - Spring 2023 Exam-Level 09 Problem 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/64eb078c413bec5951c349af00a740de_0.png)

For everyone， this is Sherry and I'm going over question3 on the CS61b fall 2022 exam prep 9 Graph conceptuals。

Like problem one on the worksheet， this problem is mostly conceptual testing you on the properties of graphs。

 so let's jump in。Part A is all true of false questions， and let's start with one。

 if a graph with n vertices has n minus1 edges， it must be a tree。

If we look at this graph that I've drawn here， we can see that this is false we have a graph right here which has a cycle and a disconnected node。

A tree has to be connected and can also never have cycles， so this violates both conditions。

 but if we count the number of vertices we see there four and there are three edges。

 so this is clearly false because we just found a counterex to it。For part two。

 it asks if every edge looks at each， if every edge is looked at exactly twice when we do DFS on a connected undirect graph。

If we recall the DFS algorithm， it looks something like this where we look at a node and its neighbors and we recursively call DFS on each of its neighbors so this question is actually true because we will look at an edge UV once when we call DFS on U and once when we call DFS on V。

For part 3， remember that BFS。Operates on a queue of nodes and distances。

 This question is asking if we can ever have a queue that looks something like this where we have something that's distanced to a par or more。

So for example， if you have a， which is distance two from the start and D。

 which is distance four from the start。Again， the answer to this is actually false。

And the reason for this is because we can't ever have a note。

 we can't ever have a queue that looks like this。If we have D4 on the Q。

 that means we deed some node that was distance 3。But remember also that the BFSQ is always ordered by distance and we always deque from the start。

So we could never deque a note of distance3 if there's still a note of distance 2 that would just completely violate the rules of BFS。

 since BFS always proceeds in order of distance from the start。

Part B is an algorithm design question which asks us that define an algorithm that finds a cycle in a graph。

 This is a pretty common algorithm design question and the answer here is that we just do DFS。

Until we see all node。Or a repeated node。So basically we do DFS。

 we keep track of what nodes that we have already visited and if we ever hit a node that we have already visited。

 then we have a cycle。For an illustration of how this would work。

 let's consider to these two graphs here where there's a cycle in the left graph。

 but no cycle in the right graph。Let's say we arbitrarily start DFSAA。Then we'll call DFS on B。

 then we'll call DFS on C， then we'll call DFS on D， and since D has an edge back to A。

 we actually end up calling DFS on A again and we notice that we've already visited A so that means there is a cycle。

If we look at a graph without a cycle and run our algorithm， we're going to start at A again。

 and then we're going to call DFSC and then we're going to call DFS on B and D。

 and at this point weve visited every node in the graph， but we haven't revisited any nodes。

 so this has no cycle。And the runtime of this algorithm is theta of V because in the worst case。

 where in there's no cycles， we just have to visit every single vertex to declare that there actually is no cycle。

That's it for this problem and here's my weekly exam tip for graph questions。

 the best strategy is always to draw examples as I've done here Obviously a single example doesn't prove a property。

 but you can try and think of counter examplesamples or testered algorithm on a small graph。



![](img/64eb078c413bec5951c349af00a740de_2.png)

Good luck on the midterm and in the rest of 61 B。