# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p24 P24 -BV1zNSCBkEgW_p24-

![](img/3ddd7169ad06ffe85fcaea44df37e5ba_0.png)

So today。We're going to finish。Faster exponential timing algorithms。Or small space。Specifically。

 we're going to do inclusion exclusion。I always want to say a few more words about that。

Slash Zeta transform。And Mobius inversion。And then。呃。

TheWell the remainder of the class as well as next lecture， I'll tell you some things about well。

 an area I work in， which is streaming and sketching。嗯。Okay。嗯。Let's get started。

 so I just want to write something I wrote on the board last time， which is this is a fact。

 we proved it last time this was inclusion exclusion。Which said that for all。Seets。R subset T。

We have that。The sum over all s's that are sandwiched in between。Of negative one。To the T minus S。

Is equal to。R equals T。Okay。Remember this is just one。

 whenever I put a Boolean expression in brackets， it means one if it's true and zero otherwise。And。

We defined thezeta transform， so if we have a function F。Mapping sets。Into。Some ring。

We defined F hat， this is thezeta transform of S was the sum over r subs equal to S of F of R。对。

And last time， what did we say？We said。Last time we ended with K coloring。Oh we have a scribe today。

 I think， yeah okay great。We said let f of x， let F of， let's say， S。B。嗯。An indicator for S。

Is a non empty？Independent set。In our graph。And then we had this claim。

Which stated that the graph G is k colorable。If and only if。

Let's say the sum over s subset equal to v， negative 1 to the n minus S。This is just。

If you want to say this differently， this is just the size of v minus S。Of。Let's say。F hat to the K。

His bigger。So I mentioned at the end of last lecture that this will let us do things more efficiently。

 and I also mentioned that。You can prove this claim using inclusion exclusion。

So the scribe actually put those。Well，ll put the details of why this claim is true in the notes。嗯。

I I am going to show you a proof of this claim， but I'm actually going to show it to you as basically just one example of something more general。

O。So you know， first of all， how would someone come up with this formula， right。

 it's one thing to just show you something and then have you prove it。

 but it's harder to come up with such things， right？

And I'm going to show you that the way that you would come up with this is basically via thiszeta transform Mobius inversion。

 which I'm， well， I guess I define the zeta transform， but I will define。

This thing here is called so thezeta transform， this F hat。And let me just include some references。嗯。

So first of all， this thing here， we're going to see soon。

You can compute it in either O star of3 to the end time。And poly in space。Or you can do it in。

O star2 to the N， time and space。嗯。And these are due to independent works。New Yorkland。And Husfelt。

This is Fox of6。And the other one is Covissto， I'm probably saying the name wrongg。Fox 06。

And actually， the former。The first paper the first of the two papers。I mean。

 these were two independent papers that were published at the same time， but the first paper。

This one。Can also get。Something like O star of。Two to the 2。461。Two to the two point。2。

2461 to the end time。And polyan space。And it's actually an open problem。

It's an open problem to get two to the end time or roughly two to the end time。With poly space。Okay。

So。Rather than prove that。Claim and talk about running time specifically for k colorability。

 I want to show you why this is。Just the kind of。Falls out of something more general。Okay so。

So we have F as before， meaning， I said， F maps。Seets to some ring。And I defined thezeta transform。

That was F hat。And then I also define the Mobius inversion formula。And I'll call that。F Tilda。

Told them S。Is the sun？R subset of s， negative1 to the size of S minus R。Okay。And。

Kind of the real place where this formula comes from and why it works。Is the following claim。

F hat tilde equals F tilde hat equals F。对。So clear what I mean， if you take thezeta transform。

 then Mobius invert it， you get F。 and if you do it the other way。

 if you first do the Mous inversion，And then do thiszeta transform， you also get。Okay。

 so let's prove this。And I want to show you just one of the directions。

 The other direction is very similar。 We'll show。That if you。

