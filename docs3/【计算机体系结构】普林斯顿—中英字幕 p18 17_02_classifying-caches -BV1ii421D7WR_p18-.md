# 【计算机体系结构】普林斯顿—中英字幕 p18 17_02_classifying-caches -BV1ii421D7WR_p18-

![](img/6b66ddaed552d86d921d644fc22e1f33_0.png)

So a few things that on our agenda for today， we're going finish up talking about a review of caches。

 And then we're gonna to start talking about in order supercals。 So this is something new。

 And I wanted to。Say this now， but we'll reiterate when I come to it。 This other book。

 The Shennon Lapate book is probably use more is much more useful for the superscale portion of our class than the or Henessan Patterson book。

 And I recommend either acquiring it or borrowing of friends or the library has a copy of that book and least reading the sort of two to three chapters in there would be useful。

 But that's not until the second half of today's lecture。 The first half。

 we have to go finish up cache is。 So going back to a review。 Let's。

 let's talk about what caches could can look like on the inside。 And a couple。

 couple different things about how to classify cachees。 So we've already talked about。😊。

Why cachees are good so。A little bit of a review here。 You have big， slow things over here， big。

 slow memories， and you have the processor。 and you can， you know。

 you can think about how to build small， fast memories。And if we can put a small。

 fast memory close and have a high probability that， you know。

 things are actually located in this small， fast memory， then we don't have to go out to the big。

 slow memory as often。 we can save power and perform and， and， and have better performance， etca。😊。

Okay， so how do we， how do we classify caches and what what are going reviewing what what a cache sort of looks like on the inside。

So processor， cache， main memory。Addresses flow that way。

 Data can go either direction because you can need do a store。

 which will put data out from left to right， or you can read back data or do a load。

 which will have data going back the other way。So let's， let's look at our sort of。

Mythical view here of what a cache looks like or our view of what a cache looks like on the inside。

 so。Cashs contain copies of what is being stored in the main memory。And。

If you look at inside of it here， you know， this， let's say。

 first line is at trying to do store Ad 100。So here we have address 100。

 and it has some data in there。 And typically， we introduce this notion of a line in a cache because we want to reduce the tracking information for a particular cache line or sometimes called a block in the cache。

 If we， it is possible to build something which you know tracks data on， let's say。

 a bit or a byte basis。But then yourre tracking information is probably larger than the amount of data you're actually trying to store。

 So that's not， not really a great idea there。In the cacheier， if you look inside it。

 what we store is we store an address tag。 So it's not the full address。

 It could be the full address， but then you're probably storing extra extra bits。

 You only need to store enough of the address to be able to differentiate different things that could be stored at the same location。

So in a fully associative cache where you can put any data in any location， you would have to store。

 for instance， the whole address in the tag。But if you， let's say。

 have a direct map cache where each address can only go to one location。

You only going to have to store a subset of bits。Yes， and I wanted to sort of point out here。

 you know， sometimes people call the whole thing here a line。

 a line typically includes the tag information。And possibly valid bits。

 and the block is the actual data that youre storing。Okay。

 so this is really review here of how the algorithm or what the， the cache actually looks like。

 But let's， let's step through it briefly。 So processor issues a load。

 So we're gonna look at a load case here。We take the address and we compare the subset of the bits that be could be different for different things that store into a single location of the cache。

 and we check it against the tag。One thing not shown here is we also need to check to make sure it is valid because it's possible you could have an invalid cache line。

 So typically there's one bit which says whether the cache line is valid or not valid。

 Its check to make sure it's valid。And if so， you get a cache hit and you return the data。If not。

 you go out to main memory。Oh， this is a tricky one here。

 You have to go find someplace to go put that data。Because this new data comes in。

 and if you want to store it into your cache now， there's probably something in the cache at the same location that used to sort of bump out。

And we're going to talk briefly about replacement policies。

 and later in the advancedance Cas lecture， we'll talk more about that and other cash policies。

 much more advanced replacement policies。But you kick something out and you fill it in。

 and then you finally return the data。 You could also think about trying to do sort of。

This step and this step in parallel， effectively， and a lot of cash systems and more advanced cash systems will actually return the data before they sort of finish the eviction for to to reduce the latency of the load。

Okay， so let's， let's do some classification。 So some pathology here of what a cache looks like。

So what what we talk about， we can talk about block placement。

 So this is locations that a particular block or particular particular address can be found in the cache。

Block identification， which is the structure of how to actually go find something in a cache。

 If I give an address。 So this is kind of the inverse of the placement question。Block replacement。

 which is figuring out what should be replaced on a miss。 And then finally， what happens on a right。

 So these are all sort of read questions。 Well， block replacement is not only a read question here。

 But the right strategy is is is is a good question here of what happens when a right occurs。

 Do we update all the caches。 only the main memory。 do wevict just out of the cache。

 And all these are possible。Strategies to choose。Okay。

 so let's look at a lock placement figure here and look at a couple different types of caches。

So up here， we have a 31 excuse me，32 word memory。So let's say this is the all of the memory in the machine。

 And depending how look at this， maybe the each block， let's say is one B。

 or it could be some number of bys。 So to give an example， a typical， something like your core2 duo。

 I believe has a 64 B cache line or cache block size。 Some people have tried to of push that up。 And。

 and there's reasons to sort of make it larger or smaller。 But we， we'll talk about that in a second。

So let's take this highlighted location here， block number 12。

And let's see where it can fit into different types of caches。

 So we have three different types of caches here。Let's， let's start on the right side here。

 So on the right side， we have what's called direct mapped cache。 So in direct mapped cache。

It is literally an array。And each。Block can only fit one place into the cache。

 And the indexing function that you use is you take the block number mod。The size of the cash。

So in this case， we are have block number 12 or byte number 12 here。We take 12 mod 8。

 It says block 4。 So this is the only place to go look for the data。Okay， that's， that's nice and。

 nice and simple。 may not be the best performance， easy to build。It's all index based。Okay。

 then sort of one step up from there。 we can start to look at things like set of sociivity。

So what set associative means is instead of having only one location。

 one unique location thats a block can be placed， you allow it to be in some number of locations。

 So in this， there's this drawing here is a two way set associative cache。

 So each block can either fit in one of two places。YouYou can actually have， you know。

 machines which have much more sosociivity or higher associivity。

 So an example of this is the modern。Core I 7 processors。

 theirre sort of L 1 caches are8 way set associative and farther out。

 They're even higher associative。 Probably， I think they have a 16 way set associative cache out in their L 3 or farther out caches。

🤧嗯。So let's， let's look through a basic example here if we want。12 mod 4。 So how do we do this， Well。

 there's only four。Buckets， if you will， and inside that bucket。

 it can f to either of the two sort of sub slots in the bucket。Or they're called ways。

 So if we take 12 mod 4， that means 12 mod 4 is 0。 So it has to fall into。This， this bucket here。

 it could be either one of those two ways， and it can't be in both。That's an important point there。

Finally， there are types of caches， which we'll call fully associative caches。

So what this means is the。Associivity or the number of ways is equal to the number of elements in the cache。

So here there is a， there are 8 elements。 There are 8 block locations in this cache。

 and it's fully associative， which means that there are 8 different。Seets， if you will。

 So it can fit in any of these locations。 So this same address here or block number 12 can fit anywhere in this cache。

 Okay， so now next question is， how do we actually find the block in the cache。So。

When you're going to， let's say， take an address and you want to go figure out where it goes into cache。

let's take a look at the example of a direct mapped cache first。And here。

 here's sort of our information。 We have， we have the the data block。And then， we have。

Some tag information。 And we have a valid bit。 So if we look at the address that we're sticking in here。

 So let's say this is like a 32 B address。Some portion of the address is just going to figure out where in the data block。

 the load or store is going to。 So if you have， let's say a 64 by。Cash line or 64 B blocks。

 Data block。 You're going to basically index into some subword in there based off the offset bits。

Then we start to look at the block address。 So the next。

 this is the traditional way to do this that that you use these sort of middle order bits as the index。

 There are more complicated cache systems which move this around or do much more complicated hashing functions。

 But the basic has function here is we're gonna take the index。 So in this cache here。

 let's say that has three， excuse me， four entries in the cache。 How many。

 how many bits are in this index，2， Yes， okay， so two to the two is 4。

 So there's this indexes in here and chooses one of these four locations。And then finally。

 this tag information here is used to compare against the tag that we store。

 And that will say whether this。Aress is actually in the cache right now。

 or if we have to go out to main memory。So let's， let's work a brief example here。

 We have 32 B addresses。We have a four way Er we have four set cache， direct maps cache。How many。

 how many bits。And we have， okay， so we have 64 B in our block size。How many。Bits are in the offset。

 Let's start with that。 The offset is going to have to index a byte within the block here。

 So if we have byte addressable memory。And there's 64 different entries， log base 2 of 64。Is 6。 Okay。

 so we have 6 B worth of offset。Okay， what do we say about the index here。

We said there's already two bits。Okay， so that's 8 B。 So how many bits of tag do we have。

 So the tag information is 24 B。 And as you can see。

 as you make the data block larger or the data block size large。

 larger or the cache line size larger， you need fewer tag bits。Because it's sort of。

Eats away this way。 And the index gets shifted up。嗯。So that's， that could be。

 that could be a good thing。 Finally， there's this this V column here。

 This is what I was alluding to before。 It's really important。 You need a valid bit。

To see whether the line is valid， it's very possible you could have old data or the cache is not initialized。

 at which point these， these V bits would all be 0 or not valid。Okay。

 so a little more advanced example here。 We have a two way set associative cache still with four lines。

And we want to go find our data。嗯。So how do， how do we go about doing that。

What's interesting here is when we did this， we only had to check one tag location。

But for a cache like this。The index is going to tell us。Which of the two sets it in。

 But it can either be in either of the two ways of， of these sets。

So we actually need to do a tag check against this tag and that tag and check the two valids。

And many caches can do this in parallel。 but that's how you can figure out。

 And it's possible it's in neither of those two。 And we have to say a cache miss。Okay， so let's。

 let's talk about when you need to go take things out of the cache。

 So let's talk about block replacement。 So we need to figure out what to go kick out of the cache。

 When you take a cash miss， you' go bring， bring some new data in。

So an important point here is in a direct map cache， this question makes no sense。

Because in direct map cache， you can only go to one location。

In set associative or fully associative caches， we need to make a decision。And。Hopefully。

 we only need to make this decision when a set becomes false。Because otherwise。

 we'll just choose the empty location in that set。 So if we have a two way set of substitute of cache and one of the。

Ways is full of data。 and the other one is just empty。 The bit is empty。

 We probably shouldn't even be looking at sort of different choices on how to replace things because there is an open spot to go put the data。

 We should go put the data there。Okay， so what， what are some。

Good block replacement policies or good cash replacement policies。 First one is random。

 You can just choose randomly out of a hat。Actually， it doesn't work so bad。It's easy to implement。

 You just like have some random linear feedback back shift register or something you just sort of choose a random number and。

 and you replace it。Not not so bad。We， now， now we start thinking about little put our thinking caps on。

 And we can start thinking about some better， better ways to go do this。 when can think about。

Least recently used。嗯。So。The idea behind this strategy is that you are trying to preserve temporal locality。

So if you've used some data recently。Theres a heuristic here that it's likely to be used again in a not too distant time axis。

 So if you go back to that sort of time versus address plot that we had in a time axis。

 we think that you know， temporal locality is something that happens relatively often。 So one。

 one really good strategy is to try to look at the least recently used。As the block2 get rid of。

So if something has not been used recently， we kick that out of the cache。Now。

 some problems with this is。This gets really hard to do。 Well， those two problems， one。

To implement appropriate lease recently used， every single load or store that happens to the cache needs to update the information。

Well， that's not great for power， but it's also not great because you basically need to have sort of。

Very fine grain tracking information on each cache line on every single cycle that doest load or restore。

So， you know， you need， you need some cache date that needs to be updated relatively often。

 P of people do that， though。 There's you know， if you have a least recently used piece of information。

 we have extra bit on each cache line。 You can think about just sort of flipping that back and forth and having one bit for that information。

 and everything single load in store actually sets that bit and lots of processors do that。

So what what starts to get hard here is when we try to go above two way caches。 So two way。

 you have sort of 1 B that can decide where， which is the most least recently used。

 If you start to have， let's say， an eight way set Associ cache。 you gonna to do true。

 least recently used， you have to somehow keep like time stamps for each different way。

You have to say， oh， well， this one was just recently accessed and， you know， you can timetamp it。

 You could try to sort of reorganize a list of of numbers in order。 And these。

 these these things start to get harder to do in hardware。 and especially， you know。

 sort of on the critical path of your processor。So a lot of times what people do is they have pseudo least recently used for higher associative caches。

 where you'll try to sort of keep maybe accurate information of the last two most recently used lines and the other ones you。

Do random or something like that。 Or there's some more complex things which we'll talk later in the class about。

嗯。Another one， first in， first out。So whatever gets brought into the cache first。

Sits in the cache for some period of time and then gets kicked out in the future。

 So you're sort of guaranteed that some piece of daily you bring will sit in your cache for some period of time。

 And this is a lot easier to implement in highly associative caches。

 But it's strictly not implementing these recently used。

 because if you sort of bring in a cache line。Let's say you have a fourway set Associative cash。

4 accesses later， it's at sort of the top of the list to get kicked out。

 But what's nice about this is you're guaranteed that'll sit in your cache for some period of time and won't just get sort of randomly kicked out。

 which like random has problems with。 finally here。Another， another acronym here。

 not most recently used。Let's think about that one for a second。 So we're gonna kick out something。

That is not。The most recently used block。 So we can sort of keep track， let's say the we have。

 some index into our cache。 If we have a four way cache。

 we can think of having sort  two bits that says， well。

 this line was the most recently used and the rest of them is sort of random。

 And we know we're not gonna be kicking out the。Most recently used。Cash。 so write strategies。

You're going to do a store。You got to know where you put the data。Important important thing here。

Caches have lots of different allocation policies and policies about whether you sort of keep the data or throw out the data in the different levels of the cache hierarchy when a store happens or right happens。

So let's， let's take a look at a couple， couple different choices here。

 So let's say you are doing a store。And you have a cache hit。 So it hits in your， your cache。

Should you go put that in main memory Also， if you， if you do a store and you。

Put every single store into your cache and into main memory。 if it's already in your cache。

Then as you point out， it uses bandwidth out to the main memory。So that can be a downside。

 There are some positives to this， though。When you go to evict the line。

 you don't have to write anything back to main memory。

 So you sort of are pre putting data into main memory。 So that's， that's a positive。

 You could also think about if you have a multi levelvel cache hierarchy。

Some levels of the hierarchy may， may may make sense to actually put it in sort of the next level out if you have enough bandwidth。

So this is actually a trade off。 As I said， computer architecture is all about trade offs。

 Neither of these is actually correct。 So the one is called right through。

 So right through means you put it in your cache。 If you get a cache hit and you put it in main memory。

Right back， cash means you just put it in your local cache。And when that block gets evicted。

 if it has dirty data， you have to go put it back in the main memory。🤧嗯。So that's。

 that's kind of the downsides and upsides there。 One。

 one thing you do need to do if you have right back， as we say here。

 is that you need to keep track of if the data is derby or not。

So if you go look at more complicated cash coherence protocols。

 sometimes you'll actually favor things like right through because right back gets really complicated when you have data that has to be invalidated and and sent out to other places。

 But if you knew the data was clean。I。e。 it has no dirty data。

 You never have to do it right back when an invalid comes in for a multi processor scenario。

So it's a tough， tough trade off there。 But generally sort of right back is considered to be more advanced and saves bandwidth。

 But there are trade offs there of why you might want to do the one or the other because right through is definitely simpler to design。

Okay， so that's our。And， and， oh， I did want to point out that， you know， you may not actually。

Go all the way out to the main memory。 So plenty of architectures。Have。Small L 1 caches。

 for instance， where you don't necessarily want to deal with invalidations coming in and complicatedlicate things happening。

Where you might do right through from your L1 to your L2， but then you want to save。

 let's say off chip bandwidth here。 So you write back out of your L2 to the Dr Ram。So that's。

 that is a pretty common sort of thing to do。 And as I was saying。

 the your motivation for this is if you have a multi processor system。And you have， let's say。

Invalidation requests。So let's say another processor wants that same cache line。

And the data is dirty here， but not not in the D。You would actually have to sort of reach down into the L1 cache if you have right back out of the L1 cache。

And that gets pretty complicated。Then， and especially it's complicated if your L1 cache is very tightly integrated into your CPU because it's on your pipeline。

 like it's in your main pipeline。 and you have to sort of。

Bubble the pipe somehow or have structural hazard for any invalidation that comes into that L1 cache。

 So typically， a lot of times， people try not to have。people consider right through caches。

 at least from the L1s， the L 2。But you definitely will save bandwidth for a。

L 2 sort of out to D Ram cache。 if you don't do right through every time。Okay， let's take a look at。

What happens on a cash miss？So， on a cache miss。We're doing a store or write to memory。

Do we need to put it in our cash at all？Well， choices， maybe yes， maybe no。

 There's no guarantee you don't have to put in your cash。A lot of times。

 and this comes down to heuristics here。 A lot of times， you'll actually do a store。

 and you may just not read that again。 So some architectures actually have。

Store instructions with locality hints。Or， or temporal locality hi saying。

 I'm doing this store or doing this right right now。

 And I'm planning not to read it again for a very long period of time。 Don't put it in my cache。Also。

 some things just decide not to do right allocate because or so no， no。

 I'll define these two things here。 No right allocate means you're doing a store or write to your cache。

 and you're not gonna pull the data into your cache。To do the merging there locally， if you will。

And you're not gonna actually store any day in your cash because you don't have to。

 You're just keeping a local copy of it。 You don't actually have to。

 you're not forced to keep a local copy。 You you can always send it out to your canonical main memory。

W allocate says， go fetch the data from memory。 merge it in the cache because usually the block line block size is longer than the amount of data you're writing。

 So merge it。And then probably either put it out to main memory if you're right through or just keep it in the cache。

So you， you， if you're， if you're right back。 So you can think about having these two policies and。

 and they both， they both have places。 some， sometimes people will。You know， typically。

 people try to do write allocate unless you have some locality information because data。

 let's say it's at the top of your stack in your processor or your in your sort of software stack。

 you're going to basically be writing and reading from that relatively often。

 So it makes sense to try to allocate that。The other thing I did want to point out is there is a heuristic sort of going on with this no right allocate that if you read that block。

 then it will get in your cache。 So maybe the first store that you do to the address won't allocate。

 but the next load you do will allocate， so。You't gonna miss that much by doing no right allocate。

 It's not like you've lost everything for forever。 It's just that that first right。 Oh。

 w I had to go out to the main memory system。 But the next load that I do from， let's say。

 my stack or some local variable will pull that line in anyway way。Okay。

 so some common combinations here。Right back with right allocate。

 So this is sort of the full blown solution that a lot of people do。

 This is kind of like the base high performance one。Right through and no right allocate is。

Kind of possible。 This is like the cheap one to build。

 You don't need any logic here to deal with no right allocate。 but all possible mixes are， are。

 are valid。

![](img/6b66ddaed552d86d921d644fc22e1f33_2.png)

![](img/6b66ddaed552d86d921d644fc22e1f33_3.png)