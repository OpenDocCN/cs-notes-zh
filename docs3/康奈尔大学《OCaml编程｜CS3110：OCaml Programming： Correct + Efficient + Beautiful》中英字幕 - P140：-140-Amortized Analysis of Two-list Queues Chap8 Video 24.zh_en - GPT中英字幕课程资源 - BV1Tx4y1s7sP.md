# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P140：-140-Amortized Analysis of Two-list Queues Chap8 Video 24.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's use amortized analysis to look at two list cues again。😡，So remember that with two list cues。

 we can abstractly have a cu that had one at its head and then two and then eight all the way at the end。

But that concretely， we broke that queuee into two lists， a front list and a back list。

 The front was stored in order。 The back was stored in reverse order。

So maybe this queue with one through8 in it really was represented by a front queue that had one through three。

 those would be the elements that had been in queued since the front was last emptied。



![](img/03d0a6f1fbef2f15446f42e20c44b30a_1.png)

And the back might have eight through four in that order。

 these would be the recently ined elements that are added to the back。



![](img/03d0a6f1fbef2f15446f42e20c44b30a_3.png)

![](img/03d0a6f1fbef2f15446f42e20c44b30a_4.png)

So we had a representation type， as I've just described， and we had a representation invariant。

Which is that if the front is empty， then the back also must be empty。

 That gave us a unique representation of the empty Q。

 It also guaranteed that we knew where to go to Dque an element。

 We always would be dequeing from the front。 Then if the front turned out to be empty。

 we would reverse the back and install it as the new front。😡。



![](img/03d0a6f1fbef2f15446f42e20c44b30a_6.png)

So what's the efficiency of each of the operations in a two list queue？Well， the peak operation。

 that was just looking at the head element of the front list， that's constant time。



![](img/03d0a6f1fbef2f15446f42e20c44b30a_8.png)

For the NQ operation， we always cons onto the back list， so cons is a constant time operation。



![](img/03d0a6f1fbef2f15446f42e20c44b30a_10.png)

There's one tricky little case there， which is if the entire queue were empty。

 then we would cons onto to the front instead to maintain the repin variant。

 but that's still constant。

![](img/03d0a6f1fbef2f15446f42e20c44b30a_12.png)

What about DQ though？Well， as we just reminded ourselves。

 normally that's a constant time operation because we're just taking the tail of the front。



![](img/03d0a6f1fbef2f15446f42e20c44b30a_14.png)

But in that rare case that the front becomes empty， we've got to do something expensive。

We have to reverse the back and make it be the front。Well， if the front's empty。

Then we've got to do the entire back， so how many elements is that？Let's call it n。

 the number of elements currently in the Q。So in the worst case， DQ is actually big O of n。

 it's a linear time operation because we've got to do something for every single one of the elements that's still in the queue。

😡，Specifically， we have to take it out of the backlist and con it onto the front。



![](img/03d0a6f1fbef2f15446f42e20c44b30a_16.png)

Let's think back to our piggy bank。Suppose that every time we ink you onto the back， we save $1。

Then whenever we get to the point that we actually need to reverse。

 we spend end dollars out of that pickgy bank， crack it open to pay for the expensive operation。



![](img/03d0a6f1fbef2f15446f42e20c44b30a_18.png)

Here's a worked out example of what that could look like。

Suppose we start off with a queue that's completely empty and a bank account that's zero。

Then we in Q1 element， that's going to go on to the front it has to by the weaponin variant。

Then we in queue nine more elements。 All of those are going to go on to the back。

And we save up $9 in the process。Next， suppose we de queue one element。Well。

 that's going to make the front empty， we're not allowed to leave the front empty because of the rapid variant。

So now we need to reverse the backlist that's going to cost us 9， which we pay for。

 that's exactly how much we have in our bank account。Now the front is going to be nine。

And we're going to have a zero account balance again。At this point。

 you know we could go on and do more operations， suppose that we finished by dequeuing nine elements。

 while those would all come off the front， and we would never more touch our bank account balance there。

 it would still stay at zero。

![](img/03d0a6f1fbef2f15446f42e20c44b30a_20.png)

So the efficiency then under this analysis， peak and N Q， those stay constant time。

But DQ is amortized， constant time。It's true， it's still worst case linear。

 but by playing this budgeting trick， this bookkeeping trick， we can say that on average。

 every operation is only costing us a constant amount because we get to spread out the cost of that expensive operation over the inexpensive operations。

😡。

![](img/03d0a6f1fbef2f15446f42e20c44b30a_22.png)

![](img/03d0a6f1fbef2f15446f42e20c44b30a_23.png)