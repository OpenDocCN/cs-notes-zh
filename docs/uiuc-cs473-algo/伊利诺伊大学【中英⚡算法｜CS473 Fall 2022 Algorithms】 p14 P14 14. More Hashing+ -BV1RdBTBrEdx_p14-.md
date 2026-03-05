# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p14 P14 14. More Hashing+ -BV1RdBTBrEdx_p14-

这个到。Nice， I got， I saw the songs in 46 right now and they。



![](img/2d235ef841744112ed6a14425bdf144a_1.png)

哪二R。average47 we going to 6 feet and'。对没有，之想钱。85。I wantさ。86。There。な。对。我建议他。嗯 thank you。啊。嗯对对对。😊，啊。Oh。

Okay， so let's go ahead and get started， thanks everybody for coming。嗯诶。

Quick administrative thing I was really hoping that we'd be able to have the exams done by tomorrow it's looking more and more likely that we're going to be finishing up over the weekend。

🤢，But Monday Monday morning is a hard deadline for us。

So the Ts might may not be getting much sleep over the weekend。

 but we're making progress just not everything is going to be done in time for me to like make an announcement about here's here's the distribution of grades and what they mean and so on I'll talk about。

The exam scores。At the beginning of class on Tuesday。

U and there'll be a post on the course web page and on Ed u just explaining what what the situation is for everybody because I know a lot of people are。

A lot of people have expressed concern， I don't actually think。Panic is the right response。You know。

 generally， the exam seems to be going pretty well。Despite problem three。

So let's wait until we actually have the data in front of us。To start。Worrying about anything。Okay。

 so I want to continue。Our discussion of hashing。嗯。This is。

Some the what I'm going to be talking about today is somewhat more advanced in terms of the analysis than the hashing stuff that we've seen previously。

 mostly at the end of the day， what I want to convince you is。😡，嗯。

You may not gr the analysis by the time I'm done， but nevertheless， you should be able to implement。

😡，An open address hash table that has provably good performance so the underlying algorithms that I'm analyzing are not terribly complicated。

 it's just that the interactions between different items in the hash table are more complicated and that makes the analysis more complicated。

So to be clear。When you use hashing in your homeworks， when you use hashing in your exams。

Provided that the things you hash have constant size。😡，No hashing like long strings in constant time。

 that's magic， so you can't do magic。But provided the things that you're hashing in constant have constant size。

 you can assume for purposes of homeworks and exams。

Looking something up in a hash table takes constant time。Inserting something in expected time。

 inserting something into a hash table takes constant expected time。

 deleting something from a hash table takes constant expected time。Now。

 if you really want to be careful， you also need to make sure that the things that you're hashing consist of a finite number of bits。

 so for in a problem setting where you're dealing with a bunch of numbers which may or may not be integers。

😡，now you're kind of mixing two kinds of abstraction one， I don't care what the numbers are。

 I just assume I can do constant time arithmetic and then hashing。

 which actually requires a stronger assumption about the data representation。😡。

Generally speaking we're not going to get into that so as long as you're hashing single things a single edge and a graph。

 a single node in a graph， you know a single number that you've been given a single character in a string that sort of thing you could just assume that hashing works in constant time using a linear amount of space as a function of the number of items you're storing。

😡，So that's what you need for your homeworks and exams。😡，In particular。

 all the details I'm showing you here。😡，This is just for your enlightenment。

 this is not going to show up。😡，In midterm two problem three。Okay。All right， so。

Last time we talked about。Chained hash tables。Where the idea is。Instead of storing a single item。

In every slot in the hash table。You store a list of all of the items that hash to that slot in the hash table or some kind of data structure storing that list。

😡，And in particular， if you choose。😡，The right hash functions。😡，And they're using a linked list。

We use an appropriately sized secondary hash table。😡，At every slot in the primary hash table。

So in Python， what's called a list of lists。嗯。Then we can guarantee。Constant look up time。

Constant expected insertion time， constant expected deletion time。系。You need。What's called。嗯。

The universal hashing function。Which here the assumption is that the probability of getting a collision for any two items。

Is at most one over the table size。But provided that the hash functions that you use both at the primary hash level and in each of the secondary hash tables provided those functions are drawn from a universal family of hash functions。

Then there will be， and you set the sizes of the secondary hash tables the right way。

 there'll be no collisions in the secondary tables。😡，And therefore。

 you need to look up the primary hash value， you look up the secondary hash value。

 and there is the item if it's in the table at all。😡，嗯。嗯。😊，So。This guarantees。Constantine lookup。Oh。

Constant expected time insertion。Or deletion。Not counting rebuilds。

 so if I really want to take into account rebuilds。

 I need to play the usual doubling having game with dynamic arrays and that that makes these amortized time bounds in addition to being expected time bounds。

嗯。In short， provided you choose the right hash functions， chain hashing works。😡。

What I want to talk about today。😡，Is。What's called open address hashing， this is your hash table。

This is the entire data structure。😡，The hash table is a。An array， a contiguous block of memory。

Nothing else。But we still need to be able to resolve collisions。😡。

So the way that this is normally done。Or the the。But。😡。

High level description of the way hashing works in this context is if the first hash value doesn't work。

Try a second hash function。If that doesn't work， try a third hash function。

And so on so what you'll get is something like。嗯。Or I goes from。Let's say zero to infinity。Um， if。

The table at the ice hash value。I is empty。Assigning that value to。Next to that slot in return。

So I'm imagining here that I don't just have one hash function， I have a sequence of hash functions。

😡，Okay now going to infinity obviously we don't really want to do that。

 so what i'm going to do instead is I'm only going to try and different hash functions and if。😡。

They all fail， then I'm going to report that the hash table is full。

 so my insertion is going to fail in this case。Although really。

 if you just keep track of the size of the table， you'll know when it's full。😡，嗯。

And then I'm going to make。😡，Again， just for very， very high level。Abstraction， I'm going to assume。

The sequence， H0 x， H1 x。Up through H of n minus1 x。Is a permutation。

Of the indices 01 up through m minus1。Okay， so。One way to think about how this works is。😡。

My hash function doesn't simply return one index into the table。😡，It returns an ordering。😡。

Of all of the indices in the table。And I will probe the table in that order。😡。

Until I find a slot where I can put the item I want to wins。Or if I'm doing the search。😡。

It gives me an ordering for the slots in the table。

Probe the table in that order until I either find the item I'm looking for， which means it's there。

 or I find an empty slot， which means that item is nowhere in the table。😡，The like music that。

二号 doing the same。I'm declaring this to be one of the rules， you have to design your hash functions。

😡，So that you get a permutation。And。Oh， sorry， that should be。Sorry。And that should be un。

M is the size of the table， right？嗯。嗯。So。😡，In reality。

The way this is usually implemented is something called linear probn。H of I， H sub I of x。

Is h sub zero of x plus I。Modem。ok。嗯。So the permutation。Is completely specified by where it begins。

But from then on， it just proceeds to the indices in order， so if have a table of size 12。

 and the zero hash value is 10， then the probe sequence is 10，110，1，2，3，4，56， up to nine。😡，Okay。

This is what's usually implemented， this is what in fact the analysis I'm going to show you slightly extended because things get a bit more complicated will actually be provably efficient so this works provided you have a good enough hash function for H0。

😡，But doing the analysis for linear probing。😡，Turns out to be a little bit。😡，A little bit nasty。

 so I'm going to do something that is a little bit less well known。😡。

But actually works better in practice。So I'm going to assume that my table size is a power of two。

 so again， like last time a couple of the hash functions I was talking about。😡。

The hash value is an L bit label。😡，Okay， so when I'm growing and shrinking my tables。

 I'm always doubling and having instead of doing anything more interesting。And then。

 instead of adding。The integer eye。To the initial hash value to get the ice hash value。😡。

I'm going to do a bit wise exclusive work。ok。Now， this is funky。啊啱。See roughly how does this work。

 so I'm assuming again。My table is a parallel two。And so let's suppose。I've got， you know hell'。

And my initial hash function。Gives me the string 0101， okay， so this is H0 of x。

Right so I'm going to look at slot 10 in the hash table because that's 10 in binary。

 then H1 of x is going to be 01011。I'm exclusive oring with the binary value for one。H2 of x is01000。

I'm exclusive oing with the binary value for two。H3 of x is01001， H4 of x is01，1，1，0， and so on。系。No。

Why would this be a good idea Okay， so a couple of things here。😡，嗯。

Let's suppose my initial hash value is。Well， that's not 10， so 10 is somewhere over here。嗯。

So address spaces。You can kind of think of them as divided up into blocks， various sizes。

 various powers of two。😡，If you remember anything from。

233 or 340 or where you're talking about different levels of memory or different levels of address space。

When you're allocating memory， you kind of want to line it up along addresses that end with a bunch of zeros。

😡，系。Um， and generally when you're doing， when you're doing mallet， for example。

 you you want to have these things nest nicely。😡，And part of the reason why you want to end with a bunch of zeros is because of the way multilel memory works in modern CPUs。

 cache lines are mapped to blocks in the address space。😡。

Whose size is some power of two and larger and deeper and deeper levels of the cache？😡，Are。

Associated with larger blocks， but still always a power of two that ends with a bunch of zeros。

So the interesting thing that happens with binary probing。😡，Is。

At every level of cash that you can imagine。😡，I'm going to explore completely a block of size2 to the K。

Before I go on to some other block。So I'm considering all addresses that have the same first two bits。

😡，And then in the first eight probes， I'm going to consider all addresses that have the same leading bit。

😡，So what this means is。😡，You're going to play very nearly nice with caches。😡，If you do this。

You load in a table and you're going to explore that page completely before you load something else into the cache。

😡，Linear probing isn't quite that nice because might be you might have a hash value that's very close to a page boundary and just a few probes will cause you to have another cash failure。

😡，Okay。Um， so。From the point of view of intuition， it's a little bit weird。

Because it's just a lot easier to go， okay， if I'm doing this by hand。

 I put my finger here and I go oh it's empty， put it there。

 That's really very intuitive and something that a human being would do was this weirdness。

 it's like， oh'm doing this weird jumping around。using some binary counter in the background。

 that's not something normally a human would do， so it feels a bit unnatural。

 but it's actually better performance in practice than linear probing。

This turns out to be easier to analyze again， because I've got this nested blocks of powers of two going on。

😡，Yeah。😊，And so in this example， I was looking at cake equals。😡，2。So sorry， I should have。

 I drew the box in the wrong place， excuse me。I explored all。

All four addresses that had the same top three bits。

 so in that case I'm looking at a block of size two to the two。

Then I'll explore whatever the block is containing the initial hash value of size8。

 then I'll explore the block containing the hash value of size 16， so the exploration。😡。

Kind of naturally does this hierarchical thing。That at every level。

Lings up with where you would expect cash boundaries， page boundaries to be。Okay。Now。

If you just want。ABack of the envelope， well， the passion is random， so fine analysis often what is。

Reposed instead is H0 of x， H1 of x， et cetera。Is a random。For mutation。

Of the integer zero threat and minus one and independently random if I if I really want to be。Oh。

Every permutation is equally likely。Okay， so。Every。😔，Or mutation。Has。

Probability one over M factorial。This is sometimes called the strong uniform hashing assumption。😡。

Because the permutation is generated uniformly at random from the set of all possible permutations。

Okay。嗯。So let me first do an analysis of the expected number of probes that you would need。😡。

Under this ridiculous assumption。嗯。So let me write T of n comma M， this is the number of probes。

That I need。To let's say， insert。The8 item。Into a。Table of size。And。

M so n is always the size of my set that I'm storing and M is always the amount of space I've using。

😡，そ这个。Okay， so。I'm interested in the expected time。For。This function。Well。

 I'm always going to do at least one pro。😡，I'm always going to generate the initial hash value that'll cost me one and then well because my permutation。

 every permutation is equally likely， in particular H0。

 the initial hash value is uniformly distributed， it's equally likely to be anything。😡，And。

So the probability that I'm going to get。😡，A collision is。

The number of occupied items divided by the number of slots number of occupied slots divided by the number of slots this is the probability of a collision I know really it should be n minus one but。

😡，There's a less than3 equal at the beginning。And now。

Because my later probes are defining a permutation of the slots in the table。😡。

I'm going to do something weird， I'm just going to pretend that that initial slot in the table that I tried to hash into and failed doesn't exist。

😡，I'm just going to imagine it vanished from the table entirely， yeah。😡，开始。The binary。

Because I want this nesting。Behavior。好的。Well， normal or you lose information。

 if you have the zero bits， they don't do anything。So if your initial hash value happened to be zero。

😡，Zero or anything would be zero and you just probe at the same place the binary probing guarantees that you actually get a permutation of the addresses。

Yeah。Okay。So if I get a collision， I'm going to imagine that initial slot in the hash table just doesn't exist now my remaining probes define a random permutation of the remaining slots。

😡，If I take a deck of cards， I shuffle it， I pull out the ace of spades。

 the other 51 cards are still uniformly shuffled。😡。

So this means I am now trying to insert something into a hash table of size M minus1。😡。

That was filled by uniform hashing， and I'm trying to insert the n minus one item。😡，Into that table。

So I get a weird。Recurrence like this。嗯。诶。You can verify this by induction。

 this is going to be the solution to this is M over M minus n。So by the induction hypothesis。

 that expression on the right， the expected value， that's M minus1 divided IIM minus n。

 and then you do some mathth。😡，嗯。Now。Typically。So notice in particular。

 this is a positive value because the number of items that I'm storing in my table is always should be less than the size of the table。

😡，So the denominator there， M minus n is。Greater than zero。

I'm going to assume for purposes of analysis throughout this lecture。

That I have a load factor of a half。😡，My table is exactly halfful。😡。

There'sNothing's really special about the number two there。

 but I just want to fix something concrete go。That's the probability that you hit an item in the table that was already occupied。

😡，There are M slots in the table and about eight of them are occupied。

that if I'm really being careful， that should be n minus1。

 and then there should be a minus one in the denominator。So get that assumption。That's two。

So if my table is exactly halfful。😡，Then not surprisingly。

I expect to do two probes before I find an empty spot。😡，Right， and more generally。

 it gets something that looks like one minus one over alpha where alpha is this load factor。

 what fraction of the table is full？系。Now。This is just somehow， if I can magically。

Produce random permutations constant of end things in constantsine， the note this doesn't work。

This is reasonable back of the envelope computation， it's reasonable like， yeah。😡。

If you don't really care too much about guarantees， this says， yeah， it'll probably work。😡。

And this is reasonable if you just want to implement something quick and dirty。

 if you want to do open address hashing， just keep your tables about half full。Um。

But you really can't do this uniform permutation thing in practice。Okay。So。Instead。

 I'm going to go back to。Binary probing。And ultimately。

 what I'm going to prove is provided your hash tables are sufficiently nice。😡。

The expected number of probes that you need to do will be a constant。Right。嗯。So。

In order to do the analysis。I'm going to。Be fairly conservative at a few points。So。

I'm not actually going to track。😡，The exact。Sequence of probes。Instead， what I'm going to do。

Is sort of look at it from a 10000 point， 10，000 foot view and say what does binary probing do。

 it says， well， try to put it into the slot given by the hash value if that doesn't work。😡。

Try to put it in that slot， exclusive War1。😡，One of its neighbors。If that doesn't work。

 that means a block of size two was full。😡，Try to put it in the sibling block of size two。😡。

If that's full， try to put it in the next sibling block of size four， if that's full。

 try to put it in the sibling block of size8， if that's full。

 try to put it in the sibling block of size 16。So I'm going to write。Bk of x， this is the block。😡。

Of length。Two to decay K。Mataining。My initial hash value。X。Of X。Okay， so。Basically。

 B0 of k is just that one address。😡，B1 of K is that one address and its sibling。😡。

B2 of k is a block of size four and so on。And so， the。嗯。The algorithm is going to look like this。

Okay goes from zero to log M。If the block of size K of x。Is not full。Put X into。P k of x and return。

And I know that this is eventually going to succeed because I'm assuming that。

My table is only half full so that I know the block of size log n， that's the whole the whole table。

 I know that's not full。😡，Only half。Right。So I' being very vague here in line three of this algorithm。

 what I mean is scan B sub k of x in some order and find an empty spot and put exit to it。😡。

Now I know in reality， the binary probing algorithm is using a very specific permutation to do that probe。

😡，But for purposes of analysis， I'm just going to say， oh。

 if you kick me up to the point where I need to think about a block of size 128， okay。

 I'm just going to scan the entire block of 128 in some weird order。😡。

And that's clearly going to upper bound the amount of work I have to do in the real algorithm。😡，嗯对。嗯。

So if I do this now。嗯。The running time。Is going to be big O of the size。Of the。Largest。Fuall。What。

Containing eggs。Okay interpret this as one if the initial hash value of x is empty and I can just put it there so if I find that the block of size 128 is full block of 256 isn't full well the way I discovered that it wasn't full is I scan the entire block so I needed to use about 256 plus 128 plus 64 nice descending geometric series that's at most。

512， that's at most four times the size of the largest full block that I found。Okay， so。

This is really the thing that we want。😡，To。Analy。What is the expected value of the largest full block？

😡，Containing。I guess I should say containing H0 of x。And the answer is， in the end。

 if assuming a hash value is nice， the expected value of this expression is constant。嗯。All right。

That's the intuition behind the sort of high level how we're going to do。😡。

The analysis is so we're going to look at this。Much looser much less specified algorithm becausem in the end I don't really care when I get up to larger sizes of blocks I've already done a bunch of work to get to that point so I can waste a constant factor。

😡，Just probing the entire block。Okay。So let me。Let me write down a few definitions and a few notations。

I'm going to say that。Bk of x is full。If。All two of the case slots。Are occupied。

And I'm going to write F of k to be the probability that this block。Is full。对。Um。Now。

 one of the things that I am going to be assuming here is that the initial hash value is uniformly random。

 and one of the consequences of that is that FK doesn't actually depend on X at all。

The probability of each block being full only depends on the size of that block。😡，Now。

 just a little more subtly。Let's think about what it means for a block to be full。

 so if I'm doing this binary probing thing and I discover that all eight of these cells have been filled in already。

😡，Now there are a couple of different ways that can happen。

 one is that I got eight as I was building the hash table。

 I got eight different values that all hashed into that block。😡，The binary probing。

Algorithm will guarantee that all eight of those will actually fit into the block before I look at larger blocks。

😡，But that's not the only way that things can get into that block。It's possible that。😡。

The next eight slots over。Were full， and I tried to put something else into them。

In which case the binary programming will overflow into this block of size 8。

So it might be that my sibling。😡，Is full。嗯。And again。

 that could be full because maybe the sibling of my parent is full。so I need a。

It's really kind of difficult to keep track of all the different ways that a block can fill up。😡。

So I want to relate this somehow to a bunch of hash values landed in this block。😡，Right。

 which is a much simpler thing， so I'm going to say that Bk of x is popular。😡，If at。Mst。

Let me actually， let me write it this way if the number of items y in my table such that H0 of y is inside this block。

This is at least to the K。So let's think about this that means。If you were doing chained hash tables。

 it would mean at least two to the K things hashed into this block。😡。

And some of it might have ever flowed， it might have been more， in which case I got longer chains。Um。

So。If a block is popular。Then a block is definitely full。

If I have eight things in my input in my set hashed into this block of size eight。😡。

And possibly some other things got overflowed into that block of size8。

 that block of size eight is full。😡，But fold does not imply popular。😡。

You can be fool because your brother was super popular。Or your uncle was super super popular。

What the right way to say this？Is。If you're full， say just I'm going to say BK is full。

 that implies either that BK was popular。Or。嗯。Sorry。Either a sibling or an uncle。Of。BK。Is popular。诶y。

😊，So maybe my sibling is popular， maybe my parents' sibling is popular。

 maybe my grandparents's sibling is popular。😡，Unfortunately。

 I don't know of a good gender neutral version of uncle。嗯。but it means， you know。

 if assuming all the blocks are male， my brother， my uncle， my grand uncle， my great grand unclecle。

 my great great grand unclecle， one of those blocks was popular。

 so for this block of size eight maybe that's popular maybe my sibling was popular， maybe my uncle。😡。

Just size 16 was popular， maybe my grandd uncle was popular。And together。

The block and all of its uncles cover the entire table。Okay。

 but what it's saying is somewhere in there， there's the popular block。

So now if I write E sub K to be the probability of sorry。😡，E of K is the probability that this block。

Is popular。What I end up with is this inequality。嗯。

The probability that a block is full is at most the probability that that block is popular plus。

The probability over all larger blocks。Sizes that one block of that size is popular。Now， in the end。

E sub K is going to be some inverse exponential function in k it's going to be like2 to the minus k and so this sum over here on left is going to telescope be nice geometric series。

😡，SoAnd so F of K is also going to turn out to be some inverse exponential function。

 so at the end when the smoke clears we'll discover f of k is within a constant factor of P of k。

But I don't want to assume that yet， so I'm just going to set this up as a。嗯。

As something we'll need to refer back to later。And now what I really want to think about is。😡。

What's the probability that a block of a certain size is popular？😡，Yes。Without any award。

 you will still be put。Yes， popular means if there were no overflow chaining or anything no linear probing。

 just regular chaining。😡，Then。You would be that block would be full。Yeah。Okay， so。

The block of size K is full。😡，That implies。That either that block is popular or one of its uncles is popular。

Its uncles have size。Going from K up to logU。😡，嗯。So。This is the quantity that I really care about。😡。

What's the probability that a block is full？T qualitative。

I'm considering my sibling to be one of my uncles， the zero level uncle。It won't matter in the end。

Okay。So。Let's。We need。To。Understand。U。That's okay。Okay。So let me write。

I to stick to be somewhat consistent capital y this is the set of all elements y in my in my input where H zero of y is in。

Bk of x so。I'm going to， you know， for now I'm just going to fix k。

Som I don't want to carry those subscripts around， why is some set？Okay。Um， actually， why is。

 I'm going to let Y be the number of items in that set， not the set itself。ok。😊，So。F of K is。

The probability that capital Y is at least2 to the K。All right， so。

Remember that at the very beginning。I said M is equal to 2 n。

 this is what we're going to assume throughout the analysis。So。What's the expected value of y？Now。

 I want to assume to answer this question that H0 is uniform。😡。

Every initial hash value is equally likely， right？Oh。Okay， so what this means is I took my N items。😡。

For each one， I generated a random number between0 and minus1。No。And is exactly half of them。

 so I took a thousand items。😡，And for each one， I generated random number between。😡，0ero and 2000。

What's the probability that a particular slot gets hit？😡，One out。Right， I， I'm drawing。

Exactly 26 cards at random from this deck。The probability that I draw the ace of spades is going to be about a half。

😡，Okay， so that means that the expected value of y is。One half times2 to the K。

If the table is half full。😡，And the hash values are sorry。Sorry， I need to understand popular。

 not full if the table is is half populated。And hash values are random that I expect every block to be half。

😡，Oopulated。Okay。😊，So what I'm actually interested in。Again， that's PK。

This is the probability that y is greater or equal to two times the expected value of y。

And so now we're in the magical land of tail inequalities。😡，嗯。So嗯。

What I'd really like to be able to do at this point is apply Cheevvy sheevs inequality。

 and the reason I think I might be able to do that is because why is a sum of indicator variables？😡。

For each item in my input data， I have a one if that item happens to be in my block and hash into my block and a zero if it doesn't。

😡，So this is exactly in setup up， provided those indicator variables are pairwise independence。😡，So。

If I assume。H zero is。Pair wise independent。喂。😊，In that case。

 I know that the probability of y being greater than1 plus delta times the expected value of y。

Is at most。啊。One over deelta squared times the expected value of y， this is Chevy she's inequality。

And this is great， I could just set Delta to be one。😡，So set Dlta to be one。

That means the probability that y is greater than twice its expected value。Is it most？

One over its expected value。But his expected values。嗯。1 over two to the K minus one。

So the probability that a block assuming I have parawiseise independence。😡。

The probability that a block of。Size2 to the K is popular。

 meaning lots and lots of things hashed into it is exponentially small in the block size。😡。

And so if I plug that back into this formula about block sizes being full。

 this is going to imply that the probability that a block of size k is full is big O of two to the minus k。

😡，I think the constant there is， I don't know， three。Nothing， nothing extreme。没。嗯。Yeah。So。

Now I'd really like to be able to plug this in to get something about the size of the largest full block。

😡，嗯。That turns out to be somewhat difficult。😡，It's like the maximum of a bunch of things doesn't have a nice relationship to the things themselves。

 so I need a slightly different expression for the running time so again'm going to be I'm going to be conservative here。

Um， the the expected running time of my algorithm is， well。

 I'm just going to sum over all block sizes。Of。The amount of work that I have to do。

If that block is full。Times the probability that that block is full。😡，Now。😡。

Notice at some point when K is small you。😡，Blocks are going to be full and as K gets bigger。

 at some point there's a transition between the blocks being full and the blocks being empty。😡。

But I'm not taking advantage of that in my analysis， I'm just saying， okay。

I'm using linear expectation to turn it into just if the block is full。

 I'm going to do two to the K work on that block。😡，Now if I plug in this formula。

 I get sum from k equals0 to log M of order2 to the K because that's the size of the block。

 I have to scan it times order2 to the minus k。This comes out to order one。And so。

I don't get what I want。I got so close， but not quite there。

This is enough at least to show that linear probing is no worse than building a binary search tree。😡。

But this is really not what we want。😡，We need a stronger assumption about our hash functions than we did for universal hashing。

 so uniform and pairwise independent， that's the same as stronglyongly universal that we used for perfect hashing。

😡，对。So we knew how to build hash functions that satisfied those properties。

We hoped that that would be enough。😡，But it isn't and even though I was conservative at various steps in the analysis。

 this analysis is actually tight。😡，It's possible for any。

 if I just give you like one of like the tabulated hashing stuff that you're looking at in your homework。

😡，That's uniform and parawiseise independent， but provably there are。😡。

Setets of data that you would store in a hash table that if you used binary probing or linear probing。

😡，You can adversararily set up a case where you need to do login probes。Okay。

 so it's not because I was conservative， it's because it really isn't enough。Yeah。

So what I want to assume instead。Is a greater level of independence。

And when we were talking about tail inequalities， I made a vague reference to higher polynomial moments。

😡，So。I'm going to assume instead of being parazed independent。😡。

One hash value has no influence over any other to four independence。😡。

So what this means is if you tell me three hash values。

 you've given me no information whatsoever or about a fourth。😡。

There is no correlation between any four hash values。😡，喂。Now。

 I haven't told you how to guarantee that yet， but we'll get there。嗯。

So then there's an extended an analog of Cheevvy Ches inequality。Which really ought to be called。

Sheevvy Chevy sheev shes in equality because it's got four shebs in it。

The probability of x minus mu to the fourth being bigger than some value z。😡，This is most big O of。

One over， sorry。Let me。Sorry， let me write it in the form you actually need it。

The probability that y is bigger than1 plus delta times mu。嗯。Before we got one over Delta squared mu。

😡，Now we're going to get。One over deelta squared mu。Squared。If we somehow had six way independence。😡。

We would get one over Delta squared view， cubeked， we had eight way independence。

 we'd have fourth and so on。All right， so in this case。

 what this means is the probability that y is greater than twice its expected value。Is big O of。

4our to the minus k。I plug in again， delta is equal to1， so it vanishes into the big O。

 mu is2 to the K。Or two to the k minus1， the minus1 folds into the bigO， and then I square。

One over the mean。And。And now what happens？My expected run in time。Is again。

 some overall possible block sizes。Of the amount of work I have to do if that block。😡，Oh yeah， sorry。

 this implies that F of k is also four to them minus k。

mountt of work I have to do if that block is full。This is some of okay。

Of2 to the minus k is 2 to the k times 4 to the minus k。This is a nice little geometric series。

That collapses down to a constant。可。😊，So。Provided that I can guarantee that the various hash values that went into building the table。

😡，Or four way independent。Then the expected running time is going to be constant。😡，All right。

Let me make sure everybody understands what we just saw okay。So just to start out。

The algorithm that we're using is binary probing。😡。

I'm going to probe within a block of size some power of two completely before I go into the next larger block of size power of two。

 I can do that by just using a bitwise exclusive or over a standard binary counter。U。

The performance of this algorithm depends on which of those blocks is actually full。😡。

But being full is a complicated thing that depends on because items can be stored in various locations。

 not because they hash there， but because they tried to hash somewhere else and needed to overflow to there。

So。Instead of looking at。What it mean the probability that a block is full。

 had this somewhat more direct way。Of looking at how blocks are bad called popular block is popular if without doing the overflow。

 the block would be full。😡，So ignoring all the overflow logic。

 still eight things hashed into this block of size eight that makes the block popular。😡。

So we get this this。Not too complicated relationship between those two。

 the probability that a block is full and a block is popular。

 but this allows us to focus on popularity， which is just a function of the hash values。😡。

No longer a function about how things overflow into other things。嗯。

And then if I can assume pairwise independence， which is what I already know how to do from my earlier hashing stuff。

😡，If I push through all the math， Chebby shes inequ implies that the probability that a particular block is full is one over the size of that block。

😡，And therefore， the probability that a block is。Right。

 and but unfortunately the most you can say then is that the expected running time of my probing algorithm is going to be log in。

😡，In expectation， I'm going to do a constant amount of work at every level。😡。

Of the hierarchy of block sizes。So I need to make a stronger assumption。😡。

And then if I make the assumption that my hash values are fourway independent。😡。

Then I can use a natural generalization of Shabishedd's inequality to get an even tighter bound on the decay of that tail。

😡，And that implies that actually in expectation， I'm doing exponentially less work at every level of that hierarchy of block sizes。

 and everything ultimately collapses down to a constant。😡，Now。

 none of this analysis shows up in the code。😡，What shows up in the code is， well。

 I have a for loop and in the body of the for loop， I do this。😡，Spoil lines of code。No summations。

 no probabilities， no chevvy， chevy， chev chhove， anything， you just do it。Right。

 but you do need to actually。Design your hash functions carefully so that that assumption of for independence and the earlier assumption about hash values being uniform are actually satisfied。

😡，Now。There is a sar subtlety here。Which is。Those hash values are for independent。

 but ultimately what I'm analyzing is the behavior of the blocks that contain particular value x。😡。

So to actually push this all the way through。We need five uniform hashing。

Which means for every five items。😡，There are M to the fifth possible tuples of hash values。😡。

And each of those has probability one over m to the fifth。

the reason I went from four to five is the four only looked at independence between the items that were already in the hash table。

But I also need to be independent of the item that I'm inserting。Okay， small technicality。Right so。

so what this means is。啊。Or all。Distinct。The W X， Y， Z。And for all I， J， K L。H。

The probability that h do of v equals H and。And H of z equals L。Is exactly one over m to the fifth。

 I guess technically I could allow it to be less than， but it won never be less than。

USo V hashs to H W hashs to I， x hashes to J， Y hashs to K， Z hash to L。

 those five events are independent and each of those hashtags is uniformly distributed。Okay， now。

 how do you actually make this happen？Well。I go back to Carter and Wedman， what I could do is。

Pick pick a prime value P， and that can define my initial hash value to be a plus Bx plus Cx squared plus dx cubed plus E x to the fourth。

Mud P。Moud M。Where。A， B， C， D， and E are all chosen uniformly at random from the integers from 0 to P minus1。

So this is the fifth degree。Generalization of multi ad。A。嗯。Now。

 one of the things you'll notice about this。😡，Is every degree of independence I need。

 I need to do a constant amount more work， more independence means evaluating the hash function itself slows down。

😡，And so this is not a particularly efficient cash function。

 especially if you want to deploy this on， let's say the internet backbone。😡，嗯。So。Instead。嗯。

There's this lovely paper by Thorpe and Zang。Where they。

Did something called twisted tabulated hashing？So like tabulated hashing， I'm going to split my。😡。

Ease into two parts， the top half of the bits and the bottom half of the bits。

So then the hash value for a given care。Is， well， let's look up。诶。

Let's use the first half of the pair as an index into a random。Aray of labels。

And then I'm going to exclusive or that with， let's look up in a second array at the location given by the second half of the word。

And then I'm going to do something just bizarre。😡，Okay。

 so I'm going to think of my w bit words as consisting of a w over two bit prefix and a w over two bit suffix I'm going to prepare three tables。

 one where I can feed in a w over two bit。😡，Prefix and look up a random value。😡。

A second one where I can put in a w over 2 bit suffix and look up a random value。

 and the third where I can feed in a w over2 plus one bit。😡。

Number that's the sum of the prefix in the suffix and get a random value。Now。

One of the things that's weird about this is if x and y were generated uniformly at random。

 x plus y isn't。😡，If X and Y are rolls of two eight sided dice。😡，Okay， let's be nice。

 the two six side dice。X plus y is more likely to be seven than it is to be two。😡，Nevertheless。

Because of the way these things mix up。😡，This is actually。Five uniform。Now， this is， to me。

 this is totally bizarre because at some level I'm just generating three independent things。

 the slide and A， the slide and B and the slide and C。😡，Yeah， maybe I'm doing some。

 it's not really into， you know。Looking at C with the equal likelihood everywhere。

 buth that'll mix it up with the other stuff so I could see this being three uniform。

 but it turns out to be five uniform。😡，Through the magic of linear algebra。Okay。嗯。😊。

There's an even better one。So this is what I would actually recommend implementing。😡，Okay。诶。

But one problem with this is。The only thing I got out of this analysis was the expected time to do a search。

😡，Again， if I really want strong performance guarantees， I want to say something more。

 I want to be able to say the time to insert an item into the hash table is big of one with high probability。

😡，Unfortunately， with five uniform hashing， the most I can say is that the time to insert a new item into the table is that most log end with high probability。

😡，So if I really want high probability bounds， even five uniform hashing isn't enough。

 I think I need to go to like nine uniform hashing。😡。

And there are versions of these things that I've showed you that will work。😡。

You may start getting slower and slower as the more independence you need。

 but there's this paper by Mattraash Co and Thorrop。Who were at AT& T。So Michaelle Thoror。

 I've worked at AT&T for many years， Mihai worked there for a few years。

 Zhang was a student intern at AT&T。嗯。So I'm just going to use simple tabulation。

So I'm going to define。Instead of breaking up my word into two parts。

 I'm going to break it up into C parts。😡，I think they recommend like c equals eight。对。

And then I'm going to generate。Random arrays。Associated with each of those parts。Okay， and then。

Use each component to look up random value and it's corresponding random array。

 exclusive or all these things together， and that's my hash value。😡，Yeah。Now， the bad news is。

This is only through uniform。So if I just want to use the straightforward analysis in terms of moment inequalities。

 this isn't enough。😡，But what's。rascu and Thorpe actually showed is it's not for uniform。

 you can't use the standard analysis by itself， but it works anyway。😡。

So the analysis is considerably more complicated。😡，But you actually still。Yes。嗯。

Order one time with high probability， the constant in here depends。On the choice of your punngsten。

Yeah。是。不太。So in order to use this analysis。😡，I need more independence。😡，To prove better time bounds。

What？Miha and Miickel did is they said actually。You don't have to stick to this particular analysis。

😡，You don't have to reduce everything ultimately to Markovs inequality。

 You can do a more refined analysis that's specific to。Paion。And if you do it carefully。

 you can still prove things like。Not only are the hash values almost five independent。

 they're almost fully independent。😡，In other words。

If you use tabulated hashing with the right number of slices and for various guarantees。😡。

Aabbuulated hashing acts like magic hashing。The hash values you get are random。They're uniform and。

They're not fully independent， but they're close enough to fully independent that up to Big O。

 you can pretend they're fully independent。I just， I don't want to read a 28 page technical paper at you to convince you that this works。

 but it's true。😡，Right I have read the paper， I trust， I know both of the authors。

 I trust them both or I trusted them， so Miha was an interesting character。😡，No。

 it' it's a sad story Mihi was。Won the CRA Best undergraduate Research Award when he was an undergraduate at MIT。

I know the people who wrote him the letters because he was publishing in my field when he got this award。

And one of his recommendation letters said。I am delighted to write this letter enthusiastically supporting。

😡，Miha Petroscu's promotion to associate professor with tenure。

 unfortunately because Miha is an undergraduate， I am forced instead to nominate him for a CRA undergraduate research award。

😡，And he was not exaggerating Mihi as an undergraduate published a dozen papers in major theory conferences。

 he made huge breakthroughs not only in hashing but in other kinds of data structures。😡，He。You know。

Gdud， went to MIT， got his PhD in two years。U went to work for AT&T and after he'd been at AT&T for about five years。

 developed the brain tumor and unfortunately passed away a couple years after that。

So this is one of these stories of brilliant genius cut off way too way， way too early。

But enough that he left his footprint on a significant fraction of。呃um。Algorithm and data structure。

 design， fine grain analysis， things like that。So really cool stuff， really sad story。This is life。U。

 but the conclusion of this is thanks to Miha， we know if you just implement your hash functions carefully using the algorithm that was essentially proposed by Carter an algorithm that was proposed by Carter and Wegman back in 1970。

😡，It works。So you can actually do hashing with theoretical guarantees。

With not that complicated algorithms， just don't ask for the proof。Okay。

This is as much as I want to say about hashing as a data structure thing next week we'll start talking about string matching and then we'll be using something that smells like hashing for different purposes。

😡，I'm happy to answer questions， but we're out of time， have a good weekend。So far to like whatever。



![](img/2d235ef841744112ed6a14425bdf144a_3.png)

Pruing to uniformity for tab。