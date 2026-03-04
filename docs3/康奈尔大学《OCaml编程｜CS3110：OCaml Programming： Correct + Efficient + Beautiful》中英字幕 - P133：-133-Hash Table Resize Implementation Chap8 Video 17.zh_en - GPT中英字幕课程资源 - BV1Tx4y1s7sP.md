# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P133：-133-Hash Table Resize Implementation Chap8 Video 17.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Next， we need to handle the resize。So for my implementation of resize if needed。

 I'm going to keep the load factor between one half and two。

 I will go ahead and resize the hash table whether it gets too big or too small。All right。

 I've sketched out a little bit of the implementation of resize if needed here。

 I know that I'm going to need to compute the load factor and then do something if it's too big or too small。

Let's pause there to write the implementation of the load factor helper function。

So I want to take the number of bindings in the table and divide it by the number of buckets Up front。

 I made the decision we were going to keep track of the size of the table in the record representing it。

And now we need to divide it by the number of buckets。And we already had a function for doing that。

Of course all of this is integral right now， these are integers， the size of the tables an integer。

 the capacities is an integer， and we really want something that's a float factor that's not going to always just round to01 or two。

 so let's convert all these to floats。And now we'll see that load factor really does give us a float as output。

 So back down in resize， if needed， we've been able to compute the load factor。

 and we need next to resize the table appropriately in either case。

So what I've done for the moment is depositit the existence of a helper function rehash that will go ahead and take the table。

Resize it and rehash all of the elements into it， but in an appropriately new sized table。

 if the load factor is too big， that we're going to double the capacity of it。

 If the load factor is too small， we're going to half the capacity。Okay。

 I've written the specification comment for rehash。 What does it do。

 it replaces the buckets array of tab with a new array of size new capacity。

And reinserts all the bindings of tab into that new array。In reinserting。

 it's going to rehash each key that appeared in the original array， and by rehashing it。

 we're going to take it modo a different capacity， which means it's not necessarily going to end up in the same bucket。

 in fact， it's likely to end up in a different bucket。😡，So far。

 what I've done is to save the old buckets。Then mutate the buckets field to be a new array。

 starts off completely empty， has no bindings in it whatsoever。

 but it does have the right new capacity。😡，And the next thing I want to do is iterate over all those old buckets and rehash each bucket in that array。

😡，So I'm positing a helper function here called Rehash bucket that will go through the bucket and reinsert all of the elements from it。

So rehash bucket is just going to iterate over the list that it finds in that bucket and call another helper function rehash binding。

 which rehashs each of the bindings that it finds in that bucket。

Rehash binding takes any individual binding that it finds in a bucket。

 which is a key value pair and reinserts that into the table。For that。

 I can use the insert no resize function that we've already defined because it's not going to somehow try to start rehashing itself at the same time。

 we factored those concerns out separately。Notice how in this case， by nesting my helper functions。

 I get to use tabab here in the body of rehash binding because it's in scope from the outer binding of it there for rehash。

😡，Also notice how insert no resize is going to handle incrementing the size field of the record each time it inserts an element。

 so I don't have to take care of that here myself inside of a rehash function。

 What is the efficiency of rehash going to be。Well。

 at the time we create the new array for the buckets， we've got a new capacity for that。

And we know that a rateout make is going to run in time that is proportionate to that capacity。

So what is the new capacity？Well， at the time of the resize。

 we're trying to get the number of buckets in the array to be the same as the number of bindings in the table。

Which is to say， if there are n bindings in the table right now。

 we're trying to have a new capacity of N。So this operation is going to be big O of N。

 Its linear time in the number of bindings in the。Updating the size is constant time What about the efficiency of all of the rehashing operation So rehash bucket is going to get called on all the buckets and it itself is going to call rehash binding on each one of the bindings so ultimately what this line of code does is to call rehash binding once for every binding in the table。

What does rehash binding do， it calls insert no resize。Okay， so we've got order in work then。

Being done。One call to rehash binding for every binding in the table and there are end binding in the table。

And then what was the efficiency of insert no resize， Well， it was big O of L expected big O of L。

Which is supposed to be a constant。So this whole thing reduces then to expected。

Linear time because a linear time multiplied by a constant is still lit。So the efficiency of this。

Is expected。Big O of N。Where。And is the。Number of findings。In the table。And with that。

 we've completed our implementation of resizing。And since weve completed our implementation of resizing。

 we've also completed our implementation of insert。It took a lot of work to insert into a hash table。

 but we did it。