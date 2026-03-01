# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p121 15_02_05_切片行.zh_en -BV13E421M7FF_p121-

You can get a slice of a data frame by using a colon。 Here's the format。 In square brackets。

 you provide a start index， colon and index。 The start index is the index of the first value included in the slice。

 and the end index is the index of the last value， not included in the slice。

 and both values are optional。

![](img/9a84501aab608c324424bdfca89ec4d6_1.png)

Let's get the second 100 businesses listed in the data。From the data frame， let's get a slice。

 We'll start at index 100， and the N index will be 200。 We'll run that。

 and we'll see that the start index is 100。 That's the first record。 And that goes all the way up to。

Index 1，99， because index 200 is not included in the slice。

Let's get the name of the last business listed in the data to do that。

 let's get the index of the last record in the data frame。

 So let's get the length of the data frame-1。 That'll be the last index in the data frame。

And then we're going to call that index。Then let's get a slice from the data frame。

In square brackets， the start index will be index that I saved up here。

 That's the last index in the data frame followed by colon。

 And then I'm going to leave out the index。 So this will get a slice from start。

 or I'll say provided start index all the way to end of。Data frame。

And then we'll store that in last business。And then， from that last business。Let's get just the name。

So the last business in the data frame is a sunrise towing， and the index is 599。

Another way to do this is to get a slice from the data frame。 Use negative one as the start index。

 That'll wrap around from 0， and that'll get the last index in the data frame followed by a colon。

 Leave out the optional end index。 So it'll go all the way to the end of the data frame。

 And then from that， get the name directly。A sunrise towing index 599。



![](img/9a84501aab608c324424bdfca89ec4d6_3.png)