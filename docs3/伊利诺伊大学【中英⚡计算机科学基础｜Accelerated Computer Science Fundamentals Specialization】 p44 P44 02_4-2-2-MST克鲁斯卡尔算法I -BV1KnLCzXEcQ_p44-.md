# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p44 P44 02_4-2-2-MST克鲁斯卡尔算法I -BV1KnLCzXEcQ_p44-

![](img/3d13c12c3ceb76ad6dfa4ec745868b64_0.png)

![](img/3d13c12c3ceb76ad6dfa4ec745868b64_1.png)

Today we're going to dive into one of the two major algorithms to find a minimum spanning tree in the graph。

This is Kscro's algorithm。 Kshcro's algorithm is going to require a couple of different data structures that you're already familiar with。

 So let's set up exactly what we need to have to run Kshco's algorithm and let's do an example run through a pretty simple graph so you can see how it forms a minimum spanning tree。

I've provided a simple graph with a number of edges that connect the different nodes。

 and every single edge now has a weight on it， so that's a cost of traveling over that edge。

If you imagine if you have a road network， that might be the number of miles in every single connection of roads。

Between two different points。 So this entirety of this algorithm is going to depend on knowing the shortest route on the entire map。

 So we're going to maintain a data structure called a Min heap that you learned about earlier in this class。

 And as part of this Minheap algorithm。We're going to have an organized list of all of the shortest edge being on top。

 So the very shortest edge in this graph is AD， and this has an edge weight of 2。

 The next shortest graph is E H EH has also has an edge weight of 2 and you can see going further FG is now the next one has an edge weight of 4。

 so we have a list that can be maintained as a minimum heap that is always going to allow us to return or the minimum edge in the entire graph。

In addition to that， we need to introduce the penult algorithm we talked about in this course。

The idea of disjoint sets。 So in addition to our minimum heap。

 we're also going to have every single vertex as initially its own disjoint set。

Remember that we use an up treee to represent disjoint sets。

 So here I drew every single vertex as zone up treee that we're going to maintain here inside of Kurs scroll's algorithm。

 So to run Cur scroll's algorithm， we're starting out with a min heap of all the edges。

And a disjoint set of all of the elements inside of that set。

So how critical algorithm is going to work is we're going to always remove the minimum element from the heap and then check if that element is if the two vertices that are part of that element are already in the same set。

If they are， we do nothing。 If they're not in the same set， we union those sets together。

So because A and D are right now in disjoint sets， A and D are going to become union together so that we have both a。

And D， in the same disjoint set。Next we look at E and H， are ENH in different sets， they are。

 so we union E and H together。Next， we look at F and G， are F and G in different sets， they are。

 so we union F and G together。A and B are A and B in different sets， yes。

 sewing union A and B together。B and D are B And D in different sets。

They both have a set identity of A。 If we follow the up pointers in the up tree， they both get to A。

 So they're in the exact same set。Because B and D are in the same set。 We do nothing。

 We do not include this edge as part of our minimum spanning tree。

 All of the edges up to now that we use to union things together are part of this minimum spanning tree。

And then GDE。G to E， G and E are different sets。 So we go ahead and union the set that contains G and the set that contains E together。

 So doing that creates these two sets。 So that's part of the minus spanning tree。 G to H。

 G to H are already in the same set。 They're both in the set identity with E。

 We do not add this to the mini spanning tree。E to C， C is now union with this set that contains E。

So this is part of the minpanning tree， and finally C to H。C to H is the E identity is C。

 H identities。E， so these are both in the same set， so we don't add them。

E to F E to F's already in the same set， F to C already in the same set。D to E。Finally， A， B and D。

 our set of those three vertices can finally be unioned with the set that contains C E FG and H。

 so we simply union A with E， and finally we have a minimum spanning tree where all of the nodes that we visited now completely connect with one another and we have a path that goes to every single node because that we have a single set in our disjoint set at the very end we did this through a period of repeated adss to our repeated checks from a minimum heap going down from the least cost edge to the greatest cost edge as we went down this tree。

Let's actually draw this mini spanning tree on the graph to see exactly what it looks like。

So I see A to D was added， so I'm going to go ahead and bold A to D on this graph。

 I then see E to H was added， so I'm going to bold E to H。And then see FG was added， F and G。

Is bolded， I then see A and B was added， so A and B gets added， notice I did not add B and D。

 because had I added B and D， I would have created a cycle and no longer had a tree。

G toE was added in。So G toE gets added in， we see this becomes an even more connected tree。

Skip GH add EC。Adding E to C， we see that this enters out in。

And then the next a to get added is D to E。 So at this point。

 you'll see that there's just two connected regions before we add D to E。

 And we see that there's only。One edge that needs to be added to fully connect this tree to get a spanning tree。

 That edge we added was D to E。 So this D to E edge finally connects our two individual parts。

 And now we have one single spanning tree where from any single node on the spanning tree。

 we can visit every single other node on this graph。



![](img/3d13c12c3ceb76ad6dfa4ec745868b64_3.png)

This is an amazing property， and CRscrorow's algorithm guarantees that not only is this a spanning tree。

 but this is one of the smallest possible spanning trees for this entire graph。

 You cannot create another spanning tree that has a smaller value than this particular spanning tree right here。

And this result is a fantastic result that allows us to know that this is going to be a minimal path we can take in our system to move around as long as we care only about the path that spans every single node。

So the next video， we're going dive into what's the run time to actually run this algorithm and see some code to actually implement Ksco's algorithm。

 I'll see then。

![](img/3d13c12c3ceb76ad6dfa4ec745868b64_5.png)