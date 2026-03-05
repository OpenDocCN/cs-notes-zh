# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p26 P26 05_第一课1-1-5：冲突处理之二——探测法与双重哈希 -BV1KnLCzXEcQ_p26-

![](img/0d36642791d04fc923050658aa43a379_0.png)

![](img/0d36642791d04fc923050658aa43a379_1.png)

A second way to deal with collisions inside of array is to use something called probebigche hashing。

This collision strategy doesn't use a list whatsoever。

 and said we're going to develop an entirely new strategy to deal with this。😡，To do that。

 we're going to consider an array just like before。

 but now our array is actually going to store the data as opposed to being a linked list。

And let's take a similar input set and run it through a similar hash function and use the different strategy when we run into a collision。

 Here we have this same set of data and our same hash function。

 I'm going to go ahead and run through this， just as before。16 mod 7 is going to be 2。

 so I'm going to add 16 to index 2。8 mod 7 is going to be 1。

 so I'm going to add the value 8 to the index 1。Four mod7 is four。I'm going to add 4G index4。

And then 13 mod7 is going to be six' going to add 13 to next six。Now we're at 29。29 mod 7 is one。

And now we go to our new strategy in probebase hashing， if we run into a collision。

 instead of simply using a linked list to handle o。

 we're going to simply look at the next location inside of the array。By looking at the next location。

 we're just going to probe ahead until we find an empty slot。Once we find that empty slot。

 we can write the value right there。 So looking at this example。Here at one。

 we can't enter 29 at one because we already have 8 there。 So means it probe ahead。

16 is also filled up。 So probing ahead again， we can finally put 29 in index 3。Next to 11。

 11 mod 7 is 4， we look at index 4， we find index4 is already filled up。

 we probe ahead and find that we can put 11 in index 5。Finally， we find the number 22。

 22 mod7 is one。 we have to start at one and now probe ahead until we find them de slot。

Notice that we have to go through an entire array， loop all the way around until we get to 0 before we can insert the value 22。

 We had to look at every single element in the array。

 at only our very last chance were we able to insert that data。

You can imagine this is going to cause some problems。

We may not want to just always insert our data at the same location。

And we're going to find the runtime of this is going to be problematic。

So we're going to express this mathematically by saying this simple function right here that we're going to try to do a single step every single time。

But what's going to happen with linear probing when we probe one element at a time is we have something called a primary cluster that's forming。

 You already saw an intuition of this when we went through the example earlier。

 the intuition here is that as soon as you start getting a pack of numbers filling up。

 We're going see that a lot of things are going have to be probed until the next tell the end of the pack。

 So if you imagine this array， we have a number of elements that have been filling up right here in this space。

 it's getting pretty crowded， lots of things are hashing here， we may hash another value here。

 So now if we hash to anything in this point， it's always going be probed until this point right here。

So we have something called a primary cluster， the idea that even with a uniform distribution that based on the laws of probability。

 we're going to end up with a cluster that has a primary set of values all in a single block。

 While the rest of the array is going to be fairly sparse。

 The remedy to this is we want to make sure our probing isn't exactly linear。

So let's do something called double hashing to fix this problem。In double hashing。

 instead of just having a linear probe every single time。

 we're going to have a secondary hash function that's going to allow us to hash into a new index that's not necessarily immediately following the other point。

So let's look at that。Here we can see that instead of saying k plus 0 times our current number of hashing。

 this was 0，1，2， we're going to multiply 0 by a new hash function。So here。

 given a key and giving the number of times you're hashing it， we have。H1 is going to be。

Our first hash function， this is。Came on 7。 Well， H2 will be our second hash function by how far we need to jump at each point。

So in our second hash function， we want this to be an output of some value that's going to be not zero and less than the size of the array。

So one can imagine that our second hash function might be something like our mod value。

5 minus our key mod 5。So here we know that K mod 5 has the output range of 01，2，3 or 4。

 so 5 minus4 is1，5 minus0 is 5， so our step functions is either going to be1，2，3 or 4。

 or 5 when we do double hashing。Diving into this example to really see what's going on。

 we're going to start with 16，16 mod 7 is still going to be2。So we go ahead and at enter 16。

8 months 7 is1， we enter8 at index1。13 mod 7 is 6。 We insert 13 at index 6。And I skipped four。

 but four is totally fine to do it now， four mod seven is four。

And we stick four right here in the next four。 Now we get to the point where collisions begin。

29 mod 7 is one。And now we have a collision at one。

So because we don't want to simply do linear probing。 Now we need to apply double hashing。

 That means we're gonna apply a second hash function。 Let's go ahead and do the second hash function。

29 mod 5 is going to be 4，5-4 is 1。 So we're going to do linear probing on 29。Our step functions one。

 that's fine。 we only need to jump two spots。We can go ahead and put 29。Second number we get is 11。

 so 11 using our original hash function， 11 mods 7 is 4，4 is filled up。But using double hashing。

 we now are going to use our second hash function。We have 11 mod 5， which is1，5-1 is 4。

 So our step function is 4。 So looking at index 4， we're gonna jump ahead 1，2。3， four indices。

 and then jump four more ahead，3，4， and find that we go ahead and insert the number 11 right here immediately following four。

 but we did so using a different process。What we find is when we do this on a large scale that this approach of randomizing how much we step at each time is going to avoid the idea of a primary cluster。

So the big idea you should take away from this is no matter what strategy we use as our hash table becomes full。

 we're going to see our performance degrade。😡，And we can actually quantify this by looking at the load factor and the amount of collisions that are required to resolve the collision to find Norman spot as functions。

I've done this for you， and we did a lot of math to get to this point to find out the exact equations using linear probing。

 double hashing and separate chaining。To find out the total number of collisions that are expected and the running time to insert using these different techniques。

The goal of these equations is not to understand the equation of the self。

 but to understand how the equations behave as the load factor of our hash table changes。

So what that means is we can look at these equations and see where is alpha in all of these equations。

 So here alpha is in a denominator denominator。Alpha is't a denominator。So as alpha increases。

You're going to see that the running time is going to be 1 minus alpha 1 minus alpha 1 minus alpha。

 So the running time is going to get worse。 The larger or load factor is。

 This intuitively makes sense that as alpha increases， the running time of our hash table gets worse。

And I don't have an intuition of exactly how these functions work。

 So I went ahead and graph these functions so that we can actually see a graphical implementation of these functions。

Using the graphical representation， I can see the load factor with linear probing shows that there's an absolutely small amount of running time。

As we go up alpha， So alpha is here is on the X axis as we increase Al running time is here on the Y axis。

As alpha increases， the running time increases as well。 Likewise。

 it's for double hashing as alpha increases， it flat for a while。

 and then the running time explodes as alpha gets close to 1。0。

What this really shows is as long as we manage alpha。

 we can have a very predictable runtime of our algorithm。 So specifically。

 let's look at having alpha be at the value of about 06。

So if we manage alpha to always be at or below the value of 0。6。😡。

Notice that the running time of this algorithm is extremely fast。

 These are absolutely as amazing running times， given an alpha value lesson 。6。😊。

What this means is it doesn't matter how much data is in R。 R can have a billion records。😡。

But because alpha is only the ratio between the actual amount of data and array and the size of the array。

 as long as we can keep expanding our array， we can find that a running time is absolutely phenomenal。

 no matter how much data is inside of our data structure。Inside of our hash table。

 if we have a billion records or just 100 records， the running time is determined only upon the ratio of the amount of data in our hash table to the size of the array and not the actual amount of data itself。

So what this means is that they're running time。Proportal to only the amount of data for any hashing technique。

 as long as we keep alpha constant， that running time is going to have an O of one running time proportional to data because the running time is going to be proportional to alpha。

 not proportional to the amount of data in their array。

The one last little bit to complete this whole idea is that we're going to have to resize the array every so often。

So when we resize the array， we're going to have to be very。

 very careful about resizing this array because if we simply resize the array by copying every value over as we've done with every other resize。

 you'll notice that resizing the array is going to change where values get hash to because we have a compression step that says whatever our hash value is。

 we're going to modify it by some value， the one important part to think about is to what happens when we do have to resize the array。

 because the one thing we know is we absolutely need to maintain that ratio that alpha value between the number of data the amount of data inside of our table and the actual size or array。

😡，As we learned earlier， when we resets an array， we're always going to want to double that array。

 And in doubling that array， we're going to have to do something called rehashing。

So rehashing is the idea that if we take a value from the array。

 the original spot it hash to is not necessarily going to be the new spot it hashs to due to the compression aspect inside of our hash function。

 So remember our hash function gets an ingers， then mods a by a value。

 If we consider this example right here， we might have originally hash something to index 1。

 When we expand the array， that hash index 1 may have been at1， or it may have been at index 8 or 9。

 depending on the size of the array。Because of this。

 we need to make sure that when we expand the size of array。

 we go through and rehash every single value in the array to make sure it's in the proper spot Right now。

 we have a complete understanding of the entire hash table system。

 We know that we need a great hash function that spreads out our data uniformly across the table。

 We know that that function needs to be quick， deterministic and satisfyisfies Suha。

 We know we have an array that we have to maintain the size of that array to be keep a great ratio and alpha value less than 0。

6 to have extremely strong performance。😊，And we know what happened， what we need to do。

 when collisions do happen， that we have different strategies either using a linked list。😡。

Or using linear probing or double hashing to handle these collisions。

All of this gives us an amazing opportunity to develop a really awesome algorithm。

 do some really awesome things with hashing。Well in the next video do。

 we'll discuss a final little bit of hashing and do some analysis on the entire system as a whole。

 so I'll see you then。🎼。

![](img/0d36642791d04fc923050658aa43a379_3.png)