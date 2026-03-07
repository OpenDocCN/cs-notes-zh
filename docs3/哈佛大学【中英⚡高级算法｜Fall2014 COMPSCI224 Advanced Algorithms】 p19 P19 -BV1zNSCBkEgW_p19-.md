# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p19 P19 -BV1zNSCBkEgW_p19-

![](img/277fc820cfb30bd4fb8404301363f36e_0.png)

那也三都さ感。嗯。Okay， so today we're going to。Finish multiplative weights。

 I just want to show you how you would apply it to linear programming to solve linear programs or approximately solve them。

And then after after that， we're going to。Switching to a new topic， namely Fs。So。呃。

So right now I'm going to talk about oh， and someone， yeah。

 so Eric just asked me when you're going to get， are you going to get feedback for。

Your project proposals， yes， you will。 So I think I should be done by the end of Sunday。

Like into the weekend， let's say okay。I'm looking through those to give people feedback。Okay， got。

 so applying。Multipplicationative weights。To let's say， LPs。

So let's just remember the theorem from last time。So theorem。We said that if you。嗯。

Use multiplicative weights to come up with the probability of vectors in each iteration。

 You get the guarantee that。Yer。Some of expected costs over all the days。 So this is M。Qi。Dot P。

 So PT is the probability vector you output over the experts in day T。 M is the cost vector on day T。

 Remember， M， the I coordinate of M is。The cost of the I expert。嗯。On Dt。This quantity is at most。

The min over all I。From one to n。So there are N experts。Of the sum over T。

Of the cost of that expert on dayT。Plus。Epsilon。So this is for all for any。any epsilon？

Between zero and a half。Epsilon times the sum of MIT absolute value。Plus。Yes， lawn end。Over Epsilon。

对。That was the theorem from last time。Okay， and remember， we assumed that all our costs。

These these entries of these cost vectors， we assume they're all between 1 and 1。Okay。

So in particular， this sum is over all the days。So this sum is at most t。

So you could also say this is at most of the min over eye。Of some over T， MIT。Plus。

 epsilon T plus lawn and over epsilon。Okay。And。Right， so this is true for all epsilon。

 So you can true， you can choose Epsilon however you want as long as T is like。

 say bigger than two line n， for example， you can pick。嗯。You can pick， for example， T2 B。

Se these two things equal by choosing Epsilon appropriately。

And this thing will be at most the min over eye。Some over tea。M I T。Plus root of lawn end。Over tea。

Okay。So， if you choose。Epsilon。To be。Root。呃。Law N over T。That's all right。I seem to be。Off somewhere。

Sorry。In the definition of Epsilon。Here。No， I mean， I want to say that if I play for a lot of days。

 my air goes down， right？こ出すように。Right。Oh， I see， okay。嗯。Oh right。 then yeah。

 So I guess normally people， people talk about maybe the average regret。

 And then that decays like whatever tea。 So， for example， if you look at the average。

The average thing here。The average。We'll go down like then I think this is okay。

So you'll often hear people talking about like， so this quantity here。

 the stuff beyond kind of the optimal bound you want。It's called the regret in some literature。

So people talk about trying to minimize regret。 So you'll often hear people talking about kind of the square T and。

Loss and regret。 Okay， so that's where this comes from。

 It's my particular choice of epsilon running multiplicative weights。So there you go。嗯。So now let's。

呃。Let's apply this to LP， so LPs。I want to have。So I want to check feasibility。Hes our ability。

X and P and AX is at least B。Where。P is some convex set。And a。Is an M by a matrix。

And I want to give a definition。So we will be considering。呃。Sub problems。Of the form。

Does there exist？An X such that P transpose A X is at least P transpose B。For P。

 a probability vector。Okay。A rowe bounded。Orracle。Is an algorithm？Which， when given。

When given this problem star。Either。Okay。If such an x exists。Output。An X such that。嗯。For all， I。AI。

t x minus B should be at most row。If no such x exists。You know， it outputs。Infeasible。Okay。

So notice that。If the actual feasibility problem， if this problem is actually feasible。

Then because the entries of P are non negative。This problem will also always be feasible。

 and also P transfer actually should be greater than P transfer B， and X is also in P。

So this feasibility problem is what the Oracle should decide。And I just said if that's feasible。

 then certainly this is because take an x， which is feasible for this。

 and then just put P transpose on both sides and by non negativity of P。This。Inequality will hold。

Questions。ベ当。Yeah， we assume that the oracle given so the Oracle is given P。The Oracle knows， oha。

 so it knows capital P， the convex set， it knows A， it knows B， and it knows little P。

And then it wants to know the Oracle will tell you。

