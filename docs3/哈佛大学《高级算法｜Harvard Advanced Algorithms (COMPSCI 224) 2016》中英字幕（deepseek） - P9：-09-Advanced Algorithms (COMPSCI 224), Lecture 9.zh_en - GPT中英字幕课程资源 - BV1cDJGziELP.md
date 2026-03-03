# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P9：-09-Advanced Algorithms (COMPSCI 224), Lecture 9.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/2052bb155cf07df3a05a22f8f281c01c_0.png)

Okay， let's get started。So today I want to actually show you the details of the analysis of the Mark algorithm。

嗯。That's the randomized algorithm for paging， which gets log K competitive ratio where k is the size of the cache。

 can people hear me？Do you have a  Scr today？系0啊。And then I want to show you。

Kind of a generic framework。For analyzing。Aly and coming up with online algorithms。嗯。

Based on this is a primal dual framework， as it's called。

 this is something that was developed by Bo Binder and Naor， I guess， in 2005。Okay， so。Today。😊。

We're going to see。2 HK。Competitiveness。For randomized。Paging。This is。The mark algorithm。

We'll also see。Online primal duall。And as an example of how you use this to develop good online algorithms。

I will show you again， the ski rental problem。So remember。Last time we saw for the S rental problem。

 you can get a too competitive algorithm。Okay。I'll reshow you that same algorithm。

 but in this primal dual language， which I haven't defined yet， okay。

 that's just an exercise to get you comfortable with the language。

And then I'll show you that you can actually beat the ratio too。Okay。

 if you allow yourself to be randomized， so you can actually get a competitive ratio of e over e minus1。

If you use a randomized algorithm。Okay， and that's。That。

That result is not due to Big Binder and Noor， it was already known before by Carlin and others。

 but it falls out more naturally from the primal dual framework。

And then we'll also see- so we'll see here E over e minus1 competitive ratio。And we'll also see。

Online set cover。So there。There are these M sets。But in the beginning。

 you don't know what items are in the sets。 You just know their names。 They're set1。

 set two up to set M。 And online， you see an item。 you see the items one by one。

And when you see an item。And。You have to make sure it's covered。Okay。

 so if it's not already covered by one of the sets that you chose， then you need to pick a set。

And cover it okay， and at the end of the day， you want to compare yourself to opt。

So I'll maybe say a few words about Se cover before I give that。Analysis。

 but I hope who here has seen set cover。 I covered it in CS S 124， Who has not seen set cover。 Okay。

 so I will define。I will define the problem， okay， who here has another thing。

 so this is also something in 124。I wish I'll do a very brief recap。

 but who is seen when you're programming？Ki。W has not seen linear programming。

 who doesn't know what a linear program is。Okay， so。I'll give a very brief introduction。

So this whole online primal dual thing。呃。Is built around linear programming so linear programming formulations of problems。

 so I will say a few words about LPs before I get into that but。So it's all about LPs。Okay， so。

The mark algorithm。This algorithm is due to Fiat and others。Journal of Algorithms， I think 91。Okay。

 so remember how this works， this is a particular implementation of the one bit LRU from last time。

 but when we evict an unmarked page，We choose an unmarked page uniformly at random from the set of all unmarked pages。

Initially。All pages are marked。Okay。Wen。When we bring page P。Into cash。We're going to evict。

A uniformly。Random。Unmarked page。Then。Mark P。Now it may happen that eventually all the pages are marked。

If all of the pages are marked， so there is no unmarked page to evict。Unmark。All of them。

And we'd like to say that expected the competitive ratio of this randomized algorithm is two times the K harmonic number。

 remember this number here is1 plus1 half plus1 third plus dot dot plus1 over k。

 which is natural log of K up to a constant。You can see this by comparing the sum to integrals in both directions。

Yeah。Say that again。Yeah， unmarked， thank you。Although to be honest。

 doesn't really matter in the beginning yeah， because you just unmarked them all well。嗯。Okay。

And all these are marked during a request。Then outside of cash。Okay。

 so the way that we are going to analyze this algorithm and I think I。

I started saying this at the end of last lecture， but I didn't get to actually prove anything。

Is it going to divide time into phases？😡，Okay。A phase starts。When don't we unmark all pages？

And a phase ends when all the pages are marked and someone is just about to make a request to a page outside the cache。

 so we're about to unmark all the pages and start a new phase again。Okay， so。Analysis。

We'll divide time。Into phases。A phase starts。When we unmark。Our new phase starts。

When we unmark all pages。Okay and I think I defined two terms that are going to be used in the proof at the end of last lecture。

 but I'll remind you， so definitions。Okay， so。A page。Is。Clean。

And let me call them you know I don't want to write Mark all the time， so for me。

 M is the Mark algorithm。Algorithm M is Markck。So， a page。Let's say page P is clean。🤧K。If。P wasn't。

Requested。So being clean is also time sensitive， you're clean at a particular time。

So a page P is clean at a particular time if P wasn't requested in the previous phase。And。Not。

Yet requested。This phase。Okay。And another kind of page that we're going to look at is a stale page。

 a page is stale。If it was requested。Last phase。But not yet this phase。Okay。

So except for maybe the last phase， how many distinct pages are requested in a phase？Okay， okay。

 so let' let's give us let's。Let's introduce some variables。L。The number。Of， let's say， LI。

 the number of clean pages。Requested in phase I。And let。I can even call it S。B number of stale pages。

Requested in phase I， and we know that Si is just equal to K minus li。As you just said。🤧嗯。So。

We're going to introduce some more notation。Okay。So we need to compare optt。😡。

Against M against the Mark algorithm。And we're going to do it phase by phase。Okay。

 so we're going to say that phase by phase， the gap between them is a factor of two times h sub K。

Plus， some stuff that telescopes。Okay， across phases。So。More notation。Let。Di。Be the number。Of pages。

Let me make sure I。Don't mislead you。In Ops memory。

Let's say DI DI is the number of pages an opt memory。At。Beginning。A phasei。Which aren't。

In Mark's memory， Mark's cash， I've been saying cash， let me be consistent。

So this is some non negative number。And。Let DI prime。Be the number of pages。呃。At the end of phasei。

Right。In particular， DI。Prime is just d sub I plus one。Interrupt me if you have any questions。

So what we will show。Optt pay。At least。呃。Think I want to say one half。L。plus。Plus D prime minusDI。

In phasei。That's the number of。Misses， cash misses that opt has。And 2。Expected。Cost。Of Mark。

In phasei。Will be at most。呃。HK times L。And it will follow from this y so one implies。Over。

Whole sequence。Ot pay。Let's say the sum over I。Well。All over two。Plus， this is just D+1。Minus D。

So this is just the similar I of L， well， let's say L。LI over to。Plus D final。Minus D initial。

So what's the initial？I didn't say it， but 0， right， So I'm assuming。I'm assuming that。

O that everyone starts with the same contents of cash in the beginning。 Otherwise。

 there's no hope to be competitive because optitete start with all the things you're about to ask for and you start with none of the things that you're about to ask for。

 right， So we're assuming that they start with the same things in memory。

 which means that initially there are there is no difference。So opt pays at least this。

 this is positive， so this is certainly at least the sum over I over 2。So I say it again？Yeah， yeah。

 Thank you。Whereas this is paying HK times the sum of LI。So the gap is a factor of2 times HK。Okay。

And in that paper by fiat at all， there's a lower bound which says that no randomized algorithm can do better than HK。

Okay。So you could ask， well， is HK achievable， and in fact it is， there's a paper by。

 I'll write it at the end of this。By McGock and Slater。

 two names we've already seen that gave an HK competitive algorithm。

 which they called the partitioning algorithm， I'm not going to cover it。And afterward。

 there was another simpler algorithm。Given by occliopusid all。

 that also achieved HK competitive ratio。 Okay， so I'm not going to go into either of those， but。

I'll insert that into the references of the electron notess。Okay， so one。Okay， so。Proof。

We'll show that。Ot pay。Actually， the max。Of。LI minus D。And D prime。

And the max is certainly at least the average。That's where we lose the factor of two。Okay so。

Why does it pay？At least li minus D。🤧。Well。I mean， it's almost immediate from the definitions。

 right so。Remember。The Mark algorithm doesn't have any of these clean pages in its cache at the beginning of the phase。

So for each of these clean requests， the mark algorithm has to bring it in to service the request。

Whereas。How many of these clean pages can optt possibly have in its cache at the beginning， well。

 DI because it only differs on DI。Right so。Opt。Only has。It most DI clean pages。

At the beginning of phase。And why does opt pay at least DI prime？Something。Simple。Okay， so。うんうん。

So tell me at the end of a phase。Describe to me， what are the pages that Mark has in its cache at the end of a phase？

Yeah， the set of pages that were requested in that phase， right？And you're telling me that opt。

It doesn't have exactly that set of pages in its cache。 It has some there's some difference。

 It has some DI prime pages besides the pages that were requested in that phase。Okay。

So it's essentially operating on the cache。嗯。Well， that means that for DI prime of those requested pages。

 there had to have been an eviction。Okay，At the end of phase。Mark。Has a set of pages。

Requested in that phase。And it's cash。And Opt also had to bring those pages in。

RightSo if there are any differences from that， it's because there was an eviction。So any of opts。

D prime。Differing。The prime my differing pages。Corsponsdent eviction。Okay good， how about two？Okay。

So。There are two types of requests that I'm going to look at， which are clean ones and stale ones。

Okay。In fact， those are the only kinds of requests which can cause an eviction for the Marquee algorithm。

Right。Only clean。And stale requests。Cause eviction。For Mark。Right because。If you you if you've。

 what does it mean to not be cleaner stale， it means you've already been requested in that phase。

 which means Mark already has you in its cache and you won't be a cash miss。So。Mark Pays。

How many evictions are there for clean pages in the Mark algorithm？LI Mark Pay's LI misses。

For clean requests。I mean， clean means it wasn't asked in the previous phase。

 which means that Mark doesn't have it in its cache。

 so it has to evict something to make room for it。So now。

 we haven't said anything about randomness yet。Now we're going to talk about。嗯。

What happens with stale requests？So。呃。There are。Okay so let's say。Let's say。We have had。

S stale requests。And。See clean requests。So far。So we're at a point in time。

We've had this many requests so far in the current phase。

And we're about to make the next deal request。So what does cash look like？So。

So let me draw M's cache。So， size K。So。How many of those clean pages are in the cache？All of them。

So nothing that's been requested in this phase is kicked out。So。This is all taken。See clean ones。

Are taking up spots in cash Also the same things is true for the S scale requests that have happened already。

Right， those S guys are also in cash now。E still。So。What can you tell me about。

 what kinds of pages are these？The pages that are left here。They're stale， exactly。

 they've been requested in the previous phase， but not yet in this phase， they're stale。Okay。

What can you tell me about，Remember， when these things are brought in， random things are evicted。

So this is a random set。Of stale pages that still exist。Right。Okay。So。This is a random set。

Random subset。Of the remaining stale pages。And what's its size， Well。

 its size is just whatever's left。 K minus S minus C。Okay。So。Probability that so the expected cost。

Of this。New stale request。Is just the probability that。This page。Hasn't。Been kept。

Which is equal to1 minus the probability that has been kept。And what's this？Well。

 initially at the very beginning of the phase， there were K stale pages。😡。

All the pages from the last phase。So。What's the chance that our one page？

Is one of the K minus S minus C pages that are left。 This is just K minus S。I feel like I。And。

Not saying the right thing。So I want to say the page that has been probably that it's been kept。Is。嗯。

If you assess going to C or K， but that doesn't sound right to me。So I seem to have。

Said to myself that this thing should be c over k minus S。Okay。Sorry， Siian。キまさ。Yeah， yeah。

 that's exactly Okay， good。 Yeah。 so okay， good。 So there there have been S sta requests。

 which means there are K minus S sta pages that still remain， okay。And so the question is。

 what's the probability that one of these C clean requests clobbered me？And that's c over k minus S。

 Okay， good， I'm not going completely crazy。Okay。Which is certainly at most。

 let's call it L times 1 over k minus S。Okay。Okay， good。And remember now S。

 the number of ST requests we said was k minus Li。So S is ranging from zero。Up to k minus。Lli -1。

Right， let me just write that here。F I start a new thing。So expected。cost。Of all stale requests。

Is equal to or is that most？L times the sum going from s from 0 to k minus li minus1。Of。

1 over k minus S。Which is exactly。The sum， L times the sum。From。呃。Jay goingang from。

So it starts at li minus1。Oh I plus one。Right up to K。Of1 over J。So when s is 0， this is 1 over k。

 is when s is 0， this is1 over k， when it's this， it's li plus 1。

And this is exactly equal to the L times， the K harmonic number。Minus the。LI plus first。

Harharmonic number or the L harmonic number。Okay。Which is certainly at most- this is L， L。

 which is certainly at most LIHK minus Li。So。That。Cances that。

And the total cost in a phase is exactly li times HK。Okay。Questions。So I'll say something about。

 you know maybe an open problem， there are final projects in this class。

 so I'll say something about that and also you know things that have been done since then。

 and then I want to move into this primal dual stuff。Oh， and。

Maybe I also want to show you why you can't do better than I won't get the right constant。

 but why can't you do better than log K？why can't you do better than a log K competitive ratio？

Let me say something about that。It was also in the fi at all paper。So the theorem。Any eg。

Has competitive ratio。Omega log K。Okay， proof。Let the number。Of pages。In the universe。B K plus 1。

Okay， and。Our request sequence。Is uniformly at random。Length。嗯。Okay。

So what's the expected cost of any algorithm？Sorry， for to serve the entire sequence。

 so we have the sequence of length M。At every stop。

 the request is a totally random page from one up to K plus1。Sorry， M what？呃。

I like what you said except for the times k。So I claim right the expected cost。Of any algorithm。

Is exactly。M over K plus1。When a new page comes。I have to pay an eviction if that's not one of the pages I'm holding。

 but it's a uniformly random page out of K plus1 pages I'm holding only in K of them。

So the probability that I don't have this page is exactly one over Ks one。Meanwhile， optt， right。

 opt， even though it's a random sequence， Op gets to see the entire random sequence。

From the beginning。Okay。Opt。Gets to see。The entire。Random sequence。From the beginning。

Or maybe the right way to think about this is。What I really showed is that。For any algorithm。

 no matter what your algorithm is。There exists a sequence， a request sequence of a length them。

Such that your algorithm will pay this on that sequence。So there's actually one sequence。

Which will trip up your algorithm。In particular， a random sequence is expected to。

 So there exists a sequence， which will。 Okay， so that's what this means There is for any algorithm。

 there is a sequence which will trip up your algorithm and make it pay this。A lengthham sequence。

 Meanwhile， I claim that no matter， I claim that。For this random sequence， Op doesn't pay that much。

Why。So。Let's say that optt now has an eviction。Right。So what is optical going to evict， I mean。

 I claim that the min algorithm was optimal。 you don't even need to know that it's optimal。

 but consider the algorithm which evicts the thing farthest in the future。Okay。

 so it has something that it needs to evict。 it's going to evict the thing farthest in the future。

What has to happen？For me to see that page in the future。😡，Every other page。😡。

How to have been requested before that page？So the question is if I'm picking random numbers between 1 and K plus1。

How long does it take me to see every single number？Which is known as the balls and bins problem。

 I'm not going to analyze it， but you need K log K。

Basically K log K numbers in order to see everything， that's called the coupon Collector problem。

When opievics。When OpV page， OpVA page P。It doesn't fault again。Until P is seen again。If。

We evict the farthest in the future。That implies that all other。Pages。We're seeing。Before P。Okay。

And the expected time。To see。All numbers。In the set1 up to K plus1。Is。Data k log K。So。

You can view this as saying any algorithm will。Falult， at least a1 over K fraction of the time。

Optt only faults a1 over K log K fraction of the time。So opt is better than you by a factor of log K。

J。If you're uncomfortable with the fact that the sequence is random， look， you can say。嗯。

The expected cost is at most this。So in fact， two thirds of random sequences。

Will make you cost at most 3M or let me say like this。 expected cost of any algorithm is that。

Let me he， let me。Maybe may you a little more careful。

 but basically the point is you could try and give a concentration argument and say that there are actually a good fraction of pages that make you cost around this。

And there are a good fraction of pages for sequences for which this is true。

 a good fraction of sequences make you pay around this。

 a good fraction of sequences make you do this。 So there's something in the intersection。Anywaywhere。

That's all I wanted to say about。Analysis for randomized paging。

And I did mention that in what's after this。嗯。There's MGa and Slater。In Alrithic 191。Achiieveed。

Competitive ratio exactly HK as opposed to 2HK。And there was a simplification later in Oliopus et all。

Both。A different algorithm and a simpler analysis。That was。Theoretical computer science。In 2000。

One other thing which as far as I could tell， seems to be open。But I can't。Yeah。

 papers didn't mention it as being an open problem。

 but I couldn't find any reference which actually solved it。Which is suppose。So was opt。Has cash。

Of size H。Whereas you have a size of cache K。So remember with LRU， I said LRU is K competitive。

But I didn't prove it if you have a cache of size K and optt has a size of cache H。

 then LRU is actually K over K minus h plus1 competitive。

W which means if the opt has half the cache to work with， then you're too competitive。Okay。

 so you could ask the same thing for。You know， the randomized setting。

So if optt has a cache of size H， then。Neil Young。In soda of。Soda of 91， I believe。Showed。

You can get。2 HK。Over。Actually。What's the exact bound， too long carry， too long。

Two times long of k over k minus h plus1。Competitive。

And he also showed that getting competitive ratio better than la of k over k minus H plus1。

Is impossible。So when H equals k， that's what we just covered， when H equals k。

 that gap of2 has been closed by MGoc and Slater。But when you introduce this resource augmentation point of view。

 resource augmentation。Is the phrase of the jargon that's used for you have a cache of size K and opt has a cache of size H。

Under resource augmentation。It seemed like that gap of two has not been closed because， in fact。

 Young's paper cites this paper。So it came after it， he knew that the gap of two was closed there。

 he even mentions it， but he has the gap of two in his own paper。嗯。

It seems like an open problem as far as I'm aware。Okay。哎。嗯。I'm not really going to get into it。

 but paging is actually a special case of a more general problem。Called the caseover problem。So。

 paging。Its a special case。Of what's called the caseover problem。Which itself has。嗯。

Quite a long history and some big open problems。So the idea here is。Your algorithm。Controls。

K servers。And also there are endpoints。There is an endpoint。Metric space。

just think they're endpoints in a distance function。So request sequence。Is a sequence。

Called this metric space X is a sequence of points in x。And。When someone requests。

A point P in this space。Must move。 You must move。A server。To lie on P。

So your K servers are always living on some K points。 and then when someone requests a point。😡。

If a server is already on that point， you don't have to do anything。

 if a server is not on that point， you have to choose which server to move there and move it。😡。

And what do you pay， you pay the distance。😡，If it's already at some point Q and you're moving into to P。

 you pay the distance from Q to P。Okay， so and you want to compare yourself to opt。Okay。嗯。

So 2 k minus1。Competitive。Deterministically。Is known。This is due to。Papa Dmitri and。

Did that write it down。This is called the work function。Algorithm。Maybe I didn't。Right the reference。

This is kuppias。And Papa tomi true。And this was in JCM 95。

And it's known that you cannot beat K competitive。😡，With a deterministic algorithm。

 So there's a factor of two there， which has been open since。You know， back in the day。

 This is the journal version。 The conference version was even earlier。

 So getting rid of that factor of two has been open for。More than 20 years。So you could ask again。

 can we do better than k or theta K with a randomized algorithm？So an open question。

Is the get a randomized？Algorithm。With competitive ratio。Polylo K。In fact。

 I think people believe that the right answer should be log K， just like for paging。

And there was quite a big breakthrough in this area very recently where they didn't get polylo K。

 but they got polylogue K， polylo N。Bonal。Bookbender。Madrie。And not or。This was just in 2011。

They achieved ratio。Which is。呃。Lg K squared。Log n cubed。Log， log in。Okay。

 so it has a dependence on n， but people believe that there should not be any dependence on N。

 You should be able to just get polylogue K。Of course。

 you can get a dependence on K independent of n。But you know it。There's that K。

 I think randomized you might be able to beat that。But still， it's not anywhere near Polylogue。And。

I don't know all the details of this， but I'm fairly sure that it uses the primal dual framework of bookbinnder not what I'm about to tell you。

哎。Oh， and。People see why this is a generalization of paging。So the endpoints are your pages。

What's the metric， what's the distance between two points？It's one。 all the distances are one。嗯。

Another generalAnother thing more general than simply paging。

 but less general than case server is weighted paging。😡。

So the idea is not all pages are created equal。Okay， so some pages live。On the network。

 it's some other machine and you have to pay a lot to like bring them over the network。

 whereas some are in your local memory and bringing them into caches faster。

 so pages have weights and you can look at weighted paging。

Where to bring a page into cash costs its weight。And that's also a generalization of I mean。

 that's also a special case of case server， so what's the distance between2 points P and Q？

In weighted paging。The difference in weights。At the end of the day。

 I'm going to pay the sum of all distances。So it's actually the average of the weights you can set up to be WP plus WQ over 2。

So when you sum all the moves， the overt twos add together and you get WP。

 I guess except for the very last thing， but you can sort of augment the problem so that you always move somewhere that's。

You always start somewhere with weight  zero and in somewhere with weight zero， let's say。Okay。Good。

 and that also definitely uses。The primal dual framework that was done by。

Bonal Bookbinder andauur in Fox 2007。They get a log K competitive ratio for weighted paging。Okay。

 good， so let me now go to Prial Dul。So the online。Primal。Doual。Framework。So primal dual。

 in the context of just algorithm design， especially approximation algorithms。

 is much older than Bookbnder。or。But the application of it to。

The online setting to get good bounds on competitive ratios， I believe， is due to Bookbinnder notor。

 this is Bookbinnder and Nutor。In。And while the journal version is an '09， I think it's math。

 something rather some operations research journal。 Well， definitely the conference version is ESA05。

 I'm forgetting the journal version。Okay。And before I talk to you about the primal dual framework。

I need to explain， remind you about linear programming。Okay。So。First off。

We need a linear programming。Recap， I'm going to call LP for me stands for linear programming or linear program depending on context。

So we want to。An LP looks like minimize。A linear function of x。So c dot xc is a vector。

 x is a vector。Subject to some linear constraints。Subject to。AX is less than or equal to B。

A is a matrix， x and B are vectors。And X。Is non negative。Coordinate wise， component wise。

 that's right。So in fact， I'm not going to do it。But， in fact， you。

 you could say you could imagine different kinds of constraints here。

 like some of the components you wanted to be less than equal， some you want greater than equal。

 some you want equality。You can imagine also not having this non negativity constraint。

That would be a more general class of LPs。Okay， but in fact， any any。

Program with linear constraints can be converted to this form by introducing possibly some number of new variables。

Okay， so maybe I'll put that in the homework， I don't know。So。For me， this is an LP。😡，Okay。

And their framework works for what's called。Covering and packing LPs。So。We say。An LP。Is a。Covering。

LP。If。All entries。Of。A， B， and C。Are non negative。Okay。And。

How many people have seen LP duality or know what a duall means in LPs？Okay。

 how many people have not seen LP duality？Okay， so some people have not seen it。Okay， so let me。

Let me now give you a little。I don't want to just define the duel， I want to motivate it。So。

Corresponding to any LP， there's another LP called the dual LP。

OkayAnd know what is duality all about。 So basically， so here I'm solving for x。

 I want to minimize over x。This is over x， not cover X。Now， suppose I want。

I want to say that I want a lower bound on the minimum。

 I want to say that no matter how you choose X。😡，I promise you that you cannot。Minimize。

 you cannot make C transpose X smaller than something。

I want to get the best lower bound I can on C transpose X， where x has to satisfy these constraints。

What's a systematic way of proving to me that you cannot do better than this？😡，Let's write this out。

 so we have our LP which says we want to minimize the sum over I of Cxii。Such that。

Let me write it as CJ Xj。Such that。For I going from1 up to M。😡，So remember。

 so think of a as being an M by n matrix。😡，So here we have A being the matrix AIJ。

 where I goes from1 to M。And J goes from1 up to n。We have that for all I， the sum。Sorry。

 I meant to say this is at least B。At least for the way I want to。Praise it， okay。I mean。

 I mentioned in LP， it's equivalent you always just。You could always just multiply both sides by -1。

But。嗯。I'm putting all LPs in this form， and then I say that it's a covering LP if this is true。O。

So for all rows of A， I want to make sure that the dot product of the I throw of a with x is at least B。

 so the sum over J from1 to n of AI J Xj。Has to be at least B。And also for all I。

Xi is at least or for all J。Xj is at least0。Now I want to prove to you that。嗯。

You cannot minimize this beyond a certain threshold。So what's one way to do it？😡，One way to do it。

Is to multiply both sides of inequality I by some。Value Yi。😡，Right。As long as Yi。

As long as Yi is not negative。The direction of this inequality doesn't change。Right。Now。Furthermore。

There's going to be one such Yi for every inequality， and then I want to add up。😡。

All these inequalities over all I。Okay。When I add up these inequalities over all I。😡，I have。

On the left hand side。I have some linear combination of the x's。😡，Right。Okay。So。う。

So suppose I introduced this why。 so I'm saying now that。

Is basically- so if I sum them up over all eyes， that means y transpose。AX。Is at least Y transpose？B。

Where I have as before。X is bigger than equal to  zero coordinate y。

 and also y is bigger than equal to 0。 As long as y is bigger than equal to 0。

 I don't change the sign of the inequality。Now this， what is this， this is some。

Dot product with the X vector。😡，This is equal to。嗯。A transpose y。Transpose。X。Right？

So what I've just shown is that。This implies that a transpose y。Transpose X is at least。

Yhy transpose B？Wouldn't it be great？If this vector in here， if a transpose y。

Wouldn't it be great if that were equal to C？Then I would have just proven to you that no matter what you do with your x。

 no matter how you choose X， C transpose X will be at least Y transpose B。

I've proven a lower bound on how well you can minimize this。Right？So。In fact。

 it doesn't even need to be equal to C。😡，But。Suppose that I show you that A transpose y is at most C coordinate wise。

That would also prove a lower bound because x is non negative。

 So if a transpo if a transpose y dot x is big， then C dot x definitely is also big。

So that gives rise to what I'll call the duall in your program， which is。

Try to find the best lower bound you possibly can。 This is the lower bound。 So the dual。

Looks like you want to maximize your lower bound over y， maximize B transpose y subject to。

A transpose y。Is。At most sea。And y is at least zero？And by the way。If。A， B and C are all bigger to0。

 This is called in the literature， this is called a packing LP。

So the duall of a covering LP is a packing LP。So theorem。This is called the weak duality theorem。

It says that if opt。P is。Min value。Possible。In。This is called the primal。😡。

So this is called the primal， that's called the duall。

If upP is the min value possible in the primeole。😡，And Op duel。

Is the min value possible in the duall？What's the inequality that we've just proven？

How can you relate opttP to optD？Opdi is a lower bound of upP。 That's exactly how we define the dual。

 The duall is a way of getting lower bounds on the primal。Then。Optt P。Is at least up to D。

 This is called weak duality。Yeah， Max。I got a little carried away with。Carries。Okay。So。🤧う。Good。

So the way the primal dual framework is going to work for us。

Is we're going to write down an LP to capture whatever we're trying to minimize。 So for ski rental。

 minimize the number of dollars you spend。Okay， and。As I'm going to show you。

Every day when you decide to either rent or buy， a new constraint is going to be introduced into the LP。

And you have to make sure kind of online that these constraints are satisfied。Okay。And。

You're going to do it in such a way that you kind of work with the primal and the due at the same time and you compare your primal solution with the dual。

Okay， so if that sounds vague， it will be less vague very soon。

There's also something called strong duality。Which says that in fact。

 as long as these things are finite， they're bounded， then the prime will opt P actually equals optD。

 we're not going to need that today。Okay， but we might see it again later。嗯。So ski rental。

And let's say that it lasts for K days。Yeah。And let's say。Renting。Costs $1。Buying。Costs。B dollars。

So what do we want to do？So。X。Is it going to be in01？Did we and it's going to tell us， did we buy？

The skis。And ZI。Is going to be in01。And did we rent？On day eye。So what we want to do is we want it。

 so the LP looks like this， we want to minimize。Well。Bx plus the sum i from1 to k of Z。Subject to。

For all I from 1 to K。We either had to have bought or had rented that day。

X plus Z had better be at least one。And。You knowTo fully capture the problem。

 we need these integrality constraints， ZI is either zero or 1， x is either  zero or1。

 those kinds of constraints are not allowed in an LP。So we're going to relax the problem。

 so it won't exactly capture the problem。 And we're just going to say， look， X is going to be。

At least zero， and for all I， Z I is at least zero。Right。What do you know it's covering LP？Okay。

And the duel。So as we saw， there's a mechanical way of converting the primal to the duall。

The right hand side becomes the cost and the A gets transpose， et cetera。 I'll just do it for you。

 So you want to maximize。The sum I from 1 to k of Yi。Subject two。

The sum from I from1 to K of Yi should be at most B。And y is bigger than equal to0。

 I believe that's it。Also y is at most1， so for all I， y I is at most1 and y is at least0。

So this is our packing LP。Okay。🤧。And before I give you a primal dual approach。

To the ski rental problem。Which it's gonna to be overkill just to get a too competitive ratio because we saw that was pretty simple。

 But you know， if you wan to get E -1， yeah。Yeah， yeah。 That's correct。 So， I mean， the LP。

The LP doesn't capture。Time。Right， you don't know like。Yeah， I mean。

 it doesn't capture when did you actually buy it。Okay。

 but the way that you should think about this is we， the algorithm， see constraints。

 we see rows of A online。😡，And whenever a row of A comes。

 we have to make sure it's satisfied immediately。😡， and then after we do that。

 the next row of a will come。Not a new LP， but just new rows of A。

 so that we keep seeing more and more rows of A。😡，And as a new row of a comes。

 we have to set some variables to。To make sure the constraintsstraints satisfied。

 so let me write that down。So。We see rows of A online。And。Have to satisfy。Constraints online。Now。

What does that mean if you're allowed to change things arbitrarily because I could just resolve the LP at every step。

There's a constraint， though， which is。Our variable。Through。The request sequence。Start at zero。And。

Are monotonically non decreasing。Okay。Because I don't want to say that you can choose to rent。

You set Z to1 on the IF day。😡，And then， you know， way in the future， you're like， oh。

 I really should have bought， and then I'll just change the I back to zero and actually set x to1。

Okay so the variables are monotonically non decreasing， so meaning that once you choose to buy。

Once you choose to buy， once you set X to Y， you've bought it。Okay， once you choose Z I to be one。

 you've rented， you cannot undo what you did in the past。 As we're going to see， though。 So here。

 these don't need to be integers， right， These can be fractions。

 as we're going to see to get this E over E minus-1 competitive algorithm。It's going to， you know。

 we're going to have to abuse the fact that。嗯。We're going to set these things to fractions。Okay， but。

Going back to the original ski rental problem。What does it mean to rent a half of a ski or a third of a ski for a day？

We'll show that online， you can also convert your fractional solution to an integral one so that it actually makes sense for the problem。

But you're going to online also maintain a fractional solution。Okay。So。If that't if that's not。

 is that， so is that clear， I guess？So you have to maintain。

You have to maintain a solution to the LP， meaning satisfy all the constraints online as you see constraints one by one。

And on the side， you also have to maintain an integral solution。

 which makes sense for the problem at hand。Okay， so you also have to have something that says， look。

 I'm not renting a tent of a ski。But were usually the way you do that is you figure out a way to solve the fractional problem online。

And then once you do that。You show that actually， if I have this fractional solution on maintaining online。

 then it's possible to also maintain。An integral solution online that doesn't do that much worse。

This is non decreasing。So I need a lemma。Which is called approximate complementaryary slackness。

Which says， so remember what primals and dues look like， I guess I erased the primal。

 So let me write the primal here， the primal。Says。Minimize。C transpose X subject to。

AX is at least B and x is at least zero。So approximate complementaryary slackness says the following。

Let X， Y。The solutions。To the primal。And the duel。A primal and the duel respectively。Okay。Suppose。

There exists alpha and beta。Such that。For all I。If Xi is greater than zero。Then。What do we know。

 We know that。We know that a transpose。We know that a transpose。

The I throw dot Y is certainly at most C。Okay。But suppose it's also at least C over alpha。

So be feasible。So just to be clear。X is a feasible solution to the primal。

 which means it doesn't necessarily achieve the minimum， but it satisfies all the constraints。

Y is also feasible for the due， so it's not necessarily optimal。

 but it satisfies all the constraints。 So suppose that X and y are feasible solutions to the primal and dual。

 such that we can say the following， if X is bigger than0。

 then not only is the if constraint satisfied in the dual， but it's pretty well satisfied。

So alpha and beta are bigger than zero。And also for all I。If Yi is bigger than zero。Then。Not only is。

AI。Ai。 x bigger than equals to B， but it's also at most beta times。BI。Then。C transpose X is at most。

Alpha times beta times b transpose y。Okay。So provingroving this will probably be in the homework。

 it's just manipulation of。Definitions， its not really there's not really much。

There's not really much。Craaziness going on in there。你仔。

But what it tells you is that if you're able to construct。😡。

Feaible solutions to both the primer and the duall that satisfies some properties。

Then you're able to say something about how good of a solution X is。

 remember you want to minimize C transpose X。😡，Right。

So if you're able to compute X and Y satisfying this。

 then you know that the C transpose X you've got is that most alpha beta at times B transpose y。

 And Y is that nice。 That's nice because we know that opt of the dual。Is that most opt of the primal？

Which is at most C transpose X。X is a feasible solution。

So off of the prime is that mostly transpose x。 and I'm telling you that that's。At most。嗯。Alpha beta。

Alpha beta times B transpose y。Right， so remember。哎呀。OThe dual is a maximization problem。

 so certainly Op of the due is at least be transpose y。Right。So what do you know？

Opt of the duall is bigger than equal to。Up of the primal is bigger than equal to be transpose y。

 which means this is at most。😡，Alpha beta。Of opt of the primal。Right。

I just basically I just multiplied alpha beta by both these sides of the inequality。

And lo and behold， C transpose x is that most alpha beta times opt。Right so if you can construct。

What this is telling you is that if you can construct feasible solutions to the primal in the duall that satisfy these complementary slackness conditions。

Then you know that the X that you found is close to opt。😡。

It does almost as well as opt up to this alpha beta。So it looks a little technical。

 but the point of this is to get some control on how well you're doing when compared to opt。Okay。

So now what's going to be our primal dual algorithm？

For to get a too competitive ratio for ski rental， look this sounds like a real overkill。

 But I promise you we'll reap some benefits for harder problems。🤧Okay， so。So。Primal dual。

Too competitive。Algorithm。For ski rental。嗯。So。Remember。

 we see the constraints come at us one at a time。😡，So we see a new constraint that looks like this。

When constrained。X plus ZI is at least one arrives。Do nothing。If already satisfied。Otherwise。

 if it's not already satisfied。Otherwise。Notice that when you go from the primal to the duall。😡。

Every constraint in the primole becomes a variable in the duall。😡，Okay。

So there are key constraints here。Right for I equals 1 to K。

 and each one of these constraints corresponds to a Yi。So what we're going to do is otherwise。

Increase Yi。Until。Some dual constraint。Becomes tight。What dual constraint can become tight。

 either Y I can become one？😡，Or this sum can equal B。😡，Okay。And then what do we do？Then。Set。

And now again。Constraints here correspond to variables there。😡，So some constraint became tight。

 which corresponds to some variable in the primal， we're going to set that variable to one。

What does that actually mean here？😡，These constraints， Y I's at most one， correspond to the ZI's。😡。

In the primal， so if this constraint became type， if Y I actually became one。We'll set Z to one。

If this constraint became tight， we'll set X to1。Its then set。Corresponding。Variable in the primal。

To one。Okay。And then。Definitely at the end of the day。We have integral solutions。Okay。For the primal。

 which are feasible。 And we have the solution to the dual， which is feasible。

Because we don't go beyond the constraint being tight。

 so we definitely were set we're not violating any constraints。So at the end。We have。Pair。

Of feasible solutions。For the primal in the duel。So now I want to say we satisfy certain approximate complementary slackness conditions。

So。We have to look at what happens if we have a positive primal variable， how much are we off by。

 what happens if we have a positive dual variable strictly positive？😡，How much are we off by here？

Well， let's look at the variables in the primal， what if x is bigger than0？😡，If x is bigger than 0。

That means that at some point， this constraint became tight。So if x is bigger than 0。

This constraint is exactly tight， there's no slack。😡，Which corresponds to alpha being 1。

If ZI is bigger than zero。That means also this constraint is exactly tight， Y I equals 1。Which。

 again， corresponds to alpha being one。How about in the duel， what if YI？😡，Is bigger than 0。

 strictly bigger than0。If Yi is strictly bigger than 0。

 all I know is that while x plus Z is certainly at least one。

 we're going to set one of them to one but we might end up sending both of them to one。

 so it's certainly at most two。😡，So alpha is 1 and beta is2。Okay。So we're out of time。

 next time we'll get a little bit fancier and show how to get this E over e minus1 with a randomized algorithm。

 and we'll do online Se cover。