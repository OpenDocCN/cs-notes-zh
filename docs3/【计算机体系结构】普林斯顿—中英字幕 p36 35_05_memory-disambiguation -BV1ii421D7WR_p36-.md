# 【计算机体系结构】普林斯顿—中英字幕 p36 35_05_memory-disambiguation -BV1ii421D7WR_p36-

![](img/d8bcc96a409a77211b08ff48636a6a28_0.png)

Let's move on to。Memory disambiguation。So， this is。Kind of the analog。Of。

Read after write hazards through the memory system。Whoops。Okay， we have a。

Basic instruction sequence here。 We have a store fall by load。When can we execute the load？Well。

 that's a tough one。If。The loads not dependent on the store。 We just go execute out of order。

You can potentially even execute the load before the store and out of order machine。

If the load is depend on the store。 So if let's say register 2 is equal to register 4。

Then we're going to have a problem。So what， how， how do we go about trying to solve this。

pU until this point， we。In our pipes， we've said， okay， loaves in stores。Are in order。

Because that that can solve these problems。 So we， let's say we just execute all those in stores in order。

And。We can still allow other instructions to move around it。

 So it's out of order relative to other instructions， but we have in order memory instructions。

 And that's gonna guarantee that we're not gonna have any problems。

But we needed performance on the table here。 We could go faster。

 We could actually execute loads and stores out of order if。Our 2 and our 4 are different。

But we're probably going need some extra structure to do that。Okay。

 let's say look at a conservative out of order。Load， example。So， our， our conservative one。

Let's split。The store into two sort of subparts。And address computation。And the actual data right。

By doing this， we can guarantee。That the store。Because we do address computation early。

We can know that that subsequent load is not gonna alias or we know that R 4 is not going to be equal to R 2。

 and we can go execute the load before the store in this case。

 by splitting the store into two different parts， the actual。

Store portion in the address computation。And。We still need to， unfortunately。

Check every single load against all previous uncommitted stores。

 where we need some structure to go do that。So that's of a kind of a problem。 it's a bummer。

And we're not able to。Execute any load if we don't know the store address of any of the stores before us。

Because we're just not going to know。Whether we can go execute that or not。Okay。

 well could we do one better？Let's start speculating。Because let's guess。The P are not equal。

Let's execute the load before the store。And then， we。Hold off。

Committing the loads and store instructions。 And we do that in order。And if something bad happens。

 So if the registers do equal each other。We have to。Replay all of these instructions。And what's。

 what's annoying is we also have to kill all of the subsequent instructions。

 So anything that was after that load in store， which could have picked up a value from the load in the store。

Or well rather from the load， any dependent instructions of the load。

 we're gonna have to go kill all that。And depending on how precise we want to be。

 we can either try to kill just everything after it or we can try to kill just the selectively the things which are dependent on it。

 It's really hard to track。And， and we have a pretty high penalty here for inaccurate address speculation。

 So if we go and we just execute these two instructions， we put them into the pipe。

 and they were dependent on each other。 We have to roll back a lot of state。So1。

 one sort of heuristic on this is。Was， was done in the Alpha 21，2，64。

Is called memory dependence prediction。 So what you do is you're still going to guess that the loads in the stores do not alias。

But then， later。If you find that the two registers do equal each other。

You're going to squash all the instructions。But then you're going to do something special to that load。

You're recently going to say。That's，'s a wait， wait for the store。 And You sort of put a barrier in。

So that you're not going to get like multiple rollbacks over and over again。

So it's kind of conservative way that when you see that you're roll bulling back a lot。

 there's a lot of thrown away work that you're doing there。 So instead， you can just say， well。

 this load， I think is dependent on that store。 You could potentially even remember that across instruction sequences。

 So if it's always the case。' say this load is dependent on the store。

 You could potentially keep it into your instruction cache or something like that。And then， you know。

 when you go to execute that same load at a different time。

 it's gonna wait for all the stores to complete。 and it's gonna barrier。

 This is kind of a prediction。 It's just a heuristic。

 But it's one way you could potentially not cause that load to always replay。

 And if you have sort of multiple dependent loads or， or excuse me， it loads depend one store。

 you could potentially cause those loads not to have to replay multiple times。But the。

 but the big advantage here is。When you go to reex that load sometime in the future。

You're not going to。Flush the entire pipe。So this is kind of like a branch prediction， if you will。

 It's like this branch。 I've， I've trained the predictor to say that that load usually。

Is dependent on previous store。 So just wait for all the other stores to clear out the pipe。

So it's a cute little trick。Okay， so we're almost out of time。Okay， so speculative loads in stores。

We're going to introduce。A store buffer to hold the speculative state。So， let's take a look。

Very briefly here， I'll flash up what a store buffer looks like。

And then we'll think about it for a second here， so。Here you have your cache。

 your L1 data cache will say。We're going to send all the addresses that go to the L1 cache also to this other structure here。

 which is the speculative store buffer。Inside the speculative store buffer。Theres going to be bits。

 basically saying whether。It's valid or not。And the load is going to check against here。And。

Let's say the data hasn't actually gone into the cache。 It can go pick up the new value here。And。

S bit is basically just gonna to tell us whether it's in flight or not。

 So it's possible that we allocate into here， but the store isn't at the end of the pipe yet。

 we're still calculating the data。 So we need to know that we're gonna get a hit if we get a load out of order。

 and we need go check for that。 And that's， that's really why we have 2 bits here。

And then sometime in the future。🤧嗯。We have to eventually move the data into data cache because this structure will get full。

 We sort of fire enough stores against it。 It's gonna get full。

 So it's probably a good idea to go move that data into the data cache at some point。

 We can do that at our convenience， though。And。If the store aborts， this is important here。

So if the store， let's say， was speculative itself。And。

 and on on the wrong side of a branch or something like that， we just remove it from this table。1。

Interesting thing here is。If the data is in both this buffer and in the cache。

Which one takes precedence。 So the store buffer has the new new values。So we have to look there。

 And then， finally。It's possible to get multiple stores in here， which have the same。Tag the same。

Address。Do let say you're storing to the same address over and over again。And when you go to read。

 you know need to go read the youngest。Value out of there because that's the most up to date one。

So this lookup through here is a little complicated。 You actually need to do it in program order。

Okay， so we'll， we'll stop here for today。

![](img/d8bcc96a409a77211b08ff48636a6a28_2.png)