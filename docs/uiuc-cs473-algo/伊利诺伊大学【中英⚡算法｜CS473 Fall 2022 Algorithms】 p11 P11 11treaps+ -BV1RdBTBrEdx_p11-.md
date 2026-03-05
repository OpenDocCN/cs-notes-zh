# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p11 P11 11treaps+ -BV1RdBTBrEdx_p11-

All right， let's go ahead and get started。

![](img/da53b589a96b3b9108a4e64b4e548b72_1.png)

Problem three，huh so I will be posting solutions to the midterm tomorrow morning。

There was one student who had COVID who needs to take the exam late。Once that's done。

 then I can everything。Um。The intention for the exam was because I knew problem three was going to be challenging。

 the rest of the exam should have been relatively straightforward。Um。

 and we're going to try to be generous with partial credit on problem three。嗯。As usual。

 slower correct algorithms are worth more than nothing， just like on the homework。

what exactly a brute force algorithm is worth will。Probably in the end。

 depend on how many people need that partial credit。U so u。If it really looks like a bloodbath。

We'll do something fair。To weight the other parts of the exam more heavily without penalizing the people who actually did that problem well。

In particular， even though the class is nominally not graded on a curve。

 we do compute a curve in the background sort of as a backstop。

In case exams turn out to be more difficult than we had planned。Please don't panic。嗯。

Especially please don't panic。Now。U。呃。We do plan to get the exams graded and back into your hands by the end of next week。

Which for those of you who are undergraduates that still leaves one full week before the drop deadline。

 so if you are concerned you can have a chance to talk to me。Before。Again。

 panicking because panic is never the right response。U。Homework four is up。It's due in a week。

We're kind of back to the usual weekly homework release submission schedule。嗯。

Any other administrative issues？Yes。😊，我听咗。ぱ的。我。嗯这是可多。嗯。这个当时电话的。

You should now see Hber4 on the website。て。Yeah。Yeah。错。For graduate students。

 the drop deadline is two weeks after midterm two。Without a W。I don't know why the difference。

 I don't make the rules， this is above my pay grade。So。And in fact。

 I don't know whether this is still the case， it used to be that if you wanted to drop through self service。

😡，You had to drop by the undergraduate drop deadline， even if you're a grad student。

If you're a grad student， you have to fill out a piece of paper。And。

If you wanted to drop before the real drop deadline line， hopefully they fix that。

But I don't know why the deadlines are different。嗯。Okay。So。啊。Today I want to talk about。

Something hopefully。Comforting and familiar。Something all of you have seen in one farm or another since very early programming classes。

Binary search trees。Okay， so you know what these things are， so I'm going to imagine you know。😡。

This is a binary tree that has a key associated with every node。😡。

So binary tree means it's either nothing or it's a node with a pointer to a left subte and a pointer to a right subt。

 each of those are binary trees， but what makes a binary search tree is the key at any node is larger than the keys。

 all the keys in the left subte and smaller than all the keys in the right subte。

So if I use letters for keys。Here is a binary search tree。嗯。And。嗯。Well。

 if I want to insert something into a binary search tree。

 if I want to find something in a binary search tree。

 I do a comparison at every node to decide whether to go left or right。

 and if I happen to run into the object I'm looking for then I'm happy if I want to insert a new token into my new key into my tree。

 I do a search the search fails， but I noticed the last null pointer that I chased and I attach a new node there。

😡，And。Well。Ideally。These things are。Balanced。So binary search tree。

 the time to look things up in a binary search tree if it's balanced is the time to do binary search。

 that's why it's called a binary search tree， so if we happen to know that our tree is balanced，Then。

Any search can be done in log n time because every node has depth big of log n。The problem is。😡。

Of course。Not every binary search tree is balanced。I can have trees that are just really long chains。

Right and。What makes this especially difficult is what I'd really like to be able to do with my binary search tree is not simply look things up in some static data set。

 but rather I'd like to be able to add things and take things out。😡，So I want to support things like。

I want to find an ement x， and if this is just yes or no。

 is it in the dictionary or maybe I have some other value attached to that key。

 so I want to look up the value associated with x。😡，If that's unsuccessful。Maybe I want to find the。

The predecessor or the successor of x in the sortded order that's encoded in the tree， again。

 maybe I just want the smallest key larger than x or the largest key smaller than x。

 or maybe I want the associated value that's attached to that。I'd like to be able to。

Insert new items， I'd like to be able to delete existing items。

And in some applications of binary search trees， I may want to do more interesting things。

 so one particular thing that I like。😡，Is I may want to split a binary tree at a particular value。

 so given a value I want you to take your existing dictionary。😡。

So the data type this is implementing is a dynamic ordered dictionary。

I want to take my existing data structure， feed in a value and say。

 now give me one data structure over here that stores all the items that are less than that value and another dictionary over there that stores all the items that are larger than that value。

😡，Yeah。And then I might also want to go the other way。

So given two binary search trees with the property that could have been the result of a split。

 meaning all the keys on the left are smaller than all the keys on the right。😡。

Glue them together into one big binary search tree。Yes。嗯。And what I'd really like ideally。

 is that all of these things happen in log end time。Now。If。

You've taken a data structures class like 225 hopefully you've seen at least one。😡。

Method for maintaining a binary research treat that is not necessarily perfectly balanced。

 but sort of balanced。I think these days 225 tends to focus on AVL trees。

 other data structures courses tend to focus on red black trees。

I can never remember how either of these work。😡，I know the general rules like the heights differ by at most one or no red node has a red parent。

 but the actual algorithms for maintaining these are just complicated enough that they don't fit in my skull。

And it's not just me， so the C++ template libraries order dictionaries are red black trees and they have been for 20 something years。

😡，For the first 10 years of STL's existence。😡，The code to delete an item from an order dictionary was buggy。

😡，For the first 10 years of the C++ standard template library's life。😡。

The code to delete a node from a red black tree was wrong。😡，嗯。It's not like people don't use C++。😡。

It's not like people don't like try to debug the standard template library。

 there are hundreds of people working on this stuff at all times， they did eventually fix it。

 yeah same。😡，Red black trees were。The modern formulation of light date to like the early 1980s。😡，Um。

So。By Leo Gibbs and Bob Sedgwick， so Bob Sedwick was the guy who did the initial randomized algorithm。

 randomized analysis a quick sort。Um。So eventually Bob Cedric stepped back into the fray and said。

 oh， put all the red nodes on the left， that simplifies the algorithm。

 here's some code and then STO work。😡，So they're really subtle things that can happen。😡。

And so sort of remembering the general idea just isn't good enough。😡，So I'm going to present。😡。

One of the。Ways of doing this。That I can tell you the rules。

And you can derive the algorithms yourself。😡，And you will be right。ok。嗯。

So the object that I'm going to describe is called the Top。Are gone， and。Cidal， I think around 1990。

Treep is a conglomeration portmentau of tree and heap。😡。

For reasons that'll become clear shortly and each of these things happens。嗯。

Each of these operations that I'm listing here。😡，Are happened in log n expected time and in fact。

 log n time with high probability， which is a stronger thing that I'll define later。And again。

 it's simple enough that I really believe that if you get bored and you decide to like let me hack some Python。

 you'll be done before I am。😡，嗯。So here's how the idea works。W says every。Noode has。A search key。And。

A priority。嗯。嗯。Search key defines。a。Well， a finery search tree。

So if I look at the collection of nodes and the only thing I'm allowed to see are the keys。

 it looks like a textbook standard binary search tree。😡，On the other hand。嗯。

If the only thing I look at are the priorities。This looks like a heap。😡。

So if you remember that the definition of a binary heap is。😡，Typically a perfectly balanced。

 but not necessarily just a binary tree that has a priority at every node such that the priority of a node is larger than the priorities of its children or sorry smaller than the priorities of its children and larger than the priority of its parent。

😡，是。Hey。😊，嗯。So。Just to。有。Give a concrete example。嗯。Or R5， I 6。

Here's a collection of key priority pairs i'm always going to use letters for the key search keys and numbers for the priority I am going to be try to be very careful to always say smaller priority and larger priority。

Because the English is a little bit weird。Priority one is higher priority than priority two。😡。

Somebody broke English， I suspect it was the same people who wrote the red black code。Alright， so I。

 I， I claim。That， in fact。😡，This。Characterization uniquely defines。😡，A binary tree。

 assuming all the keys are distinct， assuming all the priorities are distinct。😡。

There is exactly one trip。For this collection of Paris， okay？当。Well， actually。

 I think you can prove this， what's the root？Hey， why is A the root？开始。It's the smallest priority。

 right it's a min heap， so the item that has the smallest priority has to be at the root。😡，Okay。😊，嗯。

Well， in this case， what goes to the left subre？That order， alphabetical。All the keys smaller than A。

😡，Which is。A is the first letter of the alphabet， so nothing。Nothing is on the left of a。

So on the right side of a is all of this。Okay， so now what's the root of this subreop on the right？

It's the item with the lowest priority， smallest priority。And then I split。The remaining items。

Depending on whether the keys are larger or smaller。And then by the induction hypothesis。😡。

Each of those remaining sets of key priority pairs define a unique binary tree。😡，Okay。

 so if I finish this off。Let's see O is the root over here。Amaz on the left。Orarants like that。

 and so in the end。I get a tree that looks like this。

Now that doesn't look like a particularly well balanced tree， but that's okay。All right so。嗯。

Let's do an insertion。Okay， so I'm going to give a new node it's called S and let's give it an interesting priority。

Bye。Any he guesses how we would insert？Yeah。So then we first look at the priority of。

So to define this unique binary tree structure。😡，The smallest priority determines the root。

 and then the search key determines the split into left and right。😡，And then you induct。

So this kind of sometimes we'll look at the search key。

 sometimes we'll at the priorities we'll get used to this pattern。😡。

Then you would have a very skewed tree。If the keys and the priorities have exactly the same order。

 your trip is just going to be a path going down to the right。😡，Okay。

So the first thing I'm going to do to insert this new node into my tree is I'm going to say， oh。

 it's a search tree， put it in the place where it goes when you're a search tree。😡。

You knew how to do that because you've done binary search trees without worrying about balancing。

 again， you just follow the search path for the new key and the last nu pointer that you jump off。

 that's where you attach the new node。Okay。But now the priorities are wrong。So I need to fix them。😡。

And the way that I fixed the priorities uses。An operation called a rotation now this is exactly the same operation that's used to manipulate red black trees and AVL trees。

 so this is the one piece of that technology that I need to remember。😡，And the idea here。

Is I label these subtes。Again， sorry about the collision of notation letters here。

I've got this little two node binary tree， those triangles are larger subtrees。😡。

Everything in A is smaller than the key at U， which is smaller than everything in B。

 which is smaller than V， which is smaller than everything in C。

 and that's true both for the tree on the left and the tree on the right。

And that transformation from this little tree on the left to the tree on the right。

 usually refer to this as rotating you up。😡，And rotating V up。In both cases。

 the if I go from left to right。😡，The old parent of V becomes the new parent of you。😡。

The rest of the tree far away is unchanged。And so in particular， this can be done in constant time。

It's a bit of careful pointer manipulation。This is the hardest part to debug。In the home mess。

But one thing that you'll notice here。😡，Is。If。You used to be a child of V then after the rotation。

 U is a parent of V。😡，And this is exactly the sort of thing I want to fix the priorities in my tree。

 so I could perform a rotation here。And that would。Put me here。Now this is the structure of my trip。

And I've brought S a little bit further up because it has a smaller priority than its old parent now it still has a smaller priority than its current parent。

😡，So。I will do another rotation。See if I can actually manage this。Do another rotation。

We'll do something like that。Now S still has a smaller priority than its parent。

 so I will do another rotation and this is where things will get a little interesting。

U that out of the way and that of。So。This will become this child。And。I'll get a tree that like this。

And at this point。All of my priorities are rebalanced are correct。So to insert something。😡。

I pretend it's a binary search tree and I insert。😡。

And then I do rotations to fix the priorities now the only place the priorities were screwed up were between the node I inserted and its parent。

😡，That rotation fixes that pair。😡，But may move the problem closer to the root。😡，Everywhere else。

 all other edges in the tree throughout the rotation will still be okay。

Because every rotation moves the new node closer to the root。

 eventually I'm guaranteed to stop because maybe the new node that I insert。

 if it has lower priority than everything， it'll become the new root of the tree。😡，Okay。So to。Insert。

A new key priority pair， I create a new node。key priority。Insert。嗯。Looking only at keys。And then。

Bbble up。The new node。looking。Only。At priorities。How do you delete？That's exactly right。

The way you delete is you insert， but in reverse order。😡。

So the first thing I need to do is I need to get that node to be a leaf。😡。

Because it's really easy to delete a leaf。😡，It's just the opposite I just chop it off and all done so how would I get that new that node that I wanted to delete to be a leaf increase its priority to infinity。

😡，And then I rotate it down。😡，But I have a choice， do I rotate it down to the right or to the left？😡。

Only one of those choices satisfies the heat property。

Whichever whichever child has lower smaller priority。

 that's the child that I want to promote so in this particular set case if I wanted to delete S。😡。

I would rotate O up。Because O has the smallest priority among the descendants of S。

 then O becomes the root of the sub containing what's now the descendants of S。

So deletion is literally just insertion backwards in time。😡，Um。

There's slightly more complicated logic in that I have to look at my two children and decide which of them I like more。

😡，这对。It's a simple comparison。The one with smaller priority gets promoted。Okay。That's it。

That's the whole algorithm。嗯。So let's write this down， delete。Some some nodes， so I。Set the priority。

To infinity， I rotate。Down。Always promoting。The child with lower priority。

And then eventually I chop off the lead。咁。😊，Great。The running time of this operation。

iss basically determined by the so the running time of an insertion is dominated by the depth of that leaf after the insertion phase of the insertion algorithm。

So when I put attach the new node to the tree， it's a leaf。

 the depth of that leaf is going to dominate the running time of the insertion algorithm。😡。

I walked down and then maybe I walked back up。So I'm just going down that path back up again。

 likewise with the deletion algorithm， the running time is going to be dominated by the depth of the node just before I cut it off。

😡，Yeah。The running time of a search is going to be dominated by the depth of whatever node the search ends on。

 either the target node that I'm looking for or when I fall off the edge。

 depending on whether I'm falling off to the left to the right。

 the successor or predecessor of the node that I'm looking for。😡，So in all of these operations。嗯。

The time。Is proportional to the depth of some。Note。诶。😊，Now。

Remember the original goal here was to design a binary search tree， a binary search tree。

 just it's an order dictionary， you give a set of keys。😡。

To the order dictionary person and they say thank you。

 and then you ask the order dictionary person questions and they answer them。The priorities。

In this example can be chosen by the data structure itself。😡。

The priorities are not part of the input。😡，I mean， if we're using this as a binary search tree。

Rather， the priorities are what？Random。So if I'm treating this purely as a binary search tree。

 then when I insert。😡，I'm just given the key。So I need to attach a priority to this node。

So our role in infinity cied die。I generate， for purposes of analysis。

 let's imagine that I generate a real number between zero and 1 uniformly。😡。

I throw a dart at the wall and I measure its height。And that's going to be my priority。In reality。

 you only need to choose integers and there's a deeper analysis that shows you how many bits you need。

But let's keep it simple。Then those random priorities determine the structure of the binary search tree for the given keys。

😡，And the punchline from this is。If I choose my priorities randomly。Random priorities。This implies。

For any node V。The expected depth。Of the。Is the of log Ed。嗯。Yeah。

 so they're basically saying that it becomes goes to a binary research rate which right up priority。

No， I'm saying it is yeah， it is always a binary search tree。But what I'm saying is that。

If I choose my priorities is at random。😡，Actually， with high probability。

 the tree is pretty balanced。😡，It's not going to be perfectly balanced， right。

 that's a really low probability event。😡，But the depth is not going to be off perfect balance by more than a constant factor。

😡，And this is also really actually noticed the statement says for any node V so you tell me which node V you want。

 so I have this collection of letters that spells the word algorithms and you tell me what is the depth of the node storing the letter M。

😡，Then on average， the answer to that is going to be big of login。😡，And。

In the analysis of this running time。It's not really just the depth of some node。

 but it's the depth of some node that only depends on the order of the keys， so when I'm inserting。

 I'm either the running time for the insertion is either going to be bound by the depth of the predecessor inserted order or the successor in sorted order。

😡，And each of those， the expected depth is log in。😡。

So the expected running time for an insertion algorithm is log in。😡，Similarly， when you delete。😡。

The running time is going to be dominated by either the depth of the predecessor or the depth of the successor when I'm about to finish。

 in fact， when I'm done， but when I'm done， I have a tripe for the remaining nodes。

 so each of those two nodes that I care about have depth on average log n。😡。

When I'm searching for something。The expected depth of the thing I'm looking for is log N。😡。

When I search for something and I fail， again， the expected depth of the predecessor is log in。

 expected depth that the successor is log in。Now this isn't quite。

As strong a statement as we'd like to make。So the statement that I'd like to make is。On average。

The maximum depth of the tree。Is big O logA？It's true that the maximum of the expected depths is loged。

😡，It's we haven't。I won't show you today why the stronger statement is true that on the average maximum depth is also log out。

😡，Let's stick to this。嗯。Oh I also mentioned spliting and join， how would you do a split？So。嗯。

Where do I implement a split？So I want to take my troop。

And I want to turn it into two smaller treats。One where everything is less than x and one where everything is bigger than x。

Dont you just click to mean and then。我的。Rot of where that no use to。Just take。Close。

Problem is the delete pushes the node down。Seems like remember the location of where it。

 but it used to be like， I don't know here in the middle of。Something， so。は。

Let's make it interesting， let's say x is not currently a value in the tree。

So the first step is inserted into the tree， okay， now exit is a value in the tree。Yes。Right， okay。

 so sets of the priority。Of x to negative infinity。And then。Rotate it up。Now x is going to be here。

And then I delete the route。嗯。How do we do the merch？Given these two things。

 everything here is less than x， everything here is bigger than X， I'm going to join it together。

At a root。Conect。And then， well， I didn't really want this extra node， so delete it。Again。

 the time for the split。Is the time to insert x if it wasn't already there。

 plus the time to bubble x up to the root， which is the depth of x。😡，Which on average is log in？

So I can do splits in log end time and I can do joins in log end time。On average。

 provided you believe this claim in the red box？Okay。So。At this point。Hopefully。

 I think you understand the actual algorithms here。

 just not why the analysis works expected is going to be less than able to log in。

Because you said the maximum is always going to be。

On average login so then a random thing that we pick should be lesser than so okay。

 so'm I speak theoretician so occasionally I don't pronounce my big Os。Okay。

 the statement that is actually true but。The stronger statement。

Is the expected value of the maximum over all nodes v of the the。Deepth of。Is login。Bgo。

The statement in red does not imply the statement in blue。😡，The blue statement really is stronger。

 it implies the red one I'm just going to prove the red one today。

I'll approve the blue one on Thursday if we have time。All right。So。I need to， you know， figure out。嗯。

呃。Deth。To simplify notation a bit。😡，I'm going to make two notational changes， one。

 I'm just going to refer to nodes by their keys。😡，So I'm going to refer to you know depth of not V。

 but depth of k， this is the node whose key is k。And I'm going to further make the assumption。😡，嗯。

Because it doesn't matter， only the order of the keys matter， the keys are the integers。

One through n。So really， when I say the depth of k。

 I mean the depth of the node that stores the K' smallest key。😡，But just to simplify notation。

 I'm assuming that the keys in their ranks coincide。系。嗯。Okay。Well， what's the definition of depth？

The definition of depth is the number of proper ancestors。Of that node。

 so a proper ancestor is either your parent or a proper ancestor of your parent。😡。

The word proper there rules out， you know， this is like subset。

If S is a set then a subset is something you get by throwing out zero or more elements。

 so S is a subset of s if you really want the thing to be smaller you have to say it's the proper subset same thing here ancestor is used as kind of a like less than or equal to relationship so technically a node is an ancestor of itself and a descend of itself zero generations away。

 so I've used proper here that just means not me。😡，嗯。So。I'm going to use。For the analysis。

 the trick that I introduced Thursday on last Tuesday。Which is I'm going to take this count。😡。

Of proper ancestors， and I'm going to represent it as the sum of a bunch of01 variables。

so I'm going to write this as the sum over all nodes I。Of the condition。One。

 if I is a proper ancestor of k and zero， if I is not a proper ancestor of K。Right。I'm gonna to。

Write this。Like that， so I up arrow K means I is a proper ancestor。Of okay。嗯。Remember。

 I use down arrow to mean child， so up arrow means parent。

 a double up arrow means parent or further up。😡，Pnemonics。Now。

 why did I do this because what I'm really interested in isn't just the depth for any particular instantiation。

 but rather depth of the node is a random variable and I'm interested in its expected value。😡。

So by definition。The the depth is the expected number of proper ancestors of that node。

 so by definition。😡，It's the expected value of the st。😡，But remember expectations are linear。

 you can distribute them over summations， so this is really the same as this。

But now that random variable is either a0 or a 1， and the expected value of a random 01 variable is the same as the probability of that variable being equal to one。

😡，So what I really want here。Is probability。And so now if I want to analyze the expected depth of a node in a tree。

😡，The only thing I need to figure out is here are two node， I and K。😡。

What is the probability that I is a proper ancestor of K？😡，Now， if I and K are equal。😡。

That probability is zero node is never a proper ancestor of itself。

 that's what the word proper means。😡，So that's sort of a trivial case。

 but otherwise I want to make a simple claim。And then we'll do the analysis and then basically we'll be done except for a little bit of algebra。

So。It deserves its own。Lemma。Mathematicians like to use lots of different names for the things that they want to prove so they they go from like。

Propositions and theorems and lemmas and claims， and occasionally if they really want to be smart as facts。

嗯。The difference between a theorem and alemma， these are the two that are most common。

is the theorem is the thing you really wanted to prove and the lemma is just a stepping stone along the way in practice the difference between the theorem and lelemma really is a theorem is spelled with a T。

😡，And lemmas spell Bu theelle。But lemma comes from the Greek word that means help。

So this is really just helping get to the eventual thing， which is。This thing in red。All right。

 lemma。For all indices I less than k。I is a proper ancestor of K。If and only if。The priority of I。

Is the smallest？Priority。Among all nodes。Between I and K。Inclusive。Okay。😊，So。

Just to see before're on the same page。What is the probability， assuming that this lemon is true？嗯。

The probability that one is a proper ancestor of n。

 so the smallest node is a proper ancestor of the largest node。Remember， priorities are。

Completely random variables generated independently for every key。

So I'm going to assign U random number 0。6782， U random number 。39559， U random 0。0158 U random 。

2792， and then I'm going to wander over here and ask what is the probability that this person has the smallest priority？

Oneever end。So this is saying priority of one is the minimum among the priorities of all items between one and n。

😡，Priorities are independent uniform random variables。

 so the probability is the same for any one of them to be the minimum。😡，Yeah。咦对吧？

I'm not claiming anything about descendant relationships in Lemma。I'm just saying。

These are Js between I and K。😡，So move your hands horizontally， right so in the sortded order。😡。

They're in between。It's not up and down in the tree yet because we don't know how the priorities go。

So this implies that this is exactly one over in。And more generally。

This implies that the priority that i is above k， assuming i as an index is strictly less than k is an index。

This is equal to1 over k minus I plus1 because there are exactly k minus1 k minus i plus1 priorities in that set。

Each of which is equally likely to be the smallest one。嗯。嗯。So at this point I may as well do the。

The rest of the analysis， and I'll come back and I'll approve the dilemma。Okay。

 so let's look at the expected。Deepth of K。 This is the sum from I equals 1 to 10 of。

Probability that I is above K。 Now I'm going to split this into。I is less than k。

Which is given by dilemma。And。I is bigger than k。So it goes up to N。😔，In fact。

There's a symmetric lemma。That if I is bigger than K。

 then just replace the inequalities over there with K less than J less than I。Righty？

So the lemma implies this is i equals1 to k minus1 of1 over k minus I plus1。

 and then the symmetric lemma gives me I equals k plus 1 to n1 over I minus k plus1。

So to analyze this， I'm going to set J equal to k minus I plus1。And to analyze this。

 I'm going to set j equal to I minus k plus1。And if， if you do those substitutions。

The sum on the left is going from j equals2 up to k。

sum on the right is going from j equals2 up to n minus k minus1。

So this is the kharonic number minus1。This is the n minus k plus1。Harmonic number minus1。

So the harmonic number is one plus a half plus a third up to one over n， but I'm not starting at one。

 I'm starting at one half。Yeah。So this is less than two times in the natural log of bed。棒。等。Actually。

 I think I can say this。Minus2。So once you prove that lemma。

Then by just plugging that into the summation。Doing a little bit of index arithmetic。

Plugging in the definition of the harmonic numbers， I get this exact。

Expression for the expected depth of the node with the K smallest key K is less than n。

 so this is less than the enharrmonic number， which is about log n。Over there。

 that subscript is also less than n。So that's less than the anharmonic number。

 which is about natural log of n。And so I get two times the natural log n here minus two because of those minus ones。

嗯。If you're a little bit more careful， you can derive an even tighter bound。

 this is going to be maximized。When。K is n over two。

So it turns out troopss are not really perfectly balanced it's more like。😡。

The highest and lowest nodes。One of those hs will vanish and the other will turn into H of N。

 and then in the middle it's about twice as deep。So tro really looks like that。

But it's only a factor of two difference。Okay。But this is now enough， provided you believe thelemma。

To show， okay， now you know how to implement insertions and deletions and you know that their expected cost will be。

Bounded by this two natural log ofette。Just。Normally we think of binary search as being like log based two event。

 this is a log based E event。😡，Lo natural log is actually smaller than log basease2。

 so this is really about 1。6 times log base2 then。not bad so a perfectly balanced tree would look something like。

This。Okay。That makes sense。So we can go back and prove the dilemma。Right。For all I less than k。

 I have this equivalence。Between events。So groove。嗯。Whi's pretty。Straightforward。

There are five cases to consider。One is， well， I'm going to look at the root of the tree。

And there are five possibilities。So remember， the root is the item out of my entire data set that has the smallest priority。

😡，That's how the root of my trip was defined。So there are a couple of cases that I can knock off immediately。

😡，So one is case two。If node I has the smallest priority of every node。😡，In the tro。

Then in particular， it has the smallest priority in that set。😡。

And it's a proper ancestor of every other node。😡，Okay so in this case， I have， well， yes。

 I is a proper ancestor of K because I is a proper ancestor of everything and a priority of I is the minimum in that set because it's the minimum of everything。

Okay， so this is the case where things succeed。嗯。The next case I can also knock off。

 so let's suppose the root is some j that's strictly between I and K。😡，U。Now I know two things。

One is that the minimum in that set is not I。😡，It's the root。

Because root it's the minimum of all things， so I know that here priority of I is not。The minimum。

The other thing that I know because I is less than the root。

 is that node I is somewhere in the left subt。😡，And because root is less than k。

 K is somewhere in the right subt。So neither is a proper ancestor of the other。系。So in this case。

I is not less not that proper ancestor of okay。Exactly the same thing happens when the root is equal to k if the root is equal to k。

 then k is up here at the top K has the minimum priority， which means I doesn't。😡。

And K is a proper ancestor of everybody， which means in particular， K is a proper ancestor of I。

 and despite the song you can't be your own grandpa。😡。

Okay if you can't be an ancestor of your ancestor， there's no time travel in this universe。All。嗯。

Now the other two cases are a bit more interesting。😡，Suppose the root is smaller than I。Okay。

That means I is going to be in the right subre。😡，And K is going to be in the right subt。

And the right subtre is a troop that has one fewer。

 at least one less node in it than the tro that I started with。So what's the magic？Incantation。

I've reduced to a smaller instance of the same problem。😡。

I've gone from an end node tro down to a tro that has fewer nodes。😡，So here。

 dilemma follows by the induction hypothesis。Similarly， if the root is bigger than k。

 that means i is in left subre and K is in the left subte。😡，So they're in this left subre。

 which is a smaller tree， so by the induction hypothesis thelemmaholes。

And that is the end of the proof。So the only interesting case is when eye is the root of the tree。😡。

I has the smallest priority out of everything if the root is far to the right or far to the left。

 I'm just sort of putting off making a decision about whether I is an ancestor of K until I decide that one of them is the root or the root is in between。

K。At this point。You have now seen。The definition of a tree。How to implement it？And a complete。

 no details hidden。😡，Analysis of the expected depth。And we still have 15 minutes。

Did you talk about AVL trees that quickly？H。U this is one of the things that you know I find this sort of intensely frustrating so like why are you talking about AVL trees。

 it's so much easier to implement this。And the answer is sometimes this factor of 1。

6 actually matters for AVL trees you get。See if I remember correctly。

 it's not instead of log base2 of N， the depth of an AVL tree is log based golden ratio of N。

So it's a little bit bigger。Red do trees are even better if you implement them carefully。

 it's not log n time something it's actually log n plus a small constant。

So if you performance really matters， you probably do want to do red black。But you。

 premature optimization is the root of all evil。Unless your red black tree is the performance bottleneck。

You don't want to。It's probably not the thing you want to。😡，UmTo implement。

 you want to implement something simple。嗯。So one last thing I want to say but before I do that。

 I want to make sure there are no questions about this stuff。Yeah。

This is the this this list and how on the。Okay， so when the root is smaller than I。

That means I is in the right subre， k is in the right subre。

 and now I'm arguing I want to argue about the right subre， which is a smaller tree。

So the induction hypothesis is， so if I really were going to do this formally， I would say。

 let N be your favorite positive integer， assume that this le holds for all I。

 allK in all troopss of size less than n。😡，Then that's the induction hypothesis that I'm applying。

Okay， so I claim that I've now given the same lecture twice。😡。

So I'm going to give you two definitions of a tree， one is it's a binary search tree。Actually。

 I'm going to give you three definitions of a tro by random。Priorities。Okay， so second thing。

Is a tree is a binary search tree obtained。By。Inserting。He's。In。Random order。

So instead of thinking about it as I'm assigning the priority when I insert the item into the tree。😡。

Imagine instead that before I'm building the tree at the very beginning。

 I assign my priorities like I did in the example， and then I say insert the thing with the lowest smallest priority now insert the thing with second smallest priority。

 now insert the thing with third smallest priority and so on。

 this is exactly the binary tree that you would get。😡。

The first thing you insert is the thing with smallest priority so it lands at the root and now when I'm saying insertion。

 I mean completely。😡，Standard textbook， CS124 insert into a binary tree， no rebalancing。

 no trying to do anything， just follow down until you get to an null pointer and glue on your new note there。

😡，Okay。UmSo you can think of this treat as。😡，Once the priorities have been assigned as the binary search tree you would get if you inserted things in order of increasing priority。

😡，系。And the fact that you insert things with larger priority later implies the heat property among the priorities。

😡，Now the third definition of the tro。Is。A tree is a recursion tree。4。Randomized quick sort。So let's。

Look at the example here。I want to sort the word algorithms so the letters are an alphabetical order。

 I pick a random pivot a。I well why did I choose a is my random pivot I need some process that will choose what are the pivots uniformly at random I know I'll assign each of my keys a random priority and pick the smallest one that's a pretty good process for choosing uniformly at random。

😡，I recursively sort everything smaller than A， that was easy。

 and then I recursively sort everything larger than A。😡，Again。

 I choose an item on the right uniformly at random。

 again by looking at the random priorities that I assigned at the beginning of time。

 I get the lowest priority thing is my new route。And I recursively have some problems on the left and the right。

The recursion pattern that I get is exactly this binary tree。So what I've actually shown you。😡。

Is the analysis of randomized quick disorder？😡，BecauseWhat does it mean for one key to be an ancestor of another。

 that means at some point。😡，These things were at the same level。

 and I did a partition with what became the root of that recursion tree。

That pivot element gets compared to everything else in that interval and the things that are smaller fall down to the left and the things that are larger fall down to the right。

😡，So I as an ancestor of K means I was a pivot and I compared it to K in some subproblem。😡。

So sum up all the depths well each depth is log n on average。

 so linearity and log n is the total number of comparisons for randomized quick sort。Yeah。嗯。

But now I have three different views here。Which means I can look at as the following as randomized Quick sort。

Randomly per your day。Um for each。X in a。Um。Insert X into。A BST。And then do an in order traversal。

Of the BSD。Process of inserting X into a complete again， not a balanced binary tree。

 just a completely standard one。The comparisons that I do as I walk my way down are exactly the same as the comparisons that I do in the choose a random pivot recursive divide and conquer algorithm。

😡，And'm doing I'm organizing them in different order。But if in this formulation。

 I would compare 5 to 17， in that formulation， I would also compare5 to 17。

 provided that I choose the same random numbers on both sides。Um。

This doesn't look like randomized Quickstar， but it is。

So this also means that because I have this view of。😡。

Tres as sort of the recursion tree for randomized quick sort。

What am I doing when I'm inserting or deleting into a tree？I'm saying you know what。

 actually when you ran Quick sortt， there should have been an X here。😡，Fix it。

And it basically goes back in time。😡，And does exactly the amount of work necessary to repair the recursion tree until you get a new recursion tree。

😡，嗯。So you know this。Sounds like it's。Maybe kind of useless。

 but there's a lot of interplay in applications of more complicated data structures where you say run this algorithm but record what you're doing and then go back in time and fix it you probably heard of one of these applications。

😡，I think it's spelled get。嗯。Okay that's as much as I want to say today。

 so got a few minutes but I'm just going to let you go early， I'm happy to answer questions up front。

 I will talk more about the exam on Thursday。对。嗯。

![](img/da53b589a96b3b9108a4e64b4e548b72_3.png)