# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p12 20230928-Sep 28_ Divide and conquer.zh_en -BV1Mh7RzaEL2_p12-

![](img/51f3e953ad2fbc109d0ba00e9c2f8701_0.png)

诶我。没。Okay。I have no idea how little card。

![](img/51f3e953ad2fbc109d0ba00e9c2f8701_2.png)

到了。We think their really。平台。我哋系系啲方大有思想问。喺咪你多。

![](img/51f3e953ad2fbc109d0ba00e9c2f8701_4.png)

解系好似。没。可可能。好。就直直接。でな。't understand。All right， hi， everybody。Thank you for coming。嗯。系。诶。

We're going to talk about recursion some more and I'm going to talk about some more interesting versions of recursion than we talked about on Tuesday so。

Most of what you're going to see today is going to be new material。U。

I'm going to start by talking about Quick sort again。Because there was a point that I wanted to make。

That's actually going to be important for the you know later in the lecture material I planned for today about Quick sort。

嗯。So hopefully everybody remembers how Quick sort works， the idea is you choose somehow。

An element of your input array to act as a so called pivot element。You run this I subroutine。

To break your input array into three parts。On the left。

 you have all of the elements that are smaller than the pivot element。

 then you have the pivot element itself， and then on the right。

 you have all the elements in the input array that are larger than the pivot element。

And then you ask the recursion fairry to sort the part on the left。

 and then you ask the recursion fairry to sort the part on the right。Well。This。Partition subroutine。

What this actually does is you know sort of。Partition。The array A。

Into less than what is now called AF P。A of P itself。

And everything that it' greater than AFP and return。The new index。Of what is now called A ofP。

So in the example input that I'm showing you here， I would click。

And the petition subroutine with p equals 12， assuming my array is index starting at one。

And it would return。The value nine， and that would be used the rank of the pivot element nine。

 that means this is the ninth smallest element in the array。That's the variable R over here。

In quick sort。And then so the first recursive call sorts the first eight elements of the array and the last recursive call sorts the last four elements of the array。

诶。So。Everybody on board。With quick sort。Now， yeah， sorry。It get。I picked a pivot element somehow。

 it just happened to be the letter P before pivot。That is the 12th item in this array starting at s is at one。

 O is it two， or is it three， and so on。So。It's just it's the position of the pivot element in the array。

 not the value of the pivot element。Okay。Now， if you want to analyze the running time of this algorithm。

😡，What that is well， a recurrence that is unfortunately rather ugly， there's the linear time。

Or running the partition algorithm。Without going through the details for purposes of analysis。

 the partition algorithm does some constant time stuff and then it has a for loop that has about n iterations and inside the for loop I do a constant amount of stuff。

And then outside the fore loop I do a constant amount of stuff。

 so this translates to big O event the only interesting thing there is the for loop。U。

But then I need to make two recursive calls。😡，But unfortunately。

 the sizes of those recursive calls depends on the value of the rank。

Depends on the value of this variable R， which I have no way of knowing in advance。

And doesn't depend on just n， so I'd like to write something that looks like this。

But I can't because in this recurrence， the variable R is undefined。

So I need to put something around this in order to declare。Scope。

 and now I'm deliberately aiming here for a worst case running time。So I want to be able to say。

 no matter what the input is， this algorithm runs in it most this much time。

And partly because that's what Big O is and partly because especially in this class we want to be deliberately pessimistic about how our inputs are going to be designed。

 we should assume that the person designing your inputs hello has access to your code and is deliberately going to choose inputs that make your code as slow as possible。

So in this particular algorithm， the worst case choice here turns out to be either r equals1 or r equals n。

 I either choose the smallest element is my pivot， and so the left subproblem is empty。

 but the right subproblem has n minus one things。😡。

Or I choose the largest element is the pivot in which case my left subproblem has n minus one elements and my right subproblem is empty。

 yes。我 you drink咩。而 how do you know it。That there isnt a。Her bound for it。

How do I know that1 and n are in fact the max， is that what you're asking？Either bound they could。

Well， okay， so remember， I want to absolutely assume the worst。Max assumes the worst。

Whatever the value of R is。The T of r minus1 and t of n minus r describes the behavior of the rest of the algorithm。

So the only free variable that I have to control whether the pivot is good or bad is this variable R。

😡，So so there are algorithms where。There are multiple ways of doing the analysis and some lead to better bounds than others。

I'm not really going to see those algorithms in this class。Okay。So。It turns out right。

 so if I set r equal to1 or r equal to n， this these are in fact the worst cases。

 so we get this recurrence。T of n is at most big of n plus t of n minus1 t of zero goes away because I happen to know that sorting zero things takes no time。

So here you substituted one in because I just made your asking like you have could have so I'm I can。

It would take a little bit of work， but work I didn't really schedule time for to prove that in fact。

 one is the worst case here。So one way to do this is try different values of R and you'll notice if you solve the recurrence under the assumption that r is equal to n over two。

 you get the merge sort recurrence and comes out to n log n and that's pretty good when you solve it for say r equals n over four。

 you also get n log n but with a worst constant， if you solve it for 10， you end up with n squared。

 you solve it for one， you end up with n squared but with a worst constant。

So you can try a few values and in general， the max either tends to be at the extremes or right in the middle whenever you've got a parameter like this。

So I'm trying to provide the intuition without going through the math。Um， mostly because again。

 we're generally not going to be giving you things like this。

But I do want to lead up to an algorithm that does more interesting recursion with this as a significant point。

So， okay， so because。Ours if one was the worst case that exactly。That's right。

 R equals one is in fact the value of R that maximizes that expression。So I just plugged it in。UAnd。

This comes out to two of them is blue of n squared now every bgo is an implicit less than or equal to。

Big O means less than or equal to some constant times。In practice。

 it means less than or equal to a million times。Hey， Biggo is， you know。

 always at most and I should say always in practice， it's at most a million。

 if you want to be a theoretician， it's at most to Google P。But it's at most some constant。啊。

So writing less than or equal to big O， I'm being sort of redundant because the less than or equal to is already implicit in the big O notation。

 but just want to emphasize that this is an upper bound。

And not a statement about all the running time is some constant times n squared。Okay， now。

The intuition that you've been told in the past。And in various forms is that in practice。

 quicks runs an end log N time because in practice the pivot element is likely to be somewhere in the middle。

 and if we imagine that somehow magically，The pivot element is。So sometimes by magic。

We know that r is equal to n over two， so if we just happened。

To pick the median element in the array， the element that sits right in the middle after we're done sorting。

Then this would imply a recurrence。嗯。To go of n plus t of n over2 plus t of n over two。

 which is the merge short occurrencerence so we know that it's in log n。做。

And the intuition that you've been given is， well， we're not ever。

 we're actually fairly unlikely to choose exactly the middle。

 but we're going to get close enough to the middle that this is the right thing to keep in your head。

So I'm going to expand on that intuition just a bit。And let's say， you know， somewhat less magic。

R is between n over three。And two and over three。So the idea is here is my input array and R is going to be somewhere in here。

Somewhere in the middle third， the array。This is going to happen about one out of three times if you chose your pivot uniformly at random。

嗯。So what happens if we can somehow make this assumption， then T of n becomes， again。

 big O n plus the max。😡，Over now not all possible values of R。

 but are just between these two extremes。F T of r minus1 plus T of n minus R。

And the same arguments that leads you in the general case to say， oh， in the worst case。

 the pivot is the smallest element or the largest element。

The same arguments imply that for this recurrence， the worst case is when r is as small as possible or when an r is as large as possible。

So an unbalanced pivot is going to lead to more work。

 a balanced partition is going to lead to less work。

 so in this case the max it happens at either r equals n over three or r equals2 n over three。

In which case you get。This。Running time recurrence。Again。

'm there's pluses and plus ones and minus ones and for that matter of floors and ceilings。

 if n is not divisible by three， then I'm kind of brushing under the rug because I know I can do that this is the recurrence that I get if somehow magically I can always choose a pivot in the middle third of the array。

So let's figure out what that recurrence implies about the running time。系。

Any questions about the game that we're playing here？I'm imagining。

 the pivot somewhere in the middle because that happens reasonably often。

What happens if you know what would the resulting running time be if it's always in the middle？Wれ。

Like being a T 103， the T of 203 is。That that's what allows you to put art in that way。No， no， no。

 no， so let's understand the game that I'm playing here。

The intuition we have about Quicksortt is it's efficient because usually the pivot is somewhere in the middle。

So let's nail down that assumption just for purposes of strengthening our intuition。

 let's suppose somehow magically the pivot is always somewhere in the middle。

 specifically it's somewhere in the middle third， so I'm just making that as an assumption。

And then say， okay， now what would that imply about the run in time of the algorithm？Okay。

 so I'm making this assumption here。so just assume this。

That implies that when I'm doing the analysis， I only have to consider R in that range。

And within that range， again， the intuition is。Unbalanced partitions are going to lead to more work than balanced partitions。

So the worst case is when r is as small as possible and over three。

 or when it's as large as possible， but two and over three。记没。7。Right。

 so the assuming that I chose r equals n over three， say my pivot value is actually here。

Then t of n over three is the time to sort this sub array。

And T of two and over three is the time to sort that sub。嗯。So。

The way we would analyze this is to draw a recursion tree。

So I'm going to start by writing the non recursive part of T of N at the root。It's bigger O end。

 so I'll drop the bigger O。Then I have left sub problem and right， sub problem in the left subproble。

 all right。The non recursive work for。The problem of size N over 3。On the right。

 I'll write the non recursive work。For a problem with size two and over three。

Now in the left subproblem again， I'm imagining this n over32 and and over three split。

 so in the rightmost grandchild of the route， I have n over nine。

Two and over nine in the middle grand childild。Again， two and over nine in this middle grandchild。

Again， n over nine in this sorry， for n over nine in this rightmost grandchild and this tree will continue like this。

Okay， every time I branch。When I go to the left。The problem size goes down by a factor of three。

When I go to the right， my problem size goes down by a factor of 1。5。

So this is not like the original merge sort recurrence where every subproble at the same level has the same size involves the same amount of work。

But the pattern still plays itself out。诶。😊，Um，So if I wanted a great great grandchild down here on the far left。

 would I would write N over 27 there。If I wanted a great grandchild way over here on the far right。

 I would write 8N over 27 there。Always divide by3 and divide by three and multiply by two。

So does everybody understand where that tree came from？Okay。So let's figure out what this adds up to。

So we're going to do exactly the same thing that we did with the merge sort recurrence we're going to sum up along each row well along each level well level zero of course is just the root that adds up to n level one n over three plus2 and over three that adds up to n。

Level two。That's。One plus two plus2 plus four is nine and over nine。So this adds up to N。

And so just like the Mer sort recurrence。The total work at every level。Is that。

So then the next question we asked about the emergency sort recurrence is how deep is the tree？Well。

 so there's a problem here。Is that this tree isn't balanced。不。Wing to if I go down to the left。😡。

The problem sizes decay really fasted， so I'm going to hit a leaf。

A lot sooner than when I go down to the right where the problem size is are decay more slowly。

 so instead of just looking like a flat。Triangle。The recursion tree has this weird lopsided shape。

 it's bigger and deeper on the right than it is on the left。So how do I answer the question？

How deep is this tree？Well。What I'm going to do is I'm going to say ah。

 remember I'm going for a big O bound， that's just an upper bound。

 it's okay if I overestimate the sum。😡，It's okay if I come up with an answer。

 it's a little bit conservative， so I'm going to do is I'm going to cheat and I'm going to imagine that the treat continues。

On the left until I'm just going to add in these these weird nodes that don't actually correspond to anything in the running time。

 they're just values that I'm writing into a tree。But I'm going to expand that tree out following the same pattern until the tree is perfect until it's flat。

And then I ask。Now。What is the depth of this tree？Which is the same thing now is really asking what's the depth of the deepest leaf。

 what is the maximum recursion depth that this algorithm ever sees？

Does anyone want to guess what that depth is going to be？Every time I go to the right。

My problem size goes down by a factor of three over two。

How many times can I start with n and divide by3 over two until I get some small constant？

kind ofWell， okay， it's some kind of log。But what base？啊。Three over two。So log base B of N。

 what you should remember that means is if I start with n and I divide by B over and over again。

 how many times do I have to do that until I reach something one or smaller？😡。

Right flip it on its side。B to the K is the number I get when I start with one and I multiplyied by b K times。

So if I start with this number and I divide by B， that's going to be the inverse of the exponential function。

 that's going to be the log。Just so that we're on the same page here， what's done minimum depth。

 what's the depth of the minimum shallowest leaf？In this tree。So yeah。It's is log based three event。

Because again， every time I go down to the left。And starting with I'm dividing the problem size by three。

 so after log base three of N iterations of that， I'm going to be down to a problem size that's a small constant。

Now。There's a。A nice thing about big O notation。Which is。Up to big Os， those two things are the same。

Right one thing that maybe maybe you don't remember this from。

Your pre calculus classes in high school。What is this identity here。

 log base B of n is the same as log n your favorite base over log B with your favorite base。😡。

So log base3 of n is log of n over log of 3， and log of three is a constant。So that's big over in。So。

The right way to look at this from an algorithm's perspective is that the depth on the right。

And the depth。On the left。Are both big log in。It doesn't matter whether I'm conservative and expand the tree out。

Or I'm conservative in the other direction， and I cut the tree off。

That that would give me a lower bound in the running time。

 both of these are going to give me up to some constant factor log n。

 so either way the running time that I get。😡，Is。T of n is big of n log n。

OkayThis unbalanced is only an unbalanced by a constant factor。

 and so for big old purposes I can ignore it。The problem sizes are going down by constant factors at every level。

 that means the depth is going to be big over log n。

Different constants give me different basis for the log。

 but that all gets swallowed up in a bit go in the end。Yes。In practice。

These constant factors start to matter the bigger that window is that I assumed。

 so if I assumed in the middle half or in the middle 90% or in the middle 99。9%。

 I would still get N log N。Just as the window gets bigger and gets closer to the ends of the array。

 the big O constant in the N log end time crawls up and eventually sort of dominates the log。这个行的。不是。

华为的。Right， so the green depth on the left gives you an overestimate the running time。

It's at most n times log base three halves of n。The red thing if you cut off the tree at the shallowest leaf。

 gives you an underestimate of the runtime， which is also n log base3 of n。

 but these over and under estimatess differ by only a constant factor。

 so if you wanted to use theta and notation to describe the worst case running time here。

 you'd say theta of n log n， the green gives you the big O。

 the red gives you the big omega combine those give theta。Yeah。诶っ大。啊。は啊急的。好。Okay。

 so let me explain to you what I mean when I write big O of something。

Because this is usually defined。As a class of functions。

 and I believe this is the wrong way to look at this。Then I wroteB O of N。

This is an anonymous function。F' of N。Such that the limit as n goes to infinity of f of n over n is constant。

Not less than equal to。It is finite。It is a function。So it's not a set of functions。

 it is one function that I am saying， the only thing I'm going to tell you about this function is this limit。

😡，So this is very much in the same spirit as when you're talking about numbers and you're right even。

This is an anonymous even number， the only information I know about this number is that it is even it is visible by two。

Right but this I'm going to write down the information that I know and that's it so I can write say things like even plus odd is odd。

So given an anonymous， even numbered， an anonymous odd number on and I have them。

 I get an odd number。So that's how I'm using BigO。本然。

This anonymous function is the running time of partition。So it is fixed。

Every time I write every occurrence。Of the symbol big O O is its own unique but single anonymous function。

 yes。Yes。Then you't need to change your notation。Bye。All right。Now。

This provides some intuition that as long as your partitions are reasonably balanced。

Then the running time of the algorithm is going to be in log n。

there are more ways that you can firm up this intuition。

 like in particular if you choose your pivot randomly， then with very high probability。

 the running time of the algorithm is going to be in log N。

 meaning it is more likely that the running time is going to be less than 10 n log n than sorry。

 it's less likely that it will exceed 10N log n than that your computer will spontaneously combust。

Yes， so why would you。Consider quick sort thing in comparison to like merge server and guarantee that log。

And in this case scenario， you have to。Choose in the middle part of this to actually get an that outcome。

I'm not sure I understand the question。Like with merge story。

 you guarantee the analog log in because you're sliding into。

Put into two and you're guaranteeing a balanced tree， whereas this you have an unbalanced tree in it。

It's equivalent in theory but in practice it would so so let me say a little bit here about theory versus practice。

 the reason why merge sort works out is you're in complete control of the problem sizes。

And so you can choose， I'm going to make this problem size n over two and this problem size n over two。

 and I get it perfectly balanced for cursion treat and log'll get done。For Quick sort。

 you only have indirect control of the problem size。

You pick some pivot and you hope that it lands in the middle。And if you choose it at random。

 then that hope is fulfilled most of the time and so that's good enough。

Or if the data is reasonably random， then that hope is fulfilled often enough。In an actual practice。

 the constant factors in merge sort are larger than the constant factors in Quick sortt。

So if you've got reasonably well distributed data， QuickSot is actually more efficient in practice except on the rare occasion when it ist。

 then it sucks。So theory is important but it is also important to remember these things in the proper context。

嗯。So if I can keep my pivots reasonably balanced， I could actually modify Quicksort somehow。

And if I could intelligently choose the pivot， I could guarantee in the worst case that Quick Startt runs in in log N time。

😡，And so a very natural question is， can I actually do that， can I choose a pivot？

That is always guaranteed to be in the middle， and surprisingly the answer is yes。You can。

And the way that I'm going to do this is I'm going to describe an algorithm that's a very hint of quick sort called Quick select。

😡，What Quick selectlect does is it finds given an array and given an integer K。

 it finds the K smallest element of the array。Okay， so。returnturn。Okay case。Smallest。Yian a。

So if k is one， quick selectlect returns the minimum element， if k is n。

 quick selectlect returns the maximum element， if k is n over two。

 Quick selectlect returns the median element。And the way Quick Selectlect works is than they might suggest。

 this is also sometimes called one armed Quick sort。Is I take my array， I choose a pivot。A partition。

Using exactly the same subroutine as。嗯。Good sort。OkayAnd let's suppose that my target value of k is over here。

😡，All right。So I'm looking for K and it's， I don't know about an over4。

And my pivot value happens to end up after partitioning somewhere about N over two。Well。

 then I know that the value I'm looking for isn't in the right sub。

So I only need to recurse on the left。On the other hand。If my。呃。

The target index target rank K is fairly large。It's larger than the rank of the pivot after doing partition。

Then I know that the target value I'm looking for belongs to the right subet。

So I only have to recurarse on the right， I don't have to recurarse on the left。On the other hand。

 there's a small change here。Says if I'm looking for the Kate' smallest element in the original array。

 and then I throw out these R elements that I know are too small to be the K' smallest element in the array。

 the number of elements that I have left。😡，The rank of the element I have left in that right subaret is no longer K。

 it's Caman is all。嗯。So。This is not sorting the entire array。

 I'm just trying to find one element that would be at a specific position if I did sort the array。

So for the median， I want to find the element that lives right in the middle。

But to make this a real recursive procedure， I need to generalize the problem slightly from just looking for the median to looking for some arbitrary right K。

So I choose a pivot somehow。I partition the array using that pivot and then I compare the rank of the pivot after the partition to the rank that I'm actually searching for。

If the rank of the pivot is equal to K， R is equal to K。

 then the pivot element is the thing I'm looking for and I return it。

 that's the end else in the last line of the code。😡。

If the rank of the pivot is smaller than the rank that I'm looking for。

 then I need to recurse on the right， but I need to adjust。

The rank within the right subproblem is now smaller than rank in the original right。

If the rank that I'm looking for is smaller than the rank of the pivot。

 then I need to only recurse on the left， but I keep the same rank， yes。Yeah。

 I'm leaving that unspecified for now just like I did quickly。Right。Okay。

Because we're going to find a special way of choosing the pivot。And it's going to involve。Recursion。

Okay。So if you grind through the analysis for this， you get， okay， t of n is big o of n。

 that's the time to do the partition。😡，Now in order to do the worst case behavior。

 it's not that I'm going to recurse on the left and recurse on the right。

 so I'm not going to get t of r minus1 plus t of n minus r。It's going to be the worst of those two。

So this is going to be the max of t of r minus one and t of n minus r and again this is also max over all possible values of r not surprisingly this is going to come out to be。

N squared。So remember， the reason I put a max here instead of a plus is I'm only making one recursive call。

 but from the outside， if all I'm given about the problem is that integer N。

 I have no idea whether that recursive call is going to be in the larger piece or the smaller piece of the array。

So it was soon endorsed。And sure enough， if I always choose as my pivot element。

 the smallest element in the array。😡，Unless that's my target rank。

 in which case I always choose the largest element of the array。

Then this algorithm really will run in an n square time。On the other hand。

 if I could magically assume。That n over three R is this in2 n over three。

Then I would get a slightly more interesting recurrence。This would be。

 this is it most big of n plus t of 2 n over three。

IfIf my pivot rank is in the middle third of the array， then I know that when I recur。

 I'm going to recurse on a subproble， a subarray that has at most two thirds of the original elements。

😡，Might be on the right， might be on the left， doesn't matter sizes at most2/3s。This recurrence。

Is gives you a recursion tree that's just a single path。Going down goes n two and over three。

4 and number nine。So on， so the recurrence， the recursion tree looks like this。

It's a single descending geometric series。Now。I could write down the formula for geometric series。

 but the punchline is when you've got a geometric series like this that is always going down。

 the only term that actually matters up to Big O is the root。

Remember like one plus a half plus a fourth plus an eighth plus a 16th plus a 30 second and so and that's equal to two。

 even if I sum all the way down to infinity。Okay， because I'm cutting the numbers in half every time。

Up to constant factors only the largest term actually matters。

 and so this comes out to be linear time。If I can run quick select。

And somehow magically choose to pivot。To be somewhere in the middle。

Then I can choose any arbitrary ranked element in my array in linear time。

 so in particular I could choose a pivot that's somewhere in the middle of the array in linear time to pass to quick sort。

😡，But now you notice I've done this circular thing if I could somehow choose the right pivot for Quick sort I get N log N。

 how do I do that well I run Quick selectlect， but then I need to somehow magically choose the right pivot for Quickselect。

So。In order to choose the right pivot， I have to choose the right pivot。Yeahh， that's not ice。

So I'm going to use the magic of recursion。This。See this stuff in red？

The stuff in red is choose a pivot， everything else is the same。All right。

 just squint over the stuff in red else， pick a pivot somehow。

 I'm calling the pivot mom instead of P， but this is variable names and then I do the partition and then I do the three way if then else always making one recursive call。

The question is， how did I choose my pivot and sos。I'm going to walk through an example。

Because I think walking through the example is going to be more informative than looking at the pseudocode so here。

Is an array。Containing in random order， the integer is  zero through 99。表。Yeah。

 so select is taking over the job with select mom select is an example of quick select where I've specified how to choose the pivot。

嗯。哎。So I'm going to take this array of size 100， and I'm going to split it up into 20 blocks to size5。

And for purposes of illustration， I'm going to write those blocks vertically。

 but you should remember in actual memory， this is just a contiguous array of 100 things。你。So the。

This is just kind of bookkeeping。The first thing I'm going to do is for each of those blocks of size five。

 I'm going to find the median of that block， now I'm not doing this recursively。😡，Given five things。

 how do I find the median？I'll sort them in order one time and look in the middle。Brew force。

I've got a constant size problem， I can solve it in constant time。

So what I've done here is for each of these blocks。I have sorted the block。

And then the median of the block goes up right here in the third row。In green。So far。

I've spent linear time。For each of those n over five blocks。I spent constant time。

Sorting that single block of size five。😡，And so the median of that block sits right there in the middle。

So total time so far as order N， there have been no recursive calls yet。

Now I'm going to make a recursive call。And what I'm going to do recursse on。Is within this array。

Size 20。I'm going to recursively compute。The median。There it is 44。and remember。

 because when I'm recursing when I'm computing the median as a side effect。

 I also learn what things are bigger than the median。

 those are all marked in pink and what things are smaller than the median。

 those are all colored in blue。Blue for less because L is the second whether or blue。

R for greater because r is the second letter of greater。Red。Like in this case， just as。

Recursion ferry。The recursion ferry computed the median。Back away， don't touch， don't open the box。

Somebody else computed the median。Okay， you this problem you get these n over five elements somehow。

 and then you hand it to the median ferry， please compute the median goes 44， thank you。都。

Like if you wanted to write this out， you can say a media of list and then done。

If I wanted her to write this out。I would say。Hey， for each of those n over five blocks。

 write the median of that block into this new arrayM and then select the median of that arrayM。😡。

That's the line in red。Okay。😊，All right， so I've chosen my median of medians， median of medians， mom。

 MOM。And mom says， you know what？Mom's going to partition the entire array。

So not just the middle road， but absolutely everything in the array is going to be partitioned。

 so again， all of the stuff that is smaller then the median will be median of medians smaller than mom is going to be colored blue and everything bigger than mom is' going to be colored in pink yes there's your mama jokeking here tell it in your own head。

All right， so mom says， great， I partitioned the array now you're looking for the in this case。

 suppose you're looking for the median of this array now because this is numbers zero through 99。

 I know that the median is actually 50。So the median is bigger than mom。

And so now the quick select algorithm is going to recurse。

On an array containing all of the pink stuff。How does that happen， the recursionry。

 the selection fairry does it？It's another recursive call。No of my business。Now。

 the interesting thing about mom。Is that even though I chose mom by only looking at a subset of the data。

 I can argue that mom is actually fairly close to the middle of the array and the argument goes like this。

 I'm going to rearrange the blocks here so that all of the smaller medians are to the left of mom and all of the larger medians are to the right of mom。

Okay I've just rearranged the data， I haven't changed any of the colors。😡，But now you'll notice。

If you look at this picture。That everything。Above and the left of mom。Is smaller。And everything。

Below into the right of mom。Is bigger。So。In about half of the columns。

I've got three things that are definitely smaller than mom。And in about half of the columns。

 I've got three things that are definitely bigger than mom。So that means that。

Mom is sitting in this range where maybe， you know， in the I've got at least。

Three and over 10 things that I know are smaller than mom。And I have at least。

3N over 10 things that are bigger than mom。So mom isn't right in the middle？

But she's in the middle 40% of the array。I can identify 30% of the array that's too small。

 and I can identify 30% of the array that's too big。Yes。好。

The rearrangement happens in your head for purposes of analysis。😡。

The algorithm does not actually rearrange the data。

 I'm just rearranging it to show you this three10s of the array that's too small and three/ tenth of the array that's too big。

😡，What actually happens is just all of the blue stuff gets pushed to the beginning of the array。

 all the pink stuff gets pushed to the end of the array。有。It havecur on the partition。

Partition array1。How do we keep track of which values are pink， which values are blue？

Pink means to the left of the pivot after the part yes， the data structure is called an array。

So remember， what partition actually does is it puts the bigger stuff on the right side of the pivot and the smaller stuff on the left side of the pivot。

 I'm using colors to represent bigger than and less than the pivot。

 but in actuality you just rearranged the data。And so here are the data structures you need。

They arise， yeah。So in the worst case， what happens with bomb Select is that only the things in the upper left quadrant are blue or only the things in the lower right quadrant or pink。

In which case， mom is sitting at exactly either three in over 10 or seven n over 10。嗯。

So if I now plug this into my recurrence。Let's see what actually happens here now。T of N， well。

 I spent linear time finding the median of those five element blocks。

 and I called partition once that took linear time， everything else is recursive calls。

The first recursive call I made。Was to find the median of medians。That list of and over five medians。

 I said， hey， recursion fair， give me the meaning of that。So that took T of n over five times。

And then I use the median of medians as my high level pivot for partitioning。

And I know that I'm going to throw away at least three and over 10 of my input elements when I recurse。

 so in the worst case。😡，I have。sorry seven n over 10 elements left。So I get this。Recurrence。

So let's figure out how to solve this recurrence。Well， in the top level thing， I have N work。

In my left child， I have n over five work and in my right child， I have seven n over 10。My left left。

I have n over 25 here， I have7 n over 25 here I have7 n over 25 here I have。49 and over。呃。Oh， sorry。

 that's not 70 over 25。That should be seven and over 50。And this is 49 n over 100。

Every time I go down to the left， I divide my problem size by five。Every time I go down to the right。

 I divide my problem size by 10 over seven。Either way。

 my problem sizes are going down by some kind of constant factor。If I sum up along the levels。

They're starting to go down， so the top level， the root， I'm doing N work， but at level one。

 the children of the root， if I add up those two values， I get something less than n。

Get nine in over10。If I walk through the arithmetic cure carefully。I'll get 81 and over 100。

And so the pattern that falls out here is every level of the recursion tree。

 the amount of work I do is only 90% of the work I did in the previous level。

So I have a descending geometric series。Even if I let this tree run out to infinity。

 this geometric series that I get along the levels is only going to add up to some constant times n。

 I think in this case the constant' is going to be about 10。But。

The punchline is this is a linear time algorithm。I got a descending geometric series in my Le sums。

So only the root matters， only the largest term in that geometric series actually matters。

So this is the case of the recursionary method that you really like。

RightWhere you do some work to do divides and conquers and reduce to sub problems。

 but in the process of doing it， you make the total sizes of your sub problemsblem。Smaller。

By constant factor， not each subproblem， just that。

 but the total size of your subproblems has gone down by a constant factor。

 then you'll get this nice descending geometric series and you'll get you know the root will dominate the rh time。

ok。😊，U。Now there are a couple of questions that people tend to ask when I present this algorithm。

 the most common which is，huh， what， what just happened？U， this is。

Probably the most complicated algorithm you will see all semester in terms of like at least the intuitively complicated what's going on because there's this real temptation whenever you see recursion to try to open the box and go。

 what happens in here？The moment you do that， at least when I was learning this。

 the moment I did that， I found myself， what I'm just overwhelmed by all the details。

The thing that the way to actually think about this really is。I break the a chunks of size five。

 I find the median of each chunk， okay， so far this is all just， okay。

 I can't do this in linear time and then magically the recursion fairy gives me the median of those medians。

And okay， thank you and then I partition the array and then magically I either recurs in the blue stuff or I recurs in the pink stuff。

And because the recursive calls work。I can argue that the whole algorithm works。

I start opening the boxes， gets weird because I'm doing recursion for two different reasons。

So it gets really confusing really fast。Yeah。We get the median of medians in linear time plus one recursive call。

We get the medians。In linear time。It's the median of that requires the recursive call。Okay。

So this algorithm was。😡，Described by Daniel Boon。Bob married。Vughone black。Ron reverseed。

And Bob Tarjn。In the 1970s。I'm going to highlight all of the names。Here。😔，Actually， no。

 I'm going to highlight four of the names。The four names that I've highlighted have each won Tring awards。

These are brilliant people。I want to reassure you。That no one is expecting me to come up with an algorithm like this。

And I'm certainly not expecting you to come up with an algorithm like this。

This is really is like an impressive piece of work。

UWhat I do want you to get out of this is this partly recursion is this really powerful tool。

And partly。That the reason why this whole thing works so well is because when you get to the recursion tree analysis。

Everything falls into this nice descending series。Now there's another question that is lurking in at least one person's mind。

 let's see if we can get it out， yeah。Yes。Its。Yes二。Yes。我家。就我的自己。Another think better are selected。

So from now on， whenever you're asked， whenever you see a problem where， oh。

 I need to pick out the median of some set， linear time， this algorithm done。

It's all you have to say you don't have to reinvent the algorithm。

 you don't have to come up with your own， there may be other algorithms that you will need to come up with some sort of recursive structure for like the homework。

😡，But if it's helpful to use this algorithm as a subroutine。

 you have complete license to use this algorithm as a subroutine。Yes。

We're throwing out at least three and over 1 elements。So if we recurse on the right。

 we know that the left side had at least three and over 10 in it， if we recurse on the left。

 we know that the right side had at least three and over 10 in it。

 so we know what it was left with it most seven over 10。YeahSo this album divides by five every time。

 but can it be done。byGreat question that was the one I was waiting for， why did we choose five？

And the answer is five is the smallest value where this analysis works out。

To be a descending geometric series。In Prairie learn in an unfortunately not particularly well written question。

 I apologize for that， you'll walk through what happens if you try to use three instead of five。Okay。

It turns out that you end up with a recurrence t of n is t of n over3 plus t of 2 n over three。😡。

So you're not actually descending， you're doing the same amount of work at every level， why not four。

 well with four， you can do it as long as you're careful to break ties when you say media do you't mean the second smallest or the second largest。

And if you don't do it the right way。You end up with N log end time， if you do it the right way。

 you end up with N。And with two， it just doesn't work。

So five was the number I chose because that's the smallest value that makes the analysis work out the way I want。

Yeah。对。在说对。Thats okay。Yeah， so over a T of n over five。

 that is the time to compute mom given this array of n over five mediumns。Okay。

So we only have a little bit of time left， so the last example I'm going to go through。

 I am going to go through relatively quickly， we're going to see this you know applications of this idea in lab。

Tomorrow， but I'm going to go back to the really the first recorded algorithm。U。

You did this in elementary school。This is multiplication。

This particular example comes out of the first printed mathematics textbook in Europe。

The Tvisso arithmetic， which was published at sometime in the early 1400s。

 but it's exactly the same algorithm that you learned in fourth or fifth grade。You know。

 you take each digit。And you multiply it by the other vendor and you write that partial product down and you leave some gaps when you look at higher order digits of the multiple canned。

U。And then you sum those things up。By the way， that thing that you see over on the left。

 that's a check sum。So。TheSo over here on the right， these individual digits， those are check sums。

 so use some of the digits mod something and you use that as a sanity check。

This was already done in the 1400s。Um so。If you're given two endigit numbers。😡，嗯。

The standard schoolbook algorithm for multiplying two endit numbers takes n squared time because at some point during the algorithm point to your favorite digit of factor one。

 point to your favorite digit of factor two， you had to multiply those two digits。

And there's a bunch of overhead to doing the addition。

 but it all works out to be bigger over than squared。So in the 1950s。

 a Russian mathematician named Kl Maggorov decided， you know， hey。

I think this is the best you can do， I think this is in fact absolutely the fastest multiplication algorithm。

 there is no way in the world you can actually multiply numbers faster than N squared time。

 obviously you have to multiply every digit in one factor by every digit in the other and so he decided to organize a seminar where he would try to prove this conjecture that this is the fastest algorithm to do multiplication。

And one of the things that came out of this seminar is a recursive algorithm。😡，So if I write X。

This is an array of digits， but I'm going to write the array to split it into two smaller arrays。

That represent values A， B， C and D， so this is a times 10 to some number plus B。

 and this is C times 10 to some number plus D。And so if I wanted to multiply x by y。

 maybe some kind of divide and conquer algorithm would work where I've reduced to multiplying set of n digit numbers reduced to multiplying n over two digit numbers。

 so I can write here， for example， x Y is AC times 10 to the 2M plus a D times 10 to the M plus BC times 10 to the M plus BD。

😡，So I've reduced one multiplication of two indigent numbers to four multiplications。

OfN over two digit numbers， multiplying a decimal number by 10 to the something is really easy。

 I just write it over here and put some zeros， so that's not really multiplication it's just shifting。

If I want to think about this as pseudocode， there it is。But。In what you get。

It's an algorithm that satisfies this running time recurrence。

I'm spending linear time splitting up the arrays， multiplying by 10， doing the addition。

 but most of the algorithm is spent in recursive calls。

 there are four recursive calls each working with numbers that have N over two digits。

Okay so we can write out the recursion tree for that recurrence and would'll do the same thing wed always do with recursion trees。

 which is we sum up along the levels。There's n okay， sum along the first level。

4 times n over two is2 n。呃哦。4 n。This is not good。The work that I'm doing at each level is going up by a constant factor。

 so it's a geometric series and so I know the only the largest term actually matters。

But the largest term is now down in the leaves。So the term that matters here is 2 to the L times n。

 where L is the lowest level of the recursion tree。What is L？What's the depth of this tree？ワべ他れで。

Every time I go down a level， I double。If I go down at L levels， I double L times。N， then2 n， then4N。

Okay， so the the total depth of this treaty is log based two of n。

 so the running time of my algorithm is。Up to big O2 to the log base 2 of n times n。

 what is2 to the log base2 of n？And。😡，N squared， and so Kmogrov said，C。There's no escaping quadratic。

And so one of his the undergrads at the seminar went home。And he said， you know what， actually？Oh。

I was reading this thing that Gauss wrote back in the 1800s where he used this trick for multiply and complex numbers。

And he did the following thing， so I'm going to you know again。

 10 to the MA plus B and y is 10 to the MC plus D。So I have to multiply A by C。

 and I have to multiply B by D， but one of the things that Gauss noticed。

Is that this this middle thing， AD plus Bc， I can write。呃。Well。

 I can compute it in this weird way and just look let's just multiply。

The sums forget the powers of1 for a moment。This is AC C plus AD plus BC C plus BD。

And we've already computed this。😡，And we've already computed that。So。

It really looks like I only need to do three recursive calls。Not four。

By just doing a little bit more arithmetic。This was Anatoli de Cartubba。Yes。

When did AC and B get completed？How that line six and seven in Nu carpet？

A is just the number represented by the first half of the digits。

 B is the number represented by the second half of the digits in the array that represents x。

Remember under， these are arrays of digits。Right， so。So I only have to do three recursive calls。

Not for。Guss used this trick back in the 1800s， he never published it， but he left voluminous notes。

 Gaus was kind of a jerk so let's give credit to Car Subber for this one。

And so you end up with a running time recurrence。But again， the overhead to do this is linear time。

 but now I'm only doing three recursive calls。Now right away。

 I can guess that this is going to be faster because instead of doing order n plus four recursciive calls I order n plus three recursive calls。

 clearly， I'm doing less work。But let's do the math。They're right out the recursion tree。啊。

Zero fl and doing end work。The top level， I'm doing3N over two work。At the next level。

 I'm doing nine and over four work and in general at level L。

I'm doing three hves to the L times n word。So my work is still going up geometrically when I go from the different levels of recursion。

But it's only going up by a factor of three over two。On the other hand。

 my problem size is dropping still by a factor of two。

 so the depth of this tree is still log based to a end。So my overall running time is going to be。

Well。This kind of sucks。嗯。Three halves to the log base two of n times n， oh God。

 what is this madness， but I want you to remember。啊。诶。This。

This is one of the things you should probably just write on your cheat sheet。

This is one of those log identities that comes up over and over again。

 write this on your cheat sheet。These are both equal to， let's say。

 E to the natural log of a times natural log of C over natural log of B。All right， yeah。

so I can rewrite that as。N to the log base two of three hs times then。

 which I can simplify a little log base two of three。

Minus1 times n is big o of n to the log base two of three。Now log base two of three is。嗯。

And to the 1。61 something。So it's still bigger than linear， but it's definitely less than quadratic。

And so Kartsuba came into Komogorov's office and said， you know， I think actually， I'm not sure。

 I know you're really confident about this， I think I can beat un squared and Komogorov looked at it。

And immediately said seminar canceled。But then he went to the Russian Academy of Sciences and said。

 look what my student found。So it all worked out in the end there is an algorithm that can multiply two end digit numbers in N log end time this was discovered in 2019。

B forward it transforms your friend， number theory use your friend。

Group theory is your friend in practice， Python actually uses Cartuba's algorithm to multiply numbers that have more than 10 digits。

so to other big number of packages， so this is a real thing that actually gets used and is actually faster provided your numbers are big enough。

In lab， we'll play around more with this。But we're out of time， so thank you and see you on Tuesday。

algorithm， how big are the constants？😊，How big do you need to？



![](img/51f3e953ad2fbc109d0ba00e9c2f8701_6.png)