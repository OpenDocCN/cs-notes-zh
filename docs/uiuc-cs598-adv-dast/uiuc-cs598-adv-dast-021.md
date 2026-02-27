# 021： Fast integer sorting — Range reduction, signature sort.zh_en -BV1kWFGzsEmN_p21-

![](img/d1a8469b380bbad0695f66c3f514b201_0.png)

All right， so administrative you first。Apparently a couple of you have reported some issues with the registration form for project teams if you don't see your name on the schedule that means that the。

啊。TheThe submission didn't take if you successfully submitted， you should have gotten an email back。

With a link to update your submission。Use that to update it again or send me email。

With the information or something， if you didn't get that email， that probably means that the。

 the wfi was acting up when you hit the submit button or something else that for some reason。

 the submission didn't go in。 So especially if you have。

Time conflicts during the last week of classes and into dead week。

Please make sure that you fill those out so I can get you into the schedule next Thursday。

So right now， tentatively we have talks scheduled for next Thursday and the following Tuesday。

 there's still one open slot on Thursday， but there are at least two teams who said they tried to submit and failed。

 so that means we will be spilling over into dead week。嗯。Soon that people can get。

Their information in the sooner we can get everything scheduled。I also want to point out。That。

So talks。May 16，8。啊。Hes re register。

![](img/d1a8469b380bbad0695f66c3f514b201_2.png)

Yeah。

![](img/d1a8469b380bbad0695f66c3f514b201_4.png)

Your team if you if you don't see it on the existing schedule。



![](img/d1a8469b380bbad0695f66c3f514b201_6.png)

Yeah， okay。

![](img/d1a8469b380bbad0695f66c3f514b201_8.png)

Um。Reports。Oh。嗯。I have to do this little dance to stay in。You know， to follow university rules。

 the student code says that nothing can be due， no written work can be due after the last day of classes。

 probably you could make an argument that oh this is in place of a final exam so it could be due on the day of the final exam。

 I'm just going to say you've got a one week extension from the official due date because there're realistically there's very little chance that I'll be able to to look at anything until the 15th anyway。

So even though it says the seventh on the schedule page。The de facto due date is the 15th。Or。Yeah。

 roughly the 15th。嗯。If you do get it in later。At some point around May 20th。

 I'm going to need to submit grades。If you get in later， I can update those grades。

 but a little longer that you go。Dist stcer it gets the harder it is for everybody to stay。

On top of things， so please don't wait too much longer。If you were an undergrad。

 I cannot give you a DFR or an incomplete。So please submit something。嗯。All right。So。嗯。

The last couple of lectures we've been talking about data structures for sets of integers and specifically order dictionaries。

 so I want to be able to store a bunch of items， do predecessor and successor searches。

 and then if possible do insertions and deletions。And we saw several different ways of doing this。

What I want to talk about today is。What doesn't sound like a data structure topic。

 but it actually is is integer sorting。So。呃。So again， as usual， I'm going to assume that I have。

And an integer keys。Each with W bits。Where of course， W needs to be at least log based to of N。

 but it could be significantly larger。And I'm assuming that I'm working on a machine that can do W bit arithmetic or boolean operations in constant time。

Okay， so。I'm given a W bit。Word rim。So the sort of obvious stuff。哦。Runs in。

Just treating items as atomic objects and comparing them， this gives you N log N。

For exactly the same reason that in fact， there's really the same algorithm using an ordered dictionary where you're just based on comparisons。

 you can use a balanced binary search tree and each insertion deletion or query will take you log in time and in the case where you don't assume。

Underlying bit representations that log in is the best you could hunt for on the other hand。嗯。

There's。Re sort。That runs in time n times W。This is， I guess I should call this binary ra sortt。

And there's a couple of different ways to phrase this， but the simplest is， let's see。

 starting at the least significant bit。perermute so that all of the things with least significant bit zero are on the left and in least significant but one are on the right。

Then for the second least significant bit， do that again。

 but keep things in the order that they already were。And after making W passes through your array。

 everything is going to be completely sorted。If you want to be a little bit。

Do things a little bit more interestingly。You can do instead of base2 Radic sort。

 you could do base n Radic sort。And then instead of。Using W passes through this。

 you could do something like。W over log N passes。And in this case。U。Basically。

 you build an array with N buckets。You divide your W bit strings into loginbit chunks and again starting at the least significant chunk。

You insert the items into the corresponding bucket based on the value of the chunk。

 making sure to keep them in the right order， like in a chained hash table。

 and then you reabsorb that all into a permed array， you do that again W over log n times。

And so in particular。If W is。All we will again。So if W is theta of log n。

 because we know it's at least log n， but if it's at most。啊。The constant times log N。

 this is already。L your time。Okay， so if you're in the simplest situation where a word ra might make sense。

嗯。诶。If you're sorting。32 bit integers on a machine with a 32 bit word。And you've got， I don't know。

 you a few million of them。This is， you know， do。Either n area or square root of n area or cube root of n area。

 it just changes the constants in the running time。That's already going to be pretty fast。Um so。What。

What I want to show you first。Is an algorithm by。嗯。Kirrkpat and Reich。From the7s。

 I don't remember exactly the exact date。But this algorithm runs in time。And。Mg。W over log n。

Now this， you know， we already got linear time provided the word length is a constant times log n。

But。Here what you get if W is。Logged to the constant end。This will give you n log， log N time。

Whereas the other thing， just standard rate sort will already be slower than doing comparisons。

so we're in a somewhat artificial land now where the word size is actually considerably larger than login。

 but because otherwise there's nothing to prove。And the basic idea here behind the Kiroppatric rice algorithm。

Is something called。Range reduction。Okay， so if I let T of n comma B， this is the time。To sort。

And be bit。Kese。What the。Kirk Patrick Gr algorithm is based on。Is a recurrence？

That replaces each of the。B bit keys。With an equivalent number of B over two bit keys。

So in each in which I can then recursively sort。And then the base case。嗯。Is B is log n。

 then I revert back to Ra sort。Okay so the idea is I've got these， you know。嗯。

Huge keys that I want to sort on a potentially even huge word model， but by doing a linear time pass。

 I can reduce to the case of sorting words that have half as many bits each。

This doesn't use any like word packing stuff， there's no parallel computation comparison going on here。

 it's really just carefully manipulating the integers。嗯。

So I'm going to keep this first page share for summary stuff。And talk about。

The Kiurt Patrick Reich algorithm。Um。So questions about what the very high level idea， yeah。对。Okay。

 so there are two ways that one can do writing sort。You can either do most significant bit first。

And then within all the things that have most significant zero。

 you sort the lower order bits and then again with the ones。

The other way to do it is if you sort by least significant bit first。

Then when most significant bits agree。The zeros will still be further to the left than the ones。

So you'll still end up if you recursively sort in a stable way the higher order bits。

You've already put the lower order bits in the right order。

 so everything will come out sorted in the end。Um， okay。So。Again， we want to。Sort and。Bebit keys。嗯。

The idea here。Is I'm going to do something that I've done many times before in this context。

 I'm going to take my BB keys and I'm going to split each of them into two B over two bit chunks。so。

Split。Each key into。2。😔，Be over to bit。Chunks。And I'm going to build。A try。Over the chunks。

 so the idea here， here's my root， I'm going to have a child for each left for each distinct left chunk。

And then each of these nodes will have a child for each distinct right chunk that has that left chunk。

so the try has depth two。Right。These are distinct。Left chunks。

That level one and the leaves correspond to each of the original keys but。

The edges in particular are labeled by the edges leaving the root are labeled by left chunks and edges leaving the children of the root are labeled by right chunks。

嗯。Now。I can build this try。In linear time using a linear amount of space。

 but only if I slightly cheat。The issue is basically。In principle。

The root of this try has degree2 to the B over2 that's the number of distinct chunks that I can have and so what the way I could build this try in linear time is I insert。

Each of the keys one at a time in whatever order I'm given。I look at the leftmost chunk。

If there's already a child pointer corresponding to the leftmost chunk。

 I just follow it otherwise I create a new child pointer。And then again in the child。

 if there's already a child pointer for the secondary， for the low order chunk。

 I follow it and just say， oh it' another copy of this， but in general。

 if I assume everything is distinct， I'm just going to create a new leaf。The problem is。

To get this to run in only linear you're time， I need。To detect。啊。Duplicate。Left chunks。And well。

You got it in one， if I really want to do this in a space efficient way， I need to use hashing。

So the data structure that I'm actually going to use at each node。It's just a standard dynamic array。

Of the unique left chunks， but off to the side， there'll be a hash table that tells me whether I've seen each of those left chunks before。

嗯。So hash table plus a standard dynamic array。嗯。So this， of course， means。

That the running times I get are the algorithm I get is randomized， the running time。

 the order and running time is actually only with high probability。What？

Kirkpat and Reich actually did。Is or。Give up on space。Use a bitmap。And dynamic array。Then I get。

 so the bitmap just has a one if I've seen that it's of length two to that be over two。

 I have a one if I've seen that chunk before， it has a zero if I haven't。

There's a magic trick that says。I don't， you know， to make this work。

It looks like I need to allocate the bitmap and clear it all to zeros。

But there's actually a magic trick that says when you dynamically allocate an array。

 if you're willing to tolerate some constant overhead， you can do sort of lazily。😊。

You could do a lazy initialization， so you don't actually initialize something to zero until you look at it。

And so the initialization just takes constant time。

Or the allocation takes constant time and you only initialize things that you actually read or write to。

And so， you don't need to pay。For that space in time。So this means that I'm using。

Two to the the over to space。And I'm still using this much time。In the worst case。Right。

It's a cute trick， but I'm already getting too down in the weeds so。啊。啊。

Maybe I'll talk about it on Tuesday if I can't figure out what else to do。Okay。

 so this is the hard part。Is I built this two level try over the chunks。Now the second part。

And this is really only so that the second part is really only so I don't have to worry about blowing up the number of things that I need to sort。

I'm going to find the minimum child。Of each node。Bye。Grote force。So this is， you know。Linar time。So。

The reason that I want to do this is。For all of the nodes in the try that are not the smallest child of their parent。

Turns out that there are exactly。N plus。1。No， there are exactly in such notes。

So there are exactly N such nodes that are not the minimum child of their parent。

Is anything that has a parent？Or anything that is a parent has a leftmost child。

And so the number of things that I pulled out here is equal to the number of nodes that are parents。

 the only nodes that aren't parents at the leaves， and they're exactly none of them。

Okay so then the third case。Is now I recursively。Sort。The N remaining。Nodes。

This takes T of n be over two time。And then finally， I need to。哦。Permute。The children。Of each node。

To。Match the。Sored order。And then finally， I do it in order to pursue。Okay。

 now there's a slight trip to doing the permutation。Which is if I literally just。Um。Only sort the。

Chunks themselves and that is the only data that I pass to the sorting algorithm then I get this list of this sorted list of be over2 bit keys。

How do I go from that to reorganizing the children at each node， so when I look at a key。

 how do I figure out which node it belongs to and the answer is that when I'm doing the recursive sorting。

I am actually using those at B over2 bit keys and sorting by them。

 but I'm carrying along this auxiliary data that tells me which node was that keys that chunks parent。

 right， So I'm actually sorting。Chunk。诶。You know， parent ID。Pairs。By chunk。Okay， so this is fine。

 I just have to realize that what I'm sorting is not just。

Integers but integers that have some log n bits of auxiliary data attached to them。

We are  supporting man leaves and some internal numbers great。We唱。

It's actually like several sorts right No no， no， no， I take the list of N be over two bitkeys。

 I throw them in a bucket and I sort them。So it's one recursive call。Right。

If if I spread things out into multiple recursive calls。

You'd get some cumulative overhead that would give you a different final running time。

equence are so important。Like each juice effect the store both of them。Right， but yeah。

 everything each of those each of。The children of any node are going to show up as a sub sequence of that final sorted list。

In sorted order。But I need to also carry this auxiliary data to know how to glue those back into the tree。

Okay。So this is the Kb factorctor R range reduction thing。Everything， you know。

 everything after the recursion。Takes linear time。嗯。

The only weirdness is you have to decide whether you like things to be deterministic。

 and then you have to use a ton of space and you have to use this implicit initialization trick。

Or you have to admit， okay， fine， I'll allow randomness and use hashing。

And then you get only high probability results， but only using linear space。Okay。All right。So。



![](img/d1a8469b380bbad0695f66c3f514b201_10.png)

看嘛。

![](img/d1a8469b380bbad0695f66c3f514b201_12.png)

嗯。Now using some of the data structures that we've seen before。

We can also use those dynamic dictionaries。To to sort so we could。

Insert the end keys into say a venom de Bo tree。And then find the minimum element and or successfully find successors starting at negative infinity and you find the successor of negative infinity and find the successor of that and so forth。

So this will get you。And。Let's see log log U。In this case is log W。

That's what you get from Benom Devvois。And then for using。Fusion trees。Get again， n。Log in over。啊。

Well， it was log in。Is it log N over log W？I forget what is the running time for what's the insertion time for fusion tree。

 I'm sorry。Can somebody who has notes？Was some is like log n over log W or something like that？

Log based WN。I think it's this。嗯。So notice if I take。These two things， venom debois is slightly。

Slower actually than currkpatric reh， but if I take either currkpatrick re or venom debois and fusion trees and use whichever one is better。

 this immediately gives me。啊。An algorithm that sorts in end time square root of log end time。Com。

So what I want to talk about next。Is。Sorting in。En log log end time。Um。

And this uses a second trick from an earlier paper。诶。Which is called。Pt。Sorting。

And here the idea really is。To take full advantage。In a way that we haven't yet。Of the。

The idea that we can pack smaller things into larger words。系。So this。

This pack sorting idea was originally due to。U。Albers and Hagger up。

And I don't remember the dates Al Strpa at all is Haer up is one of the Al in that list。Okay。

 so the idea。Behind packed。Sorting。Is。Let's suppose。

We're in a regime where the number of bits for each of our keys。

It's significantly smaller than the number of bits that fit in a word。Okay。

 so I'm going to start off。Just by assuming that W or sorry B is at most。A。

W divided by log n over log login。系。The choice of parameters is specifically there to make sure that in the end。

 the running time of the algorithm is going to be linear。诶。Okay。So I'm going to。Pack。

Let's call this parameter K sp。Login。Log， log in， keys。Into one word。

And then we're going to use merge sort。But。OrThe way you all remember Merzart。

 so you split the array in half。Now this array of packed words， you split it in half。

 recursively sort the left and right halves and then merge two the two sorted arrays I'm going to bottom out the recursion。

When my sub problemblem fits in a single word。And in fact， I'm going to use as a subroutine。

An algorithm that will take two sorted packed words。And merged them。

Now each of those sorted packed wordss contains k keys。

 so a naive merge algorithm take order K time now my merge is going to take only order log K time。系。

But。Merge。Any to。Sored， packed。Words。In。Log K time。Not。Okay。Can。Um。All right。So if I do this。

 then what's going to happen is merge sort normally runs in N log end time。

But I am replacing sub portions of that algorithm that run in order K time with subrout that runs in order log。

Log K time。So the running time goes down by a factor of k over log k and with the。

Choice of K that we've used here， this is going to come out to be linear。嗯。

So I have to tell you how to do this merging。And。Talk about the merging I mean this。

The merger actually。Comes from the land of。parallelllel。Algorithms。This is Bacher's。Um。Bnic。

Merge algorithm。Now。Vcher described this as what's called a sorting network。Okay。

 so a sorting network。You imagine that you have wires。That carry the keys that you're trying to sort。

Say from left to right。And at various points in the network。

 you have connections between those wires。These connections correspond to compare exchange operations。

So anytime you see a connection between， say， the I wire and the Jithwi。

 that is the instruction if X I and Xj are out of order swap them。Okay。

 so the way Bacher actually described his。Merge algorithm。

Is by a sorting network that has log K depth。So I guess it's a。

Here I'm imagining that I have K wires。mI guess technically it's a merg network。

 not a sorting network， but these things generically are referred to as as sorting networks。

 maybe a better name for it as a compare exchange network。The log K depth。

Now the number of compare exchanges performed by Bacher's merge algorithm is still order K。

 but I can perform these in parallel， so you see those two compare exchanges forth and the left。

 I can perform those at the same time because they involve independent things。In fact。

 I could also do the first three all the same timen。So depth means。

 I find a prefix that I can all do at once， that only counts as constant depth。

And what'll eventually turn out is that because I've packed those k keys into a single word。

 I can actually do those multiple compare exchanges。By doing。

Parallel comparisons or board level parallel comparisons like we did with fusion trees。All right， so。

Basic setup is， okay， so let's say I have。sortred。Words。X and Y。Then if I look at。

The sequence x concatenated with the reversal of y this is this。This。

Sequence of 2K things is a property that is what's called bionic。

That means assuming there are no ties， there's one local min。And there's one。Local max。

Even after rotation。Okay， so this is kind of trivial initially because x is increasing and then y is decreasing。

 so there's a single local max exactly in the middle and there's a single local min at one end or the other。

But I'm going to maintain this property being bionic。As I。Recursively merge。Okay。

 so here's the algorithm in this。Bonic。Am。And。I'm just going to imagine that I have a single。

Aray that I'll call Z。H， so。For I goes from0 to k over2 minus1。Yes。

Z sub i is bigger than z sub i plus k over 2。Then swap。And then。Sorry， I called it byonic。

Don't batcher。Recursively merge。It recursively sort the left half。

And then recursively sort the right half。Okay， forget the I'm getting a little。

Hyper with my brackets and braces here。Okay。Okay， so。U。The two things that that。

I need to observe here。First of all。Both of those subres that I'm recursively applying the algorithm to。

Are by tonic。That's not necessarily obvious And the second thing is because the initial array was bitonic。

Everything in the left half， after I do this compare exchange is smaller than everything in the right half。

so at some level， this is Quick sort。I'm doing a partition of small things on the left and large things on the right。

 and then recursively sorting the left and right halves。

And the reason why this all works is because the original array is bytonic。诶。This is。Bonic。

And small keys， this is bionic。And big keys。This is all done in parallel。In constant time。

So notice the way that I would do that is I would take my， let's say it's a single word。

 I'd split it into the left and right halves， put the left half underneath the right half。

In parallel， I might need to inject some zeros and ones。To spread them out。

 but we know how to play these games of spreading things out and compacting with multiplication。

Then you get the results， you mask out the parts that are big or them together， put them here。

 mask out the parts that are small or them together， put them over here。

 then I have my recursive sub problemsm， so I won't walk through the details。

 but this can all be done using a constant number of standard arithmetic operations in the word realm。

😡，It off' this whole idea of workinging network came from like wireless model。

So where did this distort sorting model come from？So back when Moore's law was still a thing。

 but not hadn't really like taken off as much as it has now。

People were really interested in doing things， actually building parallel computers and you know sorting is obviously one of the most important。

呃。Most widely applied algorithms on the planet。So I think the idea of the sorting algorithm states back to the 1960s。

Your people are like trying to build special purpose hardware for this。

I guess one thing here I should point out， this was relatively early in that history。

I think Bacher's algorithm dates back to the late 60s。And if you use this bytonic merge。

As the underlying basis of merge sort。You actually get a parallel sorting algorithm that runs in log squared end time。

U using only， you know， compare exchange operations。That has since been improved。

 there's something called the AKS sorting network that actually only needs log n depth。

It's a monster， I don't want to talk about it， some of you might have been at my sorting talk and I used the word expander graph。

Yeah， they're expander graphs inside the AKS network。 So it's log n times a few hundred。

This is log squared n times 1。So in practice， people use Thatcher's merge sort。

There's another version that is essentially the same algorithm running backwardss called batchcher's Even Aword sort。

That has the same running time and these are actually also used in distributed settings。

For doing sorting now。Parallel algorithms where you've got lots of processors all running on the same data。

 that's a little bit less common now it does still show up in like you what used to be called blue waters。

Those really big things now you've only got eight cores。Or maybe 16。

 so literally large scale parallelism that is out of the question。

But now distributed computing is a lot more prevalent and same ideas show up there。

I don't know if this answered the question， it's sort of like。

It started back in the days when people were still bidding computers out of wires。啊 fresh。Yeah。

 exactly， it's an abstraction of the hardware。And it's a nice， clean mathematical model。

 So as soon as you throw it in front of somebody like， you know，oo。He's going to go， oo，ooh，ooh。

It's nice， clean math， right？Okay。But just to give you a little bit of an idea of the proof。嗯。

For all of these oblivious compare exchange sorting algorithms。

 so you notice the comparisons that I do do not depend on the values in the input array。

It's just literally a circuit that I pump data in on one side and I get data out on the other。

So any sorting algorithm that behaves like that， so it's an oblivious。嗯。Compareed exchange algorithm。

It suffices。To prove。That it sorts。Arays containing only zeros and ones。In fact。

 it's sorting these B over two bit keys or sorry these B bit keys。It's enough to say， well。

 if I close my eyes and I pretend that the input is only zeros and ones。

 then the zeros and ones will get put in the right order， and then what you imagine is okay。

 pick your favorite value of x， replace all keys less than x with a zero。

 all keys greater than x with a 1。The network sorts those zeros and ones correctly。

 and that's consistent with all the comparisons that it does on the real keys。

So all the things larger than the next end up after all the things smaller than next。

And this holds for all X because the behavior of the algorithm doesn't depend on the data。Okay。

And then you'll notice that Bionic。In this case， just means that there's a block of zeros。

 a block of ones， and another block of zeros， or there's a block of ones， a block of zeros。

 and a block of ones。And now you can kind of walk through the cases yourself that when you do the first the passive compare exchanges。

Depending on whether you have more zeros or more ones， you're either going to end up with。

 say the left side being all zeros， or you're going to end up with the right side being all ones。

And the other side will again be in this form where there's only a single interval that's out of place。

Okay， so at this point。There's this simple case analysis。And I'll read the details to work out。

 but at this point it's pretty straightforward。O。So。How do I use this。

If I want to sort in and log log end time， so now back to。Um， all stripep。Okay， well， so the idea is。

I'm going to apply。呃。Kirk Patrick Reich rangenge。Reduction。Let's poll it to log log n times。Okay。

 so I initially start with NW bit。Keys。At this point。

 I now have I've reduced it to NW over log squared n bit keys。And at this point， I do PA sorting。

Okay， so this part takes n log log n time， and this part takes linear time。Okay， so W the keys。

 I do rangetro， retro until the keys are so small。That I can then apply this packed sorting algorithm。

 which under the hood is this parallel compare exchange network。Underneath word sort。Okay。

All right so。We're now kind of left in this interesting middle space here where。诶。嗯。

If the number of keys is。Let's say B is less than w over I'll just simplify log squared n this is。

I Bruce He up。So。And kind of this we're starting to get into interesting territory here if my keys are two。

 are short。Polylaarithmic number of bits， is that right？Yeah， if my keys are only log n bits long。

 then I can sort in linear time。If my keys are only polylogarithically long。

 I can sort an log end time。If my keys are longer than that。I can still get down to N log log N。嗯。

But it turns out now the second algorithm by Lstrip at all。Which they call a signature sort。

This runs in order end time if W is bigger than。I'll just say log youd in to simplify things。Um。So。

Right， this is this sorry， let me。Rewrite this this one in quality in different form。

 this is if W is bigger than B log squared n。So the pacts， this。

Pet sorting algorithm basically says if the word size is really large。

It's a log squared n factor larger than the actual length of the keys that we're sorting then I can sort it in linear near time。

So there's this strange tension， if the word size is small， I can sort in linear time。

 and if the word size is unreasonably large， then I can sort in linear time。

And the signature sort algorithm takes that sort of unreasonably large condition and says。

 it doesn't matter about even if the keys actually fill up the words initially。

If the word size is really， really big， then I can sort in linear time。And in between those two。

The fastest disorder algorithm we know is their Kiurrk Patrick Reich。And log login。

So there's an open question here。If I'm running on a machine that has word size that is strictly bigger than log n asymptotically。

But strictly smaller than log2+ epsilon N。Can you sort in linear near time or is there some sort of weird analog and lower bound？

It's an open problem only a theoretician could love。But still it's an open problem。

 we don't know that we can sort arbitrary integers of whatever word size of linearard。Um。

So I want to spend the last。15 minutes。Talking a little bit about。Signature sort。

But I'm not going to be able to go through the algorithm in complete detail because just time。

 but I'll try to give sort of a high level overview and so I'm going to be like claiming some things that don't obviously work and we'll refer to paper or to the lecture notes from MIT。

 which I think do a good job of simplifying things for more details。Okay。So。Signature sort。

The idea here。Is again， I'm going to do range reduction。But I'm going to do faster rangetro。

 meaning I'm going to reduce。The size of my keys not by a factor of two， roughly by a factor。

 what is it a factor of log N to the epsilon？So roughly by a small polyloggoithmic factor。嗯。

Via Hassian。嗯。Now， remember， even the earlier analog log n algorithm。

 in order to actually make it work with only a reasonable amount of space。

 I already needed to use hashing。Here I'm not using hashing to keep the space down。

 I'm using hashing to actually keep the time down。嗯。Okay。So here we go。Am。Break each。Bbit key。啊。Into。

Log to the Epsilon N chunks。嗯。Now I'm going to。Replace。Essentially， replace each chunk。

With an order log and。Bit。Hh value。Or。Signature。And so if I。

 if I start with a key X that'll turn into you know X twiddle， this is。Concatenated。Cattaininated。

Chump。Signatures。Um。Now each of these is size B over logged the Epsilon N。

But remember now I'm in a regime where the integers that I'm sorting are really， really big。

 they're more than log n bits long， so replacing something of size B over log to the Epsilon N with something of length order log N is actually making things smaller。

😡，嗯。Now。Now， I， I have to somehow go from。You know， as， which has been divided up into these chunks。

To X twiddle， which is this smaller thing。That has。

 you know only length number of chunks times log in and I have to do this using hashing so it it turns out if you use。

What's sometimes referred to as binary multiplicative hashing。

So you choose a random odd number with the right number of bits。And you define。

The hash value of some chunk x sub I as。A times x sub I。诶。So how does this go？😔，Yeah。Maud。

Two to the B over2 to the B minus。Well， L， where L is the length of the thing。

The length of the final hash value。 So as long as if a is chosen uniformly at random from the set of all odd B bit integers。

Then it turns out that the probability of any collision is going to be about2 over2 to the L it's going to be in which is。

Inverse polynomial。And so as long as I make the constant in that big O log n bit hash value。

 if I make that constant， say four， then the probability that this gives me any collisions at all is polynomly small okay。

 so no collisions。With high probability。But you'll notice everything that's going on here except that multiplication is doing things modd a power of two。

 divide by a power of two， so that's all just shifting and masking。

The only thing that I'm doing that's sort of interesting here is the multiplication。

So the idea now is if I take only the odd chunks in a or it's only the odd chunks in X。

 and I multiply that by a， what I'm going to get is，哦。X k minus is2 times a and so on。嗯。

These are actually going to be， I should say， these are actually going to be two B bitword。

So they're going to fill up。What used to be two chunks？But then the hash value that I want。Is just。

A particular sequence of log n bits in the middle。Okay。

 so I can compute the hash values of every other chunk。In Constantine。And then again。

 for the even index chunks in constant time and then ore them together and then do the same kind of compaction with multiplication tricks that we did for fusion trees。

To pack all of those hash values into a single contiguous string of bits。Okay， so。So this is doing。

Parael hashing。In constant time。That is free of collisions with high probability。ok。

That was the interesting bit。Or one of the interesting bits。Okay， now。

The next step just sort of like Kirkpatrick Ric， remember that the idea with Kirkpatrick R is I split things up into a left left chunk and a right chunk and able to try over those chunks I'm going to do the same thing here I'm going to build a try。

Over where each child is determined by chunks， but not by the original chunk value。

 by its hashed chunk value。Okay， so build a try。Over。What I call this。嗯。

Build to try over the signatures。嗯。So this has depth。Log to the Epsilon then。

But I need to do one more thing here。To keep both the space and the time low。

 which is I need to build what's called a compressed try so remember when we build a try abstractly we're taking a complete tree where at each node I have a a child for each possible。

Log to the Epsilon N bit string。But I actually don't keep around the pointers that lead to empty things。

 So I prune out the irrelevant nodes in the tree。U。A compressed try means I omit。呃。

Deggree one notess。So if a node in the try has only one child， I don't explicitly store that node。

Instead， the parent or whatever ancestor is that has degree more than one points directly to its nearest descendant that has degree greater than one。

Okay，This is just to make sure that the number of nodes in the try is only order n because every node in the try has at least one split。

系am。So。This means there's going to be order n nodes。No。Um。Turns out you can do this essentially。

 I can do this in linear time。By building the， you know， I've already sorted， oh， have I sorted， no。

Sorry， I missed a step。Sorry， step three。Sort the signatures。 sorry， that's kind of important。嗯。

So sorry， let me back up and explain the recursive sorting thing。now。I've。

Now replaced my original W bitkeys。With shorter signatures。Right， so。呃。

Each of these shorter signatures has。Log to the one plus epsilon and bits。

Because it's made up of log to the Epsilon。I should say big O here。

They're logged to the epsilon in chunks for each chunk。

 I've computed an order log in but signature and I've concateated all those together。

These concatenated signatures are now small enough。

That they fit into a single word with enough space that I can do packed sorting。

So because I'm started out with a word size， it's at least log cubed in。

 getting something down to log to the1 plus epsilon in， that's enough slack。That。

I can use the packed sorting algorithm。And this will run in linear time， this is not recursion。

This is just directly calling the Alberts He sorting algorithm。By。All right。So sorry。

 that was a rather important step that I left out， I apologize for that。

Once I've sorted these signatures， then the idea is what I really would like to do is build a try over these and then do an in order traversal and then I've got the sorted order of the signatures。

The problem is I don't want the sortrded order of the signatures。

I want the sorted order of the original keys。So this hashing is not going to preserve sortded order。

But I'm still going to use the shorted hash values to be able to extract that sortded order。

Ultimately via recursion。Right so I'm going to build this compressed try。

 essentially I'm going to just insert into an empty try one at a time in sorted order。

 walking my way from left to right， each of those insertions will happen。

 even though this is a log to the epsilon and depth tree。

 one can show that each insertion takes only constant amortized time。

Another way to think about that is the operations that you need to do to build the tree。

 inserting things from left to right， exactly mirror the operations that you would need to do for a。

 I think is a post order traversal of the tree。Um so。啊。In。Sored order。去。Okay。

We're getting close to the end。Sinces four。Five， now I'm going to recursively。Sort。The the edges。

Of the try。嗯。By the actual values。Not。The signatures。Okay。

 so what I'm really going to sort by are the following tus， so the first thing is。嗯。

One of the fields in the tus I'm going to sort is the ID number of the node。

 so I'm in the end going to want to figure out for each node what the sorted order of its children are。

So I'm going to store that node ID in the。In the。Is the first field in the tuL I'm sorting？

The second node is going to be the actual trunk。The W over log to the epsilon N bits that make up that chunk。

And。Since I'm sorting the children of that node， it's convenient to just carry， you know。

 this was originally the fifth child。And so when I saw。

 I'll be actually able to extract an explicit representation of the permutation I need to apply to those children。

系。嗯。These。Tups。Have B over loggged to the Epsilon n plus big O of log n bits。啊。And in particular。

 if I first play the trick of finding the minimum child of each node and pulling those out。

re actually they're exactly n of these。So I now recurse。And then the last step is。Permute。啊。

The children of each node。And then do an in order traveral。Okay。Um。And that's the sorting algorithm。

The analysis basically， again， skipping over some details is after I do。Let's see， I think it's。

Roughly one over epsilon levels of recursion。The size of my words is going to be w over log squared n at which point I can just use Pat sorting。

But this is a constant。So。Everything here happens in linear time。Right， so this is linear time。

This is when your time。Except for this recursive call。

But the number of levels of recursion I need to do is only a constant。

 depends on what value of epsilon I choose， which ultimately depends on the word size。嗯。

So after a constant number of levels of recursion， each of which takes linear time。

 I' reduced to the case where I can apply the pack sorting algorithm directly and that also runs in linear time。

 so the overall algorithm。Runs in。L me your time。So that was a lot。嗯。

lotThere's a lot of details that I skipped over， but hopefully you get at least the main idea that goes into this algorithm。

This is the most general linear time learning algorithm we know of。Leas restricted。Okay。

I'm happy to answer a few questions， but we're out of time figure out what I'm going to talk about on Tuesday。

 but remember that next Thursday we're starting the project presentations。Thanks。



![](img/d1a8469b380bbad0695f66c3f514b201_14.png)