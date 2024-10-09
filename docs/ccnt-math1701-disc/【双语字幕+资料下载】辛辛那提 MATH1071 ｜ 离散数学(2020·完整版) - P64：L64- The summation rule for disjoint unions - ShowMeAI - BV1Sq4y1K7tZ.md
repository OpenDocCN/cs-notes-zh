# 【双语字幕+资料下载】辛辛那提 MATH1071 ｜ 离散数学(2020·完整版) - P64：L64- The summation rule for disjoint unions - ShowMeAI - BV1Sq4y1K7tZ

Let's try to count the total number of possibilities for passwords where the passwords are kind of short。

 just for illustrative purposes， either one，2 or three letters long and that the only symbols I can put in my passwords are going to be lowercase letters。

 So there's 26 different possibilities for any letter and they can slot into either one。

2 or three letter long passwords。 So how many passwords are there here。😡。



![](img/ff0c10902f386d68703af53acbbed615_1.png)

![](img/ff0c10902f386d68703af53acbbed615_2.png)

![](img/ff0c10902f386d68703af53acbbed615_3.png)

![](img/ff0c10902f386d68703af53acbbed615_4.png)

![](img/ff0c10902f386d68703af53acbbed615_5.png)

![](img/ff0c10902f386d68703af53acbbed615_6.png)

Now， there are three subcases within this problem。

![](img/ff0c10902f386d68703af53acbbed615_8.png)

There's the problem。 How many one letter passwords are there。 There's the problem。

 How many two letter passwords are there。 And there's the problem。

 How many three letter problems are there。

![](img/ff0c10902f386d68703af53acbbed615_10.png)

![](img/ff0c10902f386d68703af53acbbed615_11.png)

So let's try to solve those three different subcases。

 and then we're going to try to combine them at the end to one answer to this larger problem。



![](img/ff0c10902f386d68703af53acbbed615_13.png)

![](img/ff0c10902f386d68703af53acbbed615_14.png)

So the first case is how can I create a one letter password Well there's only 26 possibilities I've got 26 letters to put into one slot。

 so there's one out of 26 different cases for a given password。



![](img/ff0c10902f386d68703af53acbbed615_16.png)

So let's look at the one letter spot first well there's only one thing to fill。

 I've got 26 different possibilities that I could put in for my one letter long password。

 so there's only a total of 26 possibilities。😡。

![](img/ff0c10902f386d68703af53acbbed615_18.png)

![](img/ff0c10902f386d68703af53acbbed615_19.png)

Okay， that was relatively simple， what about the two letter scenario？



![](img/ff0c10902f386d68703af53acbbed615_21.png)

Well now I've got two letters， there's 26 possibilities I can put in for that first letter and then there's 26 possibilities I can put in for that second letter as well。

 and so because they're independent， I don't care if they repeat。

 I don't care if the password is AA for instance， then everything's independent here。

 and I just multiply them out， there's 26 times 26 or 26 squared possibilities。



![](img/ff0c10902f386d68703af53acbbed615_23.png)

And the same is true in the three letter case， so I've got three different buckets now。

 there's 26 in the first， 26 and the second， 26 and the third。

 I multiply them according to my multiplication rule。

 and so I get 26 to the power of three different possibilities。And then the final answer。

 what are the total number of passwords， if I'm allowing one letter passwords。

 two letter passwords and three letter passwords， then I'm just going to sum up these three cases。

 that's how many1，2 and three there are， so I'm going to say that my total is the sum of those three cases it's going to be the 26 to the1 plus the 26 squared plus the 26 cubed and if you compute it out you get this number 18。

278 different passwords。

![](img/ff0c10902f386d68703af53acbbed615_25.png)

So it's a big number， but still not that big， still we've got really relatively weak passwords。

 only 18 and change thousand possibilities when I'm only using letters and I'm only using one。

 two or three letter passwords， which of course is not what we use now we're using eight or more depending on your application。

😡，Now what was key about this example was that the three different cases and I called them S1。

 S2 and S3， sort of three different sub sampleample spaces that those were completely independent。

 they didn't overlap every password is either one letter long or it's two letters long there's no passwords that overlap here that are both cases。

😡，This idea is something referred to as disjointness。

 so this is something we could have defined back when we were doing set theory。

 but we're going to define it now because this is when we need it。😡。



![](img/ff0c10902f386d68703af53acbbed615_27.png)

When you've got two different sets， A and B and that they don't overlap that their intersection is empty。

 we're going to refer to the notion of a disjoint union and we're going to denote it it's kind of like the union symbol but squarer。

 it's like a square unions in what we call that the disjoint union of A and B and visually we can think of it like this I have two sets my A and my B。

 I think of them as being disjoint because they have no intersection right there's no overlap here。

 I've got the free space in the middle where my hand can be seen。😡。



![](img/ff0c10902f386d68703af53acbbed615_29.png)

![](img/ff0c10902f386d68703af53acbbed615_30.png)

![](img/ff0c10902f386d68703af53acbbed615_31.png)

![](img/ff0c10902f386d68703af53acbbed615_32.png)

And then I could consider what is the total number of things in A and B Well then it's just these two individual things I add up the A's and I add up the B's。

 so my theorem is this when I have a disjoint union。

 when my sample space can be broken up as to a disjoint unit of two things then the number of my larger sample space。

 my s。

![](img/ff0c10902f386d68703af53acbbed615_34.png)

![](img/ff0c10902f386d68703af53acbbed615_35.png)

It's just the sum of the two things。 I figured out how many things were there in S1。

 how many things were there in S2， and I add the two of those things together。



![](img/ff0c10902f386d68703af53acbbed615_37.png)

![](img/ff0c10902f386d68703af53acbbed615_38.png)

So in the example that we had seen we actually have a triple disjoint union。

 there's no overlaps The S1 and the S2， their intersection is empty and the S1 and the S3。

 their intersection is empty and finally the S2 and the S3 their intersection is empty every one of these passwords either1。

2 or3 and there's none that are both one and two letters long wouldn't make any sense So these three S1 S2 S3 these three subample spaces are going to be disjoint。

And so in the Normanclature of our disjoint union， we can say that our total sample space is S1 disjoint Union S2。

 disjoint Union S3， and by the formula， I can say that the total number is the sum of those three things。

 the n of S1， the n of the S2， the n of the S3， and that is precisely what we computed out before。

So in other words， the logic that we saw in this password example。

 it generalizes into this larger property。