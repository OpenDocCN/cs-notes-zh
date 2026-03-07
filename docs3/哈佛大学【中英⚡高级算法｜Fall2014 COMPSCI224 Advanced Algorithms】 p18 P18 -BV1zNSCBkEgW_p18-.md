# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p18 P18 -BV1zNSCBkEgW_p18-

![](img/058ef3137e25ad6168f0c9f1a6c30e81_0.png)

🤧Okay。I think it's so I guess we finished。A lot of stuff on linear programming。

 so I covered simplellipoid into your point。Now I want to sort of transition into other stuff。

So it turns out the thing I'm going to cover today can also be applied for linear programming。

 and I'll show you that， but it's more than just a tool to solve linear programs。

And then once we're done with this， you're just not really going to see solving linear your programs anymore。

 okay？Okay， good， so today what you're going to see is kind of multiplicative weights。s right today。

I'm just curious has anyone been seen multidative weights before？Okay。Okay。

 so or rather I should say。You know， how to know。How to choose。You know which expert advice？

To listen to。So for example， you like to trade stocks。

 there are lots of self proclaimed experts who tell you what to buy so that you make money。

And you're not sure which one you listen to。So you want to。

You want some strategy for deciding which one to listen to， okay。

 and what I'm going to say is going to remind you of competitive analysis。 Well。

 actually first let's just look at competitive analysis。

So let's first before we get into multiplative weights。

 let me just go into this listening to expert advice， so the setup。Okay， iss that？There are T days。

And experts。Okay。Each day。Each expert。We'll say。Yes。Or no。Okay， so for example， will it rain today。

 will this stock go up in value today， they're each going to tell you what they think。

And then you have to decide。What you think the reality is and then make a decision。Okay， so。

So we have to。You know， we have access。To all these expert opinions。And we have to make a decision。

And what we want， we want that at the end of the T days， the number of mistakes we've made is small。

So。You know， we won't be able to。of course， we want some provable guarantee on how smaller number of mistakes is。

But you know this kind of， you know， if you don't define your。Measure of success appropriately。

 This is a hopeless problem， right， because。It might just be the case that none of the experts know anything。

 They're just saying random junk， and then you're going to say something and then reality can hit you and say。

 oh， actually it's the opposite of what you said right， I mean， no one knows the future。

 so what are you going to do here？So you know what's the kind of？

I guess I might have spilled the beans already。 You know， in such situations， you know。

 what do you usually want to measure success as？what's something that we've covered before that seems like a good way to maybe measure success。

Yeah， sure， so competitive analysis， right， so one thought。You know， be competitive。With the best。

Expert。In hindsight。Right so at the end of the two days。

 you're going to look back and you're going to look at each expert and see how many mistakes that expert made。

 and you want to make sure that。You're not much worse than the best of them。Okay。So。

What's one natural？Yeah， yeah， so you， you have， you know， infinite memory。

 You can remember everything every expert has ever told you。 And at the end of the day。

 you see what actually happened。 You see whether or not it rained， for example。Okay， so。I mean。

 what's the simplest thing you can imagine doing in this model。Yeah。Yeah。Be even simpler。 I mean。

 doess not even look at histories。 So I pull all the experts。 They all tell me something。Yeah。

 just vote， like take a majority vote， right， so you know， simple， one simple algorithm。Yeah。

 we are going， you know， over the lecture， we are going to see how to。Get more complicated。

In terms of taking the history into account， but first let me just start off with something really simple。

 so' a simple algorithm。Just take a majority vote。Okay， and then claim。If there exists an expert eye。

Well let me say if there exists an expert。That never makes a mistake。All。

 and let me actually let me I want to make one modification to the simple algorithm。

So we're going to take a majority vote。I'm going to take history into account in a very minor way。

I take the majority vote， and if anyone。Is wrong。 And at the end of the day。

 if I realized someone was wrong that day， I just killed them。Or I stop listening to them。

take a majority vote。At the end of the day。Now， kill。All。Wrong experts。Okay。So the claim。Is that if？

There exists a perfect expert。Then， we make。At most how many mistakes？yeah， wait I heard something。

I heard log login though is what I thought I heard this way。Okay， so let's login。

We make our most login。Mistakes。Or maybe I heard C log in。Okay， right， so the proof。Well。呃。Okay。

 so the point is every time we make a mistake。Most of the people were wrong。

 so we kill half the people。Okay， so every day we make a mistake。You know， we kill half the people。

At least half。Of the population。Of the experts。So。で。Right。We always have one person alive。

 namely the perfect expert。So the number of killings we can do。Is at most。Log。Wrong days。Okay。

 but that's assuming there's a perfect expert， right， So normally in competitive analysis。

 I just want to say I'm competitive with the best expert， the one who had the fewest mistakes。

So unfortunately， this algorithm。You can't just analyze this algorithm in that model because。

It could just happen that on day。