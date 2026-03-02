# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P165：37_04_07_直线上的随机游走.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Understanding why Papa Dimitri's randomized local search algorithm for twoat works requires understanding some basic properties of random walks on the non negative integers。

 it's a very fun classic topic in this video I'll provide the relevant background。

In this video we're going to focus on a simple randomized process we're not going to discuss in this video how this connects to Papa Dimitri's algorithm。

 but in the next video we will trust me。The setup is as follows。

 perhaps you just took a super difficult exam， maybe it was an algorithms class， for example。

 you stagger out of the exam room and you're just in a complete days。

 you have no idea where you are or where you're going and so you just stumble along at each time step you take a step to the left with 50% probability or a step to the right with 50% probability。

 you have no idea where you're going。We measure your position in terms of the number of steps you've taken from a dead end at the end of the street。

 which we call position zero， so by randomly walking left or right at each time step。

 your position either goes up by one or it goes down by one， each has a 50-50 chance of happening。

The one exception is if you found your way to position zero， again， that's a dead end。

 there's no way to go left， so with 100% probability you stagger back to the right。

 you go to position1 at the next time step。

![](img/a49c01a2176f3e82c020ebcd7c92b739_1.png)

We assume that your exam room is located at this position zero at the dead end。

 in other words at time zero， you're at position zero。

There's a lot of interesting questions you can ask about random walks on the non negative integers。

 Here's the one we're going to be interested in。 Imagine your dorm room is n steps away from the exam room。

 That is， your dorm room is at position N。 Now， if you had your wits about you。

 you could go from your exam room to your dorm room in N steps。 You just zip right down the line。

 But you don't have your wits about you， You're in this post exam days staggering around。

 So doing your random walk， On average， how many steps does it take you before you make it home two position N。

To illustrate a sample trajectory， imagine that your dorm room was only three steps away at spot 3。

So in time 1， we know that for sure， you move from position 0 to position 1。

 And now maybe you get lucky and you stumble a step to the right in the next time step。

 So you're at position 2。 You're only one step away from home。 But now， unfortunately。

 you stagger backward back to position 1。Maybe now you lurch forward back to position two again。

And this time， your momentum carries you forward on home to position 3。

That was a trajectory in which it took you five steps to get home to your dorm room at position 3。

 you can imagine a trajectory which is faster if you just zipped straight there。

 you can certainly also imagine trajectories which are slower if you stumbled back left a couple times more before making it all the way to the right to position3。

So let's state this statistic precisely and check in with your intuition about how it grows as a function of n。



![](img/a49c01a2176f3e82c020ebcd7c92b739_3.png)

![](img/a49c01a2176f3e82c020ebcd7c92b739_4.png)

So for a non negative inger n， I'm going to use capital T sub n to denote the number of steps this random walk takes before it reaches for the first time。

 position N。So T7 is a random variable in the sense that its value depends on exactly which steps you took on the results of your random coin flips。

 on the other hand， once you unveil the answers to all of the random coin flips。

 whether you go left or right at each time step， you can compute T yet just like we did in the sample trajectory on the last slide。

So the nontrivial question I want you to think about on this quiz is how does the expected value of T7 grow as a function of the position N that you're waiting to reach？

I'm not expecting you to devise a proof of the answer indeed。

 that's what we're going to be doing for most of the rest of this video。

 just asking you to take your best guess。So the correct answer is b theta of n squared。

Depending on how much facility you have with discrete probability。

 you may or may not have been able to do a back of the envelope calculation that would suggest this should be the answer。

 So， for example， if you take some Bulli random variables and do some calculations with their standard deviation。

 you might expect the answer to be theta of n squared。 In fact。

 what's even cooler and what we're going to prove is it's not just theta of n squared。

 the expected value of the random variable T sub n is exactly n squared for every non negative integer N。



![](img/a49c01a2176f3e82c020ebcd7c92b739_6.png)

For the most part， in these courses， I have endeavored to give you proofs， which on the one hand。

 aren't too long。 I know you're a busy person and I don't want to waste your time。

 but also on the other hand， teach you something。 So I hope you'll forgive me if it's not clear what this proof teaches you。

 this is just going to be the slicickked up proof from the book that the expected value of T suban。

 the number of steps needed to reach position N on a random walk is exactly and squared。



![](img/a49c01a2176f3e82c020ebcd7c92b739_8.png)

![](img/a49c01a2176f3e82c020ebcd7c92b739_9.png)

The really nice idea behind this slick proof is to solve a more general problem。

 so we're going to calculate the expected number of steps not just to get from position  zero to position N on a random walk。

 but more generally from every intermediate position I to the position N on a random walk。

 The reason this is a good idea， this gives us n plus one different statistics we're trying to calculate and it's easy to relate the values of these different things we're trying to calculate from these relationships we'll be able to solve for all of them simultaneously。



![](img/a49c01a2176f3e82c020ebcd7c92b739_11.png)

![](img/a49c01a2176f3e82c020ebcd7c92b739_12.png)

So let's have some notation to make this precise for a non negative inger I by z sub I。

 I mean the number of random walk steps that you take if I start you at I until you reach position n for the first time。

 Notice by the definitions， z sub 0 is exactly the same thing as t sub n。

 the number of steps you need to reach n starting from 0。

So are there any Zs whose expectations are easy to compute， Well， sure， if we took I equal to n。

 what is z sub n， That's the number of steps on average you need to get from n to N for the first time。

 Well， that's going to be 0。For the other values of I。

 we're not going to solve for the expected value of Z sub I explicitly just yet。

 rather we're going to relate to the expectations of different ZIs to each other。

To see how this works， let's start with i equals0， that is zO the random variable that we really care about。

Now， we don't know what the expected value of z is。 That what we're trying to compute。

 But we do know that every walk starting at 0 and ending at n begins with a step from 0 to 1。

 and then is followed by a walk from one to n。 Therefore。

 the expected length of one of these walks is just one。 That's for that first top to get from 0 to 1。

 Plus the expected value of a random walk from position 1 to n。

 That's a quantity also known as the expected value of z sub 1。

So that's kind of exciting how we are able to avoid explicitly computing the expected value of Z sub n。

 instead relating it to the expectation of a different random variable， Z sub 1。

But if you think about it， we can play exactly the same game with the intermediate values of I as well。

 we can relate the expected value of Z sub I to the expected values of Z sub I minus1 and Z sub i plus1。

To make this fully precise I'm going to bust out the definition of a conditional expectation。

 so I'm going to assume that you know what that is if you want to review it。

 you can go back to part1， we needed conditional probabilities to analyze Cardge's randomized contraction algorithm or you can just look it up on Wikipedia or whatever if you're not feeling in the mood to recall what conditional expectation is actually think the computations I'm about to do or sufficiently intuitive。

 you'll find them eminently plausible even without the formal justifications。

So what's the expected value of Z sub by the average number of steps you need to hit n for the first time。

 If I start you out at position I。 Well， let's just condition on what happens in the first step。

 right， there's only two possibilities。50% probability。 you go left to I -1。

 The rest of what happens is a random walk from I -1 and you just count the steps till you get to end for the first time。

 The other 50% of the time where you go right and the rest of the process is just a random walk starting from I plus1 and you count the steps until you get to end for the first time。

If you want to be totally formal about it， you would just expand the expected value of z sub I conditioning on the first step so you'd have the probability that you go left times the conditional expectation of z sub I。

 given that you go left in the first step and a similar term for it when you go right。

 As we discussed， we know the probability that you go left is exactly one half。

 The probability that you go right is exactly one half。

 The conditional expected value of your random walk。 Given that you went left first。 Well。

 that's just one。 that's the step you took to get to I -1 plus the expected length of a random walk to and from I -1。



![](img/a49c01a2176f3e82c020ebcd7c92b739_14.png)

Similarly， if you're lucky enough to go right， then the expected random walk is just one that's for the step to go right。

 plus the expected value of the rest of the random walk。

 also known as the expected value of Z sub i plus1。Once the dust clears。

 we discover that the expected value of z subbi， the average number of steps from position I is just one plus the average of the expectations of z sub minus1 and z sub plus1。

If we multiply both sides of this equality by 2 and rearrange。

 we get that the difference between the expected values of Z sub I and z sub I plus1 is equal to two more than the difference between the expected values of z sub minus1 and z sub I。

So what's a good interpretation of this equation。 Well， first。

 let's just notice that the expected value of Z sub I。

 that number is definitely decreasing as you take odd bigger and bigger as you start closer and closer to your destination and certainly the number of steps that you need is going down。

So for that reason， both sides of this equation are going to be positive， right。

 the expected value of z sub I is going to be bigger than the expected value of z sub I plus1。

 you don't need as many steps if you start further to the right at I plus1。

But this equation is saying more。 It's saying， consider a consecutive pair of conceivable starting points。

Clearly， you have an advantage by starting one position closer。

 But this equation is saying that as you slide this pair of consecutive starting points closer to the destination。

 the advantage gets amplified。 So， so however much savings you got by starting one position closer at I instead of I -1。

 you get that same advantage plus2 more， If you get to start at I plus 1 relative to starting at I。

So why is it useful to relate all of these various expectations to each other。

 well now that we have this big systems of constraints。

 we can solve simultaneously for what all of these expectations have to be。

 in particular for the one expectation we really care about E of ZO。



![](img/a49c01a2176f3e82c020ebcd7c92b739_16.png)

![](img/a49c01a2176f3e82c020ebcd7c92b739_17.png)

So to see how we do this， let's just write down what the differences between successive expectations have to be。

So the first thing we know and this was one of our edge cases is that whatever the expected value of z0 is。

 it has to be one more than the expected value of Z1。

That is the difference between these two expectations equals one。

We concluded the previous slide by noting that if you slide a pair of consecutive positions。

 one position further toward the destination N， then the advantage you get by starting one position closer goes up by two。

 so if your advantage is1 by starting at Z1 instead of z。

 then your advantage is going to be3 by starting at Z2 instead of Z1。

 that is the expected value of Z1 minus the expected number of steps from2 is going to be equal to3。

So we can just apply that equation over and over again。

 we bump up the indices by one and the difference between the expectations gets bumped up by two。

So at the end of the day， relative to our very first equation。

 we've bumped up both indices by n minus1， so we've bumped up the right hand side by 2 n minus2。

 so we have that the expected value of Zn minus1 minus the expected value of Zn is equal to 2 n minus1。

Massive cancellation is often the sign you're on the right track。

 certainly that's what we're going to see here， so all of the expected values for Z1 through ZN minus1 appear once positively once negatively so they're all going to drop out。

And actually it gets even better than that the expected value of z sub n that's just zero。

 remember that would be how long a random walk takes to get from n to N also known as zero So if we add up all these equations we magically get exactly what we cared about on the left hand side。

 the expected value of z0 of a walk starting at zero ending at n that's also known as t sub n that the expectation we're trying to analyze。

So what is the right hand side sum too Well， an easy way to think about it is just to group the first row with the last row。

 the second row with the second to last row and so on。 For example， is if n is equal to 100。

 we're going to group one with 199，3 with 197，5 with 195 and so on。

 So each of these groupings is going to give us two n and if n is even is going to be n over two of these pairs giving us a total of n squared。

 If n is odd， the story is the same， you just get n minus1 over two groups of size2 n plus the median groups is going to have a value of n again。

 you get n squared。So that completes this very pretty。

 if somewhat inscrutable proof that the expected number of steps you need before you reach n for the first time is exactly n squared。



![](img/a49c01a2176f3e82c020ebcd7c92b739_19.png)

In the analysis of Popi Diometri's algorithm， we're not actually going to use this claim about the expectation。

 rather we're going to use an easy corollary， which gives an upper bound on the probability that this exceeds its expectation by more than a factor of two。



![](img/a49c01a2176f3e82c020ebcd7c92b739_21.png)

Specifically， we're going to use the fact that the probability that a random walk needs strictly more than two times n squared steps to reach position N for the first time is no more than 50% this is a special case of a symbol but useful inequality known as Markov's inequality。

In proof， let's denote by P the probability of interest。

 the probability of the random and variable T sub n is strictly bigger than 2 n squared。Essentially。

 the reason the corollary is true is that if the probability that T sub n was bigger than2 n squared was strictly bigger than1 half。

 well then the expectation would have to be bigger than n squared， but it's not。

 it's equal to n squared， we just computed it。So a little more formally。

 let's start from the expected value of T sub n。 Now we know this is n squared， we just computed it。

 but let's also write out the definition of this expected value。

So that's just a sum over the values that TN might take on。

 let's go ahead and just use all non negative integers k from0 to infinity。

 and then it's k times the probability the T sub n takes on the value k。

I'm going to break this sum into two parts， the parts where k takes on a value that's at most2 n squared。

 and then the parts of the sum where K takes on a value bigger than 2 n squared。

So now let me just do some very crude lower bounds of this right hand side， this first sum， well。

 whatever it is， it's going to be non negative because ks are non negative and probabilities are non negative。

And the second sum， again， I'm feeling very generous。

 let's just lower bound K in the sum by 2 n squared。 it's always going to be bigger than that。

After the dust clears the first sum has disappeared。

 that's what we're just lower bounding by zero and the second sum we're lower bounding K by 2 n squared at that point we can take the 2 n squared outside the sum。

 and at that point the sum is merely the total probability masst on which TN takes on a value strictly bigger than 2 n squared plus1。



![](img/a49c01a2176f3e82c020ebcd7c92b739_23.png)

By definition， we are calling this probability of P。

 This is the probability of interest and rearranging。 We do see that。 In fact。

 P has to be at most one half。So that completes the claim of the corollary。

 it's really just a simple consequence of the hard work。

 which was proving that the expected value of this random walk was n squared。

 will plug this corollary into the analysis of Papa Diometri's algorithm next。

