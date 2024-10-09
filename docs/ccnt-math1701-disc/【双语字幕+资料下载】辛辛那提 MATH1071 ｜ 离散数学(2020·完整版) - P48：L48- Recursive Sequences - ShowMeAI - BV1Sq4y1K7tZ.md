# 【双语字幕+资料下载】辛辛那提 MATH1071 ｜ 离散数学(2020·完整版) - P48：L48- Recursive Sequences - ShowMeAI - BV1Sq4y1K7tZ

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_0.png)

In this video， we're going to talk about sequences that are defined recursively。

 And what I mean by that is that maybe you have a few terms which are just specified。 So。

 for example， I might tell you that the a1， the first term of my sequence is the value of one。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_2.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_3.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_4.png)

But after these first few terms that have been just explicitly written out。

 all future terms are described in terms of earlier terms。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_6.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_7.png)

And what I mean by this is that there is some recursive formula like the following。

 we're going to say that the k term in the sequence。

 the AK is some formula in terms of prior terms and in this example it's the AK minus1。

 the term that immediately precedes it and then you add three to it。

 but in principle on the right hand side here you could have any weird formula that was referencing only terms before the k term。

 for example， the K minus1， the K minus2， the K minus3 and so on。

 and so this is a recursive definition in the sense that new terms。

 the AK are defined in terms of the previous terms。😡。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_9.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_10.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_11.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_12.png)

Now note that in this formula that the K is just a placeholder， I could put anything there。

 I could put some other symbol， I could put a box， I could also put some other relationship about k so for example。

 in this formula what I've done is I've taken everywhere that there was a K up here and I've put in a K minus2 here a K minus2 here and a K minus2 there。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_14.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_15.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_16.png)

And then maybe if I go and do this algebra and I take the two to the other side。

 I can rewrite this as a k minus2 is equal to ak minus3 plus3 and that this formula is only valid in the space k being bigger than three。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_18.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_19.png)

So the immediate takeaway is that these recursive formulas are not unique。

 that the first one and this one that we've gotten down here are the same basic underlying sequence。

 but they're just expressed in a bit of a different way if a recursive formula is one that says the AK is defined in terms of previous AKs ak minus1。

 aK minus2 and so on。😡。

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_21.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_22.png)

Then an explicit formula is one that doesn't reference any other terms。

 the only thing it references is that value K， it's aK is some function of K like K squared or K factorial。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_24.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_25.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_26.png)

So one of the goals that we have is if I have a recursive sequence。

 can I find an explicit formula for it that is not recursive？



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_28.png)

So let's look at the example that we had before， we've got this first term， the A1 is1。

 and then the AK is given like this。

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_30.png)

I'm going to go and play around with this， I'm going to write out the first few terms and I'm going to see if we notice some pattern and have therefore we'll have an ability to write aK as a function only of K So the A1 we know that's just given to us we don't have to do any new work A1 is equal to one。

😡。

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_32.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_33.png)

Now let's do a2。So what our formula tells us is that if I'm going to use k equal to2 here。

 so this is a2， it's going to be whatever the value of a2 minus1， so a1 is plus3。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_35.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_36.png)

So it's the A1 value， which was going to be a1， and then I'm going to add to it three。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_38.png)

And there I get my A2， which we could then compute was going to be equal to the value of four。

 So the first term is one， the second term is four。 Let's continue。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_40.png)

If I look at what a3 is going to be， well， a3 is a two plus three。So it's gonna to be4 plus3。

 but I'm actually going to keep it in its original format。 I'm gonna say that it's the a2。

 which I'll leave as the one plus the three。 and then I'm going to add one more copy of three。

 Allright， let's continue again。 I'm now going say that the a4 is equal to the one plus3 plus 3。😡。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_42.png)

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_43.png)

So that was the value of my A3 and this， of course， is just the same thing as seven。

 but I'm not going to worry about that。And then we're going to add one more copy of three。

So what it looks like is occurring here is that because of this plus three that I have in my recursive formula。

 every time I go and do one of these terms I'm adding three to it， one plus three is four。

 four plus three is seven， seven plus three is going to be equal to 10。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_45.png)

So now what I want to do is I want to write down my a subK。

 I want to write down the K term to this sequence。And I want you to note the following fact。For a1。

 there were zero threes for a2， there was one，3， for a3， there was two threes， for A4。

 there was three threes， notice how there's always one less three then the number that appears here like when the number is four。

 we're going to have three， threes， which is one less than four when the number is three we have two。

 threes， which is one lesson than three。

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_47.png)

So I believe that that's going to be the pattern every one of these terms are going to have the one。

 so the Ak is definitely going to have a one out the front of it。

And then it's got some number of threes， but the number of threes is the value k minus1。

 so I'm going to write it as 3 k minus1， so this formula is the explicit formula for AK that comes about from this recursive definition for AK。



![](img/c4ca84d3b3314fc1ed7f5b04a0644349_49.png)

Now I believe we've done this accurately， but perhaps we've made a mistake what I'm going to show you now is a verification that the result that we have down here does indeed match this particular recursive formula。

😡，Clearly， in the case of k equal to1 by plugging K equal to 1， this is gonna give me a0。

 So for k equal to1， it does indeed match that my a1 is equal to 1。 So that part's good。

 But it's the recursive part that I'm really interested in。

 So what I'm going to do here is I'm gonna to say that a K， which I just said was1 plus 3 times k -1。

😡。

![](img/c4ca84d3b3314fc1ed7f5b04a0644349_51.png)

And then the question is， is this going to be equal to a if I plug in k minus1 to it。

 so let's be careful here。If I want to look at aK minus1。

 what I do is this is my generic formula for k， but I plug in K minus1 here on the left。

 and I also plug in K minus1 here on the right。And if I'm plugging k minus1 here on the right。

 then this term is going to become k minus2 So the question is is this equal to1 plus3 and then I'm going to write it as k minus2 and the minus2 comes from plugging a k minus1 into this formula get the one more minus1 and then finally plus a value of3 and this is my question mark is it true that this is the case。

 I'm trying to verify that this recurrence relation is indeed true and I think so because I can take this formula here and I can manipulate it。

 I can say that this three can be brought in over here so it's three k minus2 plus1 which is precisely the same thing as1 plus3。

😡，K -1。And so what have I done， I have verified that this equation is true and therefore verified that this explicit formula does indeed match this recursive formula。

😡。