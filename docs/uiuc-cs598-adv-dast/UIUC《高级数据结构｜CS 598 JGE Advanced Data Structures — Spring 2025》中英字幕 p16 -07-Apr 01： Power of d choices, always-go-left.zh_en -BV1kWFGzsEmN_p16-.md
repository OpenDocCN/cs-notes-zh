# UIUC《高级数据结构｜CS 598 JGE Advanced Data Structures — Spring 2025》中英字幕 p16 -07-Apr 01： Power of d choices, always-go-left.zh_en -BV1kWFGzsEmN_p16-

![](img/721c539ef6f75f192cba8ff164974036_0.png)

So the thing I want to talk about today。Is something that came up last Thursday and it created enough discussion that I thought I need to go back and actually。

 first of all make sure that I understand the result correctly and secondly try to provide you with a with an actual proof and this has to do with this。

Power of multiple choice。Paraigm where。So in the classical balls and bins experiment。You。

 if you toss N balls。Independently and uniformly at random。Into end bins。Then with high probability。

 the maximum load is going to be approximately natural log n over natural log natural log n。

Okay I will prove at least the upper bound on the maximum load in a second just to sort of get us warmed up with the probability。

But then there's the。The the choice。Paraigm。so the connection here to hashing is hopefully obvious that if I have n items that I'm storing in a hash table of size n。

 and I use some standard overflow method like chaining， what this says is that with high probability。

 the longest chain is going to have length slightly less than logM。But one technique that we saw。

With related to cuckoo hashing。Is instead of picking one bin uniformly at random。

 I choose D bins uniformly at random。Then I put the ball into whichever one of those bins has the fewest earlier balls in it。

Okay。So。Each ball。Choooses。D bins。Independently。Uniformly。At random。And then， the ball。Goes。

To the emptt。Of those deepbs。Now， in this case。The claim is now with high probability。

 the maximum load。Drops。From。嗯。Log log and log n over log log n to log all n over log D。😡。

So there's a really dramatic shift between。You go where you're told and you're given two choices and you go to whichever one is the best。

And then there's slightly less dependence if you're given three choices and you go to the best of the three options you're given。

So。This。诶。Actually doesn't matter， this is slightly different from what I said on Thursday。

 so I'm correcting my mistake here， it does not matter how you break ties。Okay。

 so the situation where breaking ties to the left。Actually， helps is a slightly non uniform。

Distribution。Okay so the idea is I'm going to take my bins。And I'm going to break them。Into。

D chunks of size and ever D。Okay， so I have。Break and bins。Into D。Chunks。Each。With。And over D bins。

And now each ball。嗯。Coseses a random。Been in each。Chunk。And then the ball goes into the lightest bin。

He。And then so。Baold。Goes to。Emppttiest。Of。Those。D bins。 Now， this is very slightly non uniform。

Because I know that one of my chosen bins is going to be in the first chunk。

 I know that one of my chosen bins is going to be in the second chunk and so on。

 a uniform distribution， every choice， every randomly chosen bin is equally likely to be in any one of those chunks。

So I'm in some sense， forcing uniformity that among the chunks。

 the uniform distribution wouldn't enforce。A。And then there's the weird thing that happens if I break ties randomly。

Then I still get log log n over log D， but if I break。Ts。To the left。Then I get log， log n。Sorry。Log。

Log n over D， and there's a weird constant in there。And this is the。Best possible result。

That you can get from any non uniform choice。Of those deep bins using any tie breaking rule。

So in some sense， this is the best that you can hope for。

 given that you have to choose among D somehow randomly chosen bids。

No matter what that distribution is that you're using to choose those D bins。

 no matter what tie breakinging rule that you're going to use to break ties。

 your max load is going to be at least this much。So this even distribution of chunks where you choose one bin in each chunk and always breaking ties to the left。

Is in some sense， optimal。Okay，And so when we were talking about cuckoo hashing。

In Pkin Roadler's initial formulation of cuckoo hashing with。Two has functions。

You actually were in exactly the situation where you had two tables of equal size。

And one hash function gave you an address in one table and one hash function gave you an address in the other table。

Now here when D is 2， it doesn't really matter all fades into the Big O。

 but the natural generalization of cuckoo hashing， you would have D tables。And D hash functions。

And each of those hash functions would give you an address at each one of those tables。

And now we're in exactly the situation here。系。U。So。This isn't the。Original source of these。呃。

The original source of these bounds。But。The proof that I'm going to give goes back to。

 believe it said 2006。Stock paper by Viing。It gives a reasonably straightforward proof。

 for the at least for the upper bounds。S that these bounds are actually tight。

 there is an argument in Viing's paper， but it's a little bit technical and so mostly I want to give you the high level overview of where where these weird log logs come from。

And I'll refer you to the paper for the more technical details。Okay， so。

This this is a more precise description of the effect that I was describing on Thursday。

 hopefully it may be a little bit more believable。That when you just have a completely uniform。

Assignment for each of the D choices， tie breaking doesn't matter。

But if you have things breaking up in the chunks， the tie breaking strategy actually does matter。没。

Questions about what the results says。Okay， cool。All right。

The first thing I want to do is just sort of very quickly。啊。就是。

Why you should believe the initial login over log login？Um。It ultimately just boils down to counting。

And。So。Let's look at first uniform。No choice。Okay， so。Let's see。You just。Take again。

 so just to remind you， we've got end balls going to end bins。Uniformly independently distributed。U。

 so been the probability that bin one has at least。Some number capital M balls。Well。嗯。

If I choose any particular M balls。Each one of those balls is in bin one with probability exactly one of end。

系。So。I've got1 over n to the M term here。And on the other hand， there are at most。In fact。

 there are exactly N choose M possible choices for that subset。A。

Now I have to put a less than or equal to here because these events are not entirely these M tus of balls overlap。

 and so the probabilities aren't independent， but the union bound allows me to put an upper bound here。

I sum over the and choose M possible M tus for each M tuple。

 the probabilitybabilities is exactly one over end to the M。系。U。So。啊。

Need to use a couple of approximations here one is that n choose M you know by definition。

 this is n factorial over n minus M factorial M factorial。

 but this is pretty easy to see that this is less than n to the M over M factorial，The term。

 the numerator and the term the denominator。The numerator， you can think of that as。Just。

M different fractions， and then I throw away some lower terms from the top factorial。

 each of the terms on the top is at most M。This isn't quite。Oh， right。

N factorial over n minus M factorial。This fraction here。

That's n times n minus1 times n minus2 to n minus m plus1， theyre M terms in there。

 each one of those factors is at most n， so trivial each one of them is less than n。

 so the product is less than n to the M。系。U。That's。One possibility。That upper bound implies。

That this whole fraction is less than one over M factorial。Okay。So that。Implies this。

On the other hand。If I look at this expression。And let's look at the expression。

M to the M over M factorial， but this is kind of coming out of nowhere for a second。

This is less than the sum over all I greater than zero。Of M to the I over I factorial。

 The reason that this is a less than is because this is one of the terms in that cell。

And all of the other terms in the sum are positives。嗯。

But this is the standard sort of Taylor expansion。Of you do the M。

And if I plug this in and rearrange some terms。That's going to imply that this is at most。

E to the M over m to the M。This is really the sort of crudest form of Sterling's approximation that n factorial is approximately n to the n over e to the n。

 there's a square root of M error term on there which。

I'm throwing out to give me a script list down there。Okay。😊，嗯。So。

This also means the probability that the。Maximum bin as at least M balls。

Is at most n times e to the M over M to the M？Okay。😊，Now。If I set M to be。

For natural log of n over natural log， natural log of n。

And you can grind through the algebra if you feel inclined to do this。

This always comes out to be less than one over1 squared。系。Bm。

If you really want to see me grind through the algebra， I'm willing to do it。

It really at this point is just a question of plugging in the right value of M。

Heurding everything into an expression of the formed to the something。

Collecting terms and simplifying。There's one point where you have to take a fraction involving log。

 log n over log， log， log log n。And realizing that it's bigger than a constant。U。

So that's ultimately where the login log login comes from。

You'll notice that I've introduced a factor of four here。

 the factor of four is literally just to make the math easy。It's not intended to be。嗯。Sorry。

 to be very careful here it's not intended to be tight in any sense and in fact the true。

The true value of the maximum bin is with high probability。

 approximately one at times natural log n over log log n。

And they're probability varying that by a constant like plus five。Um。

Goes down rapidly as a function of five。Or minus five， again， goes down rapidly。

 so it's very tightly concentrated around this value。Okay。So。All right。And。Let's try this。Uniform。

D choices。Okay。So。Again， the idea is each ball， you need to consider the balls one at a time。

Each ball is going to choose D bins independently uniformly at random， in particular。

 there is a non zero probability that the ball will choose the same bin more than once。

So it's not that I choose a subset of size to uniformly at random。

 so each one flips an insidesided coin。Rolls an inside of die， excuse me。啊。Okay。So。

What I'm interested in bounding。Is。What is the probability？That。三。Bin。😔，Has。

Strictly more than L plus three balls。As a function of this parameter L。

 the plus three is there because putting it there simplifies the notation it's compared to putting it in other places。

 it's ultimately not it's ultimately going to fade into the background and the bounds that we're going to prove。

ok。Som what I'm going to do。What Viing proposes to do is to define an object called a witness tree。

This is an abstract combinatorial object。But it collects the probabilistic events that need to happen。

In order for a particular ball。To be the one that goes into a particular bin。

That already had L+ three balls in it。When it， went it。系。Okay。

 so it will witness a ball being the L plus third ball or the L plus fourth ball in a bin。Okay。

So this is a complete。Rooted。Dary。Tree。With。8ight。掉了。And each node in this tree。

Has an associated level， so level L， it's tied above the leads， so level L is the root。

 level L minus1 of the children's root level zero or the leads。

Each of these nodes is going to be associated。With a particular bin。And with the highest。

 the last ball that goes into that bit。So each node is associated with a particular ball。Hey， so。

Each node。Is。Associated。With。A bin。And the last ball。In that bin。At some time。Okay。嗯。And。

The overall event that's being witnessed。Is。That ball was inserted into that bin after L minus three other balls。

So。Here's the root。There's some。I'm going to use X。To represent the bin。And I'll say。

B to represent the ball。Okay， so here's the root。At BX。Now， it's gonna have。Do children？U。Now。

 intuitively what the children represent。Are the deep bins that could have taken the new ball B？

But we chose B X because it was the one that had one of the ones that had the fewest balls in it。

So these subt。Represent the fact that whatever been。Shows over here。

If this has more than L plus three balls。Then this bin must have more than L plus two balls。Right。

 because I ended up putting the new ball B into the lightest bit。

And that bin had at least L plus three balls in it。

So all bins of the D that I chose have at least L plus three balls in them。Okay， so。

When the witness tree for the whole thing is saying， hey。When I inserted ball B into bin X。

It had height at least L plus four at that time， the children represent something about another bin。

Or another ball at some earlier time。So everything that happens in the subtree is discussing what happened before X was in。

Okay。So。That I actually say this。So。Root。Is。Labeled。The last ball。In some。Overloaded Ben。啊。

Let's call that overloaded bin X。And。Clastball B。And so the children。Are associated。With bins。

H1 of B， H2 of B up through HD of B， those are the D choices。嗯。And each had。At least。啊。

L plus three bulbs。Before。X was inserted。So I continue building the witness tree recursively to reflect the state that that bin had that many balls in it。

开。Eventually I get down to a leaf。This is。Level 0。Jeps L。

What this now represents is so whatever ball was put into this bin Z。This is。Ball。A。Put into。

A thin sea with。At least three other bolts。睇。This is where the three comes from so one thing I can say about。

The probability。 so this you can imagine filling out this tree with whatever bins you want。

And just associate the balls implicitly with the bins。

 so ultimately this is a D tree with height L where every node is labeled with an integer from one to n。

But these represent certain events， so the leaf event here for leaf Z is at some point during the history of the data structure。

A ball was put into this bin for the fourth time。Now， at all times。

 the number of bins that have at least three balls in them by the Pieonhole principle is at most n over three。

There are most end balls going into end bins。So I can't have more than n over three bins with more than three balls。

So the probability。That this leaf is active。Is at most。One third。Actually， no， it's not one3。

 it's at most one over three to the D。Because in order for a ball to be put in a bin。

It already has three balls in it， it had to randomly choose D bins。

 each of which already had at least three balls in it。But each of those choices。

 each of those D choices only has probably most a third。Of succeeding。第二。

That's what what does mean for a。So ultimately， there's a huge collection of these trees。

in order for this event to actually happen， that some bin overflows。

The events associated with one of these three have to actually happen。That's what I mean by active。

 So the leaf represents an event。Namely， a ball was put into a bin。

 and it was at least a fourth ball。There are also going to be events associated with the edges that basically correspond to hash collisions。

And so the entire tree is active if all of the leaf events happens。

 the leaves are active and all of the edge events happens。 the edges are active。To make sense。O。嗯。

So what does an edge correspond to， so an edge？Event。Between let's say。

 a parent node P and a child node V， this means。That the。啊。Parent ball。engng。

Parentballs random choices。Included。呃。The child balls bin。Or should really just like been a V。

 Okay so when I was about to when I went during the history of the data structure。

I was going to insert this ball that is associated with node P。

The bins associated with the children have be are the D choices。

And I've associated a particular bin with each of those nodes。

 so actually I have to have that collision， one of the hash values of the ball at the parent must be the bin that's associated with the child。

系。So。The probability that a single edge is active。Well， that's exactly one of red。Is that right？No。

 it's actually D overed。Right， because。I'm saying one of these D random choices is that one。

And each of those random choices is uniformly distributed as probability one of random being that one。

 so again， by the union bound。The probability that an event that's attached to the edge actually happens is at most de overea。

系。So the probability that all nodes。And edges。Are active。Which is the same thing， I guess。

 saying probability that the entire tree is active。Is it most？D over n the M divided by。

Three to the QD where M is the number of edges in the tree。And sorry， Q is the number of leaves。

Now it's。This is a regular DR tree with depth L so we can plug in exact expressions for M and D。

 we'll do that in a second， but for now I just want to keep it like this。Now I want to point out。

At this point in the argument， I am。Hand waving slightly。So in order to make this argument actually。

Work， notice I'm multiplying a bunch of other probabilities together to get this upper bound。

 that only works if those events are all independent and these events are all independent。

 if and only if the balls associated with different nodes in the tree are distinct。

It is possible that what actually happens， the history of your balls and bins。You might get to。

 you know this ball hashees into these deep bins， that other ball or later hashees into three these deep bins and there's a big overlap and so when you're building the witness tree describes what's going on。

 you actually get collisions。This happens with very low probability。Ultimately。

 we're going to prove that the bad events happen。With very low probability。

 unless L is bigger than log log n。😡，Which means the number of nodes in this tree for interesting parameter assignments is only logarithmic。

So with fairly high probability， there are only log n interesting balls to worry about。

 each one chooses D random addresses。Those D log n random addresses are。啊。

Not quite going to be distinct because I can't make the addresses completely distinct because of the hash collisions。

 but the possibility that I'll through history encounter the same ball turns out to be small now again。

 still I'm handwaving here I'm providing intuition in Viking's paper he actually talks formally about how to handle the case that a ball reappears in the witness tree more than once uses some very careful pruning。

 ultimately it has no significant effect on the analysis。系。So。

 but I need to just be a little bit careful here。There's some slight hand waving here。

On the other hand， the number of witness trees that you can construct。嗯。

The combinatorial structure of the witnessry is completely fixed once I fixed this number L。

 each node is labeled with one of the bins。And so。Um。Well， if。Sorry， let me change this slightly。

Make this the number of。Nodes， so I can make this a minus1。The number of witness trees is。Ento the M。

Is that right？So for each of the M nodes， I have N choices for what bin is involved。Okay。😊。

So putting this all together。The probability that ane。Witness tree。Is active。

Comes out to be at most n to the M times D over n to the M。Minus1。Divided by 3 to the Q D。

 most of the ends cancel out。So this is N。Times d to the M minus1 divided by 3 to the QD。

Now I'm going to start approximating some stuff。Okay。

 so the first approximation is the number of nodes in the tree is less than twice the number of leaves。

Actually can say this。Number of edges in the trees is at most twice the number of leaves so this is D。

Sorry， let me make sure I get this right。呃。D to the d squared over3 to the D to the Q。

Now that expression in parentheses， d squared over3 to the D， that is bigger than1 over2 to the D。

So this is。Less than two to the DQ。And finally。Q is。诶。DVL。So this is n over2。

To the D to the L plus one。This is right。So now if I plug in L to be。Log base D of log base2 of N。

Plus。Log based D of alpha。T one。That implies that this probability。Again， going through the algebra。

 which I won't do。Is it most end of one over alpha？Log based D of something is the same as log base2。

 something over log base2 of D。So this term。This is log， log and over。冇day。Okay， so。It's saying。

 even if you're just a little bit over。That threshold。With no constant。

 there's no constant there in front。 you're a little bit over that threshold， the probability of。

That all of these events collectively happening。U droprops off。

Exponentially in how far you are away from that threshold。

So notice there's a log of alpha here and there's an exponent in alpha there。So the。

This is really again， a very tight concentration bound。系。So the punchline is。

With probability at most。One over polynomial。The number of balls in the heaviest bin is at most log log again over log D。

Plus a constant。Okay。Does everything uniform？Notice that the tie breaking rules didn't have any effect in this analysis at all。

The the only fact that I used in doing this probability calculation is。

When I put a ball into a bin and it's the 10th ball in that bin。

Every bin that I could have put the ball into has at least nine balls in it already。

That was the only fact that I used， so any tiebreak rules won't affect these events at all。Okay。

 questions about this。All right。So now let me go to the always goes left。The basic setup。

Is almost exactly the same again， you have this thing look that's a tree that sort of encapsulates a bunch of events that have to happen。

The leaves still capture the idea that I'm putting bin。

 a ball into a bin that already has at least three balls in it。

And higher levels are going to correspond to putting a ball in a bin that has more balls in it。

But the tree is no longer。Perfectly balanced。In particular。

Each node in the tree is not only going to be labeled by a particular bin。

 but it's going to be labeled by one of the chunks that contains that bin。😡。

So the children of every node are going to have one child associated with chunk one。

 one child associated with chunk2 up to one child associated with chunk D。

The levels associated with these nodes are not going to go down uniformly every time I the level of a parent is not always one more than the level of child because of the tie breaking rules。

Okay， so。Let's say。The chunks。Always。Go left。So now what happens？Is you say？Each node。

Let's associate it with a label that is the the chunk number and a height。 so a height is。

Crruudely the number of balls。Plus three， when a when the ball that's associated with this node is inserted into bin that's associated with this node。

系。So at the root。啊。This joke number doesn't really matter at the root。But I'll have height L。

 So again， this is supposed to represent a ball being put into a bin that already has L plus three balls in it。

嗯。嗯。So deeper in the。In the analysis， deeper in the tree。

 I'm going to have a node that is associated with chunk I and height L。It's going to have， again。

 D children。1 L。2 L up through。I minus1 L。I L minus1。I plus1。L minus1 up through D， L minus1。

So what this is saying is a ball went into a bin。In chunk eye。That means。That。

And it was the L plus third ball or L plus fourth ball to go in。

 so let me forget the plus three and just say I put a ball into a bin in Changhai and it was the e ball to go into that bin。

It means before I put that ball into that bin， that bin had L minus1 other balls。

All other chosen bins further to the right， also had。At least L minus one other balls。

Because if they had had less， I would have put them。The ballbe。All the bins further to the left。

Might have， you know。I had to have at least elbowballs in them already。

So balls the bined further to the left had to have more balls in them than the one I chose。

Because of the tie breaking rule， the bends further to the right。Could have had less。

 but only less by one。Otherwise， if there's something smaller， I would have pushed it over there。

So the levels are going to go down， but only for chunks greater or equal to I。

So I have a very different tree structure now。nodes that are associated with the chunk one。

All the levels go down。Nos that are associated with the chunk D。

 only the depth level goes down and all the other state the same。诶。So the。

The size of this tree is no longer simply governed by， you know， it's not just。L。

 not even just D times L one way to look at this is the number of leaves in this tree。Is。Governed by。

啊。Sort of generalized Fibonacci recurrence。ok。If I imagine that D is only two。

 then I have only two types of nodes。A white node has two white children。

 one level down each black node has a white child and a black child。Okay， so ultimately this is。

Defined。Otherwise， this is the sum from i equals 1 to d F of L minus I。系。嗯。

So this is this is going to be this is the number of nodes。

 the number of leaves in the tree is a solution to this recurrence。 Now。

 this is something that grows exponentially。With L。OkayNow， previously。

 we also had something that grew exponentially with。I was D， you know。

 the number of leaves is D to the L right here I'm going to get something that grows。

In a different way。嗯。This turns out to be。Asymptotically。There's some constant， which is。

 I think strictly less than one。Let me just write it as this is less than some constant times p to the D called p to the D to the L Okay。

 so phi2 is the normal。A。Sorry。😔，I'll learned to write eventually。

This is the normal golden ratio and as D goes up， these numbers get bigger。So fee three is about 1。

85。Phi4 is about 1。92 as a general rule。TheseThese constants feet to the D are always less than two。

 on the other hand， they're always bigger than 2 to the d minus1 over D。

And so there's an expression that's going to show up。In the analysis。

D times the natural log of this constant， this is always going to be at least。

D minus1 times the natural log of  two so。The growth of the number of leaves。Is。

Something that looks like2 to the L。Not like。D to the L。Which means。

That these events associated with these trees。Are more likely to happen。As a function of L。

In the non uniform case， than they did in the uniform case。

Which means you're going to overflow it smaller。 You're going to end up with smaller values of L。

Then you did in the uniform case。So the maximum load is going to be smaller in this non uniform setting than it was in the uniform setting。

Just a bit counterintuitive。But this is what the math says。嗯。Something is weird about this。

So I may need to go back through the paper again and check what this actually says what I think it says because something about this feels really off。

嗯。There's this effect which maybe only applies to me。And for that， I apologize that when I read。

Math papers。Everything makes sense。I read and go yeah， yeah， sure， yeah， yeah， sure， yeah， yeah。

 sure， and the moment that I explained it out loud。They go wait a minute what's going on。

 there's something weird about this that I don't quite believe because in in the initial。

 you know the original perfectly uniform trees，It was， you could imagine it like this。

 but now every level goes down at every child， and so the tree decays faster。

Here the tree is sort of decaying more slowly， so it ought to be deeper。

And somehow the math seems to be implying that it's。The tree ought to be larger。

 but somehow the math is arguing that the tree is smaller。

It may be that the answer is I shouldn't try to attach intuition to the math。

And I should just believe the formulas like a。Good little student。But。

I will go back through and add comments to the slides。啊啊。One said， look at the paper again。Okay。So。

The rest of the analysis is essentially the same。So。Each leaf event。Is。Ball goes into a bin。

That already has。Three other balls。So the probability of this happening intuitively。

 is it most one third there's again。This is the right intuition。

 but it's not right formally because it is no longer the case that。

The probability of a bin in chunk one。Having it most。Three balls。

 having three balls in it is it most one third？In fact。

 balls in chunk one are more likely to have more balls in them than balls in chunk D。So。

This is sort of correct if I choose a random bin。But you know， the probability of all leaf events。

Is still at most one over three to the number of leaves。

This is still correct essentially by a convexity argument。The King argues that， yeah。

There's a different probability associated with each chunk。

The average of these probabilities are the third and what I'm doing is essentially multiplying these probabilities together and that product。

Takes its largest value when all the probabilities we need the same。

 so this is actually an overestt of it。ok。But the intuition you can still keep as each leaf is going to be active to probability a third。

 and there are that many leaves。U。Again， the probability of all。Edge events。Is still again。呃。At most。

D over N。To the number of nodes。Minus1。Again， this is assuming that all of the various balls involved in the process are distinct。

 again， this happens with very low probability and so it does make a small difference in lower order terms in the final bound。

But。呃。嗯。We can ignore that。And again， the number of trees that we need to worry about。嗯。啊。

Is still what it was before？And to the M。So n to the number of nodes。

And if I go through exactly the same calculations that I went through here。The probability that。Any。

Tree， this form is active。Comes out to be at most and over to。To the。D times Q。

Only now sorry cus number of leaves， so I'll just write that。So this is at most。嗯。

N over2 to the D times。Fat today。Of。DL -1。And so if I plug in。L is。

Natural log of log base two of n plus log base， sorry。Plus， natural log of alpha plus1。All that。Over。

D times natural logga if feet to the D。Then this probability comes out to be less than one over end of the alpha。

So。This is。Log log in。Over a constant times D， when D gets big。

 that constant turns to roughly natural log of two。And so again， that there's a small bit of。

 if you go over this by something that looks like log of alpha。

Then the the probability of that event happening drops down to one over end of the alpha。 So again。

 get this very tight concentration around。This threshold value that decays doubly exponentially with that oh。

That error term。嗯。And。That。Is all I wanted to say about our of two choices in tie breaking。

I'm happy to answer any questions。The paper itself。

 the witness tree analysis in the paper is only about three pages。嗯。

The adjustments that need to be made for the various places where I was waving my hands that eats up another three or four pages。

 but the basic analysis is relatively readable。So if you do have questions or concerns。

I think the paper is well within everyone's ability to read。Okay。Thursday。

 I will be presenting whatever project proposals I have in my hands。I'll see you then。

 I'm happy to answer questions up front afterwards， thanks。

I have a question but not for the excellent topic that state。



![](img/721c539ef6f75f192cba8ff164974036_2.png)