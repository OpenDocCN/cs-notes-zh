# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P130：-130-Rehashing Chap8 Video 14.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

If the load factor exceeds， say two。Then the implementation of the hash table pauses to double the array size。

And copy all the elements over。Rehashing them as it goes into potentially new buckets。

That hal the load factor。Because the number of bindings stays the same。

 but the number of buckets doubles。So maybe the load factor goes from two down to one at that point。

Ol's hash table does exactly that， it resizes at a load factor of  two， bringing it back down to one。

JaA hashmap actually resizes at a load factor of three quarters。

That higher resized threshold decreases the space requirements that increases the time requirements。

When there's two expected elements to look through at each bucket。

 it's taking a little more time than when there's only three quarters expected elements to look through at each bucket。

But when there's two， then they're packed together more densely inside of the table。

 and so you're not wasting as much space on buckets there potentially。



![](img/142f37255d6fefca70450ccf2c1fba1a_1.png)

So the efficiency of find and remove is now expected constant time。😡，Because in expectation。

 there's only a constant number of elements that they have to search through at each array index。

But insert， that's still a problem。It's still a worst case linear time operation。

Because if you just inserted an element and caused the load factor to exceeds that constant。

 whatever it might be， now you've got to rehash all of the bindings in the hash table。

 and that's a linear time operation。😡。

![](img/142f37255d6fefca70450ccf2c1fba1a_3.png)

By the way， you can do the symmetric thing if the load factor goes below some constant。

Maybe one half， for example。If the load factor gets so low that you've got a lot of wasted space。

 you could then。Alloccate a new array with half the capacity and rehash all the elements into new buckets in that。

 which would cause the load factor to double， say， back up to one。

This is an idea you'll find in many textbooks。 Real world libraries don't seem to do it。

 Okaymel doesn't do it。 Java doesn't do it。I once talked to one of the implementers of the Java hashm and he said it was because they did a study of real worldor workloads for hash tables and they discovered this just wasn't a useful thing to do。

 what really ended up happening is that although yeah maybe sometimes the hash table would get a little small。

 eventually users of the hashm would be adding more elements back in。

 so it was just wasted effort to try to go ahead and do this kind of rehashing。



![](img/142f37255d6fefca70450ccf2c1fba1a_5.png)

![](img/142f37255d6fefca70450ccf2c1fba1a_6.png)

So here are our three implementations of the map ADT so far， association lists。

 direct address tables and hash tables with chaining。

Hash tables with chaining are almost the best of all worlds。 Now we can allow any keys。

We have a fast find and remove operation as long as we have a good hash function。



![](img/142f37255d6fefca70450ccf2c1fba1a_8.png)

We have a seemingly slow insert。In a later video， when we talk about amortized analysis。

 we're going to figure out how to solve that problem as well。



![](img/142f37255d6fefca70450ccf2c1fba1a_10.png)

Well for now。Let's proceed with this implementation。



![](img/142f37255d6fefca70450ccf2c1fba1a_12.png)

![](img/142f37255d6fefca70450ccf2c1fba1a_13.png)