# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P127：-127-Association Lists vs Arrays Chap8 Video 11.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's compare our two implementations so far of map。For association lists。

 we had a constant time insert and we got a constant time insert for directed rest tables too。



![](img/d751f21fbc71461b2299ee44a9808b6c_1.png)

But for find and remove， direct address tables were more efficient。



![](img/d751f21fbc71461b2299ee44a9808b6c_3.png)

They gave us a constant time operation because it was just array indexing and updating。

 whereas association lists potentially had to scan down an end height。 So those were linear。



![](img/d751f21fbc71461b2299ee44a9808b6c_5.png)

![](img/d751f21fbc71461b2299ee44a9808b6c_6.png)

It's not exactly an apples to apple's comparison， of course。

 direct address tables come with the additional restriction that keys must be integers。



![](img/d751f21fbc71461b2299ee44a9808b6c_8.png)

You get a more efficient implementation because of that。😡，In terms of time。But in terms of space。

 you might actually pay more。Because if you create a map with a very high capacity because you want to have some numbers like 1000 as keys。

 but you didn't actually care about all the numbers like 0，1，2， 100， 200， 300。

 any of those small numbers。Well you still had to allocate a huge array to make that happen。



![](img/d751f21fbc71461b2299ee44a9808b6c_10.png)

So there is potentially a space savings that comes along with association lists if there aren't going to be a lot of keys that are bound。



![](img/d751f21fbc71461b2299ee44a9808b6c_12.png)

Association lists， though， are slow in terms of time efficiency。



![](img/d751f21fbc71461b2299ee44a9808b6c_14.png)

They have these linear time operations。

![](img/d751f21fbc71461b2299ee44a9808b6c_16.png)

Wouldn't it be great if we could somehow get the best of both world。



![](img/d751f21fbc71461b2299ee44a9808b6c_18.png)

![](img/d751f21fbc71461b2299ee44a9808b6c_19.png)