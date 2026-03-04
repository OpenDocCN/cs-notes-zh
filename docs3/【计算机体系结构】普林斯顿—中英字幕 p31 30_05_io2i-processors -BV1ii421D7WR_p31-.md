# 【计算机体系结构】普林斯顿—中英字幕 p31 30_05_io2i-processors -BV1ii421D7WR_p31-

![](img/9b62d64cca6392a0b66de347933b68a9_0.png)

In order issue， out of order。呃。As to me。In order front an out of order issue。

 out of order right back and it order commit。 So the middle portion of the pipe here is all out of order。

 And then finally， we commit in order。And we fetch an order。

So this has all of those structures that we had before。It's sort of the union of everything。

 We have a issue queue。 We have a future store buffer， we reorder buffer， physical register file。

 scoreboard and architectural register file。 This requires us to have everything。

And we can start thinking about。What this does to performance。So I'm。

 I gonna to push through here because I only have two more slides and。

The state we get lost otherwise， O， so。Let's， let's see some interesting things happening here。So。

 we have。Out of order issue。 So we can see this ad here issuing before this other。

 before this multiply。That's pretty cool。Ignore this bottom for a second here。嗯。We have。

That same problem sort of showing up here。 We have this right happening。

But even an out of order issue processor。This should be able to be pulledback， as I said before。

But it doesn't， because。At this point， you'd have a right hazard。

 you'd have a hazard on the right back of the register file。 something similar。

 If you try to issue here， you'd be ising two instructions at the same time。

 So this starts to be a problem。 So it actually ends up getting pulled out。

 interestingly enough the performance of this is is not a whole lot better than what we had before。

 if you sort of like cut it here were at 15 cycles。

 the commit gets pushed out far because you have to commit in order。

 But this fixes a lot of problems that we had in the in order fetch out of order out of order out of order because we can have。

Precise exceptions at the end of a pipe。 We can have out of order issue， out of order， execute。

We still do in order fetch because that's kind of the semantics of programs。So。Let's。

 let's take a look at。Let's say we had the ability to do double issue， but not double execute。

How does this change， We actually that changes this to this diagram。And as you can see here。

 we actually have eye here and I here in the same time period。

 So we've pulled that back one and that that。You would think that would actually help。But， you know。

 so we don'， we don't have a right conflict。 Everything is still sort of okay here。

 but the commit still happens at the same time。So that's not always， always as good as you think。

 In reality， what you want to start thinking about is having。Out of order and with。So。

 here we have a。Out of order two wide superscalealar， what we showed before in order fetch。

Out of order issue out of order right back and in order commit。

And we can see is we actually are fetching two instructions at a time。

 decoding two instructions at a time， issuing two instructions at a time。 And this。

 this can actually help a little bit。But you still have problems。So here were just gonna have。

 we can only， we'll build a issue tube， but we're not gonna have two A L Us。

 We're gonna have the same sort of back end of the pipe。

 And what we start to get limited by is we end up with sort of execution resource bottlenecks here。

So next time we're gonna start talking about how to sort of add multiple AUs。

 and you can sort of pull this earlier。 and maybe even have two multiplies or something like that and try to remove some of those complexities。

 But what's nice about this is if you have double issue。



![](img/9b62d64cca6392a0b66de347933b68a9_2.png)

Out of order right back。You know， these ad instructions that are not dependent on these malls at all can just happen。

And that's really nice。Okay， we're going to stop here for today。



![](img/9b62d64cca6392a0b66de347933b68a9_4.png)