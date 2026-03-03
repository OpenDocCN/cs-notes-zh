# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P50：Chapter 4 6.Signal Assignments.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Now let's talk about blocking and non blocking assignment and how we assign signals。

 so we've used several different ways and now let's talk about specifically what the differences are。



![](img/a8c6b555e88f70458ce4c1f6a67ebd94_1.png)

So there's a difference between blocking and non blocking assignment。

 so this GS operator is a non blocking assignment that is the assignments。

 the outputs are assigned simultaneously with the others。On the other hand。

 this equals is a blocking assignment， so the assignment occurs in the order it appears in the file。

 So here's an example of a synchronizer。So we have two back to back flip flos。Here， we have our。

Always underscore FF at Po edge clock because we have two statements in here。

 we have a begin and an end。Those are like curly brackets and。Programming。

And so we have begin N1 gets D。And Q gets n1。 So these get assigned。You know。

 I can't draw this at the same time， but right they get assigned at the same time。So。And one gets D。

And Q gets n1 at the same time。However， in in this blocking assignment。

It almost looks the same the only difference is these equal assignments versus the gets。

Assignments are these blocking assignments versus non blocking。So， on this one。And one。Gits D。

 so here's this internal mode N1。And one gets D。So here's clock。

 so still at the positive edge of clock， so that looks the same too。N1 gets D， and then Q gets N1。

So it just says， okay， well， I guess Q and N1 are the same signal。

And it synthesizes into a single flip flop instead of two。Because it's evaluated in a blocking way。

 this statement of blocks， essentially the following statements， so that this statement occurs first。

🤢，And then that statement is evaluated second。And so it turns into a single flip flop instead of what we wanted。

Was two back to back flip flops or a synchronizer。And so let's talk generally about signal assignment。

 synchronous sequential logic we're going to use always underscore FF。At Poage clock。

And the GiS operator or non blocking assignment。And here's an example。Our our flip fl。

This is just the statement of the entire module。For simple combinational logic。

 we're going you use what's called the continuous assignment statement or the assigned statement that's what we've already been using。

 so here's a continuous assignment statement assigned y equals A and B。

So it will continuously to assign why。These values when anything on the right side changes。

But remember， actually what's happening is this is synthesizing into you。Into a gate， in this case。

 in the A gate。For more complicated combination logic we can use。The always calm。

Keyword and blocking assignment， so for example， within case statements or within if else statements。

Important thing is this is hardware so we can assign a signal only in one block of logic。

 So if we have an always statement that assigns Q， for example。

 I can't then go somewhere else and say， oh， assign Q。Equals。Who knows one bit of zero？Well。

 now I've tried to assign Q two different things， right I have Q here and it's getting driven。

By this block。Of logic。And is also now being driven by the second block of logic。

 And so we have contention。You can only assign Q， so this is where people get into trouble when they think of HDLs as a programming language and programming language。

 sure right， assign that variable Q， you know， once and then later you can sign it again。

Not true in hardware in hardware， only a single logic block。Can assign a signal。

So assign a signal in only one always statement or continuous assignment statement。

 you can't have two logic blocks that are assigning a signal。



![](img/a8c6b555e88f70458ce4c1f6a67ebd94_3.png)