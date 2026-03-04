# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p07 P7 7._Speeding_up_dynamic_programming_(HD_1080_-_WEB_(H264_4000)) -BV1RdBTBrEdx_p7-

我没。

![](img/14f3defac8ffc0e5e9a788859c4b3b1e_1.png)

你。😊，All right， let's。Let's go ahead and get started。Thanks everybody again for coming。嗯。😊。

So a couple of quick administrative things。U。Homework one is due tonight。

Homework two is up on the website， it's doing week or sorry， homework two is doing tonight night。

 homework three is up on the website doing week。Homework zero has been graded。

 you can look at your grades on grade scope。We're really hoping to cut down。

 you know now that people are starting to submit homeworking groups that we should be able to speed up the grading so。

Hope。Once a week， I'll be able to say one more homework's been released。

And by the time we get through the midterm， we might even be caught up。U。

So homework 3 is the last homework。Before the midterm， which is two weeks from yesterday。

Watch on the website and watch on Ed for。Location information。

 I don't know whether we're going to be all in one room or spread out among several rooms that depends on what facilities gives us。

嗯。Oh。Quick clarification because。啊。A couple of people have asked。

Just now before class and in office hours。Whenever you have a dynamic programming algorithm that asks the problem that asks you to define some kind of optimal structure。

😡，For example。Give me the assignment of books to shelves that minimizes the total height of the shelves。

😡，Or。Give me a clustering of these data items into k intervals such that the maximum error is minimized。

 and the output should be the break points and the values for each of the intervals。

It is enough for full credit just to describe an algorithm that computes the cost of the optimal structure。

😡，So for problem three， you only need to return the total height of the best way of shelving。😡。

For problem two， you only need to return the error of the best possible clustering。

 you not actually need to construct the structure because as we talked about on Thursday。

 the hard part of finding the optimal structure is finding the cost of the optimal structure。

 backtracking through the memmalization table to compute the actual structure is mechanical and fine that that's not the interesting part of the problem so that's not where I want you to spend your time。

😡，Right， so。It's。Enough。For full credit。To。Compute。The cost。

Or weight or value or duration or whatever the word is。😡，For the。

Value that you're trying to minimize or maximize。 so you do not capture actually have to tell me。😡。

Your algorithm does not actually need to explicitly output the break points and the values for problem two。

 does not explicitly need to output how many books are on each shelf for problem three。

And that's true for every dynamic programming problem。In in the entire class。嗯。呃。So。

Home here has been graded， everything's up on gradecope。

 and in particular if you go to GrScope and look at your graded work。

 there's a button there that says regrade request。I encourage you。2。You take advantage of that。

But just a couple of things about regrade requests。😡。

The reason for requesting a regrade is you got a score that's inconsistent with the grading rubric。😡。

Not。I think I need more points。So we ask when you submit a regrade request always you need to write a short explanation of。

😡，What went wrong on our end for grading， so。My algorithm works and you count it completely wrong。

 that's fine。😡，嗯。My algorithm doesn't work， but you gave me full credit， that's also fine。😡。

And in particular。If you successfully argue that you should have received fewer points。😡。

You will get back that difference positive points， so if we gave you an eight and we should have given you a two and you convince us that we gave you an eight when we should have given you a two。

 then you won't get an  eight you'll get a 14。😡，对对。So sanity check the grading。

 if we have been too generous with you， we owe you points is our job and when we're grading these things is just to give you honest informative feedback。

😡，If we haven't done that， then。😡，You deserve some reward for pointing that out。Okay。

This is also a clever dodge to do two things， one to keep the graders on their toes。😡。

Because they're the first people who are going to have to look at this and go， oh God， I screwed up。

😡，嗯。😊，And the other is for you to treat the published solutions and the grading feedback and so on skeptically。

😡，Like you would accept like you would look at everything skeptically。

 don't just assume that things are true because I said they were true。😡。

Make sure convince yourself that the things that we say actually make sense because I'm human。

 I make mistakes， the Ts are human， they make mistakes， the CAs are human， they make mistakes。

 you're human， you make mistakes。😡，Best to get in the habit of just。😡，Going well。

 let me make sure about everything。That goes for exam questions as well。😡。

so when we grade the midterms， we grade you more generously than we said we would。

On the published rubrics。Then。bonusus points。系。So。Oh。Generally。

 we'll give you a two week window when we release homework grades when you can submit re requests。

 that's the window to submit the initial request。Sometimes these things require require multiple rounds to resolve if that goes up against the two equal barrier。

 don't worry about it。For exams， that'll be three weeks。

But then the regrade request button will just sort of automatically close on grade scope and at that point it's too late so we want you to look at things。

Early， quickly， partly because。The graders are also going to forget what they did after a short amount of time yeah。

The midterm will cover everything that homeworks zero，1， two， and three cover。😡，In particular。

 the midterm will not cover what I'm talking about today because you haven't done homework on it。😡，嗯。

Any other？Administrative issues。Okay。So。We've been talking about dynamic programming for a while now everybody's sick of it。

😡，Except me， but I want to talk about one。😡，Cool algorithm。

That can be used to speed up a wide class of dynamic programming algorithms by roughly a factor of n。

😡，So， the。Now I'm going to describe。😡，The component algorithm。😡。

And show you that this problem that looks like it should take n squared time for this one component algorithm。

 you can actually solve in linear time。😡，I'm not going to have time to walk through the mechanics of applying that algorithm to。

😡，An actual dynamic programming problem， you can look at those some of those examples in the notes。

But I do want to give you an example where this technique pays off。😡。

And that is the woodcutterss problem。That I talked about。U。啊。A couple of weeks ago。So you remember。

 the problem is that I've got a long plank of wood that's been cut or that's been marked in several places。

And I want to cut this into the individual boards。😡。

I can take my plank to the mill and get one cut in time proportional to the length of the board that I'm cutting。

😡，So then the question is how what's the optimal schedule for the cuts right so in principle I should probably cut somewhere in the middle。

😡，And then I've got these two smaller boards。Which then I need to recursively cut up。

So I'm essentially building this binary tree。😡，Of ways to cut。

The cost to cut that board no matter where I cut it is the length。😡。

And then the cost to cut those smaller pieces into their component boards is defined recursively。So。

In the end， you get a recurrence。😡，That has the following form。Okay， so。Length of IK。

 that's the distance between the Ithe mark and the caF mark on the board。😡，Min cost of IK。

 that's the minimum cost of decomposing the portion of the board that starts at the Ith mark。😡。

And ends the at the CaF mark。And the recurrence says for all possible positions of the first cut within that range。

 and I'll call that position J， so I'm not going to start at the I'm not going to cut at the E mark because that's the end of the board。

 I'm not going to cut at the Ca mark because that's the other end of the board。

 but for any mark in between。😡，I pay for the length， and then I recursively pay。

 did hecompose the part on the left and recursively pay did hecompose the part on the right？Okay。

Now this length is basically。😡，Almost provided in the input。😡。

You can think of this as the position of the ca mark minus the position of the Ih mark。

If you're given this array X。That shows where each of the cuts are in sorted order from left to right。

嗯。And。Okay， this。Naturally memorizes into a two dimensional array indexed by I and K。

You're only really looking at the upper half of that array， but that's not a problem。And then。

To fill out one entry in this table。At row I column K， I may need to look at。😡。

Cells in the same row I， but in earlier columns。😡，So I need to look at all of this stuff first。😡。

And the second recursive column in the same column， but later rows。

 so I need to look at all of that stuff first。So to fill in that empty square。

 I have to look in the part that's been shaded solid。😡，And so my。1。W you might think of。

Evaluating this is let's start on the main diagonal， fill that in， that's the base case。

 then the diagonal above that， then the diagonal above that and so on up to the upper right corner。

Essentially， what you're doing is looking at。All intervals containing only one board。

 then all intervals containing two boards， then all intervals containing three boards and so on until you look at the entire plank that you're starting with。

系。No。嗯。This gives you naturally。An algorithm that runs in N cube time。But it turns out。

That by making some structural observations about。Aray that you're manipulating。

And by applying the algorithm I'm about to show you。😡，This running time reduces to end cubed。

Sorry to end squared。So you lose a factor again。Right。

Now the end cubed running time is basically well， morally what I have is three nested four loops。

 I have a loop over I， I have a loop over k， and then within that I have a loop over J。😡。

So one way to think about。What problem we're solving in the inter loops of these。

Of the dynamic programming algorithm。And again， I'm not going to make this。Connection explicit。So。

I want to find。第一。😔，Smamalllest。Entry。In each row。Of。An M by an array。

So there's a way of looking at this natural N cubeub time dynamic programming algorithm if you stare at the two innermost for loops and think about what computation is going on。

😡，嗯。So for each interval of a certain size， I'm looping over the starting index。😡。

And then inside that， I'm looping for the position of the first cut。😡，ok。So I can imagine。

I'm not actually， I don't have actually need to write this down， but imagine if I did。

 I can imagine a two dimensional array。😡，That tells me that it's indexed by the start of the interval and the position of the cut within the interval。

😡，And whose value？Is that added expression over there？And what I'm doing in that minimum。

As I'm searching for the minimum entry。😡，In every row of this matrix。

 for every possible starting point， which cut position gives me the minimum cost。😡。

So for every row in this array， what column position has the minimum value？嗯。So。

If there's no other information about this array。😡，There's really only one algorithm。😡。

That you can use to solve it。😡，so if I just give you。A two dimensional array。

And I start filling it in with numbers。Without worrying at all about no other structure at all。

How much time do I need to find the smallest element in every row？😡，And well， if it's a square array。

So right， so if it's I'm not assuming it's a square right。

 that'll actually be important in the algorithm later that it's not square。So。Root force。

Runs in MN time。So for every row， I do a linear scan for the minimum element。😡。

I spend constant time looking at every entry in the array。😡。

And there's a pretty easy argument for why that's the best that you can help for without any additional structure。

😡，This is one of those few cases。Where。You can actually prove that an algorithm is optimal。😡。

So suppose you don't look at every element in the input array。😡，Be an all power malicious adversary。

Can reach out to the vowels of hell and poke some entry that you didn't look at and change it to negative infinity and run off laughing。

Now。You have no way of knowing whether the adversary did that because they changed and entry in the array that your algorithm didn't read。

😡，And so A I said， no， it was like that when I got here。But your algorithm' is not going to return。

An entry in the array that it didn't look at as the answer first for that row， or if it does。

 then the adversary can go， okay， sorry， I meant。😡，Positive infinity。And again。

 you can't detect these changes to the input。😡，Because this is specifically defined to be part of the input that you didn't read。

😡，But yet。Depending on what the adversary does。You can make sure that your algorithm is wrong。

I assume you've all done this。Like there's a， there's a。You know， guess again。

 animal vegetable mineral， is it bigger than a bread box， does it live in the water， you know。

 you play with your friends in third grade or your sister in the back of the car and a long road trip。

😡，And of course， the way to win this game is doesn't live in the water。

 well I can think of more animals that don't live in the water than do so no。😡，You don't actually。

Come up with an answer， you just refine you answered the questions in a way that maximizes the degrees of freedom you have left and at the end you go oh yes。

 I was thinking of a capappabar all along。😡，You have to design our algorithms to like beat that。😡。

In this case， no additional structure， we can't。😡，But the nice thing is that a lot of dynamic programming algorithms like the one up there。

😡，There is some additional structure。Okay， so I'm going to define。3。

Increasingly stringent requirements。On a two dimensional array。mThat that look weird。

But the arrays that you get from the wood cutter problem actually satisfy all of them。😡，嗯。So。The 2D。

Aray。Is monotone。Oh， I guess I should ask， can anybody think of a special case of 2D arrays where it's really easy to find the minimum element in every row？

😡，Sored， if all the eras are sorted。😡，The minimum element is in column one。Well， okay， that's it。

 We're done for the day by that's not， that's not quite as interesting。 So instead。

 what I'm going to look at is。This example of an array over here on the right side of the screen。

 this is an example of a monotone array。😡，If。The minimum elements。In。Earer rose。Okay。Are above。

Or left。Of。Minimum elements。In later。Rose。Okay。Sorry。Get rid of all this stuff。Okay。Okay。

 so in this array over here the five by5 array over here on the right。

The shaded elements are the smallest elements in their rows。😡，And you'll notice that the indices of。

The positions of those minimum elements。Either stay the same or increase as I go from one road to the next。

😡，So。😡，Kind of right off the bat。You might be able to guess。

That if you knew somehow in advance that your array was monotone。

 you might be able to do a little bit better than brute force。😡，Because for example。

 once I've located。This index 8 as the minimum elements on row 3。I know that。

None of these elements appear above and to the right。😡，Can be the minimum elements in narrows。

I don't have to read that part of the array， I just have to be guaranteed that I'm given something that's monotone。

😡，系。Now。The algorithms that I'm going to describe。Look at。Subsets of the data and in particular。

 subsets of rows and subsets of columns。嗯。😊，And I'd really like to be able to say that this monotononicity property survives looking at only portions of the array。

😡，But if you。Say if I。Keep only the first and third row and only the third and fifth column say I look at this two by two。

😡，Subareray。Determined by rows1 and3 and columns3 and5。

The minimum blue element in row1 is the one on the right。😡。

And the minimum blue element in the third row was the one on the left。😡，So this is monotone。

 but if I start erasing rows and columns， it's not going to stay monotone。😡，So。This is the second。

Condition。嗯。你是。Totally monotone。If。Every submatri。嗯。

The other word that sometimes used for this is minor。

 so a minor is the array that you get when you take a subset of the columns which are not necessarily contiguous and a subset of the rows that are not necessarily contiguous。

😡，嗯。Is monottonone。And it's actually enough。To look at two by two。Miners。And。

So pick your favorite pair of rows and your favorite pair of columns。😡。

And now I'm going to do comparisons of the two chosen elements。😡，In each row， so one possibility。

Is it in this two by two minor？The minimum elements are both on the left。😡，One possibility。

Is that the minimum elements are both on the right？And then the final possibility。

Is that the top row has the smaller element on the left。And the taller element。

 the bottom row has the smaller element on the right。What you're never allowed to see。Is。

This pattern。So this pattern。Is not allowed。We look at any pair of rows， any pair of columns。😡。

And do comparisons in this two。Pears， you will never see this pattern。😡。

And I'll let you sort of stare at that five by five matrix。😡。

I don't recommend doing this for every pair of rows in every column。

 just pick out some rectangle and look at those four numbers。😡。

You'll see one of those three patterns。So it's monotone。And when you throw stuff out。

 it's still monitored。Again， it seems very weird and very artificial。😡，But。嗯。

Just to give you an idea of a matrix that。😡，Satisfies these conditions。Take that piece of board。😡。

And think about the matrix that encodes the length function。

 the value at row I column K is the distance between the I mark and the Cafe mark on the board。😡。

That matrix。some technicalities because it's only an upper triangular matrix。

 but let's ignore that that matrix， four by four any two by two subet where all four entries are defined。

Will be monitored。I should。Say。When。You need to break ties， you break ties to the left。

For simplicity， I'm just going to assume all the entries in the arrays are different from now one。

Com。And then there's one more。Technical condition。嗯。

But I think I'll get I'll talk about the technical conditions at the end if I have time。

 it's a way to get totally monoted matrices and in fact it's the most common way of getting totally monoed matrices or showing that a matrix is totally monotoned but as I said I think I'm going to talk about that at the end rather than the beginning because。

😡，嗯。They don't really need it。For the finding the row minimum。Okay。So。This。

Is the problem that I want to think about？And first。Let me start by just assuming monoonicity。

Not total monetary， just let me see what we can get。😡，With just a monotone array。喂。

Any questions about the problem before we start looking at the algorithm？😡，Okay。So。Yeah。

I'm trying to find the row Minma。DN a。Monione。All right。All right。

 so I'm going to describe an algorithm that I call in the notes。Filter。In the end。

 this will run in M plus n log M time， so M is the number of rows。N is the number of columns。

Bte force is Nm。The order M term there is inevitable because I'm eventually going to return M different values。

😡，The positions of the minimum element on each of the MRs。

But this is the real work is being done in that analog log M time。😡，And。That looks like， oh。

For every column， I'm going to do a binary search。😡，That would give me that running time。😡，No。

 that's not how it works right and again， this is one of the reasons why we don't tell you running times generally in the homework。

It's because they often suggest approaches that are just completely off。And I want to avoid that。

So there are two ways that I can describe the filter algorithm， one way is top down。😡，A。And so。

Let's start with my array， again， not necessarily square。

And the first step I'm going to do is I'm going to find。The minimum entry。In the middle。R。Okay。

 so here's the middle row of the array。And I find the minimum entry here。

Because the array is monotone， I know the minimum entries in the earlier rows can't be further to the right。

😡，And I know that the minimum entries in the later rows can't be further to the left。😡。

So just by finding。That one minimum entry。I can now essentially discard。A whole chunk。Of the。嗯。

The input array， so let's suppose that the array element that I find， this is in row M over two。

At array element H for half。Great。So。The next step is I'm going to recurse。

In this upper left portion。It includes column H， but nothing in any later column。😡。

And then I'm also going to。Recurse in。I don't know how that happens。

So I understand how that so how did I misspell that， they swapped the two letters。

 I know how that happens when I'm typing。Because one finger gets ahead of each other。

Have never understood how my own brain works or how my hand works。That when I'm writing。

 sometimes the letters come out in the wrong order， it's not like I don't know how to spell recur。😡。

But brain sometimes not work。嗯。And then the second recursive call is in his bottombright quarant。

Yeah。哎。So find that solid red thing in the middle， row。😡。

Recurs in the yellow subreet above and to the left。😡，Recurs in the pink subide down into the right。

Right。So。Let's see what the running time of this is。

M is the number of rows and is the number of columns。All right。

 so how much time do I need to find that middle element in the？

The smallest element in the middle array， the middle row。我问。This is just brute force。

 again there's nothing I can do about this。😡，I mean， I'm not looking at the rest of the array。

 so if I'm only given this one dimensional thing and I want to find the minimum。

 I have to read the entire row。😡，But then I'm going to recurse。On。

Two subs each with about M over two rows。And well， either about H columns， sorry。Yeah。

 about H columns or about n minus H columns， I've deliberately thrown out a couple of plus ones that can be massage out of recurrence。

So this is really the。How you want to see the recurrence？啱。系。So， looks's pretty bad。

Two argument recurrences are always a little bit fun。So I'm going to build a recursion tree。

And as usual， I'm only going to look at the first couple of levels and at each of those levels I'm going to say。

 oh， this is the recursion tree for T of MN， this is the recursion tree of t of M over 2。😡。

H this is the recursion tree of t of m over2 n minus H。And then inside each node。

 I'm going to write down。😡，The non recursive work that goes into that node。So in the root。

 I'll write down n， it's the second argument of the T function。

 so in this node down here on the left。The second argument is H on the right down H。

Note over here on the right and minus H。And you'll notice when I do this。

 the total amount of non recursive work that I do at the first level of the tree is also n。😡。

So if I do the thing that I usually do with recursion trees。And I sum up。The work at every row。😡。

You'll find that the total amount of work I'm doing at every row in this tree。😡，Is order N。

With the same constant actually。On the other hand。The depth of the tree。

Is controlled by the first argument。😡，When I。Ca this function。With our array with M rows。

 my recursive calls always have M over two rows。😡，So what's the depth of the tree？

What base two of them？So。This order N really is only counting how many comparisons I need to do within the rows。

😡，So the total number of comparisons I need at every level of recursion that all sums up to N。😡。

And they're log based two of M levels of recursion。😡，So this comes out。😡，To n log M。

But then there's also a little bit of overhead I have to spend at least constant amount of time on every row doing something so if I really wanted to do this carefully I need to。

😡，Every term in this every value that I wrote in this tree is at least one。😡。

And the number of nodes in the tree is M。So that's where the overhead of plus M comes from。Yeah。

It's far for。If it's only one column， then this is a really easy problem。Well。

 I'm given the size of the array when I given the input。So I do know that I look at the value of the。

The variable n， and if I see that as one， then I know there's one column。等是么怎么。Oh， oh。

 what happens if the minimum is only in one column then what happens is。😡。

You find the minimum in the middle row， it's all the way on the left。😡。

You immediately know that all the， all themin above that are all the way on the left。😡。

Because it can't be further to the right in higher rows。

And you recurse in the lower half of the array。So you spend linearier time and you cut the array in half。

You get a descending geometric series。So the left edge the right edge of the yellow part is that red entry in the middle row。

The left edge of the red part is that red entry in the middle row。😡，So no matter where it ends。

If H could be1， H could be n。😡，This analysis still works。😡。

It doesn't matter where doesn't matter where that red spot is。

 half of the array is gray and I can throw it out。😡，Yeah。对以。So if the array is wide， again。

 this still works out。😡，This means that when you get down to one row。

 you're probably still going to have a non trivial segment of that row that you need to search。

But this will all kind of get。Fold it up。Into this order N factor here。Well， remember。

 I'm always looking for the minimum in every row。😡。

So this is not a transposing the array changes the problem completely。😡，Yeah。ま。Okay。So。

I think just from a very， very high level viewpoint。

 one way to look at this is I started off with an array of size of area MN。😡，After doing。

Order and work。Unless the two subares whose total area is M over 2。😡，And。😡。

The sum of the widths of those two subs is still only in。Really， it's n+ one。

So brushing the plus one under the rug。Right。So。This。Is H and this。N minus H。

So when I recursively search the yellow array， I'm going to be spending order eight time finding the middle。

 the minimum element in the middle row of the yellow subarray。😡。

Thenim'm going to easy spending order n minus each time finding the minimum element in the middle row of the pink array。

😡，And those two running times summed together or order in。😡，Yeah。8点。So。

Really what I should be writing here。Is。This is。there's a plus one here。

W and I should write it plus one here and plus one here， plus one here。

 there's a little bit of overhead。The plus ones。So。If I add up all of the plus ones throughout this。

😡，Recursion tree。That's going come out to M。I'm doing some amount of work on every row of the matrix。

😡，But then if I ignore the plus ones。Anything every row of the tree only depends on in。Yeah。不行。Okay。

 so this is where I'm playing a little bit fast and loose whenever you just sort of get rid of the Big O。

Right。The problem is if these things get really unbalanced。Then if I don't put that plus one in。

 some of these nodes will have zeros in them。😡，And well。

 but those nodes still have work attached to them。So let me show you the same algorithm。😡。

But now bottom up。And。This is。Not a different algorithm。

 it's just a different way of looking at the same algorithm instead of starting at the top of the recursion tree and working my way down。

 I'm going to start essentially at the bottom of the recursion tree and work my way up。😡，So， again。

I've got my。M by N。Allray。Step one is。Find the minimum elements。In。Every。Even row。

So I'm going to split。My array into kind of like we did with FFTs。嗯。😊。

I'm going to find the minimum element in row two。Then the minimum element in row4。

Minimum element in row 6， minimum element in row 8， minimum element in row。1en and so forth。

So it'll look something like。This。嗯。Now。嗯。Because the array is monotone。

The indices of the row minima always go down into the right and that definition still remains true if I take a subset of the rows。

😡，So sub sequenceence of an increasing sequence is still increasing。

 the problem with total monoity comes up when we start erasing columns。So。

These red entries in this array that I find recursively。😡，so this is recursively。

So you can think of this as。😡，Take every even row and copy it into a new array at SSI's M over2 by n。

 find the minimum elements in those rows and copy it back。

 except you don't actually have time to do the copy forward and copy back。😡。

So really what you do is some fancy index arithmetic。😡，And say， well， when I tell you row 5。

 I really mean row 10。😡，So you have to like。Tell the subbertine what to multiply the row indices by when it does its excesses。

So you can do it all in place。And now。Search。In each。Od row。Only。Between the Min。

Immediately above immediately below。So the minimum element in the first row must be in that part of the row。

 it can't be further to the right because of monoity。

 the minimum element in third row has to be somewhere in this range。

 the minimum element in the fifth row must be at that column。😡，And so on all the way down。

So you end up with this。Kind of。Staircase looking structure。Recursively， I find all the red things。

And that tells me that in the odd rows。In each of the odd rows。

 the minimum must be in one of those blue ranges。😡，Now。Every blue thing that I have marked there。😡。

Is either？The highest blue entry in its column。😡，Or it's the leftmost blue entry in its row。😡，Okay。

 so the total number of things I need to look at。Here is M plus N。

The total amount of blue stuff in that picture。😡，I's proportional to the total number of rows plus the total number actually half the number of rows plus the total number of columns in the array。

It's only a linear amount of stuff。Okay so I can do brute force in the blue parts in linear time。

Yeah。So。Now I get a recurrence to looks something like this。Now。

 this is an even simpler thing to think about。So。Let's sum up the order M terms through all the recursive calls。

😡，So at the top level that I have an order M term， the next level down， I have M over two。

 the next level down， I have M over4， the next level down， I have M over8。

So the order M terms define a geometric series。😡，That sums up to order M。Roughly 2 m。

And then look at the order n term， but then notice the n never changes。😡。

The width of this array stays the same at all levels of recursion。😡，嗯。So。Every level of recursion。

 I have an order N term， and there are log based two of M levels before the recurrence bottoms out。😡。

So maybe this is a little bit clearer than the other top downway of looking at it。

 at least for the analysis。But if you actually look at what happens。

 if you run this algorithm recursively， and follow the recursion all the way down。😡。

The base case of the recursion is I only have one row。😡。

And if the size of the array is a power of two， it's going to be the row right in the middle。😡。

And then I'm going to pop up a level and then do the middle row in the top half。

 the middle row in the bottom half， and pop up a level， middle row in the top fourth。

 the middle row and second fourth and so on。So it really does end up being exactly the same algorithm。

😡，Just look at two different ways。All right。So。As long as the number of rows is substantially bigger than the number of columns。

 this is linear time。没有。😡，I want you to。Notice what I've done here， I've done something very strange。

Have described an algorithm。That does not read its input。😡。

The input to this problem is an M by N array。😡，But the running time of the algorithm is less than m times n。

😡，So the only reason I can get away with this is that I was promised in advance that this array has some particular structure。

 you've done this trick before。😡，So can you think of another algorithm？😡。

Where the running time is less than the size of the input。You saw it in 124。Binary research。😡。

Is is the number 10 in this sorted array？😡，The input has sizes end， but somehow the running time。

Doesn't have to look at the whole array because， you know in advance that the array is sorted。 Now。

 the wonderful thing about this is。This array might not actually even exist。

It might not be an explicit chunk of memory that you're searching。

 it might just be this mathematical abstraction。😡，And whenever you need a single entry in that array。

 you compute it on the fly in constant time。😡，This is actually what happens when you start using the stuff inside dynamic programming。

 you don't really build a two dimensional array and then look for the minimum element in every row。

 you say ah。😡，There's this mathematical function that I can model as a two dimensional array。

 I can find any value by computing this formula。😡，In constant time。And then I can run this algorithm。

😡，It finds the minimum element in every row without。😡，Constructing the whole array。

So is this really kind of？Lovely magic going on here。嗯。

It's the extra structure means you don't even need to build the thing you're searching。😡，Right。😔。

All right。So。That's。As far as I know， if all I know is the array is monotone。😡。

This is the best we can hope for。So。Let's look at。嗯。The case of。Totally monotone。And remember。

This is in every two by two。Im array。Every two by two minor。Is monitored。嗯。This algorithm。

 by the way， is。Called smoke。That's sure， Moran。Agar wall。Wilbur。And Clve。

Those of you who know anything about quantum computing might have heard of Shore's algorithm。No， no。

 no， this is the real Fors algorithm。This is the shorts algorithm that people。😡。

They'll actually run a few million times a day。😡，U。😊，啊。Maria Clave was the president of Harvey Mudd。

For many years。啊。This is the most impressive person on this list。I think I've met。Three of them。

 Sho Agarwall and Cle。But Marie is by far the most impressive person on this list。嗯。Okay。

 so this picture that I have here in the middle of the screen kind of illustrates the main trick。😡。

So when you have a monotone array。😡，Once you find a minimum element in one row。

 that allows you to throw out whole swaths of the matrix。😡。

And it just goes away the trick here is just by doing a comparison between two elements in the same row。

Depending on the outcome of that comparison。😡，The definition of total monoity means I can throw out a significant portion of the array。

 so if between these two stard elements here on the same row， if the one on the left is smaller，😡。

Then just looking at the rh minima in those two columns。😡，Right， I know that。😡，Well。

This is the row minima on this column doing the comparisons。😡，And therefore， these entries。

Can't be the minimum entries in their rows。😡，Because the row minima within those two columns has to be start on left and then switch over to the right for a while and that's it。

Similarly， if I do a comparison and the one on the left turns out to be bigger。

 then within those two columns， the minimum of this middle row is the one on the right。

 and so the other lower entries in that first column can't be the minimum entries in their rows。😡。

So by doing one comparison。I'm either going to throw out。

All lower elements in the first column or all higher。😡，Elements in the second column， right？

So one comparison。Tills。a bunch。Of entries。In one。看我。嗯。So。The algorithm that smoke came up with。

 here it is。😡，It's a。9ine lines。咁。嗯。This is not。By any means。

The hardest nine lines of code you will ever try to understand。

That's the Canuth Moores Pratt string matching algorithm we'll get to that later。

And that's only six lines。But still understanding exactly what's going on here is a bit is a bit daunting。

 so I'm going to I'll show you you here's the pseudo code it's really simple。

 but the explanation about what's going on is maybe a bit more complicated so let me walk through this very carefully in the next 15 minutes。

😡，All right， so。In particular。This is for the case。Where the array is。wideide。

They take a wide array where。N is bigger than them。And in linear time。I'm going to reduce it to。

An M by M array。Okay，Previous by doing recursion， I kind of looked at subsets of rows now by doing this by calling this reduce algorithm。

 I'm going to throw out。😡，SoMost of the columns of the array in a way that guarantees that the minimum element in every row survives this reduction process。

 Sam。😡，1。Those aren't necessarily。It just。Any two elements in the same row？Within those two columns。

😡，Because it's totally monotone within those two columns。

 whichever of those two elements is smaller is the minimum row element within that n by2 minor。😡，对。

So reduce takes a wide array。😡，And in linear time， time proportional to the number of rows plus the number of columns。

 which because it's y just means the number of columns。😡，Reduces it down to a square array。

 it throws out most of the columns。😡，喂。So there it is。Now it's glory。

S here is an array of indices of columns， and well。

 there is returning the indices of the columns that actually survive。So。What are the？

The invariance here。Sad this array us。I should actually say S from one to。T。

Is the stock of column indices？Sored in increasing order。In particular。

 T is the index of the top of the stack， that' why it's called T。😡，You'll see at various places。

 which says pop， T goes down by one， that means I'm reducing the size of the stack by one。😡。

Or pushcade， I'm adding tea to the stack and incrementing。

AreIncrementing the index and putting something at that place so this。

This array S is just it's a stack on pushing and popping things。嗯。So the second invariant。Is that？

Were all indices of things that are on the stack。OnThe top。J minus1 entries。In column。S of J。

Are dead。Okay， so。In the。Colum index that said S1。I know nothing， nothing is dead。

 but in the column index by S2 top element is dead， the column index by S3。

 the top two elements are dead， so the picture looks like like this。😡。

So here I'm jumping into the middle of the algorithm， in this case k is equal to7。

 I guess you see S1 S2 S3 up at labeling the tops of some columns。😡。

And the shaded parts indicate the portions of those columns that are dead。😡。

So there's this staircase going down。Now， the third invariant is that a column doesn't show up in the stack anywhere。

 the column is completely dead。😡，Okay。If J is not。I should say。

 let me be a little bit careful if j is less than K and。Jay is not。In S。Then column J。Is。Dead。

Completely dead， totally dead。Not going to get better。Okay。

So there are the invaris now at the beginning。T is equal to0。

And so all three of these invaris are vacuously satisfied。At the beginning， the stack is empty。

The empty sequence is increase sorted in increasing order， there's nothing in the stack。

 so everything on the stack satisfies that property too and K is at this point equal to one。

 so everything in the first zero columns is dead。😡，系。

So there's this weird pictorial structure where I've chosen some columns to survive and I've chosen already chosen some columns to throw away。

😡，And now what the algorithm does is it looks at。😡。

The highest entry in the column on the top of the stack。😡，It isn't dead。

And the corresponding element。😡，In the next column that we're looking at in column K。

So those two start entries are the next comparison we're going to do。And well。

 there are two possibilities for how that comparison can play out。😡，Depending on which way we go。

 I'm going to update this structure in one of two ways。😡，So one possibility。Is that I discover。

That the element on the left that pair is smaller than the element on the right。😡，At this point。

I know。That nothing here。Above the element to the right can be a row minimum。😡，Right。

Above the one on the right， if it's bigger or below the one on the left， if it's bigger。😡。

I also know that this start entry on the right can't be。😡，A row minimum。

And so now I'm going to call this as7， I'm going to push that onto the stack increment K。

 and now I have exactly the same structure that I had before， the dead things。Line up。You know。

 above these lines。Again， in his following staircase pattern。

And the next two elements I would compare would be these two。嗯。The other possibility。Is that。

I discovered that the element between those two that I'm comparing， the one on the left is bigger。

In that case， everything below the elements on the left。😡，Is dead。And in fact。

 the element on the left itself is dead。And so that is just let's。Pop。

That column off the stack gets' completely dead， I don't need to remember it anymore。😡。

And the next two elements that I would compare would be this one。And that one。And again。

 all the invaris that we wanted are maintained。😡，All in both cases。

The columns that are on the stack have an increasing amount of dead stuff at the top。

 the columns that are not on the stack are just completely dead。😡。

They don't contain any those columns cannot contain any row minima。😡，And then， I'm。

Ready to do the next comparison。Every comparison does one of two things。😡。

Either pushes a column onto the stack。😡，It's the first case。Or it pops a column off the stack。😡。

Once a column is popped off the stack it's dead， you're not going to look at it again。

 so that means each column can be pushed onto the stack at most once and it can be popped off the stack at most once。

😡，Yeah。There are N columns。So if each comparison does a push or a pop， they're at most n pushes。

 they're at most end pops。😡，So that means。They're at most。Two end comparisons。

For the entire algorithm。And what you get at the end。Is this weird staircase thing。

 but because parts the parts of the columns that we're keeping。

 the dead parts keep growing once you have M live columns，😡，Everything else is dead。So in the end。

 what you get is an M by M array。And in fact， you know that the entire upper left half。

 upper right half of that array is dead。😡，But the amount of time that I spent。

Was only proportional to the number of columns。So again。Here's。The magic nine lines of code。

I'm really not hiding anything here。There's no data structures， there's no hidden anything。

 it's like here is you know， basically the transcribed Python with a few comments。😡，That's it。

Okay so what this does again， is it takes a wide array and narrows it down until it's square。😡。

Al right， so。The smoke algorithm really combines both of the algorithms that I've shown you here。😡。

If the array is tall， then I'll reduce it by。Cutting the arrays in half， if it's wide。

 then I'll reduce it by cutting the columns down to M。嗯。

Maybe before I go into the final analysis this algorithm together， are any questions about this one？

Including wait what just happened？Because it just sort of like。I feel like going。

 is this your card at the end of showing this algorithm？Yeah。Yes， it is。

It's finding the minimum element in every row of a totally monot matrix。😡，But it does it by first。

 let's reduce it down to something。 If it's wide， let's reduce it down to something narrow。

And then what we're going to do is。😡，We notWe're halfway there。So the next step is。

I'm going to shrink it like this。😡，Using the filter algorithm and then reduce and filter and reduce and filter and reduce and filter and reduce filter。

 reduce the filter， but all this stuff is going to add up to a geometric series that will vanish in the end。

嗯。But again， earlier felt like this doesn't even go。

so you feel continuously as you feel feet already。Okay， so。Let me， let me try again to。

Think about where where this comes up in the context of dynamic programming。

 so if I go back to my example of the woodcutters problem， you've got these three nested four loops。

If I look at what the inner two four loops are doing。😡，I'm computing a value for every I。

 I'm value for every J。😡，And somehow I want the best J for every eye。Okay， so the best。

 if I think of those is value for given I andJ is being written over here in this array。

I'm looking for the smallest element in every row。Now。

 the actual dynamic programming algorithm doesn't build an array。

 a continuousig chunk of memory and write all of those values down。😡。

The brute force algorithm is kind of。Scanning through each row。

 computing the entry that would go there on the fly and seeing if it's bigger than entry it'd seen before smaller than entry it'd seen before。

 so it's scanning the array but not bothering to write it down。😡。

But you're still spending time proportional to the area of the array。😡。

What I'm suggesting instead is that we slot in one of these more efficient algorithms。😡，But again。

 the array isn't written down， but I have the ability to look up one entry in the arrays if it were written down。

😡，And then instead of doing M times N。BFor scan， I'm doing something that' looks more like n+ n。

So that reduces the running time of the algorithm by a linear factor。Okay。

So questions about the reduce algorithm。Okay， so let me go back to the high level thing now。

 so I want to find。😡，The row minima。The smallest element in every row。In a。Totally。Monione。😔，Aorray。

Okay。So here we go。This is again M。By n。If M is less than your favorite constant， use brute force。

This takes。Order end time。ButWe've only got 10 rows。

Just scan every column in every row and the 10 will get swallowed up in Big O in fact。

 in reality its if Emma is one， do this。嗯。Okay。Case 2。If。M is less than n。

Then I'm going to do this reduction algorithm。To an M by M subet。And recur。Thanks so。Sorry。

 this is the wide part。It's wide。Then in linear time。This takes me order end time。

I reduced to the square array。哎。😊，3。If M is greater than or equal to N。

So this is the case where I have a tall array。啊。I'm going to use the。Bottom up version of filter。😡。

So this reduces to an m over 2 by n。Well， I should say minor here。And recurse。And then scan。Okay， so。

Look at every even indexed。Row， recursively find the minimum of those rows。So this ends up。

Eventually reducing it to the point where the array is shorter than it is wide。😡。

And so after possibly an initial phase where you're reducing the height so it's less than the width。

😡，You're just bouncing back and forth between cases two and three。In one case。

 you're making it half as tall and then in the other case you're squaring it up again。

 so you're cutting the height in half。😡，And then you're making the width equal to the height。

 so you're cutting the width in half。And so you end up with what's dominated by a。Gemetric series。

 so I'll just write down。The running times here if M is order one。Soer n plus T of MMm。

If M is less than n。Ins sorter M plus。T of n over2。If M is greater than or equal to n。And。

After a bit of work。This comes out to be。Line your time。Yes。So in the filter part。

 remember the way filter worked is I recursively computed the minimum element in every other row。😡。

And then I did the scan to compute the minimum elements in all of the odd rows。

 that's the point where the answers are bubbling back up。That's right， we recur down。

 get the answers to sub problems and then work our way back up。😡。

So working your way back up for reduce involves doing some indirection in an array。

 working way back up for filter involves this linear scan。😡，Okay。That's it， we're out of time。

 happy to answer questions up front。😡，嗯。Otherwise， I'll see you on Thursday when we'll start doing probability。

I me like why I got the on this problem。 mean I just。



![](img/14f3defac8ffc0e5e9a788859c4b3b1e_3.png)