# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P56：4 - -61B SP24- Regular Discussion 09 Question 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/0210e27cf66601d4011ea784c7122b39_0.png)

Recoll。Hey guys， So we're gonna go over Q3 for the discussion and worksheet regular edition。

 This is a algorithm design question。 So it's very word heavyav， very concept of a so。

 let's get right into it。 It's asking us your airline company has been contracted to fly a large shipment of honey from Hosville to the 61 Bs in Op City。

 However， the airplane doesn't have enough fuel capacity to fly directly to Opest City。

 So it will stop at at least one of n airports along the way to refuel。 refueling takes an hour。

 And if the airport is one of K less than n airports。

 your airplane will be grounded for 6 hours due to curfews。 refueling is included in the six hours。

 The 6 Us want their honey as soon as possible。 So please design an algorithm to find the route that will allow your airplane to reach Opest City in the least amount of hours。

And we have a couple hints to consider that's going to help us really grasp the algorithm that we're creating。

Think of the N airports as a graph where the paths between them are edges of weight equivalent to the number of hours it takes to fly from airport A to airport B。

 You may assume that the amount of time it takes to fly from A to B is equal to the amount of time it takes to fly from B to A。

 So let's break this down。 First of all， it's telling us that we want to look at this as a graph。

And graphs have two main components， graphs have nodes， and graphs have edges。

So what are each of these going to represent Well， the nodes are going to be each of the N airports。

Along the way。The edges， as it says in the hints， are going to be equivalent to the weight of the number of hours it takes。

 so it's going to be hours it takes from each airport so or I should say from each node connected from the nodes。

Another key component the hint is saying is you may assume the amount of time it takes to fly from a to B is equal to B to a。

 that's basically telling us that this。The route doesn't have a specific direction because you can go from A to B or you can go from B to a。

 So that is telling us this is going to be。An undirected graph。So now that we have our graph。

What kind of algorithm do you think we could run Well。

 because this is asking us to find the algorithm with the least amount of hours from point A to point B。

 we are actually going to be using the。Shortest paths。3ree。Algo。Because what is this going to do。

 it's going to tell us the shortest paths。 A key component to this problem is the fact that we don't have enough fuel。

 We have to make at least one stop to refuel。 The tricky part about this is some of these airports。

 these K airports will have。Ourre plane grounded for six additional hours because of the curfew。

 So we actually have to。Adjust the graphs。To represent K。

So the big question is how do we do this There's actually a bunch of different ways to do it I'm going to be going over like three of them。

 but there are multiple solutions to this issue。The first way。

First possible way to address to actually show K airports with those six extra hours is weekend。

Increase。The edge weights。Of the。Or we can increase the edge rates。

I don't know how to spell associating how to spell， I ifs an S。Associating。With the。

Reuel and grounding times。We could basically think about because this is an undirected graph。😊。

We could basically think about this as two different directed graphs。

And increase the edge based off the node that it's pointing to that has that additional six hours。So。

Directed is too undirected， note it points to adjust it to show what K is。

The second potential solution is we could。Add the weights。Of the nodes themselves。

So this kind of creates two things to consider as re traversing。

 we have to consider the edge weight and the node weight So if we're considering both of these things。

 this kind of looks similar。😊，To the A star algorithm that we've learned。

The third way we could incorporate the K representation is we could split the nodes。Where。

We have two notess connected。And these two nodes connected havet。Edge weight。 Well， I can't。pe。

 we're ready。They have an edge weight equal to。The refuel。In grounding time。So like I said。

 these are just a couple solutions to represent K， the main idea is we want to adjust the graph。

Because we want to find the shortest path， some of these airports are going to have an additional six hours and we want to represent them in the graphs when we traverse it。

 we minimize the stops and the hours allotted to actually get to our destination so because we have our graph or sorry our graph set up。

 we can actually run our algorithm like Dgtras where we start at the node corresponding Tosville and we won't stop the algorithm until we get to node corresponding to Op City and until it is popped off the fringe the reason we wait for it to pop off the fringe is because the distance to value of Op City will be the minimum time or the shortest distance。

Once we get there， we could backtrack from Oppe City to Honeysville and that will give us the shortest path。

So this is kind of how you approach an algorithm design question you consider all possible components。

 you create the graphs with the nodes and edges and you adjust it based off whatever other given things that might be a little tricky or。

That might affect the shortest path possible。

![](img/0210e27cf66601d4011ea784c7122b39_2.png)