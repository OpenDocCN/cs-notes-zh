# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p09 P9 -BV1zNSCBkEgW_p9-

![](img/3138a5e39629b548becb6e8bdeeef981_0.png)

Okay， let's get started。So today I want to actually show you the details of the analysis of the Mark algorithm。

啊，That's the randomized algorithm for paging， which gets log K competitive ratio where K is the size of the cache。

 can people hear me？Do I have a scribe for today？看谁呀。And then I want to show you。

Kind of a generic framework。For analyzing。Aly and coming up with online algorithms。嗯。

Based on this's a primal dual framework as it's called。

 this is something that was developed by Bo Binder and Naor， I guess in 2005。Okay， so。Today。

We're going to see。2 HK。Competitiveness。For randomized。Paging。This is。The mark algorithm。

We'll also see。Online primal duall。And as an example of how you use this to develop good on algorithms。

I will show you again， the ski rental problem。So remember。Last time we saw for the S rental problem。

 you can get a too competitive algorithm。Okay。I'll reshow you that same algorithm。

 but in this primal dual language， which I haven't defined yet。

 okay that's just an exercise to get you comfortable with the language。

And then I'll show you that you can actually beat the ratio2。Okay。

 if you allow yourself to be randomized， so you can actually get a competitive ratio of e over e minus-1。

If you use a randomized algorithm。Okay， and that's。That。

That result is not due to Big Binder and Noor。 it was already known before by Carlin and others。

 but it falls out more naturally from the primal dual framework。

And then we'll also see- so we'll see here over e minus1 competitive ratio。And we'll also see。

Online set cover。So there are。There are these M sets。But in the beginning。

 you don't know what items are in the set， you just know their names， they're set one。

 set two up to set M。And online， you see an item。 You see the items one by one。

And when you see an item。An。You have to make sure it's covered。Okay。

 so if it's not already covered by one of the sets that you chose， then you need to pick a set。

And cover it okay， and at the end of the day， you want to compare yourself to opt。So。

I'll maybe say a few words about Se cover before I give that。Analysis。

 but I hope who here has scene set cover。 I covered it in CS124， who has not seen set cover。Okay。

 so I will define。I will define the problem。 who here has another thing。

 so this is also something in 124。Ihi I'll do a very brief recap。

 but who is seen when you're programming？Okay。Who has has not seen linear programming。

 Who doesn't know what a linear program is。Okay，I'll give a very brief introduction。

So this whole online primal dual thing。呃。Is built around linear programming so linear programming formulations a problems。

 So I will say a few words about LPs before I get into that， but。So it's all about LPs。Okay， so。

The mark algorithm。This algorithm is due to Fiat and others。Journal of Algorithms， I think 91。Okay。

 so remember how this works， this is a particular implementation of the one bit LRU from last time。

 but when we evict an unmarked page，We choose an unmarked page uniformly at random from the set of all unmarked pages。

Initially。All pages are marked。ok。When。When we bring page P。Into cash。We're going to evict。

A uniformly。Random。Unmarked page。Then。Mark P。Now it may happen that eventually all the pages are marked。

If all of the pages are marked， so there is no unmarked page to evict。Unmark。All of them。

And we'd like to say that the competitive ratio of this randomized algorithm is two times the K harmonic number。

 remember this number here is1 plus12 plus 13 plus dot dot plus1 over k。

 which is natural log of K up to a constant。You can see this by comparing the sum to integrals in both directions。

Yeah。Say that again。Yeah， unmarked， thank you。Although to be honest。

 it doesn't really matter in the beginning here because you just unmarked them all。嗯。Okay。No。

And how these are marked during a request。Then outside of cash。Okay。

 so the way that we are going to analyze this algorithm and I think。

I started saying this at the end of last lecture， but I didn't get to actually prove anything。

Is it going to divide time into phases？😡，Okay。A phase starts。When don't we unmark all pages？

And a phase ends when all the pages are marked and someone is just about to make a request to a page outside the cache。

 so we're about to unmark all the pages and start a new phase again。Okay， so。Analysis。

We'll divide time。Into phases。A phase starts。When we unmark。Our new phase starts。

When we unmark all pages。Okay， and I think I defined two terms that are going to be used in the proof at the end of last lecture。

 but I'll remind you， so definitions。Okay， so。A page。Is。Clean。And let me call。

 you know I don't want to write Mark all the time， so for me， M is the Mark algorithm。

Algorithm M is Mark。So， a page。Let's say page P is clean。🤧。If。P wasn't。Requested。

So being clean is also time sensitive。 You're clean at a particular time。

So a page P is clean at a particular time if P wasn't requested in the previous phase。And。Not。

Yet requested。This phase。Okay。And another kind of page that we're going to look at is a stale page。

 a page is stale。If it was requested。Last phase。But not yet this phase。Okay。So you。

 except for maybe the last phase， how many distinct pages are requested in a phase？Okay， okay。

 so let' let's give us let's。Let's introduce some variables。L。B number。Of， I let's say。

 LI the number of clean pages。Requested in phase I。And let。

