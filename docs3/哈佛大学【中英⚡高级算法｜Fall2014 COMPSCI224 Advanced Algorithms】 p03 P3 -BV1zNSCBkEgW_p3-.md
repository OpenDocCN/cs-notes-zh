# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p03 P3 -BV1zNSCBkEgW_p3-

![](img/d08e14f478bd723e80f5194f7c418640_0.png)

I guess I'll get started。So。The last thing I'll talk about is also in the word RA。It's hashing， okay。

So I wanted so I'm going to cover us today， hasshling。うう。And we' see it we'll see。Load balancing。

We'll see KY independence。' see the dictionary problem。🤧うう。嗯。And here we guess we'll see。

 I'll just review perfect caching。Very briefly。And then I'll cover linear probing。

So who took CS 224 last semester？Not a lot of people。So I covered this last semester。

 I guess I'll say some more about it this time， but who has seen perfect cashing？

W who has not seen perfect fashion？Okay， so yeah。嗯。Then I'll look at the retrieval problem。

 I'll define what these things mean。And here well look at cuckoo hashing。呃。And blue mirror filters。

Well， I guess somewhere in here I should have。Five actually comes before for， it's a membership。

 and that's boom filters。And then if we have time， I'll just say a little bit about。

Simple tabulation hashing。But not much because I don't think there'll be much time for it。

So who's seen bloom filters？Okay。Okay， good。Let's just before I talk about what。Problems。

 hashing solves， I'll just say a little bit about。What hashing is？So I imagine that。

We're going to have some family。H of functions。Remember're in road Ram， so we're mapping。Let's say。

By this， I mean， let's say0 up to u minus1。Mapping what0 to minus-1 into。啊。Zero up to m minus1。Okay。

And。嗯。There's some set。S， which is a subset of U。And the size of S is n。Okay。Such that。We want。嗯。

Some H in this family， we pick。To， you know， behave。Nicely。

 we'll see what that means in applications on S。For example， nothing in S should collide。

So the picture to have in mind is we have some n items。I1， I2。

 I'll just usually call these items one up to n。Even though they arbitrary they're arbitrary n items in the universe。

And we have some hash function H。Which sends them。And let's think of it as like， say， an array。

Of size M， this is cell 01 up to M minus1， and each item gets hashed somewhere。

And there could be collisions。Okay。Good。So now that I've said very vaguely what hashing is all about。

 let me say something about one of the problems that hashing solves， namely the dictionary problem。

Or before I even get to the dictionary problem。Let's just say， for example。

We have jobs and we have machines that handle jobs or servers Okay， so let's say it's example。

 it's not really a to example。 it's a real one。U。We have。You know， end jobs。That need。To be。Assigned。

To M machines， let's say。And each job。Or do I have a scribe for today？Okay， so each job。

Has some job ID， let's say。In this range in this universe。Okay。嗯。So if we know all the jobs up front。

 what's thing one reasonable thing that we might want to do。

 let's say that the M machines are all identical， none is faster or has better hardware than the other。

 We'd want to evenly spread the jobs across the machine so that each job each machine gets roughly n over M jobs。

Okay， if we know all the jobs ahead of time， we could just do that。

 we could just take the first N ofm， send them to one machine， the next N ofs。

 send them to another machine， etter。But if these jobs are coming， let's say， dynamically online。

 then we just need to send somewhere。 well， I guess even there we can。

We can just send it to the least load machine， but let's say that。We don't have。

 you know that requires some global picture of what's happening。Across all machines。

 And let's say that we want to do something just on。Without that global information， one。

 one thing you could do is just send it to a random machine。Okay， which is。

 let's say hashing it to some machine。Job has some job ID in you。 so when a new job comes。

Have it processed。Let's say in your job， J comes， J isn't one to U。Comes have it。嗯。Processed。

By a machine。H ofJ。we might want to understand。How well does this behave， meaningan does any。

Does any bin get overloaded， Does any machine get overloaded， Okay， we'd like。

 we'd like it to have N over M， but maybe it'll have much more。 So this is called。Usually called。

You know， the balls and bins。Random process。Where we have end balls and we're throwing them randomly into M bins。

 we want to understand how this behaves。Behaves。So。

So this is some form of load balancing across machines。And we'd like to say。You'd like to say。

The probability that。There exists a machine。Receiving。Bigger than K jobs。Is something small？

So the question is what goes here and what's K？So is the setup clear to people？

Let's say if H is a totally random hash function。

![](img/d08e14f478bd723e80f5194f7c418640_2.png)

So before I analyze that， I want to prove a certain tail bound， who here has seen the turn off bound？

Okay。So。Let me prove a theorem。Suppose。X1。X， N。Our independent。Where Xi is either0 or 1。

 these are independent random variables。And the expectation of X is P。

Meaning it's one with probably a P and Z otherwise。Then。

Where if we let x be the sum over all these eyes of Xi。The probability。

That x minus the expectation of x。It's bigger than or let me write it like this。

