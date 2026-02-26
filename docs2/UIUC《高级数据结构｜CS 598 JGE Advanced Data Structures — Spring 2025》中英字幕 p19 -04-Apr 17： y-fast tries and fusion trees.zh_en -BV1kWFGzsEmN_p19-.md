# UIUC《高级数据结构｜CS 598 JGE Advanced Data Structures — Spring 2025》中英字幕 p19 -04-Apr 17： y-fast tries and fusion trees.zh_en -BV1kWFGzsEmN_p19-

![](img/ea74d004d522f56304f0f74cf161641e_0.png)

So嗯。Administrative announcement again， there is a form linked from the course web page。呃。嗯。

To register。Project teams。嗯。Please fill this out by Monday。

Because I want to be able to post at least a preliminary。Presentation schedule next Tuesday。

 because the first presentations。We'll have to start the following Tuesday。

I're going to make sure that so the first presentations are going to be in a week and a half。Um。

 and so I want to give everybody if I can， at least a full week notice beforeum you're called on to present。

 yeah。发意思。It's up there now。Yeah， sorry， I put it up there this morning or earlier this afternoon。

Yeah。Patients for incentive， either how long are you expecting them to be what are you？

So this is a good question like what are the presentations supposed to be？Pandnatively。

 I'm thinking on the order of 15 minutes。Which if you're making slides means this is you know on the order of 10 slides。

嗯。Both of these numbers are， I think， more likely to creep up。This is intended to be。

E progress reports。Not a。Definitive description of a completed project。

 So I'm not expecting projects to be done in within the next two weeks， but at the very least。

You know， by the time you're giving the presentation。嗯。You should have。

Naiil down what your target problem is。And you should be able to present very briefly。

 here's what the state of the art is for this problem。

 or here are some related problems that have known solutions that we're trying to emulate and have to be able to say something about your plan of attack。

This is the special case that we're going to try to reason about first。

 these are the assumptions that we're going to make initially we've started implementing this。

 but you know here are the things we can think we'll reasonably be able to implement and test before the project deadline so。

Plan of attack， sorry， let's see。So what problem？Relevant。Past results。Plan of attack。

And if you actually have any sort of initial observations。That if you know。

 things are actually starting to come out of the discussions。

This would be a good time to talk about them， but at this stage it may be that know sort of the initial observations is we thought about using ideaea X。

 but we fairly quickly convinced ourselves that that was not going to work because why。

So that also is progress that if you've had ideas that you've been able to shoot down。

Those would also be。啊。Observations。Let's call them dead ends。So for a 15 minute talk。

That's like four minutes。For each of those， two or three slides for each of those。That's it。呃。

One thing that I do want to emphasize early。So I would like you to actually make slides in particular。

 because I want to record this。I'm going to ask people to present slides on Zoom。

zoom will be recording everything I think that'll be easier than like trying to swap out displays up here or having everybody send send me a link to their slides or something like that just bring up your own laptop connected to the wfi and。

We'll share the screen and you'll see that。If you're not used to giving talks with slides。It is very。

 very， very easy to make slides too detailed， it is very easy to try to squeeze too much into the slide talk。

 so getting it down to 10 slides。And actually spending only 90 seconds on each slide。

Is requires practice so as you're preparing the talk。

Give the talk in even it's in preliminary form and time yourself。

 actually say all of the words out loud。The the practice that I've honed over several decades for giving a 20 minute conference talk is I will practice the talk by myself in my room until I can give it in 25 minutes。

Because I know that when I'm alone in the room， I will go off on tangents and I'll say I'm an awe lot。

But when I'm actually up on stage， the adrenaline keeps me more focused and so I'll go through faster。

Also。Talk。😡，Slowly when you're giving these presentations。

 because there is a natural tendency to speed up your speech。嗯。Again。

 these are things that just are going to require。Practice。

And this means not only practice once you have the slides， but the practice will tell you， oh。

 I'm likely to need more detail here， wait， this is way too much detail。

 I don't have time to talk about this。To keep it under the time limit。

If we can actually keep things under 15 minutes。That means we can do four talks per day。嗯。

Which means we only need three days。Because weve got like 75 minutes slot for each lecture。嗯。

So that would be。A week from next Tuesday。The following Thursday and then the following Tuesday。

 and then the Thursday after that is reading day。So reading day I'm assuming is。An overflow。

Either because there are more than 12 projects， or if we don't actually stick to 15 minutes because people are asking questions。

Or the talks run long for some other the reason we may need to spill over under reading day so one of the things that the survey asks is whether you are。

The people on your team are absolutely not available。To give a presentation on reading day。

That will mean that your presentation will try to schedule earlier in the schedule。

Hopefully we won't need to spill over。嗯。If things look really constrained。

The 15 minutes may go down to like 12 or something， but then it's starting to。

Get almost too short to be useful。嗯。Does that answer your question？Yeah。The form does ask。

What is your project about what's the it asks for a title and it asks for a brief description like a paper abstract so the brief description just 51 paragraph。

 it's completely fine if you don't know what that paragraph is going to be when you submit the final write up。

Again， progress report， not final report， but also you'll be able to revise that submission later。

USo what you're you just， even if you just don't know completely yet。

What the outline of the project is going to be， at least I need to know who's on the team。

So that we can plan out how many talks there're going to be。Okay。Um。All right。Any other？

Questions about the presentations。Right。Okay， so last time。We talked about a couple of。嗯。

Data structures for doing。Ordered dictionaries so predecessor success are searching over sets of integers that exploit the fact that under the hood integers are represented by by bits Okay so the first2 rules was the vanom devry so this one。

呃。Do either。Whos or updates。In。Log。Log you time。Using order U space where U is the size of your universe So you're imagining that all of your items are integers between zero and u minus1。

This is fine。We know that we're doing n things that are between one and order n。

Because then that becomes log， log n time using only order end space。

 but if your universe is any larger than that， even if the time is better。

 the space is getting kind of out of control。嗯。And let me be a little clearer about this。

Then there was an alternate approach to this called the XF Tri。嗯。I was reminded recently。

 so the word try。Actually comes。From the word retrieval。And so the person who first published。

Tries called them treesre。Because that's the sound you see in the word retrieval。

 nobody calls them trees because there's something else that's called that。

So I'm going to stick with triess。嗯。The idea here is I can do predecessor and successor queries。

In log。Log you。Time。I can do insertions and deletions in log U time and the amount of space that I need is order n log U。

And。Very roughly the way X fast tries work。Is you imagine building a giant？Bineary try。Over。

Your universe。But you only keep the parts that are actually relevant。

And then in addition to a bunch of other pointers at every level of the try， you keep a hash table。

That records which nodes at that level of the try are actually relevant。

 that actually survived once you prune away any nodes that don't have so your items are stored down in the leaves。

 so if you have a node that has no descendant leaf that belongs to your set of items then it vanishes。

 the hash table records what's left。And so the log log U。Is doing a binary search。

Over the log U levels of。The try。To find the first note the deepest node in the try that would be on the path to your query value and once you've got that。

 then with a couple more pointer chases， you've got the predecessor and successor。so ultimately。

 the high level thing is it's。Binary search。Over。Levels。4。The longest。Prefix。Of X shared。With。

Some let's called the query value UQ， some X in my set。And that's where the loglo comes from。

Now the reason that you have logged U there is because when I do an insertion。

 I have to add potentially a chain of ancestors leading up to the root of the try and they're log U of those same when I do a deletion。

 I may need to delete log U things and because every time I'm inserting or deleting a node at any particular level。

 they have to do an update to the corresponding hash table。嗯。

The reason why it's n log U is for each of the n leaves that survive。

 there are potentially each of those leaves potentially is a distinct ancestor at most of the log U levels of the tree。

Okay so the analysis here can't be improved。Directly。But what Willard did？Is he proposed？A。

An improvement called a whyF try。I actually have no idea what X and y you're supposed to be referring to in these days。

 it just the， I think Y was just the letter that came after x and the alphabet。嗯。

But the punchline here is you can do queries。Or updates。In log， log you time。

Although the updates are amortized。And the amount of space that you need is only order N。All of this。

 because it's using hast table， by the way， is this is in expectation。

 because hash tables have to be randomized。嗯。So before I go on to what details of Y faststers。

 are there any questions about x Fasts？Okay， cool。So。The key idea is to use。

A trick that we saw earlier way at the beginning of the semester with range minimum queries called Indirection。

So I'm going to lump the items in my data set into chunks of size data of log n。😡。

And I'm going to build an X fast try for one element in each chunk。

And I'm going to build a secondary data structure for each chunk。Okay， so。It's a split。My data set S。

Into about an over log N。Chunks。And your and your。Splitting them by rank。

 so the first chunk contains the roughly log n smallest elements。

 the last chunk contains the roughly log n biggest elements。Each。Of size。Between。

Let's say one over four。Log base2 of N and for log base2 of n。Ultimately。

 the reason why I have this constant factor gap。Is that these chunks are going to change size when I do insertions and deletions and occasionally when chunks get too big。

 I'm going to need to split them， when chunks get too small， I'm going to need to merge them。

 and those splits and merges are going to take time。

 but I want to be able to amortize that time against the number of operations that I needed before each split or merge。

So I need to give myself some breathing room exactly for the same reason that under normal dynamic arrays。

 you grow when the number of items is doubled and you have when the number of items。

 the array is only 25% full。So。And then I choose。one。Representative。UFrom each。Chrunk。Okay。

 so I'm going to call these chunks， you know， S1 S2 up through SK。

 and I'm going to choose my representative Y sub I from each chunk s subi。系。

So I'm going to build first。An X fast， try。4。Why one through why？Okay。

And then for each re in this try。I'm going to build a balanced binary search tree for the corresponding chunk。

AndSo why sub lens here？I'm going to balanced binary search tree for that chunk S sub I。Okay， so。嗯。

Try。Part of this。Has size。En over log N， because that's how many things I'm storing in there。

UIs it log En or is it Lo U？Sorry。I need to。Play with my handwriting a bit N log U。

Each of size between log U。You know， plus or fourth log U and for log U。So this is N log U。

 not N log N。嗯。So。The total depth。Of this tree， that's n over log U things。

 the total depth of this tree is still log based to of U because the underlying binary try still has exactly U leaves one for each item in the universe。

So the depth doesn't change， even though I'm storing fewer things in it。And so in particular。

 doing like predecessor churches within the tri part still takes me loglo you time。

But when I want to do， for example， a predecessor search。

So if I want to find the predecessor of some query item Q。On。What I can do is find。

I can do a predecessor successor query in the XFtry to find the predecessor among the representatives。

Of Q and find the successor among the representatives of Q。And。What this will tell me is。Two chunks。

One of which contains the predecessor of Q and one of which contains the successor of Q。

 and they might be the same chunk and they might be different chunks。then I need to search。

The binary search tree of。Chunk。You know， pre Y and。The， the the chunk for。The successor of Hawaii。

This part takes log， log U time because it's an X fast try。This part takes log。

 log u time because it's a search in a balanced binary tree with。That contains lot view things。

So the overall time to do either a predecessor or successor query is still going to be log。

 log in the universe size。U。No。Suppose I want to do an insertion。嗯。So。First。

 I do a predecessor successor query to figure out。Which binary search tree the new item should go into？

Okay， so find the chunk。S sub I that。Should。Contain。

Q now it's it's possible that Q fits in between two chunks， pick one of them arbitrarily。

 doesn't really matter。嗯。But now I'll do a standard insertion。Of Q into that binary tree。

But then there's a。嗯。The possibility that by doing that insertion， I've made that chunk too large。

So if the number of things in that chunk is bigger than four log based two of U。

I'm going to split S sub I。Into。Well， I guess I call it S minus。And S plus。Each with。

Two log base to venue items。One of those two smaller trees contains the old representative of S of I。

 then I need to insert a representative from let' without loss of generality， one of these。

Into the X fast try。Now。嗯。Most of these steps。Only take log blog U time。So。

This part is directly from there。Bg bug you。Doing an insertion into a binary tree containing log n things。

 Again， that's log G U， assuming you do the usual balancing things with A VL red black tree display。

 What have you。嗯。Then I have to do a split and an insert into the X fast try the split。

Provided I'm doing something that supports fast splits， for example。

 troopss or s trees or the right kind of weight balance trees。嗯。

It's possible to do it with AVL trees， but it's more annoying。

 but there are balanced binary trees that allow you to split in the keys into everything smaller and everything larger than some pivot value in only log n amortized time。

Use one of those。And then finally， this insertion。Takes me。Order， log you time。But。嗯。

When I do that insertion， I did it just after creating two chunks of size。To log you。

So the next time I will need to split。Either of those chunks will be at least two log U insertions into the future。

And the next time I might need to merge those chunks will be at least three halves log n or three。

Two months a quarter。That's7， fourth log log U deletions into the future。 So what I can do is I can。

Charge。To insertions， you know past insertions。Into。S of I or deletions。And well， there had to be。

At least some constant times log U of those since SI was created either by a merger or split。

And so the actual amortized time for that last insertion step is constant。系。So the punchline is。Log。

 log u plus。Amortized。Conunston。Yeah。这不是指定。收到。So incredibly possible is that everything in SiI is prefix I'm not doing any bit prefixes here。

A representative is just an element of that chunk。I took the items which are all logggy bit words。

Their log U of them， I pick this one， this is my representative。嗯。You two some different treats。

Same thing。 Thanks fast try。There's no mapping to the X tribe taking these numbers。

 which are distinct because they're coming from disjoint sets。

And I'm storing them in an next fast try。So different numbers will different paths in the X fast try。

That makes sense。Right so there's no compression going on， there's no encoding going on。

When I'm storing things in the XF try， every one of those log U bits shows up as a node in the XF try。

 some of those bits are shared because two different items might share prefix。But ultimately。

 the two items are different， and so they must have a bit that's different and so there's a split。

I'm sorry。I'm just storing fewer of them。Yeah。Simp works out we are buffering the insert deletions that's exactly right。

 we're buffering the insertions and deletions。Yeah。Small， yes。

 it is more efficient than just like off try every time。Yeah。

 that's one way to think of it is that this really only makes sense。

It's the whole try infrastructure really only makes sense if n is bigger than log U。

 because then log log U is smaller than log N。If log log U is bigger than log N。

 then I should switch to something else that this log N is then。Sorry， it's like， yeah。

 it's like a hybrid between these two things。嗯。Dleution is similar。Deletion is。similar。

But merge instead of split。And to be more concrete。If some item if some chunk gets too small。

Then I need to merge it with one of its neighbors and do a deletion in the X fast try。

This new chunk might now be too large。So I might need to do another split。To even it out。But again。

 now。I'm charging the total time that I need to do this merge and split and the insertion and deletion in the XF try to the deletions that got that chunk to be that small。

喂。One of the other issues。Is what happens if we delete one of the representatives？嗯。Nobody cares。

I you know， you just still pretend this a representative the I'm not actually using anything about the representative being an element of the set。

The only property that I need is that the representative for chunk I。

Must be larger than everything in chunkka I minus1。

 and it must be smaller than everything in chunkka I+1。

It doesn't actually have to be a member of the set。

 so if I delete it I just oh there's this ghost representative it's still representing things and there's a little slight logic to now what happens if I try to like I chose something that's just bigger than the largest element of SI minus1 and now I need to insert something new into SI minus1's some constant time updating that you need to do。

嗯。嗯。But it the first approximation is just like you pick something that's in the right range and that's going to be good enough。

So we only need。Max of S minus S1 be less than the representative of S to be less than the min of S plus1。

So again， when the smoke clears， deletion happens in amortized log log U time。

The last thing we need to analyze is the space。So the try is storing N log U items。

And so the tri part of this uses linear space。And the binary search trees。

 well each binary search tree uses space linear in the number of things in the binary search tree that every item in my data is represented in exactly one is stored in exactly one of these binary search trees。

 so this is also quarter n space。And so I get the time and space bounce that I claimeded。

So this indirect trick。Both saves me， at least in an amortized sense。

On update time and it saves me in space。And for more or less， the same reasons。

 I'm cutting the data structure off。At exactly the trade off point where binary search trees are faster and smaller。

嗯。So questions about this。All right。So。嗯。This was more or less the state of art for a while。

 it does have a couple of disadvantages。However， one is。

That you need to know your universe size in advance。Which doesn't sound like that difficult a thing。

 but I mean you could imagine using your universe as whatever will fit in a single word and just use the word size。

 but then it's still a little bit awkward that you have to know when you're writing the code what your word size is going to be and it'd be nice to be able to avoid that。

Just have a single piece of code that runs on whatever machine with whatever word size。

Whatever universe。The other problem is it uses randomization。And that's not necessarily a problem。

 but you the hashing is a little bit awkward， it'd be nice to be able to do something deterministic。

嗯。So it actually turns out that deterministically。Even if you have a polynomial size universe。

You can't actually achieve these time bounds。There's lower bounds that forbid it randomization is actually helping you here in a fundamental way that you can't do things deterministically。

 so the question of whether you can deterministically search do predecessor searching in sublogaric time was open for a while。

 so the first paper to kind of break through that barrier。

describes a data structure called fusion trees。Now。嗯。When you。Cite this paper。

 if you ever cite this paper， please capitalize the title correctly。

The title of this paper is blasting in all Caps through the information Theoretic Barri with fusion T in all caps。

😡，And I don't know whether this is really an actual memory or a Mandela effect thing。

But my memory from seeing the paper proceedings was that the word blasting was like in 30 point type。

On the title page， if you go to the ACM Digital library， it's this very state。

 you know it's capitalized but it'ss line of Helvetica it looks like it was edited in and afterwards。

 but know very clear memory of it this being this blasting you know this huge thing was well you know they were excited they broke this longstanding barrier and so。

The editor is for the journal version， fed the acho pill。

 so the title of the journal paper isSpassing the Information Theoretic Barrier with Fusion Ts。

So they didn't even get to keep the fusion pun in the title。嗯。So。Lxi。

 what are the assumptions that they're working with here。

 so I'm going to imagine that I'm storing and integers。😡，mThey don't really have to be introduced。

 they just have to be things that are represented by by bit strings。For example。

 it turns out that IEEE floating points。If you don't know its floating point and you sort floating point numbers as though they were integers。

 you will correctly sort them as by their floating point values it's one of the features of the Ipoli standard。

😡，嗯。Um。Each。Between。LetSee zero and。U minus1。And。Each。With。At most W bits。

 where clearly you must be less than two to the W。系。So they are deliberately splitting off。

The dependencies in their analysis on。The size of lu from which you're drawing things and the word size of your machine。

And。I'll put an asterisk on this statement， the idea is to build something where the code doesn't know what you and W are in advance。

诶。I also don't know what N is in advance， but that's usual， okay。嗯。So remember， why fast？

Try as give you。Log， log you updates。Or queries。Using order N space or sorry order U。Space。Sorry。

It is order N space。Fusion trees。Give you。Log n over log W。Querries and updates。Again。

 using order end space。Now I'm not going to talk about， oh， and no randomization。

I'm not going to talk about doing dynamic fusion trees， at least today。

 I'm only going to focus on doing things， doing predecessor and successor queries because things are already complicated enough。

嗯。The other thing that I want to emphasize here， this is on a word。Ram。With。The C instruction set。

So the operations that I'm assuming I can do are arithmetic。Division mod。

Bit wise and bit wise or bitwise exclusive ore shifts。And that's it。I do in fact。

 need multiplication for at least the way I'm describing it today。😡，There is。

There variance of this construction that。So variances。

So one thing that people are actually a little bit uncomfortable with is using multiplication and division in constructing these things。

 and the reason is all of the other operations can be implemented in hardware using circuits of constant depth。

But multiplication， you can't build circuit of constant depth that multiplies two numbers and so it's not entirely realistic。

To expect to be able to multiply in constant time。In a universe where I don't know how big my words are。

So there are variants that use only what are called AC0 instructions。Um so。嗯。

This basically means that I can implement these instructions in parallel using a circuit Boolean circuit constant depth。

对。ACK means circuits of depth log to the KN。So the zeros。Just constant。嗯。Unfortunately。

 some of these AC0 instructions are not part of the C instruction set。And one of the。呃。You know。

 another variant that actually makes things a bit simpler is。Using some。Bit manipulation。

Instructions。That are actually common now in modern hardware。

 this wasn't true in 1990 when they published this paper， so in particular。

 one of the things I'm going to need to do and as I'm building the data structure is given a word。

 tell me how many bits in its binary representation are equal to one。

 tell me the index of the most significant one bit。

Those are things that show up all the time in cryptographic hashching applications and security stuff and networking。

 and so they've been over time evolved into the standard instruction set built into our machines。

But that wasn't true in the 90s。One of the rather ugly technical parts of this is how do you pull out the index of least the most significant bit from a word using the C instruction set in constant time？

When you don't know how big your word is。So if you go on stack exchange。

You'll see standard things like， oh， do a bit mask with the top half and then essentially doing a binary search。

For the most significant one bit， it runs in log W time。But A， I don't know what W is。

 I don't know what that magic constant should be。And I don't know how to write just lines of code yeah。

So I'm probably not going to talk about this in too much detail， mostly for time reasons。

But I just want to throw out that it's there。Thank。All right， it's a very。

 very high level description。Of what a。A fusion tree is。The fusion tree is a bee tree。Where B is。

Some polynomial。In。The number of bits in your word。Okay。

 so if you want to think just in terms of intuition， think of U and W as both being log at。Okay。

 so I'm going to build a bee tree that has nodes with log to the one fifth and children。诶。But we are。

Sketch。To fuse the W the1 and fifth。嗯。Numbers。At each node。Into a single word。Okay。

 so these are W to the one fifth W bit words。I'm going to compress or sketch or pull out only the bits that are actually important。

To turn each of these items into a sketch that is only at most W to the4 fifth bits long。

 and then I can fit those W to the one fifth sketches each with W to the4 fifth bits into a single word ofW。

All， so my node is going to look。like。You know， these sketch one， sketch two， and so on。

Then I'm going to do some。Word level。I've never understood how that happens。

 so I don't know if you just noticed I was writing in the word level and I wrote L E， V， LE。

Now I know how that happens when I'm typing。Because one key gets ahead of the other。

 but I've never quite understood what makes my brain do that when I'm writing。U。By hand。

So I'm going to use word level parallelism， so when I'm given normally the way a be tree works is when I'm given a query item and I want to find it in a be tree。

 I look at the pivot values at the root， and I do essentially a binary search through the pivot values to figure out what child pointer to follow。

I don't have time for that。Okay， so I need to be able to find。The correct。Ch。In order one time。

So I'm going to need to take these sketches and compare them to ultimately the sketch of my query value。

 and in constant time immediately go that point or over there。嗯。嗯。There's。A lot of the。

Manipulation of this is going to of the various words are going to boil down to multiplication tricks。

And in particular， one of the multiplication tricks is going to be finding you the most significant bit in constant time。

Which。It's easy if you've got an instruction that tells you the most significant bit。

 and it's easy to implement in hardware。But they didn't want to assume that。系。So。啊。Okay。

So I will sketch， okay？Let's start walking through some of the details here。Okay， so let's。

Go back to the binary。Try。And。Imagine that this is again， pruned。Just like。The X fast try。

so I have a try over all you items in my universe。And。

It's actually overall two of the W items that I can represent。

And the items that I'm storing in my data correspond to leaves。

 I only keep nodes in the try that actually correspond to items that I'm storing。So。In particular。

 though， I'm only going to consider using one of these tries at a single beatery mode。Okay。

 so this is storing。W to the one fifth W bit words。Okay， and let's call these you know， x1 through。

Xk in sorted order。系。So the try is not going to contain any node that has。嗯。

It's going to keep only the nodes that have at least one of these x sub I as a descendant。Okay， so。

Keep。Only nodes。With。An Xi descendant leaf。Your K is W the 15。And if you do that。

 that means that there are most。嗯。K minus one nodes that I'll call branching nodes。

 these are nodes that actually have more than one child。Okay， so I start with k leaves。

As I walk up the tree， occasionally pairs of things get merged。

The total known emerges before I get up to the root is exactly k minus1。系。um。

So that shouldn't be at most that should be exactly。

 but this also means that there are at most K minus one branching。Levels。So these are bit positions。

Levels in the try。Where there is at least one branching node。So only K of these，W， all right。

 so the sketch。Of x sub I is。Only bits。At。The only bits of x sub I。Next up by at。

The branching levels。Okay， so if the try as branching nodes at level zero， level 5。

 level6 and level9。Then the sketch of x sub I will be the zero bit， fifth bit。

 sixth fifth and ninth bit of Xi， all concate all goam together。Okay， so here's X。And you know。

 only these bits matter。Then the sketch of Xi is only going to be those four。Bits。开。

So let me give an illustration here。Just draw a small binary tree here。许。Moman。Right。

So every one time I go to the left， that's a zero， every time I go to the right， that's a one。

So I'm storing 0，0，0，0，1，0，0，1，1，1，0，0，1，0，1，1，0，1，1，0， but the branching levels。Ourre only。Here。

And so the sketches are 000，001。啊呃。0，1，1 and1，1，1。So I only take the edges coming out of these special levels。

Because those special levels have branching mode。So one of the important properties of this。

Is that Xi is less than Xj， that implies that the sketch of Xi is less than the sketch of Xj。

This takes a little bit of time to prove it's basically induction on the lexiographic ordering of bit strings。

Yes， you're right， I'm sorry。0ero， one， zero。Right so。I should be storing。Diz。Um， I just。

Said these are the only edges that matter。So I think this is an idea that somebody came up with last week about like there are levels in the tree that like every node at that level just has one child。

 basically what you're doing is just ignoring those levels complete。到 theS。

Sketchs score does it not matter。It doesn't matter。So ultimately。

 we're only actually going to be storing the sketches。

We're not actually going to be storing the tree。系。Um。So。Um。Well， I've got。Altogether here。

 I've got k minus1 k bit sketches。So I can pack them into roughly K squared bit word。

And the way that I'm going to pack them is。Something that I briefly referred to earlier。

 I'm actually going to store as the pivot value in my nodes one and then followed by sketch of x1。

 and then a 1 followed by a sketch of x2 and so on and a 1 followed by sketch of XK。

Right so altogether， this is still k squared bits。Which is less than W。

Now you might reasonably wonder why I chose W to the 1 fifth instead of square root of W。

Does it seem like squared a W would still fit， I'll get to that in a second。嗯。

There's a couple of subtleties here that make this a little bit difficult。

 so these are like ideal sketches。We're not actually going to be able to achieve this。

 especially if we want to do insertions and deletions。

 but this is the basic idea of what we're going to store in each node。So。

We have enough information to encode the sordid order of things。

If the pivot values in each node of the tree。But， you know， as usual， they are problems。嗯。So。

One problem now is that。Well。If I take a new pivot value， a new query value。

 and I take a sketch according to this recipe using exactly those positions。Possibility is that。

You know that I get the same sketch as something else in my u in my one of my pivots。

That doesn't imply that Q is equal to that value。And more subtly。

If the sketch of Q fits between the sketches of。Two other。Samples， two other pivot values。

That does not imply。That Q is actually between those two things。So yes。

 I encoded the sortrdid order of my sketches。But that's not quite enough， Okay。

 so I can't immediately jump in and go， oh。啊。Just figure out what the sketchtch of Q is。

And then figure out like where it fits in that sorted order and that tells me the thing。

 it's more complicated than that。So I need to do a little bit of what the notes I was following from Eric domainma's class at MIT calls de sketchtcherifying what I'm going to end up ultimately doing is I'm going to do a little bit of work to replace Q with another value twiddle that has the property that。

If X， if the sketch of Q twiddle fits in between。These sketches， then。I know。

That you know how to search。Where to go from there？

And get the right predecessor and the right successors。Okay， so。U。So the idea is the following。去。是。

All right， so let's suppose that I。Finds。Ive somehow figured out where the sketch of my query value fits in between the sketches of my my pivot values so the first thing I mean I'm going to need to do is I need to find the longest。

他们。😔，Prefix。Of。Q and X I minus1， and similarly between  Q and x sub I。

 and I think whichever one of these is longer is going to be the one that I actually care about。

Right right， and so。The picture that you should have in our minds。Is in the tribe。

 theres there's some。Prefix。P。That both say Q and X sub I follow。

And then there's a split now in the actual pruned try， you know， maybe X sub I is down here。

And Q would be down there。So there's a place where these things actually differ。

So in this particular case。I'm going to define。Q twiddle to be this prefix。Followed by 100000。

So the idea。Is。You know in the right subt， I don't know where XI is going to land。

Q Twiddle is going to be the rightmost node in that right subt。

And what this is going to guarantee is that the predecessor of Q twiddle is actually equal to the predecessor of Q。

If I've done this correctly。Is that right？No， sorry， successor。All right。

 so I have the successor of Q twiddle is equal to the the successor of Q once I've got the correct successor。

 then I can just walk to one side and get the the predecessor if I assume that the。嗯。I mean。

 I'm only trying to figure out where to search in this。Beere for the successor。

It's going to be in that left side。Kai。Symsymmetrically。

 I might have some prefix P and then x sub I is off to somewhere over to the left。

And Q is somewhere over to the right， I don't know where in this left sub Q sub I is。

But in this case， I'm going to set Q twiddle to be P dot011111。

 which is the same as this rightmost node in the left subree， and in this case。

 the predecessor of Q twiddle is equal to the predecessor of Q。And moreover。

 because of the way that I've built this。I know that。

If the sketch of Q Twiddle will actually behave correctly in terms of the sortrded order of the sketches of the Xs。

If the sketch of Q Twiddle fits between the sketch of Xi will fit between the sketch of Xi。Well。

Sorry。No， I was right the first time I got this backwards， excuse me。We'll get this right。Okay。

So for example， if I look at this picture on the right。嗯。诶。Between X I and Q。

 there might be any number of in terms of， let's see， how do I say this？I think at this point。

 I should say the paper proves this。Without trying to explain why。And I will admit that I。

I'm not entirely sure。Whether these are swapped or not。The the punchline is by doing this。

 I can find a sort of。Replacement query value that interacts with the sketches in the right way so that when I figure out which two sketches Q Twiddle fits between。

 that'll actually tell me which two items Q fits between， and that will let me recurse。I。嗯。

So this is sort of the high level， in principle how you build the tree and in principle how you would use the tree given a new query item。

So at each node I need to do something to figure out where I need to build the sketch of my query item。

 I need to figure out which of those stored sketches my query sketch fits in between。

 I need to do a little bit of extra legwork to make sure that I'm actually choosing the right interval then I need to test the new sketch again to figure out where it goes in between and now I can recurars in one child。

The idea is each of these steps because you're only manipulating single words。

Is going to take constant time。And so there are a couple of things here。

 how do I build the sketches in constant time？How do I find in constant time which sketch my query sketch fits in between？

How do I turn that constant time calculation into an actual pointer chase？

So the comparisons ultimately。Are going to be。You know。During a query。

On'm doing word level parallelism。So remember stored at。The node is this bit pattern。Okay。

 so now I'm going to prepare the following bit pattern。Okay so I'm going to duplicate the sketch。

K times， and except I'm going to prefix it with a zero。Now when I do a subtraction。

What I'm going to see in these bit positions。Is I'll see a zero。If sketch of Q twiddle is。

Smaller than sketch of x1。And I'll see a one if sketch of Q twiddle is bigger than sketch of Xk。

 so it probably means I need to write these in the other order or swap the zeros and ones。

 but the idea is ultimately I'm going to I can then sort of collect these into a bit string that looks like this。

And the child that I will follow depends on how many of these bits are equal to one。

So I do a single subtraction。Yeah， I think I need to write the sketches in the opposite order。

So let me fix it that way。The sketches in this order k k minus1 down to1。

 and then this is a k and this is a one。嗯。So。The larger cuwiddle sketch is the more ones I'm going to get in the result because the sketches are stored here in decreasing order。

And so I need to be able to extract those bits from the result。

 I need to be able to compress them down to this sketch of the multiple comparisons。

 I need to be able to figure out how many ones are in this result。

But the key operation to do the comparisons is instead of doing a binary search。

 I'm just doing this one subtraction。Right。So I think I'll pick this up again on Tuesday to talk about more of the lower level details about how the sketches are computed。

 why it's one to the fifth in there and not one half。And how to actually do the manipulation。

That's this。Exs summer， right to be able to， you know， find the lowest comments all that's stuff。

This is just the sketchbook。That is what is stored。在场。Oh， that's a good point。That is a good point。

I will need to figure that out how this actually works。I think this is actually done。

 this might also actually be done implicitly。But I'll have to look into that detail。Okay。So sorry。

 this is all still a bit hand wavy and I'm clearly' still a bit shaky on the details。

 but hopefully I can clarify the things on Tuesday。

 I'm happy to answer any questions now but we're out of time。Right。Thanks。当然。嗯啊。



![](img/ea74d004d522f56304f0f74cf161641e_2.png)