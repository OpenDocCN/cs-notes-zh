# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P139：-139-The Idea of Amortized Analysis Chap8 Video 23.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Amortized in the dictionary is defined as putting aside money at intervals for gradual payment of debt。



![](img/17abdf1ea58265b455f29319cbfe1ec0_1.png)

And that's what we're doing when we use amortization in efficiency analysis。



![](img/17abdf1ea58265b455f29319cbfe1ec0_3.png)

We're paying some extra， what I'm calling money here for operations。

 it's really just a kind of an accounting for the amount of time we're going to spend on later operations versus earlier operations。

😡，And we use that set aside credit， that kind of like credit for time to pay the higher cost of those later operations。

This is an analysis technique that was invented in 1985 by Slater and Tarin。



![](img/17abdf1ea58265b455f29319cbfe1ec0_5.png)

Bob Tarjan actually has a Cornell history。He won the Turing Award in 1986 with our own professors John Hmcroft。

 who just recently retired。They want it together for fundamental achievements in the design and analysis of algorithms and data structures。

Now， Bob was Cornell CS faculty for one year only 72 to 73。

One time I asked Professor Hopcroft why Tjjan had only stayed here for one year。

 The story he told me was that Bob was really a California boy and he couldn't take the Ithaca weather in the winter。

 so he left after one year of it。

![](img/17abdf1ea58265b455f29319cbfe1ec0_7.png)

![](img/17abdf1ea58265b455f29319cbfe1ec0_8.png)