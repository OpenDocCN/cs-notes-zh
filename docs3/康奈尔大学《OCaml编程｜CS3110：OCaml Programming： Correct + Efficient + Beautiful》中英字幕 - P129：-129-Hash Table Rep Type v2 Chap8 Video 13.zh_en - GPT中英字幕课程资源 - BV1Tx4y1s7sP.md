# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P129：-129-Hash Table Rep Type v2 Chap8 Video 13.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Here are the algorithms for the primary operations。To insert a key value binding into the hash table。

 we're going to hash the key to find the bucket that it goes into。😡。

Then we're going to have to search through that bucket to delete any previous binding of K。😡。

That's to maintain our representation invariant that no key is bound more than once。

Then we will mutate the bucket。To add the binding of K to V。The find operation is similar。

We're going to hash the key K to find what bucket it's supposed to be in。

And then we're going to search through that bucket linearly to find the binding of the key。

The remove operation is similar to the other two， hash the key to the bucket and search through the bucket to delete any binding of the key。

Of course， once we find one， we're done because there can't be a second binding of it by our representation。

Now right away， what you'll probably notice is that every one of these operations requires us to search through one bucket。

😡，That's a little worrisome。We chose this representation type because we wanted to get constant time operations。

 Now， suddenly， we're searching through a bucket。 And if we're not careful。

 that could turn out to be a linear time operation instead of constant。

So our efficiency here is going to depend on the bucket length。😡。

If the bucket length could somehow turn out to be a function of the number of bindings that have been added to the hash table。

 we're in trouble。But if the bucket length could only stay a constant。Well。

 then we'd be good because we'd only be doing a constant amount of work to search through each bucket when we need to。

Well， the bucket length is going to depend on the hash function。For example。

 here is a terrible hash function。 Suppose that the hash of a key K， no matter what the key is。

 is just 42。 So this is just a constant function。What that would mean is that all keys collide and are stored to the same bucket。

In essence， we have a huge array around the bucket。All of it is empty， except for that one bucket。

And at that bucket， it's just an association list。 So this degenerates to our association list implementation of maps。

And in that case， of course， insert， find your remove are all going to be linear time operations。So。

😡，Let's assume a property of the hash function。Let's assume that it distributes keys randomly over the buckets。

😡，And by randomly here， I mean that the keys are distributed uniformly over the buckets。

 they're likely to end up in any bucket with equal probability。

So that random uniform distribution implies that all buckets have about the same length because on average you're going to end up with about the same number of keys in every bucket。

Let's call the expected bucket length L。😡，In that case， insertt， find and remove。

 all have an expected running time that is big O of L。😡，The expected bucket link is five。

 then they all have an expected running time of five。

 which is just constant right Big of any constant is just big of one。 So really。

 what this means is we're getting a constant running time。 That is what we need。

We can get constant time insert， find and remove operations with arbitrary key types if our hash function gives us this property。

 think about this in terms of the number of bindings in the table versus the number of buckets in the whole array。

😡，If the hash functionch is distributing keys uniformly over all the buckets。

 the inspected bucket length is going to be the number of bindings over the number of buckets。

So if you have 10 bindings in 10 buckets， then on average。

 the expected length of any bucket is just going to be one。

You're not going to have to search any more than one element， that's great， that's constant。

If there were 20 bindings in 10 buckets， then the expected link would be2， that's still fine。

 That's still a constant。 Or if the number of bindings was 5 and there were 10 buckets and the expected link would be one half。

 that's even better half the time we won't even have to search any。

No matter what the distribution is of keys through the buckets by the hash function。

There's another quantity that's of interest。And that's called the load fact。

It's what we were investigating just on the previous slide。

The load factor is the number of bindings over the number of buckets。

The load factor effectively tells you how well the hash function is doing its job of distributing keys randomly。

😡，And because that's such an important feature of the performance of hash tables。

Real world standard library implementations give you the ability to query the load factor。😡。

So both OAMl's hash table and Java's hashmap actually do provide functionality for you to ask a hash table what its current load factor is to see whether you're in any performance problems or whether your hash function is behaving well or badly。

Now， the key thing about the load factor is that although the number of bindings is not under the implementer's control。

 the number of buckets is。😡，It's the client who gets to put bindings into the hash table。

 We probably shouldn't be writing hash tables that restrict the number of bindings they can add。

 That actually was one of the downsides of our direct address table implementation because you had to declare the capacity in advance and it was fixed。

But the number of buckets。That's the number of elements in the array。And if we needed to。

We could allocate new arrays and increase or decrease the number of buckets in the hash table。😡。

So here's the key idea。When the load factor gets too big。That is to say above some constant。

 and it's important that it's a constant。Then the hash table needs to make the array bigger。

Now in most array implementations， the array is not resizable。

 that means allocating a new array and copying some elements over。😡，When the array gets bigger。

 the number of buckets goes up， so the load factor goes down。There's extra work to do there。

 We then have to redistribute these keys across the bigger array。

 but we're keeping the load factor bounded by a constant when we do this。

So here's our new representation type。😡，I've put it inside of a record at this point because what I want to do is make the array mutable。

😡。

![](img/0c2b576ba3f84f378b93b5bf2511367a_1.png)

I could also have used a ref。 doesn't matter much， but it's going to be convenient to have a record later on。

To make the a reizable。

![](img/0c2b576ba3f84f378b93b5bf2511367a_3.png)

That field of the record is mutable。 What that means is I can mutate that field at the point in time at which I need to increase the size of the array。

 So notice the double level of mutability going on here。

The array itself has elements that are mutable。And the record has a buckets field。 That's mutable。

We mutate array elements to do an insert or remove。

We mutate the bucket's field when we need to resize the array to keep the load factor bounded by a constant。

😡。

![](img/0c2b576ba3f84f378b93b5bf2511367a_5.png)