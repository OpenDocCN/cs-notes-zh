# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P121：-121-Association Lists_ Of List Chap8 Video 5.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/e1d6c9ddc6a88ef1c3fdced68c4bb5c7_0.png)

We have two ways of creating non empty maps。 We can insert keys。And we can construct out of lists。

Let's try of list， first。I've written a test case， there's some things I don't like about this test case yet。

 but first let's just make sure that it fails。Good， it did fail。 Now。

 let's look back at this test case and clean up a couple things about it。First off。

 I've eliminated that duplicate expression by using a let binding for it。

 But I also now have duplication of。Testing code with assert equal and a call to bindings。

 I should factor out a function for that。That's more pleasant of testing code。

 I've eliminated a lot of the duplication that existed in my previous draft of it。

 It's okay if drafts involve some duplication at first， the key thing is to get rid of them later on。

Let's again try running the test suite。It fails good。 it ought to at this point。

 now we'll make the test case pass right now， I'm just going to implement of list by literally using the list that's passed in。

😡，Is that going to work。

![](img/e1d6c9ddc6a88ef1c3fdced68c4bb5c7_2.png)

I should read the specifications and think about it， but let's run the test suite， see what happens。

Yay， the test passes。Now let's go back and think about those specifications again。

 of list requires that the list does not contain any duplicate keys。

If someone did pass in a list with duplicate keys， that would be on them。

 our implementation is not responsible for it。😡，All we need to do is guarantee that we return a map containing the same bindings as that association list。

Well， our abstraction function is going to guarantee that。

If you pass in a list that doesn't have any duplicates。

 then we can straightforwardly use that list as the representation of the map。😡。

So this actually is a good implementation of the of list function。

Now that we've finished that test case， let's resume thinking about the efficiency of each of these operations。

The efficiency of L is constant， there's actually nothing that we need to do in terms of work here。

The efficiency of binding。Well， list thought Assosh is going to have to look down the entire association list M。

 potentially in the worst case， to find the binding of K。

So the efficiency of that is going to be linear in the length of the list， that's Biggo event。

And what about the efficiency of bindings？Well， first it's going to call keys M。

Which is going to get us all the keys of M。 We already know that the efficiency of that is big O and long n。

It's also going to partially apply the function binding to M。

 that's just a constant time operation we're passing in one argument and getting a function back。

And then we map down a list。😡，Now， in the worst case。

 the length of that list is going to be the number of keys in the original map。So。

 that's bigger of N。And then how much work are we doing for each element of that list Well we're looking up the binding of each of those keys。

 so that means for each one of them， we could be doing an additional big O end work。😡，Of course。

 we could simplify that。Because the big O of n squared term there actually dominates the n log n quadratic is worse than linear rhythmthic。

So we don't have a very efficient bindings function。😡。

We could have made it more efficient if we had documented a representation invariant that prevented duplicates in the list。



![](img/e1d6c9ddc6a88ef1c3fdced68c4bb5c7_4.png)