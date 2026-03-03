# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P23：-23-Advanced Algorithms (COMPSCI 224), Lecture 24.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/e199958dbb12df061dcf59c09cc3feab_0.png)

Okay， so let's get started， you're scibing today， right， is that right， great？So yeah。

 at the end of last lecture， there were some there were just maybe maybe like a minute or two minutes more I wanted to say the main cost max flow but ran out of time。

 so I just put that at the end of the notes at the end of the lecture notes you can go look at that。

Today， I want to。Well， we only have three lectures left， I guess， including today。嗯。

So I want to show you some more topics today， I'm going to talk to you about another way of dealing with。

Kind of NP hard problem， so earlier in the course。We saw that one way was approximation algorithms。

 right if you can't solve the problem in polytime， then maybe probablyably get a two approximation or a log n approximation or something in polytime。

Okay， so another way of dealing with it is actually solving the problem in exponential time。 Okay。

 but then you want to make that exponential as small as possible， so。So。

I'll put fast in quotes today oh， it's today。We'll do。Fast in quotes。Exponential timing algorithms。

Okay。And we'll look at。Three ways of doing this， so exponential divide and conquer。

So we're going to look at， for example， the traveling salesman problem。We're going to do。

Pruned brute forest。And also randomization。We'll see how to apply these things to。OhLike three sat。

And we'll also see。Inclusion exclusion。Also。Kind of a similar thing。 They're very。

 I think they're equivalent to each other is Mobiious。Fastmobilbiious transform。An inversion。

And for this， we'll look at key coloring。Okay， so these are。

A few different ways to speed up exponential time algorithms。Or in some cases。

 we're not going actually speed things up。 We're going to。嗯。You know， lower the space complexity。

So there are some ways to get， say， exponential time， two to the end time。

 but then the natural implementation will also have two to the end space。

 but we'll see that sometimes we can get the two to the end time while having poly end space。

 things like that。So let's look at， let's just go through these。These techniques。

 is there any question about？Well， yes I didn't see much yet。So the first thing。

Exponential divide and conquer。Okay， so。The example I want to give you。Is TSP？So the input。Is。

A set P of points。And a distance function。Di。Which maps pairs of points to。诶。No negative numbers。

And let's assume it's a proper distance function， so this is a metric。

 so it satisfies triangle inequality and it's a metric。

 Diss are zero only if the two points are the same。And we're also given。呃。Two identified points。S T。

 which are in P。系。And the goal。Is to。Visit every vertex exactly once。Start at S and at T。

 visit every other vertex exactly once， and the total length of your tour should be as small as possible。

Have people here seen traveling salesmen？Find。ST path。Visiting。Each vertex。Once。And。Minimize。

Total length of path。So。For the rest of the lecture。If I say o star of F of N。That means。Oh。

 love Paul and。Times of of event。 Okay， so。I'm not really going to care too much about polyan factors。

嗯。So what do we know about TSP？Okay， so what's the most straightforward algorithm。

Let's look at both the time and space。And what are you。Don't think I mean， just。Yeah， tri every path。

 so try basically all the orderings of the intermediate vertices。

And theyre n minus two factorial of them。And each one， you can sum up the length of the path。

 it takes about end time。So it's O starve and factorial。And the space。Is polyen。Okay。

 so this is brute force。Okay， two。嗯。People might probably have seen something else。

 so something to trade off the space for the time。So get time， which is much less than n factorial。

But you're allowed to use exponential space。Yeah， yeah， so dynamic programming。 yeah。

 so your time will be O star of 2 to the N。And your space。We'll also be O star of2 to the N。

And this is dynamic programming， and the point is you can define a function。嗯。Let's say。

So you can say let F of。嗯。X， S。Be the length。Of the。Shortest。X T path。Visiting。Every vertex。

Every point， I guess， every point。In S once。Where here S is a subset of the points。and what you want。

Is F of S comma， all the points， well， you don't need S or T。Right。

So the number of states of your D program。A， well。How many current so this is really like yeah。

 so you're currently at vertex S， you're trying to get to T。

And you still need to visit everything in this set。That's what this means。Okay， so there are。

 so this is an arbitrary subset that like throughout the execution of this algorithm。

 and you can write down an easy recurrence for this thing， right。

 where basically you try all possibilities for the next vertex to go to。

 so this over the course of running the algorithm could be any subset of the of this set。

 So there are two to the n minus two possibilities， roughly two to the n possibilities here。

 about n possibilities here。So the total number of states of this dynamic program is about n times 2 to the n。

 so your space is about。And times 2 to the n。And your time， well， for each state。

 you need to loop over the next vertex to go to， which has about n possibilities。

 So your time will be like n squared times 2 to the n。嗯。So great。

We can get poly space with n factorial time， which is super exponential。 It's like n to the n。

 which is like2 to the n log n。嗯。Or exponential time with exponential space。 And actually。

 it's an open problem。To get。嗯。O star。Two to the end time。Polyan space。

It' not knowing how to do that。So。What are we going to do instead？

We're going to get something like oh of。4 plus epsilon。To the end time。And。Poly in space。You know。

 for any。咁三点。No。So there's no trade off。 So actually， I just did this to。To save myself writing。

 the actual time complexity is something like4 to the n times roughly end of the login。

But that's that most。4。01 to the end， for example。Yeah， so I just shortcuted。Think of this as 4。

01 to the end。Or4。00 under the average。Okay， and this is going to be via exponential divide and conquer。

And it's actually。A fairly simple occurrence， so let me write it down。So。🤧。So， let。Ot。UST。we。leength。

Of。The cheapest。S T tour。呃 touchuching。Each point in U。What。Okay。And once divide and conquer。

 you try and split the problem in two or multiple roughly equal pieces or something， right？

 So what are we going to do， Well， the first half of the tour is going to go through some set and the second half of the tour is going to go through some other set。

We don't know what those sets are， so we try all possibilities。That's the whole algorithm。So， opt to。

UST。Is the men？Over S。Being a subset of u， let's say the size of S is the size of u over 2。Plus one。

And let's also say。Ha。S T union S。Is now you looks like so union。T union S is everything is U。

And T intersect S。Is some point M。Okay。So we're trying all subsets of roughly half the size。And then。

We're also going to say like where does？When we finish going through that half subset。

 where do we end up？And then pick that's where we pick up and continue in the second half。

 So we're going to go through half the points of U call that S。

And we're when we finish going through S， we're going to end up at some point M。

And then now that we're at M， we' we have to finish going through T。

 So T is all the remaining points in U。Okay。And then now what's the， you know， So what is it。

 So what's the best way to do this？ Well， the best way is to go。Through S from S to M。Plus。嗯。Opt of。

Now we have to go from M to T。Yeah。Okay。And now we just。Compute。Ot。Of。P。もします。呃。PST。

Just by just recursively。 Okay， just， you don't even have to do anything smart。Dev。

So the space complexity。Is pretty much just。It's definitely polyan right。

 because at every point you just really have to remember the current set that you're at。

 plus all the levels in the recursive stack above you。

The depth of this recursion is no bigger than log of the number of points。And to remember。

 the current set takes again at most end space。Okay， so。This is poly in space。How about the time？

It satisfies a recurrence T of N。Is the running time at end points？Is oh， and then the recursive。

 When do you end this recursion， The base case is when。Just。

It's trivial where basically S is only the point M or something like that。Theyre only the points S&M。

So T of N。嗯。Well。We have to pick M。😡，So there are n minus two choices to pick M。

And then we have to pick， we have to pick capital S。As well。That's something like。

Times n minus2 choose something like the seal。Of n minus-2 over 2。嗯。

And then we get to decide for each partition into S&T。Are we going to put？

Little less on the capital S side or on the capital T side。So there's some two。 this， I mean。

 this doesn't really matter that much。 And then times T of。What's left？

Whatever this roughly end over to。Okay。So if you solve this recurrence。

So it'll leave it to you as an exercise。This recurrence solves to something like T of N， I think is。

呃。All of。Four to the n times n to some constant log n or something。Okay。So。That's， that's it。All。

So that's a simple idea。I want to get into some of the more。Some of the other ideas we have here。

 any questions about？About this。About the algorithm？Okay great yeah。Yeah。

 there's this kind of tantalizing up from a problem if you。Feel like it。Good。How about next。

 So let's do。I going to show you this prun brute force。So， let's look at。呃。An example problem。

Which is three set。So the input for threeat， what does that look like？It's a formula。诶。

What's the right， so let's call it feehi， which is clause1。And clause 2 and I dot clause M。

Each clause。Is an ore。Of three literals。So let's say X。I1 or X I2 or。

Xi3 and some of these can be negated。And let's say that there are。And total variables。And the goal。

Decide whether。There exists an assignment。X equals a。Which。Makes。This phi evaluates a true。

So people have seen three set。Okay。So。Good， so algorithms。Okay， so what's。

 what's the most straightforward algorithm。那是。So time。Is0 star2 to the N space。Is polyen？

This is a bru force。Okay， so let's look at。Let's look at how to do just we're still going to do brute forest at first。

But we're going to do a pruned version of brute force。Okay so。So。Just notation。So given。given。

 so let's say。If I say like phi X or something like that。This is the new formula。Obtained。From Pi。

By setting。Let's say x X1 or something by setting x1 to be true。And if I say。If I say like， you know。

 P。X1， not x2。This is the new formula setting。X1 to be 1 and x2 to be 0。Okay。🤧K。

So another way of going about brute force。Is。🤧。Keep doing the following。Pick。Aly like this。Let。

C1 be some X or Y or z。This is the first clause。So we know that and one of them might be negated。

 We know that one of these things has to make the clause satisfied。So we'll just try all three。If。嗯。

If satisfy if the formula fee given X is satisfiable。Return true。But maybe it's not。

So then we'll try setting why。Why to be 0 else if。It's possible to satisfy Phi Y bar。Return true。

Elseph。Satisfiable。Fizi。Return true。Else return false。So let me this algorithm here is。

My SAT algorithm。Okay， so it's a recursive algorithm。

And there's some base case I didn't bother writing right， so once the formula is empty。

 you just say true。嗯。So what's the running time？What's the recurrence for the running time。

 N is the number of variables。Yeah， three。This is at most three times t。Then minus1。嗯。

Plus plus some polyanne or something。Which is when you solve it， O star of 3 to the n。

Which is worse than。That other one where you just try everything。But what's something。

 what's so now we're going to get into Pruned root4。

 So what's one thing you can do to like optimize this code。Yeah。Yeah。And你就。Yeah。Sure。

You're saying when I set x to1。Before this recursive call。I can go through the formula， and。

Simplify everything that is already now satisfied because x is one。 Yeah， you can do that。

 And also all the clauses， which have no x in them。

 you can remove the nod X and make it have only two variable， two litals And instead of three。

 You can do that。 Yeah， what's something else you can do。Yeah。

 you can assume X is set to false because here if we ever get to this else。

 it's because this returned false。Which means that there is no satisfying assignment where X is true。

 So from now on， we can just assume that x is actually false。Right。Yeah。Oh here。 Yeah。

 but M is at most N cubed or something。 Yeah，Let me say， it's a note。M is O of N cube。嗯。

The number of possible clauses on n variables where each clause has only three variables in it。

 or three literals is at most。Eight times then choose three or something。

 eight because you can choose if it's innegated or not。Okay， and again， when you get to here。

 you know that it's not possible to have y being set to zero and still satisfy this thing so you can also。

Right， you can also assume。That you have Y set to true now。

So this yellow version is now the pruned brute force that I mentioned。

And when you to do the pruned one。You get。T of N。Is that most T of n minus1 plus t of n minus2？

Plus T of n minus3。Plus， polyen。And when you solve this recurrence。You can show that this thing is。

Something like 1。8 something or other to the end。Okay。So it's the。To call this constant C。

 C is the largest root。Of the equation。X cubed minus x squared minus x minus1 equals to 0。Okay。

 so you can。You can kind of play these games in more and more complicated ways。 Okay， so you can say。

 if I'm at， you know， if I'm in this， if I'm doing this recursive call。

 I can assume that there exists a clause， which has only two literals and then etc cea， et cetera。

 and just kind of reason through the actual recursion tree and。Prune thing。

 like kind of prune things away。 Okay， and you can make this constant smaller and smaller by doing that。

Okay。And there are a lot of papers that did that for a while。嗯。

Let me show you other things you can do， and then I'll show you。I'll show you one algorithm that。

It a totally different approach， which was the record for a brief moment。

About 1 a little more than 10 years ago。 And I think even the current algorithm。

 which holds the record is more along the lines of that approach than this kind of。

Pruruned recursionions to re approach。Okay。So let me show you one more。Another。Smarter brute force。

Okay， so。So without loss of generality。We know。So， let's say。Suppose。A star satisfies。

So phi is satisfiable。If it's not satisifiable， then the algorithm'm going to tell you is just going to not find a satisfying assignment and we're going to output that it's not satisfiable。

 so without loss of generality。We know。And we know in assignment A。Such that the distance。

 the having distance， the number of variables where the assignments differ。Is that most N over2。

 Why do we know that？Why do we know such an assignment？でそょう。

When you say this or the negation of what。 So we don't know a star， I'm saying in our algorithm。

 we're gonna assume our algorithm knows something that's within N over2 of a star。とい意見。

Speaak in the assignment A， yeah。There go then。O来 see。Right， right， so yeah， so yeah， as Yarick said。

Well， just take A to be the all zero string and if that's not within n over two。

 then the all1 string will be a within n over  two， so take any assignment and inigation。So。

 we might have to run what I say twice。One for the all zeros and one for the all ones。Okay。

And now what do we do？We're going to try and， we're gonna try and fix。

 So we know that we're only off on N over 2。Variables。But we don't know which ones they are。

 but we're going to try and fix those in over two variables。While there exists。嗯。An unsatisfied。

Cllause C。Pick。One of the variables。And see。And flip。It's assignment。对。One will stop this。Loop。After。

And there were two iterations。So if this loop goes on for more than ever iterations， we just quit。

Okay， so。I so here's the point。 if， if our assignment is not a satisfying assignment。

And that means there's some clause which is not satisfied。 So we must be wrong。

 Our assignment must differ from a star and and at least one of the variables in that assignment。

Right。So。We don't know which one of the three it differs on。 So what do we do？Yeah。

 not really so yeah， we're going to get there， pick one randomly， but just pick trial3。

 trial3 in a brute force way。Okay。Just recursively。And if none of those worked， okay。

 then we're out of luck。Right。As we're doing this brute force in this trying all three。

 if there actually was such a satisfying assignment a star。

 then there will be a recursion path of depth and over 2。

Where we actually made the right guess every time。As to which thing we differed on。

And then we would actually halt with a star or some satisfying assignment。Right。

So what's the running time of this algorithm？Are people clear on what the algorithm is？

You say there's。た。Oh， so。I should really say try each of the variables in C recursively and flip it。

So for each of the variables in C， flip its assignment and A and then continue recursively back to the。

I guess I didn't say this。Is it maybe it's unclear what the algorithm is？Yeah。

 so we imagine a brute force recursion。Which does the following。 Okay。

 the brute firstcursion is the following。 It finds an unsatisfiyed clause。

And then it looks at the three variables in that clause。

 and it recursively tries to flip each one of those three。

 so it flips the first one and recursively runs the same thing。

And then it flips the second when recursor runs the same thing， et cetera。

 and if the recursion depth ever goes more than n over 2。It just like quits this this。

It doesn't go any further into the recursion。So the point is。

 if we're actually at distance at most N over 2 from a star。

 there will be some path in this recursion tree that made the right guess on every stage。

And then we would actually find AS SAR。The only time this would fail is if there were no satisfying assignment or if we were more than an over two away。

 in which case， the negation of。Of the initial satisfying assignment it would have worked。Okay。

So what's the running time for this algorithm？再。Yeah， route three to the end， right？So the runtime。

Is o star of3 to the n over 2， which is root 3 to the n。And。Root3 is something like， what is route 3？

1。7321。Okay， so that's another algorithm that gets a better。Basedase in the exponent。

So now I want to tell you an algorithm， which。it looks similar to this algorithm。

 but yeah it's going to do something random， as you said。And it's going to get。A really good bound。

 which。You know， was。Was a。Is is the base of， of kind of the best known ones now so。嗯。Randomization。

So I'm going to show you Sning's algorithm。And the journal version was in 2002。

It's going to get time。Which is O star of four thirds to the n。And space polyen。The current record。

It was， I hope I got this right。 It was annoying tracking this down because。Every time。

Every time I thought I found the new fastest algorithm。

 I realized that four months later something someone shaved a 。01。So let's see what did I find。

Did I write it， I thought I wrote it。Yeah， here we go。If you're randomized。You can get time。

 which is something like。O to the one point。307，0，4。This is hurtley。Sycom。2014。

And then deterministic。Algorithms。You can get。呃。1。3303 to the N。This is。成妈。So I think these。

 some of these algorithms anyway they。嗯。I mean， this is true not just of these algorithms， but of。

Algoms that， you know were that。That were shown before。 they kind of take。Different ideas， like。

 they combine this pruning approach with the randomization approach。 And they show that。

Kind of the men of the two has to do well or something of that flavor brge。 So I mean。

 there's more that goes on as well，Every time there's a new idea。You can like combine it。

 You often can combine it with the previous ideas to， to make。

The resulting algorithm even faster than either of them。Okay。Let me write down the algorithm。

 So let's say algorithm， before I tell you what Sning's algorithm is。It uses the following subrtine。

 And then once we have the subrtine。The algorithm is basically run the sub routine lots of times。

Okay， so。So let's call it algorithm S。So one。p a。Uniformly。At random。And2。Repeat。At most t times。

Let's see be the first clause。Not satisfied。My a。Flip。A random。Variable。And see。好。That's it。这小人。Yeah。

 so T is going to be a parameter that we're going to set。嗯。Yeah， well set to you。Yeah。Okay。

 questions about the algorithm。I mean， actually we're going to run T。

We upWe're going to end up running it in the actual algorithm of T being like n。

Have people seen the randomized， I think， well， anyone who took CS 124。

 I guess last semester would have seen it， but I'm curious how many people have seen this random walk kind of algorithm for twoat instead of threeat。

三十三。So you can do the same things for， you know， Ksat， right， you can pick a random assignment。

 And then as long as there exists an unsatisfied clause。

 flip a random variable in that clause and keep going until it's satisfied or until too much time has elapsed and then you give up。

嗯。Actually， no， I said did I say we're going to run it with T being End note。

 we're going to run it with T being4 thirds to the end。嗯。

Or you can think about it also as we're going to run it with T being n。

 and then we're going to do this algorithm multiple times。So with twoat。嗯。这就是。Similar。

Algorithm for twoat。As due to Papa Dmitri and think Fox 91， something like that。Okay。

So you can show that for TAT。If you run this for about n squared steps。

100 n squared steps or something， if there actually is a satisfying assignment。

 you'll find it with probability at least two third。

So you can drive that  error down by just running this algorithm， log one over deelta times。

And if none of those iterations ever find something， you'll just output fail。 Okay。

 so that's an algorithm that。If there actually is a satisfying assignment。

 you might not find it with probability Delta。But with high probability， you'll find it。

And how do you analyze such an algorithm as the one above？So we're going to do it via Markov chains。

Who here has seen Markov chains or knows what a Markov chain is？So most of you， but let's just recap。

So。Markov chain。Is a directed graph？Okay， and every。Fort every edge。Yi has。A probability。

Associated with it PE。And。For all。Vertices V。The sum over E leaving V。Of P E should be one。

 So it basically tells you， you， you imagine that you're moving around vertices in this graph at every step。

 there's a distribution over which neighbor you're going go to next。

that's told to you by these edge probabilities。In our case。The graph G has。Is a path。On in vertices。

Or n plus1。And vertex I。Represents。Of the distance。From A to a star。Is equal to I。So。

Here's their graph。It doesn't represent a specific assignment。So there。

 there are many assignments which might map to the same vertex。

 It only looks at the distance between our current assignment A and。The sum fixed。

 there might be multiple satisfying assignments A star。 And we're just going to fix one of them。

 And we're going have a distance to that。So。Initially， we picked a at random。 So initially。

 the the distance is some random number between 0 and n over 2 and n。

 It'll most likely be somewhere around n over 2。So initially we're here。And then at every step。

We pick a clause that's unsatisfied and we flip one of the variables in it at random。Okay。

So either that variable， we already agreed with a star， in which case， by flipping it。

 we are making ourselves。Agree less， which means we go to the right。 We increase the distance。

 or we actually did disagree on that variable that we flipped。 in which case now we agree。

 So the distance went down。So。So actually all these all of these it's a directed graph's like。

It's of like this。So at every step we can go left or right。And then at n， well， actually at n。

 there's no right and at zero， there's no left。So from zero。This probability is one。

 We're definitely going to， if， if we're ready there and we flip something。

 we're going to just increase the distance。 And if're at N， if we flip something。

 we're going to decrease the distance。How about any of the intermediate people？

So we know that let's say that we're currently， we're currently here。 We're distance。

 we're distance 2。 So this is distance 1， This is distance 2。So。

We pick a clause that's not satisfied。How many， you know， we， we know then how many。

We can say that we disagree with a star on at least one variable in that clause， right？

So there were three variables。 We disagree with at least one。

So our probabilitybillative going left is at least a third。And our probability of going right。😡。

Going right here is at most two thirds。Does that make sense？

This is true for all the intermediate vertices。Now our algorithm might halt。

With a satisfying assignment， without actually getting to0。

 because it might happen to find another satisfying assignment。But that's only better for us。

 right So what we're going to analyze is we're going say， look， if you've got some vertex。

 what's the expected time before you get to zero？But if you halt and find the assignment even faster than that。

 then we're only upper bounding your time anyway。So。Let's simplify our lives。But instead。

 just looking at。Kind of the infinite path。So here's n， n minus-1， and here's 0。

But there's also -1 over here。 there's also -2， et cetera。 There's also n plus1， et cetera。And。

Every single one of these。You go right with probability exactly two thirds。

 and you go left with probability exactly one third。Let's look at this Markov chain instead。

I claim that if you can prove an upper bound on the time to get to zero in this Markov chain。

 starting from somewhere between0 and n。Then that's going to be an upper bound on the time to get to 0 in that markov chain。

 You can only get there faster。So let's look at this thing。AndIn fact。

 what I'm going to do is I'm going to look at。The probability。

I'm going to look at the probability that we get， I'm going to make it even harder for us。

And I'm going to say not only am I so here we're okay as long as we get there within T stepss。

I'm going to say， what's the probability that we get there exactly on the T at step？Okay。

 so if we got there at time T -1 or T over 2， I'm not even going count it。

 We have to get there in exactly T steps。Okay，And even with this pessimistic view on the world。

 we're still going get our four thirds to the endbound。So let's say we start off。At distance K。

What's。The probability。That。We get。To0。After exactly。呃。T equals， we landed at zero。At exactly。

 let's say， exactly time。T being 3K。So really what we're going to do is we're going to run this work because we don't really know what K is。

 right？But as long as we're running it at least 3K steps， this analysis will apply。

And so we can set T to be like 3N。Then definitely the 3K mark will have passed。

And then we're going to show that this thing is going to be at least something like three fourths to the end。

Roughly。Okay。So then what do you do now to get an algorithm which runs in time4 thirds to the end。

 Well， we know that every trial， you succeed with probability roughly three/4s to the end。

So repeat it， you succeed with probability P。So repeat at whatever p times。

 and you expect to succeed at least once。And that's where the4 third to the end is going to come from。

 Does That makes sense。So。Okay。嗯。Good， so what do I want to say？In fact。More specifically。

Probably that。Make。K steps。To the right。And two K steps。To the left。Is it at least what？

So I want to look at， I'm going to look at this specific way of。Of succeeding。うん。Okay so。

It's the problem that we make exactly k steps to the right and 2 k steps to the left。

In our walk of length 3K。Is well， 3 k choose k。Times 1 over 3 to the K2 k。Times two third of the K。

Okay。And now let's just do a little Sterlings formula。3K choose k。Is equal to 3K factorial。

Over K factorial， 2 k factorial。Which if you remember Sterling。

ItSays that n factorial is theta root n n over e to the n。So this is。Well。

 if you just do this thing to that， you get something like， this is theta of。Whatever okay。

Three to the 3K over a 2 to the 2K。So just take my word for it that week。So。Let's call the star。

That implies that star。Is。theta of。1 over k。One third to the 2K。Two thirds of the K。Times。

Three to the 3K over 2 to the 2K。Which if I didn't mess up in my preparation should be。嗯。

One over root K。Times 1 over two to the K。Does that look right？Here you have a3 to the 2K。Do my。Good。

 good。 Here we have a three to the2 K。 here have a three to the K that completely kills this3 to the 3 K。

And then here you have  two to the K and 2 to the 2 K that makes it whatever 2 to the K。Okay， great。

 so this is one over K， one over two the K。 Okay， great。Okay， but。嗯。That's as a function of K。

 but we don't know K。So what do we do， We sum up overall possibilities for K。The probability that。

We find。Satisfying assignment。Is at least。The sum over k， k can go from 0 to n。Probability。

That distance。A an A star。Is equal to k。Times。Some theta of one over root k。Times1 over2 to the k。

Okay。So what's the problem that the distance between a and A star is exactly equal to k？Well。

I guess it should be something like。And choose k times1 over2 to the n or something like that。

So this thing is at least。AndTo a constant， let's pull this one of a root k is definitely at least one of a root n。

So。One over root end。2 to the n。Now let me just put one root end。Times a sum over k。嗯。Okay。

 so I shouldn't。 I shouldn't divide by 0。 I mean， if K is 0。

 then we're done in the first step anyway。嗯。1 over2 to the n plus k。So n choose K。

1 over 2 to the n plus k。Okay， so。This thing。I claim is。Basically。Equal to。Three， fourths to the N。

嗯嗯。Minus some constant。Why is that the case？Zoom and see this， there's just a slight trick here。Yeah。

 so basically just look at。Just look at one half plus one quarter。To the end。And expand it。

And what do you get？嗯。You get。Is that right？Yeah， so you can choose to get the one half n minus k times。

 and then you'll get the4 k times。 So one half to the n minus k times one fourth to the K is exactly1 over2 to the n plus k。

And there N choose K ways of doing that。 So really， this is the expansion of this。

 except we're missing the K equal zero term。The cake will zero term gives you。嗯。

And choose01 over2 to the n or something。 So you're losing a1 over2 to the n。

 So this is exactly equal to this minus 1 over 2 to the n。

So this whole thing is at least one of a root end。Times 3，4s to the end。Yeah。So this thing here。

 I'm going to call。You know， P。So our success probability is P。嗯。So if we run it。

 if we run this thing。knowP times1 over p times log1 over delta times。

 the probability that we never find a satisfying assignment is at most Dlta。

So this is our4 thirds to the end。Oh， star4 Thursday an algorithm， questions about that。Yeah。

 so I mean， I mentioned some of these bounds， which get。Which came after Sring's algorithm。

That drive down the 4/3s to 1。3，0， whatever， yeah。So I said yeah，Yeah。Oh yeah， yeah， we do。Oh。

 actually， I think his paper was not。Yeah， I didn't read that paper， but I did look at the abstract。

 So you're saying we already know an n plus M time algorithm for twoat。 So who cares about n squared。

So I looked at the， I didn't read this Fox 91 paper， but I looked at the abstract and he。

 he sort of just mentions it as like an aside in the last sentence。's like， oh， and by the way。

 it follows that we get this twoet algorithm。 his paper was actually about something else。

 I don't remember what his paper was actually about。 but he just observed that， by the way。

 this gives a simple twoet algorithm。Okay good， so in the last 15 minutes some change。

I want to tell you a little bit about inclusion exclusion and k coloring。And we'll see also this。

Fast Mobius transform and inversion。Okay。Any questions about this before I move on？はと合わって。媒体。Oh。

 you mean the ones that beat the four thirds to the end。So this paper of shortorning that gets this。

Kind of thing。Okay good， so let me say a little bit more。There is something more。

A slightlylight fanr you can do， which I think。Improves the polyfactor。

 like I think you might not actually need this one of root end。Maybe I'm wrong about that， but。

The paper- so shorting's algorithm really gets four thirds to the end。Up to this O star。嗯。

Then the papers afterward， which got improvements， they were。It was not。 It was not just by。

 It was not only by twidling around with。Better analysis of this， there were other ideas as well。

But I don't know those papers very well， so I shouldn't。So let me do inclusion exclude。

So what is inclusion exclusion？Well， here's one way of writing it。Next topic。

So no more questions about3 set。Yeah， yeah。Oh， so I think in real life， people use。

Other kind of heuristic。Not heuristic， but so people use this thing called was it DPLL。

Which I think is really fast in practice for。SAT instances you'll actually see。

 So SaAT is one of these funny problems where。There are systems out there that routinely solve large sad instances。

 even though it's， you know， supposedly NP hard。 And the reason is that。

The the NP hard instances are not。They're sort of rare。 and you have to like craft them。 I mean。

 not no， I shouldn't say that what am I saying NP hard instances。 The problem is NP hard。

 not an instance。 Okay， so。A lot of the instances that people come across in real life tend to be easy turn out to be easy to solve via some algorithms like D PL L。

You have to work hard to come up with instances that will break those algorithms。Yeah。

 so people aren't actually running the4 thirds of the an algorithm。Okay， good。

So the next thing I want to say tell you about， the next technique will be inclusion exclusion。🤧。

So what is inclusion exclusion？So the theorem。うんうん。So。For any。Seets。R subset equal to T。

We have the identity that the sum over S sandwich in between them。

Of negative 1 to the size of t the set difference。T。Is equal to。R equals t。So。H so。

A people have people seen this before the statement。This。So whenever I have like a logical statement。

 whenever I have a logical statement， P， bracket P evaluates to1 if P is true and0 of p is false。

So this summation is either going to be1 if r is equal to T。

Meaning that there's only one set that's in the middle， namely T itself。And if， if。

 if R is not equal to T， then the summation is 0。Okay。And why is that， Well， if R is equal to T。

As I said， the only thing in the middle is S equals t。

 in which case this difference has size 0 and negative one of to the zero is 1。

If r is not equal to T。😡，Then。🤧K。We're going to set up a bijection between the odd sized sets。

T backslash T minus S and the and the even size sets T minus S。 What's that bijection。

I should also say。For any non empty。For any sets or T is not empty。Oh， I。

 I don't really need to say that actually because if T is empty， then R is empty， too。 Okay。

 so I always get worried about empty sets and zeros these base cases。

These are sources of bugs anyway。If r is not equal to T， so let's write down a very simple proof。

Proof。R equals T implies the summation of R subset S， subset T。Is just the sum over S equals T。

Of negative 1 to the0， which is 1。If r is not equal to T。Pick。Some T in the difference。

And then we set up a e。Between。T minus S even。嗯。Between。Ask such that。T minus S even。And。

As suchs that this thing is odd。So what's the biject。A。Maps to。A。Sysymmetric different like kind of。

What do you call this Xor， I don't know if this is。What do you say for sets？Well'll say what I mean。

Take a set A。What's the projection， if it has T in it， remove it， if it doesn't have T in it。

 put it in。This is a bijection between the audit and even size sets。

So we know that there is exactly an equal number of sets where this thing is even versus odd。

 so this whole thing is0。So now we want to use inclusion exclusion。To design good algorithms。

So let's look at an example problem。K coloring。Okay。🤧So the input。It's a graph。Undirected graph。

G equals V E。let's say。The size of V is n， the size of E is N。K coloring。Is a function。See of。C。

 which maps V。Into1 type to K。Such that。If there's an edge U V in the edge set。

 it implies that C of U is not equal to C of V。So we have to color our vertices in such a way that adjacent vertices。

Do not have the same color。 And the goal。It's to decide。If K coloring exists。Okay。

Notice that it's equivalent， an equivalent question。Decide。Or equivalent problem， decide if。V。

Can be partitioned。Into K。Independent sets。What's an independent set。

 an independent set is a set of vertices such that there are no edges between any vertices in that set。

So if you can partition， so these questions are equivalent。 why。

 if you can partition into K independent sets， then everything that goes in the first set。

 you'll give color 1 and next set color 2， okay， And then you know that it's a valid K coloring。Now。

 how about the other direction， if you had a valid K coloring， then what would your partition be。

 Everyone that had color 1 would be one partition。 Everyone had color 2 of these partition 2。

 etc cea。 So these are equivalent problems。So we're going to focus on this version。Now。

What are some algorithms for k colorability？Someone tell me something。Brote forest。

 I'll just tell you brute forest， so brute forest。O star of K to the N is just a time。Polyan space。

This is a brute for。 Okay， how about something smarter。Does anyone know。

What you can do that's better than say you don't care about space， you want to get better time。

 what do people know？Dmic programming。 Yeah， we've seen that so much today。 So what。

 what kind of does anyone know what time you would get out of dynamic programming。

I'll tell you what the diamond program is。So。Kind of you're trying to compute F。Of。Our。S。Is。嗯。1。

If possible。It's a partition。S。Into our independent sets。And zero otherwise。And we want。F of。KV。

 right？And there's a simple recursion。To compute FMRS。Basically， just loop over all subsets。😡。

Capital R。 Let me not use R twice， so。There's a simple recursion to compute capital F of TS。

 loop over all subsets R of S。And。if R is an independent set。The now。Try and see if F of t minus1。

 S minus r is possible。Right， so the space of this， you have to remember T。

 that's just n that's just at most K。 this is a number that's at most K。

 You have to remember this subset S。 There's two to the n possibilities。

And within for each state of the DP， you have this recursion that's trying all subsets of that。😡。

So definitely the time is at most four to the end。For every subset， you loop over all subsets。

Actually， the time is even three to the end。Do people see why the time is three to the end？

So the time。Is O star is a。Let's say at most star， that's O star for my made up notation。Of the sum。

Over， s is subset of V of roughly 2 to the S， right？Which is the same thing as the sum。

 but what's the size of S， The size of S is anything from1 up to n。Of n choose I。

 because I can choose the set S。 there n choose I possibilities times 2 to the I。

Here's one way of interpreting this sation。I have a string。😡。

Where every digit in the string is either 0，1 or two。😡，I choose I of the digits。😡，To not be zero。😡。

Okay， so I loop over all I， I choose I of the digits to not be zero。All the other ones are 0。

 And then from the ones that are not0， there are two， I choose if it's gonna be one or  two。

 So there are two to the I possibilities for that。 So this counts the total number of strings of length n where all the dig are 0。

1 or 2。 So this is exactly 3 to the n -1 because I didn't count the all zero string。So。The time。

Is O star3 to the N？And the space。Is Paul Yen？No， the space is Im saying thing is O star 2 to the end。

😡，Because I have to remember all these sets， right。

 S can be one of two to the imp possibilitiesibilities。Inclusion exclusion， on the other hand。

Oh whoa， let mean not erase。第二。Right。Thank you。I think I'll actually be able to。Finish saying this。

Inclusion exclusion。You can either get。O star of three to the end time。And poly end space。Or。

O star2 to the N。Time and space。And how does that work？Let's define。F of S to be one。

If S is a non empty。Independent set。In zero， otherwise。And define。冇 law。

It's called the Zeta transform。Thanks'4ier transform， except it's not。

F hat of S to be the sum over R is subset or equal to S of F of S。

It just counts how many subsets of S are non empty independent sets。And the claim。Claim。Is that。

G is K colorable。If and only if。The sun。Over， s is subset of the vertices。

 negative 1 to the n minus the size of s， G of S。So the K is bigger than zero。Okay。Of SG。second you。

Yeah，对。I think we're basically out of time， but let me just say something and I'll finish up。

 maybe I'll just put the proof of this in the notes。This follows。

 this is like almost immediate from inclusion exclusion。O。But。嗯。The point is now you can compute。

You can compute all the F hat of S values。In。3 to the end time and polynomial space。 So basically。

 basically the new problem。It's the compute。F hat of S。For all us。Okay。

 and I claim that you can do this。You can do this in the time and space that I said。

 and maybe I'll devote the beginning of Tuesday to explaining why and then we'll do something else。O。

