# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p03 P3 03_1-3-运行时分析 -BV1KnLCzXEcQ_p3-

![](img/170743ed724d9a24bfe0dcf098ffb8b5_0.png)

![](img/170743ed724d9a24bfe0dcf098ffb8b5_1.png)

Runtime analysis allows us to formalize a method of comparing the speed of an algorithm as the size of the input to the algorithm grows。

 We're going to contrast two different data structures right now。 We're going to contrast an array。

 a sequential chunk of data and memory， and a list。

 which is data linked together through list link through list nodes。Remembering back to our array。

 we can access a given indexing array by knowing the size or the width of each piece of data and then multiplying the width of each piece of data by the index that we want to access。

So it doesn't matter what our index is。 Our index may be 1 million。

But since we're only doing the multiplication， we can do this multiplication extremely quickly。

 It takes exactly one multiplication， no matter how much data is in our array。 If it's one element。

 a million elements or 10 million elements。In a linked list， if we want to access a given index。

 so if we want to access index 99， we have to travel through the list 99 times by following next pointers。

So as the size of our data grows， the amount of time it takes to access an average element is going to grow as well。

Let's look at a table。 We want to access a given element， and we want to access element 3。

 in an array， we can calculate that by simply saying three times whatever the size of our data is。

And that's going to take one operation。It's going to take one multiplication。In a linked list。

 we've got to advance three different link nodes。 So that's going to take three operations to find where our data is at。

If we're going to access the 4285th element， well， within Ray， we do 4285 times the size。 So this。

 again， is one operation。In a linked list， we have to advance。4285 next pointers。

 So we say that's 4285 operations。If we want to access the0， the 1250th00th element， again，1。

2 million times the size of is still only one operation for doing this on our linked list。

 We're going to be following next point for a really long time。 This is going to be 1250 or 125000。

Operations。Now， let's think about this in terms of n。 If we want to access the inth element。

Then it still takes in times。Whatever the size of the data is。 So that is still one operation。

In a linked list， that is in operations。So we say that no matter how many elements in the array。

We're always going to be able to access the int element in what we're going to call big O of one time。

On the other side， in a linked list。We're going to take in operation。

 So we're going to call this big O of in time。 and big O is just a syntax that lets us know that this is how the function grows in time complexity relative to the input。

Let's think about a resizing of an array。 So if we want to resize an array。

 one strategy we can do is that every time we need to resize the array。

 we're going to resize the array enough to put in the next element and store one more element after that。

 so that we don't have to do this work all of the time。 So here we have an array of 6。

 We need to resize it to 8。 So I'm going to go and copy over this data 2，3，5，7，1113。

 I'm going to enter my next prime number 17。 And I've left this open space here so that don't have to do this process right away again。

 I've got room for the next piece of data that's coming in。

 So I ultimately had to make six copies of our data to our new array。

 And then I have room for two more pieces of data， one that I use right away。

So this strategy is that whenever their array is full， we want to add two mores to the capacity。

 So I'm going to formalize what this takes as our capacity grows to n。 Initially。

 our array is going to start out with a capacity of just two。

And this is going to happen in the very first round。And then after the first round。

 we're going to have to make two copies。Of our data， when we resize this array to be4。

And then we're going to have to make four copies。When we size this data to be 6。

 we're going to make six copies，8 copies，10 copies， and so forth。

So you'll see that we denote the number of copies we have to make at each level until the last level when r is equal to n over 2。

 so we know that this is going to be in pieces of data and we know it's going to take we're going to have a round of resizing every other piece of data。

😡，So in over two pieces of data， which we're going to call R。Is going to require2 R -1 copies。

Let's go ahead and actually add up the total number of copies that it takes over the entirety of the algorithm expanding from an initial array of capacity2 all the way down to when the array is the capacity of two times R。

So here we have two copies， four copies，6 copies，8 copies。

 10 copies all the way up to2 the R minus1 copies where r is equal to in divided by 2。

 because you remember we're resizing every other time， so in dividedid by two times。

And what we want to do is， we want to。Change this into a syntax that we can easily add together because 2 plus 4 plus 6 plus 8。

Is kind of roughth。 Instead， in terms of number ress， this is going to be。Two times 1， two times 2。

 two times 3。 and so forth。 So here we have two times 1 plus two times 2 plus  two times 3 plus  two times 4 plus  two times 5。

 So the total amount of copies made is going to the sum。Of two times k。When K is equal to 1。

All the way up to when K becomes R from K equals 1 to R， we're going to have two times k。

 So this is a total copies。Working out this math a little bit。

 two times ks you might remember from an introductory calculus class。

 it's going to be two times R times Rs of plus1 over2。

If we go ahead and cancel out the twos and distribute the R's， we have R squared plus R。

 So we know that some of all of the required copies is going to be R squared plus R copies。

 So we know two things。 We know that the total number of copies is R squared plus R。

 We did this by a sumnation。 And we know that the relationship between R and N is R is equal to in dividediv by 2。

So we can go ahead and substitute R back end for N。

 because we really want to know how much this grows in terms of the number of data or N。

 we don't really care about how big R is。 R doesn't mean anything to our final analysis。

So we're going to go ahead and substitute n for R and we get over2 squareds plus n over 2。

 and the final equation we get is n squared plus 2 in divided by 4。In big Onotation。

 what we want to do is we want to actually just express the largest term without any of the constants。

 The largest term in this equation is in squared。So in squared is larger than 2 in。

 It's larger than the constant 4 will drop everything that's not the largest term。

 and big O notation is always going to note the largest term in an equation。

So here we have that the total amount of time for all of the copies is going to be in squared total time。

So let's see how this differs。If we use a different strategy， our other strategy is。

 let's double the capacity every single time， as opposed to just adding two each time。

So if we double the capacity， starting with array of size 2 again， the first time we do two copies。

 the second time we do four copies。The next time we do eight copies。And so forth。

 until we do 16 copies， and eventually， we do2 to R copies where R is going to be a logarithm of the total number of elements。

So， again， doing the sumation of all of these things。

 We have a sum from k equals 1 to R of2 the k power。

 because this is to the K to the K to the cubed to fourth to the R。

And we know that this is equal to2 times 2 the r minus-1。Just like before， we have two equations。

 We have the no number of total copies， which is two times2 the R -1。

And the relationship between R and N。 And now R is equal to a logarithm of n。

Doing the same substitutions， we see that if we substitute log n for R。

 we get two time2 to the log n power-1 times 2， because2 to the log in。

Of n is just equal to in itself。 We're going to substitute this value for n。

So we have the equation two times n -1 here， looking at the dominant factor。

 We have essentially2 in -2 dominantant factor is 2 in dropping the constant。

 The only thing that grows is in。 So we say the total run time of all of the operations needed。

If we're doubling the size the array is big O of n。 this is much less than n squared。

So what we see is if we analyze the run time， we can see that the strategy actually makes a big difference。

Instead of taking in squared time to all of the copies， we take just in time。 This is awesome。

 So here is an example of where the strategy we use to resize an array makes a difference。

 So strategy number one， growing by plus 2 each time is going to take in squared work。😊。

Strategy number two， doubling each time takes O of in total work。

Now notice we talked about total work at each point。

 What we really want to care about is how much work is done every time I insert。

 If the total work to insert in elements is O of n。

 and I'm doing in different inserts to do all of that work。

 Then the total work O of n divided by a number of inserts I do。 is going to be equal to O of one。

And we call this amortized running time， because if we look at this diagram。

 we see that most of the time looking here between rounds 3 and 4。We see that we just insert。

 We copied over 8 elements。 Then we get a free insert。 We get a free insert。 We get a free insert。

 We get a free insert。 We get a free insert。 We get a free insert。

 Most of these operations don't require any copying at all。 Only once every so often。

 do we have to actually then copy over all of data and move forward。

But then we can insert all of that data again before we have to do another copy operation。

 So the average time on an average operation。Is going to be O of one time that， on average。

 resizing the array takes a constant amount of time。Amortized across the entire runtime。

So let's look at how this all comes together。We looked originally at the fact that we have a table that we filled out at the very beginning of this video。

Where the access time for an array is always O of one。

And the access time for a linked list is always O of in。

What you've just been introduced to is runtime analysis。

 and runtime analysis allows us to formalize a method of computing the speed of an algorithm as the size of the input grew。

 You saw two different runtime analysis。 You saw the runtime analysis of what it takes to access an element。

 and you saw the runtime analysis of resizing an array。

 We summarize runtime analysis in what we call big notation that we leave out everything but the most dominating term in the equation。

So the most dominating term may either be O of1， which we call constant time。

 That means it's going to run approximately in the same amount of time。

 no matter how big the data is， for example， looking at an array and getting a particular index out of array runs an o of one time。

It might run in linear time。As the data grows， the running time is going to grow at the same rate。

 It's linear or O of n。And then we have O of n squared o polynomial time。

 This is the total amount of work， for example， if we resize array by adding two elements at each step。

This O of n squared or polynomial time is going to be much slower than linear time。

 And's that's going to be much slower than constant time。 So as we do analysis。

 we're going to want to try and achieve O of one time if fall， if at all possible， Otherwise。

 we may see O of n or in squared time。 We'll keep looking at some more analysis in the next video。

 So I'll see there。

![](img/170743ed724d9a24bfe0dcf098ffb8b5_3.png)