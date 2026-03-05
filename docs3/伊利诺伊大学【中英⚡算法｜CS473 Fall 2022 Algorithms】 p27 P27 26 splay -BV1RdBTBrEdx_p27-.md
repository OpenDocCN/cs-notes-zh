# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p27 P27 26 splay -BV1RdBTBrEdx_p27-

![](img/01b9a7997b2dc8c9e3c701bae54efd86_0.png)

你好。嗯是。😊。

![](img/01b9a7997b2dc8c9e3c701bae54efd86_2.png)

Yeah。Okay， thanks everybody for coming to the second。Lecture did this matter？

Maybe I should actually show it on the screen。U。So。One quick announcement。

374 and 473 are looking for CAs。At least some of you are not planning to graduate in two weeks。啊。

374 especially could really use your expertise。Um， as you know。

 you may remember that at the beginning of this semester。

 I mentioned that this class were a little bit short staffed 374 to managed to kind of break even。

Next semester， the A section of 374 has a registration limit of 500 or 450 students。

It no longer fits an ECEB， the class will be held in Lincoln Hall Auditorium。

I will point out somewhat selfishly that I am teaching 374 next fall。

And the capacity of Lincoln Hall Auditorium is slightly over 600。嗯。U so。If you're interested。

 you can find application forms on the coursese Assist website or you contact Chra directly。For 473。

 I don't know if the application is already up。It is okay， so again， you can apply there。

Chandra says he's already managed to hire about 10 CAs for 374。

 but at least I would want to provision the class at about 24 CAs。

So there's lots more room for people473 is probably going to be a bit smaller next semester said the need for CAs is a bit less。

 but still I would guess。3。Is probably a reasonable guess of how many CAs they'll need。嗯。Okay。

 so please apply if you're at all interested， yes。No。

 office hours will continue until the funding will that。The regular regular times regular license。

So even Monday during finals week there will be office hours。哦。Chas may kill me for saying that， but。

All right， so。Last time I oh sorry， there's another question。Okay。Yes。So for TAs。

Possibly you'll need to talk with。Karen McGgor in the graduateate academic office。啊。

So there is a question about。Normally case is， the priority goes to PhD students。Then。

The next priority is sort of for masters students who were undergrads here or a place like here。

 so they know the course already intimately， and so don't have to be brought of speed。Um。

 and then the next level beyond that would be masters students who come from other places。Generally。

The department doesn't want to hire MCS students ST TAs because。

We use the tuition income from MCS students to pay for fellowships to the Ph student。Okay。

And we only get that tuition income if the MCS student doesn't have an assistantship that comes with the commission。

So the priorities are sets。For PhD students first， and then because there's a need for expertise。

 masters students who already know the course。But it's still worth asking。Okay。Good。

And I should also point out。CA positions， if you are thinking about this as a master's student。

 this is an hourly part time position， it does not come with a tuition waiver。

Say that before anyone asks。No CA doesn't come with a tuition order。Yeah。哦。O。Other questions about。

听咩意思真噶。All。Just a reminder also Tuesday， I'll walk through a sample of exam like questions。

So to give you a sense of how the exam is going be done。

But today I'm going to talk about slave trades。So last time。

I introduced this notion of an online algorithm。Where not the examples that we actually analyzed weren't really of this general character。

 but in general an online algorithm is a data structure and a family of algorithms for updating that data structure in response to various queries or updates。

 so the most common。Or one of the most common versions of this is an order dictionary。

So an order dictionary maintains a set of items and allows you to update that set right during sort or the leading phase and allows you to query the set by asking。

 is this item in the dictionary if it's not given me the next smallest item of the next biggest item？

And the standard data structure for order dictionaries is binary your search streets。

We've already seen binary research trees earlier in the semester when we talked about trees。

 if you took 225 recently you've seen AL trees， if you've taken similar courses elsewhere。

 you might have seen red black trees or bee trees or BD alpha trees or two34 trees。

 or any number of other similar skipists， K trees， any number of similar things。

Spplay treeses is another one of these。Sort of。嗯。Order dictionary data structures。

That tries to keep the tree balanced。😡，In a certain sense now。

It's not in the same sense that AVL treats me。So an AVL tree for a set of n items always has depth to go log in。

It's not the same sense as retreats， the treat with N items has depth to go of log n with high probability。

And in particular， an expectation。Spplay trees do something else。

Splay trees maintain their efficiency in an amortized sense。😡。

Meaning it's possible that this could be a sp tree here that you have node of the direction quite deep。

😡，But if you sum up the cost of a long sequence of operations and you divide by the number of operations。

That ratio will come out with big old logout。TheTotal time to execute K operations is K log A。😡。

So on average， where average now means averaged over the sequence of operations。

 not averaged over random choices or averaged over a probability distribution of inputs。

But averaged over the running time of the algorithm， the typical operation takes what income。Okay。

 so I'm going to start。By。Just sort of。啊。You know。Let's remind ourselves how binary search trees get updated。

好的。你时在。Order dictionary？Or as some people insist on calling it a map。Um。So the standard operation。

For updating。A binary search tree。Is a rotation。This is the same operation that we used。

To bounce treats。It's a constant amount of point of manipulation。So this is， you know。

 I'm rotating X。啊。Okay， so the in order traversal of these two trees gives you the same sequence of notes。

But now I've changed， I've decreased the height of x and that left secretary A。

 I've increased the height of the depth of y and that right secretary C and the depth of that secretary in the middle is the same。

Now， what a s tree does？Is whenever you touch a node that does a sequence of rotations to bring that node up to the root。

😡，But it turns out you can't just when you access an X， rotate x rotate x rotate x。

 rotate x rotate x rotatex until it gets up to the root。

 because what will happen is if the tree happens to be just a path going down to the left。

And you access the bottom node after doing this rotation。

 you have just a path that goes down to the right。And so an adversary can go that one， that one。

 that one， that one and make the average access taken time。So instead， s trees use。Double rotations。

And there are two kinds of double rotations。There is the roller coaster。Which。嗯。

If say the node that you want to promote。Is the of the left child of its grandparent？

Then you do you first rotate the parent of that node and then you rotate that node。😡。

So this is not the same thing as rotate the red node twice。

 this is rotate the parent of the red node and then rotate the。😡。

The other possibility is that your tree。Looks like this and again。

 this is the node that you want to promote。In this case， you just promote that note twice。

 but the effect that this has is to put the the。😡，Its parent will become one child and its grandparent will become the other child。

😡，And you'll get something that looks like that。It's exactly。哦。就嚟。ok。😊，So。嗯。

Whenever you access a node。😡，If it is not the child， if it is not the child of the root。😡。

You display the node。😡，By performing a double rotation and then re perfectly display。

If the node is the root that sing it does nothing， if the node's a child is the root。

 then you perform a single of。😡，So display at X is。While。Parent of x is not the root。Double rotate x。

And then。And x is not the root。And then if x is not the root at the end。Rotate us。Okay。

 so if you can write rotation， you can write things。嗯。Now。

You s whenever you touch a node you access a node for any reason。

 so in particular if you want to insert a node into the display tree。

 you insert it using the standard off the shelf binary search tree algorithm and then you slay the new node that you just insert。

😡，If you want to do a search。😡，You do use the off the self search algorithm to find the node or its predecessor or its successor。

 but in any case you're going to find some node。And you slay that note too。

If you want to do a deletion， deletions are slightly more complicated。😡。

So if I want to delete this node X。What I'm going to do is display that nodeX。To the root。

And then delete it。And then over here， the predecessor of x is now the whitemost node in the left subre。

So I'll slay W。That will create a tree that looks like this。And then I'll add one link here。

So W is the rightmost node in this left subt， so when I display W。

 it's still the rightmost node in that subtree。😡，But it's also the root。

So that means it doesn't have a right child。But there's this other subre over here just waiting to the inspection。

Okay。So putting these things together， that means that the time。4。

Find or successor or predecessor or insert or delete。Is big O of the time to do some sprite？

So from now on， when I talk about analyzing these things。

 I'm just going to think about them in terms of I'm going to do a sequence of ss。

And I'm going to look at the running time of each way up of it。

So the other thing is that it's easy to see what the running time of display operation is。😡，U。

This is order the depth of whatever node is being playeded。喂。So。Here's an example of a sp in action。

 so this is a binary search tree containing the letters of the word algorithms。

Inserted in the order that they appear in that word。And then I displayed the letter S。

 so the first thing I need to do is as z that reorganizes this subree here。

Into something that is now balanced。Then I need to do a double rotation。😡，That means， for example。

 that this entire subre containing GIH ends up getting moved down。M。

 instead of being the left child of the middle node now becomes the right child of the middle node。嗯。

LOS becomes SOL。And then finally， I need to do a single rotation。

So the intuition that you should have here is。😡，S moves up。All the way to the group。

Any node on the search path to us？😡，Gets closer to the root。

So the original search path for us goes ALORTS。So let's look at where that appears A A L O R TS。

The whole search path actually gets kind of smooed up。So up to up plus one or two。

 the depth of any node on that search path gets cut in half。😡。

Every other node in the tree gets deeper by plus one or two。😡，So over time， nodes can get deeper。😡。

But they can't get deeper very fast。😡，But when you s a bunch of notes get shallower very quickly。😡。

so the intuition here is yes， it is possible to set up by display。

 it's possible to set up a node that has depth omega then。😡。

But you need at least omega of mlaves to do that。And so you needed a lot of operations to create an expensive operation。

😡，嗯。So let's see I want to。申请。嗯。Just to write this down。What I'm interested in is。Amortize time。

Right， so the analysis， the theorem。Is。A splay tree。Execs。Any sequence。

Of capital and operations and let me just be specific here capital displays。

In Big go of capital N log little end time。嗯。Yeah。嗯。

Now there's actually a small technical condition here if I start off with a completely unbalanced tree and I do one s the snow。

 obviously the theorem is not going to the work。Capital in there is one when doing the single mega M operation。

 so I have to say， if I starting with。Either an empty tree that you build up by doing insertions or a perfectly balanced tree are actually a balanced enough。

All right。嗯。So I'm not going to give you complete print of this theorem。

 but I want to at least give you a sort of five minute sketch of the main steps in the group。

Because the main step count。Other interesting consequences。Before I go on。

 everybody clear about what display trains do。Everyone， if you get bored。

 just implement them and when you're done，'， you know。

 it'll be 10 minutes and I'll be doing something more it。对。嗯。Right。So how do I actually？嗯。Do this。

So the proof uses something called。可能 a potential method。Anial method。Okay， so I'm going to define。

Essentially a measure of potential energy。In my data。The actual time that I spend， this is。

 I'm spending energy。😡，系。Um but the way I want to think about amortize time is I'm using some of the energy that I spend to actually update the data structure and I'm using some of the energy to store a potential later。

😡，Or I'm using up energy to run the operation， but I can offset some of that cost by spending potential energy that I'd say。

😡，So think of this sort of physically as I'm manipulating the data structure as it builds up potential on kind of rolling the rock up the hill。

 and then if I do an expensive operation， it takes a long time。

 but I'm going to make sure that when it takes a long time。

 there's also a large potential energy drop so I can pay for that expensive operation by rolling the rock down the hill instead of by pushing it myself。

你。So I'm going to define the potential of a binary tree like this。嗯。

Let's define the size of any node V to be the number of descendants。Of the。

In whatever the current tree is。So in this example。The left tree down here。

 the size of the node in the letter O is higher。明。The rank of V is the log based to the size。This is。

What the depth of that subre would be if it were perfectlyly bound。

It's not necessarily perfectly balanced， but it's what the depth would be if it were perfectly balanced。

😡，And then I'm going to define the potential energy of the tree to be the sum of all of the ranks。😡。

系。So。Remember， the intuition is that。The note s。Decreases in depth really fast。

So that node is going to go in this case， from a rank of zero because the size of the sub of s is one。

To a rank of log in because。It's that one known。Grows in potential as it goes up the tree。😡。

A lot of other nodes get shallower。the those that get shallower。

 10 be more descendants and so the rank goes up and so the potential goes up。

And a bunch of other nodes get deeper。But。The rank of these nodes that stay the same like DINH。

Their rank still change。嗯。And so the game is sort of in the margins。

 some of the nodes along that search path actually get a little bit deeper their potential direction。

Okay。Now， why do we play this game？So I'm going to define the amortized time。For some operation。

And define that to be the actual time for that operation。Plus， the new potential。

After the operation minus the old potential before the operation。诶。😊。

What this means is that if I sum up the amortize time over all operations。😡。

That's going to be the same as summing up。The real time for all the operations。Plus。The final。

Potential minus the initial potential。All of the differences in potential kind of give you all stuff in some the only thing that matters is the potential where we began and the potential。

If I start with an empty tree， the initial potential is zero。😡，I can get rid of this。

And so this means that the total time。For all operations is less than or equal to the total amortized time for all those operations。

This summer here， final potential is positive。So if I can prove。that。

That something about that potential。It gives me a way of talking about advertise fine。

But in a way that I can bounce。You know actual thats fun。In terms of。All right。So。The key step here。

Is something called the access level。By the way， these。Data structures。In five， I think。嗯。

This was Danny Slader's one of the pieces of Danny Slader's PhD thesis， I believe， with his advisor。

 Bob Targen， Bob Tarjan， you may have heard this name before， he invented data structures。Morally。

We invented depth research， he invented graph algorithms， unfortunately he only got one turning word。

啊。啊。What we got。哦。啊。Anyway， so they define this access lima。And the the。

If we define the potential as the sum of the log and the sizes。

 what the access limitma says is that the amortized time to rotate。啊。A single rotation at the。

That's at most one。Plus。The new rank of the。Minus the old rank of the。

Sorry I'm missing a factor of three here。And the amortized time。To do any sort of double rotation。

Is the same， but without the plus one。Okay。啊。This as far as I can tell， is just magic。

I understand the proof， the proof is really just let's grind into somes and rearrange terms。

In the right way， so this is the right answer and I understand why it's the right answer。

 I just have no idea how they can look。I mean。I will freely admit with all part of been started agenda。

嗯。But this really is just like out of the blue。But one of the things that this implies。

Is that the amortized time。To display the。Well， a is a sequence of double rotations and possibly a single rotation at the end。

The new rank after one double rotation is the old rank before the next one。😡，So again。

 I get a telescoping sum。This is at most one plus。Three times。The final rank。Of the。Plus。

 the final rank minus three times。The initial rank of the。But no matter where B is the original tree。

 its rank is greater than or equal to zero。So this is just one times three times the final rank。

But I know what the final rank is， it's log of the number of node of the tree。😡，Okay。

 so if you believe the accesslemma。It follows that the amortized time to do a complete display is freeloget。

Threee times what you would expect in an ideal， perfectly balanced binary research。Okay。嗯。Now。Okay。

 so right off the bat just blows you to my face and off the shelf。

Perfectly balanced binary search tree。And compare it to a sp tree。

 the sp tree is only going to be about three times more expensive。😡。

Any sequence of N operations will take3 n log n versus n log n。

But there's actually a stronger statement。So sometimes when you search for things。

 you search for for them with different frequency。In which case you don't want a perfectly balanced。

😡，What you want is a binary research tree where common items are close to the root and uncommon items are further away from the。

Okay， so。If。You if you have you know weird access frequencies， okay， so let's suppose。We search。

For x。T of x times。And I'll define capital T to be the sum of the rulety indexs。Okay， so。

If all the fees are the same。Then what I'm really interested in is the average depth of the nose in the tree and then again。

 perfectly balanced tree is the one that I want。But if some teas are bigger than others。

 it's a weighted average and I want the things with higher weight to have smaller depth。😡，Right。Um。

So。The axis limitma still works。If we redefine。The size of the to be the sum of t of x for all x and that's a descendant of V。

 so instead of defining the size to be the number of descendants。

 you define the size to be the number of times any of my descendants is going to be accessed。

Over the lifetime， the data is structure。And then I still have， you know。

 rank of V is log of size and I still have potential is the sum of the ranks。And I still end up with。

This is found。But now the last step of the advertise kind of display。

 that last step isn't free log n anymore。What I get is。The amortized time。To display。

Is one plus three times the rank of the root well every node is a descendant of the root so the size is the total number of all searches。

 this is three times log t。And then that last term， well。

 I know that the rank of an initial node is at least the log of the number of times that node is accessed。

😡，So the amount of time display X。Is three of the x let me write this separately is three times。

Blog of T over Tx。This is one over the fraction， one over the。The fraction searchinges still。

This is by Shannon entropy arguments the best that you can hope for in any static by period。

I log of total number of searches divided by the number of circuits to dispen。Any binary tree。

 at least one node is going to have at least this much depth。

So this is what's called the static optimality。Spplay trees are within a factor of three of any fixed binary search tree。

 even if the frequencies are not known in advance， even if the frequencies are not uniform。😡。

I have not changed the trip。😡，I only changed the analysis。

So as long as you've got a reasonably fixed access sequence。😡，Yeah。

 you could build an optimal binary research tree and that would take a roughly immense time。😡，Um。

 if you happen to know this frequency in advance， or maybe if the cost in the factor of three。

 you could just run a slavelate trade。😡，What do I mean by changing arguments about how much income income？

II'm using words I don't with。ち。啊。There's basically an averageveraging argument that can take any binary tree and you wait the notes and you look at the sum of the pathway。

And that something like this is a lower bound than the。Okay， so single Sp tree is as good as。

Any weighted binary fixed binary search tree with the advantage that you don't need to know the frequencies in advance。

😡，Moreover， there are stronger versions of static optimality that say if the frequencies change over time。

😡，Then the S tree will adapt to those frequencies over time。😡，So temporal coherence。

 what you would like is to say if I've searched for something recently searching for again will be fast。

😡，Spplay trees have this pop。😡，Last search for this item eight steps in the past。

 displaying that item now will take log pay advertise time。

You' might if the ranks of two items are close。😡，And you search for one then。

Looking for things that are close in sorted order to that they need to search for ought to be fast display trees have this property。

 if you just search for something at rank one and now you're searching for something at rank rank R in sorted order。

 that's going to take you blog up。😡，And in general。

 you can imagine putting fingers on the data structure where anytime you search for something。

 you move one of your fingers to it， and then the cost to do search andize the amortized cost is the log of the distance to the nearest finger。

😡，So lots and lots of different kinds of optimal results here， but the one that we want。

 the one that we'd really like to prove。Is that？Splay trees。Or。Dynaically optimal。

Meaning there's a constant competitive ratio。Versus the best dynamic。

Binary search tree and in particular， the best offline。Dynamic financial。So I want you to imagine。家。

What you're comparing yourself to is any kind of binary search tree where after you do a search。

 you can rearrange things。😡，And I'm going to give you the entire sequence of accesses in advance。😡。

So you can redjigger the tree as much as you like on the fly。

 but you know you're given the sequences in advance， you still have to pay to do that recalculation。

 but you can plan for the entire sequence to minimize the overall cost of all that。

The conjecture is that the cost of any access sequence into a tree is at most a constant factor larger than the best possible offline dynamic。

😡，It's constant competitive against the best static。😡，Binary search journey， that's se。

But now I want also dynamic。And this is probably the biggest open question in the study of Data。😡。

This was conductedd by sator and Tn back in the 80s。😡，There has been progress towards it， very slow。

 very steady progress， but it's been 40 years and we've still got no one。

But what I'm hoping to get to by the end of the next half hour is a sense that we really should be embarrassed that we don't know the end。

😡，His were very close。We just don't know。系。All right。看。Now， there is a there is a。

Small issue with this conjecture the way I've stated it。Which is very much along the lines of。

When you're thinking about。PV NP。The reason one of the reasons that P versus Np is hard is that if I want to prove that p is not equal to m。

 one way of saying that is there is no polynomial time algorithm solves reset。

It's really hard to think about this。😡，Because don't have a way of thinking about all。😡，Algom。

we can talk about all。Algorithms that build a higher dimensional linear programming formulation and then solve that linear program by being shadow over that not or something that doesn't work that in the 1970s thank you。

and solve traveling sales problem po at the time by doing linear your programming。

But there to prove that， we have to specify what an algorithm is。

 what vocabulary we're allowed to use。😡，So really to make any any kind of progress on this at all。

 I have to tell you。😡，What a blind dynamic binary research tree is allowed to do。

Then we have some hope of attacking the problem。喂。So what is a dynamic binary search tree？Right。

 so imagine here is。Tree。😊，Every time I access some node X I'm allowed to reconfigure some subset of the nodes in X now the subset that I am reconfiguring must include the search path down to X。

But it can include other things as well。Okay， so I'm going to let R the。三。Upward。Closed。😔，Subet。

Of nodes。That includes。Thanks。These are the nodes that I'm going to reconfigure。One， two， three。

 four， five six， seven， eight。Now I'm allowed to reconfigure these nodes any way I like。😡。

So this is like a vast generalization of a wood。The rotation is to take two notess and reconfigure in who might name the child。

So off of these node， there's a bunch of other subtries hanging off in some you know in order reversal。

 the same subtries are hanging off as you can。哦。Rooted tree。

There's not really a good name for this this object subt always。😡。

Tends to be used to be downward closed。What I really want is something like instock。

The thing that goes out of the room is you put other things into。啊。So。

And allowed to arbitrarily reconfigure。我。In Biggo of size of our time。Okay， so for s trees。

R is the search path。And the reconfiguring is split。Um so again， whatever node。

 whatever sub is hanging off here from the leftmost node now is hanging off here from the leftmost node。

Whatever subre is hanging off here from the rightmost node is now hanging off here from the rightmost node。

And X， it looks like。Is third from the end， so I think X in this case landed here。嗯。

This is what a dynamic binary research treats。Now， in particular。

 the assumption here is that I can reconfigure this sub binary tree to whatever shape I want in linear time。

That's， on the one hand， a quite reasonable assumption because in fact。

 you can perform a linear number， a sequence of it most to our rotations to reconfigure any binary tree with our nodes and any other binary tree with our nodes。

😡，You just rotate until everything there's this spine going down the left and then。U。

What is unrealistic about this model is the first word on this last line。😡，Um，h。

 it may be an NP hard problem to figure out what shape you want that tree to have。😡，I don't care。

那就什么。I'm allowing the adversary to do that computation， absolutely free。诶。😊，So。

The dynamic optimality conjecture says。Up to constant factors。

I never need to reconfigure anything other than the search path。😡，And。

I can reconfigure using swayover。you know， going off the search path doesn't help doing more complicated reconfiguegration doesn't help。

 except maybe for that factor。😡，For some方。系。And there's lots of both theoretical and practical evidence that suggest this conjecture is true。

U。But we don't even know the following。Weaker conjecture。There is an order one competitive。Dynamic。

Pinary research street。Oh。It may be。Maybe no matter what online algorithm you use to and thinking your tree。

 you can only get within a factor of log log n。😡，Of the optimal awesome。

That we do know of data structures that are log， log and competitive。😡。

We do not know whether slaveries are one of them。😡。

So s trees are sort of trivially log in and competitive because you have that log n em down。😡，Um。

 so know how to get that something down to log log n and we believe we can get the competitive ratio of display trees down to constant。

 that's what the real competitive is。😡，But we don't know how to prove that anything is possible。😡。

Whether constant competitive is impossible。Or most suddenly。

 whether maybe con is possible that it's extra time hard。😡，I don't know。嗯。

So what I want to try to talk about is。嗯。The closest approach that we have to proving is weer conduct。

And this is。The geometry。The geometric view。Of binary search trees。This is by。嗯。They domain。

Dean Harmon。John Icono。将要倾。And me hyptro screw。Okay。All。So I want to model。

Both the input to the dynamic binary search tree and the behavior of the dynamic binary search tree as a set of points into the play。

😡，Okay， so。I'm going to start by saying， well。The inputs。Is going to be an access sequence。

I'm going to to simplify the discussion， the keys in my search tree are the interview one through n when I say access five。

 I mean access standard just。So I have an access sequence that's x1， x2 up through x capital n。

These are nodes that in the Splay tree world， I would say S X1， S X love display X1。

 but now I don't know I explain just means I need to touch X1。

And then I'm allowed in the model to reconfigure。😡，Okay。

 so I'm going to produce points of the form i comma X the X coordinate is going to be。Oh sorryrry。

 I always get this backwards。嗯。X of I come I。So my picture is going to be X axis。

Is the rank of the key that I'm looking for？And the Y axis is going to be time。喂。

So if I take as my access sequence。Three， four， one， five， two。Then at time one。

 I'll put something at exponent three， time two， at exp at four， time three， at expent one。

 then at expent five， and then finally get expent two。So any access sequence gives me a sample。U。

Now the execution sequence。I'm going to define as。The set。Why comma I such that。Note why is。In a。

The I， let's say。The isolately configuration itself。Note I is touched during the I search。😡。

Let's sleep， just write it that way。诶。😊，So in particular。

 when I in this whatever binary tree I'm searching for these five numbers in， when I access three。

 I have to touch the node。And I have to touch every ancestor。Then I could rethink。Then I access four。

 I have to touch the node four and I have to touch every ancestor of node four and maybe other ances other。

And then I re。Okay， so just to make this sort of concrete。

Let's suppose that I'm just going to use the static binary tree and I'm going to apply this access sequence okay so in step one。

 I'm going to access node three that requires me to touch two， four and three。Okay。

 so I'm going to touch two， four， and three。Then to look for four。

 I need to touch two and four to look for one， I need to touch two and one to look for five。

 I need to touch two， four and five and then finally to search for two， I just search。😡，嗯。

So my input is this access sequence the thatpoints。

And then I run that input using any kind of dynamic binary research tree you like。

P to that configurationration model， and I get this larger set of green points。Now。

 this larger set has a somewhat peculiar geometric property。😡。

Take any two points in the green set of points。😡，Or there any different。

It's possible that they're in the same row， it's possible in the same column， discard those cases。

 so let's pick two points that are not in the same row and they're not in the same column。😡。

Those two points define a rectangle。There is at least one other point。😡，On the boundary of that way。

Yeah。You can kind of fiddle around for a while go， well， I don't know。

 let's look at those people in oh。三你噶。At these two points I was no direct。Okay， so。The theorem。

From the geometry paper here。Is that。The execution。Points。Or。Satisfied。meaning。嗯。

Every rectangle defined by two points。Has another point。On its boundary。This。

The group of this basically followed by kind of chasing through the definitions of the binary search stream call。

 and in fact， sort of naively one way to think about it is if you're going to access x and greater you're going to access y somewhere in the middle。

 you needed to access a common ancestor reduction。😡，That's the sort of way of remembering。

The E theorem at least。The more surprising thing is。That it works the other way。

If you take any set of red points that responses you access to piece and you expand it until the set of the larger set of points is satisfied or as the paper puts it arboly satisfied。

过。Everyone feels a little bit uncomfortable talking about arb boialally satisfied supertype。😡。

Except Eric and John。But if I take any set of red points and I expand it。

To make that larger point set satisfied。That is the execution trace of a dynamic binary surgery。Okay。

 so if I were just given this other template on the right。

 you that in green and an initial binary search tree。

I could find a way of reconfiguring the Bible research tree so it would exactly recover。So now。

We've changed the problem from。😡，Here is an algorithm for maintaining bio circuities。

 is it close to the best possible algorithm to here is an algorithm to satisfy the set of points？

How close is it to the optimal algorithm for session？喂。So。Now， bad news。嗯。

Finding a minimum satisfying。Superet。Is NP hard？So it's going to be difficult to think about the optimal algorithm。

😡，We're not in a situation like we are with a lot of scheduling problems to pging problems where there's a dynamic programming solution for what is the best offline algorithm。

If I give you all of my requests in advance， give me the optimal way of scheduling these jobs that's usually solable by some kind of dynamic programming problem here no。

 that's not going to work。😡，The the optimal algorithm is a little bit inaccessible if we allow。啊。

What are called multi accesses。So in order for the income hardness result to go through。

 I have to allow you to say， hey， could you access these five notes same？

So I'm just giving a set of points in the grid and I want to find the smallest satisfied super set。

That problem is NP hard if I insist that in the input there's at most one point on at any coordinate。

We don't know whether the problem is hard or not。Thank。嗯。So。There's a really。Natural。

Greedy He is sick。And so I'm going to， I'm going to take。This that。And。This is called Ready Future。

 so the idea。My greedy future is。I'm going to sweep a line upwards。Through the points。

And whenever the line hits a point， Im going to add just enough other points on that same line to satisfy any rectangles that have that point on the bottom line so let's let me just give an example here so if I start at time t equals one there's a point there so the I need to satisfy this rectangle。

😡，So I need to add a point here。I need to satisfy this rectangle。So I need to add a from here。

I need to satisfy this rectangle。So I also need to add a point here， and in fact。

 I do need both of those points on the left。😡，I need the one that's in the second column to satisfy there and the one in the first column I need to。

To satisfy this right。I just created。But I don't need any more points to the right。😡，诶。😊，So。

Or I goes from one to n。Add minimum number of points。On row I。To satisfy。Rectangles。With。嗯。Bottom。

 row high。喂。This is actually relatively easy to implement in polynomial time， in fact。

 this could be executed in order and loggan。But a little bit of care。Actually。

 it's a capital and more。Conjecture。Reading future。Is constant competitive。

Meaning this the greedy futureism awful， it looks like it's in an online algorithm because I'm considering times in order。

 but it's clair buoyant。😡，In order to decide what points to put on row。

 I have to look into the future to see what points are going to come later。😡。

I can interpret greedy future as a binary search tree algorithm as follows。😡。

You're going to reconfigure。😡，Only the search path。

And you're going to do it by building a tree out of the search path where the priority is the time until you access a node again。

😡，The next time you access the node is going to be the priority used to build a tree the search key is opposed the search key。

So you optimally reconfigure only the search path。😡，Right， BST language。optimalptimly。Reconfigure。

Only the search do。And so this conjecture is。Only reconfiguring the search path is just as good as reconfiguring anything。

😡，发票方式吧。You don't know whether this is true or not， but we believe it is。

Now this requires you to predict the future and what we're interested in is an online algorithm。😡。

这 teacher。But there's this lovely thing about this picture and the satisfied superset problem。

If I take the set of points and I turn it upside down。😡。

And I compute a satisfied subset and then I turn it back right side up， I've solved the problem。😡。

It's completely symmetric， I can reflect， in fact I could even rotate 90 gradients I could swap the roles of time versus rank and solve the problem and it can still solve the problem。

😡，So in fact， I can recast this as。Readedy past。Oh。And this is actually an online。Alrithm。

And this gives you a greedy。Binary search tree， a way of actually reconfiguring and again the way this works is。

You take the search path and instead of reconfiguring it by displaying it。

 you reconfigure it into a tree where the priority of any node is how many steps in the past you most recently access them。

😡，诶。😊，So if this greedy offline algorithm gives you a constant factor approximation。

 then this greedy online algorithm gives you a constant factor approximation。😡。

And so this actually gives you a dynamic fund research tree that。His conjecture to be。

Within a constant sector of all。Now。Again， we don't know if this is correct or not。But we do know。

Something quite。Embarrassing about this。So。Let me define。Three different。

Or two different related problems to this okay。So greedy past， breathe future。

 I'm just going to call it greed。I know that greedy is an upper bound on the optimal satisfied sequence。

嗯。Now， let me define。Grey。Forward slash。And。Brey。Backward slash。

So greedy forward slash means instead of greedly trying to satisfy every rectangle。

 I'm only going to try to satisfy the rectangles that have one point in the bottom left and one point in the upper right。

😡，Similarly， really backslash， I'm only going to try to satisfy rectangles that have one point in the upper left and the other point in the lower left。

😡，So it's maybe not too surprising that you need more points for greedy than for either of these asymmetric。

What's somewhat more surprising？Is both of these are actually lower bounds。😡，On the offline options。

So you might think， oh， obviously I get a copy too。

I take a point set that satisfies all the rec things this way and I have a point set that satisfies all the rectangles that way。

 I take their union that clearly is going to satisfy all the right things。

And so the left hand side is at most sometimes to the right hand side。

 and so I proved it reduced the factorductable， unfortunately that doesn't work because when you add points to satisfy a rectangle one way。

 you might create new rectangles going the other way。

And so there's an interference between these two problems。啊。

Proving the city quality over here on the right between asymmetric greedy boils down to， again。

 looking at sort of geometric properties of these satisfy point sets。啊。

There's an intermediate result that says。If I define two rectangles to the independent。

 if neither of them is satisfied and neither contains one of the points on the other it's boundary。

Then the largest independent set of rectangles is lower that。

And then greedy is within factor two of that。嗯。So none of these， I mean。

 these results are when I first saw them， I found incredibly surprising。

And they do take a bit of work to blind it through， but there's really nothing varied going on。😡。

Once youve internalize all of these linear tools in the notation。

 everything is actually relatively straightforward。And so we don't actually know。

Whether this is a constant factor gap or not。The stronger conjecture。Is， in fact， that。Breedy is。

At most。Opt， plus。Constant。Not up timepon。But opt plus seven。And you know。

 people have tried programming this and you know， figuring out by grainy， grainy brute force。

 what greedy is and what op is， or really， what greedy is and what left and right greeny are。

And the gaps between those always even over thousands of items and thousands of accesses。

 those gaps seem to be you know， less than 10。But an additive less than 10。

John Iconno has been banging his head against this problem for probably 20 years。

And at least three times I've heard him say， I almost got it。

 there's justice this off by one error in one of the boundary cases。😡，And then later。

 I this off by one area you one a different boundary case and then later。

 is this off by one area and these other other boundary boundary。So it's really very， very close。

Unless， of course， it's false。It could be that the greedy is u most plus inverse acromen or something。

And then， well， that's not going to but even proving this was going to talking factor。一两大时。嗯。

That's all I want to say about display trees and online algorithms and open problems that we intended。

唔挂。Yeah。ok。Thanks everybody， we'll see you in their office hours or on Tuesday。So。



![](img/01b9a7997b2dc8c9e3c701bae54efd86_4.png)