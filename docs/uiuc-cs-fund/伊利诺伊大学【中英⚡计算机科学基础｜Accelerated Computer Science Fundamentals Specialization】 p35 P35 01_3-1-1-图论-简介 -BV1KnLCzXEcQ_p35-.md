# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p35 P35 01_3-1-1-图论-简介 -BV1KnLCzXEcQ_p35-

![](img/3ee255fa5a4d58305ee5a1be3d807d1b_0.png)

![](img/3ee255fa5a4d58305ee5a1be3d807d1b_1.png)

We're right now at a really exciting point in this semester up until now you've learned a ton of different data structures and a number of different algorithms on those data structures to do amazing problems with binary search trees with AVL trees with arrays and stacks and cues and a number of different algorithms。

Now we're going to arrive to our ultimate data structure。

 This single data structures we're going to be spending the next four weeks talking about。

 We're going to dive into all the different things we can do with this data structure。

But before we dive into it， I want to share with you a few different examples of everything this data structure can do。

In this first example， you see a graph here that's one of my favorite graphs in the world。

 This is a graph of the Internet。😊，As of 2003， so quite an old graph。

 and this graph is going to show us all of different aspects of every single node。

 Every single computer is a single dot。And these computers are clustered together based on their physical location。

 So here these big white clusters are believed to often be universities or large companies。

The color of the edges denote the region and the edges are in green denotes edges in the Americas。

Blue denotes edges in Europe。And red denotes edges in Asia。

All of these different edges tells us the connectivity of the graph。

 and this graph's connectivity is the connectivity of the internet。

 So now the internet's a little bit larger and it'd be very hard to visualize the entire internet on such a simple visualization。

😊，But back almost two decades ago， this visualization was able to capture the full scope of the Internet。

A second graph visualization is a graph visualization that I created with students a few years ago。

 this visualization maps out all of the prerequisite courses at the University of Illinois。

 Let's take a look。This visualization is sometimes called constellation graph。

 because this constellation graph， you'll see that a lot of courses depend upon other courses。

So you can see in this cutout right here。That we have a single course and the size of the circle is the number of courses that is a prerequisite to it。

 so you'll see that this spans out from here having a larger， larger and smaller set of courses。

As we make this great graph constellations。You'll see that at the University of Illinois。

 our STM fields that focus on science， technology， engineering。

 and mathematics are the core cluster right at the center that have a large dependency chain between courses。

Out here we see we have small different constellations that are a sequence of courses that depend upon one another。

But don't largely depend on any other subject group。 Every single subjects colored in its own color。

 So you'll see mostly's constellation are single color。

Being things like Spanish 102 is a prerequisite to Spanish2，02， which is a prere to Spanish 302。

 then you intro Spanish before you can take intermediate Spanish before you can take advanced Spanish。

 The structure of all the courses in that prerequisite make this absolutely beautiful constellation and just another application of how we can use nodes and edges between nodes to actually create something that has a lot of meaning。

😊，One of the most interesting things with graphs is to be able to solve real problems with graphs that affect our everyday life。

So being here at the University of Illinois， one big problem we have is the problem of being able to。

Know when we can schedule final exams so that nobody has a conflict。

So this next graph is a conflict free exam scheduling。 Let me show you how it works。

Every single node in this graph is a course at the University of Illinois。

So here might be the course CS400。Another node right here might be the course Spanish。2，02。

There exists in edge if there is at least one student who's taken both CS400 and Spanish 202。

So in this case， because this graph has an edge there， we know there is a student who's taken both。

 That's awesome。If we look at another course， another course here right now is going to be agricultural sciences。

418。So an agricultural science course doesn't have an edge between CS S 400。

 What that means is this semester， there are no students who are both in agriculturalg Science 418。

 as well as CS S 400。Because there's no overlapping students。 There's no edge。

 which means that can have a con an exam at the exact same time。

 and no students would be in a conflict。The total result of this graph is if we can label every single node with a different color or different shape。

 then we know that the collection of all the different colors in different shapes such that no two colors or shapes are touching each other is a collection of times we need to schedule exams and because no two colors are touching one another we know that everyone in the university can take an exam without having a conflict with another exam and you'll see this graph does exactly this。

 that it creates a conflictfree scheduling， such that none of the two nodes in this graph。

These two triangles that are turquoise。 They have no edge connecting to each other。

So all of these triangle， turquoise triangles all throughout the graph。

A different courses that can take simultaneous exams because this is a subset of courses such that no student is in two of those courses and notice that we labeled this graph with about 12 different shapes and the 12 different shapes that we labeled represents the 12 different times that we need to give exams。

 so there's absolutely no conflicts。

![](img/3ee255fa5a4d58305ee5a1be3d807d1b_3.png)

So this graph is is a classical problem known as the graph coloring problem。

 This are particularly a hard problem and a problem you're going to deal with in a class beyond CS 400。

 but I wanted to show you exactly all of the problems that you can represent and impose onto a graph before we even get started implementing graph because I want to show you why we care about this data structure and why are we're going to spend so much time with this semester。

So you're going to be able to dive into graphs and have a deep understanding of it by the end of this course。

 so let's get started learning about graphs and I'll see you for the first video coming up next。

