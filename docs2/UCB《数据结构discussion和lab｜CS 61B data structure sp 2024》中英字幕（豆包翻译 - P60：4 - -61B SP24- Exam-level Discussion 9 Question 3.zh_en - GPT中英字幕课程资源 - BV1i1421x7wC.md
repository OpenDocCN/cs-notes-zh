# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P60：4 - -61B SP24- Exam-level Discussion 9 Question 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

Hey guys， so we're going to go over Q3 on discussion9 exam level worksheet。

 this is an algorithm design problem， so it's very word heavy。

 we're going to break down every part of the problem and break down the concepts that are trying to teach us and hopefully by the end of this you'll know how to design an algorithm。

So let's get right into it。😊，Two countries， Mostad and Fontaine are located in the fictional world of Tva。

 The railroad system of Tva can be modeled as a weighted directed graph with V vertices。

 E edges and weights being the length of the railway。

 Circle the traveller wishes to take railway from Mostt to Fontaine and needs to determine the shortest railway before。

Distance between them。 Def the set M to be all cities in Modstt and F to be all cities in Fontaine。

 The shortest distance between the two countries is the shortest distance between any city C M in Modstat and C of F in Fontaine for each sub part below。

 describe an algorithm that computes the minimum railway distance from Modstat to Fontaine in O V plus E log of V  T。

You are able to call all graph algorithms you learned in class as a black box hint for some parts。

 consider modifying the graph so that running a graph algorithm yields an equivalent answer to solving the original problem。

So let's break down what the problem is giving us。 So first of all。

 we have a weighted directed graph， so all edges are going to have a specific weight and these weights are going to be the length of the railway system。

 We also have V vertices E edges。And we want to find the shortest distance。From modtat to Ftaine。

 and we want to make sure it equals to that runtime。

So let's get right into it the first problem is saying Mostad only contains one city and Ftaine contains many cities。

 so when it comes to problems like these I always like to draw a graph to visualize it so let's do that so we have one city in Mostad。

And we have multiple。Seize。In Fine， right。And these are connected in some way。

And they have X amounts of weights。 you don't really need to know like exactly the weights。

 it's just more like conceptually。So looking at this because we want to find the shortest distance from Modstadt to any city in Ftaine。

We can just run， Texas us。The trick about this is we start。At M。And we iterate。

Through all cities in Fontaine。And in doing so， this is going to give us the minimum difference distance from that one city in Moster to any of these one cities in Funtain。

The next problem is asking where we have Monad contains many cities， but Fine only contains one city。

 So this is basically flipped from the original one。 so we have。Many cities in WaApp。And we have。

One city in Fontaine， and these are connected。Let's say like that。

The trick of this is because we want to find the distance from M to F。

 we can't start at that one city in Fontaine and iterate through everything in Motadt like we did for part8。

We also don't have a starting vertex like we did in the previous one because Monst was only one city because technically any of these cities could be the starting point to the fastest route。

So this is where the hint comes in that they gave us in the。

QuestionSo it's saying consider modifying the graph where when we run the algorithm。

 it gives us an equivalent answer。So if we want an equivalent answer， we want to modify the graph。

The best way to do this is to create something that we call a dummy node。

So let's say we have this dummy node。And because we want to start at ModSt。

 we are going to connect this dummy node to all potential vertices in MoSt。

The way we make this equivalent to solving the original problem。

 because technically we're creating like a new graph because we're adding this dummy node。

 we're going to set the weight of all these edges to zero what this basically does starting with the dummy node。

 it's going to iterate to it's going toerate through all cities in M and with that weight zero it's basically creating a new graph G prime。

So we could basically run ditras。😮，Starting from the dummy burtex D。

And take the distance from D to the only city in F and return it。 So it could iterate like this。

And then it's in an it like that， or it could start from here。

 or it could start like that or it could start like that。 So it's basically。Going to。

The way this works is because for each path in the original graph from any city in M to F。

 it corresponds to a path in the new graph of this like G prime that starts from D and ends in that singular city in Ftaine。

 And because the original weight we set to all these edges are 0， it doesn't add any。Like。

It doesn't add any edge to that railway from one city to the other。So therefore。

 our algorithm can correctly compute the shortest path from any city。

 any starting point city in M to that singular city in Fine。Lastly。

 it's saying both countries contain many cities， so once again we are going to draw this out。

So we have。All these in M。And now we have， let's just put2 and F。And these are all connected。

In some way， shape or form。Once again， we don't really have a starting vertex in M。

 so we're going to do the same process we did in part B， where we create a dummy node。That's gonna。高。

To index all the vertices in M， we're going to set all these edges to0。

The only difference this has from the previous part is we're not ending that at one singular city in F。

 we're also adding another city in F or adding multiple more cities in F。So。

This creates a dummy vertex D for each city in Most。

 We create an edge from D to that city with edge weight 0。

 This once again creates that new like G prime graph that we talked about， and we can once again run。

The extras。Starting from dummy vertex tea。Now， instead of directly taking the graph from D to the only city in F。

 we take the minimum difference from D to all cities of E and we return it。



![](img/f7115efe071f2d86a0a2303b72d7782c_1.png)

I hope that makes sense， I hope these visualizations helped。

 and I hope this helps you understand the algorithm design aspect。



![](img/f7115efe071f2d86a0a2303b72d7782c_3.png)