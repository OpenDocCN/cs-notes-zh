# 【计算机体系结构】普林斯顿—中英字幕 p84 83_01_sequential-consistency-review -BV1ii421D7WR_p84-

![](img/e7f06100639fe0ad5ac3854df65a883a_0.png)

Okay， so let's continue our exploration of。Multi processoror systems or small multi processoror systems。

And we left off talking about concurrency。 And one of the things that we talked about at the end of class or just a recap。

 actually， before we do there， that let's， let's talk about。Sequential consistency again。As a model。

So sequential consistency as a model basically says that you have lots of different threads executing。

And the ordering of the memory references from the different threads could be interleaved， but。

Everyone has to agree on what the ordering is。And all the threads have to agree and see the same ordering and。

The ordering of the loads in the stores and the respective memory references have to be some valid ordering from the thread。

 So you can't reorder within the thread。So if you have two threads and you have， I's say。

If I four fingers here， I need either hand or。For for memory references。

 you can have some interleaving。 You can have some other interle。 You can have that interleaving。

 You have all these possible different combinations of interles。 What's not valid is to have。

My two fingers sort of change order there。 And that is not sequentially consistent。 Having said that。

 we talked about building processors up to this point， which are not do not maintain that order。

 So we talked about out of order processors and out of order memory systems。Which， by definition。

 are not doing this sequentially consistent notion here。And if you want to performance。

 as we talked about， sometimes you want to move loads around。

 you want to push the load up so you can get the operation out to the memory system early。

 kind of push the store down because you haven't computed the result yet and you want to be able to sort of compute the result before you go push it out to the memory system。

 So these things fight against each other， having a strict memory model。

 something like sequential consistency and having good performance。 And in fact。

You're probably not going to find any processor which actually implements true sequential consistency。

Or。I'm trying to think maybe the one of I， I don't want to say no because I'm I have a hunch that the original。

One of the original shared memory processors， the RP3 by IBM， I believe。

 might have had a very strict memory model， but besides that， I don't think it had caches。

 most things do not come even close to this。But we talk about sequentially consistent or sequential consistency as a good model。

 because a programmer likes to think about this。They like to think that when they write some piece of code。

 what they execute happens in order and happens in order relative to every other piece of code happening。

On other threats。So just to recap what this end up what this ends up doing is sequential consistency。

 we， we talked about having sort of ordering between。Loads in stores on the same processor before。

 And you might， you can break that maybe if there are different addresses。

But sequential consistency effectively adds additional arcs in our dependency graph。

 where every memory instruction in one thread is dependent on all the previous memory instructions。

 That's one way to reason about not reordering anything。 So if you introduce all those arcs。

 you're not gonna accidentally break sequential consistency。

But sequential consistency says nothing about dependence from one thread to another thread。

 So there's no arcs crossing between these two threads， so。Hence， you have all valid innerles there。



![](img/e7f06100639fe0ad5ac3854df65a883a_2.png)

![](img/e7f06100639fe0ad5ac3854df65a883a_3.png)