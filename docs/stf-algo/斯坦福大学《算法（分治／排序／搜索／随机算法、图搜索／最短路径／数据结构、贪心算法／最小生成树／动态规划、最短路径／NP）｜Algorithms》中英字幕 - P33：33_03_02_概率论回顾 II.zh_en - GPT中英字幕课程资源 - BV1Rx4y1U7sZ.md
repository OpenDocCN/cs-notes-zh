# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P33：33_03_02_概率论回顾 II.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

So welcomel to part two of our probability review。 This video assumes that you've already watched Part one or at least are familiar with the concepts covered in part one。

 namely sample spaces， events， random variables， expectation and linearity of expectation in this part of the review we're going to be covering just two topics。

 conditional probability and the closely related topic of independence both between events and between random variables。

 I want to remind you that this is by no means the only source you can or should use to learn this material。

 a couple other sources free that I recommend are lecture notes that you can find online by Eric Lehman and Tom Leton and also there's a Wiikibook on discrete probability。

So conditional probability， I hope you're not surprised to hear is fundamental to understanding randomized algorithms that said in the five weeks we have here。

 we'll probably only use it once， and that's in analyzing the correctness of the random contraction algorithm for computing the minimum cut of an undirectruped graph。



![](img/c712797a6e72ec787525b4270c73925a_1.png)

So just to make sure we're all on the same page for some stuff you should have learned from part one of the probability review。

 you should know what a sample space is， this represents all of the different outcomes of the random coin flips。

 all of the different things that could happen， often in randomized algorithm analysis this is just all of the possible random choices that the algorithm might make each outcome has some known probability P of I and of course the sum of the probability is equal 1 and remember that event is nothing more than a subset of omega omega is everything that could possibly happen S is some subset of things that might happen and of course the probability of an event is just the probability of all of the outcomes that the event contains so let's talk about conditional probability。



![](img/c712797a6e72ec787525b4270c73925a_3.png)

So one discusses the conditional probability of one event given a second event。

 so let X and Y denote two events， subsets of the same sample space。

You might want to think about these two events X and Y in terms of a Venn diagram so we can draw a box representing everything that could conceivably happen。

 so that's omega。 Then we can draw a blob corresponding to the event X。

 So that's some stuff might or might not happen Who knows。

 and then the other event Y is some other stuff which might or might not happen。And in general。

 these two events could be disjoint that is they could have no intersection or they might have a nontri intersection。

X intersect y， similarly， they need not cover all of omega。

 it's possible that nothing in x nor y happens。So what we're looking to define is the probability of the event X given the event Y。

So we write probability of x bar y。Phrased X given y。And the definition is， I think。

 pretty intuitive。 So given y means we assume that something in Y happened Orin。

 anything in omega could have happened。 We didn't know what。

 Now we're being told that whatever happened， it lies somewhere in y。

 So we zoom in on the part of the picture which contains Y。

 So that's going to be our denominator So our new world is the stuff in y。

 That's what we know happened。 And now we're interested in the proportion of y that is filled up with X。

 So we're interested in what fraction of y's area is occupied also by stuff in X。

 So x intersect Y divided by the probability of y。 that is by definition the conditional probability of X given y。

Let's turn to a quiz using our familiar example of rolling two dice to make sure that the definition of conditional probability makes sense to you。



![](img/c712797a6e72ec787525b4270c73925a_5.png)

Okay so the correct answer to this quiz is the third answer。So let's see why that is。

 So what are the two events that we care about， We want to know the probability of x given y。

 where x is the event that at least one die as a1。And why is the event that the sum of the two dice is 7。

 Now， the easiest way to explain this is let's zoom in。 Let's drill down on why。

 Let's figure out exactly which outcomes Y it comprises。 So the sum of the two dice being 7。

 we saw in the first part of the probability review that there's exactly 6 outcomes。

 which give rise to the sum 7。 Naly， the ordered pair is 1，6。2，5。3，4。4our three。Five， two and six。

 one。Now， remember that the probability。

![](img/c712797a6e72ec787525b4270c73925a_7.png)

Of X given y is by definition。The probability of x intersect y divided by the probability of y。Now。

 what you notice from this formula is we actually don't care about the probability of x per se or even about the event x per se。

 just about x intersect y。 So let's just figure so now we know what y is it's these six outcomes。

 which of those also belong to x。 Well x is those where at least one die is1。

 so x intersect y is just going to be the 16 and the61。

Now the probability of each of the 36 possible outcomes is equally likely。

 so each one is one over 36， so since x intersect to y has only two outcomes。

 that's going to give us a two over 36 in the numerator since y has six outcomes that gives us a six up to 36 in the denominator when you cancel everything out you're left with a  one third。

So just applying the definition of conditional probability to the correct definition of the two relevant events。

 we find that indeed a third of the time is when you have a one conditioned on some of the two dice being seven。

Let's move on to the independence of two events。So。Again， we consider two events X and Y。

By definition， the events are independent， if and only if the following equation holds。

The probability that both of them happen。That is the probability of x intersect Y is exactly equal to the probability that x happens times the probability that y happens。

So that's a simple innocuous looking definition， let me rephrase it in a way that it's even more intuitive。

So I'll let you check this， it's just some trivial algebra。

This equation holds for the events X and Y。 if and only if this is just using the definition of conditional probability we had on the last slide。

 if and only if the probability of x given y。Is exactly the same thing as the probability of x。

So intuitively， knowing that Y happened gives you no information about the probability that X happens。

 That's the sense in which x and Y are independent。

 And you should also check that this holds if and only if。

The probability of y given x equals the probability of y。So symmetrically。

 knowing that X has occurs gives you no information。

 no new information about whether or not y has occurred。

 the probability of y is unaffected by conditioning on X。So at this juncture。

 I feel compelled to issue a warning。Which is you may feel like you have a good grasp of independence。

 but in all likelihood you do not， for example， I rarely feel confident that I have a keen grasp on independence。

 of course I use it all the time in my own research in my own work， but it's a very subtle concept。

 your intuition about independence is very often wrong， even if you do this for a living。

 I know of no other source is created so many bugs and proofs by professional mathematicians and professional computer science researchers as misunderstandings of independence and using intuition instead of the formal definition。



![](img/c712797a6e72ec787525b4270c73925a_9.png)

So for those of you without much practice with independence。

 here's my rule of thumb for whether or not you treat random variables as independent。

 if things are independent by construction， like for example。

 you define it in your algorithm so the two different things are independent。

 then you can proceed with the analysis under the assumption that they're independent。

 if there's any doubt if it's not obvious the two things are independent。

 you might want to as a rule of thumb assume that they're dependent until further notice。

So the slide after next I'll give you an example showing you things which are independent and things which are not independent。

 but before I do that I want to talk about independence of random variables rather than just independence of events So you'll recall a random variable is from the first video on probability review it's just a real value function from the sample space to the real numbers so once you know what happens you have some number the random variable evaluates to some real number。

Now what does it mean for two random variables to be independent。

 it means the events of the two variables taking on any given pair of values are independent events。

 so informally knowing the value taken on by one of the random variables tells you nothing about what value is taken on by the other random variable。

Recalling the definition of what it means for two events to be independent。

 this just means that the probability that A takes on value little A， B takes on value little B。

 the probability that both of those happen is just the product of the probabilities that each happens individually。

So what's useful about independence of events is that probabilities just multiply What's useful about independence of random variables is that expectations just multiply。

 so we're going to get an analog of linearity of expectation where we can take we can interchange an expectation in a product freely。

 but I want to emphasize this this interchange of the expectation of the product is valid only for independent random variables and not in general。

 unlike linearity of expectation and we'll see a non-example we'll see how this fails on the next slide for non- independentdependent random variable。

So I'll just state it for two random variables， but the same thing holds by induction for any number of random variables。

If two random variables are independent。Then the expectation of their product。

Equals the product of their expectations。And again。

 do not forget that we need a hypothesis remember linearity expectations did not have a hypothesis for this statement about products we do have a hypothesis of them being independent so why is this true。

 well it's just a straightforward derivation where you follow your nose or write it out here for completeness but but I really don't think it's that important。



![](img/c712797a6e72ec787525b4270c73925a_11.png)

So you start with the expectation of the product。This is just the average value of a times B。

 of course weighted by the probability of any particular value。

 so the way we're going to group that sum is we're going to some overall all possible combinations of values A and B that capital A and capital B might take on。

 so that's going to give us a value of a times B。Times the probability that big A takes on the value。

 little A and。Capital B takes on the value， little B。

So that's just by definition where this is the value of the random variable。

 capital A times capital B， and this is the probability that it takes on that value with the constituent values A and B。

 Now， because A and B are independent， this probability factors into the product of the two probabilities。

 this would not be true if they were not independent it's true because they're independent。

So Sam sum were all possible joint values of A and B。Still have a times B。

 but now we have times the probability that a takes on the value A times the probability that B takes on the value B。

So now we just need to regroupgroup these terms， so let's first sum over a。

Let's yank out all the terms that depend on little A notice none of those depend on little B。

 so we can yank it out in front of the sum over little B。

 so we have an A times the probability that big A takes on the value of little A。

And then the stuff that we haven't yanked out is this sum over B of B times little B times the probability that capital B takes on the value little B。

Now what's here inside the quantity， this is just the definition of the expectation of B。

 and then what is remains after we factored out the expectation of B， just this other sum。

 which is the definition of the expectation of A。So indeed， four independent random variables。

 the expected value of the product is equal to the product of the expectations。

 Let's now wrap up by tying these concepts together in an example。

 a simple example that nevertheless illustrates how it can be tricky to figure out what's independent and what's not。

 So here's the setup。 We're going to consider three random variables。X1， x2， and x3。X1 and x2。

 we choose randomly， so they're equally likely to be0 or1。

But x3 is completely determined by x1 and x2， so it's going to be the x or。Of x1 and x2。

So Xor stands for exclusive or， so what that means is if both of the operarans are0 or if both of them are1。

 then the output is0， and if exactly one of them is one， exactly one of them is0。

 then the output is one。 So it's like the logical or function except if both of the inputs are true。

 then you output false so that's exclusive or。Now， this is a little hand wavy when we start telling about probabilities。

 if we want to be honest about it， we should be explicit about the sample space。

So what I mean by this is that x1 and x2 take on all values they're equally likely。

 so we could have a 00 or a 10 or a 01 or a 11， and in each of these four cases x3 is determined by the first two as the x or。

 so we get a0 here， a1 here， a 1 here， and a0 there。

And each of these four outcomes is equally likely。So let me now give you an example of two random variables which are independent and a non example。

 I'll give you two random variables which are not independent。So first。

 I claim that if you think at x1 and x3。Then there are independent random variables。

I'll leave this for you to check。This may or may not seem counterintuitive to you。 remember。

 x3 is derived in part from x1， nevertheless X1 and x3 are indeed independent。And why is that true。

 Well if you enumerate over the four possible outcomes。

 you'll notice that all four possible two bit strings occur as values for one and three。

 so here they're both0， here they're both one， here you have a0 and1 and here you have a one and a0 so you get all four of the combinations with probably one over four。

 so it's just as if x1 and x3 were independent fair corn flips so that's basically why the claim is true。

Now that's a perhaps counterintuitive example of independent random variables。

 let me give you a perhaps counterintuitive example of dependent random variables。

 needless to say this example just scratches the surface and you can find much more devious examples of both independence and nonindependence if you look and say any good book on discrete probability。

So now let's consider the random variables X1 product X3。And x2。

And the claim is these are not independent。So this will give you a formal proof for the way I'm going to prove this is going to be slightly sneaky。

 I'm not going to go back to the definition， I'm rather going to contradict a consequence of the definition。

 so its prove that they're not independent。All I need to do is show that the product of the expectations is not the same as the expectations of the products。

 Remember if they were independent， then we would have that equality can be product of expectations would equal the expectation of the products。

 So if that's false， then there's no way these random variables are independent。

So the expectation of the product of these urranium variables is just the expected value of the product of all three。



![](img/c712797a6e72ec787525b4270c73925a_13.png)

And then on the other side， we look at。The product of the expected value of x1 and x3。

And the expected value of x2。So let's start with the expected value of x2 that's pretty easy to see that is zero half the time and that is one half the time。

 so the expected value of x2 is going to be12。How about the expected value of x1 and x3？Well。

 from the first claim。We know that X1 and x3 are independent random variables。

 therefore the expected value of their product is just a product of their expectations。

This expectation is equal to the expected value of x1。Times the expected value of x2。

 excuse me of x3。And again， x1 is equally likely to be 0 or1， so its expected value is a half。

 x3 is equally likely to be01， so its expected value is a half。

 so the product of their expectations is one fourth。So the right hand side here is1/8。

 one/ half times a quarter so that's an eighth， What about the left hand side。

 the expected value of x1 times x3 times x2？Well， let's go back to the sample space。

What is the value of the product and the first outcome， zero。

 what is the value of the product and the second outcome， zero， third outcome， zero， fourth outcome。

 zero？The product of all three random variables is always zero with probability one。

 therefore the expected value of course is going to be zero。So indeed。

 the expected value of the product of x1x3 and x2，0 is not equal to the product of the corresponding expectations。

 so this shows that X1x3 and x2 are not independent。

