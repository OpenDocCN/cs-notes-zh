# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p16 20231012-Oct 12_ Tree-shaped dynamic programming.zh_en -BV1Mh7RzaEL2_p16-

![](img/111f56e72a515827c206b229aa78ab5d_0.png)

Yeah好像大家。So。

![](img/111f56e72a515827c206b229aa78ab5d_2.png)

。要。不。はい。500多。Yeah。好。没有。Yeah。Yeah。はは。这么。我我。一个明白。我的好的。他就是他。我。系系啊讲起。That would。这。



![](img/111f56e72a515827c206b229aa78ab5d_4.png)

。

![](img/111f56e72a515827c206b229aa78ab5d_6.png)

よろしく願いまはい。系。

![](img/111f56e72a515827c206b229aa78ab5d_8.png)

Yeah。Number number。

![](img/111f56e72a515827c206b229aa78ab5d_10.png)

Okay， let's go ahead and get started。U。哦我。中文。Okay， so。As I'm sure most of you already know。

 midterm grades are out on grade scope。U。This is a distribution of the grades。

 so let me explain what this chart is。So for every student who took the regular exam。

I plotted the exam score in blue， that's the blue scale over on the left。

And I computed an estimate of your overall course average based on the work that you submitted homework and great guided problem sets before midterm one。

 so homeworks one through four， guided problem sets one through five， not dropping anything。

 not taking any late work into account， so if you submitted it just assuming you got an extension if it was late。

So it's a bit of a crude estimate。But I took that estimated course average。

 sorted the students in decreasing order， so there's one person over there who has a 98% course average。

 there's one person down here who has a 41% course average。

And then plotted the exam averages in the corresponding horizontal position。嗯。

So one of the weird things that this means is you can actually see。

For a given range of course averages， what roughly what the range of homework scores is and in particular you can see variances up and down so if the blue point is high above the orange curve。

That means your homework average is relatively low， it brought homework your overall average down。

Points， blue points that are below the orange curve。

 those are people who have relatively high homework and grade scope averages。诶。The median。

Homework plus grade scope average for the course right now was 92%。So I did。

Add some estimates down here on the web page about you know。

 assuming you have a 92% overall what the rough correspondence is between exam scores and letter grades。

 but the way I plotted it here is I just took the grade grading policy that's advertised on the website。

And split people up into ABC， et cetera， based on overall compute average。

So you can kind of get a sense。Based on where your exam scores are。

What letter grade you're looking at？Adjusting a little bit up and down based on whether your homework scores are high or low now I'll notice here there are a few people who have particularly high spikes over the orange curve。

Those are people whose groupmates did not identify them on gradecope。

 please tell them to identify you on gradecope， now send them email。

 pull out your laptops check that me see if that's you。

 please check this yourself if we get to the end of the semester we can't guarantee that we'll be able to fix things。

😡，Both。嗯。This also doesn't take into account any of the outstanding regrade requests for homework and obviously it doesn't take into account any of the outstanding requests for the midterm that have happened in the last three hours。

Um， it also doesn't。Include。People who took the conflict exam。

The scores for the conflict exam were slightly lower mostly because of one particular question。

 that means I will need to make some adjustments to the conflict exam the language transformation questions on the conflict were noticeably more difficult than the language transformation questions in the regular exam。

 all of the other scores were consistent so the difference in scores is not because of the difference between the students。

So I'll have to do some adjustments to the scores at the end of the semester when when I compute the final grades。

 the difference is on the order of like two exam points。嗯。嗯。Another thing to point out here。

We did the exam grading in in parallel， so every。啊。Parts。Part A。

 part B of the two part questions were graded by different TAs and the multiple choice questions were just distributed among everybody。

So for the part A， part B questions。The different TAs who graded them。

In some cases they have interpreted the rubric slightly differently。

 so there may be inconsistencies between how your part A was graded and how your part B was graded。

 there's really nothing we can do about that， it's more important that everybody's part A was graded consistently and that everybody's part B wasd consistently。

 but if they're like really gross differences。If the same small mistake was toed one point off here and four and a half points off there。

 please feel free to submit re requests。Um。UThe the dates。

On the homework the rig requestquest is incorrect。Regrade requests will be further the deadline for submitting re requests will be further in the future。

嗯。The last thing I want to say is。You may know that the drop deadline is。Good our afternoon or sorry。

 tomorrow evening， 1159 pm。If you're concerned about your exam performance and your thinking about whether or not to drop。

 please come talk to me， I will be in my office。Time did I nail down 10 to 12 and one to four。

Exclusively for talking about talking to students who are concerned about their grades and and or are thinking about dropping the class。

 so this is going to take the place of my regular Friday office hours hopefully this will be able to handle you know everybody who needs to get there I may actually set up like a sign up sheet so we can like allocate 20 minutes lots depending on how many people think they need to go。

But。I I want to point out that the only people that I'm at all concerned about passing the class。

 I have already sent email。So if you haven't received email。

 I'm not worried about you passing the class and the only people that like got really in any even moderate moderate danger of failing are the ones who were down in this last set over here was maybe a dozen people。

ok。Um。The other the other thing to remember about this， this is a crude estimate。

 so things can go up and down and it's only based on about 30% of the coursework that you submitted in the class and it doesn't have all the bells and whistles about dropping lowest scores and extensions and all that stuff。

It's relatively common for people's grades to change by a full letter grade between midterm one and the end of the course。

 it's not that uncommon for people's letter grades to change by two letter grades between midterm one and the end of the course either up or down。

😡，So if you are。Over at the right end and concerned we I may be able to help figure out some way of changing how you're approaching the coursework。

 we may be able to do some adjustments to your study habits or who you're working with or something like that to bring you up if you're over here at the left end and you say ah I've got this。

 I don't need to pay attention to the class anymore。You can still drop down。

Does anybody have any questions about this？I won't bother to tell you the statistics because this class is not graded on a curve。

But I will say that the overall exam average was higher than the last three times I taught the course。

So。I don't think it was a particularly easy exam。So that's good news。

 I think people are in general the classes seems to be doing relatively well。So。Questions。No。

All right。So let's go back to talking about。Dennament programming。So at the end of class on Tuesday。

 except for the speed run I did in the last negative one minute。

We were talking about this edit distance problem。😡，And。Remember edit distance is。

Minimum number of insertions， deletions or replacements。To change one string。A sub1 through M。

Into another string B sub from one through n。And after working now some way of visualizing what a sequence of editing operations might look like。

And thinking about how do you figure out what's the last column in this representation and now what do I need to remember to deal with the remaining prefixes。

 we eventually ended up with this recurrence。😡，Where in English。Edit of IJ is the edit distance。

The number the minimum possible number of。Insertions， deletions and。Replacements。

From the prefix of the first I characters of A and the prefix containing the first J characters of B。

Okay the bulk of the recurrence， the main general recursive case has three subcases。

 maybe the last editing operation I do is an insertion。

 maybe the last editing operation I do is a deletion。

 maybe the last editing operation I do is a replacement and if it's a replacement maybe I actually have to pay for that replacement because the characters are different or maybe I don't have to pay for that replacement because the characters are the same if I have to do an insertion or deletion。

 I'm definitely doing one operation， which is what those plus ones are。😡。

But at this point in the process of developing the dynamic programming algorithm。

 we actually don't need to know。Anymore。What this recurrence？Um， actually。

Means we needed to know this English description so that we could develop the recurrence。😡。

We needed to know what problem we were solving so we could write down a solution。

But now that we've written down a recursive solution。

 we can take the English part and toss it out and just look at the formula。

And figure out a way of memormalizing it。Evaluate and evaluating efficiently for all the values that we actually care about。

嗯。So。U。I and J are indices into the two strings。So I is going to have。Arrange from。

 I don't say zero up to M。And。J is going to have a range。From zero up to n。

Zero in both of those cases corresponds to the empty prefix， we have to take that into account。

And the answer that we're looking for in the end。Is down here。Edit of MN。

Okay that's our final answer。Okay， so we need to memorize this function into a two dimensional array because we've got two parameters to the function。

If we had a function that had three parameters， we would memorize it most likely into a three dimensional array。

 if we had a function that had seven parameters。Yes。

 we would memorize it into a seven dimensional array， and I wouldn't be drawing pictures。Um。啊。Okay。

So that's the structure。Now， the next question we have to ask is。

 what order can we fill this array so that whenever we write a value into the array。

 all of the other entries that depends on were written earlier。

So let's start with just looking at a particular value of I and J and ask。What？

What entries does Ed Ij depend on？Well。嗯。Here。Is one thing that it depends on。Edited of I J Ons one。

 so it's the same row， but it's in an earlier column， so I'll mark that in black。

And then the second case inside that min is Ed of I minus1 j， that's the same column J。

 but it's the previous row。So I'll mark that in black。And finally。

 it might also depend on edit I minus1， J minus1。😡。

So that's the previous row and the previous column。So I'll mark that in black。And so I need a way of。

Traversing this array。So that all of three of those black squares are filled in before the white square。

 and that's true no matter which white square I start with， I mean I just picked a row in a column。

 but that same three black squares of above and to the left， the white square happens。

 no matter which white square I pick。😡，So what order should I fill the arrayt？No。

So I need to go within each row， I need to go from left to right。

So that when I in the row that contains the white square， I get the black square to the left first。

And within each column， I need to go top down so in the column containing the white square。

 I get the black square above it first。And I can decide which way to nest those four loops。

 it doesn't particularly matter， so I'm going to do standard row major order。

 which is in the inner loop。😡，Actually， let me。Let me draw these in a different color to sort of emphasize what's going on here。

In the inner loop。I'm going to consider the rows from left to right， in other words。

 increasing the column index J。And in the outer loop。

I'm going to consider the rows in increasing index order， so by increasing I。

So I could write this as for I goes from zero to M for J goes from zero to n， and then I compute。

Edit。Of IJ。Yes， question in front。有有。大都识。That's correct。

 so the notation I'm using here as a mnemonic is the double arrow means the outer loop。

And the single arrows mean the interval loop。I could this is not the only order I could have used。

 I could have swapped the inner and outer loop， so I could have done it in standard column major order where I go from left to right in the outer loop and I go down the columns in the inner loop。

😡，That just involves swapping the two four lines。Well let's go ahead and do it like this。

And now one of the things as a Sandy you check to notice here is what。

Where are the base cases in this array？Well， there's one base case up here at0 zero， that's correct。

But I mean， if you look at the recurrence。Where are the base cases in the array？Yeah， so the entire。

Row zero and entire column zero， those are our base cases。

 those are the things we want to compute first。And on the other hand。

 the thing that we want to compute last。Is down here in the bottom right。

 so as a you know as sanity check， the arrows should be pointing from the base cases towards the final answer。

 the final answer is the last thing that we should be learning。😡，Now。

I don't know if you remember from Tuesday how we got to this recurrence but。As a sort of reminder。

 you did something like the following and say， okay， I don't know。

So there was a decision we were making decisions。From left to right or sorry， from right to left。

Right， so I was。Imagining。First， deciding what goes in the last column of this？

Two by whatever it is table and then what goes in the second to last column。

 what goes in the third to last column and so on。So I said。

 I don't know what's going to go in this column immediately to the left of that line。

So the stuff in red， this is the past。Stuff over in blue this is。The future。

I don't know whether the first column that I need to do next is the one that currently contains a blank and an S。

 whether blank S is really the answer or whether it should be I blank or whether it should be I。😡。

But so I'm going to try all three possibilities and then ask about things further to the left so we are intuitively。

 we're making decisions。Going from right to left。😡，But in the final algorithm。

The answers are revealed to us。In order from left to right， by increasing order of index。

But if we think a little bit about what's actually going on， this will make sense。

 so what you're doing when you're moving from left from right to left。

 from past to future is you were asking， what do I do next。

 let me try something and then ask the recursion fairy。I check the possibility。

 I temporarily decide this is what I'm going to be doing， and then I make a recursive call。

And then I make more recursive calls， and I make more recursive calls。

 then I make more recursive calls， but an actual value only starts being computed when the recursive call is done。

And so the values appear as the recursive calls pop off the recursion stack。

Which is in the opposite order， what you're seeing up there at the top of the screen is the order that you're pushing things onto the recursion stack。

The order that you're using to fill in a table is the order that values pop off the recursion stack。

 so of course they're going to be backwards from each other。😡，So at first glance。

 is kind of counterintuitive thing， if I want in the end my for loops to go forward。

I should formulate things intuitively as though I'm making decisions from the end walking backwards。

Or equivalently recursing on prefixes。If I thinking about making my decisions going forward。

 so I'm rehearsing on suffixes， in the end， my dynamic programming algorithm is going to have loops that run in decreasing order。

Neither of these is wrong these are both fine， it's just that you know in the end some people are a little tiny epsilon more comfortable。

When their four loops go forward， then when they go backwards。So that's why at the very beginning。

 when I started this process， I said， I don't know what the hell。

 let's start at the right end instead of the left end this time。

 because I knew that when I did that I would end up with four loops that go in increasing order instead of decreasing order。

 yes。It's possible， yes。You tried them both and one of them works。So the question was。

 are you ever going to see problems where you can only make decisions from left to right and recur on suffixes？

And not， you can recurse from right to left and recurse on prefixes。

And there's actually a problem in the guided problem sets that shows you that at least if you try to do it the same way。

 going forwards and backwards， it doesn't work。So the follow up question was how do I know which way to do it。

 and the answer is you tried them both and see which one works。Yes one faced with three alternatives。

 you try all three and see which one works I don't recommend。

Only focusing on one until you reach failure， but rather you know work on one for 15 minutes and if it doesn't need to be working out。

 switch to the other one， work on it for 15 minutes or in an exam two minutes。Right。

This is also not necessarily the only way of formulating this recurrence。

 so even within the realm of deciding between prefixes and suffixes。

 there may be multiple different ways to formulate the recurrence。

 some of which might lead to one dimensional table。

 some of which might lead to two dimensional table。😡。

some of which might lead to a one dimensional table。

 but where you need n squared time to fill in any single entry， so it's actually in cube time。

 which is slower than when you use a two dimensional table。Right so it really。

There's a lot of flexibility， not in this particular problem。

 but in other problems like the ones's done the homework。

 about how exactly to formulate the recurrence， each of which gives you slightly different。

 but still correct algorithms。Yeah。Its making the。At这。I。诶そ呢。Inside of the decide by long。

So you' I'm not sure I'm understanding the question。

 so literally what I'm doing here is this is row zero。In every row。

 I start by filling in column zero and then I fill in the other columns in increasing order。

That's all I'm doing so I mean if you put this in here it would be redundant you do it filling in the same entry multiple times。

 but it's still for I equals one to m for j equals1 to n。Constant amount of stuff。

So in terms of analysis。This whole mess。Is just。Constant time。You knowS lines of code。

 there are no function calls。So the overall running time here is going to be M times n0。U。

Any other questions about this particular dynamic programming example yeah？我这个。The second。

 iss that a second M？No sorryrry， that should be an end。MN。嗯。This is my handwriting。

I've got an M by N table and each entry takes constant time to fill in。系。Okay。

 so the last thing I want to mention here is that it is possible。To make this slightly faster。

So you can shave off a log factor that's in practice only really going to be reasonable if you're editing DNA and so your strings are millions of characters long can you actually can you do you know something that's actually really be faster than this nobody knows。

So in particular， when n and M are equal， the question is this this algorithm works in n squared time and I can shave a little bit of log off。

 but can I solve this problem in end to the 1。999 time？Or less。Nobody knows。On the other hand。

But it's。But probably not。嗯。And what I mean by probably not is if you could show me an algorithm that runs in n to the 1。

999 time， then I could show you an algorithm that solves the Boolean at liabilityability problem in something like 1。

999 to the end time instead of two the end time， so it would violate an assumption that stricter than p does not equal NP。

 but it's in the same flavor。😡，So there are these conditional results that say， well， yeah。

 if you could really improve that to the end of the 1。5 memory9s。

 then some other complexity theoretic assumption would be violated。

And we don't believe that can happen， or we would think at least it would be very。

 very interesting if that happened。嗯。That last proof was done in， I believe。Like 2013。

So no probably not probably can't do any better oh yeah。

 here's here's the actual table that's computed by the algorithm for the two example strings。

 algorithms and altruistic。😡，Just the numbers， the only thing that the algorithm action computes is the numbers。

😡，And in particular， this number down here in the lower right corner six。

 that indicates that the edit distance between algorithm and altruistic is six。

 there are six editing operations that can turn one string into the other。😡，Now。

 there was a question last time about how would I figure out what those editing operations are？

And that's what the arrows are supposed to indicate， but just before I talk about recovery。

 let's actually look at you know a particular cell in this grid and ask where did that three come from？

😡，ok。So if I look at the recurrence， it says， what's the minimum of three things。

 the one above the one below， the one to the left and the one up and the diagonal？

Each with a plus one assuming those two characters are different， so if I look here。

The two characters you and R are different。😡，So that three is the minimum of。

Two plus one and two plus one and three plus one。The arrows there are showing me which of those three choices lead to the minimum value。

 so this two plus one is three， this two plus one is three。

 this three plus one is too big because there's no arrow going to the right。😡。

And that information can be recovered on the fly in constant time just by pointing at that yellow spot and looking at my neighbors。

So in particular， what I can do is start。sarchching from down here at the bottom at six and go well how did I get that six well it came from this five I could figure that out in constant time that came from this four that came from this four。

 the bold red arrows， those are the bold red numbers。

 those are the cases where the two characters actually match and it turns out in that case that the diagonal is always the right choice。

 six plus zero it was six in this case。😡，It's not necessarily uniquely the right choice。

 I could have also given five plus one to six。But it's always a right choice。

And I can sort of continue following these arrows backwards。And。Find a path all the way back。

To the top left corner of the Hu。Every time I move diagonally。That's a replacement。

Every time I move up。That's an。I think that's an insertion。And every time I move to the left。

That's a deletion。And so this particular pattern， I believe， corresponds to this。

2 by N Tableau for those two strings。If you look at the arrows carefully。

 you'll notice that there's more than one path of arrows leading from the top left to the bottom right。

 that means that there is more than one sequence of editing operations。

That has six six actual important operations in it。

 Those are the three that are listed at the bottom of the screen each of those pattern things at the bottom of the screen correspond to one of those paths。

 so for example， this one in blue corresponds to。This path。So they share the insert S operation。

But here， instead of doing delete， replace free insert。I'm doing replace， replace， replace free。嗯。

And the other one。Right， that's。This。Path。可。😊，So this is what I mean when I said on Tuesday。

Difficult part of computing the optimal structure is computing the cost of the optimal structure。

 the number of editing operations。Once you have all the data in the minimalization table。

 you can then backtrack to reconstruct the actual structure or structures。

Just by spending essentially at every cell that you visit on this path going back to the beginning。

 you revisit the possibilities for computing that value using the recurrence。

 and that tells you what previous values it came from。So as a matter of course policy。

 unless we specifically say otherwise whenever we ask you for。

Give me the best schedule for loading the ferry， what I actually want is give me the cost of the best schedule for loading the ferry。

 give me the optimal binary search tree for this set of frequencies。

 now what I actually want is give me the total cost of the optimal binary search tree for this set of frequencies whatever you know give me the best giraffe。

 know what I want is the height of the best giraffe。😡。

And then you can construct the giraffe after the fact if you want from the memorization structure。

Okay。😊，Last questions about edit distance before go on to the next example。Okay， cool。

 so let's suppose you just got a dog。You want to build the dog house。And so you buy。

Some lovely planks of wood and you work out exactly where to cut these planks of wood to put them together so that like the grain of the wood will fit nicely and this nice。

 you know， this end piece will match up with that side piece and it'll look really cool so you plant it exactly where to cut the boards。

😡，You've got this one board here that you want to cut into four pieces。But。

You don't have a place a way to cut the board it's too long to fit in your workshop。

 you have to go down to your friends who has a wood shop and say， hey。

 will you cut this board for me into these smaller pieces？😡，Who says， well， yeah。

 but this is a business， I have to make some money and I can't do it for free。

 but I'll cut any board you like。For a cost that's equal to the length of the board。

So if you give me a 10 foot board and you want me to cut it into any two pieces you want。

 I'm going to charge you $10。If you give me a 30 foot board， I'll cut it anywhere you want。

 but I'm going to charge you $30 to give me $150 foot board， I cut it anywhere you want。

 but it's going to cost $150。So you say， oh great， I've got this 10 foot board。

I've got marks at two feet from the left end， three feet from the left end and six feet from the left end or said differently I've got these these pieces mapped out of length two feet one feet。

 three feet and four feet what what I need to think oh wait how much。Where should I ask him to cut？

Different ways of cutting the board into these pieces are going to lead to different total amounts of money。

 so if I look here on the left。This is what happens if I tell my friend。Cut from left to right。

Start at the first cut and the second cut and the third cut so the first cut because the board has length 10 cost me 10 now I cut off the two feet piece that i'm done。

 but then cutting the piece on the right again because that's  eight feet long that costs me 8。

I cut off a one foot piece and then the last cut because that last remaining board cost has length seven feet。

 it cost me 7 and so altogether I need to spend $25。To cut the boards in order from left to right。

I so， well， that seems a bit expensive， let me try a different order so if I go from right to left。

say well that that actually seems better because the first cut still going to be $10。

 but I'll cut off a bigger chunk and so my later cuts will be cheaper and so now instead of。😡。

Cutting costing $25。I cut the first piece for 10 and then I cut the left side of that for six。

 and I cut the left side of that for three， total is $19。

But then I think I don't have to cut the boards in order from left to right to right to left。

 I can cut anywhere I want。And then。You can kind of smell where this is going to go once I've cut my board into two smaller boards。

 I could recursively cut those boards， so I could start by cutting in the middle。Again。

 that cost be10。And then cut the left side for $3 and cut the right side for $7 that turn has a total cost of 20 so in this particular case。

The minimum cost I can get away with。For decomposing this board。Is $19。Okay。

 there are two other schedules that I have not written up here they're both more expensive than this。

Anyone want to tell me what those two schedules are？What cases have I not put on the screen？

So after I cut on the leftmost cuts。The next cut after that could have been the one on the right end。

Instead of the one on the left end， so I could cut。Here first， that'll cost me 10。

 and then I'll cut here。That'll cost me eight， and then I'll cut here in the middle。

 that'll cost me four， so that would be $22。So one， two， three。Or for this one。

 if if I start by cutting farthest to the right， the second cut could be all the way to the left。

That would still cost me six。And then I could cut this board again， this last cut would cost me four。

 so this is 20。嗯。So。Yeah， questions。有我。嗯。the question is。

 will the best cut be the one that lands closest to the middle of the board your thinking？

This is not supposed to be a class about thinking， this is supposed to be a class about algorithms。

No， this will not always work。In this example， you got lucky and these good have said， oh。

 I should make the first cut closest to the five foot mark， that means cutting at the six foot mark。

Not cutting at the three foot or the two foot mark， but again， that's really kind of a coincidence。

In particular， if the board。Looks like。This。I might not want to cut at this mark even though it's pretty close to the middle。

Another greedy heuristic you might think is， oh， I should cut at the median mark so at the same number of marks on both sides。

 but already in this example you can see that doesn't work because if I cut in the middle mark。

I'm going to get a cost of 20。Where there's another schedule that gives me cost of 19。Right so。

Intuition that many， many people have is let's try to figure out where the best place to make the first cut is。

That's not the right approach。The right approach is， I don't know where the first cut is。

 let's try all the possibilities。And let the recursion fairy do everything else。Okay， so。

Just use brute force， so this will make sense in a minute， but I need to move that down for a second。

So the idea is now。I'm going to。I'm making a sequence of decisions I'm going to cut somewhere and now I've got two recursive subproblem now this is one thing that's different about this problem than the previous problems we've been looking at where you have a sequence and you're making decisions either at the beginning of the sequence of the end of the sequence and recursing on either the remaining suffix or the remaining prefix here I'm making a decision about cutting the board somewhere。

😡，And I get two independent recursive subprobles。Okay， so let's follow the one on the left。

So let's ignore this part for that the other recursion fair is going to take care of that。

and now within this left recursive subproblem again。

 i'm deciding where is the best place to cut this left board and now I have two more。

Independent recursive subproblems， let's sort of ignore the one on the left。

And what we see here is sort of the shape of our generic subproblem。Instead of prefixes or suffixes。

The input to a generic recursive subproblem is some interval。Some contiguous subset of the boards。😡。

USo。Which I can describe by saying this is say the I cut and that's the Jath cut。

And so I'm interested in the cost， the minimum cost of cutting up an interval。

 a chunk of the board that starts at the the I cut from the left and ends at the j cut from the left。

So that's going to be the kind of thing that I'm looking for。

And for reasons that are going to become clear later， I actually prefer to call this right index K。

So let me actually tell you what precisely I'm assuming about the input to the problem。Okay。

 so what I imagine is I'm given。An array。Let's call it L from one through n where。

L of I is the length。Of the I。Board。From the left。So in this example， L is the array 2，1，3，4。Okay。😊。

What I'm defining here is you know。Men cut cost。Of IJ actually。

Since I'll be consistent with the notation I used。When I was writing this up， let's call it opt cost。

 this is the minimum possible。Cost。Of。Cutting。Plank。Consisting。



![](img/111f56e72a515827c206b229aa78ab5d_12.png)

Of。Boards。系y。だったら。

![](img/111f56e72a515827c206b229aa78ab5d_14.png)

I through J minus1。Oh， sorry。Again。Okay， I through k minus1。So。Board one。Has cut oh no， sorry。

 that should be i minus1 through k， sorry。Board。😡，Okay， so if this is cut one。This is board two。

so cut eye is at the right end of board eye。Right so。More generally here。U。

This is going to be board I+1， and this is going to be board K。So of course。

 I wrote minus there for some stupid reason。RightAnd what we want。Is。Ot cost。Z n。All right。I think。

I've got all the off by one errors out of my system， i've got my indexing correct。

 I've got a nice simple relatively straightforward English description of the problem， I think。

 but to be sure does anybody have，Any questions about this formulation， yes？或还有一个什么。Okay。

 so'm going to let let me fix some nomenclature here。

 the long thing that I'm cutting up into pieces is a plank。The pieces themselves。

 I'm going to call boards。Maybe I should call the pieces pieces。Would that be？

can make suggestions about what I should call the long thing and what I should call the things I'm cutting it into。

Well。Yeah， okay， let me。Long plank into short boards。Yeah， okay so。

The plank gets really long because I have to walk out on and off the ship and jump into the water。

If I'm being held captive by pirates。No one ever walked the board。Um， okay。

Does that make a little bit more sense， yeah， question vector？Yeah。

I'm not sure I understand the question。I said， here are three ways I could cut up the plank into boards。

The one on the left。I cut at the first mark and then I cut it the second mark and then I cut it the third mark。

That costs me $25。The one in the middle， I start the rightmost mark and then I cut in the middle mark and then cut on the left mark that cost me 19。

The one on the right， I start by cutting the second mark， then I back up and cut the first。

 and then I go forward and cut the third。That cost me $20。Well。

 cutting a 10 foot board cost me $10 so on the right the first cut cost me $10 because the board is 10 feet long two plus one plus6 or four is 10。

The the second cut on the right cost me$3 because I'm cutting in a three foot board。

 two plus one is three。And so on。Yes。Sorry， could you yell because the acoustics in the room are really bad？

Okay， so I need to make two， I'm indexing two slightly different things。😡，Okay， so this is cut one。

 cut two and cut three。But this is board one， board two， board three and board four。😡。

So if I'm going between， say。Put one in three。That's from board two to board three。

 so if I going from I to K， that's i plus1 to k。😡，That's right。

 so the indices I'm using in this case， for whatever random reason I decided to index by the position of the cut rather than the position of the board。

嗯。There's actually good reasons for that， which I'll get to at the end。So。Sorry。

 I need to make some room here。And sort of getting ahead of myself on these slides。Okay。So。

There's a nice English description。How do we actually develop a recurrence for it？Well。As always。

 I sort of recommend。嗯。Starting with the most general case。I is， I don't know。

 50 and k is I don't know， 175 and the n is 5 million。

 so you no boundary effects or anything like that。Um u。

We need to figure out two parts of the cost of decomposing that playing。

One is what is the cost of taking the first cut， this is not going to differ depending on where that first cut is。

If I bring in a 25 foot board， it's going to cost me 25 no matter where I decide to cut it。

So the first thing I need to do is figure out。How long？

Is this plank consisting of board's i+1 through cat？well， that's easy。

J is from i plus 1 through k of L sub J。That is the total length of the board the plank that I'm considering in this recursive subproblem。

😡，系。Programmers in the room。How do you pronounce this symbol？F loop。

Mathematicians pronounce it sigma， that's nice， that's a for loop。

UBut the next thing I need to do is say， oh， I need to pick a place to cut the first time and then decompose things into recursive subprom。

So if I decide to。Cut at position J。What I'm going to end up with is the sub problemsble up cost of I。

呃。I'm going to cheat。J minus1。And opt cost。Of JK。I think I've got the off by one errors， right？Um。

 but I have no idea what J is the only thing I know。Is。I could。I could cut off just one board。

And that would involve。Actually。Let me make sure I've got this right here， so here's here's cut eye。

Here's cut k so this is board i plus one here's cut i plus one。

 here's board K here's cut k minus one so my my range of possible values。

For J are between i plus1 and k minus1。Okay，And I want the minimum over all those choices。

I less than equal less than J less than k of this if I cut at position J。

 this will be board J plus1 on the left， this will be board J on the right。But。Actually。

 i'm going between cut indices here， so this is。Between。Put I and。Cut J or sorry， cut K。Yeah。

 so I think I end up with something that looks like this。

You'll notice this is just sort of the way the world works。

I I sort of went with an arbitrary choice of let me refer to the the indices that I pass in that's the position of one of the cuts not the index of one of the boards and have to make sure that my。

I'm consistent all the way through， but I didn't necessarily have to make that choice。

 I could have used as indices as say the first and last board in the plank。

And then I would get a slightly different recurrence there。系。Um， but there's。

 there's also base cases。In this case， the base case is if。I sorry is k minus i equals one。

 then there's only one board。Between those two cuts， I'm looking at two adjacent cuts。

 which means I've already got one of the short boards in my hand I don't need to cut it anymore。Yeah。

就上个是没去。Okay， so。Let me move this stuff。Out of the way。So this part is the cost of the first。Cut。

It'sThe total length。Of the plank that I'm cutting up。And。This is the position of the first cut。

And this is the cost of the remaining。That's。有。And so L ofJ is the length of the JF board。

So I need to sum up the links of these small pieces to get the total cost of the first cut。Again。

 is this my choice of input representation was the links of the boards。😡，啊啊。

So I think the way I formulated it in the notes， I got something slightly different because I think I was indexing by boards instead of cuts。

 so let's stick with the one that we've got here。对。

So one thing to notice before we even think about doing the memorization is if we actually wanted to implement this as a recursive algorithm。

When I call up cost of IK， that algorithm consists of two four loops。😡。

The first one is a summation of the board lengths to get the cost of the first cut。

The second is a for loop over all possible positions of the first cut。

 and then inside that for loop in each iteration I make two recursive calls。Okay。

 so I've got some non trivial amount of work to do。Even ignoring the recursion。

In order to make this whole thing work out。诶。So if everybody clear on on on。

How this recurrence works。Yes。Well， okay， so so the right way to think about this is。嗯。

I've got this board that started at cut I and ends at the plank that starts at board cut I and ends at cut K。

 but it's got lots of other cut marks on it。So there were roughly came on his eye different places where I could put the first cut。

I don't know which of those k minus I first cuts is the best one。So I try every one of them。

Called my choice of first cut J that ranges strictly between I and J。

And for each possible choice J of where I put my first cut， I now have two smaller planks。

 which I'm going to recursively decompose optimally。Yeah。Is a question up front？我嗰日唔俾得咩乜，但系。

those of JThat's right so I I and K are already given the scope of I and K is outside that notation indicates I'm trying all all all integer values of I that are greater than sorry all integer values of J that're greater than I and less than K。

The number of recursive calls is variable that is correct。

 the number of recursive calls depends on the difference between K and I。

If K and I are very far apart， lots of recursive calls， if K and I are very close together。

 not that many recursive calls。Yeah好。啊我。反。阿lo have晚 time。

If you really want to understand the running time of this recursive algorithm， read the book。

I'm not going to talk about that。There is a way to do it。

 not particularly interesting because it is going to end up being something like three to the end。

So I don't want to think about it because I want to aim for an efficient algorithm。So。

I go get a drink of water。 you know， do a Sudoku， u eat a burrito。

 you moved to a different coffee shop。呃。Order my oat milk， macho latte。

And sit down and look at this recurrence and go， oh， what do I want to memorize this into？

What sort of data structure might I memorize this recurrence into？How many dimensions？

How many parameters does the function have？Two， so how many dimensions？Two。

 so I'm going to have an array。Indexed by I and K。喂。😊。

And now I have to think a bit about what order to fill in。The array。So that things appear in the。

 you know， anything like that。If i'm filling in a particular value。

 all the other things that that value depends on get filled in first， so let's。

So'll be a little bit more interesting if I can pick K that's further that way and pick I that's further that way。

So here is a particular value of IK。All right。So。That。

Entry up cost of IK depends not just on one or two things。

 but on a large number of things and how large that is depends on the distance between I andK。

But I can look at the two different cases， one is。Where did the dependencies that come from this recursive call show up in the array？

Well， they're in the same。Re， I。But they're in a different column J。

That's less than the column K that I'm aiming at。So in other words。

These things are all going to come from further to the left。😡。

And this is actually going to go all the way back。To roughly the main diagonal of the array。

All this doesn't really make any this function really doesn't make any sense if k is less than I。

 so the bottom half of the array is just sort of nonsense。Um， if I like， I could throw in， you know。

 infinity if k minus I is non positive。As as a sanity check。But if I'm careful， I don't need it。

And then similarly， where does？The stuff corresponding the entries corresponding to this recursive call come from。

Well， I'm in the same column K。But I'm in a different row J that is larger than the row I that I'm targeting with that white square。

 so these entries all show up。😡，In directly below。Okay。

 so I need to traverse this two dimensional array in some order。

So that all of the green squares and all of the blue squares are visited before that white square。

What should I do？Start the bottom of that and then so by row。So start in the bottom left。

Go row by row。Either way， so of course。都 right。Okay。

 so that the is that the inner loop for the outer loop inner loop goes to the right light？

How goes up。Of course， I could also do that in the other direction and I could do， you know。

 the inner loop goes up and the outer loop goes the right。

 I could also do that in yet another direction， I could go diagonal by diagonal。嗯。

So there are no dependencies along any diagonal in the array。

 so I can visit those in any order I'd like。But I need to proceed a long diagnosis starting near the middle of the array and working my way up to this square。

Which is opt cost of。Zero n， this is my output， this is the answer that I want。

 the squares along the main diagonal， those are my base cases， those are the things I know first。

No matter how I do this， I'm going to get two nested four loops。

So yeah I had the same things here so i'm just go ahead and delete this this one for example would be4 j goes from n to0 or sorry for k goes from n to zero4 I goes from0 to n and then i'll compute。

Opt。😡，Cost。Of I now this line here takes order end time。Because I'm considering inside that。

This is actually4 J goes from Ii plus1 to k minus1 that's roughly order n。All right。

 so then I'm considering。C。You know， down inside that。UAnd in fact， I've got two four loops in there。

 one for the summation and one for the men。So the overall running time of this algorithm。

Is going to be N cubed。Last things I'll say about this。嗯。

It's possible with a little bit more cleverness。Using this evaluation pattern to reduce the running time to n squared。

And it is even possible for this particular problem， but usually not in general， this is a very。

 very special case。There is actually an algorithm that solves this specific dynamic programming problem in N log N time。

If you take 473， I might talk about this， this you'll have to read the paper yourself。

 these are not features of general sort of quote unquote tree shape dynamic programming problems it just just I want to point out that the NC thing is as usual the start of the story not the end。

😡，But this then cubed is what I would expect you to guys staying for。

I'm happy to answer any other questions the front or out of time， see you， some of you tomorrow。

 rest of you next week。

![](img/111f56e72a515827c206b229aa78ab5d_16.png)

好了嗯好对。