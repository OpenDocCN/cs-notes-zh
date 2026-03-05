# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p15 P15 15._String_matching_via_rolling_hash_(HD_1080_-_WEB_(H264_4000)) -BV1RdBTBrEdx_p15-

![](img/6bf8470ce9326b5d7366910d1b333075_0.png)

Okay。Okay。Yeah。So as I said， now that I'm recording。😡。

I started with a short discussion of midterm grades and curves and so on because this video is world accessible。

 I didn't want to include that discussion in the video if you have questions and you weren't able to attend class in person。

Please come talk to me in office hours， post a direct message on the discussion board。

 send me email or something else similar or talk to other people who were here in person okay now I'm back in person。

Um， so。I want to talk about。😡，String matching。No。嗯。

Don't worry there're not going to be any FFTs in this lecture。😡，But there will be hasing。

It'll be relatively straightforward hashing， I hope， but the。😡。

Basic string matching problem that we're going to consider。😡，Is we're given。Two strings。A pattern。

That has length M。And a text。That has LinkedIn。And the question that we want to ask is， is P substr？

Of tea。因。😊，嗯。So I want to search。The text of the United States Constitution for the word militia。

The answer will be yes， it's in there， it's in the Second Amendment。Um。

 if I want to search to the United States Constitution for the word internet， no， it's not there。

Okay， now there are variations of this problem like I'd like to know not only is it a substream。

 but where in the text is it？😡，It's in the Second Amendment or it's you know it starts at offset 1。

374。How many times does P appear is a substring of T？Re me a complete list。

Maybe some more complicated thing like certain positions are worth more than others。

 so I want the earliest substr or the latest substr in general the way that i'm going to approach this is。

The main idea。Is scan the text。电攞子。嗯。And stop when we find D。咁。

So I'm going to stop as soon as I find the first occurrence of the pattern in the text。😡，嗯。

All of these algorithms can be adjusted if I want to find the last occurrence， of course。

 I can just reverse the pattern， reverse the text。And do the index arithmetic at the end if I want to find all occurrences with small adjustments to the algorithm that you can make。

Okay。U。So。The absolute brute force way of doing this is。For all starting positions in the text。

Compare the next M positions in the text。😡，To the pattern。Okay， so。Reforce。

Is while there are M minus n possible positions in the text that are the beginning of a substring of length M。

And for each of those， I'm going to spend order M time。😡。

Actually doing the comparison between that chunk of the text and the pattern。Yes。

So the last index of the text cannot be the beginning of a substring of Li n。😡。

Because there's only one character left。So I'm discounting the few positions at the very， very end。

 where there not enough text characters to match the pattern。Oh， you're right。Sorry。😔。

Off by sign error。Yes， okay， that that's why there was a subtraction it was in the wrong order because I'm old。

Um now。In practice。This is not the algorithm that you would actually implement。😡，Because in practice。

 if I'm searching for the word militia in the United States Constitution at position one， I say。

We the people， so I go， is W equal to M， no， and I stop。😡，So I don't actually scan all M characters。

😡，At all possible positions instead I。You know， make a small optimization。

 which is the moment I find。😡，A character in the text that is not the right character for that substring doesn't match the corresponding character in the pattern。

 I immediately stop。😡，Right so I did it with a while loop， you can do it with a for loop and a break。

 you can however you want to do it is fine， but this is this is the the。The basic idea。S here。

Is the shift parameter， this is what I'm using to refer to the beginning index of the substring of Linkm。

嗯。And so all that's happening in that while loop is I'm scanning through the text and the pattern。

 looking at corresponding characters， as soon as I find a mismatch。

 I set the equal flag default false and the loop ends and then I go on to the next I。

If I manage to look at all values of M and I still have this equal flag equal to true。

 then I'll return that shift as the position of the first substr that matches the pattern if I get through everything that I don't find a match I return none so。

😡，This。Is。是。This is the algorithm that you actually want to implement if what you're looking for is English。

This is the algorithm that is actually implemented， for example， in Microsoft Word。Reasonably sure。

This is the algorithm that's actually implemented in。U。Vimmini max。Reasonably sure。

The algorithms that I'm going to describe later that have order n worst case running time。😡。

Also come with some larger constants。And the nice thing about English is most of the time when there's a mismatch。

 the mismatch happens very， very early， so in practice you're only spending one or two one。

 usually only one。😡，Occasionally to very， very rarely three iterations inside that while loop before you find a mismatch。

 and so this is really blindingly fast on the other hand。In the worst case， you have something like。

My pattern is a bunch of A's followed by a B， and my text is just a bunch of A's。Which， you know。

 means。😡，Because of the way that I'm doing the scanning at every position。

 I'm going to match M minus1 A's and then match a B against an A and fail。😡。

So this really is going to drive that worst case behavior now this seems rather silly until。😡。

You start looking at。Genetics。And you're comparing。Sequences of DNA base pairs。

Nucleotides now DNA for purposes of most algorithms is a very。

 very long string from a four character alphabet GCT and A。

That I forget what the chemical names does correspond to。

 but those are the four types of bases that one strand of DNA is made of and the corresponding。

 the opposite strand is made of T's matching A's Gs matching C's。

 except it should be read in the opposite order。嗯。The potato gene。

Has inside it a string of several thousand As。😡，So most genes look like jumbled up strings that you rolled the D4 to generate。

 but every so often you get these long strings of things that are really all repeated。😡。

So I suppose if you're not doing potato genetics， maybe this search is okay。

 but on the off chance that somebody might throw a potato into your lab，😡。

Probably this is not the algorithm that you really want to implement。系。

The other reason why this is not an algorithm that you want to implement is it's very rare that you're really matching one pattern against one text in that context。

 it's much more you've got several hundred patterns。

 each of which you're running against the same text pattern at the same time and doing that by brute force is really not going to work。

 but there are variants of the algorithms I'm going to talk about that do。😡，诶。So。This is。You know。

 Mn。Worst case。Order N in practice。Except when it isn't。

Like everything else when practice so what we'd really like is to guarantee linear time。Really。

 in theory， not just in practice。And so。These are the algorithms I want to talk about today and on Thursday。

😡，Okay。So。The first set of algorithms that I want to think of。嗯。

I'm going to assume just for purposes of discussion。嗯。Are that the？The strings are strings of digits。

This is really just for intuition， there's nothing special about this particular set of 10 characters。

 except that we're used to using them to represent numbers and I want to think a little bit about them as numbers。

😡，But if you're。Looking at strings over the standard ASCI character set。😡。

You can just think of those as the digits zero to 127。😡，If you're doing this over UTF8， zero to 256。

Except I don't really want to get into the complexities of UniIcode。This is just raw data。啊。

So I'm going to， for purposes of intuition， I'm going to think of these strings as。😡。

Deciimal numerals。Deimal strings。Um。But this intuition allows us to interpret。

The pattern and the text as numbers。Right。Why did that shut down？😔，那个。

I really hope that my battery is not going to run out here。So in particular。

 I can think of the pattern as the number i equals1 to M。Of10 to the M。

Minus I times the I digit in the pattern， so the pattern 3，1，4，5 as a string。

The five is the units digit。😡，That's why there's a 10 to the M minus I。

The three I want is the 10000th digit。And I'm going to think of comparing this to a number little T sub s。

 so this is the numerical value of the substr of length M in the text， starting at position S。

 so this is the sum from I equals 1 to M of 10 to the M minus I times the text。😡。

Apposition S plus I minus1。Yeah。Now。What I would now imagine doing is。

If I could do arithmetic for free。😡，I I'll take my pattern string and I'll turn it into a number。😡。

Now I'll take the first M digits of my text string and I'll turn it into a number and I'll compare those numbers that's one instruction right so that takes constant time。

 right？😡，And if those numbers match， that great， I found the string I'm looking for if not。😡。

Then I need to go from the substring the number T sub1 to the number T sub two。😡，So。

The idea is now I can compute。😡，The number at the T sub s plus1 from T sub S。😡。

By throwing away the most significant digit， the one on the left。😡。

Adding a new least significant digit on the right。So this is 10 times。T sub S。Minus。

10 to the M minus1。啊。T of little S。Plus T sub S plus。M。Is that right？Yes。So if I， for example。

 pre computeutd a numerical constant that meant to 10 to the M minus1。😡。

I'm doing a constant number of additions， subtractions and multiplications here。

And really multiplying by 10 ist really multiplying， it's just shifting。

 but if I think of these as really think of these as numbers。

 I've computed TS plus1 from TS with a constant number of arithmetic operations。

And so I can then compare TS plus1 to P in constant time。😡，And so I get。

An algorithm that looks like that。Now， little P and little T of whatever， those are now integers。😡。

And I'm doing integer arithmetic and integer comparisons。

 and if you happen to be in a magical model where you could do arbitrary precision arithmetic in constant time。

 this would take linear time。Specifically， the first for loop takes order M time and the second for loop takes order n minus M time and that adds up to order M。

😡，So this is order N。Arithmetic operations。So。I know somewhere there， I went off the rails。

But the ideas is。I'm taking a window onto the text。😡，And at every iteration of this algorithm。

 I'm sliding that window。😡，One step over。And rather than recomputing the numerical value inside that window from scratch at every step。

 I'm using the value inside the previous window to compute more quickly the value inside the next window。

😡，嗯。Now， there's only one problem with this algorithm and it's a fairly big one。😡。

Which is that we don't live in a world where we can actually do arbitrary precision arithmetic in constant time。

😡，Comparing these two numbers。Takes order M time because their M digits long。😡，Okay。

 so we're not really saving any time here。But nevertheless， this is important intuition。嗯。Because。

There is a type of arithmetic that we can do in constant time。Loose a little bit of information。

 it's okay。But we can make a change to this algorithm that will actually make it run in linear time。

😡，So eventually yes， we' going to get what we're actually going to do is not compute these numbers explicitly。

 but rather we're going to compute a hash function。😡，But the strings have length them。

And then update the hash functions through the sliding window。

 but I want to be explicit about my hash functions。Yeah， something to do with modular arithmetic。😡。

so what I'm going to do is just I'm going to just add。😡，Moud Q everywhere。

And I'm going to say pick a。Prime number Q。It turns out that2 to the 31 minus1 is a prime number。

 so that's a reasonably good choice for Q。😡，嗯。So I just stick Mu queue everywhere now I have to be a little bit careful here。

😡，Because。If that subtraction yields whenever I see mods next to subtractions。

 I have to remember that every programming language implements modD incorrectly。😡。

Whatever mod Q is always。😡，At least zero and less thanq。😡，as long as Q is positive。

The problem is if I take a negative number mod cu， the answer should still be positive。

 but it never is。😡，C is broken， JavaScript is broken， JavaScript is broken， Python is broken。

 everything is broken when you're doing module arimetic because it doesn't do mod for negative numbers correctly。

 I'm going to do it correctly。😡，Sorry。我有。If you know that your number between zero and negative  Q。

 adding one copy of Q is enough。😡，If you don't， you just have to implement。😡。

Or hope that the Python Math Library has already implemented modD correctly。

This is really annoying when you're implementing asteroids and the asteroid goes off the left side of the screen。

😡，Yeah。可。Yeah， I mean， well。😡，What you really want to do is negate it。😡，Compe mod。

 Negate the result and add add Q， right， so。It's easy to implement in constant time。Really， really。

 really annoying that every programming language does it wrong。Excel does it wrong。

Basic did it wrong。嗯。Now suddenly， if I add this mod cu。😡，Now I really do have。

Linear time provided Q is the Q is small enough to fit in a single machine word。😡。

So I can do arithmetic mod cu in constant time， but now there's a problem。

With this modified algorithm。😡，Yeah， it doesn't actually work。😡，The problem is that this comparison。

😡，Here is really only doing a comparison mod queue。😡。

Because those values are always forced to be between zero and1。

 and if it just so happens that those two numbers are different， but they differ by a multiple ofq。😡。

Then your algorithm is going to be incorrect， it's going to return a match when there isn't one。

 so to fix that。😡，I'm actually going to compare the strings。Explicitly in here。

And if the strings match at that point。😡，Then I'll say yes， there was math。😡，Okay。

 so I'm using the numbers mod Q as a filter。😡，If the， the。The numerical value mod Q of the pattern。

And the numerical value mod Q of a chunk of the text are different。

 then they are different as strings。😡，so it's a quick and dirty， let's just sanitity check， ohdo。

 they're obviously different。😡，Um。If those hash values or summary values are the same， though。

 that could be a true match or it could just be a coincidence。😡，都佢个办。对对我就是。Right。

 if the numbers collide， then we will do a brute force comparison of the strings。都で次一现在。

That's exactly right so the idea is we will try to engineer continue modifying this algorithm so that we can guarantee that the probability。

Of a false match。Is。Amost one over M。then now with this brute force comparison。With mod， Q and。嗯。

Root force check。The running time。Is。N plus F times M。Where F is the number of false。Matches。

So if the probability of a false match is1 over M。😡，This F will turn out to be n over M most。😡。

And that will cancel out the M factor。And I'll end up with just order in。ok。So。Yeah。Okay。

 if we can just somehow guarantee that the number of false matches。Is。Sorry。

 that should be N M again， sorry。Don't want the number of false matches to be less than a number that's less than one can't guarantee that we really want the number of false matches to be this less than this fraction。

So if the text is a million characters long and the pattern is a thousand characters long。

 we'd really like there to be at most 1 thousand。False matches and then if we spend a thousand steps on each of those checking the false matches。

 the total time that we spend inside that sanity check is also bounded by a million now。😡。

The way that we do this， unfortunately。😡，If you know Q in advance。😡。

Then an all powerful malicious adversary can write the Constitution to his country in a way。

That will guarantee many， many more collisions。😡，Just transcribe into the Constitution。

 this is our national anthem right。嗯。And then search for militia， which just happens to have。

The same hash value as。AAA AB。But what we can get。Is that the expected number is at most N over M。By。

Playing with the parameters。Of how we do this numerical summary。

Similar to the way we've done hashing in the past。Okay。

 so I'm not simply going to choose one way to take this numerical value and hash it down to a small integer。

 I'm going to choose at random one of several ways of summarizing this numerical value in a way that will guarantee that in fact。

 the probability of any false match。😡，For any two substrs that are different。

 it's going to be at most one of M， I suppose。To be completely honest。

I should write this in big notation。Plague with the constants。

 you can make sure that the big O is than the big O constant less than one。

 but I'm only going to show this。Okay， so。This strategy was first described。I mean。

 text searching has been around for as long as there's been text。😡，UmYou know。

 probably going back to the 1890s with machine computation。

But this particular idea of like doing module arithmetic is pretty。Pretty old。Oh。

I do want to point out actually before we talk about the specific ways that we guarantee this。

 one of the other sources of inspiration of this idea。

 so you'll notice now I really am computing that number little T sub s plus1 from little T sub S in Constantine。

I'm pulling off the high order digit mod queuee gluing on a new low order digit mod queue。😡。

But it really is constant time and the。😡，The origins of this idea。Date back to the early 1960s。

 I believe。A guy named Zubbraist。So。Zubbraris was one of the first people to write a program that played chess。

Early 1960s， it wasn't very good。But it was phenomenally better than anything that anybody had implemented before because。

Nobody had implemented anything before。Um， but in particular。

 one one thing that Zebras wanted to do is he wanted to memorize。😡，Ches positions that he'd seen。

So the way that you write basically any game program at all is you say okay。

 here's my current position， there are a bunch of moves that。😡。

Say white can make next and then from each of those there are a bunch of moves that black can make next and you build this big game tree。

😡，Similar to the and or tree that you saw in the homework with death。Um，And so you at some level。

 you go down far enough and you go。😡，I don't want to search anymore because the entire chess game tree is way too big。

 so I'll search down maybe I don't know， four or five levels。

 and then I'll use some heuristic to assign a score to this position。

 maybe based on which pieces I have versus which pieces my opponent has so they're heuristic things like my queen is worth nine points。

 a rook is worth five points， a Bishop is worth three points and so forth。

And then essentially at every even level you try to maximize score and at every odd level you try to minimize score。

 mirroring， I'm trying to win and my opponent is trying to make me lose。😡。

And so you get this big game tree。But when you're doing this over and over again。

 you want to remember positions that you've seen before because there might be more than one sequence of moves that leads to the same position or a position that you thought about three moves ago might actually be happening now。

😡，And so you need a way of storing chest positions in a way that you can look them up。

So what Zebras did is he had a hash value。4。Every。Et。Square。Hair。

So black Rok at a5 would be assigned some 16 bit integer。😡。

White bishop at F7 would be assigned some 16 bit integer。

And then the hash value for the entire board was just the bitwise exclusive ore of all of the hash positions of the pieces。

😡，Okay， so as value。For the board。Is the exclusive or of。Ash of each piece。And what this meant was。

When you want to change a position by moving a piece。

You exclusive or by the old position of the peace。And then you exclusive order by the new position of the piece。

Rather than having to run through all 32 pieces on the board。😡，Remember， this is the 1960s。

 32 is not a small constant。😡，Right， maybe， you know， there are a couple of like when you castle。

 you might have to do four exclusive wars， but that's pretty rare。When you take a piece。

 you'll have to do three。嗯。But this means that I could update。😡，Hah。Board。For one move。With。

Two to four exclusive awards。So the idea is essentially it's not like a sliding window anymore。

 it's like a sliding view onto ches space， but you move through chestes space one piece at a time and so you optimize the computation of hashing so that you only pay for the changes。

😡，Not for recomputing the whole hash value itself。So this is sort of background to what Rayn and Carp did with this idea of a sliding window with a numerical value in the early 1970s。

😡，系。So。嗯。How would you make that random？Let's see if we can。

Pretends to be ravin and carp now I'll try to intimidate you first。Rbin has a Tring Award。

Carp has a different Turing award。They were students， I think when they came up with this。

 this was before either of them when they're turning words， but still。

 I think you might be able to come up with it。It change Q， how？Perfect， you got it in one。So。

This is what Carpen Ravine said。Instead of choosing Q deterministically。

 which the adversary can then predict， I'm going to choose Q randomly。😡。

So literally let Q be a random prime number between two and some value that I'm going to just write here capital M for this value for now。

😡，But there's some function of the pattern length that you need to use for this to work。😡，Um。

 and to be efficient， but the rest of the algorithm is exactly the same as what I wrote earlier。😡。

No difference at all。ok。So。嗯。The question is how do how now do I know that the expected number of collisions is small Well there is this lovely。

Observation。Which I will。Make seem really important and really subtle and deep by calling it alemma。

嗯。Every integer。X。Ass。At most， ceiling of log X。Prime factors。What's the proof。Oh no， no， no。

 you're working way too hard。Right， log X is that's the number of bits in x。😡。

So what does that have to do with prime numbers？Yeah。Every prime number is greater than equal to two。

😡，Okay， so。Prime greater than or equal to2 QED。Okay， so if I had more prime factors than that。

 each of those prime factors is bigger than two， then the number would be too big。😡，Okay。

 so what is this what does this mean Well， what's you know， think about this。

 what's the probability that my summary of the。嗯。The pattern， this is my hash value for the pattern。

 the little twiddle。😡，嗯。Let's see。The probability that those two things are equal， well。

 this is the probability that my randomly chosen prime number。

Evenly divides the absolute difference between。These two numbers now those don't have twiddles on them。

 those are the unabbbreviated numerical values that I considered earlier。So。

If Q divides this difference， then in particular， the remainder of P mod Q is the same as the remainder of T sub S mod Q。

😡，Okay。This number is at most 10 to the M。So that means it has at most order M prime factors。嗯。

And I chose my prime number Q from a set of size capital M well。It means this is going to be at most。

😡，Little M over the number of prime numbers smaller than M。😡，Okay， so this。Is the number of primes。

Less than or equal to capital M， this is this capital M that I put up there。

So as long as I choose capital M so that that number of primes is at least m little M squared。😡。

Then I have enough。So now I'm going to use。The very， very weak form of the prime number theorem。Um。

The number of primes less than any upper bound capital M is this is in fact。

 analysis is actually tight。😡，It's about that number over the number of digits in that number。😡。

I'm not going to prove this。😡，You can just look it up in your favorite Wikipedia。嗯。But。

knowDistribut to prime numbers have been studied since at least since Gaus invented them in the 1800s。

😡，sorryrry。啊。Then we actually know quite accurately what that number is。😡。

But this is enough to actually be able to prove something。Right so if we choose。

Capital M to be bigger than little M squared log M。

Then the probability that P twiddle equals Ts twiddle when the two numbers are different is at most M over。

Sa do them。Squared， which is big O of one over。So if I just choose my prime from a large enough range。

I'm guaranteed that the probability of a false match is going to be1 over M。Um，This of course is。

Okay。😊，All right。So we've got a pretty good strategy here。

 all we need to be able to do is implement the first line。😡，嗯。啊。That's not easy。Yeah。嗯。

It's still not easy know import yeah crypto people have done this。

 but what crypto people actually do when they want large primes is first of all。

 I literally am assuming that I'm generating this prime uniformly at random from the set of primes in this particular range that's not what crypto wants that crypto just wants a big enough prime。

😡，The other thing is， though that crypto doesn't actually look for primes because primity testing is too expensive。

 what they use is a randomized primality testing algorithm。😡，Due to Miller and Ran。

That when the number is。嗯。Let's see。I always get this wrong， so I want to be careful。嗯。

When the number is。Prime， it says， eh， I don't know。

When youWhen the number is composite half the time， it says it's composite and half the time it says。

 I don't know。So you run this test on your number 100 times。😡，And if it says100 times。

 it's probably pride。嗯嗯。😊，This is what's in making your bank transactions secure。😡，Now admittedly。

 I'm actually quite happy to trust something that is as secure as flipping a fair coin 100 times and getting 100 heads。

It's more likely that the bank is going to be blown up that that particular theorem is going to be proved false。

 but formally as a mathematician， they're not really primes。

That's probably good enough for this algorithm。😡，Right because you get too many collisions， hey。

 you've discovered it wasn't a prime， you've done something that the Millerer Arabian test couldn't。

That's pretty cool， you've probably just disproved the Riman hypothesis or something。

But you know formally we can't guarantee that and and even then you're doing like rejection testing on a bunch of things you have to do a linear number of or you know。

 about a logarithmic number of iterations before you actually hit a prime number。

 now it's starting to get slow again。😡，So。啱。It can do something else。

So I'm going to refer back to the discussion about hashing。嗯。

Were any questions about this before I go on yeah？It is scientific randomly。

 and that makes a harder of。As long as they're able to ensure that the adversary doesn't know what we're doing。

 it doesn't need to be a uniformly children among it just it needs to be close enough to uniform that the analysis works。

Otherwise。The analysis doesn't work。So this probability here。

 that fraction little M over pi the big M， that's assuming uniform randomness。😡。

Over the set of prime numbers， there are little M primes that are bad out of the choice of this many primes。

Now， if you choose something that's close to uniform。

 maybe I can replace that with a big O and everything is okay。

 but you can't just pick up prime number in a way that is hard to predict。😡。

I you do have to guarantee something about that distribution in order to get the performance guarantees that you want。

In practice。Two to the 32 minus1 works just fine， except of course， when it doesn't。

So we've used we've seen another place where。In passing。Where prime numbers were used to do hashing。

So specifically， there was this family of this universal family of hash functions。

Called the multily ad family where you take。To。Prameterters A and B， and hash your input X。😡。

By defining this to be Ax plus B。Maud。He。Moud M。Right， so。This hash function。

 if I choose the parameters A and B， uniformly random from the numbers between1 and p minus1。😡。

This is guaranteed to be universal， meaning the hash value of any two distinct items in my universe。

😡，Are equal with probability at most1 over M。😡，This sounds pretty close to what we want。😡。

The problem here is that。😡，嗯。In the string setting。😡，I want to hash a long sequence of things。

And I seem to only have one parameter cu that I can play with。😡，Here。

I've got two things on ones that I fix in advance and one thing that I'm feeding in as my input's not quite right。

嗯。Now there's a more。Interesting version of this that generates not just。Universal。

 but k uniform for arbitrary values of k， meaning every tuple of k hash values for any K distinct items is equally likely。

😡，And this is。To make a。Holynomial。Of degree， he。This is a little bit closer to what we want。😡。

Here that a down here is actually a vector， so maybe to make it a little clear what's going on。

 I'll just imagine that's an array A。Um。So the way to get higher independence according to Carter and Wedman was。

Let's choose at random a larger sequence of numbers。😡。

And then compute the dot product of that longer vector with the vector of successive powers of x。

1 x x squared x cubed up to x to the k minus1， and then do the modular hypinic to make it all fit in memory。

😡，This isn't still isn't quite what we want because in this particular game。😡。

The long sequence of things is something I choose at the beginning of time。😡。

And the x value is something that I feed in as input。😡，To my process。What I would like。

Is to be able to choose some single parameter。😡，In advance。And then feed in the entire string。

As my input， so instead of fix lots of things in advance and vary one thing。

 I want to fix one thing in advance and vary lots of different things。😡，So in particular。

 what I'd kind of like to do is sort of reverse these two values。

Right I really want to think of this as H sub little x of capital A。And well。

 let's name these things the way they really ought to be named the hash value of the with respect。😡。

To some now the salt parameter will be the value that I'm plugging in in advance。

 I'll refer to that as B for reasons that'll be clear shortly。😡，嗯。

And the array of values that I'm going to plug in is now I'm just going to call it P for P。😡，Pattern。

And this is going to be the sum from I equals zero。To well， in this case， the pattern has length M。

Of。B to the I times P of。i。And then I only want to do one mod。So B here stands for base。

What the way that you should interpret this expression is。😡，Think of the pattern as a number。

Written in base B。And I suppose to be consistent with the index arithmetic we've been doing earlier。

 I should reverse， you know， so the rightmost digit is the least significant one。Okay。

 so interpret the pattern。嗯。Interpret。Pattern。As a number。More in。In base B。The car wedman。

Analysis why the probability of occ is small。嗯。Is based on the fact that I've got these two kinds of parameters at the very beginning。

 either AB on one side and X on the other。😡，And basically is arguing that for。Different values of x。

 there are only a small possible values of A and B that can lead to a coincidence。

I essentially want to do the same thing here for different patterns， P。

 I'm going to argue that there are only small number of bases B that lead to a coincidence that lead to a collision。

😡，And so this is going to me my random salt。And this is now going to be fixed。

So I'm not going to choose my prime modulus uniformly at random。

 I'm just going to bake it into the code。😡，Choose a lawn that's big enough。

We'll have to figure out what that means， but it's just baked into the code。

But what I am going to choose randomly is the base of this numerical representation prior previously。

 I was assuming it was always 10。😡，Now I'm going to choose it randomly between。😡，Zero N Q minus1。

 actually， I'm probably never going to choose zero。So that would be， that would be rather silly。

The analysis is going to work out even if I allow the possibility of choosing zero。Really。

 you don't want to choose zero。Yay， all my hash values are zero。

 I'm back to doing brute force all the time。Okay， and so now my pseudocode looks like this。

Almost identical to the code that we saw earlier， except now Q is just an arbitrary prim。

 it's not random at all， you can bake it into the code compile time。

 except all of the1s are now replaced with these random number。😡，B for base。Um。And so why does this？

Work。Well。He is crime。Then。Division mod， you。Works。

The right way to say this for those of you who are mathematicians。Is。If you look at the numbers。

 mod Q。😡，You can do addition modD Q， you can do subtraction mod Q， you can do multiplication mod Q。

 and because cause Q is prime， every number mod Q except zero has a unique well definedfin multiplicative inverse。

 which means you can do division mod Q。😡，诶。Now， one of the consequences of that。Is any polynomial？Of。

Degree。M minus1 has at most M minus1 roots。This is known as the fundamental theorem of algebra。

Except it's all done in module or arithmetics， so you don't get to do any of the interesting topology that you get to for the real fundamental theor of algebra。

Again， I'm not going to prove this to you。I'm going to ask you to consult your favorite Wikipedia。Um。

 it's not terribly hard to prove， but fortunately， we don't have to gusted it for us。

So why do I care about this Well， again， what I'm interested in is the probability that my guess。😡。

My hash value for P is equal to my hash value for this substr of the text when the pattern in the text don't actually match。

Well， this is going to be equal to the probability that。Well， this polynomial that I've chosen。嗯。

Minus。This other polynomial that I get for B is equal to zero。

This is now no longer a numerical value， a single numerical value for the pattern。😡。

This is now a function where you feed in the base and it gives you back the numerical value if I interpret this mod B。

😡，Or in base B。系。Um。This is a polynomial。Of degree m minus1。

So there are most M minus1 values of b that make that equation true。😡。

So this is at most M minus1 again， where I chose。😡，You。

Cap M being now the minimum size of my prime number。So if I choose capital M to be little M squared。

😡，Then my col probability comes out to be1 overM。Okay。

 so let's ignore all of the number theory for a moment and just think about what this means。

I implement my algorithm。😡，Interpreting。The text and the pattern is numbers。

In order to make the arithmetic fast， I do all of that arithmetic modulo sub primeme number。😡。

Generally， if I'm doing modular ortic， I'm a little bit more comfortable if the modulu is prime。😡。

but now I need to and that that adds the possibility of a false match。

 so I need to add in the brute force check if the numerical values happen to collide。😡。

But then I need a way of doing something random so that the probability of a false collision is small。

 so what I do is first I make sure that my prime modulus is large enough。😡。

Just needs to be bigger than the square of the length of the pattern。😡。

And then I choose the base of my numerical representation that I'm manipulating randomly within the range of that prime number。

😡，So ultimately， all it means is I've taken that hard coded 10 out of my code。

 replaced it with a Q sided die。😡，Hope that it's not zero。Or one。

 probably what you really want to do is is not。Random of q minus1。

 probably  Q plus random of  Q minus1 or something you shift away from the small values in practice。

Because you want to avoid trivial things like this is a number base one that's not really going to be very useful。

😡，嗯。😊，That happens with low probabil， so the averages still work out。

 but in practice you don't want to do it。That this would be much easier to implement finding one prime number that's reasonably large。

😡，You can look that up at prime numbersumbers。com。There there must be a prime numbersers。com。

There's a random。org。Where you can download terabytes of random bits。You might have to pay for them。

 but there's probably a web page out there somewhere where can give you an absolute guaranteed of。

10000 digit prime number。And that's it， this is how you do tech searching with guaranteed expected linear time because you have a guaranteed expected small fraction of false matches。

Next time we'll see how to do this without randomness。We won't be doing hashing anymore。

 we'll be doing dynamic programming。😡，And this will be。The second， the search algorithm itself。😡。

I think it justifiably owns the title， second most Con seven Lines of code in existence。😡。

The first most confusing of seven lines of code in existence is the preprocessing algorithm that we use first。

So we'll see both of those on Thursday。U thanks。Hopefully I'll see some of you in office hours。对。



![](img/6bf8470ce9326b5d7366910d1b333075_2.png)

好找紧时间。