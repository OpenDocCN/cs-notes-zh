# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p30 20231205-Dec 5： Final exam review (part 2) .zh_en -BV1Mh7RzaEL2_p30-

![](img/8208d567c77fa57e75a8db08595b94cb_0.png)

Hi everybody， so as I promised in lecture earlier this afternoon。

 I'm going to walk through the rest of the practice final exam that I started talking about in class。

This will be the first of two practice exams， the other one is already posted on the coursese webp page and I will post a video like this walking through that second practice exam on Thursday。

So we went already in the other video that's on the listed on the topics page。

We went through a high level read through all of the questions。

And we skipped over the true false questions and we tackled problem two。

 which was about DFAs and whether they accept a finite or infinite set of languages。

How to express that and compute that in the language of graphs。And we also went through。

Both of the NP hardness reductions in problem four。

 I do want to reiterate that the question on this practice term and the one that will show up in the final exam。

We will give you two problems and you pick either one of them to prove NP hard。

 so those seem to be a bit of discomfort with the idea of doing threeSa reductions。

 so hopefully the other one is a bit more familiar if we give you two options。

So what I want to do in this video is finish going through the other problems。

So just to summarize here。Problem six is a typical midterm one style question。

 describe a language over the set 01 and ask for a DFA or an NfaA that accepts it and a regular expression that describes that language。

And then another language where we need to prove that the language is not regular。

There's a question about hiking in the mountains， which。Smells a bit like a graph question perhaps。

 so just say maybe this is something about a graph。Um， especially because you know I see this。

 you know， longest hike thingum that immediately should suggest， in fact。

I'm not just going to want to build a graph， but I'm going to want to build a direct ascyclic graph because in general graphs。

 I can't compute longest things， either longest things don't exist if you allow repetition or they're NP hard to find by a reduction from Hamiltonian path。

Problem four we already did。Problem three is this rectangles tiling by dominoes if we look back at this i'll you know show the picture again or as you're watching this video it's probably a good idea to have。

The actual question， she opened in another window。And we did problem two。

 and then we have this stack of true false questions。I think， you know。

 I'm going to repeat the suggestion that I made from midterm one and midterm two。

 but just start always with the questions where we think we can make the most progress and if we find at any point that we're getting stuck。

tThen write a few words down and move on to a different question and come back so I'll try to emulate that strategy here I'm just going to go ahead and start with question number one and see how far we can get before we run into run into difficulty。

So for each of the problems below， I need to check the yes box if the statement is always true under all circumstances and no otherwise。

And give a brief explanation。I should assume that P is not equal to NPp because that's what we assume normally anyway。

 even though we don't know whether it's true or not。And any other ambiguity of any kind。

 any uncertainty， the answer is no。Okay， the solution to the recurrence8 T of n over two plus n squared is t of n is big of n squared。

 so I'll you know sketch out。The first part of。The recursion tree。

 so the root I'll have n squared and then I'll have eight children in each of those children。

 I'll have n over sorry。Not an。And over two squared。And then in each of the grandchildren， again。

 each of these will have eight children， each those will have n over four squared。

So running across this way， I'll have eight times n squared over four， which is2 n squared。

ThisThe zero level clearly sums to n squared， the first level sums to two n squared。

And the next level is 64 times n squared over 16。Which is 4 n squared。

So I have an increasing geometric series。All， so increasing。Geometric series。And。

The number of leaves。Is。Well， I've got an eight airy tree and the depth of the tree is log based2 of n。

This is the same as n log base two of eight， which is NC。So that's not end's work。嗯。

And then the next one， I flipped the two and the eight。

 so for the next one I have n squared and I've got two children each with n over eight squared and I've got two grandchildren each with。

And over8 squared squared。 So now this is going to add up to n squared。Two times ns cleared over 64。

Four times n squared over。64 squared， but at this point I can probably guess。

It's going to be something that decays really fast so again here now the answer is yes because I have a decreasing。

Gemetric series。And the root is n squared。Every directed acyclic graph contains at least one sink。嗯。

Well， remember， a sink is a vertex that Hannahs no outgoing edges， only incoming edges。嗯。So。

Let's imagine that I have a graph that doesn't have an eync okay。

 so then I can start at a vertex and that vertex must have outgoing edges so I can follow those outgoing edges to another vertex and I can follow an outgoing edge to another vertex and I can follow an outgoing edge to another vertex and I can do that forever because there's always an outgoing edge that I can follow out of the current vertex。

So I can walk around this graph as much as I like， but if I walk long enough。

 I'm going to see a vertex that I've seen before。But then I had a cycle。Right so。Acyclt。Means a walk。

UMust。And。At a sink。So if I just plot myself down anywhere in the graph and I start walking。

 eventually I must reach because I can't repeat vertices。

I must reach a vertex where I can't make any further progress。And that's sink， so yes。

Given any underched graph， we can compute a spanning tree in linear time using whatever for search。嗯。

Notice that any is italicized。So I need to be careful here and it turns out in this case。

 the answer is no。So for example， this graph。If I run whatever first search， starting my vertex。

I'll say if I start here， whatever first search might create a spanning tree of V one component containing the startertex。

But it won't actually compute spanning through the whole graph。

You can't have a spanning tree of the whole graph because trees are connected。

 spanning trees are connected and acyclic and touch over the graph。So if a graph has a spanning tree。

 it must be connected and this graph isn't so only。Connected。Gs。Um。

Then there's something that looks like a dynamic programming recurrence。

And it's asking about you know memorization order and so on。

 so let's see i've got a two dimensional dynamic programming。AT here。

And if I look at a particular value of I and a particular value of J。

Let's I'm indexing it in the usual way。What of I common J depends on。What I J minus1。

 what I minus1 J and what i plus 1 J plus1？Which are。In the same row， but an earlier column。

In the same column， but an earlier row。And in the next row and the next column。Okay。

 and then the question is， can I do this by increasing I in the outer loop？

And increasing J in the inner loop， say this is the standard row major traversal。

 and the answer is no。Because this order considers what Ij before it considers what I+ 1 J plus1。

And the way dynamic programming is supposed to work is every recursive call is supposed to be replaced by a table lookup。

 so if I've evaluated this in the correct order， then I visit what I+1 J plus1 before I need to fill in what IJ。

And so here the answer is no， the order doesn't work， but in fact。

 there is no order that works the dependency graph。嗯。Has cycles。

So no order works and the way you can see this is okay， in order to fill in one square。

 first I need to fill in the square above it。So I've got dependency thing that way。

 but then before I do that I have to fill in the square below and to the right。

 but before I do that I have to fill in the square to the left。So I've got cycles all over the place。

 so what I J。Calls。What？I minus1 J， which calls。What？嗯。What is it？I J plus1， which calls。What？I J。

And so I have an infinite loop in my recurrence， so it's not only that this particular evaluation doesn't work。

But no evaluation order works at all， and so this is not a dynamic programming recurrence。

 probably I want to do something else to figure out this problem。than what I'm trying to do here。

Or B。Wwhichhich of the following statements are true for at least one language L。

 so the nice thing about this that when the statement is true。

 I really only have to give one example language where it's true。So if I start with this first one。

 L star equals L star star。This is， it's enough to say， for example。

 one star equals one star star or the empty language star。

 this is the same as the empty language and so it's the same as the empty language stard。Sttored。嗯。

So this is yes。E is decidable， but L star is undecidable。So remember what L star is。

L star is a instead of all strings that are made by concatenating one or more zero or more。

 excuse me， zero or more strings from L。But L is decable。

 so there is an algorithm which can tell me in a finite amount of time。

 definitively 100% of the time。Whether or not a given string is an L。

And so asking is a string in L star， if you say is W in L star， this is equivalent to asking。

Can W be。broken。Into。Strings。In no。But that is precisely the text segmentation problem that we saw back at the very beginning of looking at dynamic programming。

Okay， so the answer is if there is an algorithm to decide L， which we might for example。

 call is word。Then there is an algorithm that can decide whether a string can be broken into a sequence of strings in L or what we might call words。

So the answer is no。Because of the text segmentation。Alrithm。Right。

Assuming we've got a finite algorithm that decides membership in L。

 we can apply dynamic programming to get an algorithm to test membership in L starA。

L is neither regular nor NP hard。Okay。Let's think about whenever we you're seeing an example like this。

 we should think about the simplest possible thing that might work。

 so what is the simplest language we know that where L is not regular that's zero to the n1 to the n for all n greater and equal to zero。

But if this language is not going to be NP hard because I can write down a polynomial time algorithm to decide whether a string has this form。

I read the first so many characters until I read a one。

So I count how many zeros there are at the beginning of the given string。

And then I count ones following that first run of zeros to make sure that they're exactly the same number of ones as I counted zeros。

And then I checked whether the string is done。Okay， but。So this can be decided。Were recognized。

In in linear time using， you know， just a simple。Counter up， counterdown kind of thing。

And because we're assuming that p is not equal to NPp。Um， you know， if this， if this were NP hard。

 then it would be equal to NP and so we're assuming that can happen， so no。Or sorry。是。The answer is。

 yes， this language L is neither regular nor NPR。嗯。On the the exam， actually you would only。

Let me say this way on the exam， you would not have to write this stuff in。嗯。In red。

You just need to write， here's the example language。L is in P and L has an infinite fulling set。Well。

 remember， infinite fooleps the same as not regular。So。U，Yeah， we we just did this。

 this is zero to the n1 to the n where n is greater than equal to zero again。

exactlyly the same argument as the previous line， I can recognize strings that have this form in linear time with a simple algorithm。

 but it's not regular and therefore it has an infinite folding。

The language of Tring machine encodings such that MX L is undecidable， yes。

And any number of things that one could write here。One of those is racist theorem。

Because this is whether this language is decidable or not is a question about what language Tring machines accept。

And I can imagine。U for any decable language， there's going to be a Tring machine that accepts it and another Tring machine that accepts something else。

But I mean， an intuitive explanation is you know， problems。About。Tururing machines。Oh。know。

 this is a non interview problem about turing machiness。It's's probably undecidable。嗯。

So writing this second thing。This would probably be worth you know half point。

 it's a reasonable intuition that， oh， you're asking me some weird question about tuuring machine。

 is this probably impossible。And let me say that's at least half for that next one issue。Okay。

Consider the following pair of languages remember language is really the same thing as a decision problem right a language is a set of strings。

 a decision problem asks is this string in that set yes or no？

So directed to Hamiltonian Pa is the set of all directed graphs that contain a Hamiltonian path。

Or equivalently， it the decision problem here， given a director graph。

 does it have a Hamiltonian path？And acyclic is a similar problem， given a directed graph。

 is it acyclic or does it have a cycle？系。U and just to be concrete。

 I'm going to imagine that these things are represented by adjacency matrices。We're not going to。

None of these questions ask about specific running times so that that's just to nail things down in case you're wondering what I mean when I talk about a graph as if it were a string。

So what the adjacency matrix is a big block of zeros and ones I can just write it down as a string of zeros and ones and because its size is a perfect square。

 there's no ambiguity about them。Rows and columns， how many rows and how many columns there are？Okay。

 so acyclic is in NP， that means if this is true， what that means is given a graph that is acyclic。

 I can prove to you that it is acyclic and polynomial time。And the answer is yes。

 I can prove to you the graph is acyclic， in fact， that's NP P by depth research。

There is a polynomial time algorithm that decides yes or no， whether a graph is acyclic。

 and so this language of graphs is in P。AndP is a subset of NPp。Yeah。

Second question acyclic intersect directed Hamiltonian path is in P so what this is asking is given。

A graphra。G。Is it a dag？With。A Hamiltonian path。Can this question be decided in polynomial time and the answer is yes。

 it can be decided in polynomial time， so DFS to find cycles。

foollllowed by the length of the longest path algorithm， once I know that it's a Dg。

 then I can find the longest path using dynamic programming。If it's not a dag。

 then I just project it as soon as I find a suck。Directed Hamiltonian Pa is decciable now we do know that this problem is NP hard。

And this was one of the canonical NP hard questions that's listed on the very back of the answer booklet。

But that only tells me how difficult the problem is， is there a way to actually decide。

 given a directed graph， does it contain a Hamiltonian path， not in polynomial time。

 but that's not what it's asking， it's just is there any algorithm at all。And the answer is yes。

 try all permutations。Of the vertices。For each permutation。

 is that an ordering of the vertices where along some path in the graph。Now。

 this isn't something that you can write， if I say please describe an algorithm because this isn't enough information for a 225 student to actually implement the algorithm。

But in in terms of like arguing， yeah， the algorithm exists， it's like， yeah。

 I'm willing to believe that you can。Finding all permutations by taking all possibilities for the first vertex and then all possibilities except the first vertex for the second vertex and so forth just by you know。

Building a big， huge recursive backtracking thing。Next。

 a polynomial time reduction from one of these problems to the other would imply that P equals NP。

Okay， now remember， we know that acyclic is in P， we know that that problem is easy。

So a polynomial time reduction from directed Hamiltonian path to a cyclic。

What that would mean is I'll draw the usual cartoon。So this is。Um。Directed Hamiltonian path。

To acyclic。So a graph comes in and then I transform it into another graph。And I get， you know， yes。

 no。Right。If acyclic can be solved in polynomial time， right？In fact， it can， this black box。

 I actually know how to do this in polynomial time。

Then and polynomial time reduction means also that this part runs in polynomial time。

I've just described a polynomial time algorithm for directed Hamiltonian Pa。

Directed Hamiltonian Pa is NPR， it's on the list of things that are NPR on the back。

 so the answer is yes。On the other hand， a polynomial time reduction from acyclic to directed Hamiltonian path because acyclic is in P。

A erect in the other direction wouldn't tell me anything right so I've taken a problem that I already know is in P and I've described an algorithm to solve it using this horrible exponential thing for directed Hamiltonian BaF。

That tells me there's a slow algorithm for acyclic。

Well I already know there's a fast out for acycl quick so this isn't actually giving me any information at all right so no wrong way。

YouYou're doing the reduction in the wrong direction。Right。

You know what is bad is if I have a reduction from a harder problem to an easy problem that would imply that hard and easier are the same。

 but if I have a reduction from an easy problem to a harder problem。

That just means I have a stupid algorithm for the easy problem。Finally， part D。Again。

 this is more about polynomial time reductions， suppose there's a reduction from some language A to some other language B。

 both over the same alphabet 01。Which of the following statements are always true。

 assuming p is minus equal to NP？The first one is A is a subset of B。

And this is something that I see a mistake that I've seen a lot of students make。

 that somehow a reduction requires some sort of subset relationship。

 but if you think about like the reductions that we've seen。

 especially the more complicated reductions that we've seen where we'd say we go from three set to independent set or we go from vertex cover to Hamiltonian path。

 graphs that have large vertex coverss don't actually look at all like graphs that have Hamiltonian paths。

3 CNF formulas that are satisfiable don't look anything at all like graphs that have large independent sets or graphs that have that can be three colored so right off the bat if we really you know think back to those examples like no this is not the same kind of thing but an even easier example is zero star and one star I can reduce is the problem here's a binary string does it only contain zeros。

To the problem， here's a binary string does it only contain ones？

And the transformation is replace every zero with a one and replace every one with a zero。

That's a polynomial time reduction from a language A to a language B。

 but these are not subsets of each other at all。嗯。If B is in P， then a is in P。 Well， again。

 remember what this is， This is a reduction。 I'll draw the the usual cartoon again from a。To B。

 so there's some reduction algorithm going on in here。It transforms the input and then are languages。

 I'm saying yes or no。So if B is in P then then that means this magic box runs in polynomial time and because it's a polynomial time reduction。

 the input transformation also runs in polynomial time。

 so I've described a polynomial time algorithm for。哎。So this is by definition of。Pollen of your time。

Reduction。Next， if B is NP hard， then a is NP hard now if I were doing a reduction like this。

U this is the shape of a reduction that argues， I already know that A is NP hard and I'm trying to prove that B is NP hard。

So here the answer is going to be no， and the reduction is just going the wrong direction。

To make that argument。On the other hand， if I said， if A is NP hard， then B is NP hard。

 that would be true again by the definition of polynomial time reduction and NP hard。If B is regular。

 then a is regular。Colynomial time algorithms can do all sorts of crazy stuff。So I you know。

 they don't have to look like DFA transformations I mean yes， okay。

 that black box in the middle for B might actually be a DFA， but。I offhand。

 I don't see any reason why the reduction should， you know， the outer problem needs to be regular。um。

sortrt of。Curious now yeah， okay， so let's take a to B the usual non regular language。And。

The reduction。Now remember what a reduction is， a reduction from A to B is an algorithm to solve a using an algorithm for B as a submar team。

That just， but it means I can call that subine as many times as I like。Including zero times。

So this language， remember， can recognizeognizable in polynomial time。

 so just an algorithm to solve a， recognized strings in A in polynomial time is a polynomial time reduction from A to every other language。

Tervily vacuously so。Right。But if you're not comfortable with that， you could say something like。

 okay， I can still reduce a to to。I think I could。Yeah。

 maybe I'm trying to think if I can reduce it to like one star or something。

I'd have to think about that a little bit more。嗯。Yeah， I think I see a way to do it。

 but it's too complicated to think about during an exam。

 just just a polynomial time algorithm is sort of a is always a trivial polynomial time reduction to whatever other problem you like？

And then finally， if B is regular， then a is decidable， here the answer is yes。By this one。

 so regular。Implies P， which implies decidable。Regular implies P because a DFA is an algorithm that runs in linear time at the polynomial and because I have an algorithm。

 a DFA also implies that I definitively get an answer one way or the other in a finite amount of time and that answer is correct。

 so that's deable， but audits just being in P means I have a polynomial time algorithm that definitively gives me the answer so the problem's deable。

And that's it for the us no questions。All right， so we have three more questions that we need to deal with。

There's something about a grid and climbing in the mountains， we've done the MP hardness stuff。

There's something about。Strings。Instead that it。DFA NFA。Oh。

 this is the one that's climbing in the mountains， oh， and there's the domino question。

So let's see if we can do the domino question。This is maybe a bit more algorithmy。

 so closer to stuff that we've been doing more recently。

 I want to refer back just to remind everybody what the problem looks like is I'm given a two by n array of integers。

 which some of which are positive， some of which are negative， some of which are zero。

And I want to tie it with two by one rectangles， which could be like these red horizontal rectangles or could be like these blue vertical rectangles。

And the idea is that I'm going to sum up all of the numbers that are covered by blue dominoes that are vertical。

 and then I'm going to subtract all of the points that are covered by horizontal red dominoes。

 and that will be the score， the value for particular domino tiling。

And here's three examples of what a domino time can look like。

 we're looking to maximize the value so we want the domino timeling on the far right。嗯。So a dominoes。

 dominoes， dominoes。嗯。So what I'm going to imagine doing。It's going to start by saying， okay。

 I've got some。Two by in thing。😔，There's a couple of possibilities for how this dominotyling can start if I start building this thing on the left and I work my way to the right。

So， I mean， one possibility is that I can add a positive domino like this。

The other is that I can add a negative domino like that。

Those are the two possibilities for covering the upper left corner。But in the second case， now。

 the only thing that fits in the lower left corner is another horizontal dominant。

And so these are the two options that I have for what to do at the leftmost edge of the grid。

 I either put down one vertical domino or I put down a pair of horizontal dominoes。

And now I in each case， I have a smaller suffix of the two by n array that I need to cover。

 so my sub problems。Our。Suffixes。嗯。I mean， there are suffixes of this two by an array。

 but think of them as a subset of the columns that are all jammed over to the right okay。

 so I'm going to let。Max Val of I。Be the maximum。Value。Of a domino。Twiling。Of。Columns。Ae。Through。And。

This is。My English description。And as usual I want to point out a couple of things about this English description。

 one is that I've chosen a name that is somewhat reminiscent of the thing that it represents the second is that I have named parameters here and the name parameters show up on the right hand side in a way that shows how the value on the right on the right side of the equal sign depends on the parameters on the left side of equal sign the third thing is there's nothing in this statement that refers to an algorithm。

I I can now take that that rectangled box and I can hand it to somebody else and even though they may not know immediately how to compute it。

 they will agree that I know that yes， this seems to have a well defined value。

I'm not referring to the current domino or anything along those lines。

 is just everything is spelled out in terms of the parameters of the function。All right。

 so now I need to write down a。嗯。A recurrence。And sort of as usual。

 this recurrence is going to have multiple cases， but as usual I'm going to recommend looking at the more difficult case first。

 the most general case， which is the one that's kind of shown here at the top of the screen。

It's going to be the max of two options。One is that I have a positive domino covering the column I。

So this is going to be points i1 plus points。I too。Plus。The maximum value for columns i+1 through n。

And the second possibility is that I need to put down two negative dominoes covering the first two columns。

 so this is going to be minus points I1 minus points。I two minus points。

I plus 11 minus points of i plus12， so there's the first column and both of the both squares in the first column and both squares in the second column get subtracted。

And then I recursively look at Max Val I plus2。So this is the most general case。

Where this breaks down is if I is equal to n。Then I only have one column。

And so the only thing I can do is put down。Of a vertical domino。

And if bigger than if I is bigger than N， then I've actually eaten up the entire board。

 I'm looking at a board that now has zero columns left。

 so I put a zero here so those are my my three cases。Right。

So I have a one dimensional array index by I I need we need。To compute。Max vow of one， that's the。

Maximum value of the domino tiling of columns1 through n。

So every particular value of max v sub I depends on max Val of i plus one and max v of I plus2。

 so we can evaluate that。In decreasing order of I， so memorize。In1 D array。Evaluate。Right to left。Or。

Decreasing eye。And the running time is linear。Because I have n entries in the table to fill in and for each one I do a constant amount of of a input array lookups and。

Memoware hookups。ok。嗯。I should point out。This is also this also can。Be done。The longest。Haath。

In a directed acyclic graph。Um， because it's a dynamic programming problem and almost every dynamic programming column can be turned into finding the longest path or of some kind of optimal path of the dag。

I won't go through the details of this particular alternate solution for the problem because in practice very few people actually do it this way。

 but if you were thinking along hey， maybe I should think of it as a DAg question。

 yes you can actually do that， the idea is that I would have one vertex for each column and I would have an edge going from column I to column I+1 with this value and I would have an edge going from column I to column I+2 with this value and now the max gets captured by looking for the longest path。

He。So。We only have two left。There's a different question that looks like it involves graph。

 or there's a question that looks like it involves DFAs and whatnot。

I want to take a break from algorithms for a bit clear my head do some of the stuff that we used to do in midterm one。

 so let's think about。This problem here。Every zero is followed immediately by at least one one。

So in terms of regular expressions， it looks like I can just I'm looking for something like pattern that's repeating over and over again or some way of splitting the string into pieces。

And what it kind of looks like is， well， whenever I see a zero。

That has to be followed by at least one， but possibly more than one one。

And I can do that as many times as I like。Um， and well。

 the only thing I'm missing here is maybe at the beginning of the string。

 I can have as many ones as I want。So is one possibility for regular expression for this。

I alternate between runs of ones and individual zeros so I have an optional run of ones at the beginning and then after that I alternate I have a zero and it must be followed by a nonemp run of ones and then I have a zero and it must be followed by an unemp run of ones and it must zero and it must be followed by an unemp run of ones so foreverv and ever。

Another possibility for this is I can repeatedly write down either one or zero one。

So whenever I write down a zero， I immediately write down a one。So that's the second option。

 the first option is or I could just write down a one。

And do this over and over as many times as I like and that is immediately captured by completely captures the language that I'm interested in so similarly if I have here's my start state if I read so the empty string has the property that is followed immediately by one so it can let the empty string the start state must be must be accepting。

And then if I read a1， then I'm back in the start state， if I read a zero， I go to the other state。

And then read a1， I immediately go back。And from this intermediate state， if I read a zero。

 then I'm in the stone state。Bei。Now， I could have also stopped after just the first two states。

I could actually do this， and I could say okay， all missing。Transitions。Go to junk。

stateate or trash at state or reject state or to hell any of those work fine。

 but I think in this case it's actually simpler just to say if I ever see two zeros in a row just go ahead and that put that。

嗯。But the third stayed in there。Both of these are fun， just in this case。

 I think it's simple enough just to do it explicitly。

That's it we're done you know the question sheet does say you don't have to prove these are correct and more generally I don't see the word prove or justify anything in part A so we just have to write down the correct answer move on。

So let LB be the set of all strings whose run length are increasing。

 that is every run except the last one is followed immediately by a longer run。Now。

 I want to prove that this is not a regular language。So yeah。

 I'm going to use a fooling set argument。嗯。But the thing about falling set arguments。

More generally like the thing where you want to prove anything is NP hard is it's sufficient to think about special cases。

 I don't need to think in my fulling sub argument about arbitrary strings where the run length are increasing and there might be any number of runs。

It's okay to think about small numbers of runs。One run is a bit too simple so strings that only have one run in them that's either zero star or one star that's regular what I really want to think about is is just strings with two runs so consider only strings。

In LB with exactly two runs。All right， so my following set that I'm going to use。

Is going to represent the first run that's shorter and I'm just going to decide that's going to be runs of zeros and remember runs have to be nonemp so that's why I'm letting F be zero zero star this or or if you prefer zero plus this is all non empty strings of zeros。

Right。Okay， so I'm going to define F to the screen。Now consider。Any two。Strings。X， Y in F。

Then we must have x is equal to zero to the I and y is equal to zero to the J。

For sum I not equal to J。I picked two distinct strings。I is the length of xj is the length of y。

Without loss of generality。Assume。That I is less than J。Otherwise， swap。Excellent wine。First。Okay。

 so this is another point of confusion that comes up a lot。

 like what does this without loss of generality mean？

What I'm really saying here is there are two cases to consider either I is less than J or I is bigger than J and now I'm going to write down the argument for I is less than J。

And then say， well， the argument for I is bigger than J is symmetric。

 I just swap the roles of x and Y everywhere。So I'm writing by what without loss of generality is kind of an indicator that there's symmetry between the case where this assumption holds and the case where this assumption doesn't hold。

And so I'm only going to write down one of those two cases。You can't do this with things like。

Let's assume that I andJ， without loss of gene I andJ are both even。

Because that's not symmetric with maybe I is even and J is odd， maybe I is odd and J is even。

 maybe both of them are odd there's actually several other cases。

I can't say suppose J is bigger than 2i。Because I can't just swap to get to the case where j is less than equal to 2 money。

So you do really have to be careful about this and so to be on the safe side。

Let me write it exactly the same thing， but I'm going to say suppose。嗯。Excuse me。

Suppose I is less than J。And then write the argument。For I is bigger than J is。symmetricsymmetric。嗯。

On。By swapbbping。X and Y。Okay， that really maybe makes it a bit more explicit for we really wanted to make it even more explicit say there are two cases bullet。

 suppose I is less than J bullet， suppose J is bigger than I is bigger than J。

And then I'd write down oh it's the same as the first argument as the first case by swapamp。

All right。So then I need to define。What Z is Z is this distinguishing suffix I want to make sure that when I add Z onto these two strings for one of them I get a longer run of ones than zeros and the other one I don't。

So I'm going to let this be one to the J。Okay。Then。X z is0 to the I1 to the J。

 which is an Lb because。I is less than J。喂。That's this argument that I made here。Right right？And。

Yz is zero to the J1 to the J， which is not in Lb because。J is not bigger than J。

 this is not a run of zeros followed by a longer run of ones。

 this is a run of zeros followed by our equal length run of ones。And at this point， I would say， oh。

 so F is a fooling set and because F is infinite， LB isn't regular。

 but this is actually enough fund I need to see the rest of the boil plate。So。

We're left with only one question。So let's see what we can do with that。

We're given the height map of a mountain in the form of an end by end grid。

 so I'll just draw a thing to remind me here。This is what my height map might look like。

N equals five each of these points is labeled with an elevation value from at any point I can on this grid。

 I can safely hike directly north， south， east or west to any of the four neighboring grid points。

Provided the elevations of those two points differ by utmost delta。So for example。

 if I have Delta is five and。My elevations are， let's say this is elevation  three， seven。For one。

And 12。I'm not allowed to hike directly from three to the point with elevation  three to the point with elevation 12 because that difference9 is too big。

Likewise， if this were three to negative seven， wouldn't be able to hike down that either because the difference between three and negative seven is 10 and 10 is bigger than five。

Describe and analyze an algorithm determine the longest hike， okay， so again。

 reminding there's probably a dag here somewhere。From some point S to some other point T。

 where the height consists of an uphill climb where the elevations must increase。

 followed by a downhill climb where the elevations must decrease。

Your input consists of an array of elevation values。嗯。

There's a of actually a bit of an ambiguity here， what is the link？

How is length actually defined and when this problem was asked in the real final。

 we clarified that you know only X and Y distance。So plus one for each。嗯。Stop。

They're going from one grid to an adjacent。Grid cell， that has distance one。

They're all evenly spaced and you don't take deelta into accounts。

 no pythagorean theorem stuff about you know three dimensional lengths in in real honest to God。

 elevation maps these dots are typically。In the past。

 they were usually about five meters apart and maybe Delta would be on the order of a couple of meters typically。

So usually you want to hike。If you're actually doing a hike and not a climb。

 your elevation is not going to change so quickly that this makes a great deal of difference。

 but just to clarify what we mean by the length of a hike is you draw out some sort of path in the grid for how you travel around and it's the length of that path in the grid。

Okay。Now， I can kind of see。If we were only going uphill。Why we would have a D？Okay。

 so if we're only going uphill， then we just direct all of the edges。

Only uphill and only if the edge is going uphill by at least zero， but at most Dlta。Right。Now。

 because all edges are going uphill， there's no opportunity for cycles， every path。

 the elevation is monotontically increasing。And I can also kind of see like in phase two。

 I'm only looking at edges that go downhill， so again， only the downhill edges define a dag。

But I don't want to put these edges on top of the same set of vertices。

So what I'm going to do instead。Is I'm going to define a dag。G equals V E。Where I'm going to have。

Two copies of the grid。One that carries edges that only go up and the other that carries edges that only go down okay。

 so V is going to VV up union V down。And really what I want to think of this as。

Is the set from one to n times the set from one to n。Times the pair either up or down。So。

I'm going to have for every grid cell。For every row I and column J。

 I'm going to have a vertex Ij up and I'm going to have a vertex Ij down。Similarly。

 I'm going to have edges。They're going to be up edges。And I'm going to have down edges。

 but I'm also going to have edges where I'm at the top and I decide， okay。

 this is where I turn around is where。I switch from the up copies of vertices to the down parts of vertices。

So E up is going to be the set。I J2， I plus or minus1 J。Such that。The elevation of IJ。

Minus the elevation of i plus or minus1 J。Is less than or equal to delta。Let's see。

 I need to be a little bit careful about this guys。That's not what I wanted to say。I want。😔。

The elevation。From i plus or minus1 J needs to be bigger than the elevation。Via Jay。

s from going uphill。But it also needs to be less。Then the elevation from Ij plus deelta。

That's horizontal edges， and similarly now I need vertical edges。嗯。So elevation。

Ij plus or minus1 is greater than elevation。Of I， J。And at most elevation of Ij plus deelta。Okay。嗯。

E down is similar。So I'm not going to cheat by glassing this and duplicating it。Again。

 i J2 i plus or minus1 J。Where the elevation from i plus or minus1。

I most want is less than the elevation at Ij， but greater than the elevation at Ij minus delta。Union。

Again， I need this four vertical edges。I J plus or minus1 where。

The elevation at Ij plus minus1 is less than the elevation at Ij。

 but greater than the elevation at Ij minus delta。And finally， the tops here。Oh。

 and I should say these are all IJ up。U。Up。Down。Down。Down。Down。And it's point right over here。Jy up。

2。i。Plus or minus1 J up。Just to clarify。And so here I'm going to have edges going from Ij up。

To I J down。This is， I guess， an argument for bringing a pencil。

So I'm going to erase this to make it clearer。If you are going to be using a pencil。

 let me strongly recommend that you use at least a number two pencil。Um。

 if u you are not going to be using a pencil， either need to write， you know。

 more carefully than I'm writing。Or you should invest。In erasable pens。Okay。

 I think that's a little bit better。嗯。So there really are actually very nice erasable pens out there now。

 I don't know whether you can actually buy them at Argo or Walgreens but you can certainly get them at Staples or something like that and therefore you can order them off Amazon。

Okay， so this is going to be one step。Up and this is going to be one step。

Down and the last is the transition。From。啊。To down。Whi is required here。

 it says must consist of an uphill climb followed by a downhill climb。Great。Actually。

 notice it actually says increase and decrease， so I think then just to be on the safe side。

 I'm going to make these inequalities strict， it really has to go strictly up and then strictly down。

Okay。嗯。But now you'll notice that we've got edges that are not。

 there's not an exact correspondence between paths in this graph and and distances and hikes。

 so if I have a hike that consists of three steps going uphill followed by four steps going downhill。

That gives me a walk first that uses three edges in E up and then uses one edge transitioning from up to down and then uses four edges hiking down so in order to really make this work。

I need to say， you know， edges。In E up and E down have weight。1。And。Edges。In。E cap have。Wait。Zero。

And now with these weights， I have。Uphill。Downhill。Hikes。From。S to T。

Or you know one1 correspondence walks。In G。From。The up version of s to the down version of T。

So I'm going to follow some upward edges。Until I get to the single edge going from the part of the graph to the down part of the graph followed by a bunch of downward digits。

 that's the only way paths can work。I need to argue that this graph is a。

 but i'm running out of space so what i'm going to say at this point is。呃。

C page seven nice big bold friendly letters so that we can go on from there， okay。

 so page seven G is a dag。Because。Every。Let's see every。Walk。嗯。Goes uphill。Through。Edges any up。

So there's no way for there to be a cycle among the uphill things。Then， across。One edge。In。Over。

 so there's no way to get a cycle that because now that's going over to downward part。And then then。

Downhill。Through。That just in eat down。Okay， so the longest。Again。

 every uphill downhill like from us to T。With length。Al corresponds to。a walk in G and therefore。

 because it's a dag， every walk is a path。嗯。That has exactly the same length。Okay。

So that means we defined the longest path MG， which is a dag， so we can find。You know， we。

And compute。The longest path。In G。From。As up to。T down。Using the length and along this path。

 dynamicyn programming algorithm them。That we saw in class。This runs in order V plus E time。

But how many vertices are in the graph？Well， there's n by n by two。

 so there's two n squared vertices。And every vertex has at most four outgoing edges， the up edges。

 there's four going up， there's maybe four going down and there's maybe one going across so for every vertex。

Each of its four outgoing edges and sort of the underlying grid graph。

Can show up either once as an upward edge or it can show up once as a downward edge。

And then in addition for every vertex， there's another edge from one column to another。

 so altogether the number of edges and vertices is big O of n squared。And now， believe it or not。

 we are done。哦。I need to do one last sanity check。In particular。

 I need to make sure that my name is on the front page。

 otherwise I'm not going to get credit for anything。And I need to make sure my name is at least。

On a couple of these。Name boxes at the beginning， but I would also you know。

 if especially if there's time recommend using this time that we're spending writing names to actually read through each of these answers and make sure that they actually say what we want so。

I'm not going to actually do that live here in the video。

 but if I were actually doing this in an exam。It looks like the hour that we spent in lecture today following the hour and 15 minutes that I've been talking on this video。

 that still leaves me plenty of time to actually look through each of these each of these answers to make sure that it actually says exactly what I want it to say that I haven't skipped over any details that I haven't left out things that I remember might be on the rubric that you know my。

 I say less than when I mean less than， I say less than or equal to and I mean less than or equal to just to make sure that everything is as unambiguous as possible。

嗯。So this business with the graph in particular there a lot of details here。

 but I need to make sure that that this actually says what I want。

 but I'm reasonably comfortable right now that it does。This is not particularly formal， by the way。

 this business using plus or minus ones the in the indices。Arguably this is a bit ambiguous。

 but for an exam， I think this is clear enough in context。嗯。And while we did the reductions。

And there's the dynamic programming problem， it turned out to be fairly easy。

Here's the DFA Infin strings problem， not terribly difficult if you remember things about how DFAs work。

 but have this problem does have the feature that it does require two ideas。

 one is understanding how to express this DFA in accepts an infinite number of languages。

An infinite number of strings， excuse me， as a property of the underlying graph， and then secondly。

 how do I detect that property of graphs？嗯。So if when you're seeing a problem like this that looks like it requires a couple of steps。

 it's probably worthwhile when you attack the problem to write down。

 here are the two major steps and really think of it as this is part A of the problem and that is part B of the problem。

And then we've got all these yes no questions again。

 I would want to double check to make sure that I haven't mistakenly checked the wrong box or left one of the explanations blank。

But as I said， I think everything is in pretty good shape。

So after doing a final sanity check and make sure that everything is in order and then I go up and I turn in the exam and I go home and don't think about this class again at all for at least a couple of weeks。

I do recognize that a lot of people are going to be looking at the grade and final exam and are going to be。

 you know， kind of worried about how things are going to go worried about their final grade。

 but please for your own sanity， I really do recommend when you leave the exam。

Don't think about it for at least a week。That's it for this video thanks for listening we'll see you in a couple of days in the second video all right。

Bye。

![](img/8208d567c77fa57e75a8db08595b94cb_2.png)