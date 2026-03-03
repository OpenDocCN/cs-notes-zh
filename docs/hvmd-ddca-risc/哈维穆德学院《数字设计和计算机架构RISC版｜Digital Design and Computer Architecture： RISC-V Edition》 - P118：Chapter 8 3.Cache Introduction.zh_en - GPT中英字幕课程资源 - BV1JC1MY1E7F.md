# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P118：Chapter 8 3.Cache Introduction.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/b84cd1fd8b1d316830c618da579d2fde_0.png)

So caches are the highest level in a memory hierarchy is shown here。

 they are typically very fast about one processor cycle time。

And they ideally supply most of the data to the processor。 So the processor。

 it appears to the processor that the access time for memory is one cycle。

It usually holds most recently accessed data。So when we design a cache we talk about three questions。

 what data is held in the cache， how do we find data。

 and how do we replace data if the cache is already full and we need to pull more data into the cache。

So in this discussion we're going to focus on loads， but stores follow the same principles。

So what data is held in the cache， Ily， the cash anticipates the needed data and puts it in the cache。

 but it's impossible to predict the future so we can use the past to predict the future。😊。

Using the locality we talked about earlier， temporal and spatial locality。

We use temporal locality by copying newly accessed data into the cache。

 So if we accessed the data recently， that cache is copied that data is copied into the cache so that we have that ready for the next time。

 It's accessed。 spatial locality means that when we access some piece of data。

 we also pull in neighboring data。 that is data in nearby addresses， memory addresses。

So here's some cache terminology and we'll use this through the rest of the discussion。

 the capacity of the cache C， capital C is the number of data bytes from the cache and particularly noteworthy here is to notice that this means the number of data bytes。

We're going to actually be storing some other information in the cache as well。

 but this is for the amount of data that we store in the cash。

Block size lowercase B is the bytes of data that's brought into the cache at once。

 and this is also called。You'll see it referred to as the line size。

The number of blocks capital B is the cache capacity。

 the total number of data bitetes we can store are divided by the block size， lowercase B。

Degrre ofsociivity we'll talk about this is N。 This is a number of sets of blocks in a set and the number of sets is。

Each memory address that maps to exactly know one location in one set。

 so set equals the number of blocks over the number， the degree of associivity， the number of ways。

And we'll talk about both of those last two terms in more detail as well。That's the other terms。

So how is data found data in a cache is organized into sets， so we have S， the number of sets。

 and each memory address maps to exactly one of those sets。

Cashs are categorized by the number of blocks in a set。And so direct map cache has one block per set。

 an Nway set Associative cache also just called an Nway Associative cache has N blocks per set。

And a fully asciative cash is where all cash blocks are in a single set。😊。

So we'll examine each organization for a cash。 This is a， you know。

 kind of toy example to demonstrate the principles， right。

 would never have a cache with only eight words in it。 But again。

 this is a toy example to just illustrate the principles。

So the capacity for these example caches is eight words。Block size is one word of 32 bits。

 and the number of blocks is eight。So here it is written out just you know， in bullet points here。

 capacity eight words， block size one word， and so the number of blocks is eight。



![](img/b84cd1fd8b1d316830c618da579d2fde_2.png)