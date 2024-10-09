# 【双语字幕+资料下载】辛辛那提 MATH1071 ｜ 离散数学(2020·完整版) - P75：L75- Bayes' Theorem - Example - A disjoint union - ShowMeAI - BV1Sq4y1K7tZ

In my introduction to base theorem， I gave you this formula that the probability of a given B could be written by the conditional probability the other way around that is the probability of B given A。

 but you had to multiply by the probability of a and divide by the probability of B if we wanted to can take that formula rearrange and I figure out what it was the probability for B given a in terms of the probability of a given B as well Now in this video we're going to upgrade this formula a little bit we're going to investigate what happens if we have some sort of division in our sample space that we can separate it into different quote unquote buckets So the example I want to use to motivate this is one where I'm quite literally going and drawing two different buckets and I'm having balls of different color inside of these two buckets。

You'll notice that the one on the left， the one I'm calling B1， well。

 it's going to have three blue ball and three yellow balls。

 so the probability of a blue ball being drawn from that bucket would be 50，50。

And then B2 is a bit different， it's got two balls， but it's got four yellow balls。

 and so the probability of drawing a blue ball from the second bucket would be one third。

So now I'm saying， well look， what if I draw from a bucket。

 but I don't know which it is like I randomly choose a bucket and then I randomly choose a ball from within that bucket well now if I know that I've drawn a blue ball。

What's the probability that I came from that first bucket， or alternatively， I could ask well。

 if I had a blue ball， what's the probability that I came from the second bucket？

This is the problem we're going to try to investigate and I'm going to begin by just computing a few different things that I can compute and then we're going to try to put them together in a sort of upgraded base theorem。

😡，Now the first thing that I know that I'm confident about is certain conditional probabilities。

 probabilities that go in one direction， not the direction I'm looking at。

 but the ones that go in the other direction as in let me first just denote by a the event that we're going to select。

😡，A blue bulb。And I'll let B1 be the event that I chose from Buck B1 and B2。

 the event that I chose from Buck B2， fair enough。So the thing I was confident about is that the probability of choosing a blue ball。

 what I call a， given that I am looking at bucket B1。

 well I know that this is going to be equal to one half， there's three blue balls。

 there's three yellow balls， it's a 50% probability。

I am also pretty confident if I look over here at B2。

 I can say that the probability of drawing a blue ball， given that I'm in the second bucket， well。

 two blue balls， six over， so one third。Okay， that's not so bad I've at least done some computations here。

What else do I know Well， other things I might be able to compute is there's two different buckets here。

 there's a B1 and the B2 and。eququally likely to be drawn from。

 so I can say that the probability of drawing from the B1 or the probability of drawing from the B2。

 that this is just a 50-50， so another one half that I'm asserting as sort of part of the setup of my problem that my two buckets are equally likely to be drawn from。

😡，Now I want to do something a little harder I'm going and try to investigate what is the probability of a。

 What's the probability of drawing this blue ball where when I first have to randomly pick between these two buckets and then when I get a bucket。

 I randomly draw a ball from that that could be blue that could be not Who knows Now the first thing I want to notice that there is a disjoint union here。

 the B1 and the B2 are completely separate， there's no overlaps between them by design。

 this is a disjoint union of our sample space。😡，So what we can do is we can investigate what the probability of a。

 given that I'm inside of B1 is。And then I can add to that the probability of being a inside of my B2。

Now， the reason why this works is， first of all that the sample space of A can be dividing in these two things。

 the A's that are in the B1 and the A's that are in the B2。

 which I formally write down as a probability of A intersect B1 and a intersect B2。

And then the second thing I'm using here is knowing that for disjoint unions。

 that the probability of a disjoint union is the sum of those individual probabilities， indeed。

 if you were doing an accounting problem， you were said。

 what is the number in a disjoint union you figure out the number in a and you add to it the number in Bs。

 the is exact same idea is what we've seen before。Okay， so I have these two different intersections。

 but what I know is I now know how to deal with intersections in terms of conditional probabilities。

 so let's remind ourselves how conditional probability worked we had this particular property that the probability of a given B was by definition just the intersection of a intersect B。

😡，All divided by the probability of B so that was my broader formula and I can use that formula I can put it in here so how does it work well okay this is a intersect B1。

😡，So ans B1 is the probability of a given B1， and then I have to take the denominator multiply it up。

 multiplied by the probability of B。😡，And then the probability of a intersect B is the probability of a given now it's the B2 and multiplied by the probability of my B2 and because I was planning ahead I've already computed all four of those numbers。

 so the probability of a given B1 was a half。😡，The probability of just B1 here。

 I'm going to add in the subscript B1 was equal to another half。

The probability A given B2 was a third。And the probability of B2 was another half equally likely to choose B1 is B2 All right。

 so this is going to be a quarter。Plus one，6。And then this is going to be 312 plus 212。

 which is going to be a total of512。That's my final answer。All right。

 now I've gone and computed some values here， but what am I I even asking in this poem。

 let's go back and try to remember。I was given these two different buckets and I was saying。

If I draw a blue bottle， then what is the chance that I was in the bucket one。

 that's what I'm asking， I'm asking this conditional probability was the probability of being in bucket one。

 given that I've drawn a blue ball so I can apply base theorem and I've written it down for you already it is going to be that the probability of being in bucket1 given a that's what I have here is going to be the probability of a given B1 times the probability of B1 all divided by the probability of a this is base。

😡，All right， well let's try to compute this we've done the probability of a given B1 already that was just one half remember there was three blue balls and three yellow balls so it a 50% probability the probability of B and B1 we did that already。

 there was the two buckets， they were equally likely it was another value of a half。

And then we just went through the sort of somewhat arduous task of figuring out the probability of A so that was the512s we did in anticipation of this。

 and now I can get this so multiplying by the 12 up。

 that's going to leave me with a final value of three fifths。Now。You should verify。

 does this make sense。 I think so。 If you remember in the two different buckets that we had。

 the B1 had more blue balls than as as a probability or 36， then the B2 would only had two sex。

 So if you've got on a blue ball， it is somewhat more likely that you're in the bucket one than you are in the bucket2。

 And so we get this value of three fist that's a little bit bigger than the 50% probability of randomly choosing between the two buckets。

 So this makes sense at least at a broad picture for us。

So this is an example of how we can apply base serum in a scenario where there's two different buckets。

 it's basically exactly the same thing if you have three or four or n different buckets。

 you just have to divide it up into more cases， your P of A is going to have n different subdivisions inside of it。

 but other than that it's the same idea。