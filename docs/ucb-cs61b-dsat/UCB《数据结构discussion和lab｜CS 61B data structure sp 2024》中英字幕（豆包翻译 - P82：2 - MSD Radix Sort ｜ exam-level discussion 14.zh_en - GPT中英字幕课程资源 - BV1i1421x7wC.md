# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P82：2 - MSD Radix Sort ｜ exam-level discussion 14.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

All right， so we'll be going over exam level question number two， MSD Raic sort。

So in this question they're asking us to implement MSD rate sort， what do they give us well。

 they give us some myskeleton code and as well as some methods to use when answering these blanks。

But before we hop into any of them and in any of that。

 let's go ahead and go over some intuition about what Raic sorting is。



![](img/2278acda2e1af9105b1cd5305f1c723f_1.png)

Well， rate sort sortting instead of comparing values。

 we're going to be comparing the values of each digit。

 so what we're going to be doing is we're going to be going digit by digit。

And comparing them and sorting it that way。 So for MSD Ras。

 we're going to start at the most significant digit， hence MSD。

 and we're going to continuously increment our index to the right until we get to the least significant digit。

So over here， we notice。We have the very first iteration of MSD。

 what do we do while we choose the most significant digit and then we sort buy that most significant digit。

 notice how all the lowest significant digits as in the ones over here get pushed to the top。

 the fours are grouped together and put right below the ones and finally we have seven and nine。

But this doesn't fully sort our entire。Array or our entire list of items。

There's more that we have to do and what do we have to do well？We have to partition and recurse。

 What does partition mean， Well， partition means we're going to be grouping。

All are elements that are equal in the digits。That we are comparing。

So we notice in this green bubble we are comparing 121 and 120。

 the current digit that we're comparing is the most significant and the ones are the same。Therefore。

 we're going to group those two together in partition them， and then we recursively call MD on this。

Group。Notice how4，5 for 45，2 and for435 in this purple section。

 we have the same thing we group the elements。That are equal at the current digit that we are comparing。

4，5，2 and 435， well we're both comparing the four and so we're going to group those together and call Raic sort on those。

What happens when we call rate ex sort on those Well， before we get to that。

 let's go ahead and look at 789。And9，5，0。Notice how they don't share any digits。

Or they're not equal to any other。Digits that we're currently looking at in the index that we're currently looking at rather。

So what do we do， well， we just group them up with themselves and recursively call MSD Raic sort。

When we sort one element， what happens？One element is， well， trivially sorted， right？And so。

We can just return that element。Hence， we have this long arrow putting it into our answer。

 like our final item sorted array。But say it's not just one item。

 say it's more than one item and those items are different， just like we have in our purple section。

 what do we do， Well we're going to increment our index at which we're checking the digits。

 So in this case we're going to be checking the middle digits and sort via those。Well， what happens。

 the twos get pushed to the top。They stay the same and the three and the five fl。All right。

 so notice how we are going to group the two together， why。

 because the current index that we are working with， they share the same digit。

 they have the same value of two， and so we're going to group those together and recursively call MSD on them once again。

But for this other section we notice that they are not equal and so we're going to group them up with themselves and go ahead and call MSD Raatic sort。

 well since they are only one element what's going to happen well we're just going to return it and add it to the list and that's why we have this arrow pushing it to the brightmost side。

Then we have finally one recursive MSD ratings so call。

And so what's going to happen well we got to increment our index once more and we're going to be looking at the third or the least significant index。

We're going to sort according to that index so0 comes before one。

 we're going to put 0 above one and we have 120 and 121 sorted notice how these do not share the same value at the digit we're currently comparing they're0 and1。

 they're not equal and so what do we do， Well we're going to group them up with themselves and go ahead and return them。

Once we hit our base case， that being their size of one。

So now with that little bit of intuition on how MSD Ra sort works。

 let's go ahead and hop into an implementation。

![](img/2278acda2e1af9105b1cd5305f1c723f_3.png)

So we're given this skeleton code notice how we have to。Methods called MSD。

The only difference between the two is that we have this extra index over here。

So this implies that we are most likely going to be calling our other MSD passing in some sort of start index。

The question is what's going to be that start index Well with MSD we're going to be starting at the most significant digit and that's what we saw in our example over here。

 we started at the most significant digit or the zero digit。

 so we're going to be passing in zero for our index。



![](img/2278acda2e1af9105b1cd5305f1c723f_5.png)

![](img/2278acda2e1af9105b1cd5305f1c723f_6.png)

是。Now for the base case， when did we just return our item？



![](img/2278acda2e1af9105b1cd5305f1c723f_8.png)

Well， we've returned our item， as we saw in our example， when we hit an item or a grouping of size1。

 right， we have 120 and 121 and 4，3，5 down here。And 4，5，2 and 7，8，9。

 these are all groupings of just one element。 and if they are groupings of one element。

 then we have nothing else to compare it to。 Therefore it's sorted。



![](img/2278acda2e1af9105b1cd5305f1c723f_10.png)

And so we just want to return。So how do we represent the NA code Well we save items stuff size。

Is going to be less than or equal to one。Well， then we want to just return the item。

 That means we are guaranteed at least or anything lower than one item， right， if there's zero items。

 well， there's nothing to sort。All right。There's one other case that we have to go over。

 What happens if there's duplicates？

![](img/2278acda2e1af9105b1cd5305f1c723f_12.png)

Let's take a look。Say we had a duplicate of 121 and。Let's say we just were working with two elements。

 right of that duplicate。So we start comparing our。We start comparing our very first。Elements， right。

 we have the one and the one。So let me just delete this really quickly。These create a grouping right。

 we' are going to petition them together because the current digit that we're looking at。

 which is the very most the most significant digit they're equal。

And then we're going to increment our index and call MSD rig sort。

 then we're going to get to the twos， notice how again they are equal and then we're going to get to the threes we're going to increment our index or the third index right or the second index。

 the least significant digit is another way to put it。Once again。Those are equal。

 and so we're going to group them together according to our partitioning rule and call MSD Ra sort on them just once more。

And when we call MSD Ra sort。Reccursively， we noticed over here we'd increment our index at which we look at。

 right， at which digit we look。And so if we increment our index once more。Well。

 our index is going to be past it， right？We never hit our base case of just， is our。

Grouping less than or equal to one， right， this is less than or equal to two。

And so our index has surpassed our length of our elements。

When our index has surpassed our length of our elements。

 we noticed that all the elements that we're working with are going to be equal。

 so 121 and 121 have to be equal if the index has passed them and they're still greater than the size of one。



![](img/2278acda2e1af9105b1cd5305f1c723f_14.png)

All right， so how do we put that， we're going to say or。

Or if our index is going to be greater than or equal to the length of the element， right。

 we were looking at the length of the element over here。



![](img/2278acda2e1af9105b1cd5305f1c723f_16.png)

![](img/2278acda2e1af9105b1cd5305f1c723f_17.png)

So how do we do that， we say items dot get at burau。Go like。Why did I say get at zero？



![](img/2278acda2e1af9105b1cd5305f1c723f_19.png)

Well。Once the index is past this， we are guaranteed that all of the elements are going to be of same length。

Therefore， we can just call arbitrarily the zero within。The zeroth index rather。



![](img/2278acda2e1af9105b1cd5305f1c723f_21.png)

ok。So with our base case established， let's go ahead and move on。



![](img/2278acda2e1af9105b1cd5305f1c723f_23.png)

What was the very first thing we did？The very first thing we did was sorted the most significant digit。

And then we worried about all of our ifs and partitioning and recursion and all of that complicated stuff。

But first， what did we do， we sorted it according to our given index that we started at and in this case we happened to start at the most significant digit or index equals zero。



![](img/2278acda2e1af9105b1cd5305f1c723f_25.png)

So let's go ahead and reflect that in our code， we're given this stable sort down here。

This stable sort does exactly that when we call stables stable sort。And passing some item。



![](img/2278acda2e1af9105b1cd5305f1c723f_27.png)

And our index。What we're essentially doing。六。What we're essentially doing。Is this？

This is passing in our index of zero and we're going to be ordering all of our elements according to their current digit and their value right so in this case our current digit that we're going to be working with is the most significant digit and we're going to be sorting that according to that。



![](img/2278acda2e1af9105b1cd5305f1c723f_29.png)

Cool。So that's how we got this part。Now we can worry about all of these crazy ifs and whatever is going to happen。

 but before we do that， let's go ahead and ahead and notice that we define something called start equals zero or is going to be starting at zero and we're going to be incrementing through our end right we've also created an end。



![](img/2278acda2e1af9105b1cd5305f1c723f_31.png)

Let's go ahead and。Work with those then。We're going to take our start and point it at index0。

Just how it's defined and same with end and points set index1。K for loop。So， we noticed that。

They're currently pointing at the same。Or they're currently pointing to elements that are in the same partition right the ditch that we're currently comparing are the same。

So。Do we want to partition here， Well， not yet we don't know if the next element is going to be part of that partition。

So。Let's go ahead and increment or end just once more。Now。

 we notice comparing our start to our end that the digit that we're currently working on。

 which is our most significant digit。It's not equal anymore， we have 121 and 452。

The one is not equal to the four。 And so what does that imply。

 That implies that we've iterated already through our。Through over our entire partitioned group。

We've iterated over everything that we need to group up and recursively call MSD Rad sortton and all of that。



![](img/2278acda2e1af9105b1cd5305f1c723f_33.png)

So let's go ahead and implement that。So we say if our item。



![](img/2278acda2e1af9105b1cd5305f1c723f_35.png)

Dot get。 Well， we're getting it our very first element at start。



![](img/2278acda2e1af9105b1cd5305f1c723f_37.png)

嗯。The character at index。We have to compare the current index that we are on when we are partitioning。

So we want to say。Hey， if this is not equal to。

![](img/2278acda2e1af9105b1cd5305f1c723f_39.png)

The same index set the end。Well。That means we've iterated through our entire grouping of the same element。

Therefore， everything before the end。And including the start， we want to call MD Radixtorton。

That rings a bell。

![](img/2278acda2e1af9105b1cd5305f1c723f_41.png)

We're essentially grabbing a sub list， right？And so let's go ahead and use this hint that they give us the subst。



![](img/2278acda2e1af9105b1cd5305f1c723f_43.png)

We're going to define a new variable。嗯。Let's call it sublist。And we're going to say。

Items do subs where we're going to be passing in our front index。 Well。

 we want to get our sub list starting at this start element。



![](img/2278acda2e1af9105b1cd5305f1c723f_45.png)

And ending at our end element。our end points is 452， and you might ask， hey， Dylan。

 won't that 452 be included？

![](img/2278acda2e1af9105b1cd5305f1c723f_47.png)

No， well， our sub list keeps Dar as inclusive and end as exclusive。



![](img/2278acda2e1af9105b1cd5305f1c723f_49.png)

So we're just going to create a sub list of 1，2，1 and 120 and not one and not 4，5。

2 right so the element just before we hit end。And so look at that。

 we created a sub list of all the elements that should be partitioned together。

 all the elements that share the same value at the digit we're currently exploring。Now。

 what do we do with that？Well， we noticed over here we incremented our index and recursively called。

M S D Raic sort until we hit our base case and returned it。

So let's think of how we can do that once it's returned， we will have to add it to error。



![](img/2278acda2e1af9105b1cd5305f1c723f_51.png)

Final answer， right， our final returning list， and that's what we have defined over here。

So we're going to say answer dot at all， vote add。Oh。Of。What are we passing then， Well。

 we have to call MSD on our sub list。

![](img/2278acda2e1af9105b1cd5305f1c723f_53.png)

And。What happens to our index？Every time we've called MSD， we've incremented our index。

Notice how we started at the most significant digit。

 then we're starting at the middle digit and finally we're ending at the least significant digit。

So every time we call MSD Ratorrt。We're incrementing our index。Because we then have to sort by the。

Each index。Fromrump starting from them was significant。Digs all the way to。

Are the least significant digits。Okay。Now， what's this last line？Well。

 we need to figure out once we've partitioned once， how can we find the rest of our partitions？

So say we've hit this if statement here， right， we've partitioned the green bubble out。

Now how are we going to get that partition of the 452 in the 435 or that purple section？Well。

 if we set and and start equal to each other， they're pointing at the same place。Well。

 we're not going to enter our if statement， right， because the digit that we're currently working on452 is going to be equal。

 right？The end and the start， the digit that we're currently working on is going to be equal。

 so what do we do while we're not going to enter our for loop and we're going to move our end down。

Notice they are still equal at this case， the current digit that we're working on。

 which is the most significant digit those being four， they're both still equal。

 so we're not going to enter our statement rather。And so what do we do。

 we increment our end just once more， and bam， we found the partitioning of purple。

So what did we notice was the key， we're essentially going to start。

 we're going to set our start to our current end。And we're done。

Except there's one thing we were missing。What happens when end points to the very last element？

And what happens if start also points at that very last element？

Right we've partitioned this orange part out， and we're going to set end equal to start。

And now we're going to have a little bit of a dilemma。We're going to say， hey。

 increment our end and point it， o， increment our end， and point it to the next element。

But do we have a next element？Ope， oh my god it's stuck。But do we have the next element？No。

 and so we're going to get an index out of bound error。So how do we prevent that？ Well。

 if we say end is pointing to our very last element。Then partition that last Ellen。We're done right。

 there's no more elements that we need to look for to partition。



![](img/2278acda2e1af9105b1cd5305f1c723f_55.png)

And so let's add that little。Extra condition。So。We say， if our item。Or， rather。

 let's say if our end that we're working at。Is going to be equal to items。Dot size。

 or it's at the very last element。Then。We need to partition and we are done。

So this was the final implementation for question two on discussion 14 exam level。



![](img/2278acda2e1af9105b1cd5305f1c723f_57.png)

诶。I hope that was helpful。