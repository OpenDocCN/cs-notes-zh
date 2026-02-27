# 022： Predecessor searching on the ultra-wide word RAM.zh_en -BV1kWFGzsEmN_p22-

Recording。

![](img/3cf4d5083a4c37c984a0e83943a5a205_1.png)

All right， so as I said， this is the last official lecture of the class that I'm going to give。And I。

It trying to figure out what exactly to do。We've been talking about integer data structures。

Integer sorting， integer dictionaries。And eventually settled on a paper that was。

Published in conference form in 2022， it appeared in a journal in 2024。

That talks about a relatively recent extension of the word RAM model。

That attempts to capture large scale vector processing。

Computers not just scalar processing computers with words， but actual。

Things that are actually meant for fast， large scale computation。And so this the model。呃。

Is called the。Ultra wide word ri。The model itself。Was。First proposed in 2015。

And it's an extension of the standard wargram model。呃。Memory。Sas。Or。哦门。W bit words。With the。

Usual operations。In constant time， where usual means what you would expect if you program and see。

Addition subtraction， multiplication， bit shifting， boo and operations and so forth。But in addition。

You have。We're called U words。呃。This。W squared bits each。And as a general rule。

 the number of these is。Memo is full of W bit words。

You're allowed to use a small number of these U word registers。Now you can think of this as W。

Words concatenated together and they'll be in algorithms that work in this model。

There's sometimes a translation thing where you take W addresses and you load them into a single U word。

The U words。呃。So house。So。嗯。I time。But。There's a couple of other。Things that I want to be able to do。

Should say here a small number。Of these old rewards。嗯。So the the。好。

The other thing that I want to be able to do with an ultra word is what the variousrry' papers refer to as it's scattered reads and writes。

So in constant time on the normal word Ram， I can take a W bit address。

And I can go get the contents of the cell in memory cell at that address， which is in the W bit word。

 I could load it into my W bit register or load it into a different address。

Or chase the pointer indirect， The usual things that you do with memory addresses。F ultra words。

You can't use the U word as an address。Your memory space is still only two to the W cells wide addresses are still only W bits long。

So what you do instead is。For example， a read。So if you're given。

I'm just going to write you word for U word and in general I'm going to use capital letters to represent。

Ultra words and lower case letters to represent single words。So if you can imagine。嗯。啊。

Think of this as a vector of W。Words。Each representing an address。U。

And then I'm going to retrieve the result。Which is you know， memory。

 the word at address a zero followed by。The word address A1。And so on。As a single ultra word。

And similarly， right。哦。Given。The addresses and the data。Onm。Right。Deace sub I into。Memmoth。A sub I。

For all I。And these happen in constant time。啊。So this is apparently。

Based on some specific architectures that I don't know enough about real actual physical computers to say this with any authority or in any detail。

 but the paper does talk about sort of，In the real world。嗯。啊。Ulter words。Have。Thousand of bits。So。

They it say somewhere between 1000 and 10000， and this was10 years ago。

 so things may have changed by then。 so this is reasonably consistent with a 32 bit word architecture。

32 squared is。Is that 16 k？听。32 square， sorry。Oh， 32 squared is 1024。Right， so 64 squared is 40。

 96 yeah so this is reasonably consistent with W being 32 or 64。And formalizing it in this model。

There's one。There's some other operations that。In addition to the sort of standard ones。

 given two U words compute their sum， given two U words compute their difference。

 given two U words compute their product or do bit shifting or ans and ors。U。There are sort of。

Secondary。Operations that。Can be built out of the standard vocabulary of sea operations now on these really ultra wide bit strings。

So one of them is。Compress。So。Given an ultra word X。I want to compute。A single word little X。

Such that the I bit in little X。Is。Leftmost bit of the I word。So left。Bit。Of。

The Ithe word in this U word。So given。An ultra word that looks like this， I'm just pulling out。

These bits。Into a single word。A in these other architectures。

 this is sometimes called pack sign bits。So if you。

If you imagine that each of the component words of capital X。

A s integers in the usual to complement representation。

 then the most significant bit it represents the s and zero is positive one is negative。Um。

This can be done using U word multiplication。We've already seen this in the context of。Fusion trees。

So， given that we can do it in constant time using the other vocabulary。

 we may as well assume that this is a built in instruction。

Some other things that we might want to do。Our。Component wise arithmetic。So。

If I want to do component wise sum of。2。Ulter words。

 what that really means is I'm treating those as vectors of length W。

 each component of which is a single word， and I'm adding the components separately mod to the W。

Okay， so this is。啊。X of I plus y sub I。Moud to the W indexed over I。

Hopefully this ad hoc notation is reasonably clear。Likewise， I can do。嗯。呃。You know， component wise。

Subtraction， I can do component wise comparisons。So this is。呃。In the result， this。

 the ultra word that results。Each component， the Ih component is the word with value zero if the if component of x is greater than or equal to the ifh component of y。

And it's the word with the value1， so all zeros in a1 in the low bit。

 if the if component of x is smaller than the if component of y。

Of course I can compact to that and just get a single word whose bits represent each of the comparisons。

 they mean this is this is the sort of standard parallel comparison that we've already seen in practice in a couple of other data structures。

Then。There's。Component wise multiplication， this one is a little bit more subtle。

Because the product of 2W bit integers is a 2W bit integer when you multiply。

 you add the lengths of the integers so what this。啊。Really the way they formalize this。

Is you can say assume。That x sub I equals y sub I equals 0。If I is odd。So。I'm going to have。

The zero thing will have data and then the first one will have zeros and the next one will have data they't have zeros。

 so essentially I'm taking w over2 w bit words and spreading them out to make room for the 2W bit product。

嗯。And then this is going to be Z。Where。Z sub2 I is。嗯。X sub 2 I times y2 I。呃。Maud。

Two to the WN Z2 I plus1。Is x2 I， Y2 I。Dive。2 to the W， which is the same as it's shifting down by W。

So it's just Z2i and Z2i plus1 or the low order word and high order word in the component wise products。

 but it's always only multiplying the things at。Even indices。Again， this。

Can be done using standard multiplication tricks， apparently。

The papers didn't explain this one the paper that I was mostly focusing on didn't explain this particular operation in detail。

 so I'm a little bit。嗯。The others I can see how to do using tricks we've already seen。

 this one is a little bit funky。So it's certainly clear that if you can do word level multiplication in hardware in constant time。

Then you can also do this with ultra word hardware in Con time。

What's less clear is whether this can actually be implemented in constant time。

 assuming that you have other standard operations。But this is actually。Used。

In some of the algorithms I'm going to talk about。So this is the machine that we get to play with。

A data structure consists of a bunch of words， they might be in W length chunks that I can load as U words。

 but they don't need to be contiguous because they have this scattered read write ability。嗯。

And I've got a small number。I think it suffices just to say a constant number of U word registers that I can use these operations on。

Ay。And then the the。The actual result。That I want to talk about。Which is by a group of Danes。嗯。收的。

Journal version。I can do。啊。Order dictionaries。In with constant time operations。So predecessor。

Successor。Insert。And delete。Now。These are amortized expected。Under the hood。

 it should maybe come as no surprise whenever you see something constant involving integers。

 there's hashing going on。But the predecessor and successor queries are Constantine Moores case。

As you again， would expect from a careful application of hashing。So notice that that。

The best that we talked about。In the standard word Ram model。Was u。

Essentially log log n I mean there were a couple of different variants of this fusion trees gave you one bound。

 why fast tries give you another bound， the compromise between those two bounds turns out to be about square root of logW。

 there have been lots of ways of putting things together that I think the high level thing to keep in your head is that on a standard word RA you can support predecessor queries inserts and deletions in about log log n time。

Per operation， assuming the word length is roughly log ahead。This just constant。

And that it's provably impossible to achieve constantantine performance in the standard wordrun。

So this really is using this more interesting。Architecture to get something that is， you know， well。

 obviously optimal except possibly for this。Amortized expected stuff。嗯。Um。So。Questions about。

The model。嗯。At the end， if I have time， I'll say like， I'll just state the result。

 There're in a couple of other results。Within this model， not just dynamic dictionaries。

The original paper actually just said， hey， we've got this model， it seems to be interesting。

 let's do some algorithms。And for example， they showed how to get multiple factors of W shaved off of like standard dynamic programming algorithms。

嗯。Using sort of very relatively basic parallelism。And then there's a more recent。

Data structure in this model by the same people that handles dynamic range minimumqueries so going back to the very。

 very first data structure that we talked about。嗯。I believe the。The running time there was log， log。

 log n。Per query or insertion or deletion。嗯。So this is still。

 it still feels like this is a bit wide open， there are lots of other things that one could look at in this ultra wide model。

Am。Okay。So。I'm going to develop。This dynamic order dictionary， first of all。

 I'm not going to talk about insertions and deletions in the lecture。Most of the ideas actually。

 I think are sort of either built into。The design of the data structure and query algorithm or are similar to data structures that we've already seen。

 so I wanted to just focus on in particular。I'm really just going to focus on predecessor if you also want to support successors。

 there's the obvious dodge of you build a data structure for predecessors and then you build another data structure that that is a predecessor thing but backwards。

嗯。But successors actually will fall out at the end。But focus on predecessors。So。I'm going to start。

By forgetting about the order for the moment。And just thinking about what it's possible to do as a dictionary。

So remember a dictionary， you have keys and you have values。

And you store the keys and you store the values with them。 And then later somebody says。

 here's a key， do you have that and the data structure says yes。

 and here's the value or the data structure says no。This is standard hash table territory。

 and we've seen multiple ways at this point of handling that。

 even without the underlying assumption of the word Ram。In constant time per query， your update。

But I want to do something a little bit more interesting。Which is I want to be able。To look up。

Multiple things at the same time。Okay， so here。The idea is I want to。Maintain。

A set S of NW bit words。Subject to the following operations。Well。

 obviously I can insert a key and I can delete。Key but。I'm going to exploit the ultra wide model。

 and I'm going to use， I'm going to define。What's called a P member for a parallel membership query。

嗯。I'm going to return。A。A single ultra word。Or。Where the if component of R tells me whether the。

I component of the input U word is in my set。OkaySo for just as illustration。

 if my set that I'm storing is the set of all consonants in the English alphabet and my query is the word hashing。

Then the word that I'll get back is10，11，011， but with that ones and zeros spread out into ultra words。

K。嗯。For technical reasons。嗯。Do I need to do that no I don't need to do that here and I need to do that later here I can do W bit things。

嗯。So。I'm going to get n plus W space。啊。Order one。Curry time。And order one。

Amortized expected update time。And again， I'm going focus。

 I'm not going to talk about updates at all。So notice here that that this is strictly better than what you get from a normal hash table because a normal hash table you have to look up each of those W words individually and so the membership query would take。

Or W time。And remember， W， you should imagine as being at least log in。

So I'm getting a savings of W here。But。Yeah， it's a hush table。And in fact。

 it's even a familiar hash table。So the basic idea。Is something that actually shows up in 473。

So I do。So two level。What is。Sometimes inaccurately referred to as perfect hashing。This is。

Fredand Comlo Zimmeredti。啊。84 is old。So the idea is I'm going to have a primary hash table。Prong n。

Every cell in this table is going to point to an overflow hash table。

That has size roughly n sub I squared where n sub I is the number of things that。

Are allocated to bucket I in the primary table。Okay， so I'm going to hash n things into。

A primary table of length N， and then a secondary table whose sizes the square of the number of things that I need to store。

The reason that I want to do the square of those things is that that guarantees that with constant probability when I choose a hash function from a reasonable family of hash functions。

There will be no collisions among the ends of I things in that secondary table。

And that's what allows me to say， oh， I want to look something up。

 compute the primary hash value that tells me which secondary table to look in。

 compute the secondary hash value that tells me where in the secondary table to look， and that's it。

So queries are very simple。What？嗯。So assuming。Let's say two uniform。Action。This。

It's a no you can guarantee that there are no collisions。In the secondary tables。And the total space。

Is only the total expected space is only linear。And to uniform means that for any pair of keys。

 their hash values are likely to be any pair of addresses。嗯。Okay， so this one。

 this one is is familiar， hopefully， but I'm going to use a specific。Family of。Uniform hashing。

Actually， it doesn't have to be uniform， it just has to be close。

And we've seen this has function before as well， this is。So multipleply shift passion。

So at the top level。The hash value of a word x。Is。Sum number a times x。Rounded down to the near mud。

To the W。Well， I'm just going to follow the notes。 I think this， this may be actually。嗯。

I think this is actually div， not Maud。So the idea is I multiply。My。嗯。I。

Multiply the given value X that I want to look up in the table by this random number a。

 a needs to be chosen uniformly random among all odd。W bit integers。

Then when I multiply these two together。The result。Is going to be。

X times a and the actual hash value is going to be the bottom log n bits。Of the。嗯m。Top word。

That's not what that formula says。嗯好。嗯。Yeah， I think the way this is written in the。

The way this is written in the paper is somewhat different than the way。

That I've seen this hash function described before。 So I think this is AX due2 to the W。And then mod。

Man。And I'm assuming that N is power of two。That's the form that I'm used to seeing。

 it may be that they're taking the high log n bits of the bottom word。

 I think that maybe that's where I'm confused。In their version of it。

 so just to be consistent with the paper and sorry about this， I'm going to change it。

Back to what it was。So Mau。To the W shifted by W minus log n， and so that is these log n bits。

That right？Exact that's consistent。And there's another paper somewhat later than Fredman and company that described how to maintain this two level perfect hashing structure。

Dynaically under insertions and deletions with constant time again amortized expected insertions and deletions。

 it's not quite as simple as just when the secondary tables get too full you double you have to be a little bit more careful about the hash functions and so the authors use this particular。

hasash function to。We get things to work out。嗯。And so that also means。That。When I'm looking at。

The ice。The hash function for the I secondary table。嗯。啊。That I do exactly the same thing。

 Only now my salt parameter is different for every secondary function， every every secondary table。

 So these are。Random。Od words。诶。And so this family of hash functions turns out to have the right collision probabilities。

For the hash table to work。But now the other thing that this particular family of hash functions has is it has enough structure。

That we can actually compute， given a vector of words in an U word。

 we can compute the vector of corresponding hash values。In constantt time。

Because it's all just based on multiplications and masking and shifting。

 you do need to do the sort of component wise multiplication。

 and there's a little bit of subtlety in the secondary things。But。

Just let me sort of walk through the high level ideas so if I'm given。My U word X。

 the first thing I need to compute。Is the U word I。

That in the I position contains the hash value of the I。Word。I need to not use I here。

 as that's going to get confusing， say in the cafe position。

 it contains the primary hash value of the cafe component of x。Again， this is。A times x k。Moud to W。

と。Shifted by。W minus log n。嗯。So。The way that I need to do this。

Shifting is easy mod to the W that's just masking。The hard part is doing the multiplication。

 so this is a component wise。Product of。An U word capital A that consists of just W copies of little A。

And the U word X， now I have to do this in a few stages， mask out the even indices， do the product。

This just gives me w over to2 w bit results， mask out the parts that I want。

 put them in the right place。Mask out the odd indices， do the same thing。

 mask out things and then or things together， so it does take a few steps。Ung。

The next thing I need to do is。I need to compute J。So this is computing。The appropriate secondary。嗯。

Hash values。And notice that which。Secondary hash function， I apply。

Depends on which primary hash values I got。So first of all， this is。Essentially going to be。嗯。

You know， I start off with needing to do a component wise multiplication with an ultra word a prime。

 but the components of a prime are things that are。Depend on the primary hash values。

So in the hash table itself。I'm actually going to store。This is store a0， a1， A2， et cetera。Okay。

 so there's an array at the top level that stores all of the salt values for the secondary hash tables。

And so what I'm doing here。Is。A what did I call it？Scattered read， yeah。This is a scattered read。

From that table。Okay， so this lets me pull the appropriate ACce of I into an ultra word。

Do the multiplication that gives me the product part。Moud2 to the W。 that's。

 that's just cutting off the lower reward。 But now， notice when I shift。

 I need to shift by different values。And so。That's actually going to be。



![](img/3cf4d5083a4c37c984a0e83943a5a205_3.png)

嗯。

![](img/3cf4d5083a4c37c984a0e83943a5a205_5.png)

Again。What。没。嗯。So instead of thinking of this as shifting to the left by different amounts。

I'm going to think of it as shift to the right by different amounts and then shift to the left by a common thing。

But shifting to the right， shifting to the left by different amounts is the same as multiplying by different amounts。

So again， this is a component wise multiplication that shifts things up and then shifting。

 then you just do a global bit shift to shift things back down。Okay。嗯。So。Then then I need to。呃。

Return。m the  query result。In this case， it's just。诶。Let's say is。Jy。😔，Sorry。Compute result。This is。

You know， do the actual lookup， this returns the values。

Or whatever is actually stored at the appropriate address in the appropriate secondary hash table for each of the keys in the original input。

And then basically。I can compute。A bit vector， for example。嗯。If all I want to know is yes or no。

I can just say， oh， is the result of what was that I retrieved from the hash table。

 is that key equal to the key that I passed it？ButAgain。

 I'm doing this in parallel for each of those words。

If I want to associate secondary data to the items in the hash table。

 then I also need to compute this sort of indicator array， but then I would do another。呃。

Another scattered read。To pull things out of parallel data arrays in the secondary hash tables。可以。

So this is all a bit sketchy， but I think there's enough ideas here that if you needed to actually work out for the details。

 I think this seems relatively straightforward at this point。Okay。

So I have a hash table that allows me to do parallel lookups。Saving me an order W factor。

Over a normal hash table。Okay。Questions about how this works， does it sort of makes sense。Yeah。

So when doing these ultra wide word operations， they don't need to be continuous or raising them we can do like scattered look the idea is you have。

 you know， a constant number of these ultra wide registers。

 you can load them by doing a scattered read from a bunch of different places in memory into the register。

And then you're doing the constant time operations on those small number of registers。

Part of the function like so apparently we can also do like W parallel and rees to IU。 Well， I mean。

 so that that that's I mean， what you would actually do here is not compute。USo。

You're taking the address of the primary table。Then you're looking up pointer values to get the addresses of the secondary tables that gives you a vector of addresses。

 then you're adding a vector of offsets to get the addresses into the secondary tables。

 then you're doing a scattered read to get the contents at those addresses。right and Yeah。

 because you as long as you line up all the addresses in an ultra word thing and say。

 go get me the memory and come back。 there is a bit of subtlety when you get to the insertions and deletions that when you do a scattered write。

You have to make sure that the addresses are distinct。

So this is a standard issue in parallel computing models。

Where you use a parallel RA where you've got a bunch of processors and each one is executing the same code。

The standard model that people use is what's called a CREW PRAM， concurrent read exclusive right。

So if two processors try to read through the same address， fine， we get the same result。

 if two processors try to write to the same address。Your computer turns into a kitten。

Garbage gets written into that address。嗯。So the similar assumptions going on here。

 I don't have to be careful about。If some of the components of the U word that I passed in。

 this capital x are equal， that's fine。I'll get the same results back out。But when updating。

 I have to be a bit more careful。Okay。So。This is really where almost all of the work is actually done。

I've totally lost order。 There's no way to do predecessors with a。Atable。

So what the authors of this paper propose。Is to use。A variant of Willard's X fast， Y fast tries。

Or the same thing that underlies fusion trees， which they call an extra fast try。

Yes spelled without the E。So。嗯。Again， they're clearly referencing Willard's at Fast triess。

 which used the letter X for reasons that I don't understand。

 except that one of the variables in the data structure was called X。Again。

 they're just calling it extra without the E to remind you of Willard's X Fast tries。

 but it is not Willard's X fast try with some modifications to it。

It's still using tries under the hood， but it's using them in a somewhat different way。

So this is going to be my dictionary， I'm just going to talk about how to do predecessor queries。

For technical reasons。I'm going to assume that we have NW minus one bit words。嗯。

This is mostly so that when I'm like doing parallel comparisons。

 I can have that one bit at the beginning， it's really easy to take if I actually have NW bit words。

And I want to do predecessor queries with that， I build two data structures。

 one containing the words that have assigned bit equal to zero。

 and one containing words that have assigned signed bit equal to one。Okay， double the space。

 it's fine。当。And okay。嗯。So。The idea at。H level， high level design。Is a what they call a compressed。

Or compacted， try。So I'm going to give a specific example that one of the authors helpful put into their slides。

So the idea behind a compressed try is sort of， as usual， I can define a try over the words。To be。

A complete binary tree of depth W。Where I store the words that I want in the leaves。

 and then I delete any node that doesn't have one of those stored items as a descender。

What I mean by compressed is that I only store nodes that have multiple children。

And the leaves and the root。Okay， so。That means that paths。Sorry， edges。

In the compressed tri are not going to be labeled with single bits， but rather with bit strings。Okay。

 so this is a compressed try storing the integers 01815。48。60，61 and 63。对。嗯。You know。

I'm not actually going to。This is not really the main data structure， but I do want。

To define the string of V， this is the label of the path。From the root。

To the so the string leading to here is 1111。The string leading to here is 001 and so on。可以。So。

What I also need。Was Min V and max of V。 This is the。Min or the max。Leaf。嗯。Below。对。so。That means。

 for example。UmIf this node is V， then this is the min， this is the max， if this node is V。

 then this is the min and this is the max。Hey。I'm。Deliberately to keep things simple。

 hopefully not at too much risk of confusing people。

Minvi and Max V you can think of either as pointers to those two leaves or just the values of those two leaves。

I won't add the notation that would distinguish those。嗯。

So what does the data structure actually consist of？It has two parts。It's a doubly。Liinked。List。

Of leaves。In。Sored order。This is also you know the keys in S in sorted order。

 so every key in S is represented by a unique leaf。

I'm literally just going to build a chain of things。And the idea here is as long as I can get close。

To the item that I'm searching for， the predecessor and successor I can get to by chasing pointers up and down this linked list。

The second thing。Is I'm going to build a W parallel。Ash table。4。嗯。The set of all。Vertex strings。

For all vertices in this compressed try。Now I'm deliberately sweeping a little bit under the rug here。

 those the compressed try has depth w minus1， and so every one of those strings has length at most。

W -1。 but when I build a hash table， I need to build a table of keys of length， exactly。W。Um。

 so in fact。What they do is they look at every edge of the try。

They take the string of the tail of that edge and the first bit of the label along that edge。

 and then a bunch of zeros。So they appropriately pack things。

 but they do it in a way that for every non leaf node you actually get。Two items。

But I think for the sake of intuition， it's okay to just think of it this way。可。So。嗯。

And for each one of these。These are the keys that I use to start in the hash table。

 the data that I use in the hash table for each node V is MinV and MaxV。And so。The idea is。

I'm going to look。For a node V。That corresponds to， in some sense， the longest common prefix。

 in the try， the deepest ancestor in the try for the query value and the nodes that I have here。

Then the predecessor is either going to be the men or the max of one of the children of that men。

Okay。Okay， so。How do we do？Am。Find the predecessor of X。嗯。啊。So。I want to sort of imagine。That。Say。

X is here。And I don't know it。Don't want that to be black。Make that red。X is here。

Let's say in this case， x is。12。系。嗯。So the first thing I'm going to do is。诶。Build an U word。

Containing。All prefixes。Of x。 so in this particular case。That's here's X。

And then I start tearing bits off。so there is my ultra word again， in the real algorithm。

 I'm not dealing with these shorter bit strings I'm appropriately filling out。

The remaining bits so that these are in fact。W， W minus-1 bit。Or actually， W，W Bi strings。Now。

If I look at each of these prefixes。Some of these prefixes are the strings associated with nodes in my compressed try。

So啊。I'm going to。This down。So for example。This。Grerifix is the label of this。Note。嗯。Likewise。

 this prefix is the label of this node， and those are the only ones for this example。Hey。

So I'll look up。嗯。啊。Prefixes。In my hash table。And compact。And then in this case。

 I'm going to get a bit string that the 000110。Okay。嗯。The most significant one bit。

Tells me the length of the longest prefix of x that corresponds to one of those notes。

So I pull out the。The most significant bit in this case， it's two indexing from the right。

 that points to this node。So in the hash table that stores those prefixes。

 I guess I also need a pointer。Well， no。It implicitly is going to point to that particular node。

 yeah， sorry。是。zero okay， so this is not in the tree。

 this is not the pre not the label of any node in the try， this is not， this is not， this is this is。

 this is not。😡，That's what those bits correspond to。O。嗯。

So the most definitive bit tells me which of the component。Which of those prefixes？Actually。

 when I look things up in the data structure， I actually pulled data out。Okay， so let's。

Let's call this node。Let's call this node P for prefix。And now the predecessor of X。Is either。嗯。

Let's see it's either。P dot left dot max。嗯。Or。It's P dot， right？Dot min dot previous。Okay。

 so I know that if the longest common prefix of x and anything else is 001。

I know X is in the tree rooted at this node that I've labeled P。

But I know that the place where the path to X splits off。Is above any other branches down below。

 so it's sort of between all of the stuff in the left suby of P or all of the stuff in the right suby of P。

It's between those two sets of things。 Now， it's possible that X actually is the the the。

Minimum element of the right subter of P5 past in 15。嗯。I guess in they're a little worried。Yeah。

 I guess they wouldn't bother storing the paths going all the way down to the leaves in the more detailed description and so you actually want this strict predecessor you don't want to say。

 I found it but you want its predecessor so you would have to walk one step to the left in the doubly linked list。

嗯。啊。There's also this also this case analysis， I think also takes care of the case where the place where X branches off is in the left subte。

So if I had set x to be， say 10 instead of 12 that I would have had a branch coming down that thing to the eighth。

 again， it would fit in between， but it might actually be and thenm not sure why there is an max maybe it's。

Or P dot left。Dot max dot previous just to be on the safe side。But in any case。

 all of these operations are happening in constant time。

The hard part here is finding that longest common prefix that's done by assembling this family of prefixes into a single ultra word。

That can be done by just doing a multiplication to create several copies of the word and then masking out by nothing and then a single one and then two ones and then three ones and so on。

 so you need to build this constant ultra word to do masking， but then you do parallel lookup。

You look in the data that either gives you directly the address of the predecessor or one step away from the address of the predecessor。

いや。all the edges in this tree is like continuous number of 0，01。

 can we use the technique we like applied in the homework like instead of storing like 0，0，0，0。

 we st and how many0 and to save on space。So。Possibly， but。I mean。

 maybe if I'd done like a better example here。Me changed this to a one。And that number to 50。

There's actually a jog。In there， so it's not always the case that the labels on these edges are all zeros or all ones。

It was just in that one example that he gave。Yeah， for that edge， I meant do in grabb， b。

a half ago like this。But it's still one edge in the compressed try。

And now it's not as clear that doing run LiedIn coding is actually going to save you。Any space？Right。

There is a whole industry。About string data structures for compressed strings。

So you can do compression by run LiIn codinging， or compression by limppleziv compression or compression by Huffman coding。

And now I think the grammar based stuff from Lmple Ziv is the most interesting now I give you a bunch of strings that have been compressed this way and I want you to build me a data structure so given a new string I want to find its predecessor among these or I want to。

See what it matches or find longest common prefixes and things like that。

And there are non trivial results。That say you can get roughly。

 maybe within logs at the same running time。In terms of the compressed length。

That you would for standard data structures in terms of the uncompressed length。嗯。Here， though。

 you're not actually going to be saving that much space because you do need to write down each of the keys。

So you're going to be using n wordss no matter what。The plus W in the space。So。

Here ultimately we got。呃。Yeah。This comes the plus W here。

That comes from the various constants that you need to do to do all the shifting and masking and stuff。

All right， so they actually do describe a way of dealing with the weird corner case where the number of things you're storing in the table is smaller than the size of a word。

Basically， you use variant diffusion trees。And you assemble every time you insert。

 you build a little bit more of these constants。嗯。啊。And again， in the actual extra fast try。

 there's also some other constants that you need to precompute to do the appropriate masking to get the prefixes and multiplication and things like that。

嗯。So that's it。Because you've got this way of finding the longest common prefix in constant time using the hash table。

 that's ultimately where。Everything boils down to once you found the longest common prefix。

 the rest is relatively standard， although you do still have to use the model in order to get it because you're not actually given a pointer directly do the thing。

There's a little bit of subtlety there。But basically， that's it。嗯。And yeah。

 the only other thing I wanted to mention。好的。是。What's the dynamic range minimum queries。嗯。Which。

In the same model， they do similar tricks they can't quite get it down to constant。

But they do manage to get it down to log， log， log end。I think this。

This is one of only a very small number of data structures that the right。I think tiny pointers。

 there was another log log log in， but there are very few places where in the wild。

 the best result known is exactly three logs。Usually after a bit more work， people go， oh。

 that's really log start。U so。Open problem if you want something else to do over the summer。

 is add another log。Make it log， log， log， log。嗯。But that's it， we're actually several minutes over。

 I apologize， but thanks， I'm happy to answer questions if you have any。If not。

 I'll see you back here on Thursday for the first two talks。哎。Thanks。



![](img/3cf4d5083a4c37c984a0e83943a5a205_7.png)