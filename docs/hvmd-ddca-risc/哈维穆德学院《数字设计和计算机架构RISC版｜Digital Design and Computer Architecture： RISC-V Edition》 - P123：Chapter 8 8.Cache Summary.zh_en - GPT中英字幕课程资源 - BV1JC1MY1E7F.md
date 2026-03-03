# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P123：Chapter 8 8.Cache Summary.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/fce1c5c9ee579d8903f83b36fe8bef48_0.png)

So here's a quick recap of caches， what data is held in the cache。

 recently used data using temporal locality and nearby data， spatial locality。😊。

How is data found while the set is determined by the address of the data supplied by the processor。

And then the word within the block is also determined by the address。In Associative caches。

 data could be in one of several ways。What data is replaced。

 the least recently used way in a set is replaced。So here's a graph showing miss rate trends。

 so you can see the cache size on the bottom， it's increasing to the right and then we have our so this is in kilobytes。

Increase into the right， and then we have our missrate type。And overall miss rate。Going up。

 so you can see miss rates， some typical miss rates of cashs。 you know。

 this is 10% risk rate is relatively high miss rate for a cash。

 and then this is going down to a 1% miss rate down in here or below 1%。

So as the cache size is smaller。You can see that as we increase the number of ways。

We're going to get rid of our。Our conflict messes。Okay，And so conflict misses are shown up here。

In those different colors and so if feel one way our direct map cache。

We're going to have conflicts but we to a two way cash。We're going to get fewer conflict misses。

For a given size， for example，s say an 8 kilobyte cash。 you can see that by going from one way。

The two way。And then， you know four to eight way doesn't helps us a little bit。

 four way helps gives us a little bit of decrease in our miss rate but going to eight way did not。

It did not reduce the number of compulsory， excuse me have conflict misses。

But you can see these capacity misses down here as we get our。Cash size to be larger。

 those capacity misses go down。And then compulsory misses。

 you can barely see it because they're a very small number of percentage of the miss rate。

So bigger caches reduce capacity misses and greater assoativity reduces our conflict misses。

And here's some missrate trends with block size， so again for spatial locality。

 so increasing our block size from know 16 bytes to 64 bytes to 256 bytes。

 you can see that increasing and then we'll see what the missrate does and this is showing for different cash sizes。

 so4 kilobyte cache up to a 256 kilobyte cache。😊，So for smaller cash sizes， for example。

 let's look at this4 kilobyte cash， you can see that increasing the block size helps somewhat。

 it reduces our miss rate。😊，And， you know， a tiny bit more as we increase it to 64 bytes。

 but it actually goes up after we increase it even further。

And what's happening is we're making the block size so big that we're actually increasing our conflict misses because of that。

But for these larger cash sizes。64 kBte and 256 kBs。 We can see a decrease in risk rate with our。

Spatacial locality， but not much of a benefit after 64 kilobyte block size。So multilevel caches。

 we can have a level one cache， the one that we've been talking about。

 but we can also have multiple levels， level two and level three caches are level two caches are very common and level three caches are not uncommon in today's systems。

So the lower level caches or the larger caches are going to have lower miss rates。

 but longer access times。So。We don't want to make the first level cache very large because we don't want to make it too large。

 in fact larger， so that we don't want to make it so large that it takes longer than one processor clock cycle to access it。

So in order to get you know an effectively larger cache size we increase the number of levels。

 so level one is going to be small and fast， typical size is 16 kilobytes。

 one pro clock cycle to access， level two is going to be larger。

 256 kilobytes but take several pro clock cycles to access and then you level three will be even larger with even a longer time to access。



![](img/fce1c5c9ee579d8903f83b36fe8bef48_2.png)

Here's a picture of the Pentium3 die， so you can see what it looks like。

 there's a know the processor is basically all the kind of random type memory logic that you see。

 but then you can see the regularity of the level one caches and you can see the regularity of those memory arrays and the level two cache。

Both of which were on chip。