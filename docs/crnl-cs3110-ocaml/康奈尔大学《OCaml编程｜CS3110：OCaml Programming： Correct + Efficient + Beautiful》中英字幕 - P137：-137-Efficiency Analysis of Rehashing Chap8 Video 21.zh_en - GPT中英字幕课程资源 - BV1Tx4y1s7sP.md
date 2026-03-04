# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P137：-137-Efficiency Analysis of Rehashing Chap8 Video 21.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

When we implemented hash tables with chaining， a representation type had an array of buckets and at each bucket we stored an association list。

The length of that association list could vary from bucket to bucket。

 but we kept its expected length at a constant by assuming that the hash function distributed keys uniformly over the buckets。



![](img/5a82a39dcc7accc4f17f6f45f06b5016_1.png)

Finding therefore， was an efficient operation， but insertion required from time to time。

 a resize operation to keep the average bucket length bounded by a constant。

At the time of a hash table resize， suppose that it's capacity or C that is there's C buckets in the array。

We agreed that we would double the capacity of the bucket array and create a new array of capacity to see when we implemented our own hash tables。

 that's also what the OCMl implementation does too。😡。

So just reallocating that array cost order to C the length of the new array。😡，Now。

 the number of bindings at the time of a resize was also going to be 2C because we resized when we had twice as many bindings as buckets。

😡，So let's call n the number of bindings， that means that the resize operation is itself an order n operation because n equals 2 c。

Bad， right， We've got a linear time resize at this point in the worst case。

 and we're not even done after allocating the new array。



![](img/5a82a39dcc7accc4f17f6f45f06b5016_3.png)

We also have to rehash and reinsert every element from the original array into the new array。😡。

Now that causes where each binding is in terms of what bucket it's in to perhaps change because the hash function will now be used to map that binding。

 that key into the buckets again， and we're going to take that modo a new array length。😡。

So it's not as simple as just copying the buckets over。

 We actually have to do the rehash on every key。Okay， well there were n bindings。

 that means there's n keys to rehash。 We've assumed the hash function is constant time。

 So that's order in work just to rehash all the keys。Then we have to reinsert each binding。Well。

 that's n more insertions into this new bucket array。That's going to be order in work， as well。

And that holds whether we've got a good or a bad hash function because in the worst case。

 and all the keys collide in one bucket， we're still going to have to do n insertions at that bucket。

So we've got a worst case linear time， rehash and reinsert as well。



![](img/5a82a39dcc7accc4f17f6f45f06b5016_5.png)

That means the total cost to resize is worst case linear time。Or big O of N。Now。

 you'll recall from the definition of big O notation that it really hides a constant。

When we say something is big O of n time， what that means is it's bounded by some constant times n。

 That constant might be1。 It might be a half。 It might be2。 It might be 5000， whatever。

 There's still a constant hidden there。It'll help if for a moment we think about that constant。

 which we don't usually do。Let's suppose that the hidden constant in this particular big O expression。

 which is the cost of resize is actually R， so I've chosen an R there to represent resize。

It will further help if just for a minute， we break down R into some pieces。

I'm going to break it down into three pieces。 I'm going to say R is x plus y plus C。

 Now this is just conceptually to help us think about this。

 we're not going to go too much farther with it， but suppose the X here represents the cost to allocate a bucket。

😡，Because we're going to allocate n buckets and each one of those is going to have some cost。

 we're calling that X。We're all also going to have to end different times hash a key。

 so let Y be the cost to hash a key。😡，And we're going to have to insert a binding n different times。

 So let's say that Z is the cost of inserting a binding。😡。

So R then is the total cost per binding of doing the reallocation， rehash and reinsert。😡。

Now the whole reason we got into implementing hash tables was that we wanted constant time performance and we lost it here。

😡，We blew it on this insert operation。So here's the question。

Can we get the cost of all of this resizing down to big O of one。

Can we somehow bring it down to constant cost。Because if we could。

 then we would have what we set out to achieve the best of both worlds between an association list representation of maps and a direct addressed table of representation of maps。

😡。

![](img/5a82a39dcc7accc4f17f6f45f06b5016_7.png)

![](img/5a82a39dcc7accc4f17f6f45f06b5016_8.png)