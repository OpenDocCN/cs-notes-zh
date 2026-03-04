# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P142：-142-Bankers and Physicists Methods Chap8 Video 26.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

The banker's method is to metaphorically store credits in a bank account。😡。

At each location in a data structure。So you can think of if you're doing this with a linked list。

 say that the banker's method would say every node in the linked list has its own bankage。

If you're doing it with a Q， it could be every element in the queue has its own bacon。

If you're doing it with a hash table with chaining。

 it could be every binding that's represented as a pair in that hash table has its own bank account。

😡，Then you define the amortized cost of an operation to be the actual cost。

 what it really does take according to the code or according to the algorithm。Plus。

 the credits saved by that operation。Minus the credits spent。

So typically you're going to either save or spend， not do both， although you can mix and match。

So the actual cost is either going to go up if you're saving some additional credits or down if you're spending some credit。

And then all you have to do is to prove that no operation makes an account balance negative。😡。

Because by doing that， you're guaranteeing that the amortized costs are always at least as big as the actual costs over the whole sequence。

But you get to think about it per operation。

![](img/d20c2f2a23670592535727b1c3d75b21_1.png)

Here's what that looks like for cues and hash table。

We needed to define how many credits each operation saves or spends。With a Q。

 let's say that in queue saves one credit in the element that is being in queueed。😡，And that DQ。

When it goes to move an element from the back to the front。Spends that credit。

These account balances are never going to go negative。😡，They'll always be either zero or one。

And they go down to zero exactly when an element moves from the back to the front。

And that can only happen once。You never move an element into the back again from the front。

 it's an invariant that every element moves at once most into the front。😡，As for a hash table。

Let's say that an insert saves two credits at each binding。So metaphorically speaking that binding。

 you know， you've got a pair there， think of that also having a bank account balance along with it。😡。

At the time of an insertion， two credits go into that binding。Later on。

 someday that binding might need to be rehashshed and reinserted。At that time。

We spend those two credits and we do it in a clever way。

We spend one of the credits to rehash and reinsert that binding。But。😡。

Then that binding acts as a kind of donor to some other binding that's missing a credit。Now。

 why would there be bindings that are missing credits？Well。

 if there's already been a rehash and reinsert， any binding that came from like one of those old cycles is going to be down to an account balance of0。



![](img/d20c2f2a23670592535727b1c3d75b21_3.png)

So it needs help from a friend at that point。😡，And that friend comes in the form of one of the bindings that has been inserted since the last rehash。

Now there's going to be as many bindings inserted at that point as there were old bindings from before the rehash。

 we've got twice as many bindings now and so having two credits stored up is exactly the amount we need in order to be a good friend and help out our friends that don't have any money in their account at that time。

The physicist's method。Is a little different than the banker's method， but not so different。

Metaphorically， we think of the entire data structure， not just particular elements。

 but the entire data structure as having a potential energy。

Think of this as like having done analysis of， you know springs or the tension of a string in a bow or the potential energy of a child at the top of a swing when they're about to swing back down any one of those physical metaphors。

With the physicist' method， we define the amortized cost of an operation as the actual cost。

 as usual。Plus， the change in potential energy， which might go up or down。

Here we prove that the potential energy is never negative。And again。

 that ensures that the amortized costs always are a conservative bound on the actual costs。

For the physicist method。For two list cues， we could define the potential energy of the entire data structure as being the length of the back。

So that that by definition， can never go negative。 and any time we do the actual operation that causes the back to be reversed。

We are able to pay for that with the potential energy stored up。 it's just the length of the back。

 and that's exactly how much we needed to have stored up in order to reverse the back。

With a hash table， we can define the potential energy as being two times the number of bindings inserted since the last rehash。

 and again， for the same reason as we went through with the bankers's method that's going to be enough。

So you might notice right away here， there's a lot of similarity in the analyses I just did with those two examples of cues and hash tables between the banker's method and the physicist method。



![](img/d20c2f2a23670592535727b1c3d75b21_5.png)

That's no accident。 They're actually equivalent in power。

 They're just different metaphors for understanding the same thing。

If you want to take a banker's method analysis and turn it into a physicist method。

 then just define the potential energy to be the total number of credits stored up at all elements in the data structure。

😡，If you want to go in the other direction and take a physicist analysis and turn it into a banker's analysis。

 then just find some designated location in the data structure。

 I don't care where you pick some particular element of it and just store all the credits only in that one location and just make sure it's the potential energy that's stored there。

When I did my original analyses of hash tables and two list cues。

 I actually was doing a mash up of these two I was doing the banker's method in that I was doing it in terms of dollars rather than potential energy。

I was doing the physicist method because I wasn't bothering to say where I was storing these dollars。

 I just imagined I had a kind of central pig。So notice that you don't really have to adhere exactly to any one of these metaphors。

 you just have to be able to define the amortized cost of an operation and show that you always can pay for that operation without ever going negative。

In other words， always stay positive when doing amortized analysis。



![](img/d20c2f2a23670592535727b1c3d75b21_7.png)

![](img/d20c2f2a23670592535727b1c3d75b21_8.png)