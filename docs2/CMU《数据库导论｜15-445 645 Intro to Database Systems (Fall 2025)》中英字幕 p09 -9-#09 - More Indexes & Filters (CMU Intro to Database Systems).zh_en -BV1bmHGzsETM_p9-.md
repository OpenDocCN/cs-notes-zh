# CMU《数据库导论｜15-445 645 Intro to Database Systems (Fall 2025)》中英字幕 p09 -9-#09 - More Indexes & Filters (CMU Intro to Database Systems).zh_en -BV1bmHGzsETM_p9-

![](img/2eed7525e1bad4e3ff590c615f25b11c_0.png)

🎼给我给我。🎼Let's check。🎼换这我可。🎼P。Rund of applause for DJ Cash。👏Again， thank you for being here。

 A lot to cover today。Have you heard from your friend， That's a fat history。 Yeah， he's doing good。

 He's doing better。 Okay， picked up the charge though。You could to a charge in London。For boy。

I can't tell you。Oh man。 Alright。's， that's his problem。 We can't's in London。

 we can't help him here。 Allright， so let's jump the databases because that's。

 that's the most important thing of life。 So again。

 this is just a reminder for everything for you guys is do。 Project one is do coming up。

 Home 3 will be out today， and that'll be due in。😊，In a few weeks。

 and then mid midterm exam again will be in class on October 8th and it'll cover lecture zero of that。

 lecture1 to lecture 11， okay， and then we'll post the study guide this weekend early or like Monday next week。

 okay？Any questions about any of this？Again we have the special office hours this Saturday at 3 pm in Gates on 5207 that's one of the lab rooms。

 again there'll be multiple Ts there， we'll use OHQ to the queuee yourself up and come and ask questions okay。

😡，All right， so let's continue on our discussion on our journey about indexes and the data structures we're going to use to build these things inside of our system today's class we want to talk about indexes and filters。

 we' sort of mention filters briefly early in the semester when mention balloon filters we haven't describe what they are yet。

 but I just want to highlight the distinction between what a filter is and what an index is and we're going to need both and sometimes you'll put a filter in your index to help sort of speed speed up certain operations。

So an index that's going to be a data structure like a hash table or a B plus tree or the things we've talked about so far that we're going to use as a way to find In records that we want or sets of records that we want based on some attribute within the table。

 like a column in the table we want to a quick lookup to find all the users or all the people with at cs。

cmu。edduu email address right we can use the index to go find that right so it'll give us for some key it'll give us an exact location where we can go find the data we want or at least a starting point for the data that we want。

😡，A filter is going to be a going to be like an index， but instead of being able to tell us。

Does this thing exist and where does exist in our tables？

AFil there iss going to even tell us just set membership， does this thing exist， yes or no。

 And it can't tell you where it is。 It's just going to tell you that it does exist。😡。

RightNow the tricky is going to be when we look at Bferss。

 these we what to call probabilistic data structures where it will tell you that it's likely that the key you're looking for exists。

 but it may actually give you a false positive， it may tell you actually it exists when it actually doesn't。

 it'll guarantee no false negatives， so if it says it doesn't exist， it definitely doesn not exist。

 but it may give you false positism we'll see what that looks like。😡。

So I'm quickly describe what a bloomlo filterer is and then we'll see how we can tack this on to other data structures we've been going through okay so today we sort of do a smors borg of a bunch of other data structures we're going to want to use in our data system and we'll start off with Blo filters and then we'll jump to skip list tries inverted indexes and vector indexes Quick show of hands who here has heard of a know what a bloom filterer is。

😡，Less than 10%， who here knows what a skip list is。Ah， about that same。

 we're not tries and reddx trees。Yep， okay， inverted indexes。

Few and then vector indexes I'm assuming maybe HNSW， IVV FF flat。😡，Nobody perfect， all right。

 so we'll see as we go along in today's lecture as well that we're going to use some of these early data structures were described as building blocks to make more complicated things or we'll apply some of the ideas we've used in other parts of the database system and we we can use them to enhance these different data structures。

😡，All right， so let's start off with B filters， these are super useful， super common。

 pretty use in almost every single database system。😡。

And it's a probabil data structure where it's going to be able to tell you whether a key exists in your set or whether it does not exist。

😡，RightAnd the term probabilistic means that like there will be some bitter randomness to it where it could tell you something exists。

 even though it doesn't， but it's guaranteed to never tell you something exists something that does not exist when it actually does so it give you false positives with and you can tune it based on how what the false positive rate you want it to be depending on the size and the number hash function you're going to use。

 but again you'll never get false negatives。😡，So B Foer is only going to be able to give you basically two operations。

 the API only has two things， you can insert a key and you can do a lookup a key。

 you can't delete a key。😡，We'll see how to handle that in a second with other other data structures。

 but you can only do lookups， you can only do。Ins。And basically way it's going to work is that there's going to be this bitmap。

Our bit vector， like the thing of like one hot encoing that we're going to use to keep track of whether a key hash is some location in the bitMap。

 and we can use multiple hash functions to land at different locations to ensure that to change the false positive rate or change the accuracy of the data structure。

😡，So this can be widely used for like imageory caches， we want to use this when we do joins。

 we can also put these things in our hash tables， put these things in our be bsteries。

 we can use these things everywhere because they're really compact。

So here's a basic bloom filter that has eight bits right and initially when I first start the data structure。

 they're all set to zero， right？😡，So say I'm going to insert a key， I want to insert the rhythmIS。

So for this blue filterer， I have eight bits， I'm going to use two hash functions。😡。

You can calibrate how many hehtons you want， you can calibrate how what size you。

 the bitmap you want to be make this work in PowerPoin， I'm doing two functions with eight bits。😡。

So what' idea is I'm going to hash it these two hash functions。

 and again it'll be the same algorithm， the same hash function algorithm， like Murber hash。

 city hash， whatever you want， just give it a different seed so that it permes it in a different way for each invocation。

😡，So say that I get now two different hash values， 222，4444。

 and I'm going to modify the number of bits I have in my blue filter bit bit vector， six and four。

 so now I'm just going to jump into those different offsets and set those bits to one。😡。

That's pretty cheap， that's fast to do。Let me insert the Ger。sameme thing， hashher twice。

 modify by the number of locations or spots I have in my bitmap。

 and then that's going to point me to now two different locations， I set those bits to one。😡。

So now I'm going to do a look up on Rsm。😡，Do the same thing we're going to hash it again and I'm going to get to the same bit locations and then long as whatever I'm pointing at as long as all the bits are set to one。

😡，Then I know the key is know， I'm going to say the key exists。

And this is why we can't have false negatives， right because if one of those bits were zero。

Then I would have never been able to insert RISa because when I hashed to put it in there。

 I had seven to one。so this will always return true and it' will be this case here。

 it's correct but I do look on Raycon the chef。Same thing I hash it twice now I get five and three one of those bits is set to zero。

 so I know that this key was not inserted， so I said it the false。😡，嗯。Now I look up ODB。

 rest and peace， same thing， hashher twice， get two different locations。😡，I didn't insert ODB。

 but my two hash locations that I land on are both set the one。😡，So in this case here。

 I'm going to say true。😡，And this is an example of the false positive。

Both locations are set to one that I'm looking up on， but I know I didn't insert this key。😡。

So now you can see why if I have more hash functions， I can have a higher guarantee of。😡。

Of this thing producing a， you know a correct answer。 But now if I have a really small bitmap。

 then if I have a lot of hash functions， then like。I made to be setting them all to one。

 and then it's basically useless。😡，So there's a bit of a balance on how once you want to the size and the how much cheap you want to do。

 we're talking maybe kilobytes， these things aren't that big relative to the size of large data sets。

😡，You guys did the countman sketch， that's another example for Project zero。

 that's another example of our publicistic data structure where in exchange for not having to store giant list of all the possible keys I could have to keep count of everything。

 I allowed myself to have some wrong answers。😡，With some guarantee of that probability。

Preciate it for it， right？And as about optimization as you can do to make these things real fast。

 really efficient for this class again， we're not worried about cashline stuff and the CPU。

 we get ignore of that you don't understand the basic data structure， it's pretty small。

 it's pretty compact， it's pretty fast to do this lookup。

Much faster than doing a probe and a hash table if you get the scan through because now I'm comparing hashes and pairing keys as I go along。

 so when we talk about doing hash joins in a few weeks。

 some systems will build a bloom filter in front of the hash table so you probe the bloom filter first。

If it comes back as negative， then you know it can't be in your hash table so you don't probe the hash table。

 if this comes back as positive， then you go probe the hash table to see whether it actually exists。

😡，Right sometimes it's called a bloom join。 a B has join， basic idea。 Well again。

 this is a useful data structure we can use in a bunch different locations。

Other filters we may want to consider also is a accounting bloom filter for this one。

 you basically have multiple levels of。😡，Of bitmaps。

 and this allows you then to also then do deletes。😡。

You sort of sort of stage things out right and instead of sort single bits。

 I can store actually the account。😡，Right so I know if I decrement the count to zero。

 I know I've removed something， but I still have to guarantee where I can have false positive but not false negatives yes the question is how do you update a balloonfer if you delete a key you can't。

😡，You can。Because again， if I delete going back here， if I delete。Who has to my。

 Risa hash to what three？Right or four I so if I or six hey take the six and then one of these guys hash to it right or maybe I didn't see that by anyway。

 if I delete one of these hashes or one of these bits for one key。

 then I don't know where are the keys I have in here because it says a bits so I made end up removing a key removing a bit from a key that should be in there and now I'm going to get false negatives。

This means that the positive rate of fall was increase。

The question is that the false positive rate will increase when sorry dont you don't delete keys with these。

 you just don't the way you want to delete keys， you want to use accounting B filter where instead of sorting a bit。

 you sort of count。😡，And that solves that problem。There's another version of this called Koo F and the basic ideas is like。

Its it's kind of like the K hash table and instead storing the entire key。

 You just store a small representation called a fingerprint of， of the。

Of the key and then that guarantees that if I remove it the fingerprint gets removed andm I still have the guarantee that I。

You can have false positive， but not false negatives。And the last one is called a sync ring filter。

 we'll see this in a second when we talk about tries。

 but this basically be a compact version of a Radix tree where not only can I do set membership queries。

 but I can do range membership queries， like does this key exist within some range of values？

Whereas all these other ones cannot do that。So the bottom two here。

 we're then to here at CMU cuckoo F was created by Dave Anderson at his students in computer science department and then the same range filter or SurF。

 that was also created by a student that I co with Dave Anderson who's now a faculty Esh Wa and that again's another cool data structure and actually in Redis you can actually explicitly ask for cuoo filter and they have their own like builtin type for this again gives you that same probability the same guarantees you want for actually a value you can store。

The question， what's the accounting move or anment sketch。

 countment sketch is giving you approximate cardinality。Like for a given key。

 how many times have I seen it？Kellie Luifer just says like does this key exist。

 but then if I do multiple keys I can delete it Conlie Luford whatt handle the deletes won't tell you the exact number of times you've seen the key。

你个证面的保车咗。呃。So even as you can do same account sketch。I mean count sketch again。

 it's meant to track cardinality， this is just trying to say like does the key exist？

Calies Act can do more than this than a accounting limitor。好月。So so Blo filters， again。

 that's the most important filter you need to know about。 it's used everywhere。

 These other ones that has talked about they're used。

 but they're not not as common as bloom filters because they're not as fast as a bloom filter， right。

All right， so last class when we talked about the B plus stream。

 switching over now to index data structures。😡，We talked about how the leaf nodes are essentially a sorted linked list。

😡，And then all the inner nodes and the root nodes above it with those guidepost keys。

 the scriminator keys， they're basically allowing you to jump into。

The link list define the data which you want more quickly， right？So。If now we want to do， you know。

 if we just use a linked list， we end up with ON searches on average case。

 right because any single time we always look for something。

 we may have to scan the entire entire link list to find the thing we want we're not even talking about how to maintain it。

 but it's basically the same right？😡，So a simple like landscape would be sort of like this， right？

Key followed by a pointer to the next key， right？And so if we want to make this go faster。

 we can do what the B plus tree did was as things get inserted。😡。

You start keeping track of the guidepost as you go down just figure out when you would even go left and right to narrow down where you want to jump。

But a really more simple approach would be， let's just have every other key also maintain a pointer that allows us jump over the next key。

😡，I jump over one， so if we land on key1， if we know we got to get to some later point。

 we can just the key follow the pointer at the top to jump over key2 to get to key3。😡，And so forth。

 right？And we keep doing this to now also then jump over larger segments。Right。So this again。

 this is going to smell a lot like the B plus tree。😡，What we're doing here。

 But instead of having the。The keys beings are added incrementally and then building things out。

In a skip list， we're basically going to flip a coin and decide when do we want to have these little sort of skip pointers。

😡，Right。So you can think of a skip list， its just a it's a multile linked list。

Where you just add these extra pointers， allow allowed you to skip over nose to jump to farther locations into the list。

😡，The way it works is it's a probabilistic data structure in that not that you'll get false negative or false positives。

 but more like the construction of the data structure is based on some randomness。😡。

So way thing about it is like at the bottom level of the list， we're going to have all the key's。😡。

And then in the next level above it， we're going to have about half the keys as the one below it。

 and then the next level above that， I'll have half the keys below that。😡。

And so now when we insert something， we're basically going to flip a coin in the side for any keyword' inserting。

 what levels do we need to keep those skip pointers for？😡。

And so you'll get approximate log n whereas in the B plus tree if it was balanced。

 it guarantees to be log n in this case here on average， it's approximately log n。

 and it usually works out to be just fine。😡，So the skip lists are from the 1990s。

 B plus trees are from again from the 1970s， if you squint at them， they're basically look the same。

 we'll see in a second， but these are typically used for in- memorymory data structures and in memorymory indexes when we talked about the me table or log structure merge trees that were like this in- memorymory piece oftentimes a lot of systems that's going to be using the skip list。

😡，There are very few systems that I'm aware of using Sless on disk。Just because it's the。

There's a lot more movement that you would have than a B plus tree for moving things wrong in the back。

 yes。it。It question， is it only three levels， no， you can go？You flip the coin and keep adding。

All right， so here's a bit one again， I'm showing three levels， but it doesn't have to be。 sorry。

 so say we've already heard a bunch of keys and again I flip coins and decide how we want to put these。

 So on the on your right or left side， we have all the levels these are the entry points into the data structure and then on the right side these have these markers to say this is the end of the link list。

😡，So if I see this， then I know I've gone too far。All the thing I'm looking for doesn't exist。

So the probability that a key is going to exist at any level will be the number of keys that I have divided by2 n from one or divided2 n from the one below me right so at the first level the probability at key is going is mean one because it's all the keys at the next level it'll be n over two and four and this so forth going up。

😡，Right， skipping this， right。When I want to insert a level or insert a key。

 I'm basically going to flip a coin。And starting at sort of the lowest level I'll flip a coin and if it's equals to true。

 then I know I want to I'll sort the key there so the very beginning again the since you have to always put the key at the bottom because that's the final location where every key has exists so this one you don't flip a coin you know you're always going to insert it right？

😡，But then at the next level， I' say， all right， Ill flip a coin。U and if it's true or heads。

 whatever， then I know I want to insert this and I go to the next one， if it's false。

 then I don't insert an entry at this level and I'm done。

So this case here I flip a coin the second level it's true so I know I want to a coin or insert the key。

 then flip go to the next level， flip a coin it equals true that I I want to sort it again I could go that above that and decide okay now it's equal to false so I don't want to put an entry in here right so for this key here we're going to put something in here so we know it has to go in this location。

So the way it's going to work is。I'm going to first insert the keys where I want them to be。

 but without connecting the rest of the data structure to them。😡。

Right so simplicityities assume it's in memory right so I'm going to create these the key value records for these guys so the ones at the top。

 the values are going to be pointers to the next level below me。And in Sk's parlance。

 they would call these towers。So at the root level， I have the value， at the upper levels。

 I'll have pointers to the level below me in my tower going down。😡。

So then now I need to connect this to the rest of the data structure。😡。

It's going to have pointers coming out to whatever the next one the next location should be in my data structure。

 right？In this case here， the bottom one key5 should go go before key6。

 so it's going to point to key6， but key5 at the other levels， there isn't another key after that。

 so they're to going to point to the end markers。😡，Shes just aminity。

And then now starting at the bottom。I'm going to then reconnect it into the rest of the data structure by changing this pointer here now to point to my new key。

😡，And at this point， the key is safely now in the data structure。

 so even if nobody follows those guidepost up above。😡，I'll still be able to find this key here。😡。

But I'm going to then add those keys at the top upper levels because then again。

 there are guidepost to help me find them what I want。😡，So then I do the same thing。

 go to the next level， change that pointer， now point to me， go to the next level。

 change that pointer now to point to me， right？😡，And now Mac key is fully integrated with all the towers。

So now if I want to do a lookup， I want to find key three。

So I start at the very top and I'm going to look ahead on the pointer to what the key is pointing at in this top level。

 in this case here it's five， but because we know that three is less than  five。

 I don't want to follow this pointer， I want to go down a level。

Because this is basically saying key5 is that the any value that comes after this where key5 is located at the top level is be greater than an equal to  five。

So if I'm looking for three， which is lesson than five。

 then I know I don't want to go to the right of it， I got to go before it。

So then I go down to the next level， do the same thing I compare key3 with key2。

 key3 is greater than 2。😡，Or threeDs greater than two。

 so I know I want to follow this pointer to jump to this location。Then do the same thing。

 check the next node along this level， key3 is less than the key4。

 so I know the thing that I want has to be down into to the right of me rather than going across to key4。

😡，So then I move down here， just then scan along the leaf nodes as I would and any link list。

 and then I'll find the things that I want。In back， yes。杭州省南坡。Yes。😊，然做为一个。必要だ。Yeah。

 the question is going back here on these levels here。

It's it's basically like like the bucket array just tells me where to jump into so I know how to jump to the starting point at each level。

Yeah。Yes。Yeah。So I'm not showing the lines going down， but you would have them as well。Okay。

So let's go we talk about how to handle the elites。So again。

 without talking about multi threadreading stuff， yet， that'll be next week。

 the way it basically works is that every key is going to have a little marker to say。

 is this thing deleted yes or no？😡，And then without me having to go physically remove it because that's actually an expensive operation because I' got to go remove the towers。

 I got to go change one to pointers， so I'll have sort of the thread that wants to delete the key just first mark this thing as being deleted and then like compaction and log structure meries。

 there'll be a separate background worker background process that comes along and cleans things up at a regular interval。

😡，去。So again， along all the leaf nodes， again， I'm going to have this bitete value or Boolean that says。

 is this thing deleted yes or no？😡，So if I want to go ahead now and delete key5。

 I'll do that traversal as I did before， so I would run along to the top level。

 see that I have key5 and then go down and then set it to delete it as true。SoNow， again。

 any other thread that comes along and wants to do a lookup on key5。

 they may see this leaf node here or the bottom node in the linked list that it's been they can find the actual key。

 but then it would check the bit and see that it's been marked deleted so notes would just ignore it。

😡，So now I want to go clean up the tower， basically I'm going to do this in reverse where I'm going to want to change the pointer at the top。

😡，First， and then work my way way down right when we insert it we change the pointers at the bottom and then to work our way up to it this is the opposite。

😡，So again， I'll go over to the starting point at the levels。

 change that pointer now can set a point to K5， have it point to the end。

 and at this point here anybody comes along after me won't be able to see K5。😡，Same thing good。

 the next level flip that pointer， then once I have that change that point at the bottom。

 and this point here， again， assuming， I'm single threaded。For simplicity reasons。

 I know that there isn't another thread。hangingang out here and to follow something that goes to nowhere。

If there's some different guarantee I can provide， make sure that nobody's actually reading this。

 then it's safe for me to go ahead and delete it， and I completely remove the key from the data structure。

So I mean， skip load are kind of cool， it's a nifty little thing， right？Again。

 if you just sort think of it sort of being rotated， it's like a B plus tree。

 but I have instead of these guidepost being determined on how I'm doing split emerges。

 it's flipping out coin decide where things are。And again， there's no free lunch。

 it's still going to be a log gap。是。So the other thing I also point out to is。In my example here。

 I showed a one direction linked list， whereas in the B plus G。

 we said we could have simply pointers going in both directions。😡。

So this if you want to have point go direction， it kind of complicates things。

It complicates some of the operations to make things thread safe， if you have a single thread in it。

 no big deal， multithreads makes a problem because you could have one guy come in one guy， one way。

 another work guy come another way， and you'll be able to handle that。嗯。Unlike B+ treess。

 Siplets don't require any rebalancing or split emerges because it's just removing towers then when you remove a tower when you delete a key。

 or if I insert a key， I'm adding your towers， it doesn't change the location or doesn't change the layout of the rest of the keys in the data structure。

😡，But again， I'm showing this PowerPoint， if it's in memory， no big deal。

 you could pack multiple keys in a chunk of memory， but if now if I am have back as my disk pages。

 then you end up doing more IO than you would in a B plus stream。😡，Right。So again。

 you typically you see these only for inme data structure。

 so the single store people I talked about a few weeks ago。

 they were all in on the skip list and that's the main data structure that they used for a row store in some log structure of meries like Rock Db。

 the mem tables give me a skip list。I think wire Tiger for the long Ma's a skipless， so for in stuff。

 it's often a really easy thing to implement and a lot of systemss choose to do that。Okay。

So now another point I also too with B plus trees。Is that the。The inner nodes are。

Being used as again guidepost that tell us how to get to the bottom remember last class we talked about we said that end up it may end up deleting a key。

 well it'll get removed from the leaf nodes。😡，But then I may keep it around as one of the guidepost because it's a good discriminator and I don't want to rebalance things because I don't need to。

And so if I'm traversing down the B plus tree and I see a key in an inner node。

 I can't be guaranteed that the key actually exists because I always got to get to the leaf node。😡，系。

And so what will happen is I always have to be able to traverse to the bottom of the tree in order to tell you whether a key exists or not in a P plus stream。

In the case of the B Epsilon tree， we talk to end the last class。

 if I'm lucky and I landed the first node， I look into this mo blog and I see the keyI1 has been deleted。

 I don't think that's the way， but again for large key spaces， there's no guarantee to do that。😡。

So an alternative to doing a sort of tree search or a B plus3 or in a Sless as well。

 is to do what's called a try。And the basic idea here is that instead of storing at every sort of level in the tree an entire key。

 I'm going to install a portion of the key or a digit of it。😡。

And then so now as I'm traversing the key as I'm traversing the tree。

 the path I'm taking down into the tree actually can be used to then reconstruct the key that I'm looking for。

So if I'm looking for a particular key and I don't see it in the first node。

 I don't see the first maybe the first character， the first bit that I want in the first node。

 then I know it can exist in the rest of the tree and I can stop right away。😡，So triess are older。

 tries are from like the late 1950s， was inventeded by some French guy， again Bbl Street in 1970s。

 tribes are like 1959， 58， the term Tri was actually invented by somebody here at CMU。

 I think he died last year， but he coined to Ter that in the 60s， yes。

One one of the keys is like the subboard of the。Quest is。

 what if one of the keys is a subward of another key there yes？Yes。😊，How will we resolve。

You just add it。Nobody like what would that look like。Oh， his question。

 how would you resolve it we'll go through examples， but like。

You have H A and you would add and then pointers coming out， oh。

 how to resolve like where something's a subset or another key， you would have both。

Oh like how there's an H to A and H to E just feeling like T no like a T and then T to E， yes， yeah。

Yeah， so keys， he basically ask like， how do I handle the case where a key is a subset of another key？

How do I make， how do I know whether the keys are exist， Because again， I'm。

 I'm going to bem going to be using these tries for。Forgiving key， you find the things that I want。

Range scan is a bit more tricky because you have to bounce up them back。

 but we're ignoring that for now。But the use cases are he handles this mind because if I know him for hat。

 it's ATT。I don't follow whatever pointer down to the next letters， the digits。

 I just stop if there's a pointer I say no there's something that exactly the key。😡，Yes。

s question the question is how does this work for strings and ins， Give me a second？Just fine。

 no problem right what is a string？Asumm as ASI， what is it， Yeah if it's ASI。

 there are always eight bytes， it's just an integer。So there's yeah。

 there's no big deal other data other data types I don't a slide to this。

 other data types are more tricky。Like floats can be tricky。Because it depends on ininess as well。

 we're ignoring all that。Summ it's ASs eight bit characters。Okay。

So what's really cool about tries is that they don't cry rebalancing。Um， not always。

 but the the other cool thing is that the the。ThisThe data structure is like the layout of the actual。

😡，Nos within our data structure doesn't depend on the order in which you insert things or delete things。

 it just depends on the keys， so no matter how what order you insert the keys into your data structure。

 you're always going to end up with the same sort of layout。😡。

And this can then guarantee that any lookup is always going to be okay in time where k is the length of the key that you're looking for。

😡，So if I'm looking for you for hello， right， that has five characters， I in this my example here。

 I know I'm going have to look at least five characters to find the thing whether the thing exists or not。

And the way you just traversely every time you go down to the level。

 you just look for the next character or digit that you want。And if it's not there。

 then no it's not there， if it is there， then you follow the point to find the thing you want。😡。

So in the same way we define B plus trees sort of the M data structure where Ms the number number of points coming out of it。

 in a try， you would say the span of the try is the number of bits or digits we're going to represent in every level of the trot。

😡，Right。And then if the digit exists in the corpus or the keys that we're trying to maintain in our data structure。

 then we have to have a pointer to the next level， otherwise we just say it's null if we don't want to represent it。

😡，And then the fan out would be the the。At every node， how many things are coming out of it。

 and then that also determines what the height of the physical tree is。

So let's look at a really true example where they were asking for how would you represent integers in this。

 let's say we were to sort three keys， 10， 25 and 31。So for this one。

 we're going to store this in a one bit span try， so it means that every single level or every node in a try is going to represent one B in the value you want to store in a real system you wouldn't go by bits。

 you'd go by bytes or something maybe even larger， but for simplicity we'll go with this。😡。

So to insert these records， to insert these keys in this tribe would essentially look like this again where every single level in our tribe represents just one bit position in the keys that we're trying to store right so these are the bit representation of keys 10。

25， 31。😡，And then for。For simplicity， instead of saying， you know drawing all the bits out。

 I just put repeat 10， or you would have a bunch extra notes for that。So now the first level。

 a try is bit position zero， they're all zeros， so we just have a pointer at the zero position in our node。

 jump down to the next level， whereas for for the position one， the bit1， it just goes the null。😡。

So if anybody is looking for a key where the first bit is set to1， I would jump in the first node。

 see that one is mapped to z or null， and I therefore I know the key doesn't exist。😡。

I can stop my search。Again， the next level， they're all zeros and repeat this 10 times for simplicity。

Then we now get down to this level here where now we actually have different differentiating values。

 so we have some of the keys are set to zero at this position， some of the keys are set to one。

 so I again pointers coming out of both of them。So that's say I go down here。

 now I see have 1010 and then same thing I have different levels of those positions in just mapping down and then when I get to the bottom。

 it'll be a record ID or a pointer to something this is the value that we're trying to then represent in this trial。

So。TheJiming head。This is actually kind of inefficient， right， sorry。

Ignoring the fact oforing zero and one， we could just represent that as just in one bit instead of two bits right because if you have characters。

 you wouldn't be able to easily do that or sort of bys wouldn't able to easily do that。

 But in this case here， we we see that we have a bunch of these。

bunch to these nodes where we're not actually storing any differentiating information。

Right like we don't need to store that we have one of the bits set to one and one like one of the bits that set the other ones not set or one is null ones not null。

 so instead we can do sort of horizontal compression with each with each level。

 just remove the values that we don't care about and only store those。😡。

If key we don't want the keys， we' have some set to one， some set to zero at any given level。

 we destroy whatever the value actually is at that bit and we're just the pointer to the next level。

😡，But then we can compress this even further because we see on this case。

 over here on the side or the bottom ones， it's kind of a straight path to the leaf nodes。

Right like for this one over here， zero set，0，0，0 going forth， right。

 we don't need to record anything information extra information about this。嗯。So instead。

 we can do what's called vertical compression and just truncate the try and say the key that you want exists here。

 or key that you're looking for， what exists here， but rather me sting the entire key。

 I'm just going to stop the。😡，The branch going down and does have a pointer immediately to the record that I want。

😡，So if you do this， this is called a raix stream Radix tree is a compressed form of a try where you're doing vertical compression now if you truncate those branches it's going to end up being on probabilistic data structure in that you may get actually false positives because it may tell you a key exists when it actually does not because you don't have the full key embedded in the try。

😡，So you got to follow the pointer to good， then go look up and see whether the key that you want is actually there or not。

😡，Or I could do this again as a filter and say， it's there not there or might be there。

But most systems will use this as actual index， not a filter。So。

When systems say they're using triess。99% of the time， they're using a Redix tree。I。Because again。

 it's a compressed form of tribe without having to show all possible combinations of a key at every single level。

There's a bunch of systems that use this and what's interesting is that even though the try is really old。

 there's been this sort of resurgence in the last 10 years of a bunch of systems saying。

 hey well look tries are actually a good idea， we should be doing this instead of B plus trees in some cases。

😡，Or instead instead of Sless， like Cassandra was using Sips for their meme table for their orchestra nursery and got rid of that and switcheder to a radish tree。

 yes。我的。这是给我。他开始做。The question is before I did this compression， it was deterministic。

And then when I did this compression， it made it probabilistic more like it's deterministic。

 the structure itself is a deterministic， meaning like no matter what order I insert the keys。

 it's always going to have sort of the same， this level has this， this level has that and so forth。

 right？The probabilistic part comes to be like。If I do this truncation。

 I made do look up and find a match for the key that takes me to the bottom and then I follow the point to see whether it actually exists or not。

😡，Um， it's basically given me a false positive on saying the key exists when it doesn't actually other because I'm throwing away information when I do this truncation。

So the truncation part is where you get the false positive， the compression doesn't give you that。

 So going back here， like for。For this path here， like I have。It's a straight line down so。

If I didn't do that compression over here， then I end up with like a。Hows it。

I don't know whether the key exists。Even though I landed at the， I think the key might exist。

 even though I landed at a leaf node in the try， so then I could follow the point to figure out whether actually doesn't exist or not。

Yes。Is this a that that we the inserting keeping。The question is。

 is this the data structure you're inserting keys into， yes？And what would happen if when key kids。

Yes， his question is。What happens if you start inserting a key that then falls along the path。

 you have to expand that？Two slides， we'll handle that， yes。Yes。😊，我们这 check有 original会。A question。

 when I say check the original tool， let' see what the key matches。

I don't know what the record pointer is actually I don't care what the record pointer is actually pointing to it might be a table heap I go check that page the data structure could be for the storing the tuple is the B plus tree doesn't matter whatever the final resting place of the tu is I got to go check it to see whether it's actually a match or not think it like when I do we were doing that linear hashing or linear Pro hashing I hashed my key I land somewhere in the hash table I can't to say I'm done because I land somewhere in the hash table and that's occupied by something I got to go check the key in that hash table to see whether it's actually the one I'm actually looking for same idea I got to go follow something to go look at the original tuple because I've thrown away some information to compress it。

😡，trying to to the same moment because of locality preference getting benefit of the supporting camera。

The question is the complexity of this is seen as what？As a normal drive。

 because if you you very pupils， then we are going out the entire outbreak。 still over and。

This question is， is the complexity of a compressed try ON？Or。The number of land of the state。

Its still， I mean， so were like。Yet so。If it' if it's an index， if it's a unique index。

 then whatever I'm pointing to。i。It's either going to be the key I want or not the key I want so that's a one lookup to your other point of like if it's a non unique index。

😡，What that。You have to measure key，It's okay plus one。我哋如个给你法所的个同的解释。What will we be faster sorry？

甚至。You would have to jump in different locations。咁备追。T of the。

I think so I think what you're saying is。That if it's if it's。me compressed try and non compressedry。

 it doesn't matter。Now on Queve try， I look at my key then so the number of things I got to look down is the length of the key yes。

It in different not the same kidneys block。Typically， yes。So what he's saying here。

 if I compress it down， this is like a really triple example。

 but I compress press this down that everything be inside a single block。要了个80多块。啊。

Sorry say the last one again， sorry， yes， the keys， the key somewheres else， sorry。

 the original twoal somewheres else。So whether it's compressed or not， sorry， if it is compressed。

 then I got to go follow the pointer to go see whether the key actually does match or not。

 if it is not compressed， the key might not exist， I get the bottom of the try and I'm done。😡。

If I get to the bottom try and it is a match， then I still got to go follow the pointer to get the two or follow the record I need to get to the two pool。

😡，You get her enough you're just doing all this work to make sure you're not。

So the whole point of index is us for like not to do a sequential scan on everything to be able to say for a given key。

Goat， does this thing exist not and if it does tell exactly where to go get it。

 so I don't think because I want to avoid toential scan of the tables。😡，Again， think of extremes。

 if I have a billion tuples， I don't want to scan a billion tus to go find the record I want if I have a data structure that again it's a little larger。

 I sorry it's an extra space， extra computational cost to maintain this thing。

 but I'm avoiding that sequential scan， that's usually going to be a good trade off。😡。

All right so tries， again， they're an old data structure。

 but there's been a resurgence and in the last 10 years a bunch of systems is actually using it and it all comes from the Germans who built this system called Hyper。

 and then soductDB uses a versionin of their try because DDB sold their papers and wrote the same thing and then the hyperges sold his data system to Tableau。

 which got all by Salesforce， and then he rewrote a new system called Ura that also uses this Tri indexex。

 but then Ura got forked off as a commercial product called CedarDB， but Redis and SQLite。

 and much of the systems uses internally。You sometimes see this literature called Patricia treeses。

 I look this up and it's actually from like Don Canose books from the computer science in the 1970s and there's a data structure there's a version of this called practical algorithm to Retat information。

 Co and aphromanaric and so Patricia trees come from that acronym， again。

 sometimes you see these calls Radius trees， or there's tries or Patricia trees they're all roughly the same thing。

All rightLet's quickly talk about how we want to handle modifications。

 say now we have a try looks like this， and now within every node I can actually store multiple keys inside them。

 they are they're very at length， but we know how to handle that using sort of roughly thela ofy architecture that we saw before。

😡，So if I want to insert hair， right， I know it should go here， so I just follow the pointers down。

 find a free slot in this node here and insert my entry。😡，If I want to delete hat。

 follow the pointer down to HATT， find T， go ahead and delete that， that's fine。

But then now we can decide that if we delete have， now we only have one entry in this bottom note here。

 so in some implementations of tries or called adaptive Ra trees or arts， they can decide okay。

 well I don't want to have this guy hanging out by himself because then it's a straight path from A down to IR again I could do that vertical compression and move IR up and everything's just fine。

😡，是是。I'm glossing over the details of this quite a bit， but that's roughly how these algorithms work。

So couldn just want to mention that there's a bunch of implications implications of this again Sury mentioned before the art index is the one from hyper thatductDB uses as well。

 there's another one called Judy arrays， just sort the first Radix tree that allowed this sort of the adaptive nodes。

 moving things something down this is an event about HP but they wrote a patent on it and so for years it would show up on hackcker news saying like hey。

 there's this cool thing called Judy arrays， it'd be nice if we could implemented this but there's this patent and then even though the authors of the extra JuD array says。

 oh HP won't see you trust us nobody actually up actually implemented it。

 it's off patent as of like two years ago， but as far as I know I'm not aware of any other system using it。

 instead they're all using the art index。But basically roughly idea is the same thing。

 but you can have these adaptive node layouts and you can resize them based on what the keys you want to store。

All right， so in the last half an hour， I want to go through full text search indexes and vector indexes。

Yes， quite。But better。The question is in what scenarios would a radix tree be better than a P plus tree。

 for range scans， P+ trees are going to be better。For large keys。

 tries will typically be better because they're more compressed。Um。With that？

Like point like point lookups， yeah like I'm looking for a single key tries would probably be better if if the tries aren't like the if the keys are really big。

😡，Again， it's a cop， I'm saying it depends like if I'm doing like a bunch of lookups on keys that don't exist。

 try going be way faster because like if I don't see it in the first node， I'm done。

But if I do range scan， the B plus G be better。And typically in most city these systems。

 they'll implement either BB trees or the radish trees， as in table indexes， they don't do both。😡。

Whereas like some they'll have the hash table indexes plus the B plus trees。

 but they won't usually implement two data structures。嗯。O。So all the indexes we talked about。

 all the datas we've talked about so far are fantastic for doing what again， call point queries。

 go find Andy's a bank account or go get your single user account and for range scans。

 find all the people within that were born within some date range， right？😡。

What they're not good at are sort of keyword searches。

So meaning like find all the articles where the term or the word Pavlo appears。

Because think about how would you do that in your B plus Street because the key has to be the entire of the index has to be what the entire value is for a given column。

So if I just sort of show an example example of like Wikipedia， we had this sort of revision table。

 there was this column called contentt， that was just the text field or whatever somebody entered in when they wrote the Wikipedia article。

😡，So if I build an index on this， like a P plus tree or a try， it doesn't matter。

 then I'm not picking out the individual keys or sort individual words of the column。😡。

It's the entire column。So I can't do a query like this like on an index。

 likefin all the records where the content contains the keyword Pblo。😡。

Because the B plus tree doesn't know how to pick apart the individual words。

 it's going to see trying to do matching the how thing。

 so this is always going to end up being a sequential scan in a system。はい。

It's actually an incorrect query anyway because the wild card at the end can like someone like there's a Russian scientist Paavlov with the V at the end who would match them。

 not maybe exactly what I'm looking for。So this is what an inverted index is going to solve for us。😡。

 sometimes called a full text search index。And the basic idea is that for a given column or attribute when they in a table。

 we want to build this index on， we're going to pull out the individual words or terms in the data and build an index on those things。

😡，Rather than the entire value。Right， so this is。Again。

 sometimes called full text indexes in like medieval times， they were called concordances。

 like there were some monks back in the 1200s that went like they some guy had a bunch of people like read the Bible and create a mapping list of like here's every word in the Bible。

 like a glossary what pages it appear on the same idea。Right。

And then a bunch of data systems are now going to support these， they're not always great。

 and then the SQL syntax of how to use them is going to vary widely between one system to the next。

 but the general idea of how they're going to work is going to be the same。😡，So we take this， again。

 the content field here of this table， and we're going to pull all the individual terms。

 we'll talk a second how we actually do that， and then we'll have this dictionary data structure。

 where for every single term we'll keep a counter how many times you've seen the term。

 and then it then have a pointer to what call a posting list。

 we're just going to be the record IDs of of the tus that had this particular term in the data structure or sorry term in the column we built the index on。

😡，It'So term frequency and so forth。So there's a bunch of these sort of specialized storage engines or storage managers that'll give you these sort of these inverted indexes and that's all pretty much all they do is just do the inverted index like but not meant to be the primary storage of your database。

😡，呃。RightBut like you can build a larger system on top of that so Lucne is probably the most famous one of all these it's written in Java it's widely used Zapen as one of C++ the new hot one now is T Tivi。

 which is basically Lucine but written in rust。And again。

 they're basically building these things and they have various ways to tokenize them and split things up other other things。

And then there's larger systems built on top of this have these again that expose a sometimes a SQL interface。

 expose custom API， but then allows you to do queries on top of these inverted indexes。😡。

This space is super proud of last of search is probably they're a public company。

 they're probably the biggest one in the space， but then they changed the license and people didn't like that so then Amazon 14 became open to search Splunk is a really old one they got bought by Cisco last year Quickwi just got bought by Datadog in January right so these things are widely used and they're pretty popular。

Even though again， your favorite relational data system like Postgres and others will have these kind of these functionality built in。

 they're not going to be sophisticated as。😡，As the specialized engines like Lucine and Tt。All right。

 so let me show what an inverter index looks like for the scene。

 and then I'll show what the Postg button looks like。😡，So in Luc。

 the basic data structure I'm going to use is called a finite state transducer。

 and it's basically going to be like a try。😡，Where we're going to break apart the digits within the keys we want to represent or the terms we want to represent。

 but then rather than being a pointer to where the record actually exists。

 we're actually going to use the weights in the data structure to determine the offset in this sort of dictionary of keys or terms。

😡，So it looks sort of like this， so say I going to do a look up and find the key PV PAV。😡。

So I have my entry point into the data structure and this I'm going to try I'm going to look at the different branches or different possible keys that I have at this level。

 and that's going to tell me whether I want to go left or right or whatever down what path and then at every edge here I'm going to have a weight that's going to of course that I'm going to use and then sum up all the weights to get to either a terminating point or the key that I want and that's going to tell me what offset I want to jump to in my dictionary。

😡，So again， looking for PAV， I follow the edge down on P， that edge has a weight of two。

 so I add two to my all。😡，Then I'm want to find now a， right， follow that path here。

 that edge has a weight of one， else that now goes to three。😡。

Then I want to find V that's a straight path to the bottom， this terminating node here。

 the weight is zero， so my all is  three and then has jumped to that location in my dictionary and I find what I want。

😡，Pretty cool。So the。The data search itself is not immutable you can you can you can you can sorry it is immutable。

 meaning like I can't add new keys to this because I haven to change the weights and mess things up so the way it works in Lucene is that。

😡，You basically do a batch insert。Build the transducer and then freeze it and then any new keys are get inserted you're going to build another transducer for that and then there's a background job that then merges this together to compute larger transduucers so you're not storing the keys over and over again across different dictionaries。

😡，Basically removing redundancies。So we can do all the same things that we talk about for in our dictionary。

 like the bit packing stuff and the delencoding to reduce the size of these data structures。😡。

So this idea is pretty cool。😊，In Postgres they have some what's called the generalized inverted index。

 and they're actually going to build upon sorry in the back yes。他的意见。How do you get the weights。

 you compute them， Do you have all the keys ahead of time。

 and then you sort the keys in alphabetical order。😡，And then based on that。

 you can then build the transduer graph。Again， that's why it's mutable because if I add more keys。

 like if I add key， I don't know。😡，Jelly， look with the J that a go in between BR AV and PAV。

 I would have to change the weights and I have to rebuild the whole graph。

 so that's why they make it immutable。AllIn Postgres。

 they're going to use what's called the generalized inverted index of the gin and with that basically the dictionary is going to be a be plus tree using the existing be plus tree they already have。

 and then for the posting list， they're going to be at the leaf notes。😡。

So in the leaf knows if the number of records that map to a single particular term or key you're looking for。

Again I want to use the term I I want to use term not key because key to imply the entire value of a column we're trying to build an index one。

 this is like a portion of it， so if you have a given term have a lot have a small number of record ID that are matching for it。

 then your posting lists or just just as those values。

 but then this goes above a threshold you don't want have to do a sequential scan every single time to find all the things may be looking for in these posting lists。

 they'll then convert the posting list into another B tree。

 you basically end up with a forest of trees， you have a tree to get into looking for terms and then the leaf node may end up pointing to the entry point of another B plus tree where you're maintaining the sort of list of the posting IDs。

😡，Now maintaining this again is going to be expensive。

 so to avoid the overhead of doing that every single time you do an insert updated delete。😡。

They're going to bring in a mod log， just like we saw many times before the semester。

 where all my updates will get absorbed into that mod log。

 and then there's a background job that runs through and compacts it and merges everything into the main dictionary。

😡，So beyond just doing forgiving key or sorry given term。

 find me all the records that have this term in it。

 some other things you can do with these full text search indexes that are really cool。

 you can use them for ranking。😡，So instead of just saying。

 go find me all the records where this term exists。

You want to know what's the importance of the different records that match。So again。

 if if I'm doing a lookup on the word like Woo Tang。

 I could potentially get a lot of articles in Wikipedia that match that。

 but the one that's probably the most important is the one where Wootang appears the most likely the article about the Wu tangang cllan。

😡，And that'll have a higher importance if I just use a civil ranking algorithm that says。

 what's the frequency of this term appearing in a given record relative to the appearance in all the other records？

This helps you other avoid things like the word the that's going to appear everywhere。

 everywhere and so that you don't end up with weird rankings because。

That term appears everywhere as well。So TF IDF is the basic one that things like Postgres do。

 but then the like Lucene and the other like sort of specialized search engine systems with full text search indexes。

 they can do BM25， which is an enhanced version of this basically。

If you have a key that's repeated a term that's repeated over and over again。

 at some point its weight decays because it like it's not overflooed with that term over and over again。

 like if an article has nothing but the word wu tangang in it with no other words in it。

 you don't want that thing to maybe always be the most important thing。

Because it's kind of full of garbage。So again， the other。

The not all the data systems that like the relational data systems that support full full text inverted indexes can do the more sophisticated things like Postgres only does TF IDF。

 you have to use extensions and add ons to get BM 25 I don't know what Oracle and SQL server do。

The other thing you can also do to improve search is to run these things through tokenizers。

 so my simple example， I just said all right， I'll split all split the column attribute based on the space。

But like。Then maybe sometimes where if I wanted to do like a fuzzy match。

 find things where people even though they misspell the words。

 I can run this through a tokenizer that can rewrite the terms into Ngramms。😡。

Or do other things like move hyphens or map things like。s。a。

 it's the same thing as USA without the periods， sos a bunch of other tricks you can do to improve search。

😡，So with an Ngram tokenizer， you basically take the term wottang and then if I to make trigrams。

 I just have all combinations or consecutive characters up the three letters。😡。

So now I get do fuzzy matches of like someone only writes， you know。

 sometimes which just like you know。itLtan instead of the G， I can still do a match look on that。

Whereas if I'm just using an Albertvera index without this tokenization。

 then I can only do exact matches。It't be been late without this twice。With that， oh， that's a typo。

 Yeah， question is why does U T A appear twice？ at's a typo， right。Thank you。 I'll fix that。

All right， so these inverter indexes are useful for， again， looking for contents。

Based on on the on the keywords， but it's kind of like trying to do。Almost an exact match。

 like does this keyword exist？Again， you can play some games like woo tangang with a hyphen can be matched a woo tangang without the hyphen or woo tangang without the space。

 the tokenizer can sort of handle that。😡，But what you can't do is。Do searches based on the meaning？

Of what's the actual the data it actually represents。

So I can't ask my databases with a full text orverted index and say。

 find me all the songs that talk about people slinging。Or doing some action。

Unless I can do a lookup exactly in all possible combinations of the synonyms for that action。

 for that idea。Because it's just trying to match bits in the index。

 it can't match doesn't have any deeper meaning about what's actually in your data。😡。

So this is what the similarity search that people are doing or the rag stuff people are doing in modern AI systems。

And you can just build this directly in your database assessment we do this， it's just another index。

So let's say again， I have my table of all my albums and for whatever reason I have a column in there with all the lyrics for all the songs and every album。

 obviously we would not want to it in tower album， store it per song， leading ignore that。

So what I'm going to do is I'm going to take all that text column。😡。

I'm gonna run it through my favorite transformer， Open AA has one that's a bunch on huging faces。

 there's the original one work to Vec， whatever I want。

 some it's going convert free form text into a fixed length array of floating point numbers called an embedding。

And then I can take those embeddings， store this in a vector index。I'm not saying what this is， yeah。

 we'll cover that in the next few slides， but like there's some way for now for me to do lookups on those embeddings in an efficient manner。

So now when my query comes along and here I'm showing freeform text instead of SQL。

 but you could put whatever the search term in SQL if you want them。😡，And I want to say。

 find me all the lyrics about running from the police。So I take that running from the police portion。

 and I've run it through my same transformer and somehow magically it generates an embedding that represents that search term。

😡，And then now I do a approximate nearest neighbors search in my vector index based on that embedding that I got。

 and it's going to produce。A rank list of record IDs。

That somehow semantically match the thing I'm looking for。

 like the semantic meaning of the search term running from the police is somehow through the transformer。

Imbbided in that or imed in that vector of floating point numbers。

 right the floating numbers aren't meant to be read understood by humans just the transfer magically does that for it because that's what it's trained on。

😡，I can also do other things like store additional metadata that is in my table in my vector index so that if I have additional queries。

 I want to do lookups on semantic meaning and additional qualifiers，😡。

I instead Im doing a sequential scan， I can do all the sorts inside of the index。

So if I want to find all the songs that talk about running from the police and released after 2005。

 I take， again， that search term， run that through my transformer， I get an embedding。

 but then I can also pass along and when I do my lookup the qualifier year greater than 2005。

So now as I'm doing my approximateimate nearest neighbor search inside this thing。

 I can also throw away entries that doesn't match that second qualifier。And there's a question like。

 do you do the year the first before you do the embedding lookup？

There's no good answer how to do that。So the magic of this makes this all work it's called a vector index。

And this is a specialized data that's explicitly designed to do nearest neighbor or approximate nearest neighbor searches on these embeddings。

 which is going to be a one dimensional array of floating point numbers。

 and the array fixed is always fixed length， meaning like the size of one embedding from one record to the next record is always going to be the same because that's what the transformer generates。

😡，So the challenge in this is that just so like we talk about ranking， like。

 you how do I get a bunch of results and then rank them in the order of importance？

In semantic search， it gets kind of really fuzzy because like there's no。

 because the transformer is doing this magic to convert free form text or whatever it is we want to look up on into this embedding。

 and so now the embedding represents some higher level meaning that we've extracted from the data we're trying to look up on or store。

😡，There's no guarantee that we're going to find exactly the results that we want。

So you can't just go by what feels good enough， what feels okay。Right。

So there's a bunch of different data structures you can use。

 sorry a bunch of specialized database systems that you can use to do these things like PineCone and weviiate。

 Middleists are probably the main ones， but pretty much every relational data system that people are actually using today and actually maintain has their own vector index。

 like PostsCO says PG vector Oracle， MySQL， actually at myC， I don't know， like Oracle SQL server。

 everyone has a vector index now。And the two main data structures are going to use。

 idea they're going to be an Alberta index like we just talked about or a graph index。😡。

I'll go through both of those。So in avert index， the basic idea is that we're going to。

 we want to maintain a mapping from from some。Some location in this high dimensional space to the records that match。

have an embedding that's close to the one that we're trying to do a look up on。

Right so the basic ways it works is you just sort of scan through your data ahead of time。

 you're going to do run your can clustering algorithm where keys define whatever。😡。

It's a black magic how you design it， but it's usually not quite large and then you're going to then do lookups by just running the same cluster algorithm to jump into that high dimensional space and figure out what are all the records that are close to you in the cluster。

 right？😡，So look at an example， so say we have all the manybeddings we got from the lyrics。

 and so in the first past we want to compute Ks cluster。

 we want to figure out how to cluster these guys into a lower dimensional space that allows us to find things that are similar to each other。

So I'm just going to sequentialtial scan through the data and place clusters on a again a high dimensional space here。

 I'm showing two dimensions， but in actual route it would be much larger。

And I want to do this for all the other key embeddings I have in my data app。

So then now I'm going to run my cluster algorithm， that's going to then generate a bunch of different regions。

 and then for each cluster I'm going to compute the centroid。

 like what's the central location that's closest to all the points in my cluster。

And then now in which I have my centroids， I'm going to build it and basically an index。

 inverted index， that's going to map these centroids to the records that exist in my cluster。

because now what we don to do is for a new embedding key that shows up。

 I run it through or for new key， I want to do a look up one or term。

 I'm to look up for I run it through my transformer， I end up with again this 6。

1 dimensional array of embeddings。😡，And then I run the caing I compute where it exists in high dimension space。

 what cluster exists in that's going to give me the centroid。

 and then the mapping then for the posting list is just going to be the records that are close to this in the space and somehow through the embedding。

 I know these things are similar to each other semantically。😡，Pretty prettytty basic， right？

Cha course is how do you maintain this right so if you if I insert a bunch new keys then that's going to put the clustering may get out of whack and therefore my results may not be as accurate so you can either do this in a sort of partition manner like we did with Luc where you sort of build that dictionary list once make that immutable and then build another one for new ones that come in and occasionally combine them and recomp stuff。

😡，Right， the basic idea is the same。The alternative approach is to do a graph search。

And the idea here is that we're going to build now a graph of our our。

of our embeddings again in high dimensional space， and then for each point in the high dimensional space。

 we' compute the utmost and nearest neighbors and maintain the edge between them。

And this edge is how we're going to traverse along this between the different entries until we can narrow down and find the one that we think is the best match for what we're looking on。

😡，So let's say that the embedding we want to find is this search vector here， again。

 it's in my query， I run it through my transformer， I get an embedding。

 and then I plop it down in my high dimensional space like this。😡。

And so for this graph data structure， I always have to have an entry point like where am I allowed to start because I'd maintain a pointer or something somewhere that says。

 how do I start doing traveral intodo this？😡，So at this first location here。

 I'm going to look at all my neighbors that this node is connected to。😡，And for each of those。

 I'm just basically going compute their distance， according to some function of how close they are to my search vector because I know what my search vector is so I I know what the location I want to get to。

But I'm trying to find all the ones that are close to it。

So in this case here it's this one of the top， so we're going to follow that pointer and then do the same thing。

 look at all the other entries that I'm connected to， figure out who's closer， jump along to this。

 and then I land to the one that I want。Pretty cool。But again， think in extremes， if I have。

 Trolln records。Doing this graph traversal is going to be expensive。

So the optimization that people use is what's called AsianNSW or hierarchical graph or hierarchical navigable small worlds。

Where you basically have multiple layers of graphs。

And you start at the top and you follow a bunch of these。

 you follow the traversals and a smaller subset of the graph at the top。

 and then when you exhaust your search at the top level。

 you go down so there's pointers going down to the nodes below you。😡，What does this smell like。

 I think you just said it？Skipless， exactly right。Same idea when I build these I always have my graph at the bottom。

 want to add the layers to the top， I'll flip a coin decide whether I want to keep a node there or not。

😡，And then then that way， like as I progressively go to the top。

 the number of nodes are smaller because then I can do that search more quickly and then narrow down to the result that I want。

😡，A lot of stuff's not new， even though it's AI， they're barring ideas from Sk lists from the 1990s。

Right so again， this is the search vector I want I sort at the top level。

 I enter my graph here in this case here I only have one neighbor。

 I know it's closer to in my starting points， I want to traverse down。

 come down down to the second level， do the same thing， look at all my neighbors。

 see that this one the bottom is closer， I go there and jump to this one， go there。

 jump down here and then my search is done。Yes。😊，あ。It question。

 how do you store a graph representation in a relation database system？

You just have a table for nodes and then you have a table as the D matrix for edges。I created。

So the question is。There are so he's sort of asking like would I stored this as a table， you could。

The vector index implementation do not， they restore this as a specialized graph data structures。哦。

You're stepping in a landni here， so I'm of the opinion that graph databases are a bad idea and the better way to store graphs is in a relational database system and there's a bunch of algorithms that we won't cover so much of this class。

 but there's optimized algorithms to do graph reversal very efficiently unrelational data。😡。

Whereas relational data to people， like the neoo4j people， they would say， oh no。

 you want to store things as like node and edges explicitly and you just sort of you follow those pointers in your data structure when you do one new graphres。

In a modern relational aid system that does one of these enhanced。

fans query processing and techniques， we'll talk a little about them in a few weeks。

 but you can rip through that DCC matrix very quickly， think of like running through a comm store。

 but there's other tricks you can do where you know if you're traversing a graph。

 you can do things more efficiently than you would if it was regular tubs。

Then in SQL 2023 in the standard they added now property G queries。

 so now in SQL you can define graphs over existing tables and you can do things that look like cipher graph queries in SQL directly because one of the things that the graph data says will do better than a relation system is if I'm doing no traversal there's got to be lodged to decide like okay I'm at this node where do I go next and if you just do that in the application now you're going back and forth between the application of the client and a database server and a bunch of network round trips whereas the graph data guys have a single API says you know traverse this graph and everything runs on the server side。

When they added property Gqueries to SQL， now you can define that tra logic all on SQL so there's no round trip。

 everything's done on the server side。So会的那。Quest is， what do implement that？😊。

Only Oracle at this point。But's a extension for Ducky Bead， add property graphs。

 I don't think it made it the mainline branch， but there's a paper I'm happy to share on Piazza from like two years ago。

 they moff the floor out of DuckDB crushes like Ne4ge and all these other systems by adding some of these additional and they don't add all the enhancements。

Just some of them crush Ne over and Ne4j is not a good system， sorry， remember phase that。😡。

The everyday day is a poorly written system。As if that's better， so yeah。

 usually the graph database they'll get if a relational system natively supports graph and some of the query processing techniques where you own graph。

 they'll crush any graph database， don't use the graph database。Yes。

Especially how is PG vector implementing their data structure。

 so PG vector is the widely used extension to Postgres that give you vector search。😡，They have both。

 they'll have， they start the inverted index， the IBB F of flat， and then they added HNSW。

 I think last year。Right。It's written my like it was written my one dude right he just doing it because he wanted to do it and then the Pg vector guy and then it's got a lot of traction I think Amazon's throwing some time and like it's it's pretty it's pretty good and for。

For 90% of the use cases， it's probably good enough for remote people。

The in the same way that like Elasticse and Vespa and these other specialized full text search database systems。

They will have a more sophisticated algorithms and data structures to do inverted indexes than Postgress and other relation data systems。

The specialized vector databases like a P cone， like aevate and so forth。

 they're going to have much enhancements that like PG vector is going to have。

 but for most people PG vector is probably good enough。Yes。公知是。这30。Yeah。

 question like when I' searching here， it's near neighbors I want to find all the the。

Depending on how many nodes I want to get back or how many entries I want to get back。

 I want to find which vertices is the closest to me。我们的医院。All the points in the entire graph。Now。

But like if my graph has a billion nodes， and I want the top 10。I would， you know， if I do this。

 I can skip a bunch of the rest of the graph and jump， get closer to the location。

 land them in the bottom part here and then kind of expand out to I find the 10 the1。

 if I'm looking for 10， find the 10 nodes that match。Okay。

All right so I missed this last class but I do want to talk about because I just kind of cool I'm gonna show you one last thing of extra stuff that you can do with indexes。

 so regardless of whether you're using a Sless try whatever you want。

 there's some actually some cool things you can add in SQL to make your indexes even better。

So the first one you can do what it called partial indexes so every single time when I've declared indexes before。

 I would call create index on table whatever， and without a partial qualifier it's going to build the index on the tire all the tuples in that table。

😡，But I can add a qualifier like this， like a wear clause in my create index statement to then say only build the indexes on the tuples that match this。

So what this allows me to do is like tricks like this where if now I have a query like select B from F where a equals 1。

2，3 and c equals Wootang。😡，I can actually just take this first predicate here。

 look in the catalog and say， oh， this index I want qualifies this。

 and therefore now when I do my lookup on A， I don't need actually check the C C values。😡。

Because I know that if it's in this index， it has to match my wear clauses。😡。

So it's an extra check I don't have to do。 I don't to do it once in the catalog see what the index matches for me。

 Furthermoremore， now my index is going to be much smaller。

 take less space and memory and be way more efficient because I'm throwing away a bunch of stuff that I don't need。

😡，So typically you see this in people create separate indexes for events that occur like per month per year。

 so every month you're going to create a new index so finally look up all the events that happened。

 what are all the orders that occurred in the month of September。

 I'll have my September 25 index and that's the fast look up to go get that。So that's good the cool。

The other thing you do is called include columns。So again。

 when we talked about storing data in indexes， again， whether it's be plus， whatever you want。

 like all the attributes， whatever defined is the key， they're going to be stored within the。

Within all the nose and the data structure。But I can add this include qualifier， where。

I say this is not what the keys based on， so in this case here， the key is still based on A and B。

 but in the leaf node I'm in the B plus， I'll throw in C。😡，So now if I have queries like this。

 the same before select select B from F where a equals 123 and c equals Wootang。😡。

The B& A part I'm going to get from the index。😡，And then when I get to the leaf node。

 then I just checked the C attribute， and if it matches， then actually in this case here， I'm done。

 I actually don't even look at the original tuple。😡，Because it's called a covering index。

 everything I need for this query is in the index。 I didn't have to go look at the original tubple or if it doesn't match on the Wu tangang。

 then I don't follow a pointer anyway。😡，Right。So again。

 this is called a covering index or1 minutes called an index only scans。

 this is a huge win if you're not storing an index organized table with your table heaps。

 if you can pack a bunch of crap in the leaf nodes，😡，Obviously don't want to put the entire table。

 then all my queries touch indexes and I never go look at the original tables。😡，And that's much。

 much faster。All right， again， I think is kind of cool。

 I think you guys be aware of it that you can do this extra stuff and Postgres and Postgres can do this and all the enterprise systems can do this so when Postgres says the best open source enterprise data system it's because they have bunch of these extra features that like MySQL and others don't have。

Okay， so as I said， we went through a lot again， this is a buffet of cool data structures for databases。

 we'll see filters again when we talk about joins， B plus trees are still there going to be default choice for indexes。

If you love inverted indexes， there's a whole course on this in LTI。

 and then there's a whole other data structure' we being talked about called R trees or Kaie trees。

 where think of them as like low dimensional vector indexes。😡。

Like if I want to like bounding boxes within like geospatial stuff。

 like find me all the what's the bounding region of zip code 15，217。

 I could represent this in one of these data structuress there's a whole another course on that from 15826 I don't know how often that's taught that they cover those things。

All right， so next class we will break the assumption that we have so far is that all our data structures are single threaded。

 we will make them multithreaded and talk about how to make them thread safe okay。

 project two or project one is due this Sunday， if should do that and then office hours are on Saturday。

 okay， hit it。😡。

![](img/2eed7525e1bad4e3ff590c615f25b11c_2.png)

![](img/2eed7525e1bad4e3ff590c615f25b11c_3.png)

🎼你。🎼不知怎不缺。

![](img/2eed7525e1bad4e3ff590c615f25b11c_5.png)

🎼Yeah。🎼说你会论帅我走。🎼Yeah。🎼欢你对说 that不见。🎼Yeah。🎼说你对最帅，我 man走不见。😊，Get the the maintain my strain flow the。

