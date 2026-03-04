# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P141：-141-Theory of Amortized Analysis Chap8 Video 25.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've seen two examples now informally of how to use amortized analysis with hash tables and two list queuees。

Let's talk a little bit more about the theory behind it。So with amortized analysis。

We analyze the actual running time of every operation。



![](img/bcf50191649d0a7ac1ae9be45a58424a_1.png)

This is just the normal kind of efficiency analysis that you've learned already in 1110 and 20110 and in the other courses。

 Nothing changes about that with amortized analysis。

 We're still interested in figuring out what the actual running time of each operation is。



![](img/bcf50191649d0a7ac1ae9be45a58424a_3.png)

But then on top of that， we layer the notion。Of a bookkeeping trick， essentially。

We define an amortized cost for each operation。 We had to that。

 That comes out of our own imagination of what we want that amortized cost to be。

But we have to be right about it。In particular， we need to prove that the amortized cost is a conservative bound on the actual cost。

So suppose you have a sequence of operations。What you really want to show is that if you take the sum of the actual cost of every operation in that sequence。

😡，Well， that's actually going to be bounded from above。

By the amortized cost of the entire sequence of operations。

So the amortized cost is always worse than the actual cost is what you're trying to prove there for the whole sequence。

That's what it means for the costs to be conservative bounds。

Means you are overestimating in that amortized cost what the actual costs are going to be。

 It's important to get it wrong in that direction so that in the worst case。

 we're overestimating the cost of operations， not underestimating the cost。😡。



![](img/bcf50191649d0a7ac1ae9be45a58424a_5.png)

![](img/bcf50191649d0a7ac1ae9be45a58424a_6.png)

Let's return to our example of two list queuees。So by actually analyzing the code。

 the actual cost of an in queue is going to be one because we have to cons on to a list。

The actual cost of a DQ is either going to be one because we have to take the tail of a list。

Or it's going to be one plus we discovered now the front is empty。

 so we have to reverse the back that's going to be the length of the back in order to do that reversal。

So that we get by looking at the code。Now from our imagination。

 from being creative in our bookkeeping， let us define the amortized cost of NQ to be 2 and the amortized cost of DQ to be what。

So what we're saying here by Fiat is that we're only going to pay one for a DQ ever。

But we're going to pay twice the normal price for any N queue operation。

So then what we need to do for any sequence of operations is to prove that the total amortized cost is bigger than the total actual cost。



![](img/bcf50191649d0a7ac1ae9be45a58424a_8.png)

That's hard to do for all sequences。Here's one sequence we could do it in the concrete floor。

 supposeupp we did four inqs followed by four Dqs。 Well， each one of those ins actually costs one。

 but we said that its amortized cost would be2。Each of the DQs takes a different amount of time。

 the first DQ takes four because of the reversal， the rest of them only take one。

But we said that the amortized cost of every single one of them was going to be one。

So if you add up all of those actual and amortized costs。

 you'll see that the actual cost is less than or equal to the amortized cost。

 and that's what we want。But it's not enough just to do it for one particular sequence。

 we need to do it for all possible sequences。

![](img/bcf50191649d0a7ac1ae9be45a58424a_10.png)

That gets a little messy。In fact， it's kind of hard to analyze all possible sequences of operations。

 I'm not saying you couldn't do it， but mathematically， it's not fun to do。



![](img/bcf50191649d0a7ac1ae9be45a58424a_12.png)

![](img/bcf50191649d0a7ac1ae9be45a58424a_13.png)

It's a lot easier if you can analyze each operation individually instead of having to think about the whole sequence。

😡。

![](img/bcf50191649d0a7ac1ae9be45a58424a_15.png)

![](img/bcf50191649d0a7ac1ae9be45a58424a_16.png)

Amortized analysis comes with two techniques for doing that。

And they are known as the banker's method and the physicists'。



![](img/bcf50191649d0a7ac1ae9be45a58424a_18.png)