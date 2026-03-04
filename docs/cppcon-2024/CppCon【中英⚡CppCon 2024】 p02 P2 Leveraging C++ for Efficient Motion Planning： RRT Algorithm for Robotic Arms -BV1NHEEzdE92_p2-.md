# CppCon【中英⚡CppCon 2024】 p02 P2 Leveraging C++ for Efficient Motion Planning： RRT Algorithm for Robotic Arms -BV1NHEEzdE92_p2-

This one in particular， it's at a beautiful venue， pretty much everybody staying in the hotel here。

And so that means you know， after the sessions， people are going out and getting a beer。

And continuing the conversation。It's just a great way to experience。



![](img/8524a1e17afd4a549946f63c15cdc9bc_1.png)

![](img/8524a1e17afd4a549946f63c15cdc9bc_2.png)

Hi everyone。 My name is Addihi。 I'm here to present leveraging C++ for efficient motion planning using the RRT algorithm。

 So as a junior engineer， this is my journey of using C plus+ for my robotics code earlier I used to write in other languages who which weren't as robust but now I am trying to shift solely to C++ so let's go with the outline first is why we need C plus+ for robots or why it's useful then the need for motion planning motion planning basics。

 the RRT algorithm， my C plus plus implementation the output and my key learnings。



![](img/8524a1e17afd4a549946f63c15cdc9bc_4.png)

![](img/8524a1e17afd4a549946f63c15cdc9bc_5.png)

So lets start with y C++ for robotics as you all know C++ is a very fast language because it compiles and builds a machine code it gives us more control over the hardware which we always want。

 it is more efficient and it can be run on different different devices， it is very portable。😊。

Let's look at this Fun example。You know what would prevent this if we did motion planning？

So lets start with some basics What is motion planning Mo planning is the process of using computational methods to calculate a collision free path from one one location to another location and the algorithm that we use to calculate this path is called a planner。



![](img/8524a1e17afd4a549946f63c15cdc9bc_7.png)

![](img/8524a1e17afd4a549946f63c15cdc9bc_8.png)

是。So there are different types of planners available。 There are graph graph based planners。

 there are sampling based planners， and there are optimization based planners。



![](img/8524a1e17afd4a549946f63c15cdc9bc_10.png)

RRT， the one we are considering today is a is a sampling based planner。 So how it works。

It is used to efficiently search。By randomly building。A space tree。

 So I'll give you the basic overview of the algorithm。

It starts with the start toward and the idea is to reach the goal node。

 but not by a fixed known path， what it does is it tries to sample random path random points in the space。

And it tries to build a tree with all the nodes that would lead to the goal destination。

 And if any tree path ends up in an obstacle， then it just discards it Later。

 it backtracks and gets the most gets the one path that connects the whole thing。Okay。

 so let us let us dive into some motion planning basics for robot arms， particularly。

So the configuration space is the space is the set of all configurations that the robot can attain out of these we want to so when we do motion planning considering a higher three dimensional robot what we want to do is always reduce a dimensionality and get it to an easy problem for us to write code for。

😊，So what we do is we， we。Get this dimensionality down by defining a configuration space obstacles。

 So these are the set of all configurations that the robot。😊。

Cannot attain because it would be in collision with an obstacle。 So if there was a。

 there was an obstacle here and my robot tried to hit this， this would be an obstacle。

 but this whole area would be a configuration space obstacle。 And， of course。

 free space is the space that is left over and that it can attain。😡。

So we convert from a real life problem to a configuration space problem。

 which has configuration space obstacles。 Now our planning problem has been reduced to just finding a path between point A and point B for a single point。

Let's dive into the code。So this is the configuration space example that I'm working with。

 and there would be a start and。😊，Goal node generated in the code。

I am using open CV to show the input to take the input images and to do the output the open CV would take the input images。

 generate a map array that would be passed to the algorithm and then each step of the algorithm will be carried out which Ill explain as I go。



![](img/8524a1e17afd4a549946f63c15cdc9bc_12.png)

Okay， let's start with the basic data structures used。

 so RRT is basically a tree implementation wherein each node has only each parent of the tree has only one child and that child has also only one child and it's not like a binary tree or like it cannot go more in more than one directions so I use a class node to store my node object for each node in the tree it contains x Y which other coordinates and the parent and a point to the parent。

Parent node。Then I use a vector of node pointers that can be used to store all the addresses of all the nodes in the tree。

So in one big learning here was like using classes and object oriented programming like we all know what is object oriented programming but the key is when to actually use a class and when to actually use private data members when you need to protect them and when you need to restrict the access to them so in this case I am using my vector vector of vertics as a private member and I' am restricting access to it and I' am using all the member functions of the class。

😊，Do。To only those of that can access the object。I have used pointers to pass around the notes between functions to be more efficient with the memory。

Let's take a deep dive in each of the functions。 And then like how we build a code is by bottom up approach so I'll explain to you each function individually and then we will build it up okay so the check col function checks for a collision between two points passed to it these two points are passed as two nodes first it checks the destination node So the back that we got from the map that we got from open C。

 that's basically a binary map it would it has it is consists of just zeros and ones wherever there is obstacle there's a one wherever there is no obstacle。

 it's free。 it's zero。 So first it checks for the destination if that destination is on an obstacle then it checks for each point each point between that node and the destination So how I'm doing this is by using linear interpolation So I do linear interpolation between those two points and I get like。

Hundre0 points in the middle of them。 And I check for each point。 If either of the point is in col。

 then。That means that path is not to be chosen。Next， we come to the random point generation function。

 So the random point generation function， as it says， it generates a random point。

In the freeze in the space of that matrix。 And there is this thing called goal bias。

 So what is a goal bias。😊，As I said previously， if the tree is built randomly and there is like a huge image but you have to go in a particular directions。

 it would take you like forever to reach them maybe so what we do is we include a goal bias which means that if your goal bias is like say 10% like 0。

1 that means that 10% of the times it will choose the end goal node only as the destination node so that it tries to go in that direction。

😊，And other times， it will find a random node and choose that。 Next comes the nearest node function。

 So once we found the near we have found a random node， and we have selected that。Now we。

 we need to find the where to correct it to or3， right， So what we do is we take each node inside。

 we just take。We take our new node and we take our tree and we trade over all of the points in the tree and try to find which has the least distance towards least distance between。

The new node and that node， and that is the nearest node， and we return that value。

Now comes now we come to the implementation of R。So as I explained to you， this。

Algorithm starts with it generates a random point。😊。

Checks for collusion finds the nearest point in the tree that can join with that point。

 then connects it。But it connects it only so R T implements like extends only by a fixed distance。

 So it all always connects the point。 But if it say like 15 units away from our nearest node like R3 and we need to connect and our。

😊，Step distance is fine nodes。 Then it will plot another point on that。



![](img/8524a1e17afd4a549946f63c15cdc9bc_14.png)