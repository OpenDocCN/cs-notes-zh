# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p08 P8 -BV1zNSCBkEgW_p8-

![](img/6c1780667ae8cd0b284e80e958dad167_0.png)

Okay， let'll get started。Yeah， thanks， I think it's good to be this。Problem4。F yes。

State how much time you spent on the pieceet。 it's good I put that in there because I think next pieceet I have to make not as long。

 I was scheming some of those answers。

![](img/6c1780667ae8cd0b284e80e958dad167_2.png)

Yeah， sorry about that。Or 1 B， is that？Yeah。I see。 okay。嗯嗯ん。嗯。And。

 actually there's a way to get a really short answer to 1B。Which诶。

I guess we'll put the description section。😊，呃。Okay。Today I want to talk about online algorithms。

Is this the right grid to be writing out？And this is all about making decisions。You know。

 in the face of。Uncertainty。So I'm going to imagine there's an input which is a sequence of requests。

 you're going to see some examples。And I don't know the future。

 I just know the requests I've seen so far。And based on。

And let's say there are many ways to satisfy this request。

 and I have to make a decision about how I'm going to satisfy it。Okay。

 and I want to make these decisions in such a way that。嗯。

I don't regret the decision like in the future， when I look back at what I decided。

 I don't want to regret things too much， Okay， so we'll see。We'll try to formalize this。嗯。Okay， so。

There。Is some。costst。To making a decision。Cost paid。For making。Say a certain decision。And at the。

End of the day。You have the sequence of requests。Or do you have a scribe， by the way？Okay。

We want to make sure want to save。We didn't。Spend much more than some omniscient being who knew the future at the beginning。

Or much more。Then the best in hindsight。All right， so let's say you're。You know， you're working。

You're working。On Wall Street or something， or you're managing the。

Investment portfolio of Harvard or somewhere else。And。You know。

The amount of money you made this year is。呃。Much less than the amount of money that the person who had your job last year made。

 So now they want to fire you， right， And you want to say， look， it's true。 I made less money。

 but this year is a different year than last year。 You know， this year。

 the best anyone could have made， even if they knew the future。

Is much less than what you could have made last year。

 And I was competitive with the best I could have possibly done。 So， you know。

 you could use this kind of thing to。Save your job。So well okay。

 you can use it for also more real applications， you'll see that later in class。Okay。

 so let me let me。🤧嗯。Let's formalize this a little more。嗯。So。Weirrun。Some algorithm A。

To make decisions。And opt。It is an algorithm。Making。The best decisions。While knowing the future。诶。

And then definition。We say that。Yeah。We say a is。Let's say are competitive。

If for all request sequences。Sequences sigma， which is Sigma 1， Sigma 2。Sigant M， let's say。The cost。

Using A to serve Sigma is at most R times the cost。Of opt to。Sure signal。

 maybe plus some additive term。嗯嗯。ok。And。This。This is called competitive analysis。Okay。

And it was introduced by none other than slater and Taent。Totally different paper。Then display trees。

But the same year。At least the journal versions are the same year。

Can't remember about the conference versions？Okay， so before I。Look at。

 well so today we're going to look primarily at the paging problem。

 I'll define that later in lecture， but before I define that problem I want to give you I guess two toy examples。

Okay。I think if people were in CS 124 with me last semester， I mentioned one of them。

I'll just refresh your memory。Yeah I don't it's okay if you weren't in their last semester。

 you'll see it again。 So one is one classic to examples so to examples。

So one is what's called the ski rental problem。People always start off online algorithms with this thing。

Because it's simple enough to demonstrate。What's going on。So。呃。

The only thing that's unknown in the ski rental problem is M， the length of the sequence。

 So what's going on。 So you imagine that you and your friends are at a ski resort and they didn't tell you how long they want to spend on this vacation。

But you're willing to spend as long as they tell you， okay？嗯。And。

Each day they'll wake up and they'll either say， okay， we're done with this vacation。

 we're going home now。Or they'll say， we want to stay one more day。Okay， and ski。

And if they stay when we're day in ski， you have to have skis to go out skiing with them。

So you can either rent the skis for the day that costs a dollar。Or you can choose to buy skis。

 which costs B dollars。Each day。WeMt either。Rent skis。$1。Or buy skis。That's B dollars。And of course。

 once you buy skis， you never need to run them in the future。

 you can use them on all future days for free。Okay。So the question is， what do you do？

So if you want to look at。Opt Opt knows the future。

 What does that mean here means Op knows when your friends are going to say， let's go home。Okay。

 so what would Op do？Yeah， otherwise rent every day， right， so opt。So Opt says。

Different a number of days。Greateaer than B。Buy skis。Else， rent every day。

RightBut we don't know the future， and we want to be competitive with this。 So what do we do。Yeah。

To us。