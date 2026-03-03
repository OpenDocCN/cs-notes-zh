# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P32：Chapter 3 5.State Element 4 D Flip-Flop.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/2b8525b2498d445cd0e82ed3dd7d839a_0.png)

Now let's talk about the last kind of state element that we'll talk about in this chapter。

 this is the D flipflop and you'll understand its name once we talk about it the internal circuit。

 so the D flip flop D again stands for data has two inputs just like the D latch clock and D and here are the symbols。

 the D flip flop symbols。It has D input， and then it has this triangle on the top input。

And that top input is the clock input。 We don't even have to label CLK because that triangle indicates that it's clock and indicates that this circuit is edge triggered。

So this triangle indicates that it's edge triggered。

 And that means that this circuit responds to the edge of a clock。So what is a clock， Well。

 a clock is really more of kind of a。A click， right， But don't call it click。But it goes hell， low。

 hell low。Clock goes 1，0，1，0，1，0，1，0。 And everything in a synchronous sequential circuit is synchronized to the clock。

And so when we get an edge， this is called the edge when it goes from 0 to 1。

 This is the rising edge。The circuit is synchronized with that rising edge。

And so the deep flip flop responds to the edge。Of the clock。

 So here's a bigger view of the flip flop。 And we can also even get write a smaller version of the flip flop where we don't even label D and Q and don't show Q bar。

For conciseness。 But this is still D。 This is Q。 And here's our clock。

And we'll most often use this one symbol for our default flow love just for conciseness。

 right and less clutter in our circuit。So the function is that theD flipflps samples D the input on the rising edge of the clock。

😊，So our our D latch was level sensitive in that whenever clock this input was high。For D latch。

Just D pass through to Q。But now， so this is for our D latch。 That's how that worked。

 It was level sensitive。 When clock was high， D passed through to Hue when clock was low。

Q equals Q previous。But now for our D flip flop。😊，Deep goes passes through to Q only at the rising edge。

Of the clock。 So samples， D， the D。Flows through to Q。Only at the rising edge of。The clock。

And every other time。Is。Memory， cubicle key previous。So again， when clock rises from zero to one。

D passes through to Q， otherwise Q， holds its previous value， or in other words。

 it has memory all other times。Q will only change then on the rising edge of the clock。

 So we have very tight control over when our output Q of a D flip flop is going to change。

And it's called E triggered because it's activated on the clock edge。

And so here we have our picture of our clock and the edges of that clock。

Particularly the rising edges。So how do we build a default float flop。

 The internal circuit is two back to back D latches。 So here we have Latch 1。And here we have Latch2。

And this is the D latch that we just talked about in the prior state element。

And we have clock coming into the rightmost latch。And clock bar， we invert clock and get clock bar。

Going into the leftmost later L1。And this L1 is called the leaderer lottch。And this is the follower。

 the right LT is the follower latch because。The first latch， the leader latch， is going to feed in D。

Into this internal node and one。 And then the follower is just going to follow whatever that latch did。

So let's talk about the timing of how D passes through to Q。Okay， so when clock is equal to zero。

 so here's our clock edge。😊，And we'll look at that。So when clock is equal to zero。

just clock being equal to zero。Well， let's see which one is， is allowing。

 Which one is transparent We' allowing its D。Input through to Q。 Well， L 2 isn't。

 L 2 is what we call opaque or cut off， right， This internal node N one cannot pass through。的 kill。

So clock is zero， L2 is opaque， but L1 is transparent。7 o'clock。Is 0 oclock bar。 remember。

 this is the inverse clock。Clock bar is equal to one。And so this leftmost latch L1 allows。D。

Through to this internal node， right， you can't see the difference of， you know， this。

 this happening on the output Q。 But D is being passed to this internal node N1。Now。

 when clock equals one， so clock transitions from0 to one here and clock becomes one。Well。

What happens？Clock bar becomes0。And now this L2 becomes transparent。

And allows anyone through to queue and。Because we have a 0 on this L1 D latch now。

L1 becomes opaque and does not allow D to its internal node。 So right at this edge。

 right before that edge。D got passed to the internal node N1。 And then right after this edge。

Clock equals one。And one gets passed through。的 you。And that won't happen again， right。

 this kind of passing through。Of D D to Q won't happen again until the next rising edge。

 the0 to one transition。So again， when clock is zero。L1 is transparent， L2 is opaque。

And we allow or it allows D to pass through to N1。And then when clock equals one。L L1。

Is now opaque and N1。 this internal value that was just， just sampled。

 The value of D gets passed through to Q。So。😊，On the edge of the clock， the clock rises from 0 to 1。

 In other words， right， That's what the edge of the clock is。 D passes through to Q。 D is is sampled。

 right， The value of D。Passes through， really， it's in lock stuff， right。

 right before the clock edge。 When clock is 0， D passes through the internal node。

 And then right after the clock rises to one。It gets passed to Q that internal node。

 And so that's why it's called a flip flop， because only one of these。Latches。Is。

 is active or transparent at any given time， And they flip flop their state。 right。

 This one's transparent， this left。Latch is transparent。 And then as after the clock rises。

 now the right latch L2 is transparent and keeps going back and forth。Flip。Fop。

So let's compare how a D latch and a D flip flop work。 So here's our symbol for our D latch。

And it looks very similar to the D flip flop， except that we just have a clock input up here。And now。

 our D flip flop has。A triangle here indicating indicating edge triggered for the clock input。

So here we have our clock and let's start with the latch。

 so we'll start with this leftmost circuit here。We know that the latch is going to be transparent or allow D to pass through to Q only when clock is high。

 So it's level sensitive。 It's sensitive to the level of the clock。And so we can draw， you know。

 we can even draw kind of lines here。 This is where。Q could change。Is when clock is high。

 So only possible time， all other times between that will be， will be memory。 So when clock is low。

The latch will retain itself， its state。Okay， so here we go at time， you know。

 at the time when clock rises。The clock is high。 Q just follows what our D does。

So D is low and then high。And then， clock goes low。And so。

The Dlash just retains whatever state it had right before the clock went low。Now， when。

Clock goes high again。 Like here's the clock going high again。Again， it passes D through。The hue。

Clock goes low， again。And。Just retains that state that they had right before the clock went low。

And then， finally， the last。Time clock goes high。 Well， D is still high， So it stays high， right。

 It just falls whatever D does。Okay， now for our D flip flop。Well。

 deflouff offs a little bit simpler because all we have to worry about is this rising edge。

 we're going to sample D when clock transitions from zero to1 and be careful some people try to include about the falling edges。

 you know don't do that just for rising edges of the clock。And so we can sample what D is。

At those rising edges of the clock。And put that value down for the output or state being stored in our flip fl。

 we have 0。And then we have one。And then we have a one here。And what happens between those memory？

So we get 0， stays there until the next surprising edge goes to one samples D gets a one samples D again。

 happen to be a one again。But between those samples。Memory， it just retains whatever it had。

And so we have to only have to worry about queue changing at these very discrete points in time。

It's only going to change at the rising edge of clock。And so one question is， well。

 what is the value before we get our first edge or the first time clock goes high， Well， we don't。

 we don't know， right we turn this thing on， It could be one， It could be0。 And so we just put。

That kind of value。Could be one， could be zero， we don't know。And so， we put both。Say we don't。

 we're not sure what it is when when the circuit just turns on before we get the rising edge of clock。



![](img/2b8525b2498d445cd0e82ed3dd7d839a_2.png)