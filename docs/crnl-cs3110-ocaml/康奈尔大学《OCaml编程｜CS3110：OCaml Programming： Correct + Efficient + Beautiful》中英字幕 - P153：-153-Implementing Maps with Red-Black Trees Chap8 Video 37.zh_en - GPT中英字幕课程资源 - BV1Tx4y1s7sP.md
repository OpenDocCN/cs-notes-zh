# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P153：-153-Implementing Maps with Red-Black Trees Chap8 Video 37.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Finally， let's return to maps We started off all of this balanced binary tree implementation by thinking about sets instead of maps because sets are a little easier。

To get back to maps， all we have to do is store a pair at each node。😡，A pair of a key and a value。

 In other words， a binding。The key is what we use as the ordering for the binary search tree。😡。

So if our keys are integers。Then the BST is ordered by those integers。

 So you would have 460 to the left of 461 and 462 to the right of 461。



![](img/88668518e6b86a3f8cc35f6c69b0c732_1.png)

![](img/88668518e6b86a3f8cc35f6c69b0c732_2.png)

The values are irrelevant at that point， we don't look at the values that those keys bind when we're trying to figure out whether the BST invariant applies。

 they're just a little extra information that's carried along in each node。😡。

Then when we go to find a binding in the tree， we can find its key that takes only logarithmic time and the value it binds will be right there next to it。

That gives us a final implementation here of the map ADT。😡。



![](img/88668518e6b86a3f8cc35f6c69b0c732_4.png)

All of the operations insert， find and remove for red black trees are big O log in。

 so their worst case log rhythmithmic time。

![](img/88668518e6b86a3f8cc35f6c69b0c732_6.png)

That means we have an asymptotic efficiency that's in between hash tables。And association lists。

But logithmic is way better than linear time。So the performance of red black trees is going to be way closer to hash tables than it is to association lists as inputs get very。

 very big。So we've got something that's almost as fast as a hash table with these functional red black trees。

But they're persistent。 You get this additional ability to keep around old values of the data structure if you want them。

It's something you didn't get to do with hash tables。

 at least not without explicitly creating copies。So we get something for this a little additional performance penalty。

It's common for persistent data structures to require logarithmic more time complexity than the equivalent ephemeral data structures。

I went ahead and finished off our set implementation table here， by the way， and we're back to sets。

By creating a hash set out of Ocael's hashable module。And for the andcending and random workloads。

 we get really blazing fast performance from hashheets。

 in fact about an order of magnitude better than red black assets。

So if you really want the best possible performance， mutability actually is essential。

I joke a lot about the evils of mutability， but you really do get something for it。

 You get the fastest map implementation of all the four that we've looked at here。

You'll all remember， Sir Tony Hore。Turing award winner in 1980 for his fundamental contributions to the definition and design of programming languages。

He said， we should forget about small efficiencies， say about 97% of the time。

Premature optimization is the root of all evil。It is very tempting as programmers to start thinking way too early about how we're going to optimize some piece of code。

😡，What Sir Tony was trying to say here， I think， is that we should let that go most of the time。

Don't get caught up in every line of code of trying to optimize it completely as you're writing it。

 You're not going to get very far that way。😡，On the other hand。

 there's a difference between optimization and premature optimization。

The asymptotic complexity theory that you have been learning in this class and other classes is meant as a guide so that you know in advance what operations are going to be really expensive。

Versus cheap。If you know you need a really efficient map data structure。

 well now you know to use hash tables or red black trees。

 probably not to use plain old binary search trees and definitely not to use association lists。

On the other hand， if you know you don't need a super efficient map implementation。

 you just need something quick and easy to implement Well association lists are your ticket if you only have very。

 very small maps， they're going to be fine because there just can't be that much to do to go through in linear time。

😡，So it's important to think about the asymptotic efficiency of the operations of the data structures。

And then later on， worry about the detailed optimization of individual lines of code。

 either in those data structures or in your own code that's using。😡。



![](img/88668518e6b86a3f8cc35f6c69b0c732_8.png)