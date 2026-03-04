# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P138：-138-Amortized Analysis of Hash Tables Chap8 Video 22.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

So can we bring the cost down to constant for this resize operation？

Well the answer is we can't algorithmically change this to bring the cost down to constant。

 in the worst case， it is still going to be linear。But we can do a different kind of analysis。

And that kind of analysis can help us conclude that there is a way of looking at this that makes the insert operation be constant time。



![](img/dd13d90f07923cca5a45e738e73941a5_1.png)

Here's how that works。Let's imagine we have a piggy bank。And in that piggy bank， we save money。

 and from time to time， we crack open the piggy bank and spend money。So here's my idea。😡。

Every time we do an insert operation， let's save our dollars inside of our piggy bank。😡，Then。

On that rare occasion， when we need to do a resize operation because the load factor of the hash table has gotten too high。

Then let's crack open the piggy bank and spend whatever money we need to from inside of it。

 In particular， if we've got n different bindings in the table at that point。

 let's spend our times N dollars in order to pay for that resize operation。

Let me give you a concrete example of this。

![](img/dd13d90f07923cca5a45e738e73941a5_3.png)

Suppose that we have a hash table。And its capacity is 16。 That is， it's an array of length 16。

 it's got 16 buckets。And suppose that this hash table currently already has 16 bindings in it。

So that means the load factor。The number of bindings over the number of buckets is currently one in this hash table。

Often in these kinds of analyses， we write alpha for the load factor， so alpha is1。At this point。

 let's suppose that our bank account balance is empty。 We don't have anything in our pickgy bank。

All right， so this is just the starting place。 Now we go ahead。



![](img/dd13d90f07923cca5a45e738e73941a5_5.png)

Suppose we were to insert 16 new bindings。😡，Well， now the number of binding has gone up to 32。

And that means the load factor has just reached2。That's the point at which we're supposed to do a resize。

Well， how much money do we have saved up upon our piggy bank？We were saving R dollars per insert。

So we've currently got 16 times R dollars in our bank account。We do the resize and the rehash。Well。

 it's going to cost R dollars per binding in the hash table。

 That was the analysis we did earlier with Big O right， we said that it wasn't just big O of N。

 It was actually R times n。 R was the hidden constant。

So we've got 32 bindings that we need to resize and rehash that's going to cost 32 R dollars。

And so if you deduct $32 r from 16 R， what are you left with。

 a negative account balance of negative 16 R dollars， so we just went bankrupt。That's no good。

 We shouldn't be going bankrupt。 We don't have enough money to pay for the resize。Okay。Well。

 maybe we just weren't saving enough money。What if we go back and double the amount that we save。

So for every insert operation now， instead of saving R dollars， let's save2 R dollars。😡。



![](img/dd13d90f07923cca5a45e738e73941a5_7.png)

Let's try the analysis again。So we start off with 16 buckets， 16 bindings， and a load factor of one。

 and an empty account balance。We insert 16 bindings that brings us up to 32 bindings and a load factor of two。

But now we have 32 R dollars because we're saving2 R per insert。

We do the resize and the rehash that costs R dollars per binding， so that's $32 r and look at that。

We had exactly enough money saved up to pay for that entire resize and rehash operation。

Our account balance is now back down to0。Well， what happens the next time all of this repeats。

 Suppose we insert another 32 bindings。 So we've got 64。 Now。 The load factor has just hit two again。

Now we need to do another resize and rehash， so we've got to pay $64 R to pay for that resize of rehash。

 but that's exactly how much we have saved up again because we saved 2 R per insertion。

 and so 2 times 32 times R is 64 R。Would you look at that？

We have come up with a way to pay for the resize operation in advance by storing away some credits to be spent later on when we need them。



![](img/dd13d90f07923cca5a45e738e73941a5_9.png)

This is a budgeting problem。When I was a grad student， I loved sushi。

 but I didn't get to eat it very often。 it costs a lot of money to eat sushi。So， you know， Monday。

 Tuesday， Wednesday， Thursday， maybe I ate a lot of ramen noodles。 I did。 I liked ramen。

 and then I had saved up enough money by Friday to pay for some sushi together with some friends。

It's the same idea as we just did for hash tables on those frequent cheap operations， the inserts。

 we save up a little extra money so that by the end of the week， by the end of all of the insertions。

 in other words， we have enough money to pay for that wonderful sushi dinner or that expensive resize operation。



![](img/dd13d90f07923cca5a45e738e73941a5_11.png)

So here's the idea of this kind of analysis。We analyze the efficiency。

 not just of an individual operation， but of a sequence of operations。

So that we can use a kind of budgeting model to pay for those rare expensive operations by setting aside a little bit with each one of those common inexpensive operations。

😡。

![](img/dd13d90f07923cca5a45e738e73941a5_13.png)

With that kind of analysis， the find operation for hash tables that's still expected constant time。

But， insert。Well， that can be what we call amortized， constant time。

The amortized here is a financial term， and it basically means the kind of budgeting that we're doing here by setting aside money to pay for expensive operations with each one of those little cheap operations。



![](img/dd13d90f07923cca5a45e738e73941a5_15.png)