# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P152：16_图形.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

When considering a given problem in computer science。

 it is always important to consider what executions might be required to solve your problem。

 and through this reflection， choose an appropriate data structure to hold your data。

Consider that you might work for a large Internet company that wants to store a directory of locations and their connectedness to one another。

In this illustration， our cities plotted in relation to one another。

Notice how every possible detail need not be recorded。 Sa， for instance。

 you want to know how far Chicago is from Boston。 You can easily deduce this from the way in which the data is organized。

 This same approach could be used to model Internet destinations。

 relationships between words or people on a social network。



![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_1.png)

This approach to saving information is a graph based approach In the coming video。

 some terminology and advantages to this approach will be outlined。



![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_3.png)

This structure illustration is a graph that is made up of nodes to denote destinations and edges that show how each node relates to another。

 The presence of values between the nodes means that this is a weighted graph。

 There are no arrows present， which means that this is an undirected graph。

In contrast to a directed graph， an undirected graph has no order of precedence。

One way to think about directed and undirected graphs is like two way and one way streets。



![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_5.png)

Sometimes it helps when ordering data to highlight some progression when in other instances。

 the edges are there just to show association。😊，A path then is a sequence of two or more nodes that is connected by an edge。

A connection in a directed graph is considered weakly connected if the edge is only one way。However。

 if there are two connections going either way between two nodes。

 then it is said to be strongly connected。 At this point。

 you may be considering that a graph resembles a tree。 In some ways。

 you can say a tree is a simple graph。 Notably， a tree has a starting point and models a hierarchy with parents and children。

 A graph is a far more complex structure that has no beginning or end。

 Two nodes bordering one anotherccor neighbors and nodes that are connected through a neighbour as said to be adjacent。



![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_7.png)

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_8.png)

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_9.png)

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_10.png)

Grass like trees can be traversed breadth first and depth first。

 recall a breathth first search involves visiting every node on the same level， then going lower。

 and a depth first search involves drilling into the end of every branch before moving on to the next one。

😊，A breathth first approach involves choosing a given starting location and iterating over all the neighbouring nodes。



![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_12.png)

Each neighbor will have a connection of connected nodes。

 which can be added to another data structure already mentioned the queue。



![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_14.png)

In this way， you can systematically visit every node to achieve a depth first search。

 you can employ a stack， recall a stack process elements differently than a queue。😊。

While the queue prioritizes first in first out， a stack focuses on last in， last out。

 So by placing all of the neighbor nodes systematically on a stack。

 you would ensure a depth first traversal。

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_16.png)

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_17.png)

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_18.png)

Graphs are a much studied data structure and are the basis of many algorithms that have been developed to establish importance between nodes。

Regardless of the element stored in the node， one notable one is shortest path。

 What is the quickest way to get from node A to node E。

The edge weight would inform as to the cost of choosing each path。

This approach is used when routing internet packages on the Internet or when calculating a journey on Google Maps。

 Another common graph based challenge is a travelling salesman。



![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_20.png)

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_21.png)

A salesman has a select few nodes to visit。 What is the best route to plot that hits all the nodes in the shortest time。

 This would be used in package routing。

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_23.png)

Given X destinations and Y vehicles， plot out the most efficient route so that all packages get delivered with the least spending of resources。

 In this video， you learned how graphs give you the opportunity to model data in a flexible way that facilitates inferring information on the data by how it is stored。

😊。

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_25.png)

![](img/a9a3b0600f70f09aaa79e50a6c2e53ca_26.png)

This versatile approach only retains the minimum of information。

 The distance from Chicago to Boston is not stored anywhere， but can be deduced。

 It's easy to query different questions without changing the makeup of the data Calalculating the best time when walking can easily be substituted in place of driving with minimal fuss。

There has been a whole field of statistics devoted to inferring information from node placements。

 which can be levered to make inference on any data stored there。😊。

