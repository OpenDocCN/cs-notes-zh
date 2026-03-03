# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P76：01_01_04_应用-互联网路由.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

The design and analysis of algorithms is the interplay between on the one hand general principles and on the other hand。

 instantiations of those principles to solve specific problems。

 While there's no silver bullet and algorithm design。

 no one technique which solves every computational problem that's ever going to come up。

 There are general design principles， which have proven useful over and over again over the decades for solving problems that arise in different application domains。

 Those， of course， are the principles that we focus on in this class。 For example， in part1。

 we study the divide and conquer algorithm design paradigm and principles of graph search amongst others。

 On the other hand， we study specific instantiations of these techniques。 So in part1。

 we study divide and conquer and how it applies to say Stras ands matrix multiplication merge short and quick sort。

 In graph search， we culminated with the rightfully famous diyxrous algorithm for computing shortest paths。

 This， of course， is useful， not just because as any card carryinging computer scientist or programmer。

 You want to know about what these algorithms are and what。They do， but it also gives us a toolbox。

 a suite of four freeee primitives， which we can apply to our own computational problems as a building block in some larger program。

 Part two of the course will continue this narrative we' learn very general algorithm design paradigms like greedy algorithms。

 dynamic programming algorithms and many applications。

 including a number of algorithms for the greatest hits compilation。 and in this video and the next。

 I want to wech your appetite for what's to come by plucking out two of the applications that we'll study in detail later in the course。

 specifically in the dynamic programming section of the course。 First of all。

 for both of these problems I think their importance is self-edent。

 I don't think I'll have to really discuss why these are interesting problems。 Why in some sense。

 we really need to solve these two problems。 Secondly， these are quite tricky computational problems。

 and I would expect that most of you do not currently know good algorithms for these problems and it would be challenging to design one。

 Third， by the end of this class， you will know efficient algorithms for both of these problems。

 In fact， you'll know something much better。 you'll know general algorithm design techniques which。



![](img/bf95f41aa67e22632457dec5ea0d4aa1_1.png)

is a special case to these two problems and have the potential to solve problems coming up in your own projects as well And one comment before we get started on these two videos。

 they're both at a higher level than most of the class by which I mean there won't be any equations or math。

 there won't be any concrete pseudocode and I'll be glossing over lots of the details The point is just to convey the spirit of what we're going to be studying and to illustrate the range of applications of the techniques that we're going to learn。

So what I want to talk about first is distributed shortest path routing and why it's fundamental to how the internet works。

So let me begin with a kind of very non mathematical claim。

 I claim that we can usefully think of the internet as a graph as a collection of vertices and a collection of edges。

So this is clearly an ambiguous statement， there's many things I might mean as we'll discuss。

 but here's the primary interpretation I want you to have for this particular video。

So to specify this， the vertices I intend to be the end hosts and the routers of the internet。

 so machines that generate traffic， machines that consume traffic and machines that help traffic get from one place to another。

So the edges are going to be directed and they're meant to represent physical or wireless connections。

 indicating that one machine can talk directly to another one via either a physical link between the two or a direct wireless connection。

So it's common that you'll have edges in both directions so that if machine A can talk to machine B directly。

 then also machine B can talk directly to machine A。

 but you definitely want to allow the possibility of asymmetric communication。So for example。

 imagine I send an email from my Stanford account to one of my old mentors at Cornell where I did my graduate studies。

 so this piece of data， this email has to somehow migrate from my machine local at Stanford to my mentors machine over at Cornell。

 so how does that actually happen？Well， initially there's a phase of sort of local transportation。

 so this piece of data has to get from my local machine to a place within the Stanford network that can talk to the rest of the world。

 just like if I was trying to travel to Cornell， I would have to first use local transportation to get to San Francisco Air and only from there could I take an airplane。

So this machine from which data can escape from the Stanford network to the outside world is called the Gateway router。

The Stanford Gateway router passes it on to a network whose job is to cross the country。

 so last I checked the commercial Internet service provider Stanford was Cogent。

 so they of course have their own gateway router which can talk to the Stanford one and vice versa。

And of course， these two nodes and the edges between them are just this tiny， tiny。

 tiny piece embedded in this massive graph comprising all the end hosts and routers of the internet。

 so that's the main version of a graph that we're going to talk about in this video。

 but let me just pause to mention a couple of other graphs that are related to the internet and quite interesting in their own right。



![](img/bf95f41aa67e22632457dec5ea0d4aa1_3.png)

So one graph that has generated an enormous amount of interest and study is the graph induced by the web。

 so here the vernatices are going to represent web pages and the edges which are certainly directed represent hyperlinks that one web page points to another one。

So for example， my homepage is one node in this massive， massive graph。And as you might expect。

 there is a link from my homepage to the course page for this class。

It is of course essential to use directed edges to faithfully model the web， there is， for example。

 no directed edge from this course's homepage to my own homepage at Stanford。

So the web really exploded around you mid-90s， late 90s so for the past 15 plus years there's been lots of research about the web graph I'm sure you won't be surprised to hear that you know around the middle of the last decade people got extremely excited about properties of social networks those of course can also be fruitfully thought of as graphs here the vertices are going to be people and the links are going to denote relationships so for example。

 friend relationships in Facebook or the following relationship on Twitter。

So notice that different social networks may correspond to undirected or directed graphs， Facebook。

 for example， corresponding to an undirected graph， Twitter corresponding to a directed graph。

So let's now return to the first interpretation I wanted to focus on that where the vertices are inhosts and routers and it just represent direct physical or wireless connections indicating the two machines can talk directly to each other。

 So going back to that graph， let's go back to the story where I'm sending an email to somebody at Cornell and this data has to somehow travel from my local machine to some local machine at Cornell。

So in particular， this piece of data has to get from the Stanford Gateway router。

 in effect of the airport for Stanford's network to the Cornell Gateway router。

 so the landing airport over on Cornell side。Now it's not easy to figure out exactly what the structure of the routes between Stanford and Cornell look like。

 but the one thing I can promise you is that there is not a direct physical link between the Stanford Gateway router and the Cornell Gateway router。

 any route between the two is going to comprise multiple hops it will have intermediate stops。



![](img/bf95f41aa67e22632457dec5ea0d4aa1_5.png)

And there's not going to be a unique such route， so if you have the choice between taking one route which stops in Houston and then Atlanta and then in Washington。

 DC， how would you compare that to one which stops in Salt Lake City and Chicago？Well。

 hopefully your first instinct and a perfectly good idea is all else being equal。

 prefer the path that is in some sense the shortest。

Now in this context shortest could mean many things and it's interesting to think about different definitions。

 but for simplicity let's just focus on the fewest number of hops。

 equivalently the fewest number of intermediate stops。Well， if we want to actually execute this idea。

 we clearly need an algorithm that given to a source and a destination computes the shortest path between the two。

So hopefully you feel well equipped to discuss this problem because one of the highlights of part one of this class was the discussion of Dyketra's shortest path algorithm and a blazingly fast implementation using heaps that runs in almost linear time。



![](img/bf95f41aa67e22632457dec5ea0d4aa1_7.png)

We did mention one caveat when we discuss Dykester's algorithm namely that it requires all edge links to be not negative。

 but in the context of internet routing， almost any edge metric you'd imagine using will satisfy this non-negativity assumption。

There is however a serious issue with trying to apply Dykestra's shortest path algorithm off the shelf to solve this distributed internet routing problem and the issue was caused by the just massive distributed scale of the modernday internet。

 probably back in the 1960s when you had the 12note aRPpant you could get away with running Dykestra's shortest path algorithm but not in the 21st century。

 it's not feasible for the Stanford Gateway router to maintain locally reasonably accurate model of the entire internet graph。

So how can we alllude this issue， is it fundamental that because the internet is so massive。

 it's impossible to run any shortest path algorithm。

 well the ray of hope would be if we could have a shortest path algorithm that admitted a distributed implementation whereby a node could just interact perhaps iteratively with its neighbors with the machines to which it's directly connected and yet somehow converge to having accurate shortest paths to all of the destinations？

So perhaps the first thing you try would be to seek out an implementation of diytras algorithm where each vertex uses only local computation that seems hard to do if you look at the pseudocode of diketch just doesn't seem like a localizable algorithm。

 so instead what we're going do is we're going to learn a different shortest path algorithm it's also a classic definitely on the greatest hits compilation。

 it's called the Belman Ford algorithm。So the Belman Ford algorithm as you'll see。

 can be thought of as a dynamic programming algorithm and indeed it correctly computes shortest path using only local computation。

 each vertex only communicates in rounds with the other vertices to which it's directly connected as a bonus will see this algorithm also handles negative edge length。

 which of course Dter's algorithm does not but don't think Dx's algorithm is obsolete。

 it still has faster running time in situations where you can get away with centralized computation。

Now what's really kind of amazing here is that the Belman Ford algorithm， it dates back to the 1950s。

 so that's not just pre- internet， that's prearpannet。

 that's before the internet was even a glimmer in anybody's eye。

 and yet it really is the foundation for modern internet routing protocols needless to say there's a lot of really hard engineering work and further ideas required to translate the concepts from Belman Ford to actually doing routing in the very complex modernday internet。

 but yet those protocols at their foundation go all the way back to the Belman Ford algorithm。

