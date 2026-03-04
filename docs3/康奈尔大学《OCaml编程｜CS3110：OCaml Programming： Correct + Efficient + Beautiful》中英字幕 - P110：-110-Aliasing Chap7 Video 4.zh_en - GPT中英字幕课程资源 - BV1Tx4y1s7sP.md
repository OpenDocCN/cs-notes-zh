# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P110：-110-Aliasing Chap7 Video 4.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Now that we have references， we can have aliasing。Aliaing is when two references point to the same location in memory。



![](img/38b6035904324bd11eedf6ec6ff840ca_1.png)

So for example， we could create two refs， both initially storing the contenttents 42。



![](img/38b6035904324bd11eedf6ec6ff840ca_3.png)

Bd1 to x and 1 to Y。So now we have two distinct locations in memory。



![](img/38b6035904324bd11eedf6ec6ff840ca_5.png)

If we say let z equal x， z and x are now aliases， they both point to the same location in memory。



![](img/38b6035904324bd11eedf6ec6ff840ca_7.png)

![](img/38b6035904324bd11eedf6ec6ff840ca_8.png)

So if I use assignment to update the contents of x to be 43。

 that simultaneously updates the contents of Z to B 43 because they are the same location in memory。



![](img/38b6035904324bd11eedf6ec6ff840ca_10.png)

Therefore， when I de referenceence Y and Z to add them together， I will not get 84。

 I will get 85 as a result of this code。

![](img/38b6035904324bd11eedf6ec6ff840ca_12.png)

![](img/38b6035904324bd11eedf6ec6ff840ca_13.png)

Let's check that。So， we'll pause here。We've created the two references， bound them to X and to Y。

And created the alias of Z to X。So you can tell that Z has Cons 42。

 you can't really tell from what Ochemel says that it happens to be an alias for x。

 there's no way of knowing that from that output。Now I can update Z or X either one。

And by doing that， I have updated X since it's an alias。I get 85 back， not 84。

 as I would have originally。So what if you did want to tell whether two references were aliases of one another。

The equality operators can help you with that。And now I can finally explain the difference between structural and physical equality in OcaMl。

Suppose you have two refs， R1 and R2。Both initially containing the same contents。

Double equals is physical equality。 It checks to see whether those are quote physically the same location in memory。

So R1 double equals itself because it is the same location as itself。

But R1 is not physically equal to R2。So the negation of physical equality is written exclamation point equals。

They are not the same location in memory， even though they have the same contents that doesn't matter。

 Ph quality is asking， is it the same location in memory？Single equals。

 which is what I've been encouraging you to use so far this semester， is structural equality。

 Think of that as looking at the contents， the structure of a location， not the location itself。So。

 R1 equals R1。R1 also equals r2 because they currently contain the same contents， 3110。But。😡。

ReF 3110 is not structurally equal to Ref 2110， because those two locations will contain different contents。

The negation of structural equality is written less than greater than this kind of diamond operator to indicate inequality。

Most of the time what you really want is structural equality。

 only use physical equality if you really care about whether two references are aliases for one another。

😡。

![](img/38b6035904324bd11eedf6ec6ff840ca_15.png)