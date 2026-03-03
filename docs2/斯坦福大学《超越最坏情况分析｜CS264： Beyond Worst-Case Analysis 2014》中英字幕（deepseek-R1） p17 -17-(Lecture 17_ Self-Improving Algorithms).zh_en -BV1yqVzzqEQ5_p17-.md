# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p17 -17-(Lecture 17_ Self-Improving Algorithms).zh_en -BV1yqVzzqEQ5_p17-

Plan for today is something called self improving algorithms。

 So let me tell you what those are about。So here's going to be the assumptions that we make today。

SoThe first one you're starting to be a little bit familiar with。

Which is that there'll be some randomness in the inputs。

So the inputs will be drawn from a distribution。so the last four lectures。

 of both when we were talking about empirical performance of hashing and also have three lectures on smooth analysis。

 there again， we were talking about data inputs that had some randoms in it。

 and we're talking about the expected performance of algorithms。

 Today is going to be sort of a little bit different in focus in that we're really going kind of use this assumption in a stronger way。

 And in particular well be considering algorithms that are designed or even try to learn the distribution over inputs。

 So contrast that with say smooth analysis， say the simplex method or of local search where really。

 you know， distribution on inputs wasn't fundamental to the algorithm making sense。

 The distribution just served as a sort of plausible narrative for why these algorithms work so well in practice。

 it really wasn't kind of a fundamental assumption about why we were using those algorithms。Okay。So。

In contrast to say average case analysis。We're going to be thinking of this。

 This distribution exists。 Okay， so we believe in that nature is really giving us inputs drawn from some distribution。

 but we don't know what it is at the beginning。 Okay， that'll be the assumption。

So that's different than average case analysis where you。

Assume you know the distribution and then you tail your algorithm to the distribution。

 It's also different than we talked about， say planted cleeeks or planted partitions there again。

 it wasn't sort of a uniform distribution。 It was a sort of interesting distribution。

 but we sort of assumed it up front and then designed algorithms tailored to it。

And now the third point is what's really going to characterize the next three or so lectures。

 And this is going to be new。 Okay， so this is something that hasn't been true for anything we've talked about so far。

 which is that we'll actually observe multiple inputs drawn IID from the same distribution。

So observe multiple。IID。s。Okay， so concretely we'll be talking about sorting for today。

 So it means you're just given one array that another array。

 that another array all drawn IID from some distribution over arrays， okay。

So we haven't really seen this before at all and observing multiple inputs from the same distribution gives us a new opportunity in our algorithm design。

 which is now we actually have an opportunity to， even though we don't know the distribution up front。

 we can learn it or at least perhaps learn relative statistics about the distribution and use that in our algorithm so that's a new thing and we'll be talking about that for the next few lectures。

So opportunity to learn。All right。And it's easy to imagine， you know。

 not all practical applications will fall under this umbrella。

 but it's easy to imagine some that do right So if you're just sort of watching the search queries come into your search engine every hour。

 every day or whatever， you can then batch those and think of each of those as some kind of distribution drawn from you who searches for a particular query term。

 Okay so it's not hard to think of cases where you might actually want to have algorithms that indeed adapt to a distribution of input and you have enough data。

 enough independent samples of data that you actually can adapt over time。All right。

 so what do we want then？If this is the setup， so what we aspire toward。

Is an algorithm which well well initially。Does not know the input distribution。

Quickly evolves to a point where it knows enough about the input distribution that its performance becomes just as good as if we had known that distribution over inputs in advance。

So an algorithm that quickly converges。By this， I mean。

 doesn't need too many IID samples from the distribution， doesn't need too many inputs。

And then what should it converge to， well， the best thing you could do is， well。

 if you knew the distribution up front， you could run some optimal algorithm for it。

 so that's what you'd like to be。So to optimal algorithm。For the priori unknown distribution。

So you can think of it as sort of an algorithm that tunes itself to the data。

So that's at a high level what self improving algorithms are。

 and so we're going to talk about today about sorted。Okay， so obvious example。Maan example。

So this was indeed the first case study of self improving algorithms that was ever done。

So this is back in '06。Since this time， there have been follow up works dealing with other problems。

 like especially in computational geometry， so 2D maxima。

 the same problem we studied back in lecture number two， convex holes， delanni triangles。

 stuff like that。Okay。So it's the sorting model。So throughout the lecture。

 the array length is going to be just some fixed number n Okay， so fixed n。Number of elements。Now。

Each of these array entries you can think of as a real number or rational number。

And it's drawn from some distribution。So the eighth element。Of input。

Xi is drawn from some distribution DI， and again， we don't know what this is a priority。And so again。

 maybe think of this as just a distribution over a subset of rational numbers in some range。

And the DIs， we're going to assume they're independent。And I'll comment on that in a sec。And also。

 it's important that they're not necessarily identical。All right。

So let me comment on both of these assumptions briefly。

So why do we assume that the Ds are independent， It's not really because we believe in real data。

 the different array entries are going to be independent。You know。

 maybe there's some lucky applications that's going to be true。 But if you think about it。

 that's actually probably not the common case。 The reason is because positive results are only known for self-improving algorithms under this assumption。

 Okay and on the homework， you'll explore some negative results。

 some lower bounds without independence。 That said， you know。

 it seems like there should be some room in between the lower bound on your homework and the positive results in class today。

 But that's an open research question。 Okay， to get analogous positive results under some relaxed notion of independence。

 right， So this really is the state of the art， even though you really would like more general positive results。

😊，So that's why we're going to assume independence。The identical case， I mean。

 that's a special case of what we're talking about。 So in some sense。

 we will cover the identical case， but that's uninteresting。 Okay。

 so if all the array entries are drawn identically from the same distribution。

 then the relative ordering of the n elements is equally likely to be any permutation if you think about it。

 and this will become clear as we proceed， there's no opportunities to beat just your basic n log n bound when the permutation over the elements as uniform at random。

😊，So I want you to， it's not， I mean， we will handle the identical case。

 but don't think of that as the canonal case， okay。

 that's not where the results for today are interesting。All right。So， even though。The numbers are。

The array entries are real numbers。 We're going to be working in the comparison model。 Okay。

 so we're going to assume that we only can access these real numbers by comparing any pair of them。

So given D1 through DM， these independent distributions over the Xs。

I'm going to use pi of D to denote the induced permutation。

 the induced distribution over permutations。So induced distribution。Over permutations。

Of one through M。Okay。So in other words， suppose I give you some array with arbitrary real numbers。

 you know， seven fourths， negative one half， blah， blah， blah， blah。 Now。

 just imagine replacing each of those numbers with its rank。 So the number。

 which is the fifth smallest number， just imagine that's a5 and similarly for all n elements。

 so that just turns any array into a permutation。 I'm gonna assume for the whole lecture that there are no ties。

 Okay， you can still prove things with ties， it's just sort of uninteresting details。😊。

So any array you can think of as a permutation of one through n pi of d denotes the induced permutation of the induced distribution over them。

And again， we're thinking about the comparison model。

So we aspire toward correct sorting algorithms whose expected number of comparisons is as small as possible。

 And here the expectation is actually over the input when we say expected number of comparisons。

All right。So that's the model。That's our sorting model。 Now， we what are we sort of hoping。

 So to get results that have any meaning， what are we hoping is true。Well。

 we're hoping two things are true， so first of all。

 we know a lot about sorting even in the worst case right so sorting is not really one of those problems it exposes the problems with worst case analysis。

 we have all merge sort and log n pretty good actually right？

So for this has been an interesting question， we have to hope that there are interesting conditions under which we can do even better than N log in。

That's sort of the only interesting positive result here would be something we couldn't get in the worst case。

So hope number one。Is that sometimes。We can get little low。Of N log N。 I mentioned。

 and I'll mention this again later that if it's the uniform distribution over permutations。

 you can't beat N log N。 Okay， so it's like a fully random permutation。

 N log N is still a lower bound。 So the hope would be then that it's for some other kinds of distributions over permutations。

 You can beat N log N。 Like maybe there's not too much randomness。 It's not too close to uniform。

Okay。So for now， I'll make this precise in a second。So it can get better than analog log N。

If the Ds have。Low entropy。Okay， and I'll give you a definition of that in a second。

 it's the standard definition， all right。And in some sense， you know， it's obvious that this。

 if you know， use you know， restrictive enough definition of low entropy， Surely this is true。

 right Like imagine I told you either the array was totally sorted or totally reverse sorted。Right。

 with one comparison， you can figure out which of the two of us。 All right， more generally。

 it's easy to see that if you only have K things in your support with K comparisons。

 you can figure out which of it it is。 Actually， you can do much better than that， too。 Okay。

 but it's sort of clear that， you know， at the extreme point， if it's not very random。

 then you need much fewer than N log N comparisons to sort correct。

So that's the first open but the second hope is that you know。

The conditions are not so stringent that they preclude kind of any interesting application。All right。

So the second thing you got to hope is that real data。Maybe not all the time。

 but at least sometimes in some interesting cases， has low entropy。

So if both of those two things are true， then there's definitely sort of a meaningful。

 positive result that we might hope to prove。 Okay。

 we might hope to prove that in certain kinds of you know， real sorting data sets。 First of all。

 you know， you can be then log in。 And second of all， let's give an algorithm that does it。

 even though we don't know the distribution up front。

I want to point out there's sort of an amusing counterpoint between what I wrote here and what we've been talking about for the past four lectures。

 both in our three smooth analysis lectures and in the hashing lecture。

 totally random data was too easy。So like think about hashing， right if the data is totally random。

 you don't even need a universal hash function， like really trivial hash functions do fine。

 But we said， oh， that's unrealistic， right， let's make our lives harder by sort of not assuming that the data is fully random。

 but it can't be worse case。 So we need to assume a lower bound on the randomness in the data。

 same thing with smooth analysis。 we couldn't have a worst case input。

 so we had to assume a lower bound on the amount of randomness in the input。Ironically。

 or interestingly， with sorting fully random data is actually the hard case。

 that's like as hard as it gets。 case it's as bad as worst case。 So instead。

 we have to have an upper bound on the amount of randomness in the data to hope it have positive results。

😊，Okay。Now， I guess a quick comment and number two。 So with real data ever have low entropy。

 Well it's not always going have low entropy。 Sometimes it's just going to be it is gonna to be pretty random data。

 and you may as well use merge sort or something or quick sort， something like that。 But you know。

 dead there are applications where know when you hear about this when you get warned about sort of quick sort pivoting rules where the common case is maybe not sorted but an almost sorted array。

 know you have something sorted。 if few random things got sorted。 now you need to re sorted。

 And if sort of that kind of application， then actually if you're just having inputs that are close to sorted。

 that's going to be a small support distribution， it is going to have pretty low entropy。

 So you cant imagine stories where this is relevant okay。Though， again， it's not clear to me。

 It's not clear to me that， I think probably I don't think this is the common case， in some sense。

 but you can certainly imagine stories where that's true。Okay。So what do I mean by entropy？Well。

 I just mean the standard notion of Shannon entropy， though I'm not going to assume， you know。

 if you've seen that before， awesome， but I'm not going to assume that you've seen it before。

So suppose you have a distribution on a finite set。Let let's say the finite set is capital X。

 the distributions D。The entropy， which ought to note by H of D。Is what you do is use sum。

Over the little x's。So if I just did this sum， I'd get one， because it's a distribution。So。

 for the entropy。I additionally have these log base two of one over the probability terms。Okay。

So think of all the Ps as being， you know。Strictly between 0 and1， or if you like， I mean。

 generally what you do is if px is0， you just interpret this as zero。

 which is what it is in the limit as P goes to zero。So。If you've never seen this before。

 let's just let's get a quick feel for it， although I should say， I mean， perhaps happily。

 we're actually not going to need to work with this particular definition。 It's simple enough。

 And on the homework， I'll ask you to play with it a little bit。

 but we actually don't really need to play around much with this formula for this particular lecture。

 okay。So， but this skip some feel for it anyways。So I claim that if you have a distribution and the support size。

Is it most2 to the H。For some H， say a positive integer H。Then， the entropy。Is it most age？Okay。

So first imagine that if I told you that the distribution was uniform。

Over a support of size 2 to the H。 Okay， so I had probability 1 over2 to the H on each of these two to the H things。

Well， then after disregarding all the zeros， this would always be1 over2 to the H。

This would be log base2 of1 over2 to the H， also known as log 2 to the H， also known as H。

So the px is sum to 1， and then I have this H。So if it's uniform distribution over support of this size。

 then this is exactly H。 So on the as an exercise in the homework。

 I'll ask you to prove that's the worst case for the entropy。

 That's the biggesttro entropy can be if your support size is H is 2 to the H。 Okay。

 so the entropy is always the most H。 if your support size is and most2 to the H。

So that's one simple fact。In general， you know， the bigger the entropy， the more the randomness is。

In your in your distribution， with the uniform distribution over everything in the finite set。

 maximizing entropy over all possible distributions。All right， so。想起来。Okay。So let me， as usual。

 let's talk about the line in the sand， Right， So what's sort of the best， you know， So suppose。

 even let's just suppose we knew the distribution in advance。

 What sort of the best sorting algorithm we could possibly hope for， Like。

 when can we be N log N and by how much。I guess just to quickly connect that。

Just to quickly connect that last comment to sorting。And to our model， our sorting model。

 So like imagine each DI。So imagine each array entry could only take on one of two possible values。

Okay， so possibly a different pair of values for the different X's。

 But suppose each X I was either sort of some high number or some low number。Well。

 then there's only two to the n different arrays， which you could possibly see。RightSo the support。

 so the support of the distribution。Pive of D。Okay， is going to be at most N。

So I specified a distribution with the most two to the n possible outputs。 So the entropy is at most。

That's not to keep in mind。By contrast， so that's small。

 relatively speaking for distribution over arrays because。You know， if， on the other hand。

 you just took the uniform distribution over all possible n factorial permutations。

Then you'd get log of n factorial， which is basically N log n。

So those are some sorting specific examples。there questions？Clear so far。Okay。

So let's try to connect the entropy of distributions back to what we care about。

 which is we're trying to design sorting algorithms with the minimum possible number of expected comparisons。

And so the claim is that the best we could hope for in this model of self improving algorithms。

Is an algorithm so that no matter what。These Ds are。 Okay remember， those are unknown。

 We want the algorithm to evolve， to be optimal with respect to the D's， whatever they may be。

We want the running time。To converge， I claim。To o of n plus the entropy in the induced distribution on permutations。

So I claim this should be our holy grarail。Now。This is easy enough。

Right we have to write down the output。 Okay， so there has to be an end there， no matter what。

In a second， I will justify why we're stuck with this as a lower bound and we can't hope to beat the entropy of the permutation distribution。

 no matter how smart we are with our algorithm design。So before that me just say you know。

 there's other goals， there's other sort of second order goals you might want to optimize in addition to running time。

 but I'll sort of keep those pretty much largely under the rug as we do the development。

 so one thing you might care about is space。So in particular， you know one of these algorithms。

 you sort of expect to do some kind of learning of the distribution D so it's probably measuring certain statistics of the distribution。

 so that's where sort of space comes into play， you don't want to cheat by sort of measuring an exponential number of different things。

The second thing you might want to care about is sample complexity。

 namely the number of sort of inputs you have to see before your running time starts converging to this best possible bound。

So I'll give a report card at the end of the lecture。

 but the main thing we're just going to focus on is let's get an algorithm which converges to this running time。

Okay。So now， let me now explain why not only is n a fundamental barrier， but so is this entropy term。

So this follows， this follows by sort of a famous fact and a simple but very cool observation。

Connecting sorting algorithms to encoding schemes。So first， let me mention Shannon's theorem。

This down here。So this theorem of Shannon is what's going to allow us to pretty much totally ignore this formula。

 this whole lecture， we're basically never going to have to think about this again。

So what it says is that for all distributions。D， on whatever finite set you care about capital X。

You can equally well characterize the entropy， not just algebraically， but combinatorialily。

So this number， H of D。Is almost exactly the same， meaning up two plus one。Almost exactly the same。

As the minimum。I me write this down， and then I'll explain what I mean the minimum possible。Expected。

Over the distribution D。Enco length。Of x。Okay。So here's what I mean。 Okay， So x， know。

 maybe X is a set of 20 elements or something like this， right。There's a lot of ways you can。

 you know， encode 20 things in binary。 right， There's the obvious thing。 where it's like 0，1。

 you know，0，0， etc cetera。 But as soon as you start imposing frequencies on these different 20 elements and saying some are much more likely than others。

 all of a sudden， you get tempting to be creative with your codes， right。

 And to give the more frequent elements shorter codes， right。😊，And so that's what this says。 right。

 So it says， you've got this finite said capital X。 There's the obvious way to。

There's the obvious way to encode it。 But given a distribution D， instead。

 think about the binary encoding that makes the average encoding length。

 meaning I'll pick a random element of capital X according to capital D。

 And I'll look at the length under the code of that element of X。

 And let's minimize that expectation。 Okay' to get the expected encoding length as smallest possible。

So is it clear what I mean by that？So again， encoding is just a mapping from capital X to binary strings。

 lengthng is just the number of zeros and ones。 And the expectation is just over D。

 So among all binary codes， just make that expected length as smallest possible。

And the theorem says that the answer or the optimization problem is essentially exactly the same as this number。

Okay and this is the version of entropy we're going to be using for the lecture。Right。

How does she improve that So the proof is， it's all elementary。

 it's going to take us too far a feel to do it in lecture but I'll include some aspects of it on the homework just so that you're not too scared of it。

Okay。So we'll be using it though。Alright， so now how does this， All right。

 let me actually leave me a couple more comments。 So in particular， just again。

 so that you're not scared of this， hopefully some of you have seen Huffman codes。 So， for example。

 when I have time， I fit that into undergraduate algorithms。

 So Huffman codes already achieve the upper bound in this theorem。

I Huckman codes are good enough to get up to the get basically the entropy bound。

 And then the lower bound is some basically， you know， pretty simple combinatorial arguments okay。

And good。Good。So。Let's apply this to our sorting problem。

Because notice this is about encoding schemes。 and we don't care about know。

 our encoding scheme lectures were long ago。 we're talking about sorting algorithms。Oh。

 but actually sorting algorithms given coding schemes， if you think about it。So remember。

 we're working in the comparison model。So what can a comparison algorithm do， just for simplicity。

 let's think deterministic， but it really doesn't matter， okay。Well。

 the version thing it does makes a comparison。 maybe the know。

 third element of the array to the 12th element of the array。Whatever。And there's two possibilities。

Either the first element is less than the second one， or it's bigger than it。

And for a comparison based algorithm， you know， the only thing you can do with each of those branches is do another comparison。

So， again。Now， if this is less than it's going to pick possibly adaptively some other pair of elements。

 compare them， and on the right branch you might pick a different pair of elements and compare them。

Okay。And so。So this is what comparison based voting algorithms look like。 They look like trees。

 binary trees。And。Eventually， the algorithm has to stop。And say what the output is。

 and we're assuming the algorithm is always correct。

 So it's going to output the correct permutation that the input was。So we have leaves。

And every leaf we can label with a single permutation。

 namely the output of this sorting algorithm on that particular termination of its execution。

 and every permutation has to appear at least once。Okay。

Because each of the in factorial inputs might show up。

 and the algorithm has to correctly sort every single one of them。So in the leaves。We have。

Single permutations。I get one permutation per leaf， just the output of the algorithm。How can we。

 from a correct sorting algorithm， extract a binary encoding。

We just label the left children with zeros and the right children with ones。

You tell me a permutation， I look at a leaf。That's labeled with that permutation。

 And Ill read off the binary encoding， going back to the root。Okay。

So this ascribes to every single permutation， some binary string。Moreover。

 the number of entries in that binary string is exactly the number of comparisons that this algorithm used to figure out that this was indeed the output。

Okay， so again， root leaf paths correspond to permutations， possible inputs。

 We can view those as encodings， and the encoding length is exactly path by path。

 the number of comparisons used Okay， so no matter what the distribution is。

 the expected root path length into that distribution is exactly the same I。e。

 the expected length of the encoding is exactly the same as the expected number of comparisons used by the algorithm to figure out the correct output。

So summarizing。Induces encoding。Of all permutations。With expected length。Equal to expected。

Number of comparisons。So Shannon's theorem， what does it tell us。

 it tells us the expected encoding length of any binary code， in particular。

 one arising from a correct sorting algorithm is lower bounded by the entropy。

 so that means that the expected number of comparisons。

 is exactly the same as the expected encoding length is equally well lower bounded by the entropy of the distribution。

That's why want to go back to the best case scenario。

 Not only do we have to expect an n in the running time just for output considerations。

 but for these entropy considerations， we also have to expect the entropy of pi of D to be a barrier。

 no way we can do better。Okay。And so this fulfills a promise， I said earlier also。Which as I said。

 if the permutation is uniform at random， then you can't beat the n log n bound。

 So the interesting case is low entropy。 and you see that here。

 right So if it was uniform overall in factorial permutations。

 then the entropy would just be log of that， which is N log N。

 And we just argue that north sorting algorithm can beat that。

 Okay So that's why uniform permutation is not the interesting case。

 you may as well just use a worst case optimal sorting algorithm。All right。

 Any questions about all of that。 So this was the part of the lecture where I tell you。

 I draw the line in the sand。 I say， you know， this is what we really want。The rest of the lecture。

 I give it to you。any questions？Allright， so let's move on the algorithm。

The algorithm really is quite natural。And it's based on bucket sorts。Okay。So bucket sort。

 you may have seen， it's usually described when you have data say like that are real numbers in the interval 01。

So this is not bucket sort normally is not a comparison sorting algorithm。

 It's a classic example of a noncomp sorting algorithm， which does better than comparison sorting。

 when you know some stuff about your data， like for example， if it's uniform from the interval 01。

 How does it work in that case where you just say， oh， well， let's just have n buckets or so。

 with the if bucket basically what are you going to do We're going to do a single pass of the input array and we're gonna look at know what's the I for which this stuff is in between I over n and i plus1 over n and then we just dump it in a bucket。

 we put all of the elements in that interval in this one bucket。

 Then we go through the buckets one at a time。 We hope that each one is very sparsely populated。

 we do some simple sort in each of the buckets。 and then we just concatenate them all together。

And this this is super fast in certain contexts。 So often， for example， to put something in a bucket。

 you just look at the higher order bits。 And that'll just immediately tell you which index of some array to go to put it in。

So that's the normal bucket sort that you learn in undergraduate algorithms。

 So how do we use it here。So。First of all， what are the buckets。

 we're not assuming that the data is in the interval 01。

 we're assuming nothing about the data is's just some arbitrary comparison type model。

Even if we knew what the bucket should be， there's a question of， you know。

 how do we figure out quickly， which element goes in which bucket Now。

 we can't do something like just look at the high order of bits and index directly into some array。

 We're working in the comparison model。And in particular， let me point out that， you know。

 the obvious thing you might be thinking about， which is suppose you add n buckets。

 And then you basically want to just just to be clear。 So remember， we get a whole bunch of inputs。

 I D inputs from the same distribution。 So in general。

 what the algorithm is going to do is it's going to look at a bunch of instances。

 learn some stuff about the distribution。 Like learn what the bucket should be。

 And then it's going to try to apply that knowledge to future instances， future arrays。

 Okay So what we're going to do and with natural is to use some batch of training instances to learn what these bucket should be。

But even then there's going to be this challenge where faced with a new instance。

 how do you figure out where each of those n elements， which buckets they belong to？Now。

 the first thing you might think would be， and this is just， again， to kind of。

Help you understand the challenges we face in getting to this bound。 You might say， well， dude。

 how hard is it to just put one element in one of end buckets that are sorted。 binaryary search。Okay。

 but how long does that take？Log N binaryary search is log N。

 There's n things we got to put in buckets。 Okay， so that's N log N。

And this whole exercise is only interesting when this is better than N log N。

 So the whole point here is you want to think about H as being less than N log N。Okay， so we're。

 we might be shooting for a linear time bound here。 Right， Again， go back to that case where。

 you know， each X was drawn from one of two different options。 Okay， so we know that the permutation。

 we know that the at most two to the n permutations so that we know that the entropy is at most n。

 then we're shooting for a linear time algorithm。 because our algorithm better run in linear time。

 if it's ever the case that each X is drawn independently from only two choices。 for example。

 Okay So it's just not going to be okay to do binary search independently on these n different things。

So these are some of the， this is just foreshadow some of the issues we have to address to get this kind of result。

Okay。Good。So。You know， like I said。Your first array shows up。 You don't know anything， right。

 So you're not really hoping to beat M again for the very first array you ever see。 Okay。

 so we're just going， you know。Play a conservative， use merge short。

But also start keeping track of some statistics of what we're seeing。

 that we can hope to exploit in future instances。So， specifically。And basically。

 the goal of this training phase is to figure out what the bucket should be，So。

For the first log n inputs。Okay， so there's some constant here， like 5。 Don't worry about it。

 Okay so lambda like log。So for the first log instances。We just use merge sort， say。

To sort the array。But then also， sort of in the background， what we're going to do for these log。

 these first login arrays is we're actually going to maintain a master list of the union of all of the elements we've seen in all of these instances。

 and we're going to keep them sorted。 so we sort the first array。 We got the second array。

 We sort that， return the output。 then we also keep a copy and merge that back in with a sorted version of the first instance。

 Okay， we keep doing that。 log in times。So that log n instances each with an array of length n。

 so there's going to be n log n elements we're keeping around。So emerge all lambmbda you log in。

Sor it lists。Into one。Which is state of N log n elements。Okay。All right。

 so don't forget Shannon's theorem entropy is the same as the best。

 the minimum expected encoding length of any binary encoding。 We'll use that multiple times。O。

So why did we， Why do we have this master list， Well， we have this master list to identify buckets。

So if the buckets were going to have any property， what would you want them to have， Well。

 we want them all to kind of expect to get roughly the same number。

 right So we want stuff to be spread out as evenly as possible over the buckets that we choose。

 So we're going to do that in the obvious way。So， we just say。喂原英。So we have these n log N elements。

 N buckets feels like sort of the right number shooting for like a constant number of elements in each bucket in the future。

 So we're just going to pick every every lambeth element in this sorted list。Okay。

So we've got a bunch of stuff。 So here's the first lambda in sorted order。Second land。

In sorted order， we picked that guy， We picked that guy and so on。Okay。

So capital V has cardinality N。Alright， so there's n numbers。

 and they're sorted from smallest to largest。 And these naturally split the real line into n plus one buckets。

So this is the first resolving the first challenge， I think， like maybe the most natural way。

 You could ask， where does this log n come from， Like most log ends， you see。

 it comes from a turn off bound。 We'll talk about that。 But you know， modlo that， it's， I think。

 a very natural way to figure out what the buckets are， okay。So good。So the first level。

Says that the buckets work。 They do what we want。They spread future instances out。

Here's exactly what they do。So with high probability， and of course。

 we have to say with high probability because you might have gotten unlucky and just gotten these lambda instances that all have。

 super small elements for no good reason。But， of course。

 it's very likely that you'll get a wellsp out of elements in your first login instances。

In the sense that for all buckets eye。If you look at a fresh sample。

From the distribution over arrays。 And you look at how these fresh X1 through X Ns distribute into these n plus1 buckets。

 The expected size of each bucket is constant。I it's even better。

 the expected size squared of each bucket is constant。And we'll see in a second why that's useful。

But it's certainly stronger than just saying the size is constant。so at most 20， say。

 some reasonable constant。So that's the first。 So that's this basically says the you know。

 the plan worked， okay。That basically， if we just take log training instances。

And define bucket boundaries in the obvious way， then future instances will be distributed quite uniformly。

Now， right， and so the expectation here。So with high probability is over the lambda instances that define capital B。

 V。The expectation is over a lambda plus one instance。

 a fresh new instance and how it distributes amongst capital V。All right， so what's the point。

 So here's what's cool。So given that this is true。Okay。

 we're sort of a lot of the way there as far as defining a good self improving algorithm。 Okay。

 there's definitely one challenge we've talked about that we haven't solved yet。

 But modular1 challenge we， we're done。So we have these training phases， and that's fine。 You know。

 we're just doing N log n runtime。 And we're not really trying to do better for this first prefix of log n instances。

Then we define the set of bucket boundaries， capital V。 And with high probability， this is true。

 So what does that mean， Okay， that means， consider now a new instance that shows up。Modullo。

 the challenge of distributing X1 through X N into the correct buckets。 Okay。

 that'll be the rest of the lecture talking about how we do that。 But if we can solve that problem。

 Okay， then we can finish the algorithm in linear time。They forget about this entropy term。

 just O of N time。Why， what's the algorithm？ Okay， Well， again， So we've defined capital V。

 We're conditioning on the fact that they're good in this sense， high probability。All right。

 so now a fresh instance shows up a fresh array。 We somehow distribute X1 through X n into the buckets。

 Now we just use say insertion sort on each bucket separately， whatever， Okay。

 quadratic time sorting algorithm them， say。How long does insertion sort take on the I bucket？

Constantine， right， because the expected size squared of each bucket is over one。

So by linearity of expectation， summing up over the buckets。

 all of that sorting bucket by bucket takes only linear time。 And then， of course。

 concatenating those sorted lists together takes always linear time with probably one。Okay。

 so this is what we do。 We define the bucket boundaries in the first log n。

 We somehow distribute to be determined。 But given that。

 insert and sort in each one cancatenate and we're done。And so that's really the algorithm。

 modular of the subroutine of distributing into the buckets I haven't told you about。

So is everyone super solid on everything so far？This is kind of all of the relatively easy stuff。

And then this is one。Interesting piece。Okay， so what's the point？After。

So basically done except for buckets。Don except for bucket assignments。That's the。All right。

 there's the question to prove。So the proof here is churn off bounds。

 and it's actually a pretty nice， pretty nice application to turn off bound。

 So I'll sort of spell that out for you in bite size pieces on the homework number9。I intuitively。

 why would you sort of expect this to be true。 Well， so remember the turn off bound hat， you know。

 it gives you probability bounds of the form like E to the minus stuff。

 And then the stuff is the expectation。 It's often mu when you go and read about it。

So the reason we've taken these sort of log n instances is to make sure that that mu is logarithmic。

 right， So either to the minus log means inverse polynomial。

 The point being is log n is where you start getting really nice concentration。

 Okay for true knockdowns。 when you're just sort of counting what fraction of time something happens。

 So the fact that， you know， we have high concentration around expectation says， well。You know。

We really expect a typical instance to just look sort of exactly the same as the distribution as the union of our first log end instances。

 but just obviously sort of scaled down。 Okay， having only a one over log factor as many elements。

So you can make that precise。 It's slightly tricky。 but again， once it's broken down。

 it's pretty straightforward。So we're going take this on faith for the rest of lecture。 Okay。

 the buckets work in this sense。All right， so any questions before？We talk about how to do the。

Bucket assignments。 And again， the whole point here is we need to do better than binary search。

 right， So we need to really need to compete with that entropy lower bound。

 which in general will be smaller than en login。Okay。So。So to do。The bucket classification。

So for a while， let's develop the approach as a thought experiment。

 so this is not going to be realizable but this will help us think about what is realizable。

So I suppose we actually did know what the DIs were。Okay。

 so DI is the distribution from which XI is drawn， but I'm not going to allow you to just design some new sorting algorithm from scratch。

 I force you to use my bucket boundaries。 I force you to use my bucket sorting algorithm。

 but I do allow you to know what the Ds are。Now， of course， we don't know the D I。

 The whole point of this is we don't know the D。 So I'll remove this at the end of the lecture。

 But for a while， it's suppose we did。What would we do。

 How would we do the assignments from X's to buckets。Well。I mean， let's。

 let's think about them separately。 right， So we have。 We have V， capital V。

 We have our bucket boundaries。You know， we have our X I。 It's supposed to go to its rightful bucket。

 Okay， so there are these two bucket boundaries that bracket it that flank it。

 We have to figure out which ones they are。But we know excise is distribution。

So the sensible thing to do would just be like， well， let's just like use the optimal search tree。

So let's just literally do this sequence of comparisons。

 which minimizes the expected number of comparisons needed to figure out which bucket Xi goes in。

We know DI， what's stopping us。Okay。So。If we knew the eye， we could build。The optimal search tree。

Tian。For each exile。Okay。And again， you， because we're in the comparison model。

 there's just not that many ways， conceptually that you can figure out where Xi belongs。

 All you can do， right So all that's relevant is X's relative position to the elements of capital V to the bucket boundaries。

 That's all we care about。 We just want to find the maximum bucket boundary less than it and the smallest bucket boundary bigger than it。

 So the only thing that's useful to do is to compare Xi to the elements of capital V。

 compare Xi to the bucket boundaries。 Okay And so again。

 just like we wrote down a tree for sorting algorithms。

 we could write down a tree for when of you search trees at the root。

 you compare X to some bucket boundary。😊，It's either bigger than it or it's less than it。

 and you branch。Then you compare X I to something else to some other bucket boundary and you branch and so on。

 Again， remember， the bucket boundaries themselves are already sorted。

 but we have this sortedless capital V。 We know what's up with them， okay。

So there's only a finite number of trees in the world。

One of them minimizes the expected number of comparisons necessary to identify excise bucket。

 That's the one we should use。Okay。And in fact， things are even maybe a little less crazy than it sounds。

 Oh， yeah， so just give you some intuition。You know。

 so if this was like a perfectly balanced binary tree。

 then it's going to be something like binary search。

 right So that's sort of not the interesting case for us。 interesting case is when you can do much。

 much better than binary search。 So， for example， suppose you knew in D I。 Okay。

 so you know the bucket boundaries。 You know D I。 Maybe you know that X I is super likely to be in the 17th bucket。

😊，You know， like half the time。Well， then the very first thing you should do is you should check maybe X is both bigger than the left endpoint of bucket 17 and less than the right endpoint。

 And if it is， you're done， you stop in two comparisons。 Okay。

 so that's the kind of thing you're doing that's smart with these search trees。

 You're sort of checking for common cases with very few comparisons。All right。Now。

 not only does such a search tree exist to optimal search exist， because there's only finitely many。

 but actually， you can compute these things in polynoial time。 I don't know if you've ever seen this。

 Sometimes I teach this in undergrad algorithms as a dynamic programming exercise。

So and this is something I'll put on the homework。So if I give you DI。

T I give you the bucket boundaries， you can actually figure out the optimal search tree and again here optimal means minimum expected number of comparisons where the expectation is with respect to DI。

 you can compute that tree in cubic time。Right。对。Why' each bucket of the same size。

What what do you mean by size or has this the expected or。

I thought each we we I thought we set the buckets in such a way that。

Yeah every element of DI is has the same probability。 No， that's not what it is。 What it is。

 is that if， if you look over all n of the elements。 So from each buckets perspective。

 it's going to see roughly the same number of the n elements。 Okay。

 but it could be the bucket number one is very likely to get x 1， x 3 and or an x 5。

 whereas bucket number 2 is very likely to get x 10， x 15 and x 23。Okay， so here。

 we're thinking from the perspective of the buckets。 How many people do I see Here we've switched。

 We're thinking of the perspective from an element， which buckets am I going to wind up in。 Okay。

 So it's like two sides of a bipyy graph， if you like。So this is saying one side of。 Yeah。

 they could be completely different。 I mean， again， keep in mind， I mean， again， like in particular。

 imagine this thing where each X I takes on only two different values。

 and these can be totally different pairs of values for the different X， right。Yeah。Okay。

So there's really， I mean， so in general， so this whole search tree thing。

 we're going to do totally separately for each Xi。 The different Xs really have sort of nothing to do with each other。

So。Okay， so， in fact， you can even sharpen this。 So Canoeuth came up with a really nice trick where you can actually bring this down to n squared as well。

 Okay， But the straightforward， the relatively straightforward dynamic programming algorithm gives you an N cubed。

 okay。😊，So you， it's not crazy fast， but it's polynomial time。So， good。O。So if you knew the Ds。

 that's clearly what you'd do。 if you had enough time。

 But now there's there's sort of a non trivia question here， which is， is even this good enough。

To compete with the lower bound of n plus the entropy of the distribution of re permutations。

And even doing these searchries optimally， there's no guarantee that this is good enough。 Why not。

 Because that n plus entropy term is a lower bound on any sorting algorithm of your wildest imaginations。

 Okay， So what I've done here is I've fixed this sort of outer scaffolding。 I'm saying。

 I'm insisting that you use bucket sort。Okay， and I'm insisting that you kind of use these end bucket boundaries。

 And then only within this inner subroutine of bucket classification。

 am I allowing you to fully optimize of the distribution。

 So who's to say you haven been fundamentally lost on the number of comparisons needed by being stuck in this bucket sorting algorithmic framework。

 so the next question I want to answer what I want to prove to you is actually。

 there's no loss of generality doing bucket sorting。

 If you could have the luxury of using optimal search trees for the buckets， actually。

 you'd meet the entropy bound。And that's actually kind of maybe the most interesting part of the whole the whole lecture。

 that part。 Okay so there's still going to be the issue of sort of getting rid of this assumption that we know the these because we don't。

 But this is really the key point coming up okay。All right。So here's how we're going to freeze。

That statement that。We really lose nothing other than constant factors。

By insisting on this bucket sort approach。Okay。So at BI。

Be the distribution over buckets over exciseise bucket。Throughout this whole discussion now。

 I'm thinking of capital V。 Okay， the bucket boundaries， they're fixed。 Okay。

 so the training phase has happened。 I'm conditioning on this event that the bucket boundaries are good。

 Okay， so those are now fixed。So the randomness is only over a future instance。

So only over the randomness in Xi， in other words。So， now。Suppose we do do this optimally。

 How many comparisons do we have to make in order to assign all n of the elements。

 all of X1 through X N to their rightful buckets。Well， by Shannon's theorem。

 now we're using it in the opposite direction that we were using it before。

So before we just said that， you know， any encoding length is lower bounded by the entropy。 Now。

 we're saying， oh， given the entropy， we can actually exhibit an encoding that matches that bound。

So about Shannon's theorem。Expected number。Of comparisons。To classify Xi。It is like the entropy in B。

Okay， so remember， when I talked about Shannon's theorem。

 it was just with respect to an abstract finite set capital X。 The first time we used the theorem。

 capital X was all permutations。 That was a big set。 That was like n factorial things。 Okay。

 now we're using it again， but the set has changed。 Okay， Capital X now before we were doing sorting。

 Now， we're just doing searching for particular element X I。

 So capital X is just the n plus one different buckets。 Okay， but whatever。

 Shannon's theorem still holds no problem。😊，O。So。Then。Here's the keylemo。And this one， I will prove。

Which is that with probably one over V。 So again， we're thinking of V。

 the bucket boundaries is just totally fixed。We're going to compare on the one hand。

 the number of comparisons that we're going to need to use in this bucket sort framework。So。

 that's going to be。For each element I， the entropy of the distribution over its bucket。

 and we have to do that for each of x1 through Xn。 So this is what we pay in our algorithm if we use optimal search trees。

And we need an upper bound on this。 So we want to say that we're not losing anything by just using this bucket sorting approach。

 So we want to say is big O。And in here， we're just going to use the upper bound that's our target。

Okay。So remember， this is what we said was our line in the sand all along。 Okay。

 we were really shooting for an algorithm that at this running time。

 we argued that we couldn't do better than this running time， no matter what anyways。

So this is what we're going to pay if we have the luxury of using optimal binary search trees。

 and it is indeed and most a constant factor times what we were shooting for anyways。Vker。

I've actually sort of cheated slightly。Right here， I don't know。

Anyone noticed little sleight of hand。So the little slide of hand I did is if you go back to Shannon's theorem。

 it says， so what does it do， So it promises you can actually match the entropy bound。Well。

 so it promises you can match the entropy bound with some binary encoding scheme。Now。

 when were using the forward direction of Shannon's theorem， we noticed that， oh。

 special case of a encoding scheme。Is those induced by sorting algorithms。

 Those induced by binary search trees。 And given that we were doing a lower bound。

 that was fine for us。 right， So the entropy lower bounds。

 the expected length of any binary encoding scheme in particular。

 one arising from a correct sorting algorithm。 But here there's an issue that we're trying to do the reverse direction。

 right， So the Shannon St I wrote down only promised you some encoding scheme that meets the entropy。

 not necessarily an encoding scheme realizable by a search tree。😊，Okay。But fortunately。

 since the 70s， people have known that actually， you can even get away with using an encoding scheme induced by a search tree。

 Okay， so this is actually true。 right， And if I have the energy。

 maybe I'll put that as a problem on the homework as well。

So just want to be honest about that little sheet。So we really， the point is。

 we really can realize this up to a O of one term using optimal search trees。

 So this really does characterize the best case performance using the optimal Ts of the bucket sort approach。

All right， so any questions before I approve this to you？

And this is the proof of this is really very clever， to say。It's not that hard， but it's very clever。

G。So。And so now we're going use Shan and St in both directions。 in this proof。So what do we want。

 We want an upper bound。 We want an upper bound on this。That's the point of this。

 Well I'm never bound on this of that form。So the forward direction of Shannon's theorem says， well。

 if you just want an upper bound， just exhibit any encoding scheme。

RightSo the N B equals the best ening scheme。 So any ening scheme gives you an upper bound。

 So that's going to be our high level approach。So we'll upper bound left hand side。V suitable。

Bineinary encoding。Of everybody's buckets， okay？So。The bucket of X1， blah that back。bucket of accent。

So'm going to give you a binary encoding of all N of these things。

And the expected length of it is going to be this。All right， so what's the encoding？

So here's where I're going to。 So here's Ill now use Shannon steer in the opposite direction and say。

 well， first。Okay， so we're given x1 through X n。 Okay。

 And I have to tell you what the encoding is of these。So given x1 through XN。

 the first thing I do is I encode their relative ordering。Okay， and binary， how do I do that。

 I do that in the optimal way， whatever it is， given the distributions D1 through D N， okay。

So optimalim。In code。The relative ordering。Of the Xs， In other words。

 I encode the permutation that X 1 through X n induce。So the expected length。

Well the expectation is over the choice of x1 through xN， what's that expected length going to be？

It's something which is on the board。This。So by Shannon theem， there exists up to a plus one。

 there exists a way to encode the permutation so that on average with respect to the DI's。

 this is the length。Okay。So expected length。Entropy of the induced distribution over permutations。

Okay。So that's the first thing。All right， so again。What are we encoding。

 Okay's what's a function from， What's a function from x1 through X N to the identities of the bucket of x1 through the bucket of X n。

 So the first part of this encoding。Is just what's their relative ordering。 Okay。

 so now that I've read this part of the encoding， okay， that lets me sort X 1 through X N。

 And I have a sorted version of them without loss of generality， okay。

So how do I use this sorted version of x1 through x n。To figure out sort of in a single shot。

 what everybody's buckets are。Well， let me ask you to take 30 seconds to think about the following。

Think about， we have two sorted lists now。Okay。So we have a sorted version of x1 through xn。

And we also have the bucket boundaries， capital V。That's another sorted list， okay？

So convince yourself over the next minute that you can read off the identities of the buckets of all of X1 through XN with a simple merger。

Of these two sorted lists。 So you take the sorted version of x1 through xn。You take capital V。

 which is already sorted from low to high。You merge them。And at the end of that。

You figured out which bucket everybody's in。Are。It's just like the combined step in merge short。

 We have these two lists and you're looking at both of them and you say， whichever one is smaller。

 you copy over first，So you know if you're one of these XIs。

 you know when you reach the head of the list， maybe some bucket boundaries get copied over before you。

 but then whatever that last bucket boundary that you're compared to， you lose， okay。

 and you get copied over before that bucket boundary， that's your right endpoint。Right。

So the last bucket boundary to which you are compared in this merger is exactly the right end point of your bucket。

Okay。So how many comparisons do you use when you merge two sorted lists， both of length O of N？

Oh then， right， just for each copy， it's one comparison。So given the X's ined order。

All you need are an extra N comparisons to encode。What happens in this。Merger of these two lists。

 Ergo to encode the bucket identities of X1 through Xn。Okay。

So you first encode the relative ordering from that， you can extract the sorted ordering。

And then you're only O of N away with probably one from describing everybody's buckets。

So on code O in。To merge the sorted。Ex eyes。With capital V。Yeah。And again， just to put it together。

 right， so suppose you told me。I so there's some X1 through X n in the background。 Okay。

 and I don't know what it is。 But suppose you wrote down bits that allowed me to reconstruct a relative ordering。

 and then you wrote down some more bits that allowed me to simulate this merger of the sorted version of the X's with the bucket boundaries。

 That's all I need to know to deduce what all of these things are。 so in that sense。

 this is a valid encoding。These bits， plus these bits are enough to encode this。

For every X1 through exit。So from one plus two。Can compute， i。e。 can uniquely reconstruct。

All of the bucket of the exc。Okay。And again， the expected encoding length here is this entropy。

 the forget about expected with probably one， the encoding length here is n。 So overall。

 the expected length is n plus the entropy of the induced distribution of re permutations。And then。

 of course， the optimal encoding， which is the one that characterizes the entropy of what we're trying to encode。

 can only be better。Okay， so this is an upper bound。Okay。

I did one other sort of slidele of hand here， which is what I gave you， is I gave you an encoding。

Of the sort of joint distribution of the buckets of x1 through x N。

 whereas what I wrote here was just a sum of the marginals。

 Okay so some of the entroies of each of the marginal distributions。 But the Xise are independent。

 Okay， so sort of easier to prove in standard fact is that if you have a product distribution。

 So independent random variables， then their entroies just add。 Okay， So in fact， this is the same。

 In other words。This equals the entropy。Of B1 through BN。Because the exercises are independent。

If they weren't independent then altogether， they would have strictly less information right。

 so you would get an overestimate in general if they were not independent。

So just think about x1 and then x2 So think about a fair coin flip and then the flip of that fair coin flip。

 So each marginal would give you one bit， but actually so that would give you two bits in the sum。

 so there'd only be one bit overall in the joint distribution。

So what I really gave you was an encoding for this。 but that's good enough for this。Okay。

 by independence。So any questions about that。You're not used to these sort of information theore proofs in my local goal。

Md boggling first time around， but they're pretty cool。Questions。All right， so where do we stand。

 What we've proven is that if we actually had the luxury of knowing the Ds in advance and we had the luxury of using optimal search trees to classify people into their buckets。

 that would be good enough， which again， is not obvious okay， but that would be good enough。

So what remains is to understand how to basically simulate this argument without losing anything。

 even though we don't know the DIs upfront and therefore not in a position to compute optimal search troopss。

So unknown Ds。So here's sort of the key insight。So suppose you had one of these search trees。

knowIt's in general， in the interesting case。A very unbalanced。Okay， right。

 so balance searches are going to very boring when you're talking about sort of optimal average case things。

 right， So you're only beating the log n down if you have some stuff which is super shallow。 Okay。

 frequent stuff where you're using many fewer than log n comparisons。Now， the observation is， you。

 suppose instead I just sort of like chopped this tree off in the middle。Okay。

 supposeupp I just sort of got rid of all of the lower layerss。All。Now。

 you'd have a justified complaint， which says， well， but now it's not even like correct。 right。

 So now it happens， you do some comparisons。 And if it's sort of this， great。

 you know what bucket you're going to。 But what if you just like fall off， right。

 There's still ambiguity。 You don't know which of the buckets it belongs to。 So say， fine。

 I'll give you a safety net。I'm going to chop off the tree， and if you fall off。

 you just resort to basic binary search。Now， suppose I make this level epsilon log in。

 where epsilon' is a constant。Point1， something like that。The observation is that only。

The first epsilon login。Levels matter。This is of the optimal binary searchries TI。

 Why well suppose you chop off the bottom and resort to binary search。 What does it cost you？Well。

 now there were these cases where you would follow the tree。Okay， but if you fell off the bottom。

 you knew even in the old days you were paying at least epsilon log in comparisons。

 Now you have to do this binary search。 you're paying a log in comparisons。

 So you've got a one over epsilon blow up in your search time。 It's like if epsilon is 。1。

 you have a 10 x blow up in your search time。 So so what？

 You took these cases where you already were losing log and you're still losing log。

 Okay so you lose nothing。 So it's some kind of like space time trade off。Because notice， right。

 the old search trees in general had length had space N。 But here。

 if you only have epsilon log N levels and it's a binary search tree。

 the largest number of nodes it could have would be two to the epsilon log N also known as n to the epsilon。

 Okay So these are small trees。 But they give you kind of all of the bang for your buck。Okay。So。

I'll just kind of hand， you know， we're running low on time。 So I'm just going throw a hand wave。

How you do this， although everything I'll say， actually。

 can be made precise and a little bit of it'll show up on the homework。So again。

 it's not like we can compute this either， right， So what did we just argue。So now he said。

S I told you the DIs， I let you compute the optimal search trees， the TIs。

 but then I chopped them off， you'd still be fine。And you're like， but I don't know the Ds。

 I can't give you the D I。 Its's still not hopeful， right， But。

 but there's there's sort of a lesson you can take away from this。

 which is that only sort of end the epsilon things actually matter。

That's all you need to actually sort of match the entropy bound。

So now we're going to do something actually is kind of much more straightforward。Which is。

So what you do is you see you keep some more statistics。So for all Xi。You keep track。Again。

 this is over some more training phases。 so before we have log n training inputs now we're going to have a little bit more。

 we're going to have end to the epsilon training inputs。So keep track of。Exise， most frequent。

Puckets。Just empirically。And by frequent， I mean probability or frequency。

 at least one over end of the epsilon。Okay。So a different way of saying this。This it going to add。

Roughly end the epsilon。Times log n， extra training phases。 Okay， so before we had log n。

 we were using that to construct the capital V list， okay。So this is more， it's not crazy。

 it's end the epsilon， where Epsilon is as small as we want。F sometimes log in。 And now for each X I。

 So we have these buckets， right， We have these n buckets。

And so now what I do is I look at how many of those buckets does Xi show up in in the training phases。

 at least log n times。Okay。So there's end of the epsilon， Time log training phases。

And I'm gonna add And there's n buckets。 Okay， so in a typical bucket， it's never going to show up。O。

So sorry in a typical bucket that's going to show up。Well， some number of times。 Okay， so basically。

 what you do is you look at this many training phases and you look at which buckets it shows up in the most the most frequently。

 and then you build a search tree only on those most frequent buckets。

 And that's a simulation So you're trying to identify the end of the epsilon most frequent buckets。

 And that's meant to be a proxy for the end of the epsilon nodes that would show up in T I in the first epsilon log n levels。

 So that's the way you actually implement this。 You use this to say， oh。

 morally end the epsilon element should be enough。 But I don't want to actually compute this tree。

 So let me just do the obvious thing and see which buckets。

 you know does Xi show up in the most often。 And turns out that works。去。2 questions about that。

And this works for arbitrary distribution。So again， the exercise could be very strangely distributed。

Yeah， yeah， they're independent。 But that's all you need to assume。 Yeah， So， I mean。

 it's sort of funny。 Like so if X I is uniform over the buckets， then I mean， on the one hand。

 the algorithm is doing something very stupid because it's just like totally random。 So notice。

 I mean， the number of training phases is still far fewer than the number of buckets。

 Okay So if X I is uniform over the buckets， it's gonna be in like each of these once。

 and you're just gonna get a random sample of the buckets and you're gonna build this sort of useless search tree。

 But other hand， there is no good search tree。 If X is uniform over the buckets。 other hand。

 suppose X I actually showed up in this one bucket with 10% probability。 Okay， then you know。

 if you do this many training phases， you're gonna notice。 you're be， whoa。

 that's a bucket we need to remember for X。 Okay， so more generally。

 as long as the probability is at least one over end of the epsilon。😊。

That's when you're going to be expecting， so say in some bucket。

 the properties one over end of the epsilon or higher。

 then the expected number of times XI will go in that bucket and the training phases is login。

 which is exactly when turnoff bounds kick in。So the point is any probability of a given X in a given bucket being bounded below by one over end of the epsilon。

 that's exactly the frequencies that you're in a position to estimate accurately using turn off bounds。

 So that's what the algorithm does。 It just says， you know let's just look for any buckets if there are any where we see a lot。

 We're only going bother to build the search tree on that subset of buckets。

 morally that should behave just like the upper epsilon login levels of TI。

 And it's actually not that hard to prove that that's true。Yeah。

Some will continue the training if we realize。Imer the training phase with I guess it's kind of difficult。

 building up the trees expensive Yeah， I mean， there's different ways you could think about。

 So let me this， this is relevant to the。Final scorecard。

And this is the last thing I'm going to say for the lecture。

 but just there's been a lot of pieces and I know I've given it to you sort of one piece at a time。

 so let's just make sure we're clear where we are。So， first of all。

How many training instances do you need or how many samples do you need to learn stuff。So again。

 epsilon is just some constant， that's under our control。

 you just have to suffer a one over epsilon blow up in the search time。

So we have end of the epsilon times log n samples。We have a logithic number of samples to discover the bucket boundaries because we only need to log to have that lemma 1。

 which is the bucket boundaries do their job of spreading things equally。

 But then to get good estimates of the frequent buckets for each X。

 that's when we needed to boost this up to end of the epsilon Time of login Now。

 you get ask the question， Should I think of those as disjoint sets of samples or should I use the same samples for both。

 doesn't really matter。 I mean， for the analysis， it's simple to keep them separate。

 but it's not going to be a big deal。 I'm not thinking and actually。The implementation。

So as far as the space。Well， for building up the V list， we just needed to remember log n instances。

 So that was N log n space。 when we were constructing the bucket boundaries。 But then again。

 you know， we are in。In this implementation， keeping track of potentially a search tree on end to the epsilon buckets for each of the N elements。

 Okay， so the space is going to be。End of the one plus epsilon。

It end to the epsilon for the tree corresponding to X。So。

So there's n log in runtime for the training inputs。

Because we're just running merge short before we know what we're doing。And then。

 the really cool thing。Is there's n plus the entropy of the induced distribution on permutations。

Post。Training inputs。 So after this many inputs。Okay。

So it's en log N for a while for end of the epsilon。 And then it drops to whatever it has to be。

 There's sort of this one extra thing where it's not quite clear where to account for it。

 which is you do have to build those search trees。 Okay， so in between the training phase。

And the post training phase to transition from analog log N to n plus entropy。

 You have to build those search trees。 And that's going to be in。To the one plus three epsilon。Time。

So this is using that， so remember each search tree is on end of the epsilon elements。

 and I said that there was a cubic algorithm using dynamic programming I'll do that on homework if we wanted to use the clever canuth version we could get this down to1 plus two epsilon。

To build search streets。So this is somehow like in an interlude in between the training phase and the post training phase。

 some extra work that has to be done。And again， just to conclude， just to make sure。

You keep track of the algorithm because the algorithm is actually very simple and nice at the end of the day so you just compute the bucket boundaries in the obvious way。

 you know log instances and you take one every log of the union of all the list you've ever seen so far then for that determines the buckets for each XI for the rest of the training phases you just keep track of the frequency with which XI lands in each bucket。

 you remember the top end of the epsilon， you use that dynamic programming algorithm to compute the search tree on those end of the epsilon buckets for each of the elements and then in the steady state you just use the search trees to classify people in the buckets and search and sort on each bucket can catnate the result so that's where all these come from。

Questions。Yeah， Andy， does ever， does anyone ever do this with like self with like adjusting binary trees like a s or something by this you mean。

Could you use this play tree instead of using the Cuba algorithm to build the perfect？Tries。

 could you use a s tree or something Yeah， so that's that's let's see。 So in this context。

 it's a good question。And that would also maybe help if the distribution changes over time or something。

 right？It's a little weird here。So you're absolutely right that when I talked about。I mean。

 so there is the static optimality property of Sp trees。

 which says that it will eventually get to the point where it's as good an expectation as the best fixed tree if data happens to be coming ID from some distribution。

So that's relevant here。 It It could be the， I mean， So the the thing about this optimization。

 I'm a little unclear on it。 have to think about how it plays out。 So here， like the membership。

You're using this separate sort of estimation subroutine to figure out who even gets to go in the tree in the first place。

 and it certainly seems plausible you could somehow blend splay tree machinery with that sort of selection of who's in the Sp tree。

 but one would have to think about exactly how it works。the displays are so flexible。

 it seems very plausible。 it could be done。 It good comment it。Yeah。We not in the comparative models。

 then the goods。Basically， is a very simplified， regional place。

To get a better bucket sort or a bucket sort we don't have a prior。The distribution。So。

When you say so what do you want to assume， when you say you're not the comparison model。

 you have to say what you are assuming。 So like our elements in 01 or I mean。

 if elements are sort of arbitrarily spread out on the real line， it becomes a little less clear。

What to say。If they're in some bounded range， then what could certainly problem。Directly。

 put them index them into into the buckets。Yeah， I mean， it's not， I mean。

 if it's some very heavy tail distribution， I mean， even its not， it's not clear。 Yeah， I mean。

 I mean， once you start， I mean， classic bucket sword is meant for sort of bounded range data。

 And so I agree for bound range data， you'd sort of expect， you know， to do something better。

 learn some of the distribution。Yeah， so， I mean， this is one comment I want to make。 I mean。

 one thing that's really nice about this result is it's not explicitly learning the distribution。

 Like if you think about the distribution， the distribution is over permutations right So there's like in factorial free parameters in this distribution potentially。

 And so you need in factorial space， you need in factorial samples to really write out the distribution in the naive way。

 And you look at sort of what this thing's doing， right the space is like okay， it's super linear。

 but not by much。 the sample complexity is really good。 I mean， this is subline sample complexity。

 So I mean this is heavily using the fact that the Dis are independent。 I mean。

 so you really can't get this report card for general distributions。

 But the independent case is a huge， huge， huge win over the obvious learn the distribution approach。

 know， now if it's a bounded distribution， know， maybe there aren't many things that are relevant that you need to learn。

 but。Yeah one thing that keep in mind is know one reason we're in the comparison world is because we need lower bounds。

 So there's an analogy here with the instance Omology discussion long ago where if you want to prove you're as good as anything else。

 which is what we're doing here because we have this information theoretical lower bound and what anything could do So to prove an optta result that's so strong。

 you need to be working on a problem in a model where you can prove lower bounds so so here even though so that's one of the sort of features of the comparison model is you know you know what the yardst so you can really show nothing that's not comparison base could possibly do better。

 So I mean the lower bound is going to totally break down if you go outside the comparison model So then you have to say what are you competing with probably you're just competing with n at that point so。

Okay， do you want to say。