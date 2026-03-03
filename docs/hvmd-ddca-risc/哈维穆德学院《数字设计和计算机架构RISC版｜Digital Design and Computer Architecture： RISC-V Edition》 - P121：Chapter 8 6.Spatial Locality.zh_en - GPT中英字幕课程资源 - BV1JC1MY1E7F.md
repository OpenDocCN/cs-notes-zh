# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P121：Chapter 8 6.Spatial Locality.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/041dc9174d7bcfb3216e9f9267f042de_0.png)

So far we've only talked about temporal locality， so let's now talk about spatial locality。

Spacial locality is when we pull in more than just the word that we're accessing so in the prior examples we were pulling in just one word at a time to the cache。

 but now even though we're accessing still a single word， we're going to pull in multiple words。

For every memory access。So。😊，诶。We're going to increase the block size in our prior samples。

 the block size was just one word， now we're going to make it have a block size of four words。Okay。

 our capacity is still eight words， and so now we can only have two sets。

 so set zero and set one here。And so we're only going to have a single set bit。

 log base two of two is just one。But now we have this new field in our memory address called a block Off。

And because our block size is four， we're going to have two bits and that block offset。

 had our block size been larger， like eight words， would have log B two of eight is three bits or 16 words。

 and we would have had four bits in the block offset。

But we have two bits here because our block size is fours。

 and so that will tell us which word within the block do we actually want to access？Okay。

 so after we read the data。诶。We're going to choose which which word within that block we want。

 so it looks almost like an assoative cache， but it's not this is a single block but the block is four words wide。

Instead of just one word， but it's still just a single way right for a direct map cache。

 we just have one way in that in that。And that set。

And so the number of blocks that we can store is just the capacity over the block size。

8 over four is two， so we just have two blocks。It is， you know， one block。Top here。

 and then we have our second block。There。And so we're going to use that block offset to tell us which board we want。

 let's suppose we have some address here。Yeah， just kind of。Slowly making it up。

Let's suppose we had that one and we'll go ahead and do。Once here。嗯。Let's just do them in order here。

So word zero， word at address zero， word at address。Or。Orre at address 8。We're to address8。

And the word。An address。12，4 C。Okay， so still we ignore our bite offset。

 this will tell us which bite within the word we want， we're not going to worry about low bys。诶。

And so this is our still our bite offset。More those。The next。Bits are our block offset。

 So these two of those bits that tells us which。Which word within the block that we want。

 and in this case， we only have a single。Set bit， this next one tells us which set it's going to be in。

 So these， these addresses can address Hex 0， Hex 1。Excuse me， Hx 4。X8 and he C。

These all mapped the same set， you can see they all maps set zero。嗯。But。

The block offset that's different。So no matter which one of those I access。

 I'm going to pull in that entire block。 So address0。For。8， and see， I'm not drawing the data。

 I'm just drawing the memory addresses。 The data， these， each of these addresses would get pulled in。

And then I would use the rest of the bits。第。So then the remaining bits would be the tag or tag bits or everything else。

Our tagbits， and that tag is the same， you'll notice。For all those， all0 in this case。

 And we'd make that valid。 So if I let say I did an access to address 8， 8。

 I did something like this。 I did a load word。T0， making up an address there， Hex 8。0。

If I access that word， So or this word at address 0， I'd pull in not only。The word at address 8。

 that also pull in the words and addresses。0，4。And see。So it pulled in that entire block。

And now to tell which  one I actually want， I'm going to use this block offset。

It's here to tell me which word I want Project 8， we go and say， okay， I want this。You know。

 this word10， that's the one I actually want。If later， I didn't access to。So after this。

 if I didn't access to instead of word8。We change it and we say， well now the next。Access comes to。

You know， let's say he C。Already in the cache。 And now， instead of accessing word 8 here。

 would look at the block offset。He C is this address here。

Block offset again are these these two bits here。 We look at that block offset。And would say， okay。

I want to address Hex C。Within that block。But the nice thing is that first access to address 4 pulled in that entire block。

 and so when the next access came to that block， he C didn't have to pull up for memory。

 it was already there because of spatial locality。So here's another example， some other address here。

 hex 8000。009 c。 And so this one， again， we ignore the bite offset。And we look at the set。

 So this maps to set one。And in this case。The word that we actually want is up here。

 right the block offset set is 11 that tells me which word I actually want， Hex 9 c。

 but also pulled in Hex 8， all zeros，9，8。Here，9，4。And 9，0。So if another access came in。

 maybe after this load word came into hex eight all zeros， nine， zero instead。The block off。

 I would say0，0 here and would pull。That data that I hadn't even accessed before。

 but because of spatial locality， it's there and we'll pull out that data from our cache。

So here's an example showing the advantage of spatial locality。So let's look at these addresses。

 These are hex4，12 and C。 we actually looked at those， I mean， excuse not Hex 12， but。4，8。

 and I said T C， but it's written as 12， same thing。And so remember that these addresses are。B。eight。

And see。And so they all mapped the same set。And and we can look at our block offset。

 it's our block offset to tell us which word we actually wanted。So the first access to address 4。

 Here's our first address here。 This is Hex 4。It's a miss and if it's a cold cache。

 if it wasn't there already。But the processor then goes and pulls in to the cache。Address 4。

 but also the neighboring addresses0，8 and C。It pulls in that entire block。And so for address。

 the memory at address4 is what we really wanted， we're going to get that， but now。

In this next access， access to 12， instead of being amiss。

 which it would have been in a direct and I am in a cache with only one word block size。

Now it's going to go and say， oh， hit， I already pulled that in， I thought you might need it。Al。

 so it pulls that in。 You look at address 12 and see that the block offset。Is  one1。

And so now it pulls out using that block offset as a select line for that multiplexer。

 it pulleds out。That data that it needs， which was already， you know magically， well。

 not really magic， but because of spatial caity there。So this is a mess。

 and then this one's is a hit。And this next one's also a hit because of spatial locality。

 There it is ready to go， uses the。Block offset X 10。Just select that out of the cache。And so this。

This loop。Go executes five times， you have three accesses。Per。Loop iteration of five times three。

 the number of total accesses or load words。Is。Five times three。6， what a 5。Five times3 equals 15。

 the number of misses， well， just that first one was a miss。We have just a single miss。

So the number of misses is just one。And so our miss rate is one out of 15。

And so you can see the advantage of spatial locality。So， again。

 these larger block sizes reduce compulsory misses by。Using spatial caity。

And access to a given address is being made likely nearby addresses will also be accessed soon。

So as a review， the type of misses that we have are compulsory misses。

 this is the first time datas accessed， we're compelled to pull that into the cache。

The second type is a capacityist， the cache is too small to hold all the data of interest。

 and the third is conflict where data that we need maps the same location， the cache。

 and so they kind of knock each other out of the cache。

Miss penaltyal is a new term and it's the time it takes to retrieve a block from the lower level of the hierarchy。

 so as our block size gets larger it's going to take typically longer to ask to pull that into that level of the hierarchy。



![](img/041dc9174d7bcfb3216e9f9267f042de_2.png)

So here's a recap of cash organization capacity， capital C， B size， lowercase B。

 number of blocks in cash， capital B， capital C over B， number of blocks of set。

 capital N and number of sets is the number of blocks over B。Number of blocks in the set。

 or in other words， the number of ways。So this is， we also call this simply。Or up wayss。

So for direct map cache， the number of ways is just one。

 We only have one way in that set where we can store that data。And the number of sets is capital B。

B over n is just be over1。And for an N set Asocciative cache， again。

 simply call this an Associative cache。😊，We have at least you know two ways and less than。

The number of。Blocks。And the number of sets is then B over N for fully sociative CA cache。

 the number of ways is equal to the number of blocks， and we have a single set。

So the number of ways for a fully Associative cash depends on the number of blocks in that given cache。

 so if it had 16 blocks， a 16 way Associative cash is also called a fully Associative cache。

 if it had four blocks， a four way Associative cash in that given example would be called also called a fully Asciative cash。

😊。

![](img/041dc9174d7bcfb3216e9f9267f042de_4.png)