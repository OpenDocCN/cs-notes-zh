# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p03 -03-(Lecture 3_ Online Paging and Resource Augmentation).zh_en -BV1yqVzzqEQ5_p3-

As far as what's the plan for today， I'm going to just open with a few comments。

 making sure we're all clear about the big picture。And then three。

 the next four lectures are about the online paging or caching problem which we talked about briefly in the very first lecture so the problem with traditional worst case analysis for online paging is twofold so first of all it doesn't give very accurate performance predictions second of all。

 it doesn't meaningfully differentiate between different solutions so today we're going to talk about two techniques resource augmentation and loose competitiveness that really focus on the former issue so these are really different ways of analyzing paging algorithms that give you more meaningful worst case guarantees and then the other two lectures about paging will be more trying to model data more carefully so that we get sharper distinctions between different algorithms like LRU and FIO。

Okay so starting with this lecture， you know in particular these two topics I'm going to start throwing different ways of analyzing algorithms at you at a pretty rapid clip and that's going to persist throughout the whole quarter。

 so periodically I just kind of want to stop and make sure we don't lose the forest for the trees and just help you think about how you might organize all of the different ideas you're going to be seeing in this class。

So first， let me just make kind of a comparison a sort of metaphor with how many people。

 including myself， teach undergraduate algorithms。 So undergraduate algorithms I think of as trying to equip you with a toolbox。

Primarily for algorithm design。Now， you know a class like CS161， it's not solely about design。

 you learn some things about analysis， like the language of asymptotic analysis。 but really。

 I think most people， when they think about that， you you think things like greedy algorithms divide and conquer dynamic programming that kind of stuff。

 so these sort of high levell paradigms for algorithm design and you learn several and you know what you learn is that there's no one silver bullet。

 Okay so no algorithmic technique is going to solve every computational problem that you come across。

 you really need a toolbox。 And frankly， it's a bit of an art to know exactly when which one you should apply。

 but you know we give you practice throughout the lectures and through the exercises and you come away with a class。

 hopefully with at least some initial expertise on that point。So that's the first thing。

 The second thing is the way that we teach these fundamental techniques in algorithm design。

 We try to kill two birds with one stone。 So on the one hand。

 we give you lots of examples of these techniques in action。

 But we also pick examples that are famous and fundamental and useful in their own right。

 so you both learn about sort of the general paradigm And you also learn about specific algorithms that fit in that paradigm。

 which any card carrying and computer scientist would want to know So we do divide and conquer。

 We talk about sorting， merge short quick sorting to instantiations， greedy algorithms。

 We talk about minimum spanning treaties， Pri and crustco and so on， dynamic programming。

 We talk about Belman Floyd， Floyd Warll and so on。

 And there's really a very strong analogy to this class C is 2，64。😊，But you know。

 rather than really focusing on how to design algorithms， we're really trying to understand。

 you know， how should you analyze algorithms so that you get meaningful information about them and meaningful comparisons between them。

So you might want to think about this class。As a toolbox。For algorithm analysis。Okay。

And in undergraduate algorithms， again， you don't see very many perspectives on analysis of algorithms。

 you almost only see worst case analysis。 maybe you see a little average case analysis， for example。

 when you study hashing， and this class you're gonna to see lots and again。

 it will not be the case that any one of these methods of analyzing algorithms is going to always be the right way for a problem that you encounter。

 but rather it's to equip you with many ways of making progress on understanding algorithms again I would say even among know kind of people who do this for a living。

 I don't think there's a very good understanding of when you should use which analysis framework we're kind of still figuring that out even in the research community。

 but at least it's a bit of an art to figure out which way to analyze which algorithm。

 but at least this way you'll understand that there are a lot of different ways of doing it and again。

 we'll study them through fundamental examples that are interesting in their own right。

 So things like the paging problem， linear programming and the clustering problem that we all talked briefly about on Monday。

So that's kind of， big picture of how you might want to sort of slot this class into your overall curriculum in computer science education。

All right， so。Any questions about the preamble， otherwise I want to start our。

Discussion about paging。 I think I was calling it caching on Monday。 I mean， exactly the same thing。

 Pa and caching， I'll use them synonymously for this class。Okay， good。So。So this is one of those。

 know， this is a real world problem。 Okay， so you it really would be nice to have accurate theory around this problem。

 but it's simple enough that allows us to showcase sort of many different attempts at how to meaningfully think about algorithms。

 That's why it' in addition to being real， it's a great one pedagogically。 Now， I should say。

 every time I teach this this word online is more and more of an anachronism。

 So theres this field called online algorithms， which some of you may have heard of。

 it was invented in the mid-80s。 So the Internet did exist in the mid 80s。

 but only in a very embryonic form。 So to the person on the street。

 the word online didn't really have much meaning。 So now this is a strange phrase。

 So online here means data arrives over time。 you have to make a choice when data comes in irrevocably without knowing the future。

 just like the paging problem we talked about on Monday。

 So probably the field should have a different name now。 But this is still what people call it。😊，嗯。

Yeah， and so I'm going to start where the field of online algorithm started， namely。

A paper is sleter and tar。Like I said from the mid 80s。

 and there's a lot of cool results in this paper。 I'm only going to cover the results which are kind of important for the narrative I want to tell here。

 And those aren't necessarily the strongest results in the paper。 So apologies to later and Tarjan。

 I'm sort of gonna focus on some of the least satisfying results in their paper。😊。

So let me just remind you quickly the paging or caching problem we talked about Monday so you have a cache so that's the small fast memory it can hold some number of pages we're going to call it K and there's something requesting pages over time。

 if something's already in the cache， no problem they can just access it directly whenever requested page is not in the cache you have to bring it into the cache and you have to evict something else and that's the algorithmic problem So that's the problem of designing the cash policy what to evict on a page fault or on a cash miss。

And so the performance measure that we're interested in for the paging problem is what you think it would be。

So here's Z is an input that is a sequence of page requests， A is some online algorithm。

 and we just count the number of page faults。Or cash misses。But the algorithm incurs on Z。Okay。

 so the formalism is identical to on Wednesday， but the semantics have changed， right， Wednesday。

 we were talking about the running time of algorithms。 That is not what we are talking about now。

 We're talking about totally the units are completely different。 Okay。

 we're not measuring running time we're just counting number of page faults。

That could be related to the running time of some application， but that we're not modeling that okay。

 just count page faults。Alright， so what I want to do is first introduce you to sort of the traditional。

 the dominant paradigm that you analyze online algorithms。 We're going to see what happens。

 We're going to look at some respects in which it leaves us wanting。

 And then that will motivate two sort of follow ons alternative ideas to the traditional approach。

 Okay， But first， I need to tell you kind of the traditional approach。So a key definition here。

 which if you've ever studied online algorithms you've seen before。

 is the notion of the competitive ratio of an online algorithm。Okay。

 so there's an important definition for this lecture。So we look at the cost。

 so if we're given online algorithm。For an input Z， look at， in this case。

 how many page falses this algorithm A incurs。So this is our protagonist。 Okay。

 if this is something like L R U， we're trying to prove this is small。 Okay， small relative to what。

 Well， small relative， the best you could have done in hindsight。Okay。So given that the input is Z。

 we look at the optimal algorithm for that input。 and we look at， So basically， we look at。

 what is the smallest possible cost that any algorithm could have achieved on Z。Now。

 this is the paging problem。 So as we discussed Monday。

 sometimes we're not even going to know what this is。 this is an unknowable object。

 But for the paging algorithm， we know what this is。 So let me emphasize。

 we're going to compare ourselves to a very tough competitor， namely the best offline algorithm。

 an algorithm which actually does know the entire future sequence of requests and can act accordingly。

 And the paging problem， we know exactly what that algorithm is， That's that greedy。

 furthest in the future algorithm。 Okay so that's the denominator。

 We look at how many page faults to say L you have。

 how many page faults could we have hypothetically obtained with clairvoyant knowledge of the future。

 We're in the furthest in the future algorithm。 and we look at the ratio。 The ratio， of course。

 is always at least one。 You can't do better than opt， you can only do worse。

 The closer this is to one， the better we're sort of simulating the optimal offline algorithm。Now。

 there's also the Z here， which is unspecified， and the traditional approach is worst case analysis。

 So you look at how big this ratio can ever get。Overall， inputs Z。And use a different color for this。

So that's the full definition。Of the competitive ratio。

So it summarizes the performance of an algorithm with a single number。This is the number。

 and the smaller the number， the better。Any questions about that？Yeah。that next no place phone。Yeah。

 so then the denominator is 0。 Well， so it wass defined as infinity then。

So in particular for this so what the question is pointing out is that you basically if you have a finite competitive ratio that implies in particular。

 then whenever there exists a way of having no page faults， your algorithm also has no page faults。

 Now， if you think about it in the paging problem， this isn't a big issue。

 if you think about it for 30 seconds， you realize that the only way you're never going have any page faults is at most K pages distinct pages are ever requested for a cache size K。

 And so that means you any paging algorithm which doesn't just know for no good reason of V stuff is going to also have no page faults。

 But you're right。 it's almost like a sanity check of does this definition even make sense for a given problem。

 can you at least get zero when it's possible to get zero， But in this problem， you can。

 That's a fair point。Okay。Good。Now， just to remind you， okay。

 so the pros and cons of sort of know so grossly compressing the entire performance profile of an algorithm down to one number。

 So the con obviously is that you just lose tremendous information about the performance of this algorithm across all the different inputs。

 Okay， you just summarize it with one number。The good news is now you have maybe not uncontroversial。

 but it's really an unequivocal ordinal ranking of algorithms。 and traditionally in this field。

 one declares an online algorithm to be better than another one。

 if and only if it has a smaller competitive ratio。

 There's an unequivocal notion of the optimal online algorithm。

 that's just an online algorithm with the smallest possible competitive ratio of any online algorithm。

 okay。😊，So that's traditionally how research is done in algorithm analysis so let's see what oh so one other point let me just try to you know throughout the course I'll try to make connections wherever they exist between all the different concepts that that I'm throwing you at so let me point out that actually this is really quite closely related to our instance optimality definition that we were talking about last week。

So remember， instance optimality said an algorithm better input by input be almost as good as every other algorithm on that input。

 Okay， And if you look at this， actually， this is more or less saying that。 Okay， so say I mean。

 think of this， suppose this ratio was small。 You know， at most a small constant or something。

 What would that mean， that would mean input by input。 We have a Mac Z here。

 So something would have to be true for every single input Z。 And here opt is anything。

 So in particular， opt can be know dependent on Z。 so this is sort of the best possible performance on a given input Z。

 This is our performance。 If this ratio is small for every single input Z。

 that's actually the definition of instance optimality we had last week。

 almost as good as every algorithm on every input。 In fact。

 what we're asking for it here is kind of even more insane。 than instance optimality。

 in the sense that the denominator， this algorithm。

 this is not one of our options as an algorithm designer。 something like furthest in the future。

 That's not on the table。 We're still using it as a yards stick。😊。

But we're restricting ourselves to the much smaller class of online algorithms。

 So it's actually insisting on instance optimality with the additional restriction that whatever algorithm we try to prove is approximately instance optimal has to be online。

 Okay， so it's very， very strong to try to prove this is， say， a small constant okay。So notes。

The competitive ratio is at most alpha。Let's say of A。Then a is instance optimal。

With the approximation ratio alpha。So remember， in instance optimality。

 the final definition we used had two relaxations。 One was we restricted the class to natural algorithms or we had that option。

 So we're not doing that here。 The other one was we allowed a constant on the right hand side。

 So that constant is just this alpha。 So again， small competitive ratio。

 even stronger than being instance optimal。 So you know， realistically。

 we shouldn't be expecting to see super small competitive ratios and problems that we care about。

 Okay， it's just very strong definition。All right， and that will in fact be the case。All right。So。

 I'm about to tell so what we're going to do next， we're going to apply competitive analysis。

 meaning we're going to analyze this ratio for the paging problem。

 and we're going to see what happens。 Okay now， as we do that， I want you to keep in mind， you know。

 the goals that we talked about of analyzing algorithms because we want to give competitive analysis a report card at the end of the exercise for how it does in the paging problem。

And so the goals。There's only three goals。One could suggest others。 So the first one we had was。

 that is sort of a natural scientist in a way。Where we have， for example。

 we have an algorithm and observed performance and we want a good mathematical model of observed performance。

 or you know maybe we actually don't know what the performance is going to be and we want a good prediction。

So this is sort of a very quantitative goal。A different goal is just to get good ordinal ranking。

Of algorithms。 So maybe you punt on very accurately predicting the absolute performance。

 but at least you get the relative performance of different algorithms correct。

 And then it still tells you what algorithm you should use， which is obviously useful information。

And then the third one， which really won't be a goal for us right now， but can be a very good goal。

 is you want sort of a benchmark。 you want a sort of brainstorm organizer。

 So a yardt that really focuses your attention on optimizing something to encourage you to come up with new algorithms。

 new ideas。All right， so。What happens when you apply competitive analysis， I。e。

 you try to minimize the competitive ratio for online paging problems？C。Where are we， Here we are。

Alright， so first of all， what can we hope to prove， Okay， so as we said， instance optimality。

 we emphasized last week was very strong。 This is even stronger。

 So that suggests that somehow lower bound should be easy to come by。 Okay。

 so let's just kind of see where the line in the sand is， Allright。So here's a theorem， easy theorem。

Which is。The following， every。Deterministic。Paging algorithm。And I mean here online algorithms。

 so ones that don't know the future。Has competitive ratio， at least K。Where K is the cash size。P。

Okay。So usually that's really big。O。So on this first goal， maybe unsurprisingly， you know。

 as far as performance and prediction， we're not going to be doing that。 well。

 I'll say more about that in a second。 Okay， but for now， it's just a theory。

 I'll show you the proof。 And then we'll talk about， you know。

 can we have matching upper bounds or not。All right， so the proof is simple。Here's how it works。

So suppose there's， so we have this cache。 It can get K pages at a time。

 Suppose there are only K plus one pages in the entire world。Okay， at any given time。

 the cache will be missing exactly one page。 So there's only one request at a given time that will cause you to have a page full。

 right。Fix your favorite algorithm A。Okay， deterministic。So suppose you're an adversary。

Choosing the input。What are you going to do， So if we're the adversary。

 you want to maximize the number of page faults that they encounters。Well。

 you know this K plus on pages in the world， this cache has case， it always one missing。

So we can just always request the one that's missing。So if you fix the algorithm first。

 I can certainly design a sequence of requests inductively that causes the algorithm to every single time step。

Okay，It's a very pathological input， you know， it's a true mathematical statement。

 Any determinants algorithm， there exists in input so that it faults at every time step。Now。

 I want to point out it's not clear that that's a deal breaker。

 It's not clear that that's a huge problem for us because we're interested in this ratio。 Okay。

 so maybe some input sequences just everything's terrible。 It's not our fault。

So that' we're not done with the proof yet。 but slowly there are sequences where a is terrible。

So can define Z。Define Z。Such that a faults。At each time step。

So that means the numerator on that Z is exactly the length of the input， okay。

 which can be as large as we want。But the claim is that actually opt can be a factor of K better。

So let's see why that's true。So the claim is butO， which remember is just furthest in the future。

 so that means whenever you need to evict something， look ahead， again。

 this is a clearairvoyant algorithm， look ahead， whichever one is going to be requested farthest in the future。

 that's the one you evict now。So farthest in the future。And here's the key point to realize。 Okay。

 so it's not that furthest in the future is' never going to have page faults on this sequence Z。

 it will， but fast forward to one of its page faults， okay。Remember。

 there's only K plus1 pages in the world， okay？So。There are these K options that it can evict at the moment。

 right， It just got a page fault。 It has to evict one of the current K。

So it just looks in the future and in the next K minus1 time steps。

 only one page is being evicted each time step。 So over the next K minus1 time steps。

There's going to be some page in the cache right now that's never requested。

K minus1 steps in the future， only K minus1 distinct requests that leaves one page that I've got right now that's not going to be requested again for K time steps。

So I'll evict that one or maybe something even further in the future if it exists。

 and I'm not going to have another page fault until that page is requested。Remember。

 there's only one missing page at any given time。 There's a unique page that could cause me a page fault。

 Okay so I just do the one which won't be requested for K steps。 I evict that。

 No page fault until it's requested again。Summarizing every time I have a cage fault， page fault。

 it's succeeded by k -1 hits。 Okay， Ca hits。 So I only have a fault every K time steps or even more infrequently than that。

Okay， so it has at least。K minus-1 cache hits。After each vote。

So that means if the sequence length is a billion。Then the numerator is a billion。

And the denominator is like a billion over k。So's like gives' a competitive ratio of K。

 at least it's a lower bound。So that's the proof of the lower bend。 So this is the line in the sand。

That says we can't do better than K， no matter how smart we are。

 It's just a inevitable consequence of comparing the performance of online and offline algorithms on a worst case input。

 Okay， this is just what happens。So any questions about that about the lower bound proof？Okay。

So what does this mean？哎。Well， what it means is we really shouldn't take you know the output of competitive analysis。

 We really shouldn't take these lower bounds you know， numerically， literally at face value。

 Okay so what is this predict。 I mean， this is predicting that you know， So in particular。

 this could be LRU right that's one deterministic paging algorithm know。

 LR in practice is pretty good。 it's not as good as if you had clairvoyance， but it's pretty good。

 It's certainly not， you know， arbitrarily you know larger than the optimal in hindsight on any request sequence that anyone cares about。

 Okay so that's the first thing is just it's sort of I mean， we really see the ridiculous pessimism。

 the worst case analysis causes for you with this K lower bound。

 The second thing is sort of qualitatively what it's telling you is very weird also in the sense that it says you know。

Imagine you increase the cache size in your system， right。

 You'd somehow expect your paging algorithms to improve。RightThe more resources you have。

 like the more stuff you have to store pages。 But if you really like take literally this Murphy's law data model。

 where the input just conforms to your design decisions， what this proof shows is， you know。

 take your cache size as long as you want as large as you want， I'll make you miss every time step。

 by choosing the input sequence appropriately。 So that， of course。

 doesn't correspond then he sort of coherent know model of data。 but again， it's sort of true。 Okay。

 so it kind of says throwing resources at the cache won't help you in system design， which is。

 clearly in accuratecurate advice about how to build systems。 So those are the negatives。 And again。

 you like I said， last lecture， worst case analysis you usually puns on these sort of know quantitative predictions。

 you know， also remember， there's still this hope of getting good information about which is the optimal algorithm。

Okay，So now the question is， you know， what has matching competitive ratio。

 what algorithms achieve a matching upward bound？So here we have some seemingly good news。

So this is kind of a very special case of what's laterlater and Ta proved， which is LRU。

 So remember this is least recently used。 this so there's an online algorithm and says to decide what to evict。

 look at the most recent request of everything in your cache right now。

 whichevers most recent requests is furthest in the past。

 that's what you evict this has excellent empirical performance， and it has competitive ratio okay。

你看。So LRU， in this competitive analysis sense， is an optimal online algorithm。

 There is no other deterministic algorithm， which has a strictly better competitive ratio。Okay。

 so that's good。All right， so let's look at the proof。The proof idea is quite simple。

 It's also very useful， though， Okay， so we'll use exactly。

 we'll see that this exact same argument gives us other， know nice consequences later in the lecture。

 It'll probably show up on your homework。 This is a good little good little proof way to analyze caching algorithms。

😊，So。Fix a request sequence。 Okay， so remember what we have to prove。 Remember the competitive ratio。

 we have to show that every single input。We in most K times as many page faults as any other algorithm in particular。

 furthest in the future。So fix an input。Call it Sigma。Now， for the analysis only。

 we can look at the entire sequence sigma。 of course， the LR U。

 when it was making decisions didn't know all the sigma。 But in the analysis， after the fact。

 let's look at the entire request sequence and break it into blocks。

So let me tell you how we break it into blocks， and this is important。So here's what we do。 Okay。

 so we started at the beginning of the page sequence and we start scanning forward， okay。

And we count the number of distinct page requests that we see。Okay。

 so maybe in the first 12 page requests， there're for four distinct pages。

 that's going to contribute4。Now， we stopped this block just before it's about to pick up the K plus1。

Distinct page request。 Okay So this block has only cage K distinct page requests subject to that。

 It is maximal。 That's the definition of the first block Sigma 1。So that's important。

 both of these properties are important K distinct page requests。And maximal。Subject to that。Okay。

And now having defined Sigma 1， we just define Sigma 2 in exactly the same way。

 We just start anew from this spot do exactly the same exercise，And so on。And at some point。

 we have our last block。Okay， call it Sigma B。 the p block， except for the last one。

 they're maximal subject to containing K distinct page requests。So again。

 those can be arbitrarily long。 They're going to have at least K page requests。

 but they may have way more。 It may have 100 times K page requests if the same pages get requested over and over and over again。

All right， so any questions about that， that's an important definition。Any questions about that。

 again， it' just it's for the analysis only。So for the analysis， what we have。

 So what's the motivation for this definition。 So we have to do two things。

 We have to get a handle on the upper bound side from the number of page faults that LR U incurs our protagonist。

 We also have to get a handle at the same time。 a lower bound on the number of page faults that any other algorithm like furthest in the future could obtain。

 Okay， so this way of structuring the input allows us to get both of those from the same structure。

 So that's what allows us to compare L R U and furthest in the future。 I this decomposition。Okay。So。

Here are the two key points I if we need an upper bound on LRU and a lower bound on anything else。

 so here they are one at a time。First， the upper bound。I claim that within a single block。Sigma I。

LRU faults。At most， how many times do you think？OkaySo we have this block could have like a ton of pages。

 could have like cube K cubed page requests， faults most K faults， that's right， most K faults。

So why can have it most K faults。 Well， the claim is that， you。

 consider some page that gets requested in Sigma 1， maybe many times。

 because there's any K different pages。The claim is that if a page is requested once in Sigma 1。

 then it's not going to be kicked out of the cache。 and therefore。

 there won't be a fault on it until the next block。 So in other words。

 you'll never fault twice on the same page in the same block。Why is that， well。

 suppose youve just faulted on page  107。Bomer， got to bring it into the cash， okay？

Now to fault again on page 107， it's got to be evicted from the cash。And for L R U to evict 10。

7 from the cache。 when it just brought it in， it has to be that K other pages have to subsequently get requested。

 Okay，1，0，7 will not be evicted by L R U until K， different pages are subsequently。Request。

 so that's K plus  one different page requests。 Okay， and within a block， you can only have K。

 So the second eviction on 10 7 has to be in a future block。All right。At most once。

 per distinct requested page。So that's ut most KB faultanol。Okay。

That's our upper bound on our protagonist， LRU， what about on our competitor？All right。

So here we're going to use a slight variation on the blocks。

But I'm gonna have a sort of set of shifted blocks。

 where I'm going argue that every single algorithm has to incur a page fault on each shifted block。

Okay。So the first shifted block is going to be all of Sigma 1。Plus， the very first request of Sig2。

Okay。Sigma 1 is maximal。 So that means the first request of Sigma 2 is going to be a K plus1 distinct page request relative to the beginning of the sequence。

If you see requests for K plus1 different pages and your cache size is K。

 you got to have a page full。 They can't all be in the cache at the same time。Allright。

So any algorithm， no matter how clever。Has to suffer。A page 12 here。

A variation of that argument says in general， for all the subsequent shifted blocks。

If you look at the second request of a block followed。

 but through the first request of the subsequent block inclusive， there's got to be a pageful。Okay。

 what's the variation on the argument well。Press pause right there， okay？Say this is page 107， okay？

So after this is processed， certainly the optimal cache has to have page 107 in it。

 it was just requested， and it has k minus 1 pages which are not page 107。Okay。

So that's what it's gotten its cache。 Whatever it's doing， it has 1，0，7 and K -1 other pages。Now。

If you look at the start of Sigma 2 through the first request of Sigma 3， Sigma 2 is maximal。

So there are K plus one distinct page requests between Sigma 2 and the first request of Sigma 3。

One of those is 107， but there's also K requests which are not 107。

And the cache has 107 plus K -1 things， which are not 107。 Again， one of those isn't in the cache。

 It's going to result in the page fault， no matter how smart it is。So similarly for all of these。

 so at least one page fault。So upshot。Number of faults and opt。Is at least b minus1。

 so who knows what's up with this last block， that's just kind of the dregs at the end。

So consider second request。Of sigma I。Through first request。Of sigma i plus1。Inclusive。O。

And that completete to the proof。 why。 Well， so the ratio then。

 remember that the input was totally arbitrary。 And we proved that no matter what the input was。

 LRU incurs at most K times B。And opt incurs at least B -1。 Okay let's call this B among friends。

So K B over B， that's a factor of K。Okay。In general。

 one comment I sort of forgot to say is in the competitive ratio， generally。

 you don't worry about just sort of additive terms。 Okay， so really what we have here is you know。

 a factor of K minus some error， which is a function of B only， okay， which we're not worrying about。

So that's the proof of this theorem。LRU has。Pitive ratio K。

 which we know is the minimum possible question。Seema 1 and Sma 2。The first to like the block there。

Completely different pages， not clear。Not clear。 Yeah， they could or they could not。 depends。 I mean。

 in particular， you might want to think about taking the bad example that gives us our lower bound where there's only K plus1 pages total。

And thinking about what this block decomposition looks like for this specific input。Okay。

 so there you're going to have right there's going to be huge overlap in these blocks。

 this is the only K plus1 pages in the world。So， but what we've done is we've。

Group to the input into these blocks， where there's just sort of so many distinct page requests that no matter how smart the algorithm is。

 the cache size just isn't big enough to fill it。I mean， so that's， that's。

 So there are these fundamental reasons why you have page faults。

 which is just that your cash is too small， right， And that can't be overcome。 So always in caching。

 there are inevitable page faults just because your cash is too small。

 And then there there are avoidable ones。 There are ones that are caused by deficiencies in your caching policy。

 And those are the ones that we're trying to minimize。

So we're trying to get a handle on how many unavoidable faults are there。

 That sort of always buzzs down to accounting argument。

 and we'll see more of these in future lectures where you just say， look。

 there's just too many things being requested， There's just no way we could have。

 know even with foresight， we couldn't have packed all these into our cash， sorry。That said， I mean。

 it's also possible that these are， I mean， a good， you know。

 one thing I'll say is I think that's a nice kind of simple special case to start developing your intuition for this proof。

 Like imagine it was， you know， suddenly a group of K different pages being requested all the time。

 Then it was a totally different group。 than it was a totally different group。

 that's a relatively easy instance。 But that's a fine initial kind of special case of these proofs to think about。

😊，So right， But if you think about it， our analysis is almost sort of talking about that case。

thest in the future。 that's right， agreed。Yeah， so sort of every， I mean， in some sense。

 every algorithm meet Yeah， I agree。 So in that sense of sort of uninteresting inputs。 But just。

 you know， as far as slowly developing， you know， always with proofs。

 if they seem too abstract at first， you know， I recommend thinking about these special cases。

 I think that's a fine， easy special case to start with。

For all possible input we are guaranteed that there will be at least one request in Sigma 2 that was not saying Sigma 1。

 right？There would be least one so if there wasn't， it would just be Sigma 1， exactly yeah。Yeah。

 so right。 So I guess if you like， I'm sort of。I'm focusing only on instances where B is bigger than one。

I guess would be a different way of saying it。 I'm really thinking of B as sort of going to infinity。

 frankly， as my canonical case。 But， but yeah。Yeah。Good， other questions？All right， so。

Let's talk about these results。 Good news， bad news。 Let's think about it。So at first。

 this seems actually pretty nice。 This seems actually like a quite satisfying achievement of what I've been calling the second goal。

 So the idea of you might want to have a performance summary。

 which gives you good advice about what algorithm is better than other ones。 What's optimal。

 And what do we see， LR you， the gold standard in practice， Indeed， Min possible competitive ratio。

 Okay， So that seems like that seems really good， okay。😊，On the other hand。The plot sort of thickens。

Let me show you another catchching algorithm。Called flushush when full。

Not something used in practice。 I don't know how you'd even dream of this unless you were like a worst case analyst looking for extreal examples。

So here's what you do。So whenever the cash is full。And there's a page fault。

You burn the thing in the ground， evict everybody。Okay， full evacuation。All right。So。

 you just I let to point out that it's actually very。

 there's a tight correspondence between when these mass evictions happen and flesh when full and our block decomposition of the input。

Okay。So， in fact， the points of time at which the flushing happens are exactly the delimiters between the blocks。

 right。So initially the cache is empty and so it stays full and happy with no cash misses until this is the maximal sequence。

 that's the K plus first sequence， that triggers a page fault with a full cache that triggers eviction。

 and then it's memoryless so it just starts all。So you have one flush per block endpoint， right。

And as a consequence of that， actually， if you think about a little bit。You look at this proof。

And you say to yourself， well， so what if it was actually flush went full and not L R U。

Where's the bug in the proof？And you start sort of going through the lines。

So this holds with the quality for flush windfall。Okay， but。Otherwise， nothing changes。

So the exact same proof remains valid， so it proves the exact same conclusion for this different algorithm。

Okay。So note。And you upper bound。Still holds。So while on the one hand， you know。

 we would have been really sad if， you know， something like last in first out had a better competitive ratio than L R U。

 that would have really been a disaster。 You know， In fact， last in first out。

 if you think about it as an infinite competitive ratio。 You know， So it's nice that LU is optimal。

 but it's not uniquely optimal。 And it doesn't even say it's strictly better than things。😔。

Where it is obviously strictly better then。 Okay， and not just for real real data sets。

 really kind of always。 LU is clearly kind of a better。 It's going to have fewer cash misses than。

Fluush went full。 So kind of very mixed results on the second goal。 Okay， question。

 Doesn't this sort of assume that bringing the new item into an empty cash is free of charge。Yes。

 it does， it's sort of a slide of hand， I mean， but maybe you'll get a factor of two。Yeah。

 so I mean here's the way you'd actually probably implement that。In a real caching system is。

 you know， you'd never bother to actually like kind of zero out all the bits。

 You just have like a 1 bit flag。 You know， you'd set it to0 saying， like this is stale。

 This is gone。 Don't take what's in this in this， know， right here seriously。 And so then really。

 it's more kind of like when something else gets brought in， it would evict some stale page。

 And so you know。So when I say flush， know， when I say burn the place down。

 what I really mean is set all those bits to zero。That's sort of a reset。um。But the point is， I mean。

 I mean， the real inefficiency here is， if it's not already clear， you know， is that you know。

Maybe almost all the K minus-1 pages you're leaving in your cache。

 which LR you would leave in the cache and Flush1 Fo is going get rid of。

 those might well be requested even very early on in Sigma 2 you might get all these cache hits on those pages so that that's sort of the concern。

O。So。Right， so mixed results on goal2， okay， not an unmitigated disaster。

 but it's safe to say we'd want finer granularity of the advice it's giving us about different paging algorithms。

So that concludes what I wanted to say about just the what the first attempt at using worst case analysis and this competitive analysis framework gives you for the paging problem。

 And I want to be clear， I mean， these kinds of unsatisfing interpretationsre immediately clear to to the researchers proving these results in the 80s。

 I mean， so a large community people have thought a lot about we're not very satisfied with this and look for lots of alternatives and I'll be cherry picking a couple of the highlights in the lectures I do so but this is one of the earliest examples。

 these paging problems I know of algorithms researchers really doing a lot of soul searching and thinking hard about know what are all the different things you could do alternative to worst case analysis so it's a really nice sort of showcase for that style of thinking so today we'll be talking about stuff mostly from the 90s tomorrow will be from maybe about 10 years ago and then the third lecture on the topic。

 which will actually be a week from Wednesday will be from just five years ago。

 so we're still seeing steady conceptual。Progress about how to think more accurately about these problems。

Okay。So， questions。Otherwise， I want to move on to。Resource augmentation。All right， so。

Just to remind you of the report card of competitive analysis for paging。

There's really two issues right so the first one I mentioned is that the performance predictions you get are not meaningful and sort of the implicit advice for how to build systems and pick cache sizes is also not meaningful So that's complaint number one and that's actually the complaint we're going to more drill down on in this lecture okay complaint number two is about you can't differentiate different algorithms。

 The other two lectures will drill down on that point。

 actually it's pretty hard to get all of the goals at once。

 so often you pick them off one at a time okay。The third goal of designing new algorithms for that。

 actually， traditional competitive analysis has been super successful。 Okay。

 there's a huge literature about all kinds of different interesting online algorithms。

 but that's not so much the focus of this course。 how can you use them。

 how can you use competitive analysis to guide new algorithms if you already have achieved the best value。

😊，So well you know， you can ask that about the say 2D maxima problems。 The question was。

 so what else could you do right So in the 2D maxima problem， we had Kipat Sael， we could have said。

 oh， it runs at analog end time and declared victory。

 but in fact there were older algorithms that were're also running an analog n time。

 So one way you can do it is you can parameterize at a finer granularity。

 What is the performance of this algorithm across different inputs。

 And then you could start imagining you might be able to say LRU is better than flush went full。

 right So maybe their worst case performance is identical。

 but in a sense that you've made rigorous there's lots of inputs or LRU is strictly better。

 So thatd be the initial thought of just how you apply last week's ideas to this problem。

 We'll see others as well。Okay。So resource augmentation。This is a nice idea。It's kind of you。

 it's hard to know how you'd think of this in the first place。

 But then once it's been pointed out to you， it's kind of pretty easy to use。

 So that's a nice combination。So what we're going to do here is。So again。

 what we're trying to do is get sort of more meaningful performance guarantees。And remember。

 one of the things that was so tough in the traditional approach was how powerful our competitor was。

 Okay， this all clairvoyant， optimal， offline algorithm。 So we're going to weaken our competitor。

 Okay， and therefore， of course， our competitive ratios will only get smaller if our opponent is less powerful now。

We're not going to actually weaken it in probably the first way you'd think of。

 And that's what's kind of neat， okay。So， the idea。Is we're going to compare our algorithm。

So say something like LRU。With extra resources。Where in the context of paging。

 the resource is the cache or the cache size。 So our algorithm with a relatively big cache versus。

Ops， this is still going to be furthest in the future， so it will still be clair voyant。

 all powerful in that sense， but itll be handicapped by having a smaller cash。

So this is what we're going to do。All right。Or equivalently， if you like。

 maybe we have the original cash size and opt as a smaller cash size。

 we're going to think about it both ways， whatever's convenient。

So this is the sense in which our competitor is weaker than it was before。 Incidentally， something。

 is probably intuitive。 I'll ask you to prove on the homework。

 if you fix an algorithm like LRU or opt say， and you make its cache bigger。

 the number of cash faults only goes down on every sequence as you'd expect。

 So just keep that in mind。 that should be true。 It is true。

 not hard to prove so you have monoity in the cache size。 everything gets better on a fixed sequence。

Okay。So that's our weaker notion of ops。Now， one question you might ask is。Why do this or like。

 suppose you prove bounds about it。 What does it mean， I'll get to that。

 But let me actually just point out that know the proof I just erased So that's hopefully least sort of still in your mind kind of immediately extends and starts giving us know pretty juicy guarantees with this kind of loside of guarantee。

 Okay， so we've actually already done the work to get guarantees of this form。

 Okay so let me explain that。So recall。So in the proof we just did。We had these blocks， Sigma 1。

 Sigma  two， et cetera。Okay， so maximal sub sequenceequence is subject to having K page distinct requests only。

And we argue that LRU。Has it most k faults。Her block。

Because it only faults at most once on each distinct requested page in a given block。

 that the argument。And then we also had the opt。Has at least one fault。Per shifted box。Okay。

So remember the argument there。Which was you focus on a given request say for page 107。

 theres k minus one other pages currently in the cache and the rest of the shifted block there's going to be requests for K distinct pages that are also distinct from 107。

 and so that results in a page fall。Okay， but now imagine that Op's cash size was smaller。

Had size only H instead of K。Let's run exactly the same argument。 Okay， page number 107 is requested。

 It's brought into the small cache of size H。At that point。

 there's a 107 and there's each minus1 pages other than 107。But in the meantime。

 in the shifted block， there's going to be requests for k distinct pages different from 10，7。

 At most H - one of those are currently in the cache。 So that's K minus quantity， H -1 falses。

 you've got H -1。 even if you knew exactly what these things are at best。

 you get an H -1 subset of them。 The rest are not in your cache。 you'll suffer page faults。

So in general。So， more generally。If Opt has cash size。Only H less than K。

Then it has at least K minus H -1。Falults per shifted block。So remember。

 this is the number of distinct page requests coming up different from 107。

 This is the number of pages that could currently that are allowed to be in the cache different than 107。

 So the difference is the number of page faults， at least that you'll have over this rest of the shifted block。

W are you calling a shifted block because it was the second request of Sigma I through the first request of Sigma I plus one inclusive。

 so we're using the original blocks to upper bound LRU and the slightly shifted blocks to lower bound odds。

Okay， so guys exactly the same proof。But actually， it gives us something really cool now with this lopsided comparison。

 with this resource augmentation comparison。So。How are you。Has competitive ratio。

 its sort of an abusive the term a little bit， but you know what I mean？Competitive ratio， K。

 instead of over one， it's now over K H -1。So me just， let me just distribute the minus。

K minus H plus one。Against opt。With catch size H。For example。

What if your algorithm has doubled the cache size of us？That is if is what if H is roughly k over 2？

What is this ratio， roughly？2。There used to be K， remember。Okay。

 so it used to depend on the cash size。 now it doesn't。and all like that。

 it's a very nice function that doesn't depend on the cache size too。

So that's a little bit eye opening。The sort of quantitative prediction we get。

And the theory changes quite a bit once we think about resource augmentation。But still， you know。

 let's go back and say， okay， but， you know， is this a cheat somehow， I mean， in some sense。

 it feels obviously like a cheat。 But is it a cheat that we could at all justify。

 Does it help us think about anything or understand some problem。

So I'm trying to convince you actually it does。So the obvious concern or the thing that say hard to interpret is it just feels totally apples versus oranges。

 okay。So we have two sides of this competition。 And， you know。

 our two contestants are both handicapped， but in seemingly totally incomparable ways。 right。

 We have the left hand side。 We have our algorithm with its， you know， complete big cache。

 but without knowledge of the future， without clairvoyance。Okay。

Then we have somebody who knows the whole request sequence， but just doesn't have as many resources。

 And we're saying， you know， one is not much worse than the other， right， it seems like。Okay， but。

 you know， were， we're not clair voyant， and we don't have a small cash， so。Well。

 what do I make of this？So let me suggest two interpretations that I think are very nice。

The first interpretation， we don't even have to do any more math。

 It's just kind of a story about what this suggests。

The second interpretation is a little bit of math， not not very hard math， a little bit of math。

 So it's not going to be， in some sense， corollary of this resource augmentation result。

So answer number one。So remember， we said our first genre of criticisms of what。

Competitive analysis gave us was not only to give us a big competitive ratio。

 but it's not like it was big in the sense of being 1000。 It was big in the sense of being K。

 And it sort of suggested that you know， having a bigger cash doesn't help。

 Okay So we've gotten rid of that problem。 So that's good news。 right。

 No longer is it sort of saying that know， somehow clearly a big cash helps because all of a sudden you blew up our cash by a factor too。

 we're getting almost as good as opt was previously， we were terrible。

 Okay so we're starting to see benefits of having a bigger cash。😊。

But mean actually more sort of maybe even more usefully， it suggests you know admittedly cartoonish。

 but still plausible approach to how you might design a system。

 right So suppose you're trying to figure out how big to sizeize your cache and maybe you're also jointly trying to decide what caching policy to use。

 or maybe you know you're going to use LRU。So then what it says is here's what you do。 Okay first。

 as a thought experiment， suppose you can run an optimal algorithm， Okay， furthest in the future。

 you can't just first think about if you could。Now。

 size the cache so that you're happy with its performance。 Okay。

 so that the page fault rate is smaller than whatever target you care about， you know，0。01%。

 whatever。 Okay， so that's the first part of the problem。 The second part of the problem is， okay。

 good。 and the thought experiment。 actually， when be using LRU。 just double the cash。

 you'll still meet your page fault rate target。 Okay， so it makes it a modular problem。 Okay。

 rather than jointly trying to size cash and figure out the caching heuristic factor it into two。

 assume you can actually see the future。😊，Apply this result。Get the size of the cash， double it。

 you're done。So that's nice。It suggests。Not unreasonable two step approach to system design。

Which at least satisfies the very weak litmus test of exposing why having a bigger cash is， in fact。

 a good idea or will help you。 Obviously， there's other trade offs for that。

 But just as far as the pay fall rate， you'll certainly be doing better。Okay， answer number 2。

So An number two is， I think， not especially well known。The very cool result by Neil Young。

So this is from the late 90s。Soda is the name of sort of the biggest algorithms conference that happens every year。

And so the way we can think about Young's result is it sort of says even though resource augmentation is an apple's oranges comparison。

 even though it seems like you're cheating by comparing your algorithm to a hobbled adversary with a smaller cache。

If you have a resource augmentation bound like this。

 it actually automatically has consequences for your performance， your competitiveness。

 with respect to algorithms with exactly the same cache size。

So it's basically going to be a coroll of the resource augmentation bound， which says lopatic。

Guants of this form translate to nontri guarantees， even when the cash sizes are the same。

So that's the high level takeaway of what I'm about to show you。All right， so informally。It says LRU。

Is provably very good。I'm leaving this in quotes for a reason。呃。For most。Cash sizes K。Okay。

And this is going to be an input sequence by input sequence guarantee。

So that's informally what it says。You should be wondering， you know。

 I said that there's going to be some consequences。

Even when you compare two algorithms that have exactly the same cache。

 but you should be kind of wondering， but we saw that lower bound at the beginning of class saying that there's no reasonable comparison。

 So how we going to get how are we going to sort of dodge this lower bound of K。

So we're gonna dodge it by having two relaxations。 So， first of all， by being provably very good。

 we'll see that this act will allow this to mean two different things。

 So one thing will be what it went before， having a small competitive ratio close to one。

 we will also accept as very good performance， if L R U does well in absolute terms。 Okay。

 So if it's page fault rate is， know， super small， only epsilon， okay。😊。

So that's the first trick is we'll have two notions of good performance。 The third sorry。

 the second relaxation is that we punt on a few cache sizes K。Okay， so you fix the input sequence。

 you imagine in your head that you ran LRU over and over again for different cache sizes。 Note LRU。

 of course， is well defined whatever the cache size is， Okay， so you can fix a page request sequence。

 you can fix LRU and then you can see what happens for lots of different cache sizes， K。

So we're going to punt on a few values of K。 There'll be some unlucky values of K where we do poorly。

 otherwise we'll do well。Okay。And so this is， you know， in my opinion， this is a quite， you know。

 reasonable relaxation unless you're a totally die hardd disciple of Murphy's law， right。

 because we really don't expect page request sequences to be adversarally tailored to the cache size K。

 In's fact， if anything， if it's a super optimized application。

 it's going to be optimized for the cache size K。 it actually be in your favor。

So I don't think it's a big deal， just saying you know， in some sense。

 the data set should be uncorrelated with the cache size。All right。So let's go the proof。

I guess any questions？This is gonna exclude。 It's gonna exclude things like our our lower bound earlier where we had K plus1 pages。

 Good， right， So good test case would be the sequence we used for the lower bound at the very beginning of lecture。

 there， the sequence really was adversarially tailored to the cache size K。

 We said fix the algorithm fixed K。 assume this K plus1 pages always request the thing which is missing。

 right， So in some sense， this is dodging that。 It says no， no， no， no， no。

 you tell me the page sequence first， okay。Then I'll tell you the cache size or nature will pick a cache size at random。

 Okay， so it's sort of reversing the order a little bit of the adversary and the algorithm designer in some sense。

 our input has to have an input number of pages any finite number of pages we can size take Yeah。

 so in the formal statement， the way we'll do it is we'll just sort of fix。

 know our favorite number N。 and then we'll just say some， you know。

 for a small fraction of the cache sizes between one and n。 this will be true。 And then implicitly。

 it'll only be interesting if input size exceeds that n。 Yeah， but I mean。

 the spirit of your comments correct。 Yeah， So we'll handle it in sort of a finite way。 But。Yeah。

Do other algorithms do worse on。诶嗯。Good question。 So there'll be a homework on this。

 So nothing I say in today's lecture succeeds in differentiating between， say， LR U and FiIO。

 or even， in fact， between LR U and Flush Winfall。Okay， so everything here is in some sense。

Just about getting reasonable guarantees， it is not about differentiating between algorithms。

 although we will have two lectures about that。The answer to。

 isn't it quite similar to the definition of。Natural algorithms that we use good Well。

 so isn't which。 I mean， so I like that you're making this connection， but what do you have in mind。

inputput。Is basically the， the input cannot have like a certain order or。Yeah， it's in the spirit。

 So the comment is， doesn't this sort of seem like similar to what we're doing with this optimality。

 where rather than competing with all algorithms， we were just competing with natural algorithms。

 So I think actually， resource augmentation is maybe even more strong in that spirit， where， you。

 we're sort it's not quite natural algorithms anymore。

 but we're restricting only to a subset of algorithms。

 namely those that are forced to use a cache of half the size。

 say So that's already in that spirit here it's， you know。

We actually are going to compare ourselves to。 So here it's a little different because it's more。

There's this extra parameter K being chosen here， right So there's both the algorithm。

 which in sort of in some sense， is independent of K， right。

 It's either furthest in the future or L R U。 Then there's the input， which is also independent of K。

 and then there's K。So what we're more trying to get at is that the input shouldn't be a function of k。

But in some sense， I completely agree with the spirit of this question。 And later in lecture。

 later in class， once we have more examples， I'll try to， you know。

 organize all of the different you know， order of quantifiers of all these different models。

 But that's exactly， that's a great way to be thinking and trying to connect this to last week。

 So that's a good comment。😊，Let me tell you sort of， you know。

 just in two sentences why morally this proof should be true。 Why something like this could hold。

 Okay， so here's why。 so we've got this resource augmentation guarantee。 And again。

 we'll use the general version。 But just think about the special case where H is K over two。

 Okay where it's half the cache size。 We're getting a factor2。So what do we know， So we know that。

If we're allowed to have twice as big a cash， so the optimal has a cache of 10， we have a cache 2000。

 we know we're doing almost as well。All right， so the really happy case is where you know。

If we decrease our cash from 2000 to 1000， maybe we actually don't suffer that many more page faults。

 Maybe we just have like twice as many page faults。

 if we back off and go back to the original cash size， then we're just done right。

 because with double the cash， we were almost as good and we're almost as good with half the cash size。

 and now it's a fair comparison。So the only bad case is when that doesn't work。By that not working。

 I mean， if we cut our cash size in half， LRU would get radically more page faults。

 which could happen。But it just can't happen that many times。 I mean， you know。

 as you vary the cache size from really small to really big， you know。

 there's only so much the number of cash the number of page faults could vary how many times in the number of page faults you suffer double can't happen over and over and over again。

 because that's an exponential growth in the number of page faults。

 whereas your sequence is only growing linearly。Okay。

 so this bad case can only happen in a small number of times。 that's， in some sense going to。

Corresd to the exceptional cash sizes。 So that's what's going to be happening in the math。

But let me give you a real proof。 And actually， what I'm going to do is I'm just going to show you the argument。

 I mean， because the argument is not that hard。 And then once we see the argument。

 we'll kind of see what the precise statement is that corresponds to this informal statement okay。

All right， so fix a parameter B。At the end of the day， B is going to be like a small。

 constant fraction times the cache size。 or whatever。 It's just some number。

 We'll figure out what it is when we need to。So now let's see again。

 so we're going to follow that intuition where let's just try to in a black box way。

Apply a resource augmentation guarantee and identify the cases where that gives us actually a small competitive ratio。

So for every sigma。And cash size k。The resource augmentation guarantee。Gives us all right。

 So we think of B Bs the number of extra pages we're going to give L R U。 Okay。

 so it starts initially with K。 And we're thinking about giving it an extra B。 Okay。

 So in other words， it's kind of it's a slightly confusing change of variables。 I apologize。

 But so for us， K is going to be K plus B and H is going to be K。 But you know。

 I'll write it all out in detail。 Okay， So K sort of the original size。 and we get B extra ones。

So LRU。With cash size， whoops sorry。So the number of page faults。Of LRU。With cache size K plus B。

this just means the cost with that cache size on this input sigma。So this is the most。So again。

 I'm just plugging in there。Where what used to be k is now K+ B and what used to be H is now K。

And so this is times cost of opts。He sigma。Okay。So all I'm doing is instantiateating this guarantee。

 I've done nothing so far。Just a change of variables。Now。

 let's formalize what I said before that like we have these two cases。

 the good case and the bad case。 The good cases where L RU's performance is not changing very rapidly with respect to its cash size。

 Then we can just piggyback on this guarantee。 And the bad case is where that can happen。

 So let's start with the bad case。So now think about a particular value of k，So either one。

Adding B extra pages to LRU's cache makes it radically better。 that's case one。So cost LRU。

But radicalically better， let's say a factor two。Not that important。Okay。

So we're going to call this a bad cap size K。Okay， everyone parse that？

You give it a lot of you more pages。 It only gets better， but it might get only a little bit better。

 It might get a lot better。 So case1 is it gets a lot better with these extra B pages。Now。

 if this doesn't happen。Then this number is within a factor two of this number。

And we already have an upper bound。Sorry， we already have't ever bound on this number。Over here。O。

So if this holds in the opposite direction， then what I can do is I can just hide that B。

so the only difference here is hiding the B。 so I can hide that B and just pick up an extra factor two。

Okay， if one fails。So or。Cost。LRU。All right， this way。Cost， LRU， K Sigma at most。So also。

 let's just go ahead and cancel the case。K plus B。B idea。K plus B over B plus 1。

And we pick up that too， that's the same as that too。Cost ox。Sigma。O。

Anyone need any handwriting clarifications。Or other clarifications。 I mean， what I've said is。

Content free。 Okay， so if something doesn't make sense。

 it's just because you sort of lost the trainer thought。 Okay。

 there's no actual ideas in what I just did。I'm basically just taking each cache size K and I'm classifying it as good or bad。

 bad means if I add B more pages， LOU gets radically better， good means it doesn't。

 and if it doesn't， then I can piggyback on the lo side of guarantee and actually get a slightly worse guarantee we're both opt and LOU have exactly the same cache size K。

 That's what we've done。All right， so now the question is。Okay， let me just point out。

If supposeupp this was a constant。 I at the end of the day。

 we'll choose parameters so that this is like constant。right。

 So the way you should think about this is in case 2， for a good cache size， we're golden。

 we're like constant competitive。 Forge about K competitive。 We're like， you know。

0 of one competitive。 Okay， so case 2 is going to be a happy case。 Those are good ks。

So then the question is， well， why are we ever in case 2， Maybe every single cast size is bad， okay。

That's。That's the issue。So what if there are a ton of bad cat sizes？

So let's say theres L bad cash sizes。So a bad cache size is a size where adding B more pages would make LU radically better。

So intuitively， what I want to do is I want to take all these different radical improvements of LR's performance。

 and I want to chain them together and say， well， man， if you had a ton of bad cache sizes。

 that would obliterate LRU's performance down to like  zero。

 It would just be having like no page faults， okay。😊。

So I want to chain these different bad cache sizes together。To do that。

 I need them to be at least spaced B apart。 Okay， that's just because there's a plus B here。

 This is not a very important step， but I do need it。So take your L bad cash sizes。 Okay。

 maybe maybe， you know， if you have a size of cash，7， it's bad，10， it's bad，15， it's bad，24。

 it's bad and so on。Maybe B is like， you know，10 or something。 Okay。

 then list out all the bad cache sizes and take the every 10th one。 Okay。

 and just focus on that subset of like L over B， bad cash sizes， each of which， of course。

 is going to be at least 10 apart。So take your Lba cash sizes and we're worried about this being super big。

So then there are at least L over B。Bad cash sizes。Each at least be apart。Okay。

I just mean like literally the difference between the two cache sizes is at least B。All right。So。

What we want to do now is apply。This inequality。We want to iterate this over and over again。 Okay。

 So look at the smallest bad cash size。 Maybe it's  three。 What it mean to be bad。

 It means if I gave you 10 more pages， your cash number of cash pulses would drop by a factor 2。

 So go to 13。 Look for the next bad cache size。 Maybe it's17。 If it's bad adding 10 pages。

 drops it by factor 2 again。 Add 10， move on for the next bad cash size and so on。 Okay。

 So you can do that。 L over B times。Okay。Which means that you for a really big cash up at the highest bad cache size。

 the performance， meaning the number of page faults at that really large cache size is bounded below by one half raised to the L over B times the number of page faults with the smallest cache size。

 which at worst is the length of the sequence。So。By iterating。

 condition one of bad cash sizes on these L B cash sizes， we get at the cost。OfLRU。

At some big cache size N。Is it most two？Raised to the minus L over B。Times the cost of LRU。

With a cache size of let's say one。On sigma。And in the worst case。

 you fault on every single time step。 So that's the length of the sequence sigma。Okay。

So what have we learned， We learned that if you have tons of bad cash sizes。

 then the number of page faults that you have for big enough caches is tiny。

 It's exponentially small fraction of the time steps that you're going be faulting okay。So。

Suppose L is so big that this is epsilon。Okay。So that L would be。B log base two， one of epsilon。Then。

 the cost。Of LRU with n in Sigma is the most epsilon time sigma。Okay。

So that was just plugging in parameters。Now， Young makes a very nice point。

 when he derives this into final inequality， he says， okay， so how do we interpret this。

 How do we interpret that， you know， for this big cache size， LRU has total number of page faults。

 epsilon times the sequence length。Well， think of it as not as a competitive analysis。

 not a competitive ratio。 But I think it was a page fault rate。

 So imagine epsilon was  point quadruple 01。that means over this whole sequence。

You're faulting at most， a。01% of the time。 Okay， Maybe there's some other algorithm。

 which is only faulting， you know， a point triple01% of the time。 But at that point， who cares。

Who cares if if your competitive ratio sucks if you're almost never page faultton。

We should declare victory at this point。And it seems like an obvious thing to do。

 But this' is actually very rare in sort of theoretical algorithms papers。 So it's， it's a small。

 I think， very cute point， okay。So let's just write good enough。For small enough epsilon。O。

So the claim is not that the competitor ratio is small。

 The claim is that the absolute performance is small。So the final theorem is the following。

And this is just， I'm not going to do the proof because the proof is just setting parameters。

 it's just setting L and B to be suitable functions of these other parameters。But。

For all Epsilon Delta of you're choosing and for all upper bounds on cash sizes n。

It should be for all sigma2。For all， but a deelta fraction。Of cash sizes。In the range1 through n。

Either。The competitive ratio is constant。And specific it's constant for constant epsilon and Delta。

 so specifically it's one over Delta。Log one of Repsilon。Or two。Page fault rates。Is it most epsilon。

 And by page 4， the most epsilon， I just mean this。So again。

 there's two compromises in Young's theorem， which lets us dodge the lower bound of k。

 First compromise is we punt on a fraction of the cache sizes。

 The fraction that we punt on is a parameter that we can tune however we want。

 So maybe think of Delta as like 0。1， say。Secondly。

 we allow ourselves to argue good performance in two senses， the standard relative。

 competitive ratio that being constant or alternatively absolute performance， okay。

 just in terms of the page fault rate， So those are both crucial ways that we dodge that lower bound。

The final point I want to say is just that， there's a lot of parameters here。

 but keep in mind the algorithm is fixed。 the algorithm is just LRU。

 We are not somehow tuning an algorithm according to data。

 So you can this is really an infinite number of theorems。

 pick n epsilon and deelta however you want， all of those guarantees are true for LRU。 for example。

 if you want， if you want to be more permissive on the page fault rate。

 you're going get a better upper bound on the competitive ratio。 Similarlyly。

 if you're willing to tolerate a higher fraction of bad cache sizes。

 you're going get a better relative bound for the competitive ratio in these cases。So that's。

Today's lecture on Wednesday， we'll start talking about how do you differentiate。

 say LRU and PIFO for that， we're going to have to start talking about models of data。

 The solution will be to parameterize page sequences with respect to the amount of locality that they possess because really we sort of know from practice。

 That's why LRU is better than PIFO so that's going to be Wednesday。 See you then。

