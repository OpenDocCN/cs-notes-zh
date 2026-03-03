# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P79：04_01_02_应用-最优缓存.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/197aa144a2b914d212618bd0b2aae508_0.png)

So what are greedy algorithms good for Well， it turns out they're well suited for a number of fundamental problems across different domains of computer science and to wet your appetite for the many examples that we're going to see。

 I want to begin by discussing the problem of optimal caching。

The punchline of the lecture is going to be that a natural greedy algorithm in fact。

 minimizes the number of cash misses over all possible ways of managing small， fast cash。



![](img/197aa144a2b914d212618bd0b2aae508_2.png)

So what is the caching problem well on the one hand there's going to be a big but slow memory which you can think of as holding everything you might be interested in。

 but then there's also going to be what we call a cache and so this is a much smaller memory to which access is much faster。

So this situation comes up all the time across different domainance computer science， architecture。

 operating systems， networking， just to mention a couple of really obvious examples。

 you could imagine the small fast memory being something like an L2 cache and the big slow memory being main memory。

 or perhaps actually main memory of the fast memory and the big slow memory would be disk。

Now your task in the caching problem is to process what we're going to call a sequence of page requests。



![](img/197aa144a2b914d212618bd0b2aae508_4.png)

So a page request just means that the client wants to access something in memory and it's guaranteed to be in the big slow memory。

 but if it's not already in the small fast memory， then you got to bring it in。

 you got to put it there for the subsequent access。



![](img/197aa144a2b914d212618bd0b2aae508_6.png)

The algorithmic aspect of the problem enters the picture when there's a cache miss or also known as a page fault。

 that is when there's a request for some data which is not already in the cache。

 when that's the case you have to bring it into the cache and the design question then is。

 what do you evict from the cache in order to make a room for this new piece of data which you have to bring it？

So to illustrate the issues， let's look at an extremely simple example。

 a cache that just has four slots for pieces of data。

Let's assume that initially the CA is seated with the four pieces of data， I'll call A B， C， and D。

 Now， remember the input is a sequence of page requests。

 so these are requests for different pieces of data。Now， when a new request comes in。

 you're basically sitting there crossing your fingers that what's been requested is already in the cache。

 So， for example， if the first request comes in for the piece of data marked C， you said good。

 we're good to go。 It's already in the cache go ahead and access it。 Similarlyly。

 if the next request is for D。 you don't have to do anything。

 The good times role and D just gets accessed directly。

 The problem arises when something is requested that's not in the cache。

 So let's say the next request is for the data item E。 Now， remember。

 you have to bring E into the cache。 And of course。

 you have to evict one of these four pieces of data to make room for it。

 And your algorithm has to decide which getting to get rid of A or B or C or D。For this example。

 let's assume that we evict A to make room for E。Assume further that the next request that comes in is for a new piece of data F。

 again， it's not in the cache， so we have to evict something to make room for it。

 Let's assume we get rid of B in order to bring in F。And now an unhappy situation。

 but something that could certainly occur is we get a request for something that used to be in the cash。

 but which we have since evicted。 So， for example， if the next request is for a， then we're stuck。

 it's going to be another page fault， we have to evict something to bring in A。 and similarly。

 if there's a B， again， we're paying the price for evicting B to make room for F in the past。

So in this example， with these particular choices for page evictions， we incur four page falses。Now。

 the first two that E and the F， there's nothing we could have done about it。

 We were given a cash that initially did not have ENF， and then ENF showed up。 Well。

 what are you going to do， You're going to miss no matter what。However。

 two were caused by our unfortunate eviction decisions earlier on to evict A and B only to find them requested just after eviction。

And with 2020 hindsights we can conclude we really should have evicted C and D。

 not A and B to make room for ENF。So the point of this example is to illustrate first of all the caching problem。

 how it works。 You have this small， fast memory。 It can't contain everything at once。

 And so you have to sort of manage the cache and evict things to make room for stuff as it gets accessed。

 That's the first point of the example。 The second point is to illustrate there's really two types of cash misses or page faults。

 There's the ones which know really you can't do anything about， no matter what algorithm you use。

 you're going to suffer those faults。 But then depending on the eviction algorithm。

 you may be able to avoid some of the cash misses that you would incur with an inferior algorithm。

 So now the obvious question is how well can we do， What's the best algorithm。

 How do we minimize the number of cash misses suffering only the ones that are inevitable。



![](img/197aa144a2b914d212618bd0b2aae508_8.png)

So this question was given a very elegant answer by Bladi back in the 1960s。

 and I'm going to state the answer as a theorem， it's a theorem we're not going to prove for reasons I'll discuss in a second。

 but what the theorem says is that a natural greedy algorithm is an optimal algorithm for the caching problem。

 that is it minimizes the number of cash miss over any way you might think about managing the cache。



![](img/197aa144a2b914d212618bd0b2aae508_10.png)

And the natural greedy algorithm that is optimal is called the furthest in the future algorithm。



![](img/197aa144a2b914d212618bd0b2aae508_12.png)

So what is the furthest in the future algorithm， Well， it's exactly what you'd think it would be。

 It's basically what seems like a good idea at the moment you have to perform a eviction from the cache。

 Basically， you want to put off judgment day， you want to put off the regret of evicting this particular piece of data as long as possible。

 when are you going to regret evicting a piece of data。

 Well it's when it gets requested next So if you have four things in the cash。

 know is one is requested next， ones requested in seven time steps and one's requested in70 time steps。

 that's the one you want to evict now because it'll take the longest until you actually regret that eviction So for example。

 in the example on the previous slide， you can check that the furthest in the future algorithm。

 It would in fact evict the ones you want to evict A and B。

 not the ones that we evicted in the example C and D。Now， at this point。

 many of you are probably justifiably scratching your heads。 You're wondering， you know。

 why is this useful。 It doesn't seem like this is what we wanted。

 The objection to this result being that the furthest in the future algorithm is clairvoyant。

 Its very definition assumes that you know the future。

 It assumes that at the moment that you have to make an eviction。

 you're aware of when each of the pieces of data in the cache will be requested next。

 But if you think for a minute about the motivating applications for studying the optimal caching problem。

 This assumption just doesn't hold。 you simply do not know the future。

 you simply do not know when each of the pieces of data and your cache will be requested next。

 So this algorithm is not defined。 It is unimplementable。 Despite that。

 this is still an extremely useful result to know why。



![](img/197aa144a2b914d212618bd0b2aae508_14.png)

Well， two reasons。 first of all， this unimplementable algorithm can nevertheless serve as a guideline for practical implementable algorithms。

 For example， it naturally motivates the LRU or least recently used， Caching algorithm。

 So what you do in the LRU algorithm is instead of looking for in the future。

 which you can't do generally， you look in the past。 and you say， well。

 let me guess that whatever has been requested recently will be requested again soon。

 whatever hasn't been requested been requested for a long time。

 will continue to not be requested for a long time。

 So that says as a proxy for the piece of data that's going to be referenced the furthest out in the future。

 you look for the one that was most recently referenced the furthest back in the past。

 So that's the LRU algorithm。 And as long as data exhibits what's called locality of reference。

 meaning whatever is being requested a lot in the recent past is also going to be what's requested in the near future。

 then LRU is going to approximate furthest in the future。 And indeed， LRU is in many。



![](img/197aa144a2b914d212618bd0b2aae508_16.png)

In many applications， the gold standard amongst practical implementable caching algorithms。

The second reason this theorem is useful in practice is because it serves as an idealized benchmark。

 a hypothetical， perfect scenario against which you can compare your latest and greatest caching heuristic。

So for example， maybe you have a caching application and you start by implementing the LRU least recently used caching algorithm then as a sanity check。

 you probably want to go back later once you have hindsight。

 you look at the last few days of traces of logs of page requests and you say how well did we do。

 Let's look at how well our caching algorithm LRU did and let's look at how well we would have done had we know in the future。

 and hopefully you're just a few percent away， and then you can conclude that yes， indeed。

 the data seem to have locality reference。 Yes， indeed。

 LRU is doing almost as well as if we know the future and we can proceed。 On the other hand。

 if you go back through the last few days of logs and you find that your caching algorithm is doing much worse and furthest in the future。

 then it's back to the drawing board with respect to your caching algorithm， You should work harder。

 understand the data better and come up with a smarter heuristic。

So for almost all of the greedy algorithms that we cover in this course。

 I'm going to explain to you why they are correct。 I'm going to prove it rigorously。

 This algorithm is an exception。 I'm actually not going to prove this theorem for you。

 The way it works is by what's called an exchange argument again， you may not have seen any examples。

 but you will soon but the exchange argument to prove belate's result， as far as I know。

 it's pretty tricky， believe it or not， even though the algorithms natural。

 you might think this result feels a little self-evident， try to prove it rigorously， not easy。

 not easy at all。Indeed， if you look at a textbook and say operating systems or a field like that。

 generally， you'll see a description of this algorithm， you'll see the claim that it's optimal。

 but you won't find the proof。 Some algorithms， textbooks， for example。

 algorithm designed by Cl Garddo do include a proof of this theorem for those of you that are interested。

 I challenge you to prove it yourself without looking it up on the web or in a textbook。

 I think if you try to prove it， you'll appreciate the subtleties that come up in understanding whether greedy algorithms are correct or not。

 In the best case scenario， I would love， love to see a simple proof of this theorem。

 something that I could explain in a class like this and say five minutes or less。

 that would be amazing。😊。