# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p04 -04-(Lecture 4_ Parameterized Analysis of Online Paging).zh_en -BV1yqVzzqEQ5_p4-

As far as what we're going to do today， we're going to start talking about parameterized analysis。

 so that'll be a theme for the next couple lectures and it'll recur throughout the course。

 and we're going to apply it specifically to the exact same online paging problem that we talked about on Monday。

 we'll talk about how to parameterize the performance of caching algorithms via the locality in the data。

 and that'll allow us to finally say in a rigorous way that the least recently used policies better than alternatives like in first out。

So let me just sort of remind you know conceptually what we're in the middle of doing and what we did on Monday。

 So we talked about online paging and I introduced you to the dominant paradigm traditionally of competitive analysis and competitive analysis got a pretty bad report card when we scored it according to our goals for algorithmic analysis。

 So the first goal of either predict or explain the empirical performance。

 it was a total disaster because the competitive ratios remember growing with the cash sizes were sort laughably huge。

 there was no way we could take them literally as performance predictions。 that was the first issue。

 the second issue is that while it was a partial success in that it did identify at least recently used in some sense our ground truth solution。

 as an optimal online algorithm， other things were also optimal。

 including relatively clearly inferior solutions like flush wind full。

 So Monday I also introduced to the idea of resource augmentation and so what we did there is the good news is we made absolutely no compromises as far as doing worst case analysis。

 We still got guarantees input。By input， but by changing our comparison， changing the benchmark。

 comparing to optimal solutions， while still offline with smaller caches。

 we got much more sort of meaningful and interpretal guarantees。 So for example。

 if we had double the size of the offline optimal we were getting within a factor of two and again even in the worst case So that was really good for our first goal it gave us sort of know bounds that we could know perhaps interpret as some kind of guarantee on real instances but this you'll see on the homework number two。

 we actually made no progress Monday on differentiating LRU from other algorithms okay so on the comparison goal of getting a nice ranking of algorithms we haven't really done anything yet and that's going to be the purpose of today so。

Intuitively， you know， the reason we believe LU is better than alternatives is because of properties of real world data。

 So we shouldn't expect to see a theorem which singles out LU without somehow articulating those properties of real world data。

 Okay， so that's what we're going to do today。 We're have We're really going parameterize data according to the locality。

 And that'll allow us to prove that LU is better than alternatives， okay。So that's what we're doing。

 Any questions make sense， motivation clear。Okay， so just to sort of couch this as part of a bigger picture or a bigger theme of the courserus。

Let me tell you what I mean by parameterized analysis。And in fact。

 we already saw a really nice example of this exactly a week ago。So。You know， it fix some problem。

 It could be paging。 It could be 2D maxima。 We'll see many other examples of problems in this class and think about this set of inputs。

 Okay， so this's this big， rich set of all the different inputs you might have for this problem。

And so parameterized analysis is a way of trying to， know think at the。

 you at a pretty detailed but still know alyzable level of granularity about algorithm performance。

 Okay so the first thing you want to do。Is you want to have some kind of natural parameterization。

Of all inputs and intuitively。You want to think about this parameter as somehow measuring the easiness or the difficulty of this particular input。

 okay？So for example， we might hope that paging sequences in some sense get easier as they in some sense have more locality and we'll have a formal definition of that。

And so basically， you wind up having this。Ranking of inputs。According to this parameter。

 which of course you have to make up， you have to sort of come up with a good one。

And another way of thinking about this， for those of you who have seen it is we can sort of interpret this as a condition number。

 if that's a phrase that you're experienced with， again。

 a sort of measuring sort of input difficulty in some sense。

Now you want to somehow connect the easiness of an input to the performance of algorithms。 Okay。

 so again， anyone can just sort of propose numbers about inputs for them to be relevant for algorithm analysis。

It should be the case that you can express the performance of some algorithm or maybe many algorithms in a sensible way in terms of this parameter。

So you want to talk about the performance analysis of an algorithm， the number of page faults。

 the running time， whatever。As a function of the parameter。And you know。

 what we somehow have in mind is that as the input grows easier， the performance of。

 our favorite algorithm or every algorithm is going to get better and better and better。

Performance should improve with the easiness。So we've already seen a nice example。

 a parameter analysis， which was last week， the Kiippatrick Sideel algorithm。For 2D maximum。Now。

 the point of that lecture was not parameterized analysis per se。

 The point of that lecture was instance optimality。

 proving that this algorithm was best possible in some sense， input by input。

 But as we said many times that lecture， a prerequisite to proving instance ox result。

 you need to have a lower bound that applies to every single algorithm which is tight and certainly a minimum prerequisite is that it at least understand completely the running time of your protagonist algorithm in that case。

 Kipatrick side dell。 So we need a tight input by input upper bound on Kipatrick side dell。

 and then we had this sort of hierarchy of finer grainined guarantees right So first we said。

 oh what if we only parameterized by the number of points in the input size。

 Well then it was easy to prove an upper bound of n log n and there exist input endpoint datas where that's tight。

 but it wasn't tight input by input， It was only tight in the worst case for each value of n。

 So then we said， okay， let's have a more sensitive， a more fine grainined parameterization。

 Let's also throw in the。Output size， the number of maximum H。

 And then we're allowed to have some running time analysis， which depends on both n and H。

 And on the homework， you gave an upper bound of n log H。 And that's also tight in the worst case。

 But it still wasn't good enough， For instance， automatic result。

 So we parameterize it at an even finer level of granularity。 Okay。

 so all of these are examples of parameterized analysis。

 What's changing is just sort of know how many parameters do you have to work with。

And so how tightly can you fit your analysis to the actual performance of the algorithm。

 the first parameterization was just by n the number of points。 Then it was by N and H。

 And then the final one was this sort of crazy expression where you minimize over all the legal partitions。

 and you have this entropy term the sum over the eye。

 the Carneality of S log n over Si And so that actually was sort of such a fine grain parameter。

 It actually characterized up to a constant factor， the running time of the Kirkpat Sael algorithm。

 Okay so that was sort of just wildly successful parameter analysis of of a very nice algorithm。

 And again， remember， this is always just in the analysis。 right usually when we're doing this。

 the algorithm we have in mind is dirt simple or at least small lines of code。 Cripat Saideel。

 it's very clever algorithm， but it's very succinct to describe very elegant。😊。

We recently used very simple algorithm。 Okay， we want to do the same kind of approach there。

 All right， So remember， all of the kind of work that we're doing in parameter analysis is just in hindsight。

 trying to figure out when the algorithm works well and when it doesn't work well。All right。

So why do this， Okay， so what's the motivation， Well， there's two motivations。Well。

 these two motivations。 The first one is just， there's an algorithm you really care about that。

 for example， you already have it implemented and it's sort of at your ready disposal and you can use it on problems if you want。

 you want theory to kind of tell you， you know when is it going to work well。 So again。

 the best case scenario is you just have some great worst time bound。 it always runs in linear time。

 then great， use it always But for lots of algorithms， either the running time or for heuristics。

 the solution quality will be good on some inputs and bad on some other inputs。

 And if you have a very finegrained understanding of its performance。

 and you know something about your inputs， you know it condition number， It parameter value。

 then you can reason about whether this is the right algorithm to use in that setting or not。

 to give a very simple example， which you should be familiar with， just think about graph algorithms。

 So when we study graph algorithms in undergraduate in 161。

 we actually parameterize the running time， not just by one thing but by two things。

 the number of vertices， usually called n， the number of edge is usually called M。

 And so you depend on both。 And you know， if you start looking at the running time。

Of different algorithms for a common problem。 sayy all pair shortest paths。 You see that。 Well。

 you know， there's some combinations of NMm where you want to use one thing。

 like maybe you want to use dikeres and times。 And then there's other graphs， like， say dense graphs。

 or you want to use something else like Floyd Warshaw。 So depending on the edge density already。

 that' sort of a very coarse parameterization that tells you whether you should use algorithm or algorithm be for a problem based on some easily computed statistic of the input。

 Okay so that's a reason number one。 Okay， fine grand understanding of an algorithm performance tells you when to use it and when to not use it。

The second reason， and this is going to。Show up in this class。

 especially in the smooth analysis segment。 But it's also， you know。

 going be really kind of the overarching narrative today is， you know。

 suppose you have an algorithm and it works great in practice。 Okay。

 so meaning on certain benchmarks or certain classes of inputs。 And you want to have an explanation。

 Okay， So again here we're gonna to be the natural scientist explaining this observed phenomenon of good empirical performance。

 And approach to doing that， which is exactly what's going to play out today。 So first of all。

 you do this kind of parameterized analysis。 okay， well some inputs are easy。 Some inputs are hard。

 for example， some inputs have a lot of localities， some inputs don't。 Okay。😊。

And so what you might want to then do is say， well， as long as the input is easy。

 as long as it has the sort of small parameter value。

 then this algorithm that's used in practice provably performs really well。 Okay。

 so maybe the worst case analysis says it's not so good。 like think about the simplex method。

 but at least on easy inputs， according to some condition number。

 according to some parameter It is good。 So that's step 1。

 Step 2 is you make some argument about why real world instances actually have small parameter values are easy in this sense。

 maybe this is just something you compute on your benchmarks。 And you just say， look。

 I compute the parameter and it's small。 for example， Or maybe you have some theorem which says oh。

 if it's a randomly generated instance， then it's easy in this sense。

 Okay so it's a two step approach to explaining good empirical performance on real world instances。

 proving that the algorithms good on easy instances， prove the instances are easy。Okay。

So like I said， I'm giving you this high level discussion now because there'll be several parts of the point that we'll sort of be able to slot into this kind of philosophy right。

 but now let's just do this kind of very literally for a problem we're very comfortable with at this point。

 which is the online pageaging problem okay。All right。So now zooming in to paging。

So what should the parameterorization be？So again， the intuition， we know what we want。

 We want over here。 we want there to be page sequences， which exhibit a lot of locality。

 And over here are page sequences which don't。So we need some way to measure or quantify the locality of a page sequence and there's not a unique way to do that。

 I'll show you there'll be others on the homework， but I'm going to show you a very natural one here。

So I mean this is an old idea not invented by theorists， been around for a long time。

 called the working set model。Almost 50 years old。So we're going to parameterize locality by a function from the natural numbers to the natural numbers。

And the point of this function is basically to say how many repeats。

 how many repeated page requests you're going to have in a given window。

 a given sub sequenceequence of a page sequence。 Okay， And so in some sense。

 the more locality you have， the more page repeats you're going to see， all right。So， formally。

We'll say that a page sequence sigma。Conforms to this function， F if。For all window links， W。

And for all windows。Of size W。Okay， so by window here， I just mean know somewhere in this page。

 she wins W requests in a row。Then the number of distinct pages requested。Should be at most， F of W。

Okay。So FFW is an upper bound on how many different- I mean， you see W page will press total。

 but the question is how many different pages are those four， and it's going to be at most F ofW。

 four sequences that conform to a given function？So for example。

 let's just kind of play around in this a little bit。So what if F is the identity function？

What restrictions does this function and legality for it impose on page sequences？No restrictions。

No restrictions， right， It just says for every window of length N。

 there can be at most in distinct pages。 Well， there's only end pages there。 Okay。

 so it allows them all to be distinct。 Okay， so no， if it's just the identity function。

 no restrictions。So no restrictions。What if。This is， again， just another sort of silly example。

 What if F of2。Equals one。So f of1 equal1 says nothing。Okay， that just says like a page is a page。

 What if actually F of2 is one？What page sequences are？Legal， the pages are the same good。

 all the pages are the same。 So only the constant sequences， right。

 So it says in a given pair of successive pages， they have to be the same。

 But then by transitative quality， it means everything's the same。So only constant。

 so these are both kind of dumb examples。Just to get that out of the way。So only constant sigmas。

Okay。Now， what I might want you to have in mind， we'll do some， you know， more detailed examples。

 But just for now， maybe think of two candidate F's as F being， roughly root in。

Or F being like a login。Okay， so those are two things I want you to kind of have in mind is what F might look like。

So in other words， so if it's a root in that says， you know， if you're looking at。You know，100。

 a window of size， 100， you're only going to see 10 different page requests and so on。

So log would say you look at a window if it size 1000。

 you're only going to see 10 different page requests。

So that's the kind of thing you should be thinking of。And intuitively， we're thinking of smaller F's。

That doesn't quite make sense because there's in a total ordering on functions。

 but is roughly speaking， smaller F's correspond to more constraints。

 higher locality so the smaller the F， the easier in some sense。

 the sequence is sigma that are legal for that F。All right。Good。So in this theorem。

 we're just going to focus on one theorem in this。Lecture， full disclosure。 It has two parts。

 three parts， but it's basically just one result。 I think it's a very satisfying result， actually。

And so I want to build up to the statement of that theorem。And let me sort of highlight。

 what are the two kind of nice modeling ideas that the authors had that allow this theorem to exist to escape the kind of prisons we' were stuck with on Monday。

So the first idea。Is to use parameterized analysis。So we're going to parametermeterize。

The performance of a caching algorithm。Via this function F。Okay，Now， usually parameterize analysis。

 it's kind of a little simpler if you just， you know， parameterized by a single number。

 not by an entire function， but because we have this variable cache size K。

 sort of seems like you need to have this parameterization by the entire function。

 Okay so it seems like the right thing to do for this particular problem。Recall， for example。

 in Kiurrkpat Saideel， our condition number， our parameter was just a number。 Okay。

 It was just something like， you know， 17240。 Okay， here it's really a function from。

Natural numbers to natural numbers。Okay， so that's the first really good idea。 Okay。

 So do parameterize analysis with respect to this， really you know。

Quite uncontroversial way to articulate locality。Now this is not enough， it turns out。Okay。

 if you don't think about it very long， you might hope that just， you know。

 already you're going to be golden that basically oh that competitive ratio of K was an artifact of not doing parameterized analysis。

 but actually， it's a little more complicated than that。So on the homework， this is one going out。

I'm going to ask you to show that even if you look only at the subset of page sequences that conform form with a function F。

 and it basically doesn't matter what F is。 Okay， root n， log n， even much smaller than that。

 any nontrivial F， it doesn't help。 Comp ratio stays stuck at K。

 even if you just zoom in on the sub sequenceequences， legal 4。Okay。

So that's annoying because it seemed like a really good idea， Okay， but actually。

 it is a really good idea。 Okay， And so just in general。

 if your gut feeling is that you have a really good idea and you're stymied by some kind of stupid examples。

 don't give up。 Okay， make some more changes。 know， keep pushing。So that's what the authors did。

 And so this just sort of shows you， we need a second idea to start having meaningful analyses。 Okay。

 and the second idea is also。Kind of very simple， but people generally just weren't analyzing things this way。

 which is we're going to switch when we talk about good performance， we're not going to。

 instead of talking about relative performance instead of comparing to an optimal offline algorithm。

 we're going to talk about absolute performance。 We're just going to talk about the page fault rate。

So that's the second idea。So we're going to use the page fault rate。

AndRemember what this means So this means for a given an algorithm， you run it on the sequence。

 You just count the number of faults， and you look at the length of the sequence。Okay。

 that's the page fault rate。 The fraction of the pages on which you missed。 Okay。

 So this actually showed up on Monday。 you might recall in Young's theorem。

 the guarantee was good performance in two senses。 Either relative or absolute。

 So case 2 in young's theorem exactly said that this quantity was most epsilon for L R U on most cash sizes。

 Okay， so you have seen this before。Alright。But this lecture。

 we're only going to discuss the page fault rate。And the really good idea here is we're really bypassing the need to compare。

 we no longer have this benchmark， our benchmark now is sort of zero。The absolute benchmark。

 And we're no longer using this optimal offline algorithm as a benchmark，Can get you in trouble。

 because if you think about it， we're only analyzing online algorithms。

 So it's just sort of very indirect to can take two online algorithms and compare them both to this option。

 which is not on the table。 It can be useful。 Don't get me wrong， but it can get you into trouble。

 Okay， because it's really just sort of too powerful in some ways。 So we're skipping that comparison。

 So that's the second ingredient， which makes this all work out so nicely。Okay。All right。

So that's what we're going do。 We're gonna to ask basically。 So again， combining these two ideas。

 we're going to take caching algorithms like LR U。 and we're going quantify the page fault rate。

As a function of the locality， as a function of F。Okay， that's what the theorem' is about。Okay。Good。

 so let me state the main theorem for you。I'm going to leave a few things in the theorem undefined for a minute just so that the conceptual content of the result really shines through。

So as I write it down， I'll tell you。What is not yet defined？So here's the main result。And it's not。

 you know， as paging results go， it's not that old。 It's from O2。 So it is from this century。Unlike。

 a lot of the。Well known。Paging results。So like I said， three parts。

The first two parts are analogs of things we had on Monday in terms of the competitive ratio。

 but instead in terms of the page fall rate。So the first statement is going to be a lower bound that holds for any deterministic online algorithm。

 Okay so that's going to be a line in the sand that tells us what we're shooting for。

So for all concave F。So I haven't told you exactly what concave means， but again， think Ru An log in。

 should have。Good notion of what concave means， even though these are not real valued functions。

For all cash size is k。The worst case fault rate。And here， when I say for worst case， remember。

 we're parameterizing by F。 So when I say worst case， I mean。

 over all of the sequences sigma that conform to F。

 Okay So F is sort of restricting what I'm doing the analysis over at the moment。

So the smaller f is the fewer sequences I'm arguing in the worst caseover。

So the worst case fault rates。Of every deterministic。Online algorithm。Is it most？S number。

 and I'll give you a close form formula for it in due time， Al sub f of k。K is the cache size。

 F is this function we're parameterizing by， and alpha is some function of both of those two things。

 but whatever it is what it is， and you'll know exactly what it is shortly。

So the lower bound is the first part of the theorem。

B is going to be a statement about the optimality of LRU。Okay。And it's going to know。

 so we had optimality of LRU for the old competitive analysis model。

 what's better here is sort of two things。 First of all， once we work out some examples。

 we'll see that this is actually small in lots of interesting cases。

 So we' actually get sort of a good absolute bound。

 The second thing is LR is going to be optimal in a more strongly parameterized sense。 So And again。

 this analogy with Kirk Patrick Saideel。 if you parameterize only by n。 Well， yeah。

 Kirkpat Sas optimal。 N log n， you can't do better without parameterization。 But then the more。

 you know， finally you parameterize the harder it is to say you're always optimal for all values of the parameter。

 So same thing here， we're gonna say L is optimal no matter for each fixed choice of F and K。

 on Monday， we only have that LU is optimal for each fixed choice of K so here it's also function by function optimal。

 So that's an improvement。 that's already。😊，Quite nice。So for all F and K。Worst case。Ft rates。Of LRU。

Is it most。Alpha F of K。Okay， so optimal for every F and K。

 worst case over sequences consistent with F legal， What am I calling it conforming to F。So， again。

 but this is roughly analogous to what we had on Monday。 It identifies LRU as optimal。

The issue on Monday was other stuff which kind of shouldn't have been optimal。

 was also called optimal， okay。And the third part of the theorem says is that is no longer true。

So specifically。There exists。A con cave F。And a choice of K。Such that the PIfo。Worst case fault rate。

Is strictly bigger。T this number， alpha f of K。Okay，And then， of course。

 something like flush when full is going to be even worse than PIfo okay。So finally。

 we have a rigorous separation in part C， while really combining。B and C。Between LRU and PIFO。

 And we got it by parameterizing the locality in the data。

 Okay so it really jives with our empirical intuition that LRU is better than something like PIO because of locality。

 It's the theorems actually expressing that very cleanly。

So this this is the main point of the lecture。 Okay。

 the fact that you know under some very easy to swallow kind of modeling choices， we really。

 I think get what we want。 And again once we start seeing what the value of alpha is will be actually even happier。

 I'm really stressing the fact that this solves our second goal。

 the comparison goal trying to identify a uniquely optimal algorithm， but in fact。

 know once we evaluate alpha， we'll see actually our performance know our guarantees are more interpretable and meaningful than we had before。

 So there's also for icing on the cake progress on the first goal。Okay， any questions about。

Motiation。All right， so to prove it， I obviously have to tell you what this alpha is。

So let me talk about that。Alright， so here's how I want you to think about these functions， F。Okay。

All right，So remember what F says right， So F of N says how many distinct distinct pages can be requested in Windows of length N。

 Okay， so it's the most n。 That's the unrestricted case。

 The smaller F of N is the more locality you're imposing on Windows of size N。

So F of one has to be one。 We agreed that if F of2 is one， then it's trivial。

 It's only constant sequences。 So we can ignore that。Let me also point out that there's。

 there's never a reason to have a jump in this function。So like， imagine， you know。

 I told you that in every window of size 7， you're never gonna to see more than four distinct pages requested。

 Well then automatically in any window of link 8， you're going to see the most  five pages requested。

 Okay， so just， it's a logical implication。 One more thing in your window at most one more distinct page。

So as you go down here， this number is either going to stay the same or it's going to get incremented by one。

 those are the two choices， okay。So for example， one function that might show up would be this one。

So that would be kind of a function that we might be talking about。Allright。

 so now a little notation。 And then I want to define what I mean by concave。So by。MJ。I mean。

 the number of columns were Js on top。Okay， so in other words。

 the number of different elements of the domain where the function evaluates to J。

 how many different inputs give you the output J？So here， M1 would be equal to 1。 M2 would be 2。

 M3 would be 2。 sorry， M2 would be1。 Excus me。 M3 would be 2， M4 would be 3 and so on okay。So， MG。

Number n， such that F of n equals J。And by our previous discussion。

 these are consecutive elements in the domain because you don't have any jumps in this function。Okay。

 good。So what do I mean by concave。 And this， this actually won't show up in the proof very much today。

 But just for completeness， by concave， we just， I'm just going mean that。The sort of level sets。

 So the number of points in a row where the function stays constant。

 that's only getting larger as we look at higher and higher function values。 Okay。

 so this isn't know， literally a concave function in the way that you learn it in calculus。

 But and in fact， they call it concave star in the paper to make that distinction。

 But the spirit is the same。 Okay， it's sort of growing more and more slowly as you look at larger and larger values。

So this， for example， at least the part of this function I've shown you does conform to this。

 because we have M1 equal1 M2 equal 1， M2 equal 3， M3 equal 4。Okay， so if this next value was a 6。

That would violate this concave restriction， because then M5 would be one。Good。

 that's what I mean concave。 So what do I mean by alpha。So here's the magic parameter。

Can you see this color。So for a given cache size K and a given function， F。Oh。

 I get another definition here。 But so this is going to be。And again。

 once we prove all of these statements， you'll see that this， you know。

While seemingly obscure looking， this actually really is the right answer。

K minus1 over the inverse of F。Evaluated at k plus 1 minus2。So what do I mean by the inverse of F？

So because remember， in general， these functions， F will take on this value many times。 Okay。

 So like if I wanted to say， oh， let's invert this function F at the value 4。

 It's not really defined， right because 5，6 and 7 all evaluate to 4， okay。

So the inverse for this class is going to be defined as the smallest domain element。

 which gives you that value。 Okay， so for this function， the inverse of 3 would be 3。

The first time you get three。The universe of four would be5。

The first time you see a four and the inverse of 5 would be eight。Okay。

Here's the reason why this inverse is going to be。's going to show for a couple of reasons。

 But one way to think about it is， suppose there's some window。

And I told you that P different pages got requested in this window。Okay。

If you know that in this window， P different pages got requested。

 then you immediately know that the window has to have size， at least F inverse of P。Okay。

 and that's why we define is the minimum。 that's how we're going use it。

 So it's really the minimum number。 It's the minimum window size such that you could see that many distinct pages in the window。

All right。So。Let's just get a little bit of a feel for this function Al， since it is， after all。

 governing our fault rates。And then once you kind of play with a few examples。

You either take questions or move forward to the proofs。So some examples。

So suppose F is the identity function。What is alpha F K as a function of K。Yeah。

 so this better be a number between0 and1 always， because it's allegedly a page fault rate。

 It's only meaningful when it's between 0 and1。And if it's the identity function。

 then the inverse is just itself。 So k plus1。 So we K -1 over k -1。 So it's1， no matter what K is。

So alpha F of K equals1。 So that's， you know， remember， this is the fault rate。

 So this says you might be faulting every single time step。 But again， for worst case sequences。

 we already know that's true。 That was our lower bound on Monday。 Okay， so this， you know。

 it's not this basis is no parameterization。So how about if F of n is roughly root in。

 it's growing like root n？So for sufficiently large K say。What is this going to be roughly。

So we're going to better be between 0 and1。我都我都。Yeah。So。If F is like the square root。

Then the inverse is like the square。So down there， you're going to see it're basically like a k squared。

 So like K over K squared。 So that's like one over K。So that's already， like as a page fault rate。

 that's actually sound pretty attractive。 if cases pretty big。 It's pretty big cash。 Okay。

 so for this root end function， which is not unreasonable。 as far as modeling realro locality。

 we're getting a page fault rate dropping inverse linearly in the cash size。

 It's actually quite attractive。😊，And then you can imagine if there's even more locality。Like。

 say F is growing as the logarithm in N。 Well， then the inverse of the log is the exponential。

 So this is going to be like  two to the K。Okay， this is going to be like K over 2 to the K。

And in that case， even if K was just like 10， you'd be seeing a fault rate of like 1%。 O。

 that's a pretty extreme locality， but。Still， it's kind of you start getting very attractive bounds very quickly。

So I think what I've now done， hopefully， is I've both given you a completely formally specified theorem。

 So we're in a position to try to actually prove it。

 And I've also tried to back up my previous statement that even though I'm emphasizing the progress on making strict comparisons between algorithms。

 We're actually getting quite meaningful guarantees， even sort of taking these at phase of value。

 They already have。😊，Pretty solid meeting。So any questions about any of that？

I it realistic to model real data as with a concave function， that's a good question。

 So the question is， to what extent does real data conform to a concave function。

Pretty often it does。 or it's very close。 actually。 Okay， So's you know， again。

 this was not a model invented by theorists just you know， looking for something to analyze。

 It was really more， you know， people doing experiments and seeing what kind of functions they got。

 And they're often sufficiently close to concave that that was proposed as a property they often have。

 Another thing I want to point out is remember that we're using this function in the analysis only in some sense。

 So suppose you have a function which is not quite concave。You know， it was a little bumpy。

Then what you can do， what you want to apply the theorem， you can say， well。

 the sequences that conform to this function are a subset of the sequences that conform to this function。

If I make the function only bigger everywhere， then I only permit more sequences to be legal for。

 to conform to it。And so then you can just， then the theorem just applies， actually。To。This curve。

 and then sort of by monoticity， the same guarantee holds for the original curve。

So that's another trick。 The final thing I want to mention is that actually， in our upper bound。

 So the main place the concavity shows up is actually in this lower bound， Part A。

 So sort of arguing the tightness of our upper bound。 So I'm actually。

 I'm not going emphasize this point， but I will use much less than concavity when we actually prove B。

😊，So we actually so it's an excellent question， it turns out for all those reasons。

 I don't think we should be very disturbed by this concavity assumption。Other questions？All right。So。

Alright， so let's prove them one at a time。 So we first have the lower bound。

For any deterministic online algorithm。Then we'll do the upper bound for LRU that will match for each f and for each K。

 and then I'll exhibit an F and K that separates PO from LRU。All right， so the lower bound。

So the starting point for the lower bound is the same lower bound that we had on Monday。

 showing that every deterministic online algorithm has competitive ratio K。So we're going to fix K。

SoWe're going to fix F。 Remember， for every K and F。

 we need to show that this is a lower bound and and every algorithm we have to show that's a lower bound。

So fix K and F。And just like in Monday's lower bound。

 we're going to assume that the number of pages is just K plus1。

 so at any given time step there's exactly one page missing from the cache okay。Now， at this point。

 we realized we have to do something a little different， though， right So F could be anything， know。

 but maybe it's rude end to say， okay。So the previous lower bound。

 what it did is it kept requesting adversarally the page not in the cache of the current online algorithm。

 because guess I should fix the algorithm， too。So fix。Algorithm a。Deterministic。

But if you think about it， that might generate a sequence where， you know， in a given span of all。

 you N pages of n requests， you see all n different pages。 Okay。

 and that's not going to conform to most functions like if F is root end。 Okay。

 so which is which is what we want to have happen。 right。

 We kind of want the old data example to kind of go away to be illegal。

 That's the point that parameterization。So instead， in this proof。

 we're just going to simulate that lower bound， that sequence as well as we can。

 Sub to conforming this given function F。 Okay， and in fact， there's a generic way to do that。

 that's that's what I'm going to show you now。So here's the bad sequence。The bad sequence for a。

So the way we're going to just sort of you know copy the same idea but conform to F is we're going just request a page many times in a row。

 now obviously this algorithm will probably only fault the first time we request it。

 know if we request it again the next time step， it's not going to fault on it。

 So our fault rate won't be as high as we'd like it to be as the adversary。

 but that's the best we can do。 it turns out okay。So the sequence begins。

 So it's going to be in phases and these phase'll just repeat。 They'll be the same。

So we start with M2 requests。 What is M2， you ask。 Don't forget。

 that's the number of different domain elements on which F evaluates the2。 Okay。

 so the number times2 shows up in the upper row。So M2 requests to P1。What is P1 you ask。

 Well I'm going to define P1 just as whatever page happens to be missing from the cache at that time。

So remember we have this algorithm so we can just simulate it on what we've done so far。

 and I've ever given time steps， some page is missing， so there's a uniquely defined missing page。

Okay， missing from cash。And then we do M3 requests to P2， P2 is whatever just got evicted。Okay。

 so again， that's just whatever is missing at the appropriate time step。M4 requests to P3。And so on。

You might have repeats， okay， that's fine， could be the same page shows up more than once。

 doesn't matter。You're just always requesting， you know， so at the beginning of one of these things。

 you're always requesting whatever' is missing to ensure that A picks up a fault。Okay。

And then finally， at the end。And K。Requests。To P K -1。Okay。

So that's just some finite sequence of requests。 We want arbitrarily long sequences of requests。

 So we just repeat this as many times as we want。 Okay， arbitrarily large number of tonguens。

And when I say repeat this an arbitrary a large number of times。

 I don't mean you remember the identities of these pages from the previous phase。

 I just mean like whenever you get here， look at what's missing and request it and then request it another MJ -1 times。

再做了毕。So is that construction clear， we have to analyze it。

 but do you see what sequence of pages we're feeding into the algorithm。Okay。All right。

 so let's compute the fault rate。So all these phases are the same。 Let's just focus on one phase。

So how many faults does A suffer？In a single phase。But a hand。How it there。Theres one。P。

 so the phase is this whole thing。あ。So呃。对。K -1， exactly。 So one fault there， one fault there。

 one fault there and so on。 Okay， And's K  one of these， All right。So。A faults， K -1 times。Perfect。

Now， we're interested in the average or the fault rate。

 So we're interested in the fraction of the phase， which result in faults。

 So we need to compute the length。 We know the numerator。 We need the denominator。So length of phase。

Well， that's obviously。M2 plus M3， blah， blah， blah， blah。Up to M K。

So how should we think about that， Well， so for starters。Just as a thought experiment。

 imagine there isn't， but imagine I threw in an M1 here。Okay。what would this mean？Well。

 now you just be skipping through this table。So M1 is the number of times1 occurs。

 M2 is the number of time two occurs，3 occurs。Four occurs and so on。So by adding up M1 through M K。

 you just skip through this table through all of the entries that are1 through K up top。

 so where do you find yourself at the end of that skipping through one through K。

 you find yourself at the very first column at which F takes on the value K plus1。

Also known as the inverse of F at K plus1。Okay。So if I threw N M1。It would be the inverse of F。

A K plus one。See that agree。O。Now M1 isn't there。All right， so we have to subtract that back out。Oh。

 heading off by one ear， actually， didn't I。Yeah， sorry。 So let's do this let me。 let me clarify。

 So suppose Am was there。So let's think about here， so M1 is1。Okay， M2 is also one。And then， M3 is 2。

So let's just look at M1 plus M2 plus M3。That would put me in the fourth column。

 so M1 plus M2 plus M3 puts me in the column， which is the last one at which the function has the value 3。

If I add in M4， then I add in another three， I'm in the last column where the function takes on the value4。

 so I'm actually in the column prior to the one， which is the first at which it takes on the value K plus1。

Okay。So if the M1 is in there， then this evaluates。To F -1 of k plus 1-1。Okay。Again。

 so where do I wind up， I wind up in the last column where it takes on the value K。

 one before the first column where it takes on the value K plus1。Okay。Now， M1 is not in there。

But remember' assuming M1 is one。Okay， if M was 2， then f of two would equal 1。

 and we have only the constant sequences。 So forget about that。So M1s one。So without M1。

Then what this is is the inverse a K plus1-2。So the numerator is k minus1。

The denominator is F -1 to k plus1 -2。And that's exactly our faultright question。

 Can you repeat Why can M1 be So it could。 So here's the， So if M1 was 2。

That would mean an F takes on the value one twice。So it would mean F of 2。Is equal to one。

Which is possible， but we agree that F2 equals1 means it's only only the constant sequences。

 So everything has page fault0， So the theorem is true。 So precisely， I'm saying。

 let you know let's once and for all treat the M equals bigger M1 bigger than one K separately。

 And now for the rest of the lecture， pretend like it's not true。So that's the formal argument。Okay。

S that's where the fault rate。Computation comes from。 so the numerators came at1。

1 fault from each of these lines。 and the denominator comes from just the length of this phase。

So we done？Finish proof of A。对啊。Is the storage case sequence。Well， I mean。

 I guess part B is going to be an upper bound。You haven't yet shown that this actually does conform the constraintss。

So it's not a complete proof。And actually， this part of the proof， it's not too hard。

 I'm going to kick it out to the homework。Which is to check。 So remember。

 why did we bother doing this， You know， why did we bother sort of requesting the same page over and over again。

 which from an adversary， it kind of seems like a stupid thing to do。

 right We're trying to make you fault a lot。 So why do I keep request the thing I just did before。

So remember， the reason we did this is because the adversary has to generate a sequence that conforms to F。

Right， and I didn't actually prove that that does that。 Okay， but it does。 Indeed， you know。

 we I won't surprise you to hear that we chose this particular duplication sequence exactly to make it so that we could prove conformity to F。

 Okay， but I do want you to check that， All right。So check that this sigma。Conforms to F。

And then modlo， that check。That's the proof of part A。Okay。그。I'm not clear on why a false kis times。

Sure， so that's so that's just by definitions。 Let me review the definitions。 Okay， so remember。

 there's the number of pages is exactly one more than the cache size。 So in other words。

 at every given time step there exists a single page， a unique page missing from the cache。

So what the adversary is going to do。 So here's what the adversary does， you know。Once in a while。

 it wakes up and decides to actually be a real adversary and make you miss。 Okay。

 And then it kind of sleeps for a while and just keeps sending you the same request， which。

 of course， at this point is in your cache。 and is doing that for the conformity right But at each time step where it wakes up。

 it says what's missing。 Okay， that's what's next。 So it's really， by definition。

 forces you to follow them each one of these lines。 exactly right So M2-1 extra requests。

 M3-1x requests。 and that's all just so that the sequence conforms death。Sure。

I'm not sure I understand why becauset started M1。Why doesn't it start， so M1， so I guess。Let's see。

 That's a good question。in the down just。YeahF fingers K plus blind。Yeah。

 and so would that be better or worse？Let's see， okay yeah， that's my concern。Yeah。Yeah。So， I mean。

 it's a valid construction。 You'd have to check the conformity， too。

 It can actually go wrong in either part。 And I'm not。 It's an excellent question。

 I'm not sure if the top my head。I mean， in some sense。

 part B will provide some kind of certificate that we're doing something right。

 because we'll match this。For each F and each K with LRU but。Yeah， I'm not。

 I I would I don't know if on my head， which of those two things goes wrong。 Good question。

On the Part B。Okay。So LRU， why is LRU good？I'm requesting on one the bricks。It bringss it farm me。

系先布先布定过而家听。Considerative function one2。あ、十。都さ。你几点带过嚟。佢系讲嘅四廿一。Which jo about this truck？Okay。Part B。

So again， for every F and every K， we want to show that LRU's fault rate is at most this on every sequence that conforms to that F。

So fix K and F。And consider sigma。The conformness to。Alright。

So we're again going to do some kind of block decomposition idea。

 although its going to be different than last time。 And in particular， I mean。

 our motivations are different。 Our motivation last time was really to compare to furthest in the future because we're trying to say this relative performance guarantee。

 And now don't have to do that。 We just have to see the page fault is small。 So honestly。

 it's kind of once you know that this is maybe what you're shooting for。

 that can definitely guide how you might want to partition the blocks。 Okay。

 if you actually believe this is the right answer。 It gives you some pretty strong clues about how to chop up the input。

😊，Okay， so。Partition sigma。Maybe I'll draw the picture first。So in hindsight。

 we want to sort of look at the page sequence and look at where we had page faults。 Okay。

 so I'll just draw a bunch of dots。And then an x， wherever we had a pageful。对。And so on。

And so now we're going to break it into phases as follows。So let's say for this picture。

 I'm going to take k equal3。So I'm going to group them into k minus1 faults。Okay， y k minus-1。 Well。

 that's in the numerator。That's the clue there， right So remember we want some sort of it's a fault rate。

 so we want to talk about number of faults on average。

 So it's natural to think about blocks where we have K -1 faults in the length of the block is going to be this。

 that's sort of what we have in mind。So K -1 here is 2。So that's going to be a phase。

That's going to be a phase and so on，So， basically， I。

A phase ends just before you would pick up that Caith fault。But these are phases。

And then we're going to ignore， So at the beginning， the prefix before the first fault。

 we're gonna to ignore the suffix where you might not fill up a phase with all K -1 faults。

Does it clear in that definition？So a phase starts with a fault。

 and then you go as far forward until you're about to pick up that ca fault。So part sigma。

 according to。Groups of k minus1 folks。All right。All right， so here's the claim。Allright。

 so the claim。Is that consider an arbitrary phase？Plus， the requests。Just before。And after。Okay。

So these extra two requests are going to correspond to this -2 in the denominator， okay。

So for example， for this phase， we would also add that fault and that fault， for this phase。

 we would add that which is not a fault and which is a fault。So fault or not。

 we just add the requests on either side of this space。All right， what's the claim say， it says。

There are， at least。There are requests for at least K plus one different pages。

In this sub sequenceequence。It's not obvious。 we have to prove this。

But this is sort of this is the meat of the proof。In fact。

 let me show you that if we prove this claim we're done。Okay。So if the claim holds。

Then every phase has on the one hand。Length， at least what？けます。

OfThenominator of the target page fall rate， exactly right， So because take the phase。

 add these two things to it， you get k plus one distinct requests。 What's the meaning of F inverse。

 It says the minimum window length。 Okay， a lower bound on the window length。

 If you know that you have that many distinct requests。 Okay。

 so F-1 of K plus1 says that's how big the window has to be。

 If you're gonna to see K plus1 different things。 Now we added two requests to it。

 So we cheated by adding two。 So we have to subtract that back out。Okay。So each phase has length。

At least F inverse of k plus one。Minus2。While， by construction。The phase includes k minus1 faults。

Okay。So in the limit， if the sequence is arbitrarily long。

 then we could ignore the kind of error terms from the beginning and the end。

 And the ratio of these two things is indeed upper bound on the fault rate。 So K -1 faults。Yeah。

 came on its own fault。Divided by the phase length。 And that's exactly alpha F。Okay。Okay。

So we've reduced part B of the main result to proving this claim。Do you agree that。Good。Now。

 it's sort of interesting about this claim。Is if you believe me。

 if you believe what I said about part C。That PIO is sometimes strictly worse than alpha F ofK。

If you believe that， then somewhere in our proof of part B。

 we have to use a property of LRU that is not shared by FiIO。

 yet we literally have not seen such a property in any lectures so far。 Okay。

 so you want to be on eye out for that。 Where are we using the fact that it's LRU and not something else。

 Okay， we certainly haven't used it in any way on these first two boards。 Okay。

 this doesn't reference the paging algorithm at all。 This is just grouping the input。

Sot it has to show up in the claim somewhere。Alright， so proof of claim。

So here we got to do a little case analysis。So fix your favorite phase。With P requested。Just before。

Okay。So depending on which phase we're talking about。

 P might be that if we're talking about this phase， if we're talking about this phase。

 P is that and so on。P may or may not have been a page fault。Either is possible。 We have no idea。

 Okay， What we do know is at the start of this phase， P is in the cache。Maybe it was already there。

 and we just got a page hit， a cash hit， or maybe it wasn't。 We got a page fault。

 but I'm going to bring P in。So pe's in the cache when this phase starts，So now consider。

The K faults。Of the phase。Let's just say。TheK also the phase plus。

The it's really K -1 faults of the phase plus the one after。Okay， so K falses in total。A phase plus。

The cave， just after。Okay， so again， we either looking at， we might be looking at these three faults。

 or we might be looking at these three faults。So now its a little bit of case analysis。

 So case there's three cases。 case one is really trivial。So we have these k faults， right。

 So like P is right here saying。Maybe that's Pete。Moving at that fault， that fault and that fault。

 Okay， And remember， remember sort of the window that we're arguing about。

 the window we're arguing about。Is this one？So we took the phase。

 we added in the thing just before and the thing just after。So， we have P。

And then we have these k faults。Now， if。All of these faults are for distinct pages that are also not p。

Then we're trivially done。This is the first super easy case。

 Okay If all of these there's K plus1 things。 if they're all distinct。

 then there's our K plus1 distinct page requests， okay。Clearly。

 this is not where we're using any properties of LOU in the proof。

 We're actually using any properties of anything。There's just to sort of focus on where the difficulty is。

So case one。All faults， all of these k faults。Are on distinct pages。Different。V p。So。

 then we're done。So if this page is like 107， none of these are 107 or none are equal to two each other either。

 then we have our four distinct requests。Any questions， yeah。And can you clarify consider Yeah， yeah。

 so。Let me just let me show you the picture。So I'm talking about one thing I might be talking about would be these three faults。

 So if we're focusing on this phase， then I'm saying consider the two faults that are inside the phase plus the fault which is immediately after the phase。

 Why do we know that exists， Remember how we define a phase。

 We say pushush out as far as possible until you're just about to pick up that case fault。

Okay so in the definition of the phase， you don't include that ca fault。 but remember。

 if you remember the claim， we're actually arguing about the window that does include that ca fault。

Its a little potentially confusing。 but that's why。 O， Or if were talking about this phase。

 then we'd be talking about its's two faults plus the third fault just beyond it。Yeah， thanks。

Other clarifications。None nonene of the action has happened yet。 So if you're confusedfuse now。

 it's just purely a handwriting or notation thing。 So any other issues。Okay。So case two。Suppose。

We have two faults。 So， again， think about these K faults。 So like  three in that picture。

We're trying to argue that there's K plus one distinct page requests， counting P。

Souppose there's two pages on the same page amongst these k。Q and not equal to P。O。

So this is a different thing that could happen。Right， so we're saying， look at。

 So there's gonna be three cases。 We have these K faults。Okay。

The third case is going to be where one of these faults is on P。 Okay。

 P is the thing that was requested just before the phase。 Okay， so we look at the K faults either。

One of them was for P or none of them are for P， okay。If none of them for P。

 either they're all distinct or they're not。We just handle the case where they're not P and they're all distinct。

 Now we're handling the case where none of them are P， but they're not all distinct。 I。e。

 some pages is faulted on twice in amongst these K。 So that's what we're drilling down on now。

What do we have to prove in all three of the cases。

 we have to somehow exhibit requests for C+1 distinct phases？Counting people。Well。

 now we're going to start，s now let's actually use the fact we're running a reasonable caching policy like LR U。

 Okay， so what just happened。 All right， so P is page 107。 We never faulted on that again。

 But there is some page 123 that we faulted on twice in this phase。 we faulted on it。

 So we brought in page 1，23。 Later， we faulted on it again。

What had to happen between those two successive faults to page 123？So basically， I mean。

 what has to happen is 123 must have become the least recently referenced page in the cache。

Which means subsequent to this fault on 123， you must have seen requests for K other pages。 Okay。

 that's the only way 123 would have been kicked out again。All right， well。

 there's our putting it all together K plus1 requests for different pages。

 so the only way 123 would defaulted on twice would be to have K distinct page requests in between。

 so we're done。Would that argument work for FIFO？We just need K plus one K， okay plus one。

 different just requests。That are not。Just any requests I guess。Right， on。

So which way are you arguing？It does work with PIO， that's right。It wouldn't work for arbitrarily。

 It wouldn't work for like LFO。A case one， that could be lifefo， it would still be true。So case 2。

 we're using a little bit of L U， but not its full power。 Okay。

 we're not using enough to separate it from PIO yet。 If you think about it。

 this isn't totally obvious。 I encourage you to think about this offline， okay。So two， but what's。

 what's the summary， two faults on same page Kinematicical P。 I'm just going to write。

Since we're using LRU， although again， this would be true for other caching policies as well。

Since LRU。Must have K， distinct。Requests。In between。The two faults。Hqu。Okay。Agreed。2。

So it must be case3 that we use something about LRU that would not be true for PIFO？

So what's the only case left？All right， so we've handled all the cases where P is not one of these K faults。

 So if cases1 and 2 don't apply， it must be that one of these K faults is on P。

So most at least one fault on P。Okay。Now， here's what you need to remember。 Okay。

 here's the subtle point。So what do we know about P， know P was requested。

By definition is that we define P， P was requested just before the phase started。

This might have been a page fault。 This might not have been a page fault。

 He may or may not have been in the cash at this time。Okay。If we're running L RU。

We don't care whether this was a page fault or a page or page hit。 either way， when P is requested。

 its clock is reset， if you like， by LRU。Okay。And if P was just requested right here。

 it's not going to get kicked out until there are requests for K distinct pages other than P。Okay。

 and P in those K other ones gives us our K plus1。Okay。Suppose we were running the FIFO policy。

If P was a page fault， we'd be okay。Because then it would basically get a clock of zero。

If P was not a page fault， if P was already in the cache and we were running PIO， well。

 then for all we know， P was brought into the cache a long， long time ago。

The FiIFO policy doesn't reset P's clock when it's requested。Okay， so for all we know。

 the very next eviction is going to e to P because it was originally brought into the cash so long ago。

Okay， so that's the part of the argument that works for LRU and does not work for the FiIFO policy。

Alrrect。So since P requested。Just before phase。There must be at least K， distinct。Requests。And again。

 all of these have to be other than PD。Before keys ection。OK。

And so that's our K plus1 distinct pages， P and the K that forced its eviction。

So those three cases cover all the possibilities。 So that completes the proof of the claim。

 We agreed that if we have the claim， then we get the desired numerator， this F -1 k plus1-2。

 We know we have a desired， sorry， denominator。 We have the numerator K -1。

 So that gives us the alphas sub F of K upper bound。For the LRU policy only。So questions about that。

So needless to say， we haven't actually yet proved a separation。Between L R U and PIO。

 we just exhibited a proof of an upper bound that happens to only work for L R U and not for PIFO。

So we don't know at the moment that there isn't some better proof。That works for both simultaneously。

So to show you that there isn't to prove C。 I need to show you an example。

So there's actually lots of examples that work。 Okay。

 I'm just going to show you one of the simplest ones I could devise that illustrates the point， okay。

 but it's not， you know， if you choose F to be the identity function， you can't separate them。

 but there's plenty of f's that lets you separate the two policies， okay。Here's one。

So take K equal four， that's the cache size。Five pages。I need to show you the F。The function。So。

 it's simple。So as soon as we there's only five pages in the world， so as soon as we get to five。

 we can just stop。So it's actually a lot like the example function I showed you before。

 which is a little bit different。So there's no locality in position until you get to windows of size4。

 you can only have three distinct pages。 and that's sort of where you start having a nontrivial restriction on sigma。

Okay。So。We're trying to show that PIO is strictly worse than that bound upper boundly proved。

 So take 30 seconds， work quietly。And evaluate alpha F of K for it。 Let me remind you what this is。

 This is K -1。Divided by F -1 of k plus 1 -2。K is 4， remember。So if you got three/ fifths。

 that's correct。Right， so K is4。 the numerator is 3。 So we have to invert F at 5。 that gives you a7。

 That's the first time you see 5。 subtract to you get5。Okay， so 60%。

 that's a really big page fault rate。 Don't worry about that。

 There's other examples with smaller page fault rates， too。

 That's just because F is very close to linear you know。

 around the cache size that we're talking about。 That's why the page fault rate is so high。

So now let me show you a sequence where PIO's page fault rate is strictly bigger。Okay。

 we know that LR U， for all sequences that conformative this function F has pageful rate at worst 60%。

 We also know from part A that there does exist a sequence where LRU is off by 60%。

 as well as everything else okay。So， here's the sequence。It's just。

 a sequence of8 pages repeated over and over and over again。Okay。So here's a。Here's a block。

 here's another block。And。There's actually pretty strong intuition about why FiIO might do worse than LRU in this sequence。

 Maybe the intuition isn't so strong。 Why it's going to do worse than 60%。 But at least on the input。

 you expect to do worse than LRU。Because， you know， is I mean， LRU is never going to evict that0。

Right， it's requested every other time step。 Okay， very first time when the cache is empty， it'll。

 it'll miss on 0， but it never misses again。 PIO is not resetting  zero's clock whenever it's requested。

 So it'll eventually get evicted once in a while。 Okay。

 So PIO is gonna incur some constant fraction of evictions on 0， as L R U will not。

So that's some intuition， but let's see what actually happens then。

So let's say we start with the empty cash。Okay。So then I'll use an X whenever we fault in a check whenever we hit。

 So it's empty。 So nothing's in there。 So， of course， we fault on one。No。

You bring that into the cash。We fall on zero， we bring that into the cache。IfYou default on two。

 you bring that into cache。 we finally get our first cache hit on zero。Right。Three。

 that's the first time we've ever seen that， so that's a miss。Three goes in there。If get hit on zero。

 it's still there。Four， we miss on。What do we evict？Right， so one was the earliest thing。

 We filled this left to right。 right， So the first first in， first out。

 So one was the first one to be brought ins was the first one to go out。So one is replaced by a four。

Zero is still in the cache we're going to get to hit。Now， one。

 we're going to miss on because we just evicted it。And now we see why LRU and PIFO were different。

So LRU at this juncture would evict the two， because that's the most least recently referenced。

PIFO is going to say what was the original entry date of each of these four numbers and zero entered earlier than the two or the three or the four。

RightSo it was this0 that triggered 0 brought in earlier than two earlier than three earlier than4。

 So PIO will evict to the0。Okay。And that'll get replaced by the one。O。

So that triggers a fault on zero。And then again， we're just going to keep， I mean。

 Pfos is the way I've set it up， it's just going to keep cycling through the cache left to right。

 left to right， left to right。So zero replaces the two。Causing a fault on two。We get a hit on zero。

Fault on， ohop sorry， I forgot to bring in the two here。So on that too we have to bring it in。

 we evict the three， then of course， naturally the three shows up， so we have to evict the four。

And we're going to hit on zero。I miss on four replace the one。And hit on zero。Okay。And now it's so。

 you know， I started with the empty cash。 And so you might have wondered if that was sort of the culprit of this X X。

 X check， X check， X check fault pattern in the first block。But we saw it， we got it again。

For the second block。Allright， and now that you've seen the second block go through。

 I think I've find it very plausible that is going repeat add infiniteum。 Okay。

 it was just keep doing cyclic shifts on exactly where the numbers are in the cache。

So the block length size is8， and each one we're faulting five times。

Five over eight also known as 62。5%。Strictly bigger than the 60%。It's not a lot bigger。

In their defense， empirically， PIO is often not that much worse than L RU。 Actually， Okay。

 it's generally worse， but it's not radically worse。 That's point number one。 Second， in this model。

 these， you can actually prove a upper bound。 You can prove a worst case theorem about PIO。

 which is not a whole lot bigger than the worst case we prove for LR U。

 Okay that's one of the problems on homework number  two。

