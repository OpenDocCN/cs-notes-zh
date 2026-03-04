# 【计算机体系结构】普林斯顿—中英字幕 p55 54_04_write-buffers -BV1ii421D7WR_p55-

![](img/606bc0c0869e3eef0042aca76d6e2354_0.png)

So that's the our first optimization technique。 Let's， there's no questions。 We can move on to our。

Second optimization technique。Your book lists 10 optimization techniques。 We're only going to cover。

 I think，7 of them between。Today， in next lecture， because I think some of them are not actually that important。

 but we're also going cover some other ones， which I think are important。Okay， so。

Next thing we're going to look at。 The next optimization we're to look at is。How to deal with。Hits。

 or excuse me， how to deal with。Read misses in the cache。That。

Have some data there that needed to get kicked out of the cache。So here we have our CPU。

Oh one data cache。Our next level of cache here will say a level L2 cache or maybe main memory。

There's something in this cache at a particular line。And。It's dirty in the cash。

So the dirty bit is set， it has state we cannot throw out。We do a read。

And El least is that same location。 And we need to evict that line。 or create a victim。

In a naive implementation， we'd actually have to sit there and wait for all that data。2。

 go out to main memory while we go get sort of the next。

While we go to do the read and get the data and fill it in。Okay， that's， that's。

 that's not very good。 We sort of have to wait for this evicted， dirty line。嗯。

We'll talk about that in a second。So the processor could be installeded， wit on rights。

One thing you do is actually have the read misses。Go beyond the rights， sort of pass the rights。

And pass the rights going out to the unified L 2。 But one of the problems here is you don't have that many ports onto this unified L 2。

 You really only have one port out here， we'll say。So youve either have the， the load。

 sort of pass it。But thing you have to do this little dance that when the read data comes back or the load data comes back。

 you need to have a place to put it。So either at that point， you might need to wait for it to go out。

To main memory， Er go out to the next level of cache。 So you can't really get around this。

 So you can say， oh， I'll try to get my load out early and just sort of。Worriry about it later。Yeah。

 but that that doesn't work if that。Load hits in your next level of cash。

 You need to access the next level of cache， and you're waiting for this data to go out because you need some place to put it。

So the solution to this is we put a little buffer between our L 1 and our L 2 our L 1 and our main memory。

 And this will hold。Rights or victims that go out。From the L1 to the L2。

And now we have some place to put the data。So if we wanted to do this fast。

 we'd actually do the load。 We'd miss in our L1 cache。 We'd send that request out to here。

 And then instantaneously， we would start evicting the line。Into this buffer。

And the reason we can't invict it here is because the load's actually using that that data right now。

 or it's using the L2 cache， we'll say。But we have some place to put。The victim data。

 And when the load comes back， we can put it into the L1 data array。

So this bringss up a whole bunch of problems。Biggest one being。At some point。

 you actually need to transition from the right buffer into the L2 cache。嗯。You can do that。

If you have extra time。 So you just have some circuit here checks。But then comes the question of。

 if you need to do this a second time， what happens。 Your second。

 let's say load that has to create a victim。 and this buffers full。What do you do。

 Well you can just stall。And wait， that's a pretty good option。

So the this kind of what you're saying here is the probability that you have two victims generated in very short period of time is low。

And。This is actually a scheme that people do use。They don't do anything special。

 And the first victim that gets generated goes into the rip buffer。

 The second victim gets generated just stalls the pipe。That's okay。You can have higher performance。

If。You can have the subsequent read， basically。Go beyond the right buffer here。

And start actually doing something in the memory system。And if you want to do this。You need to。

 just like what we did in the previous example， you're going to have to check this ripe buffer to see if the day is there。

And that introduces complexity because now your data can be。Here or here or even farther out。

 So it's just more places to check。Okay， so that's like the first half of the rip buffers。

The second half of a rip buffer， why we want to put a rip buffer。Is if we have a right through cash。

So we've been talking about right back caches， which introduce victims。

But if you recall a right through cache， every single store that happens。

Gets stored into the data cache， the low level L 1 data cache。

 And it also gets re into the next level of cache。 we'll say， because it's writing through。

 So let's say you have right through from the L1 the L2。

And one of the challenges with this is you might not have enough bandwidth into the L2 cache。

To basically take in every single store that occurs。

So the solution to this is you actually put a right buffer here。

 which will sort of buffer up some of this extra store bandwidth and。

We'll introduce a notion of a coalescing right buffer。So， this is a。

Extra addition to a ripe buffer here。That'll actually merge multiple stores to the same line。

So let's say you have a store to address。5。And a store to address six with a right through cache。

You don't want to actually have to write sort of two full cache lines out to the L2。Instead。

 what I people do is they have coalescing ripe buffers。 So there's one ripe buffer here。

ItMight have multiple entries that holds a whole cache line。

And that first store will push the entire cache line out into here。

The second store will try to push the whole cache line out。

 but it'll notice it's for the same address that it already has in it。

 So actually merge the two cache lines into one location。

 And what this does is it actually decreases the bandwidth that you need at the L2。

Because it's very common in codes to write sequential addresses。So it's very common to， let's say。

 you're adding two arrays， the destination array。You'll actually just be writing address after address after address。

And you don't want to actually have to go fire up the L2 for every single。Store that you do in that。

Aray operation。If you have a right through cash， so you can put a coalesing right buffer here to to save bandwidth into your。

L2。So this this is our sort of second technique is。Having this rip buffer。Okay。

 so what does the right buffer do。Does it decrease our mis rate。Cashs are the same size。

Sociivity is the same。Probably not going to change our mis rate。Mis penaltyal。Okay。

 raise your hand here。 Who thinks this affects the mis penaltyal。Some people raising their hands。

I think we should probably all be raising our hands because that was really what we were trying to do with this whole right buffer is to reduce the miss penalty。

 And the reason this reduces the miss penalty is when that read misses in here。It。

 it doesn't need to wait for the right to occur of the background data or the， the victim data。

 Instead， it can just。Have that happen in the background。This also doesn't affect our hit time。

 It may actually help our bandwidth。 The reason it doesn't affect our hit time is our L1 cache just will still work the same way it worked before。

 You still can do loads and stores against that。 And if you hit， it's fine。

 So it' only affects miss sorts of things。Bandth， like I said， if you have a write through cache。

 this might actually。Effectively give you more bandwidth if you have a coalescing rights offer。



![](img/606bc0c0869e3eef0042aca76d6e2354_2.png)

![](img/606bc0c0869e3eef0042aca76d6e2354_3.png)