# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P24：-24-Advanced Algorithms (COMPSCI 224), Lecture 25.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/5a7a7830d2226b280b0a7714c97f5b15_0.png)

So today。We're going to finish。Faster exponential timing algorithms。Or small space。Specifically。

 we're going to do inclusion exclusion。I always want to say a few more words about that。

Slashzeta transform。And Mobius inversion。And then。呃。

Well the remainder of the class as well as next lecture。

 I'll tell you some things about well an area I work in， which is streaming and sketching。嗯。Okay。嗯。

Let's get started， so I just want to write something I wrote on the board last time。

 which is this is a fact， we proved it last time this was inclusion exclusion。

Which said that for all。Seets。R subset T。We have that。

The sum over all s's that are sandwiched in between。Of negative one。To the t minus S。Is equal to。

R equals T。Okay。Remember this is just one， whenever I put a Boolean expression in brackets。

 it means one if it's true and zero otherwise。And。We defined thezeta transform。

 so if we have a function F。Mapping sets。Into。Some ring。We defined F hat。

 this is thezeta transform of S was the sum over r subs equal to S of F of R。是。And last time。

 what did we say？We said。Last time we ended with K coloring。Oh we have a scribe today， I think， yeah。

 okay great。We said let f of x， let F of let's say， S。B。嗯。An indicator for S。Is a non empty。

Independent set。A our graph。And then we had this claim。Which stated that the graph G is k colorable。

If and only if。Let's say the sum over s subset equal to v， negative 1 to the n minus S。This is just。

If you want to say this differently， this is just the size of V minus S。Of。Let's say。F hat to the K。

Hiss。So I mentioned at the end of last lecture that this will let us do things more efficiently。

 And I also mentioned that。You can prove this claim using inclusion exclusion。

So the scribe actually put those， wellll put the details of why this claim is true in the notes。嗯。

I am going to show you a proof of this claim， but I'm actually going to show it to you as basically just one example of something more general。

O。So you know， first of all， how would someone come up with this formula， right。

 it's one thing to just show you something and then have you prove it。

 but it's harder to come up with such things， right？

And I'm going to show you that the way that you would come up with this is basically via this Zeta transform Mobius inversion。

 which I'm， well， I guess I define the zeta transform， but I will define。This thing here。

It's called So thezeta transform F。And let me just include some references。嗯。So first of all。

 this thing here， we're going to see soon。You can compute it in either o star of 3 to the end time。

And poly in space。Or you can do it in。O star2 to the N， time and space。And these。

 these are due to independent works。 One is。Newland。And Husfelt。This is Fox of6。

And the other one is Covissto， I'm probably saying the name wrongg。Fox 06。And actually， the former。

The paper the first of the two papers。I mean， these are two independent papers that were published at the same time。

 but the first paper。This one。Can also get。Something like O star of。Two to the 2。461。

Two to the two point。2。2461 to the end time。And polyan space。And it's actually an open problem。

It's an open problem to get two to the end time or roughly two to the end time。With poly space。Okay。

So。Rather than prove that。Claim and talk about running time specifically for k colorability。

 I want to show you why this is。Just the kind of。Falls out of something more general。Okay， so。

So we have F as before， meaning， I said， F maps。Set to some ring。And I defined thezeta transform。

That was the F hat。And then I also define the Mobius inversion formula。And I'll call that。Ftilda。

Tell them S is the sub。R subset of s， negative 1 to the size of S minus R。Okay。And。

Kind of the real place where this formula comes from and why it works。Is the following claim？

F hat tilde equals F tilde hat equals F。对。Sos clear what I mean。 If you take thezeta transform。

 then Mobius invert it， you get F。 And if you do it the other way。

 if you first do the Mous inversion。And then do thiszeta transform you also getF。Okay。

 so let's prove this。And I want to show you just one of the directions。

 The other direction is very similar。 We'll show。That if you Zeta transform the Mobius inversion。

 you'll get F。Okay。In the other direction。Well， not the other direction， but。You know， showing。

That F tilde F hat tilde。Is that is similar？So let's evaluate this thing。On some set。So。We have。

 let's look at F。Tilda hat。Of tea。Okay。So。嗯。So what does it mean to take so we're taking the hat of the tilda。

嗯。Let's see so。Well， first， let's just look at what is F tilde of T。A tilde of T is equal to。嗯。

The sum of s sub equal to t negative 1 to the t minus S。Of F of S。C。Which implies that。F tilde hat。

Of Qi。Is。嗯。Let me see where is my definition。The sum over。That's the sum over。Let's call it。嗯。

S subset T。Of。Now I'm confusing myself with double indices，Of F tda。Of S。Right。Which is equal to。

 so let's actually call this Fil the S。So this is now R is a subset of S。诶。

And this thing is equal to。This。Of。R is a subset of S is a subset of T。Negative  one。

To the S minus R。呃。Of effort。I don't know how I。Okay。I feel like I'm off by a minus sign somewhere。

 but let me continue。Seems right。 Very good。And now I want to invoke inclusion exclusion at some point。

So。This is equal to。嗯。Some over。Our。Subet equals to T。And then， F of R。And then some over。S。

 and then。S R is a subset of S。Subet of T。Negative  one。To the。R。And。What I wanted to say is that。

The thing that's confusing me。 I wanted to say that this thing。I seem to have confused myself。

Hopefully it iss going to be r equals t in which case I would just be left with F of R。嗯。唔 sorry。

There for that to the。You you add two some， I think you change the order。In red。

The problem is I really I really wanted this to be t minus s， not S minus R。There。どうしてろ。

Thebo good does extend the sums。Everybody else。get something like。携たし？sum。あのちゃい。And。Wai so I think。

Ex as。Okay， so。I'm not sure I followed exactly that， but I think this thing。Is equal。

 I think this thing is going to be equal to negative one to the t minus S times some fixed sign。

Right。Which doesn't depend on。Anything else？In which case。

 this thing dies when R is not equal S anyway， so the sign doesn't matter。

 And otherwise you get otherwise you're only left with。One thing in the summation anyway。

So I think I confused myself by being off by the sign。嗯。Let me I'll fix this at some point。

And I'm pretty sure what I said is。So， okay， good。 So， so， so given， just given that this is true。

 where did this formula come from for K colorability。Okay。So。嗯。So let's define a function。Which is。

Number of ways。To write。S as the union。Of K。No empty。Independent sets。Okay。So if if G。

 so we really want to know。So GFT。Being bigger than zero is the same thing as saying K colorable。

T is really the set of all vertices。Right what does it mean to be K colorable。

 It means we can write our graph as a union of K independent sets。9 in the independent cents。

 of course。I didn't say anything about these being disjoint。Okay。

But that doesn't matter if you can write it as a union of K non empty independent sets。

 and they overlap。Okay， I mean， just greedily go through one by one and assign it the first color of the set it was in。

If it's in another set later， just ignore it the second time around。Okay。Basically。

 all I'm saying is if you can write it as a set of possibly overlapping independent sets。

 as a union of possibly overlapping independent sets。

 you can also write it as disjoint union of independent sets。Just drop， you know， if。

 if a vertex appears in multiple sets， drop it from all of them except one。Okay。

So we just need to be able to compute GV。Okay。But the claim。Is that。Well， not really's pretty。

 it's not really even at the level of a claim， just note that G hatt of S is the same thing as F of hat of S。

To the K。Okay。So。What is F remember？😡，F。Just as an indicator function for non empty independent sets。

Okay， so I claim that the way to see that these two things are equal is just to interpret what they both mean in words。

 So what is this。 So G of S is we want to write S as a union of K9 independent sets。

 So what does G hat of S mean under the definition of thezeta transform。 That means we want to count。

The number of ways of coming up with unions of independent sets such that the union lies in S。

 it's contained in S。So we want to choose k independent sets that are all K non empty independent sets that are all contained in S。

That's what this is counting。 How many ways are they of doing that。Well。

 how many ways of doing that are there？Just choose。

 just choose K non empty independent sets or just count how many non empty independent sets are contained in S and raise it to the K power。

Which is exactly the right hand side。Okay。Does that make sense。

Are people okay or are people confused？Okay， I'll interpret that as people understand what I'm saying。

So。Let's call this double star。Both。Left hand side and right hand side。I'm double star。Count。

The number of。Weiz。Of choosing。K9 empty independent sets。That all。L are contained an S。Okay。唔。Yeah。

 very。続け。Right， so they're ordered。 So if you take set one and then set two versus set two。

 then set one， count those count is two different。Thanks。For them to be equal。 That's right。So。

 that implies。That G of V， which is the thing we want to compute。GFV is equal to by Mobius inversion。

It's equal to。Gihat。Tilda。A V。 And we just said that Ghad is this thing。 So that's equal to。

F hat of S。To the K， tiled。Or， I guess。呃。I should write it as。F。Hat to the K。Tildad evaluated at V。

Okay。So that's where that formula I wrote before is coming from。

 It's just taking F hat and then taking the case power and then Mobius inverting it。So。Claim。

We can compute。嗯。You can compute， say all。F hat S。Or F tilde S。Values。Sequentialally。In space。

O star 3 to the N。In time O star 3 to the N。And polyan space。And when I count time， I'm assuming。

 let's say that evaluating F takes unit time in the case we care about evaluating F will take you poly time right because you have to check whether or not this set is an independent set。

嗯。Okay。So why is this true？When I say all， I mean for all S。So if you think about this formula。

 I guess I erased it， The formula here was sum over S subid V。

Negative 1 to the v minus minus S of F hat。Of S。奇。That was the value we had here。So， I claim that。

You could， for example， compute this thing in three to the end time and poly space。

So how would you do that？对。あじ。I mean， yeah， so not it。嗯。ぱくらちゃっました。Yeah， so not。Right。

Not even really recursion， but just， I mean， just kind of brute forcing it。Right。

 so let's say you wanted all the hat values。 right。

 The naive way to do it is you loop over all S and you compute， right so。Let's look at hat。

 for example， F hat of S。This is sum of all R subset or s of F of R。

So let's say that I wanted to compute。Let's say we want。You knowF hat of s for all S。

And after we compute F had of S for a particular S。

 we don't need to store it because we're going keep it into a running sum that we're using to compute something else。

 right。We just want to compute them， compute the answer， throw it away。

 compute the answer for the next test， throw it away， etc。How much time does it take Well。

 for each S， we take time proportional to the number of subsets of S。Which is2 to the size of S。

Right so the time。Up to the star notation is the sum overall ss， sum overall R sorry。

 subset of s2 to the size of R。And we already saw this before。Right， what is this， This is equal to。

嗯。Wellll actually want this for all Ss， so some of our all subset of V。To the S。

Two to the S time because we have to loop over all Rs， which are ins。And we said， look。

 we said this is equal to the sum overall I from1 to n of n choose I。

 That's the number of sets S there R of2 to the I。 and we already saw last time that this is at most three to the n。

We talked about this last time。So it's three to the end time and it's poly space just by brute force doing it。

So last time we mentioned that there's a dynamic programming algorithm for K colorability。

 which took roughly three to the end time and two to the end space。

 but it turns out using inclusion exclusion， you can do it in three to the end time in poly space。

Okay。So what about a faster algorithm？So there's something called Yt's algorithm。

And that gives you something like two to the end， time and space。Okay。

And I'll describe it for the Zeta transform。And I'll actually prove that it works。

 And then I'll just mention what you would do for the Mobius inversion。 It's very similar。

So it's a dynamic programming algorithm。Usually I like to describe dynamic programming algorithms by just giving you the recurrence。

 I describe it as a recursive algorithm， and then you can turn it into dynamic programming using memorization。

 right， you remember the answers to things you saw。

So let's come up with a nice recursive formulation that will get us all of the F hat of S values。

So remember we want。F hat of S for all S。Let's define a function。We I'll call G of I comma S。

As the sum over all R sub of s。And I'll say what this means very soon。 S equals R。Times F of R。

What's this S of I business， So S of I just means。S intersect I plus1 up to n。

Let's say that all of these are subsets of1 to n。Okay。So we want F hat of S。

 What's F hat of S in terms of G。Yeah， GN， right， so note。F hat a s。Is just G of n comma S。

Why is that Because when I is equal to n？The set from N plus1 up to n is the empty set。

So S of I is S intersect the empty set， which is the empty set。

And the empty set always equals the empty set。 So this is just always one。

So you have a sum overall R of F of R， which is exactly F hat of S。So we want G of NSS。

 and we're going to come up with a recurrence that lets us compute G ofNS。So first of all。

 the base case G of。So let me claim it and we'll prove it。I claim that G of I。Is equal to。

 First of all， the base case for me is I is 0。If I is zero。Then this is everything， so S of I just S。

So this is just testing whether r equals S。Which is only true when R equals S。 So you get F of S。

If I is equals to0。Otherwise， the recurrence that I'm。The current that I'm going to claim。

Is that this equals G of。I minus1 S。Plus。An indicator for I being an S times g of I minus1。

 S minus I。If I is bigger than zero。So just in terms of space and time。

 we're going to prove that this is actually correct， in terms of space and time， well。

 how many states are there in this memorized function？There are two to the n possibilities for S。

 there are n possibilities for I。So the space is like n times 2 to the n。

Times the amount of space it takes to hold these sums。But these sums are， you know。

 at most exponentially large， so you can write them down in at most end bits or of end bits。I mean。

 it depends on what F is。 And， F maps to some arbitrary ring。

 So the space is n times 2 to the n times the space to store a ring element。Okay。How about the time。

 Well， within each state。To compute the value for that state。

 you need to do at most a constant number of recursive calls。

And then a constant number of arithmetic operations。 right， So the time is proportional to the space。

So。You can compute all of this， and for all S， you can compute G of NS in O star 2 to the end in time and space。

So now let's prove that it's correct。Prove that it satisfies this rerence， I。

So let's write G of S in a different way。 Let's just break up this sum into two pieces。

So I can write that G I of S。Let me give myself some more space。So I can say， look， G of S。

Is equal to。The sum over R subset of S such that I is in R。Of。Si equals R。Times F of R。Plus。

The sum over R subset S says that I is not in R。SI equals R。Times F of R。

So now let me prove to you that this actually satisfies this recurrence case1。

Case1 is that I is not an S。😡，If I is not an S。And R is in S is contained in S。

 then certainly I is not an R。😡，In which case， the first sub completely disappears。

Because it's the empty sum。 There are no such Rs。Okay。But if I is not an S， well。

 S minus1 will be the same thing as Si。And I is not an R either， so R is also the same as R minus1。😡。

So this implies first sum。0， it vanishes， it's the empty sum。And the second sum。

Is a sum over R contained in s such that？Si minus1。Equals R minus1。F of R。Which is just。

G of i minus1 S。And this term didn't appear because I is not an S。So that's great。Case2。

Let me maybe give myself some space。Is that I is in S？Okay， so if I is in S。Then。If I is also in R。😡。

That means that S I -1 will equal R -1。Because both of them， both S and R contain I。So if I is in S。

Then。The first sum。Equals。The sum overall R subset S subset that S -1 equals R -1。Times F of R。可以。

Which again is going to give us。Whered it go？It's going to give us this term， the G -1 S。

And then let's look at the second sum。So in the second sum。

We want to sum over all R's that don't contain I such that it agrees with S from I plus1 onward。Okay。

So。That means that it agrees with S minus I from I onward。😡，In the second sum。We want。Or。

Which agrees？With S。From I onward。Which implies it agrees。With S minus I。From eye onward。

So what is that， that's the sum overall R subset S。Of S minus I。I equals r minus1 equals r I minus1。

Time is effort。And this remember we're in the second case where I is in S。

 so for this term to appear I has to be an S， and then we get exactly G of I minus1 S minus I。

So that's it。So。Summary， we can compute， we can figure out。

 we can decide K colorability in roughly two to the end time up to all the N factors。Questions。

And I should mention maybe some references if you want to see more on this。嗯。🤧。呃。

Can solve other problems。Using this technique。I only gave you one example。So for example。

 Min Steiner。Ti。You know， find。All K colorable。And do subgraphs。And there are a bunch。

 maybe I'll give you some references so you can look at， for example， hsal。As a survey article。

I think it's called， actually I have a copy with me。

An invitation to algorithmic uses of inclusion exclusion， Okay， so he's inviting you。

It's in ICP 2011， it's also on the archive。And there are several other。

You can find more references in that paper。Yeah。Yeah。Very。Yeah。Let me think for a second。Theょ。

All right， So you want。 So I said that this function G， I said that G of V is。What did I say。

 I said that G of V。Is bigger than zero if and only if it's k colorable。男性？Right， that was our final。

 I It's erased now。 But at some point， this is a different G。 I defined this function G。

 which said G of S is the number of， of choices of K independent， non empty K。K。

 non empty independent sets that are all contained in S。And then we just wanted to check that。

Or whose union is exactly S actually。 And we wanted to check that G of V is strictly bigger than zero。

嗯。Are you saying？Yeah， yeah， it's actually。That is actually true。That's actually true。 Yeah。

 so let me think about what's going on there。 Yeah， so what you said sounds make some sense。

 makes sense。 Yeah， So yeah， okay。But there are other problems that have nothing to do with coloring too。

 which you can solve。Okay。So okay， so before I switch to the next topic。

You know one thing I should point out is you the first question that might come to your mind when you see this algorithm is。

 well， maybe I don't actually want to just know if it's k colorable。

 I want to actually find a k coloring。Right， so at the end of the day， I evaluate this formula。

 I guess I'm being positive。 I know there's a K coloring。 How do I actually then find a k coloring。嗯。

It turns out that you can do it in roughly the same algorithm and roughly the same running time。

So for example， there's a reduction。A reduction in New Yorkland。Hoelt。Fox06。Shows。Can also。Find。

Kay coloring。And I'll start to the end。It's actually very short。 It's maybe a couple paragraphs。

 I'm not going to cover it in classes because I'm running low on time， but if you want。

 you can go the papers on archive， check it out。嗯。I mean， it it's it's a black box reduction。

 They're saying， like if you can compute。If you can compute the chromatic number of a graph into to the end time。

 then just black box that implies that that you can actually find a K coloring in roughly the same time。

It's not specific to their algorithm。So in the last， I guess， class and a half。

 I'm going to talk about something totally different。So before I do that。

 namely streaming and sketching。Are there any questions？Oh， right。 So， I mean， that formula I had。

 right， So the formula we remember we had。G is K colorable。If and only if。

And then I said this sum R subset of。What this thing。

So it's S subset of V negative 1 to the V minus S。F hat。Of S。To the K is bigger than zero。

RightSo remember we had this， this was our algorithm。

 our algorithm is just going to compute this thing。Okay。And check that it's positive。So， I mean。

 the reason I， so I said I was going to talk aboutzeta transforms and Mobius inversion。

 but this is exactly the Mobius inversion of the zeta transform。

So I told you about those two transforms to explain where this formula is coming from。

And then I get so this Ys algorithm。 Oh， and I I didn't mention。

How to actually compute Mos inversion。I just mentioned how to compute thezeta transform。

 but maybe I'll leave that as an exercise。There's almost an identical way to compute the Mo inversion using a similar kind of dynamic program。

Maybe I'll put that in the notes or until then you can try and。Think about it as an exercise。

Any other questions？Okay。So。Final topic。So there are many。advancedance algorithms classes。That。

 maybe spend。More than a lecture and a half on this topic。

We have a whole class on this topic at Harvard。 It will be offered next fall。

 namely algorithmms for Big data。 It's not just on this topic。

 but this is one of the topics that we spent a lot of time on。 So I didn't want to。

Kind of reduplicate things that are in another class by too much。

Just in case you have taken it or will take it in the future。嗯。That's sketching and streaming。

Andll also try to。Next lecture， I'll mention。An algorithm that's connected to something we've seen already。

That can be used to speed up something we've seen already， actually。So what's the idea？First。

We'll cover streaming。Okay， and what is streaming， streaming is just。

It's really just data structures， small space data structures。系。

So I'm going to look at a particular model。So we have some。High dimensional。Vectctor x。It's in RN。

Or maybe。High dimensional matrix。Capital X。Today， we're just going to look at a vector vector problem。

呃。And。We want。Just like data structures， we want to support。Updates to X。And also queries about x。

Okay。So。What kinds of updates and queries do you want to support？Well。

 I'm going to talk about one kind of update that we're going to look at。

 so there's something called the turnstyle model。This term was duty Muhu Krishnan。Maybe an '05。

 but I'll look that up。And the idea is。Each update。Is there pair， It's an index I。

 as well as an amount V。Causes the change。Xi gets incremented by V。对。

And also at the beginning of the stream， let's say x starts off。As the zero vector。哦。So， for example。

Maybe X is maybe n is the number of IP addresses that exist。 So 2 to the 32 or 2 to the 128 and IPV6。

And。Some algorithm is sitting in a router and it's maintaining X where Xi is the number of packets that were sent to IP address I。

So every time you see a packet。You can interpret that as an update。

 you look at where the packet is going to， it's going to some IP address I that can be seen as an update icona 1。

There's one more packet going to that I。And then at the end of the day， you want to compute。

Some query about x。So example queries， maybe you want to know。You know。What is X I for some I。

 or maybe you want to know what is。The support size of x。Right。

 how many IP P addresses receive traffic since the beginning of the stream。

Or how many packets did this IP address receive？And。Maybe I'll mention there's always。So。Always。

The solution。Of either。Remembering。Remember？Ining。Or the whole stream。So either， you know。

N or M space。Where this thing here is the streamlink。So the goal， usually in streaming algorithms。

 is to come up with an algorithm that uses。Much less space than the trivial solution。

You don't to remember the whole vector and you also don't want to remember the whole stream。

So one goal。Use very little space。So you imagine you're seeing all the traffic going through your router。

You're using IPV6， you don't want to use 2 to the 128 space， you don't have 2 to 128 space。

You also don't remember every packet that you've ever seen。So。Let's look at an example。

Let's say there's only one query that's allowed。Which is the support size。And for historical reasons。

 I'm going to denote this by F0。对。And also。All updates。IV。Have， let's say V being one。In general。

 you might allow negative updates as well。But for us。

 we're going to assume that this is the query and all updates gates have vehicless one。

So really it's how many distinct IP addresses。Did my router receive traffic today or something。

 that's， that's the thing we want to know。Questions about this example problem before I say some more things about it。

So to be more precise， you can use exactly n bits of space to solve this problem。

You just remember a bit string where the IF bit is one if you've ever seen IP address I。

Or you could use M times log n bits of space where the stream length is M。 remember。

 And what is a stream element， It's an index I， which takes log n bits。

 So to remember all of them takes M log n。So we want to do much better than that。Unfortunately。

 claim。Any deterministic？Algorithm。For F0。Requires。Let's say。Omega。I mean。And。Bits of space。

So unfortunately， we can't solve the problem much more efficiently， let's prove this。

And is this I think was first observed in。Paper of a loan。Matius Sensgeti。

I know the conference version was 96， but I believe the journal version was in 99。

So let's prove that。So it's going to be via an encoding argument。What do I mean by that？I mean。

 if we could actually solve this problem in less than linear space。We're gonna be able to encode。

 So suppose I， suppose I want to design a compression algorithm。Okay。

 what should this a compression algorithm do， It takes this input in end bit string。

And it outputs some compression of it。What's the compression of it。

 It's just some mapping that can be inverted。 Okay， it's some injection。So。

Our compressed version version， let's say we're compressing it into another string。Okay， so。

If I want a compression of all n bit strings into some other bit into say t bit strings。

 how big does T have to be to ensure that this is possible？

At least add right just by the pigeonhole principle， I mean or know。

 you can't have an injection into a smaller set， so that's what it。So。Suppose。

Let me write down what I mean， suppose we had。A space。S algorithm。Streaming algorithm。We will show。

How to then。Design。Design a compression。Algorithm。Mapping。Enbit。Strings。Two S bit strings。

Which implies， as you said， S to be N。A compression algorithm is an injection。

So you can't have such an injection unless this is at least done。And。

The streams that are going to arise in this proof。We'll have M being roughly and as well。So。

In this example， Eminade are roughly the same thing。So let's。

 let's design such a compression algorithm。So let's say Alice。Receives。Some x。

 which is in 01 to the n。And wants to compress it。Using。Our F0 algorithm。诶。So what does she do？Well。

 I mean， the A A takes input streams。 So she's going to create an artificial stream。Feed that to A。

And then she's going to compress her string X as being the memory contents of A。

And since a uses S bits of memory， that's going to be an S bit compression。

So what's the stream that she's going to create？And we also have to show that it's an injection。

 And to do that， we'll give a decompression algorithm。So how does she encoding of x。

 how does she encode X？She creates a stream。Containing。The set I such that X is 1。Runs A on it。

And then she outputs。The memory contents of A。So now we have to show that this compression allows for decoding。

So now Bob gets this compression and he wants to decode。So what do you do。

How do you decode and figure out what x was based on this compression？Yeah， exactly。

 try adding more bits and see if the support size changes。Right。So we're given。Mam contents。Of a。And。

We'll continue。Running a。Starting。With this state。So what do we do？Here's the algorithm。Let's let Z。

B。AQuery。Okay， a dot query。So that's the number of distinct elements in the stream。

Starting off from where Alice left off， basically the number of1 bits and X。And then。

For I being  one to n。We'll insert I in the stream。And then we'll check。If ADOT query now。

Has gone up。That means that。Sorry， no， if it hasn't gone up。If ADOc query hasn't gone up。😡。

It means that the I bit was already one。Right？Which means that Xi is 1。Otherwise， if it did increase。

 otherwise X is 0。And then now we we'll。Sent Z to be the new value。That's the decoding algorithm。

Questions。So。Great， so we can't do it with a deterministic exact algorithm。So。

Let's look at termmin exact F0。We just show that that's impossible。How about。

Deterministic approximate。How about。Randomized。Exact。And how about randomized？Approximate。

What do I mean by these？Here I mean it's a deteristic algorithm， it always is correct， okay。And。

It doesn't give us the support size， but it gives us a value which is going to be within 1% of the support size。

Like guaranteed。What I mean here， I mean we have a randomized algorithm。😡。

Which with 99% probability will give us the support size。With the other 1% probability。

 it might output some junk。so the question is， is that possible？

And then this is like the most relaxed version。It's a randomized algorithm with 99% probability。

 It'll give us an answer that's within 1% of the true answer。And then with 1% probability。

 it might give us a junk。So。嗯。It turns out that。I'm not going to prove it here。😡。

Both of these are also impossible。You can prove also via encoding arguments， actually。

ThatThese things are also impossible。All of these are due to the paper AMSS。And it turns out that。

 yes， this is possible。And when I say possible， I mean possible in sublinear space。

 it's always possible by remembering everything。And this is due to flage delay。And Martin。In JCSS。85。

Okay。Yeah。Yeah， let's say you want。Any constant， like to approximation。It's impossible， yeah。たに。

You mean in the randomized。嗯。No， it's just going to be。

 it's like this Monte Carlo kind of algorithm right。 So there's in general。

 when you talk about randomized algorithms， there's this Las Vegas Monte Carlo。

 Las Vegas means it's always right， but the running time or the space or something is expected。

And Monte Carlo means。The efficiency is always guaranteed， but the correctness is randomized。 So。

 yeah， so this is this Monte Carlo flavor。 And yeah， we don't have a guarantee when。

 when it's wrong that 1% of the time， it's just could do anything。嗯。

You can decrease that 1% to be as small as you'd like。

 You can make your failure probability be Delta。Let's say for this problem。

 but you would pay in your space by paying some log whenever Dlta factor。Okay， so。

Let me wrap up by showing you kind of why。This is even possible。

Why is it possible to beat or give you some intuition for why it's possible to beat linear space if you're allowed randomization and approximation？

So。Remember， what's our goal now？Is to develop。A randomized。Algorithm。A， such that for all。嗯。

For all streams。S。The probability。Over the randomness in the algorithm。That。

Let's say the output of A on stream S。Minus of zero。Is bigger than。Let's say epsilon。Times of0。

Should be at most， let's say， a third。You can make this third be as small as you'd like。

 make it be Delta， you'd pay something in your efficiency。So let's look at an idealized。

Randomized algorithm。Fdliene Martin。So。Why is it idealized。

 the next thing we're going to write is going to be idealized。 So let's say we have。

A totally random hash function。Which maps？from now on， I'm just going to call this thing bracket N。

It maps our universe， our coordinates of this vector X。Into the continuous interval from 0 to 1。

So each index of x gets assigned a totally random fraction between0 and1 by this hash function。

Uniform。Uniform value。 So ready， this is a little problematic。We can't actually store， I mean。

 the point is to use a linear space。And if I'm telling you。

 I'm using a totally random hash function that's that takes as that has n different possible inputs。

 We have to store these n random numbers。 That's already end space。Furthermore。

 these are real numbers and our computer can't store real numbers right it has finite precision。

That another catch。So it turns out that A， discretize you can make an algorithm like the one I'm going to tell you worked by discretizing this。

 so the precision you need is not that bad。You can discretize this into fractions whose denominator is。

 say Paul N。So you just need to work with numbers that are take long end bits of precision。

And another thing is， you know， the fact that you need n random numbers that would take you end space to store this hash function。

 But remember earlier in the course， we talked about， you know。

 pairwise independence and other kind of limited。Randomness hash functions。

 You can use those kinds of things to。In place of what I'm gonna tell you as well。 Okay。

 so I'm not gonna talk about that here， but you can get away with a reasonable hash function that doesn't take that much space to store。

Okay。So the idea that makes Flla Martin work。Is。Its the following， so here's the algorithm。

Let Z be the min。Overall， I in the stream。Of HRI。The number Z can be stored just using one number。

 I mean， Z is one number， right， So this is like one unit of memory。 if we can store real numbers。

Every time you see an eye， you hash it and then you set your current value to be the min of what it was before in the new hash。

And then when you ask for a query。To answer。A query for the number of distinct elements。

Or the number of the support size we output。1 over z minus1。If you want to。ううん。So。Here， if I put。

 I put this epsilon here。 So if you want， if you want an epsilon in your， in your guarantee。

 what you'd actually do is。You'd pick。H1 up to HR。Independently。

Where r is going to be something like1 of Rson squared。Okay。

So you pick our totally random hash functions。 one of represents on squared totally random hash functions。

And then。We're going to let。Zi。Let's say ZJ be the min。Over I in the stream。Of HJI。Basically。

 run this algorithm are times in parallel with different random hash functions in each iteration。

So now you're only remembering our units of memory as opposed to one number of memory。

And then what do you output you output。1 over， let's call it z bar minus1。

Whereas Z bar is just the average of all the Zs or Zjs1 over R。Sum J from1 to R。of Zj。

And the idea is this averaging will decrease the variance。So that。If you average enough of them。

 you'll be within a multiplic of one epsilon as opposed to。嗯。As opposed to constant error。



![](img/5a7a7830d2226b280b0a7714c97f5b15_2.png)

So I haven't proven anything。But。Are there any questions about？About the algorithm？

What the algorithm does。No。So the basic idea is， look。Let's look at this hash function H。

So we have this continuous interval from  zero to 1。And we're hashing these F 0 items。

 F 0 is the support size。 We're hashing these F 0 items。Into this interval。

So kind of what do we expect to happen？We roughly expect them to be roughly evenly spaced。

The gaps will be roughly1 over F0 plus1。And the smallest of the hash values。

we expect the smallest of the hash values in expectation， right that should be 1 over f0 plus 1。

If you want to formally prove that， you can say， look。The expectation。Of Z is。The integral。

From 0 to 1， the probability that z is bigger than xdx。

And then you can compute this and get what I said。Right。

 so maybe the easiest way to do this is to say。This is。1 minus the probability that z is at most x。

And then this thing here is the probability that for all I。In the for all I in the stream。H of I。

Is at most act。Right。And since the H values are independent， this is equal to the product。

Over I in the stream。The probability that。HI is that most。And this thing here is just x。嗯。Right。

Z is the min。Oh， right。G your point， you can't do math。So。Good， so for the min to be bigger than x。

 this means that this is the probability that for all I。H ofI is bigger than X。Okay。In the stream。

And this is just equal to 1 minus x。To the F0。Okay， good。

And then you can integrate that over X and you get what I and evaluate it。

 and you'll get what I said。You can also show。You can also show that the expectation of z squared again。

 by a similar kind of integral。Is equal to2 over。F0 plus1。F0 plus2， I'm not going to do it for you。

 but you can show it。And remember that we have chubby Che's inequality。The probability that。

Z minus the expectation of Z。Is bigger than， say， epsilon times the expectation of Z。

Is at most the variance？Over epsilon squared times the expectation of z squared。

And this is at most the expectation of z squared。Over epsilon squared times the expectation of z squared。

Okay。So you can do this kind of thing to analyze and say， look。

 there's a decent chance that Z is actually close to its expectation。

 meaning it's close to1 over f 0 plus 1。Meaning that。If you invert it。

If you invert it and subtract wine， you'll get something pretty close to zero。ラスベーシ idea。

And the second algorithm here， where we averaged a bunch of copies before inverting it。

What's the point of that， the point of that is。Look so。

Each one of those copies has the same expectation。So when we average it。

The expectation of the average is the same thing。But when you average it， the variance。

 the variance goes down by a factor of the number of things you averaged。So if you average r things。

 the variance goes down by a factor of R。😡，So if you set r to be1 e ripsson squared。

The variance goes down by a factor of one of uppsilson squared。

 which is just enough to kill this epsilon squared here。And making this thing still small。

so that's basically how this works。嗯。And yeah， I guess class is over， any questions about？

About this algorithm or I mean， it's idealized I already mentioned， but any other questions？Question。

This is。Yeah。Or you want to know Xi？So yeah， as he said。

 something more specific than the size and entire support。

So so so one I don't know if this is what you mean if what you mean。

 but so here it's funny in that there's only one kind of query。 Oftentimes when we。

 when we solve data structural problems， there are lots of different possible queries。

You could look at other problems too。A query also gives you an indexi， and you have to give XI。

So just like we had all these impossibility results for support size。

 you can prove such things for other things as well。 so for example， that problem， given I output Xi。

There's no deterministic exact algorithm。 Theres no randomized exact algorithm， but actually。

 there is a deterministic approximate one， and there is also a randomized approximate  one。

 which is a bit slightly more efficient。What does approximatex there mean。

 it means I'm not going to output XI。But I'm going to output， say。X I plus or minus some error term。

 and that error term is allowed to be， say epsilon times some norm of x。

 maybe the L1 norm or something。So for that kind of relaxation of the problem。

 you can also get small space algorithms。And there you have lots of different possible queries。

 you and possible queries。Well， so you get this for every single I， right， So in particular， if I is。

 if X I is 0。If Xi is 0， the query algorithm might tell you that Xi is epsilon times 01 norm。

Right so you don't know which ones are actually zero and which ones are maybe close to zero。

If what's discrete great？Oh， I mean， even if they're integers。Right， so。Let's say， I mean。

 Epsilon might be。A 10th or something。 And the L one norm might be divisible by 10。 So， I mean。

 this thing will still be。And this might still be an integer。😡。

And you wouldn't know whether or not it's。Whether or not it's zero or not zero。

Whether X is 0 and un0， I don't know。 Does that answer what your worry is or。Yeah。

 but then your space will increase as a function of epsilon。For example。

 in the deterministic algorithms， your space will be like one of uppson squared。

 in the randomized algorithms， you can get space1 of uppsilon。Up to some extra， maybe log some。

Log one Delta， et cetera。I think we're definitely out of time。I guess I will see you Tuesday。

 Happy Thanksgiving。