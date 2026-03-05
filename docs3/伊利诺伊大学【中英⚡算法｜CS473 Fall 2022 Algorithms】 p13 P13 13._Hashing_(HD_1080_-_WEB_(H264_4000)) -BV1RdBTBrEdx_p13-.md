# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p13 P13 13._Hashing_(HD_1080_-_WEB_(H264_4000)) -BV1RdBTBrEdx_p13-

![](img/af0c945dfb12f7367fe38878e4e11340_0.png)

えそて。啊。

![](img/af0c945dfb12f7367fe38878e4e11340_2.png)

谢谢。Before I present。So we're going hold。合理。Yeah。sorryorrry。

Then we would be that through in the homework。啊系做咯，你个要话。YesDP的。有。Okay。

Thanks everybody for coming again。U。Don't have any administrative things to announce。

 I guess homework five is out。How much for student I we're back to the normal weekly schedule。So。Um。

Today I want to start talking about what is probably the single most。Common use of。

Randomization or what should be the most common use of randomization。U。It's the Almighty hash table。

So。Hopefully， all of you have seen hash tables in some form or another。The idea is that you have。

Some large universe。Which I'll write capital U。啊。That contains data that I might want to store parts of。

😡，嗯。So I'm given a bunch of items from that universe and I want to store them in a table in a way that gives me as close to direct access to those items as possible right so I'm given a subset。

Of some universe U。 And I want to store in。An array。Of。Size M。嗯。And for purposes of discussion。

 I'm going to imagine that my universe consists of numbers between。

That are just W bit binary numbers。So in particular。

 I'm only going to be talking about hashing fixed width items， fixed size items。

 there's a whole addendum onto this theory when you talk about hashing strings。

 it gets more complicated， unfortunately'm not going to be able to get to that。😡。

But at least the intuition behind the theory still generalizes。So。嗯。In order to make this work。

I need something called a hash function。That maps my universe to the set of possible indices。

Of positions in my hash table。And ideally， what I would like。Is。So ideally。

We have H of x not equal to H of y。For all X and Y in the input。

In the data set that we want to store。Okay， this is the goal。This is。

To first approximation what we pretend is true。So if I want to store an item in the hash table。

 I compute a hash value。😡，And then I put the item into that spot in the table。😡。

If I want to look up an item， I compute its hash value and then I look in that spot on the table and that item might come with more than the element from you。

 it might have some other value or values associated with it so it's more like a dictionary or key value store so I look it up by the key and I retrieve the value。

 but essentially it's I just treat it as an array where I have this hash function that translates the item itself to its index in the table。

😡，And the standard fiction。Is this just works？And。So you use it and it works and it's great。

And don't ask too many questions。now。There are a couple of different applications of hashing。

One of those applications is to cryptography security。

 you want to compute a hash value for a document so that。

You know that two different documents somehow magically have two different hash values， so I can say。

 well here's the MD5 hash of my version of the contract， it's the same as the one that you have。

 so we're pretty sure that we signed the same contract。

I'm not going to be talking about cryptographic security here because I'm not competent to talk about cryptographic security。

The only thing that I know is the first commandment of cryptographic hasching do not roll your own hash function。

😡，Leave it to people who know what they're doing。There's a fantastic YouTube channel called Lock Picking Lawyer。

I don't know how many of you have seen it？But basically he says so and so from the master lock company sent me the most recent version of their unpicable lock here。

 let me wave a comb over it， look， it's unlocked， that'll be all for today， thank you bye。

Its just really。People try really hard to make unpable things。And if you know what you're doing。

 you' just victim， same goes for any any kind of security thing， don't don't， don't。

 don't do that yourself。The second thing is you're using this in an algorithm or a program that you're building。

 and you want to rely on this fiction。😡，For the efficiency and correct。

Rerely about strong theoretical practical guarantees about the efficiency of your code。😡。

This first commandment still applies， thou shalt not roll thiny own hash function。

I just want to do something relatively simple。😡，Like here's something that， okay。

 something that you can actually implement that has some guarantees for the context that we have here。

😡，嗯。So。What is？The most common hash function that when people say， hey， just use this。Sorry。

So stuff stop。I'm sorry， say that again。With what？It each relevant。

So I have an item X in my universe， I want to compute hash value， how do I do that？Yeah。Well， okay。

 so if it's just a number between0 and m minus1， I can return x itself and that's a perfect hash function provided my universe is exactly the same size as my hash table。

😡，We saw this when we were doing dynamic programming。😡。

Because there the universe of sub problems was， in fact， the items one through n。😡。

But that's if you want a larger universe。😡，Anyone yeah。Yeah。This is by far。

The most common hash function， this in particular is the very first function described in the Wikipedia article in hash functions。

😡，Anybody notice a problem？😡，So the problem is we want this fiction that each item like maps to。😡。

You， ideal， there are no collisions， but if I hash zero and M。😡，They both go to zero。The end。

And I know this in advance and an all powerful malicious adversary who read your code knows this in advance。

 so you can try to be a little bit more clever。😡，So here's。呃。A version of this。

M times x times the golden ratio。Modam。Okay。This is a hash function that's recommended by Don Kath and his out of computer programming。

 Volume one。😡，It sucks。I can do a little bit of math and I can come up with pairs of integers。😡。

That hash to the same position。There's a nice little golden ratio there and K spends like five， six。

 10 pages analyzing why the golden ratio is the right thing to multiply there。

 so if you're hashing consecutive integers by choosing the golden ratio you're spreading them out in hash table as much as possible。

 but to respond to that， if you're hashing consecutive integers。

 I can think of a much simpler hash function。😡，Subtract the smallest integer and now just use an array。

Um， so no， these， these are bad。Because， in fact any deterministic。Hash functions。

Guarants a collision， guarantees collision。And in fact， it guarantees predictable collisions。Now。😡。

Again， if you put on your crypto hat and go， well， yeah， but there're， you know。

 SHA 256 or ShaA1024 or whatever， whatever we're up to now。

We haven't found any collisions for that well yet。😡。

SHA1 stood as a collision free hash function for about， I don't know。

 it was about 10 years until somebody found a collision。

Because we knew there was going to be a collision， you can't map megabytes down 2000 bits。😡。

Without some pair of megabyte long files hasing to the same thousand bits。

 because there are more megabyte files than there are1 thousand bit strings。

So this is just a matter of doing the right math。😡，So。The only way to have any guarantees at all。😡。

When you're using hash functions。Is to insert some randomness。Now。嗯。On the other hand。诶。

Perfect randomness。Is also useless。So every time I get a new item that I want to put into my hash table or look up in my hash table。

😡，I pull out。My。Oh。Cash of 20 cid dice and I rolled them。And I go okay，1，2，5， six，7，94。

 that's my hash value， put the thing there next time I get the same value。

 I roll my 20 sided dice again。And unless I'm Will wheatheaon and I generate all ones。

I'm going to get different values every time。😡，So there's a very subtle use of randomness that has to go into this。

😡，Right， so the way。That we really do this is we fix。A set， capital H。Of hash functions in advance。

This is sometimes called a family of hash functions。And then when。We create a hash table。We pick。

A hash function out of this family at random。And then we use H that one hash function for the lifetime of the table。

😡，对。So。And I'm going to describe several different ways that this can happen。This。Is often done by。呃。

Really choosing。Prameterters for the hash function。

Which are sometimes called the salt for the hash function。Okay。Um。

But that choice really does need to be rampant。RightOtherwise， again。

 an adversary can figure out what is your algorithm for choosing the hash function from this family and then do the math in its head to figure out how to how to give you collisions this is not just sort of like a theoretical fantasy so one of the places where。

😡，A lot of 21st century hashing research has taken place AT&T。

The reason AT&T cares about hashing is AT&T controls several of the backbone routers for the internet。

😡，roouting involves hashing， here's a packet where does it go， thank you that way， it has to be fast。

 it has to be accurate。😡，Um，Uh， even in the face of， you know， malform packets。

 even in the face of adversarary designed packets and AT&T， they observed。

That they were getting millions of attempted。Deial of service attacks on their backbone routers every day。

People deliberately trying to。😡，Specifically timing attacks on the hash tables。

 trying to get the backbone routers to slow down because some people just want to watch the world burn。

😡，So it was crucial for AT&T to be able to not just theoretically develop。😡，Theoretically scalable。

 high performance， strong guaranteed hash functions。

 but to actually be able to implement them and in particular implement them in specialized hardware so that a single packet can be routed in a。

Small handful of nanoseconds。Okay， so very， very strong theoretical guarantees for efficiency inside those backbone routers now because of the attention paid to how the hash functions were developed。

嗯。All right。So。U。So before I talk about。😡，嗯。How to build a good hash function。

What properties do we want hash functions to have？All right， there's one that almost。

Usually comes to mind。Fairly quickly。Again， it also shows up in the Wikipedia article。

What would he like？To know about。If we hash a particular item into the table。

What's one thing that at least intuitively， we'd like to know？How likely' is baride is something on。

This is actually getting the second order thing that's actually the correct thing。

 which is given two items， we want to know that there's a small probability of collision。

 but this is usually phrased as something else。嗯。To play Ca and I versus cash J。Again。

 this is about pairs of things， what do I wanted about one thing？嗯。最后才是现在位。Well。

 it will because I've chosen a function H at the beginning， so it gives me the same output。

 remember the randomness comes when I create the hash table， not when I get each new item。😡，Yeah。

Youautiform。Okay， so some of you have。Perhaps， read ahead。But again。

 I want to mention this because other people mention it。😡，And and I。

Want to argue that this is the wrong thing to be focusing on。So。H of x equals I。

 any particular index happens with probability1 over m。intuitively。

 what we want is when we pick a hash value， that hash value is uniformly distributed in the table。😡。

Now I'm going to describe for you。A uniform family of hash functions now I'm using my words carefully here。

 these are properties of the family of hash functions that we fix in advance。😡。

These are not properties of single hash functions because single hash functions are just function input output。

 there's no the only probability is in the choice of which function we chose out of that family。

 right？😡，So， here is。A。So really， I want to say the probability is over this choice of hash function。

😡，But this is really bad， Okay， so I'm going to define a family of hash functions， okay， ready。

 H0 of x is zero for all x。H1 of x is1 for all x。HM minus1 equals M minus1。For all X。The family H0。

 H1 up through HM minus1。Is uniform？俾。😊，So this is the following hash function。😡。

What do you want to hash？80 diamonds， what do you want to hash， 80 diamonds。

 what do you want to hash， 80 diamonds， what do you want to hash， 80 diamonds？It's perfectly uniform。

This card has the same probability as any other card。😡，Of being chosen out of the deck。

And so the probability of getting any particular hash value is1 over 52。😡。

But this is utterly useless。As a hash function。And obviously so。😡，So。啱。

The moral of this story is sometimes Wikipedia is stupid。😡，It's not Wikipedia's fault。Because both。

Um， you know， modular hashing and uniformity are held up in almost every algorithm's textbook as the thing to do。

😡，When it's。Not the thing to do。😡，Um。So we don't really care about uniformity。

 this is not what we want， what we want instead is something a little bit more subtle called universality。

😡，Again， probability over the random choice of hash function。That two things hash to the same value。

😡，Is small。No matter what those two items are。So。You too。嗯。

I'm going to pick my random hash function and the probability that you two get the same hash value is one over the size of the table。

😡，Right。Now this is1 over M and not one over m squared because really you can think of it as suppose I fix H of x。

 then I want that there are still M possibilities for H of Y。😡。

And only one of them should give me a collision， yeah。It really it's less than or equal to。

And there are families with hash functions， I mean。

 an ideal random hash function would give you exactly what' at there。

If every hash value were completely independent of every other hash value。

Every other set of hash values then you would get exactly one M there some of the families I'm going to describe actually are better than universal in that you get strictly less than one of M probability there。

 which is weird， but okay。That's the way math works。Um。And often if you're really， you know。

 if you want to put them on big old glasses。You can say， you know near universal。

 I can put big O here。 you know， at most five ofM， that's probably anything that really needs universality。

 probably really only needs near universality unless you really care about the leading constants。😡。

Okay。嗯。Okay。So。Let's do。There there are other versions of this where a stronger version of universality just sometimes called strongly universal or to uniform is that。

😡，The the hash values for pairs of items are uniformly distributed over the space of all pairs of indices。

😡，Um there is pairwise independence， which means that if I know something about the hash value of x。

 that gives me no information at all about the hash value of y。😡。

And these things are all very closely related to each other， but not exactly the same。😡。

I'm mostly going to refer to the notes for specific technical details about the definitions。

But of course， I'm happy to answer any questions。So let me show probably the simplest example of how function hash tables are kind of implemented。

😡，And then showed that universality actually implies something about the efficiency of that implementation。

So。This is a question of what happens when you get collisions。😡。

You're never going to be able to avoid collisions， so you have to change。😡。

Your table from a simple array to something else。In order to resolve those collisions。So。Yeah。

So we'll actually that's something called linear probing。

 so when you get you get a hash value and look at that point on the table。

 if it's already occupied and you're trying to put something in or if it doesn't have the right key when you're looking something up。

 you then just sort of scan to the right until you find an open spot or until you find the thing you're looking for。

😡，That's easy to implement it's harder to prove things about we'll get there on Thursday。

But what's another way to do it？对。Yeah， so there's something called chaining。SoSo you imagine。

Building。And your hash table。As a as a simple array。

 but instead of just storing key value pairs in the array。

 you store a list of key value pairs in the array， so maybe it looks something like。This。对。系。

By the way， you've seen this picture before， you the context。What is this data structure？

I'll give you a hint， it's usually drawn like this。That's an adjacency list。

I don't know why adjacency lists are always drawn with the array vertical and the link list horizontal。

 but whereas chain hash tables are always drawn with the array horizontal and the lists going down。

It's the same data structure。Okay， so this is。嗯。What's called a chained。Aash table。

So you resolve collisions。By。Storing a list。At。Every entry T ofI。对。Okay。嗯。

Now if I want to look up an entry X。😡，The expected time to look up X。Is one plus。But on the order。

 I'm not going to worry about constants here， one plus the expected length。🤢。

Of the chain containing X。😡，Which I can write as order one plus。

The expected number of y such that H of x equals H of y。🤢，Right。So if x， if x is a。呃。

Here I'm really thinking of this as looking up something that's not in the table just to keep things simple。

 right？嗯。But this is。One plus the sum over all y the set that I care about。

Of the probability that H of x equals H of y。By the usual。

 I'm expressing an expected sum of 01 variables as a sum of probabilities。😡，But now that probability。

 if I have a universal family of hash functions is one over M， so the hash function。

The expected value comes out to be n over M。So as long as the size of my hash table。

Is not too much smaller than the number of items that I'm storing in the hash table。

The expected time to look something up is a constant。

So if I want to store a thousand things in a chain hash table。

 I should use a hash table that the top level arrays。A few hundred， at least。

If I try to make the hash table smaller， the probability of a collision goes up and therefore the expected time to look things up and the table goes up。

😡，U。I suppose I should also say this is really less than or equal to because I could do other things like keep the linked list in random order that would get rid of a power of two。

 I could implement the chain not as a linked list but as a binary search tree that would turn that L into a log instead of a linear search。

Or if I really wanted to be fancy， I could use recursion and implement the chains as hash tables。

Good。Which we'll come back to。We'll come back to it's not as crazy as it sounds。

 but even if I just use standard linked lists， which is usually what people implement right off the bat they just need something quick and dirty you get。

😡，Constant provided the load of the hash table is。😡，U。Is usually referred to as alpha is the。

How full the table is。For chained hash tables， this number can be bigger than one。😡。

If you want to use an open address table where you do like linear chaining， or sorry。😡。

Is that what it's called？Linear overflow， you want to use a for loop to scan through the table when you see a collision。

 then the data structure consists entirely of an array of Liedm。

 so the load factor is by definition at most one。😡，generallyenerally。

 this is the thing that we want to aim for being a constant。Now。嗯。是。

You don't necessarily know N in advance， so what do you do？😡，How big a hash table do you make？😡。

You do dynamic resizing of the table。😡，Okay， so what Python does？😡，Which is good。

 Python does the right thing。What Python does。Is。U。When you insert things into the table。

 it tries to do the insertion， I think it uses linear overflow。😡。

But when the number of empty spots in the table。😡，Exceeds a third of the size of the table。

It doubles the table。😡，When you delete things， you just draw an X over the thing。😡。

You need to do that for the overflow algorithms to work correctly。

 you can't reorganize things afterwards so when the only way you ever shrink your tables is when you delete things and so you have a bunch of what the author calls Tds in your table that's a technical term but then you later insert something you notice that your tables full of crap so you rebuild it from scratch using only the items that you think are live and build a smaller table。

😡，But the standard advice is。😡，When the number of items in your table is more than。

 say three quarters the size of your table， double it when it falls below about half of the size of the table or a third of the size of the table。

 you cut it in half。😡，And that is enough that in an amortized sense。

 all the insertions and deletions will itll be just like you had a constant load factor the whole time with the right table size。

😡，Okay so I'm not going to worry about this growing and shrinking。

 although obviously in an industrial application of hashing， you will have to worry about that。系。

Okay。So。How does one build？A universal family of hash functions。So。I'm going to give you。嗯。five。😡。

Examples， I'm not going to go through the proofs of these。

 three of them they're already in the notes， one of them is in your homework。😡，Okay so。

Almost all of these date back。To a single paper by Carter and Wegman。

Um around sometime in the late 1960s， early 1970s， these are the first people who really systematically studied hashing。

 although the idea of hashing had gone back。嗯。In the context of computer programming back to the 1940s。

 in other contexts back to antiquity。😡，So what they did they defined is something called。

Multiplicicative hashing。嗯。So I'm going to。Choose a prime number。

P that is bigger than the size of my universe。So if my universe is all 32 bit integers。

Then I need to choose a 33 or 34 bit prime number。😡。

If I need to hash double precision floating point numbers at 64 bits。

 then I need to choose a 66 bit prime number。Um。Okay。So let me define。

Racket P as the integers from0 to p minus1。And bracket P plus as the integerters from 1 to p minus1。

嗯。That'll come up later。Choose my salt A out of this set。😡，P+ uniformly at random。

And then I define my hash function with respect to that A。As。AX。Maud P。Maud M。

So it smells like the division method in that you do have this mod M going on at the beginning but。😡。

What's happening here in the AX mod P？😡，Is。Because of the way prime numbers work。

 and there's a little bit of elementary number theory here。😡。

By multiplying x by a random number between 1 and p minus1。

 you're intuitively randomly mapping x to some number uniformly chosen between0 and p minus1。😡。

Now it's not exactly what happens， but that's a good enough intuition for what happens and in particular if you take two numbers x and y。

😡，Theyre difference。AX mod P minus Ay mod P is going to be uniformly distributed。😡。

In the range between0 and p minus one。And so the probability of getting a collision at this first level is going to be about one over P and then mod M takes that probability down to one over m okay。

 so this isn't quite universal。😡，But it is near universal。So the probability of getting a collision。

嗯。Is at most to over。And this is easy enough to implement if you。Can finde a large prime number。

The proof boils down， like I said， to doing a bit of number theory。If you don't。

 if you really want universal。😡，Then what you can define instead。It's a two parameter F function。

Just almost the same。You just add an offset。So I'm going to choose。A。

 uniformly random from P plus and B uniformly random from P。This is universal。It's also uniform。

 which the previous scheme wasn't， why is that that family of hash functions up there multiplicative hashing。

 why is that not uniform？你如是。Yes， the probability that h to0 is equal to 1 is zero。😡。

Probity H of zero is equal to zero is one。Zero is not mapped spread out through the table。

 it is always mapped to zero。😡，And that's not a problem if you want universality。

 the probability that zero and 17 collide is still about two over the tableside。😡，U。

But if you add this random offset。😡，Which again is pretty easy to implement once you've already done the first one。

Then you get a truly universal family of hash function that also happens to be uniform and in fact it's too uniform。

 meaning if you take any two items and look at their hash values。

 that's equally likely to be any pair of entries between。😡，Zero and a minus one。系。

But crime numbers are not necessarily what you want。Because prime numbers are hard。

So there's another one called binary multiplication。This one is actually again。

 described in the notes including the proof， but it's a little。It's a little hairier to actually do。

So remember， I'm assuming here that my universe is the set of W bit binary numbers。So as a salt。

 I literally choose a random item from my universe。😡，嗯。

And let me assume for simplicity that the table size is also a power of two。

 so I'm mapping W bit words to L bit labels。😡，W is say， 64 and L is say 12。Right。

So here is my hash function。It looks a lot scarier than it is。Hey。😊。

So I do multiplication again now instead of mod P， I take mod to do the W if W is literally the word size is my computer。

😡，I'm just。Multiplying two w bit numbers and getting a W bit result。

But then I do this weird thing where I shift it down and then take the floor。😡。

So one way to think about this is here's my item。X。

 I'm going to multiply that item by some other number A。 I'm going to get a product。

And then what I'm really pulling out。Or。These。Ebits。Right， so I'm multiplying two w bit things。

 I get a w bit result。😡，That shouldn't be a mo， that should be a div。系on。嗯。

So if I actually want to implement this in C。Be something that looks like this。I don't no。

 it was right the first time。So this is what your code looks like for your hash function。

This family of hash functions is again， not universal， but it's near universal。

 which is good enough to get guaranteed results for this kind of chain hashting thing。😡，That's three。

Okay。Or this is the one that shows up in your homework。And。This is actually。

The one that I would recommend implementing in practice if you want stronger guarantees。😡，Um。

 mostly just because I've read more papers that use variants of tabulation hashing than anything else。

Okay so the idea， again， I'm going to assume that the size of my universe。

Is2 to the W and the M is2 to the L。 So I'm hashing W bit words into L bit labels。

 But I'm going to think of every item。In my universe as consisting not of one word with W bits。

 but of two words with W over two bits。😡，Take the high order W over 2， low order W2。

 think of them as two fields in an order pair。😡，嗯。H。So。I'm going to define。Two random。A raise。

A goes from zero to2 to the w over  two minus1。B goes from zero to to the W over2 minus1。

U filledilled。With。Random。Ebit labels。So if I'm hashing。

 this is not going to work very well if I'm trying to hash Ws 64 because then I need to build two tables each of size two to the 32。

 but if I'm hashing 32 bit things，😡，Building two tables of size2 to this 16 is not so onerous。Okay。

 so if I'm hashing， say， 32 bits down to 10 bits， then I'm going to build two tables。😡。

Each storing 65，536。Random 10 bit strikes。嗯。And then I'm going to define my hash function。

Given now a single item in the universe， remember， I think of that as two small words。😡。

This is lookup X， exclusive or， lookup Y。So again， it's sort of intuitive that this works well because I'm taking random bits of noise and exclusive or together and the random bits of noise again。

😡，So this。Turns out to be。啊。Universal。It turns out to be too uniform。In fact。

 it turns out to be three uniform， meaning every triple of hash values is equally likely to be any triple of indices。

😡，But it's not for uniform。And this is easy to generalize to more tables that are of smaller size。

 so if I wanted to hash 64 bit things， I would build four tables。😡，Each indexed by a 16 bit word。

And then I would think of my 64 bit key that I want to hash as a quadruple。😡。

I would look up four different random things from my four different tables and exclusive or all four together and again exactly the same statistical properties。

 two uniform three uniform， not four uniform is is a bit weird that by adding more tables。

 I don't get more independence or more uniformity， but that's how it works out。系。So again。

 this is the one that if I were to implement something。

 this is what I would implement just because I know that there are stronger。

 more subtle guarantees that I'm not going to be able to talk about attached to this。😡，对。Um。

And then the last one。Is。呃。Linear algebra。We all like linear algebra。

So I'm going to build a random matrix that is。Oh。Two to the W this way and2 to the L this way。

And this is a random matrix of zeros and ones。And then I think of my item， oh， sorry， they say2 to W。

 I'm meant W。Much better。So 64 bit keys， I'm going to have a matrix with 64 columns and if I want 10 bit labels。

 it'll have 10 rows。And then I do matrix multiplication， but I do the matrix multiplication mod too。

😡，So everything happening here is。Moud two， which means instead of addition， I'm doing exclusive war。

Inside the that matrix vector multiplication。So， I。Build a random matrix。

 and then my hash function multiplies that random random matrix by the vector that encodes the item I want and I get out vector that encodes the address that I want。

嗯。This is， again， near universal。And similar to multiplicative hashing。

 if I add a random offset vector to the result， then I can get it to be truly universal and uniform and things like that。

So again， not terribly difficult either to implement or to analyze but reasonably strong performance guarantees。

Okay。All right。嗯。Questions about how to make cash functions。Okay。Now。

When we start talking about linear probing， I'm going to need a family of hash functions that has even stronger guarantees。

😡，It's not going to be enough to look at pairwise collisions。

 I'm going to have to look at interactions among larger collections of hash values。

 the only one of these that's easy to show generalizes is this one。😡。

If I want something that is three uniform， instead of defining a random polynomial of degree one。

 I pick out three numbers and I build a random polynomial degree two。😡，If I want seven uniform。

 I pick out seven random numbers and build a random polynomial of degree six。

So a plus bx squared plus cx cubed， et cetera， et cetera， mod P mod M。嗯。

There are versions of tabulation hashing that also do better but。They're more complicated。Yeah。

All right。So if I build this particular。嗯。One of these families at hash functions。

And I use simple chaining to resolve collisions that when I'm guaranteed for any particular search。

 the expected time for that search is going to be constant。😡。

But now let's think again about the context。嗯。Now。啊。

Ignore for the moment the fact that in real internet routers。

 the set of things I'm routing to is dynamically changing all the time。

 but let's just assume I have a fixed set of things。That I stored a fixed hash table。And then。嗯。

I want to do lookups over and over again。Okay。Notice that I did not say。

The expected worst case lookup time is a constant， said for any particular item。

 the expected time to look up that item is a constant。😡。

Looking up different items and watching how long it takes the hash table to respond to me。

I might learn something about how many collisions there are with certain items。

 I might notice that when I hash 473， it takes just a little bit longer than than when I try to hash 225。

😡，So me being the evil genius that I am， I'm going to ask the hash table for 473 more often。😡。

And over time， I'm going to learn basically where things are in the hash table。

 and then I can something's going to be slow and I'm going to attack it。😡，And。呃。There's， in fact。

 a theorem about this， right？So。Re item X， we have。knowThe expected value of the size。

 the length of the chain containing x。Is constant， but what we want。Is the expected max length？

To be constant。Right， unfortunately， we're not going to get that。Even if。Somehow magically。

I could assign a completely independent random number to every item in the universe。😡。

So an absolutely perfect perfectly random hash function。ok。

So if I use what's called ideal random hashing。Then the maximum value， maximum length of any。Chain。

For a table of where M equals n， meaning I'm hashing n things into a table of size n。Is。F。

Roughly log log in with high probability。😡，So what this says is if I'm hashing。

A million things into a table of size a million。So a million is about two to the 20。That。

The largest chain is going to have size if I pretend that theta is a1。😡，20 over log 26。Okay。

 which is maybe not terribly bad， but if I look at this for large values of N。

 that means that there's always going to be some query into my ideal random hash function table。😡。

That makes the performance of the table almost as bad as if I just use a binary search tree。😡。

Any particular query， if I fix the query in advance and then build the hash table and then query is going to be constant。

 but if I build the hash table once from a random hash function，😡。

There's going to be some query that is going to require log n over log log n time。😡。

With high probability。OkayIt's no worse than that， it's also no better than that。

And this is one of the counterintuitive things about randomness。

If I generate a bunch of random numbers， don't look random， they don't look uniform。😡，They clump。

So just take a10 sided die。😡，You all have 10 sided dice， right， and roll it 10 times。Um。

 or just ask among yourselves about your birthdays。

 assuminging birthdays are reasonably uniformly distributed。

 there are enough people in this room that there's probably three people that have the same birthday。

Even though there are only 365 days in a year。once you have about 30 people in a room。

 chances are pretty good that two of them have the same birthday。Okay。

This is just an extension of that birthday paradox。On the other hand。

If somehow I could make my table size be significantly larger。Then。

The number of items that I'm storing in the table， then the expected number of collisions。Is it most？

Well their end choose two pairs。Of things that could collide。And for each one of those。

 assuming I'm using universal hashing， the probability of collision is at most one over M。So。Well。

 if I take m over n squared， this is less than a half。So if I can make my table really big。

I can make the expected number of collisions is going to be smaller than one。😡。

And if I work a little further。The probability there are going to be any collisions。

Is it is at most half？So most of the time， the hash table will in fact be perfect。😡。

Provided that is big enough。So I have this weird trade off if I make my table too small。😡。

Big enough to store everything。But just barely。Some chain is going to be really big。

 I'm going to get a large set of things that collide。😡，I can avoid that。

 but only by making my table really， really big。😡，Roughly the square of the size of the set that I'm storing。

So what I want to show you is a way of。Getting the best of both worlds。

How to get a data structure that has expected linear size。😡。

So the total size of the data structure is order N。😡，Inex。And。You can do lookups in constant time。

Not constant expected time， constant time。Okay。And this is something that is。Rather。Euphemistically。

 I think。Called perfectf Haing。So the idea is I'm going to build a chained hash table。对。Of size n。

But then each chain I'm going to implement。As another hash table。

With the size of this hash table sitting at index I。

Is equal to the square of the number of items that have hash value I。Okay， so。Maybe you know。

 12 things hashed into that slot in the table that's fine。

 I'm going to build a secondary hash table of size 144。😡，In practice。

 I'm really going to build something that where the size is the next power of two larger than the square of n sub I。

 but all this survives the same sort of dynamic resizing arguments that we use for simple tables。

Okay。Now， this doesn't seem like it would help。😡，And I do want to be I do want to be you know careful about this。

 so I have a。Primary。Hash function。H is from a universal family。And inside each secondary table。

 I have another secondary hash function。H sub I also from。A universal family。

And these are independent。Meaning that。The well， first of all。

 the sizes of the various secondary hash tables are going to be different from each other。

 so I'm really choosing functions from different families altogether。

 but the choice of the salt parameter that I choose randomly for this secondary hash table has nothing to do whatsoever with the salt that I choose for this other secondary hash table or with the salt that I chose for the primary hash table。

 all of these hash tables， all these component hash tables are completely independent from each other。

Okay。So。How do we actually do a search？Okay， so I'm going to write H is。Oh， actually， let me。

Call it I is H of x。Okay， and then。J is H5 x。And then I return。

The secondary hash table at position I。Add index J。I guess if we're doing Python lists of lists。

 it would look like this。咁。Yes。Now， notice something about this。Where do I handle collisions？呃，拿个。

他是我他是是。Yeah， but I claim I don't need to。I made my secondary hash tables big enough。😡。

That there are no collisions。😡，So。Remember the previous line here？😡。

The probability that I have if I build a table of size n squared。

 the probability that I get any collisions at all is less than a half。

 so if I ever get any collisions I throw that table out choose a new hash function and start over。😡。

In expectation， I need to start over at most once。😡，Before I get a hash table that actually works。

So once I'm done building the hash table， once I've built my secondary hash tables so that they have no collisions。

 my lookup function doesn't need to worry about collisions because I know there aren't any。😡，Yeah。

今年没すです。how they they。Okay， so I'm imagining that I start with just the set of items I want to hash I build my primary hash table。

 I do an initial pass， counting how many things hash to each thing。

 then I allocate the secondary arrays， and then make a second pass actually storing them in that second pass if I see any collisions I restart that secondary table。

😡，I mean， you can do more complicated things if things are dynamically coming in and out。😡。

In reality， what I would probably do is at this stage， I would do linear overflow。

Until the table got too full， and then I'd rebuild。

But to fold in now means that the number of items in the table is more than twice the square root of the table size。

Or something like that。Yeah。😊，I said earlier about this evening everything for added that state。

That's right。I haven't done that analysis yet。So notice the size of this data structure altogether。😡。

Is a random variable。 I don't know how big N semi I is a priori， yeah。在还。Okay。

 I'm going to give you 1064 bit integers， I want you to build able a data structure that allows me to look them up quickly。

😡，Are you going to use an array of size2 to the 64？No。咩晒。And okay。

 so I can pre assigns a value to each of those thousand integers now I need somewhere to store the values that I've assigned to each of those thousand0 integers。

 what data structure would you propose that I use for that？😡。

That's the problem we're trying to solve。Right， so yeah， in principle， you think， yeah。

 if I know in advance what I'm going to store。Why do I need to build a hash table？

It's not enough just to sort of know I need to be able to quickly compute with those thousand things。

😡，嗯。Attach other values to them。And things like that。Okay， so what's the size of this hash table。

 the space that this uses is well， n for the primary table plus the sum over all i from1 to n of n sub i squared。

Okay， but of course， this is a random variable， so what I'm really interested in is the expected space。

hich by linearity I can push the expected values all the way in through the summation。

 so what I'm really interested in here is what's the expected value of n sub I squared。😡，系。So。诶。

This is E， let's see。Ex value of n sub I squared is。嗯。Yeah。Not a second。没人高兴。Yeah。

 if you the expected value of n sub I is one。But remember。

 you can't get the expected value of the square by squaring the expectation。

You can't treat expected value， you can't treat random variables as though they were equal to their expectation when you're computing these things。

Um。Sorry， I need to look at this carefully。So this is。The expected value of some overall all。X and Y。

Of the indicator variable， H of x is equal to I and H of y is equal to I。

 and x and y both go from one to。so this is。I'm going to break this into two parts。

 one where x and y are equal and one where x and y are not equal。

We've kind of seen this analysis before。嗯。停。Squaing a bit leaves the bit alone。

So the square of 0 is0， the square of1 is1。 so this first sum is just n sub I the number of things that hash into spot I and the expected value of that is1。

Two times the expected value over x less than y of。H the indicator H of x equals H of y equals I。系。嗯。

No。Maybe I need to actually pull the summation of over。To make that a little bit easier。

The summation over eye。Of。And sub I squared is now。N plus twice the expected value of sum over i。

 some over x less than y。Of。The indicator x of h of x equals H of y equals I。

This is n plus twice the expected value now I'm going to use the fundamental theorem of comminatorics。

 addition is commutative to swap these two summations。

 and then that comes down to x is less than y times the indicator H of x equals H of y。

Expected value of sum of indicators is a sum of probabilities。

But I know that the probability because I use the universal family hash functions， this is at most。

Two times the sum of x less than y of1 over n。Which is。N plus 2 times n choose 2 times 1 over n。

Which is less than 3N。So。I think if I'd carried through the calculations。

 if I could assume to uniformity， it would have been easier， I just wanted to assume universality。

The moral of the story is。It's not only true that the expected number of things in a secondary hash table is constant。

😡，It's the square， the expected value of the square of the number of things in a secondary hash table is constant and so even though there is some possibility。

😡，In fact， it's quite likely that one of these secondary hash tables is going to have size log squared n。

😡，嗯。Altogether， the total size of all of those secondary tables is most2 end。😡。

And there's the last end for the top for the primary table。So I'm using a linear amount of space。😡。

I have a hash function that I can evaluate in constant time。😡。

I can guarantee lookups in constant expected time。At least all in expectation。😡。

Provided that I choose my hash function at random from this universal family。

 of which there are several choices that you could implement。Now you can really do hashing。

And believe it and understand why it works and in what sense do I mean that it works？嗯。

What I'm going to talk about tomorrow or Thursday is how to do things like this when you don't have secondary data structures at all。

😡，It requires a little bit more。Effort， and then I'll spend a little bit of time。😡。

Talking about more recent results in hashing just because I think they're cool。All right。

 thanks everybody。happyy to answer questions up front。嗯我了。And's all that。



![](img/af0c945dfb12f7367fe38878e4e11340_4.png)

。