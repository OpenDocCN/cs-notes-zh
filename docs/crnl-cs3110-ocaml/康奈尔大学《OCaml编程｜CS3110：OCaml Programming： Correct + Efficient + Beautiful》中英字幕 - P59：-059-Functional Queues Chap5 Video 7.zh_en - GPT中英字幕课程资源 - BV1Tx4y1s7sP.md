# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P59：-059-Functional Queues Chap5 Video 7.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's implement functional cues as lists， the first element of the list will be the person。

 if you will， at the head of the queue， and the last element of the list will be the person at the end of the queue。



![](img/850de436278d5dfdb1abb1e150bfcff7_1.png)

The type I'm using to represent the Q， alphapha Q is just a synonym for alpha list。

The empty queue is the empty list。To Nq an element。

I use the append operator to put that element at the very end of the list。Now that is linear time。

Which of course makes me sad， I'd rather not have a linear time in queue operation。

 We'll return to that in a second。Peak and DQ should look familiar from our stack implementation。

 They're basically doing the same thing。 Peak gets the first element of the list。

DQ gets the rest of the list。One difference here is that I've chosen。

 instead of raising exceptions to return options， I did this just for sake of example。

 we could also do the same thing with stacks。Here I'm returning none if there is nothing in the queue。

And I'm returning some of the appropriate return value if there is an element in the queue。

 Let's go back to that linear time operation。The problem is that my representation of cues as lists means that if I want to put somebody at the end of the queue。

 I have to traer the entire list to get there。Wouldn't it be nice if there were more efficient way to do it？

There is one， and it turns out it was invented by a PhD student of Professor Gs back in 1981。

Let's code it up。We're going to represent a queue with two lists。😡。

The front of the queue and the back of the queue。So there's a kind of arbitrary dividing point in the middle of the queue that we're making here。

The front of the Q is all of the people in the queue in the right order。

The back of the queue is the rest of the people in reverse order。

Let me write a comment to make that clear。So if the front of a queue contains two elements， A and B。

 and the back of the queue contains three elements， E DC in that order。That represents the Q， ABC， D。

 E。A is the first person in the queue， B is the second person， C is the third， D is the fourth。

 E is the fifth。That's the clever idea that enables an efficient implementation。😡。

When I get to this point in implementing peak， there's a bit of a tricky issue。

Suppose the front is empty and the back， well， what about the back？If it's empty。

 then the queue is definitely empty， but what if the back is non empty？

I would end up having to write separate pattern matches to handle these cases。

One simplifying assumption I could make is to instead require that if the front is empty。

 then the back must also be empty。 That guarantees that any time we want to check the front element of the queue or remove it。

 it must be in the front field。 It could never be in the back field。

So let's add a comment to document that decision。This will simplify the rest of our implementation。

Now， when I want to peak to get the front element of the Q out。

 the only thing I have to do is look at the front field， I never have to look at the back field。

Let's just pause here if I'm inqueuing an element。😡，And the front is empty。

 then I know by the assumptions I've already made that the back is empty since this is a totally empty queue at that point。

 where should I put the element， should I put it in the back or the front of the queue。Well。

 I made the decision it would always be in the front part of the queue， so that's where I put it。

If the queue is non empty。Then all I need to do since this is going to be the newest element to the queue。

 it needs to be at the end， I can put it。At the head of the back field。

I put it at the head because remember， the backfield is kept in reverse order with respect to the order people joined the queue。

So the last person who joined the queue can be put at the front of that back list。

What's great about this is this is now a constant time operation。

Because all I'm doing is coning an element onto the beginning of a list。

 which as we know is constant time。Let's pause here in our implementation of DQ。

If the queue is empty， then I return none。But what if the queue is non empty？Well。

 the usual thing I would need to do then to deque someone from the queue is just to take them off the front of that front list。

So as long as there is a head element of the front list， I just remove it。

That's a constant time operation as well。Now there is one tricky issue remaining here。

When I remove the head element of front。Front might become empty。

Because tea might have been the emptyt。Now， I made the decision earlier that if front is empty。

 then back must also be empty。I might have accidentally violated that invariant at this point。

So I've added a pattern match now to handle that case where the front just has a single element in it。



![](img/850de436278d5dfdb1abb1e150bfcff7_3.png)

What should I do after decoqueing that single element？Well， there might be some elements in the back。

I could make those now the front of the queue， I just have to reverse them so that they're in the proper order。

😡，So the front becomes the reverse of the back， and the back is now empty。

 What's the efficiency of this Dq operation。It's going to be constant time。

 except in that rare case where the front list gets exhausted and we have to reverse all of the back elements。

Later in the semester， we'll study something called amortized analysis that will enable us to conclude that。

 in fact。The efficiency of this really is constant time because the reverse operation occurs so infrequently。

Isn't that a neat implementation of cues next time you see Professor Gs tell him how much you enjoy it？

