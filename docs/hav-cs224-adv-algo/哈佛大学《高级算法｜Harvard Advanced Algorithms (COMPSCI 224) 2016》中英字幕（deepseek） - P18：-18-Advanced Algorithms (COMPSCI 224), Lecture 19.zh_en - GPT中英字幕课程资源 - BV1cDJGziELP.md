# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P18：-18-Advanced Algorithms (COMPSCI 224), Lecture 19.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/1154ac5df5ee504dbb680d120c1b1760_0.png)

🤧Okay。Right，I think it's fine。so。Yes we we finished。A lot of stuff on linear programming。

 so I covered simplellipoid into your point。Now I want to sort of transition into other stuff。

So it turns out the thing I'm going to cover today can also be applied for linear programming。

 and I'll show you that， but it's more than just a tool to solve linear programs。

And then once we're done with this， you're just not really going to see solving in your programs anymore。

 okay？Okay， good， so today what you're going to see is kind of multiplicative weights。So today。

I'm just curious has anyone seen what lookingative awaits before？Okay， so or rather I should say。

You know how to know。How to choose。You know， which expert advice？To listen to you。So for example。

 you like to trade stocks， there are lots of self proclaimed experts who tell you what to buy so that you make money。

And you're not sure which one you listen to。So you want to。

You you want some strategy for deciding which one to listen to。 Okay。

 and what I'm going to say is going to remind you of competitive analysis。 Well， actually， first。

 let's look at competitive analysis， so。So let's first before we get into multiplicative weights。

 let me just go into this listening to expert advice， so the setup。iss that？There are T days。

And experts。Okay。Each day。Each expert。Will'll say。Yes。Or no。Okay， so for example， will it rain today。

 will this stock go up in value today， they're each going to tell you what they think。

And then you have to decide。What you think the reality is， and then make a decision。Okay， so。So。

 we have to。You know， we have access。To all these expert opinions。And we have to make a decision。

And what we want， we want that at the end of the tea days。

 the number of mistakes we've made is small。So。You know， we won't be able to。Of course。

 we want some provable guarantee on how smaller number of mistakes is。But you know， this kind of。

 you know， if you don't define your。Measure of success appropriately， this is a hopeless problem。

 right because。might just be the case that none of the experts know anything。

 They're just saying random junk。 and then you're gonna say something。

 and then reality can hit you and say， oh， actually， it's the opposite of what you said， right。

 I mean， no one knows the future。 So what are you going to do here。So you know， what's the。

 what's the kind of。I guess I might have spilled the beans already。 You know， in such situations。

 you know， what do you usually want to measure success as？

know what's something that we've covered before that seems like a good way to maybe measure success。

Yeah， sure。 like so competitive analysis， right， So one thought。You know， be competitive。

With the best。Expert。In hindsight。Right， so at the end of the two days。

 you're going to look back and you're going to look at each expert and see how many mistakes that expert made。

 and you want to make sure that。You're not much worse than the best of them。Okay。So。

What's one natural？Yeah， so， yeah， you， so you， you have， you know， infinite memory。

 You can remember everything every expert has ever told you。 And at the end of the day。

 you see what actually happened。 You see whether or not it rained， for example。Okay， so。I mean。

 what's the， what's the simplest thing you can imagine doing in this model。Yeah。Yeah。Be even simpler。

 I mean， I let's not even look at histories。 So I I pull all the experts。 They all tell me something。

Yeah， just vote， like take a majority vote， right， So you know， simple， one simple algorithm。Yeah。

 we are gonna over， you know， over the lecture， we are gonna see how to。Get more complicated。

In terms of taking the history into account， but first let me just start off with something really simple。

 so a simple algorithm。Just take a majority vote。Okay， and then claim。If there exists an expert I。

Well let me if there exists an expert。That never makes a mistake。All。

 me actually let me I want to make one modification to the simple algorithm。

So we're going to take a majority vote。I'm going to take history into account in a very minor way。

I take the majority vote。 And if anyone。Is wrong。 And at the end of the day。

 if I realized someone was wrong that day， I just killed them。Or I stop listening to them。

take a majority vote。At the end of the day。Now， kill。All。Wrong experts。Okay。So the claim。Is that if？

There exists a perfect expert。Then we make。At most how many mistakes？yeah， when I heard something。

I heard log login， though， is what I thought I heard thats why。Okay， so let's login。

We make our most login。Mistakes。Or maybe I heard C log in。Okay， right， so the proof。Well。呃。Yeah。

 so the point is， every time we make a mistake。Most of the people were wrong。

 so wed kill half the people。Okay， so every day we make a mistake。You know， we kill half the people。

At least half。Of the population。Of the experts。So。That right end。We always have one person alive。

 namely the perfect expert。So the number of killings we can do。Is at most。Lo。Wrong days。Okay。

 but that's assuming there's a perfect expert， right， So normally in competitive analysis。

 I just want to say I'm competitive with the best expert， the one who had the fewest mistakes。

RightSo unfortunately， this algorithm。You can't just analyze this algorithm in that model because。

It could just happen that on day one， everybody was wrong。And then you killed everybody。 Now。

 who do you listen to from then on， right， So what。

 what's a modification of this algorithm if you want to be competitive against the best expert。

Till the worst half。I mean， let's say day1， everybody's wrong。 What do you do， Day  one。

And then maybe the best expert is right from day two onward， right。

 but now you don't know because you killed him。I mean， he's， he's not really dead， right， He's。

 we're just ignoring him。 Sos， he's not really， yeah， you can， you can go back to him。 But yeah。

 so what do you do。嗯。Kill at least half randomly。 Yeah， I'd have to think about。

I don't know off the top of my head what that would do。But。

Let let me suggest lead you toward a different algorithm。 So what's the problem with this algorithm。

 It's what I just said， right， It's that everybody could be dead。So one thing you do is。

IfIf you're ever in a situation where everybody is dead， you just revive everyone。是人。So。

So do as before。I don't know， Yeah， sorry， I just thought I don't know if people watching Ario。

 this Eddo tenee。No， yeah never mind so。Do as before。If everyone。Is dead。Then revivebe everyone。

And the claim。If the best expert。Makes。E errors。Then， we make。At most。E plus one。诶。Think log。

Base two of N errors。Okay。Do people believe this？And why do you believe that？Yeah。

All the other exposed。waitait， wait so we kill the so the best guy， we kill him at most E times。

 he said， okay。Right。Right。We make it most that many mistakes before we go。Right， yeah。

 exactly right。So the number of phases， like revival phases is e plus one。

 including the first phase when we just start。嗯。And then basically within that。Within that phase。

 we can make our most login errors before we kill everybody。嗯。Phass。When we kill。The best expert。

Re legible when we kill the best expert。Atmost log base。To n。Errors per phase。这一 go。Okay， so。

 it's something， but it's like a logarithmic competitive ratio， right？So， I mean。

 there's also this additive one， but if you ignore the additive one。

 it's roughly a log and competitive ratio。So。嗯。I want to do something better。

The question is how can we do something better and the way we're going to do something better is we're going to allow for some additive error in the competitive ratio as well。

Okay，Okay。So。You going find some rotation， let。呃。M T。Equal number of our mistakes。By。Yeah。Beginning。

Of。Da tea。And。A I， little MI T。Is the number of expert eyes。Mistakes by the beginning of dayity。

So I'm going to show you。We can get。There is a strategy。 There is an algorithm。

 which allows us to get。呃MT。To be at most， something like two times one plus epsilon。呃。

The man over eye。From one to N， basically the best expert。legible。

1 less than equal to I less than equal to T of Mi。This is let's say， T plus1。呃。

Let's say by the end of8T。Plus。Tan and。Over up。For any。Epsilon in the range from zero to a half。

So on the one hand， we can make can。Before we basically had- so this is like E。

Before we had roughly log n times E now we have roughly two times E。

 but then there's some additive error depending on how close we want to be to 2。

 as well as depending on this log n。 Anyway， we already had an additive log n。 So that's not。就感。Okay。

Any questions？Okay。You what's a natural thing to try？I know at a very high level， right。

 So what what's what's the， the thing we did here is pretty extreme right。

 which is once you're wrong， ever。You're just dead。Right。So。Okay， good。So。Yeah。

 what's something you can do that's a little less extreme than just killing people when they make a single mistake。

Yeah， trust them according to their past performance， right， So here we said that。

We're taking a majority vote。Right， majorityity vote usually means everybody has an equal little vote。

So we could。Weigh people's votes， according to how much we trust them。Right。

 and if someone's been making mistakes a lot， we should trust them less。

 but we'll still count them just not as much。Okay。So the idea。Is。You know， never。今日。

An expert just this for being wrong。Yeah， just。Trust。Tm less。Right， so。

We're going to have a weight vector， W， which starts off as the all ones vector。Of dimension N。 Okay。

 so this is like the。The weight in the majority。And。We will。Take a majority vote。

A weighted majority vote。Where expert I。Is weighted by WI。Okay。Okay， great， so we can still be wrong。

 now what are we going to do when we're wrong？So there are some experts here who。

We trust less now because they made a mistake。And we're going to decrease their weights。

At the end of the day。For each。Wrong expert。I。We're going to set WI。To be1 minus epsilon。Times w。

Okay。I mean， we sort of implicitly are。Just because。You， I mean， you could say。

You could say I'll decrease him by one minus epsilon and increase the others by one plus epsilon。

 But really， that's the same thing as saying。I'm increasing the other guys by the ratio one plus epsilon over one minus epsilon。

 and I'm not changing them， right。Yeah， without loss of generality。

 you can assume that you'll either increase the。The correct people and leave the others the same or decrease the incorrect people and maybe the others the same。

Okay。So。So this is the algorithm that I claim is going to get this bound。Yeah。So let's prove it。

So actually what I want to do is I want to let me introduce some new notations， so let's say WT。

Is the weight vector？At time， T。On dayT and the beginning of dayT。

And I'm going to define a potential function。F of T。

This is going to be the sum over all I from one to n to sum of all experts of their weights。

So in particular， on day one， the potential is N。Okay。Now。Now， what can we say？About。嗯。Fiti。

FT plus1 versus VT。On days。When we make a mistake？Right， yeah。Decreases by n by two weight。Or sorry。

 so let me write I just want to write down inequality。 so you're saying P T plus1。

And what's the inequality？Actually， I want to upper bound it。Or yeah， I want to up it。

So is there an upper bound you had in mind？You said。So I mean， I want to say so for us。

I guess what I want to say is， so the weighted majority is wrong。

Which means at least half of this weight has to be on the wrong thing， right？

So what I want to say is if you look at that half of the weight。The half of the weight decreased。

Right。By 1 minus epsilon。And the other half of the weight， I don't know。 I mean。

 they could have been wrong， too， but I'm saying at least half was wrong。And the other half。

 it definitely didn't go up。 It definitely didn't。呃。Go up。

So I can just say that' just let's say it stayed the same。As an upper bound。Which is equal to。嗯。

1 minus epsilon over 2。Times， V of T。唔。So now you can do an induction。And you can bound。嗯。

You can bound。Phi of t plus。 okay， so first of all， what don' I want to say。This implies。

By inductionuction。That feehi of t plus one。Is that most the original fee？嗯。Times。

One minus epsilon over two。Times the number of mistakes。That we make by time capital T。Right。

Which is equal to。This is just n。Okay， and for what I'm going to do next。

 I also want to use the fact that1 minus x is at most E to the。Minus x。

1 plus x is at most e to the x。 So x is my negative epsilon over 2。

 So this is at most n times E to the minus epsilon M。MT。Over two。Re good。

So this potential function is just going to serve as。Something that lets us get a bound， right。

 so we've now upper bounded the potential。Now I want a lower bound of the potential。

And I'm going to use kind of the weakest lower bound you can。Imagine， so say I is some expert。

 in particular， maybe I is the best expert。What can you tell me about P T plus one compared to。嗯。

And compared to the weight of the best expert。Compared to the weight of the ice expert。

We have VT plus one。I want to say is at least。Something。Well， it's the sum of all the weights。

And all these weights are non negative。So it's at least。WI of T。But what is WIFT？Yeah。

 it's 1 minus epsilon to the number of mistakes。Of the Ithe expert by time T。So。Actually。

 did I even want to do that？Exponential。Maybe not。 But so now I want to， I want to do one thing。

 I want to say this implies altogether that。This therefore is at most that upper bound。

So this implies that one minus epsilon。To the MI of T。Is that most？And actually， let。

 let me just stick with this one。嗯。N times1 minus epsilon over two。Times empty。

And now I'm going to take lawn of both sides。Then I get MI of T。Times the lawn of 1 minus epsilon。

Is that most？M of T。A lawn of1 minus epsilon over two。Plus， Law N。Okay。Now let's just remember。

A very small amount of calculus。Okay， so calculus tells us that。

write if you tailor expand some function， so FMX。Around， say A， so F of a plus。F prime of a。Times x。

Plus， and let's say you do it up to the linear term and you want to understand what the error is。

The error is。The second derivative at some point z over two。Times x squared。For some。Z。

In the range from a to x。Or x to A depending on which one's bigger。Yeah， thanks， whoops。All。So。

This tells us this implies。That。L。Of1 minus epsilon。Or a law of， say1 minus x。Is equal to。Minus x。

Plus an error term。Which is the largest derivative。So you take the function line of。1 minus z。Okay。

 so。Times x squared， so here I'm Taylor expanding about zero。And F of x is this law of 1 minus x。

Actually， F x is la of1 plus x， and then this is F prime of。Some Z。For Z in the range from。

 let's say， zero to a half。Okay。So。You can show that if you just bound the largest derivative of this function La of 1 minus x in this range。

 then you can show that this thing， well， certainly。

You can show that this thing is certainly going to be。Non positive。Okay。

And it's going to be at least。What's the worst case？I'm sorry。Yeah I think you can say that you know。

You can show。For x in the range from zero to half。L of 1 minus x。Certainly at most minus x。

 and it's at least， yeah， minus x minus x squared or something like that。Yeah。Basically。

 just for this Taylor's theem reason。Okay， so。So now you go back to here。And you say， well。

 this M of T。L of1 minus upps along over two。Plus's law n。Well。

 line of 1 minus epsilon over two is at most。嗯。Negative upps number two。Yeah。

 I guess I could have just taken a lot over there， but then for the other side。

 then you need to use this fact。嗯。And then on the other hand， you have this is at least。

Where we said MIFT。Land of1 minus epsilon。Which we said was at least。MIFT， well， negative epsilon。

Minus epsilon squared over two。M IFT。Okay， and then now。You multiply by the negative sign。

 you rearrange things， and you get the theorem。Okay。So that's the， that's it。O。

So are there questions about？The algorithm or anything about its analysis。Good。

So now I want to go even further。I want to make some generalizations。Some。

 let's say generalizations to the model。Okay。So。First of all。Let's say。At each step。We want。

Not let's say， not to。Not to not make a mistake。Not to be correct。But。To minimize。The， let's say。

 the probability。Now we're incorrect。Okay。So what I mean by that， I mean。

 in every day we're not going to choose an expert to listen to。

We're going to come up with a probability distribution over experts。阿一。On each day。We output。

Probability distribution。PT。Over the experts。So， we want。

Some from T going from one to capital T of the dot product。呃。Let's say。Am I of T。Dtted。With PT。

We want this to be small。So that's our expected。ItThis is the probability that we make an error。

 So imagine that MI is zero if we're right and one if we're wrong。Okay。Also。We will assume。That。啊。

Am I。T， so before we said that， it's in。It's either zero or one， right。

 the person is either right or wrong。Now we're going to assume that this is actually in the interval from minus1 to 1。

Oh yes。 Oh， good point， whoops。Okay， so。Yeah， this is。MT。Is is now。Yeah，The mistake。Vectctor。

At time tea。So。Am I selling right this over here？I imagining how that。MI of T is equal to1。

If expert I。Is wrong。At time T。And zero， otherwise， if he's right at time T。Yeah。

 so it's no longer the number of mistakes by time Z。Yeah， sorry。

I should have used a different letter before。 now it is kind of。Also。Will generalize。

instead of just saying it's binary。We'll say that MT， this vector MTt is actually。

In minus-11 to the n。And not just。0，1 to the n。Okay go。Right。

So you should think of a negative number as meaning。As being like a benefit。Right。

So we're trying to make sure that this thing is small， so negative numbers help us。嗯。

It's like not only was he right， but he was right and gave us $100 or something。Okay。So。

So the multiplicative weights algorithm。So we need to figure out what this probability vector is that we're going to output it on day T plus1。

We're going to say that。Pi。T plus1。S I。Is equal to。Okay。1 minus epsilon。嗯。응 응。Mftt。Okay。

And so this is just the generalization of what we already saw， right？Before MI was either zero or1。

If it was zero， then we didn't change this。 Think of now this P as being the weight vector。

Before if MI was0， this was just one， so we didn't change the weight at all。And if MI was was one。

 meaning they made a mistake。Then we decreased the weight by a factor of 1 minus epsilon。So now。

 we can also increase weights because of the fact that MI can be negative。But you could also imagine。

That's just the ease of a notation。 Okay， You could also imagine not actually。

Doing that and just keeping the ratios similar。Okay。嗯。So this algorithm。

 so I'm going to keep calling it the multiplative weights MW algorithm。So MW。It has been。You know。

 rediscovered。Over and over again。By different people with different names。In different fields， even。

So like economics。Theoretical computer science。When I say that， I mean， you know like algorithms。

 let's say。Machine learning。E cetera， okay， I'm not going to put all the references。

 but there's a book。Or monograph that。Goes into the history and also talks a lot about various applications and multiplicative weights。

So you can see a book see book。By。Aurora。Haazan。Color。嗯。Mly this is the monograph right here。

 So what year is that 2012？Okay， so。I'm sorry。This a。So again， we want to be competitive。

With the best。Expert。Before I start proving things， you got a question？Yeah， yeah。

It's really what I maybe should have said is。Yeah。But why't you also even be consistent of last time？

And then I'll say。PI of T is just the weight。Over with some of all weights。So theorem。坐的。嗯。

Now I want to say that multiplicative weights does well compared to the best person in hindsight。

So I'm going to say here is that the sum from T goes from little one to capital T of this dot product。

A I。Of tea dotted with。P IMT， where P is the thing that multiplicative weights outputs。Is that most？

嗯。This should be M of T。This should be PT， there's no I。There's no eye here。

M is a vector indexed by I。Okay， so this sum of expected costs should be at most。The sum。

T goes from one。To。To capital T。Of the number of mistakes of person I。

And then what we're also going to get is plus epsilon。Times。

The sum over t of the absolute value of MIFT。Plus。Law and over Epsilon。Right。

Questions about the statement of it。So let's start proving it。So proof。So again。

 we have this potential that I again set of there， so remember P of T。Is the sum。

Over I from one to end of WTI。And again， we can say the same thing as last time。Right。So I want to。

 I want to bound， I want upper bound fee and also lower bound fee。

 And then I want to compare those two things and then derive some inequality involving。

Involving how we do versus how。Versus how expert eye does。不是。So。Let's see how these things relate。

 So fee of。T plus one。Is equal to， by definition。The sum I from 1 to n of W IT plus1。

And then now we're just going to plug in the definition。 so this is equal to。The sum over I。Of WIT。

Times 1 minus epsilon MI of T。Right。Which is equal to。If I distribute this。

 the sum of WITs is just VT。And then here I have。The sum of。What is going on here， this is Epsilon。

So here this is just。V of T。Minus the sum over I。W I of T。Times MIF T。Okay。But what's WIFT？Right。

By definition relating it to P， this is just equal to。P IF T。Times。Phi of T， right？

So this thing here。Oh yeah， there's an epsilon。So this thing here。Is equal to。呃。P of T。Times。

1 minus epsilon。嗯。Basically。MT dotted with PT。Okay。And now I'm going to use again my favorite trick。

This is at most。V of T。Times E to the minus epsilon M of T。Dotted a P ofT。So， by induction。

This implies。嗯。That phi of T plus1。Is that most？Phi of1， which is n。Times。

E to the minus epsilon sum over t from1 to T。M T dotted with PT。你个。And then now again。

 we do the other side。And we're going to say。Also。V T plus one。Is at least？WI。嗯。W I T。

Which is equal to， what's WIT？Right， that's right， so this is equal to PI of T。Times。Well。

 so let me first， let me just write it in terms of。嗯。Yeah， so that's true。呃。But yeah， let me。

 So not express in terms of P， but just in terms of kind of。Basically， in terms of that。

 so let me write。呃。So I want to say what you get by induction， basically。Okay。

 so this is equal to1 minus epsilon。So basically the product。T going from1 to T。Of one minus epsilon。

MIT。sure I'm。Very good。And then now I want to use。Some calculus yet again。Oh。Yes。Okay。

 and this thing is equal as at least。Let me write this。1 minus epsilon。Times。The sum over。

Let's say the less。That least zeros M IF T。Times this product of one plus Epsilon。

 sum of less than 0。M I of T。Where。Sum of greater than equal to0。Is over。The I such that。M i t。

And equal zero。Some of the tea。Okay， and。Where does this come from？This again， is some more。

Calculus tricks， basically so。I'm not going to actually do it， so calculus claims。

I'm to sure I write it down properly。So。1 minus epsilon to the x is at most one minus epsilon to the epsilon x。

If epsilon， if x is in 01。And then also。1 plus epsilon to the minus x。Is at least。

At most one minus Epsilonx。X is in minus10。Okay， so the way that you improve these is actually。

The way I just realized the way I did it with Taylor's Theorem is a little clumsy。

 you can just use the fact that。For example。So E G the first bullet。

You just use the fact that the function F of x， which is 1 minus epsilon。

To the x is a convex function。Right。You just check it second derivative and it's positive。

So that implies。That， you know， F of。X， which is F of。1 minus x times zero。Plus x times 1。

Should be at most。1 minus x times f of0。Plus x times F of1。Right。

 that's what it means to be a convex function。 And then。That's exactly that。Okay， so。

So you can verify these things。And here I'm just applying that to。Right，This is my x。

 this is my 1 minus epsilon x。And then I separate into cases。

 either this thing I'm adding is positive or negative， depending on the sign of MIFT。

 So this is the cases when MIFT is positive or not negative。

 and this is the case when MIFT is negative。Today I just put things together。You say， well。

 phi of t plus1 is at most this quantity， and also phi of t plus1 is at least this quantity。

So this implies。That。One minus epsilon。A。S T， some better equals 0。MIFT。Times  one plus epsilon。

Some of less than 0 M IF T。Is at most？N times e to the minus epsilon。Some over T from1 to capital T。

Of MT dotted with。Pg。And then you just take lawns。And then rearrange things and agree。So。

So if you really want to see that calculation， I mean， there's really nothing more going on。

After this， you can look at the paper yourself， so it'll be in the notes。Quutionions。So now。

What I want to finish and this will probably carry on into。

The beginning of next lecture as well is I mentioned that this multiplicative weights thing is not only about the stock market and whether you can also use it to solve linear programs or approximately solve linear programs。

Okay， so。嗯。So， plot can。Smoise。Tarniish。I'Sa math operations research。So use multiplicative weights。

To。Approximately solved。Packing covering LPs。Okay， so remember I defined packing covering LPs。

When we're doing。I guess competitive analysis。s point。don't worry， though Ill when it comes time。

 I will remind you。So。So， now。You know， we'll show。嗯。How to use M W。You know， just for general LPs。

Assuming that you have a certain kind of oracle that I will describe。

 Okay so this this description is in that book as well in that monograph by Aurora Haan and Kala。So。

Set up。Is that we have。I want to check。If。AX is at least B。And。X is in some set P。Is feasible。Where。

P is a subset of RN。Is convex。Just remember， just means that if you take a convex combination of points。

 that stays inside of P。Yeah。And a。Is it。An M by N matrix。Now。If not feasible。We should say so。

Otherwise， we should find an x。Such that。嗯。X is in P。And。AX。

Is at least b minus epsilon times the all1s vector？Okay。Right。

 so we want AI dot X to be at least B I。 So what I'm saying AI dot X should be at least B I minus epsilon for all I。

So we're going to see that。Multipplicationicative weights。Assuming some other property of the set P。

 I mean， I didn't say anything about P but。Assuming that P allows you to do some things efficiently。

Multipicative weights will allow you to find such an X。嗯。Quickly， by quickly。

 I mean in a small number of days。Okay， so this capital T is， so there are no more days anymore，Yeah。

Abs。然。Yes， so yeah， that's a good point。 So I think we said before。You know。

 once you solve things up to really fine precision， like there was this L parameter before， right？嗯。

Then you basically solve the problem exactly。 the problem is that in order to get this kind of guarantee in multiplicative weights。

The number of iterations you'll need to do the updates， meaning this capital T parameter。

Is going to end up being something that's polynomial in whatever epsilon。

whereasas with interior point， we were getting away with something that was like login。

Law you want epsilon。Yeah， so。Yeah， it would just be extremely slow is the problem。Okay。

 any other questions？Yeah， actually so， that epsilon should really be like exponentially small and L。

O。Okay， so， you know， let me just give an example before we actually。Talk about how to use this。

 you know， how to use multiplicative weights to solve this。 So example。

Let's say fractional set cover。So。Let。L。I don' know when he' oh， let's say let's see。Alpha。

What alpha and R。Re such that。Alpha。Is。At least opt。Then we're going to set P。To be。嗯。Well。

 first of all。Let's write the LP down， so we want to minimize。The sum overall sets s of xs。Such that。

For all elements E。The sum over all sets containing E。Of excess should be。At least one。And excess。

Should be at least 0。For all us。So we have a set of elements we want to cover and we have a collection of sets S。

ok。So in the In program， you imagine each excess would either be zero or1 telling you whether or not you took the set。

 but here we relax it to a linear constraint。So as I described it here。There's no。

 there's no optimization。 There's no minimized linear forms。 This is just a feasibility question。

So the way you would use it for a problem like this is you would assume that you know an alpha such that alpha is at least opt。

And then you would set P。I mean， I didn't tell you what， you know。What you really need from P， but。

You would set P。Is the set of x's such that？Let's sayy x is at least zero。And。嗯。S over S X。

Is that most alpha？Okay。So you don't actually know opt， right， So， you know， what would you do。

 Supp that you had a way of deciding now the feasibility question。 Now you want to now。

 you want to figure out。If let's say these constraints。If the star constraints。Subject。

Its x being in P。It's feasible。So that's the way we're actually going to use multiplicative weights。

 but you don't actually know this alpha， right。So， you know， what would you do？

Suppose you had a way of deciding feasibility of this。What would you do to actually？

To figure out the optimal。Valuing now for。Yeah， binary research， right， so binary research on alpha。

And alpha is anything between， let's say one and the number of sets。

So this is the number of sets in your collection。So goodbye in research。

And then at the end of the day。You know， what would you get if it were feasible？You would actually。

 you would be off by this。By this epsilon， right？If feasible。You would get。X such that for all E。

The sum。Of excess is at least one minus epsilon。Right， so。I don't know， so people will recall。

One way to get an approximation algorithm for set cover is to solve the LP relaxation and then do some randomized rounding of sets and choose them according to the probabilities X of S。

So that， you know， that's one reason you might want to solve this LP to then feed it into that randomized rounding algorithm to approximate the actual integral set cover。

But the problem is。This is not a valid。 This is not a feasible solution for the， for the relaxation。

 Right， So， so what would you do to make it a feasible solution。Yeah， just rescale， right so。

Final solution。Not feasible。Perhaps。But。X over1 minus epsilon is feasible。And it achieves cost。Well。

 the cost is this dot product。Well， the cost is the sum， sorry， the sum of the excesses。

And before it was in P， right， So we knew it was the almost alpha。

 it achieves cost some of our excess。At most。嗯。Over1 minus epsilon is at most alpha over1 minus epsilon。

 which is equal to1 plus o of epsilon。Times alpha。So you're getting an approximation algorithm anyway。

 you're getting a law end approximation。And now， if you use multiplicative weights to solve the LP。

 you would get a long n times one pluspsilon approximation。Right， and the point is。

 you wouldn't have to run。 So we'll， we'll see what you actually need to do in the multiplicative weights algorithm to。

To， to get this。To get this x vector here。But the point is that it's to be a fast algorithm。 Okay。

 It's not going be as slow as you know， ellipsoid or interior point， et cea。不是。

So are there other questions？So this is， this is the end of。That set cover application。

So now let me get to the analogy。Okay。So。I'm going to set。So。Given some X。We'll define。Am I。To be。

The cost vector。To be。呃，AI。Dot x。Minus B。Okay。Where。Wait a second， what I want to say。

I want this to be in minus11。So。o k。So let me think。

 I guess I'll get into this normalization next time and confuse myself about。

 I want this to be in the interval from minus1 to 1。But the point is。

So this is going to be some positive or negative number。 So if it's positive。

 that means the constraint is actually satisfied， right so each。Each constraint。I。e。 row of a。

Is an expert。And。So it looks weird because。Positive Ms were supposed to correspond to mistakes。

 whereasas here， a positive MI means we're actually satisfying this constraint。

But the point is you should think of the experts as telling you whether or not they think constraint I is hard。

Okay。I think that's the right way to think about it。 So that if it's positive。

 then you've satisfied the constraint。 So it's not really that hard。 Okay。

 and the the more you've satisfied it， the bigger the slack is， then the easier it is。

 which means the more wrong that expert was。Okay。But really。

 what matters more is think about how multiplicative weights treats experts who are wrong。

 it weights them less。Right， so multiplicative weights is trying to figure out multiative。

 So eventually。You know， we want。This approximate feasibility up to this epsilon over there， right。

 eventually we want approximate feasibility。So multiplicative weights。You know， wants to。

Focus all its weight。On constraints that are not yet satisfied。Right。So the point is。

 if something is very well satisfied， we're going to spend less effort on it from now you know。

 in the future days， the future iterations， whereas if it's already satisfied， if it's not satisfied。

 then we're going to pay more attention to it。So。Yeah。

So I guess next time it's now for next time I'll actually give you an analysis to show you。

The number of iterations you need on multiplicative weights to get this kind of approximate feasibility guarantee。

 and also what property do you need from P， eta。So。That's Thursday。And I guess that should not take。

Too much of the lecture， and then we'll start something here too。No more of solving LP at all。

