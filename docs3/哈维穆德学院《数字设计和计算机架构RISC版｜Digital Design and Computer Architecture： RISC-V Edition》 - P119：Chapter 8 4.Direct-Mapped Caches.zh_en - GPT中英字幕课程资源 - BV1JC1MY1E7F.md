# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P119：Chapter 8 4.Direct-Mapped Caches.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/da41226a4a926d2c4e30b073ce42a9c2_0.png)

First， talk about a direct map cache。 So here we have a system where we have 32。Bit addresses。

 And so we have addresses from 0。All the way up to all one。

 and we're just showing the word addresses。 so that's why the lower two bits are always zero。Right。

 so to hex zero all the way up to Hex， FF FF， F FFCc。That's the entire address space of our system。

But only a subset of these addresses of this data can be held in the cache。

And so what we do is we say， okay， well， basically we take the first eight。Blocks eight words here。1。

2，3，4，5，6，7，8。So those first eight words and those all map to the cache。

So if we just access those first eight words， word zero would go here， word one would go there， two。

 three， four， five， six， and seven。All those words would go there。And then， well。

 then we filled up our cash。And so。What happens is the next group of eight。

 they also map to that same。That same。You know， those same sets， the next one， word8。

We'd restart at the bottom and map two。The bottom word in the cache。The bottom set set0。M9。

 be in the next。The next set， 10 would be here， 11 and so forth and so multiple words in main memory can map to the cache。

And so if I accessed word zero。I'd pull it in， but then if I access word8 after that。

 it would knock out word zero and replace it with the data at address8。

And so this is called a direct map cache。These go directly to given set word zero goes here。

Word8 also goes here。And， and so forth。So here's a picture of the cache hardware for a direct map cache。

And so we start with some memory address。 Here's our 32 B memory address up here。And we can see that。

Because we're pulling in an entire word， we ignore address the bottom two bits of the address。

 we're going to pull in the entire word。🤢，And then the next。3 Bs。

 because we have eight entries or two to the three equals8 entries， right，2 to the three。

Equals 8 entries。 That's why we have three bits here。诶。Two to the three。

ll make that look a little bit better there。That's why we have three Bs here。

 That tells us what set is' going to be in。 So， for example， address 0。

 I won't put all the address bits， but。Address 0， is that address。And then if we were to access。

The value at word8 or in another words， 8 times 432。Addres 32。Loloading。The address。

 32 load word of 32。Like we said。That also maps the same set。Look at those next three bits。

And they would map to that same set。And then the remaining bits are what we call the tag。And the tag。

Identifies which address it actually is， right， So it's a tag for， for this address。Addres 32。

The tag is one。Here we can see the tag here。Is one。Whereas the tag for。Addres zero。Is。0。

And so that tag， we have to store it with the data because how do we know if in set zero。

 if we have right both address0 and address 32 map to that same set。

 and so the way we can differentiate or say， hey， what actual data is here， is it the form word 0。

 word 32， the worded address 32 you know， et ce， right？嗯。The way that we can tell is by the tag。

 we store both the data that's at that memory address， but we also store the tag。

And the last thing that's in there is what we call a valid bit。

 and so when a cache is cold or we haven't pulled any data into that cache yet。

The valid bits are all zero。 and we only set the valid bit once we pull in some data into that。

 into that cache。So the size of this is actually， you know what we use here is a small memory。

For caches， we use a small SRAM or static Ram， and each entry is 32 plus 27 plus one bit wide。

And so this is an8 by 1 plus 27 plus 32 bit SRAM。And so let's say we had。

 let's suppose we had address we had pulled in， we' had accessed address zero。

 we did a load word T200。It's not。Or0， let's do x 0。load word T2，0， x0。

Then we would be accessing address zero。Maybe that was the first time。 And there's some data。

 I'll just make up the data 0，1，2，3，4，5，6。诶。There's some data that we pull in that was at that memory address。

And we store the tag as well， so in this case， like we saw before。

 the tag for that address would be zero and would set the valid bit。

So now let's suppose after that that we have another load word。😊，This time。It's to。Word address 32。

And so remember， word're at us 32。Look's like this。dot dot， ignore these two bottom bits。

 the byte offset tells us which by if we were doing a load byte right for load word。

 we know those are always zero。And so what we do now is we look at this。And we say， oh， yep。

 that still goes to set。 right， This is set 0 here。 This mouth to set 0。

And so now we have to knock out what was here in our。Or cash。The data at memory address zero。

 we have to knock that out and we're going to rewrite the tag to develop it's already one so we could leave it that way。

And so the tag now is going to be0，0， blah， blah， blah，0，0，0，1， all0s and01， and datas。

 whatever was at that address， ABCD。1，2， three， four， making up some data。And we could go you know。

 access other sets as well if or we could load data into other sets as well。

And so if we did another load word， let's suppose we had another load word after this。😊。

After this load word right here。we had a third load word， and it was also to。Addres 32。

The memory address is sent by the processor。And so the tag would be all zeros，t dot dot and a one。

 So it would be all zeros。 And it would come and say， okay， where am I going read it from， Oh。

 I want to read it from set 0。So go over here， read from set zero， and it' would check and say， hey。

 does the tag match？The tag I'm requesting。We use an a quality comparator it says yep， one。

 is that valid， yes it is great， then we have a hit and the data。

 the read data in this case can be sent to the processor。But if on the other hand。

 instead of that next access being a load word to that same address。

Let's suppose it had been a load word to address0 or some other address。' save address 0。

Then the tag would have been all zeros， right address zero has zeros in the tag。

 it would come in and read what's in the cache。It doesn't match anymore we' get a zero out of that quality comparator。

 say no not equal， it is valid， right this would still be a one， but it would say no， no dice。

 that was not a hit and so cannot use the data that we've read from the cache instead to go to the next level in the hierarchy to get the data and would pull that data then into the cache。

So here's another example with some actual risk five assembly code。Let's suppose that we have here。

 We have a some accesses。 Let's look at our load words。We have three load words to address for。

 Let's see what S1 is。 Yeah， S1 is 0。 So address 4。Here S1 is being set or given the value zero。

 and then we have a load from address 4。Followed by address 12。Followed by address 8。

And so let's see what happens。 So address 4 is this one showing。Yeah。

 this is showing address for right here so the first access this load word。

 it would go in the first time through the loop。It's going to access that。

 let's say the cash is cold order in other words， holding no data。

It's going to say it's going to go look at the set。 while those three bits after the two zeros。

Mount to set one。And it wouldn't find that data there， but it would pull it in。

So then on the next axis。 So after we get address 4， we'll access address 12。 So 12 looks like this。

And then all zeros up here。And so this would map to set。3。I' go to set three for this one。

And it would pull in whatever is that memory address。Heack C or 12。And then for the last one。

 last memory access， it would also be a miss， Ca is cold， this would be address 8。Or for that。

 address 8 would be。1，0，0， zero with a bunch of zeros up here。

Again we look at our set bits that would map to set20，10。And so then it would miss。

 but it would pull in。That。Data at memoryory address 8。

So then the next time through the loop after these load words have been processed or been executed once。

Then we're going to go back to the loop。It's going to happen。5，4，3，2，1。F times， right。

 And so it's going to say S0 is5。 A is it equal to zero nope。Right yet。Decrmented by one。 Now。

 S 0 is4 and keep going through。 So this will execute five times。 That loop will execute five times。

 The next time， So the zero iteration， we get to pull in all the data。 But the next time goes to say。

 hey， let's see address 4。Is at set one， it goes and looks at set one and says yep。

There my tag matches， are the rest of us older zeros。Or the tag check the tag。

 yet those match the tag that I'm requesting and the data in there is valid， awesome。

Give me that data I one process clock cycle instead of having to pull it in for a main memory。

Same thing with address 12 goes to。Set 3。2 step three finds that data hit right so every and then same thing with address8。

It goes to set two。And gets the data。So all the rest of the accesses are hits。

So we had three misses and how many total axises， well， five iterations of the salte。

 five times three is 15。 so we had three misses。The first three。

And then we have 15 total memory accesses in this case， they're all loads， but。15 accesses。

Our miss rate is three out of 15 or in other words， one fifth or 20%。

So this is a case of temporal locality， because we access these。

Memory addresses recently were likely to access them again， and in fact in this loop。

 we did access them again repeatedly for an additional four times that loop。

 four times to read the loop。And these are an example of compulsory misses because the cache was cold。

 so the first time we access any data。We're going to get a compulsory miss。

 in other words where you know we are compelled to or we have to miss in the cash the first three times。

So here's an example code for conflict miss so conflict miss is where we're accessing data that maps to the same set and so it kicks each other。

 you know kicks the data out of the。Out of the cash。So again。

 we're going to execute this loop five times。And so the first time we access address4 again。

 is our address4。It looks at the set bits and it says， oh， that maps to set one， this is address Xx4。

And looks at those set beds and says， okay， great， I will。Do that and so we look at address Hx 4。

 pulls that into cache it missed， but compulsory miss， no problem。

And then the next time it's going to go and say， okay， well， now let's access the next one。

And we'll get next addresses。Hex 24。X24， so this is0，0，0， and lots of zeros up here。G0。1，0，2。four。

And we look at those set bits。The bottom two， next three are the set bits。

 and those are map 2 set one as well。 unfortunately。 And so now we kick out。This memory oh。

 this data from that memory address， address 4， and we make the tag equal to0，0， blah， blah， blah。

 one， and we pull in。Whatever data is at memory address， hex 24。That's fine right。

 that was a conflict well actually that would have been compulsory but the next ones now we go back through the loop。

😊，Gos to restart this loop， jump loop， goes back here， tries to access address 4 again。 Look。

 checks the tag。 Is that the same as my tag up here。All， all zeros。0，0， all zeros。 It's not the same。

 Nope， wrong data is in there。 In fact， Hex 24 is in there。 So it's going to kick that data out。

 Hex 2，4 and。Bring its own data in， so hex24 is gone， you pull back in Hex4。But then Hex 24 says。

 hey， I actually you write this next load word says I won add memory address Hex 24。

 it goes and checks， text itss tag。those the tag bits looks and compares and says， hey。

 are those equal？Athetic quality comparator。There equal note。Not again。

And so then is going to kick out。Ex scores data。And so forth。

 so this is called a conflictness because they mapped the same set and so we're going to get。

 in this case， we have two memory accesses each time each iteration through the loop。

 and we have five iterations of the loop。And so we have。The number of accesses。

 the total memory accesses。Is。Two times 5。and。And the number of misses we have is 10。

 every single one of those memory accesses miss in the cache because of the conflict。

Because they map the same set。And so the mis rate is 10 out of 10 or 100%。And again。

 these are because this type of miss and the cash is called a conflict miss。



![](img/da41226a4a926d2c4e30b073ce42a9c2_2.png)