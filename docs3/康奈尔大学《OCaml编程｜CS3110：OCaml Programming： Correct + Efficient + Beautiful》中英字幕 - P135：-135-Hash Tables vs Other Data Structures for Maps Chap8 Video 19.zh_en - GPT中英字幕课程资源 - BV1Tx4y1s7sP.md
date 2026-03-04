# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P135：-135-Hash Tables vs Other Data Structures for Maps Chap8 Video 19.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've finished implementing hash tables， let's take a look back at their performance compared to other implementations of the map ADT。



![](img/7c452c05791d4cb5edeff7b30d7004b9_1.png)

The benefit of hash tables with chaining over association lists is that we have a more efficient find operation。

 instead of linear time， we have expected constant time。

 where I have to say the expected because of the hash function that's in use in expectation。

 a good hash function will distribute keys uniformly over the buckets and therefore keep the expected bucket length to a constant。



![](img/7c452c05791d4cb5edeff7b30d7004b9_3.png)

![](img/7c452c05791d4cb5edeff7b30d7004b9_4.png)

On the other hand， for insert and remove， we have worst case linear time operations。



![](img/7c452c05791d4cb5edeff7b30d7004b9_6.png)

In some of the earlier videos， I said that wrong。 I said expected that was a mistake。

 They are worst case time operations that are linear。For hash tables with chaining。

 that makes them worse than association lists and worse than direct address tables。

What we're going to see next week is a technique called amortized analysis in which we can actually conclude that the insert and remove operations for hash tables are really constant time。

 not linear time。😡，But that's something to look forward to next week。 we'll get there soon enough。



![](img/7c452c05791d4cb5edeff7b30d7004b9_8.png)